# Architech Sport

Site public des applications de sport de Lionel Coquin, [CountRep](https://countrep.architech.lu) et [Step Challenge](https://github.com/mauvaisetroupe/step-challenge) : présentation, aide et pages légales (confidentialité, suppression de compte), en anglais et en français. Publié sur l'hébergement OVH sous `https://sport.architech.lu` ([ADR 0001](docs/adr/0001-site-commun-des-applications.md)).

Généré par [Hugo](https://gohugo.io), avec des gabarits maison, sans thème tiers. Aucun service tiers : ni statistiques, ni polices, ni scripts externes, ni cookie.

## Lancer en local

Installer **la version de Hugo figée dans la GitHub Action** (`hugo-version` dans [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml)), par exemple :

```bash
brew install hugo          # dernière version : vérifier avec hugo version
pip install hugo==0.167.0  # ou une version précise
```

Puis :

```bash
hugo server        # http://localhost:1313/, rechargé à chaque modification
hugo --minify      # construction complète dans public/ (ignoré par git)
```

## Structure

| Chemin | Contenu |
|---|---|
| `hugo.toml` | Configuration : langues, adresse du site, e-mail de contact |
| `content/_index.*.md` | Accueil : une carte par application, puis le texte de la page |
| `content/<app>/` | Une section par application (`countrep`, `step-challenge`) : présentation (`_index`), pages légales, FAQ, aide (`help/`) |
| `layouts/` | Gabarits : `baseof.html` (squelette), `home.html` (accueil), `section.html` (accueil d'une application, ou liste d'une sous-section comme l'aide), `page.html`, `home.sitemapxml.xml` (sitemap), `robots.txt` |
| `layouts/_partials/` | `app.html` (application de la page), en-tête, pied de page, boutons d'une application, sélecteur de langue et drapeaux (SVG intégrés), `url.html` (adresse sans `index.html` final) |
| `assets/css/site.css` | Feuille de style, minifiée et empreinte à la construction |
| `i18n/` | Textes des gabarits (`en.toml`, `fr.toml`) |
| `static/` | Copié tel quel : logos (`images/`), marqueur `.architech-sport-site` |
| `scripts/deploy-sftp.sh` | Envoi du site chez OVH en SFTP (voir « Déploiement ») |
| `docs/adr/` | Décisions d'architecture |

### Une section par application

Le fichier `_index` d'une section décrit l'application dans son en-tête : l'accueil, l'en-tête et le pied de page des pages de la section s'en servent.

```yaml
---
title: CountRep
description: …                  # résumé, aussi affiché sur la carte de l'accueil
weight: 1                       # ordre sur l'accueil
tagline: Log your daily reps    # sous-titre
logo: images/countrep.svg       # icône (en-tête, accueil, favicon)
playStoreUrl: https://…         # facultatif : bouton Google Play
webAppUrl: https://…            # facultatif : bouton de l'application web
sourceUrl: https://…            # facultatif : lien « Code source » du pied de page
status: Coming soon on Google Play.   # facultatif : mention sous les boutons
footerNote: CountRep — free, no ads.  # facultatif : ligne du pied de page
---
```

Le pied de page d'une application liste ses pages `privacy`, `agreement` et `delete-account` quand elles existent ; l'en-tête, ses pages `help` et `faq`.

Les logos sont dérivés des icônes des applications (SVG maîtres dans leurs dépôts, dossier `icons/`) : les régénérer si une icône change.

### Langues

- Anglais, langue par défaut, **à la racine** ; français sous `/fr/`. Aucune adresse en `/en/`.
- Adresses en `.html` (`uglyURLs`) : `content/countrep/privacy.en.md` donne `/countrep/privacy.html`, `content/countrep/privacy.fr.md` donne `/fr/countrep/privacy.html`. Ces adresses sont déclarées aux magasins d'applications : ne pas les changer.
- **Mêmes chemins dans les deux langues** : seul le préfixe `/fr` s'ajoute. Le nom du fichier fixe le chemin, le suffixe la langue.
- **Sitemap unique** `/sitemap.xml`, avec les pages des deux langues et leurs traductions (`hreflang`), annoncé par `/robots.txt`.
- Le drapeau de l'en-tête mène à la même page dans l'autre langue.
- Les versions françaises des pages légales sont des traductions ; la version anglaise fait foi (mention en tête de page).

## Ajouter une page

1. Créer les deux fichiers, avec le même nom : `content/countrep/guide.en.md` et `content/countrep/guide.fr.md` (ou `content/<app>/help/guide.*.md` pour une page d'aide).
2. En-tête de chaque fichier :

   ```yaml
   ---
   title: User guide           # titre de la page
   linkTitle: Guide            # facultatif : titre court dans les liens
   description: …              # résumé (moteurs de recherche, liste de l'aide)
   weight: 3                   # facultatif : ordre dans la liste de l'aide
   ---
   ```

3. Lier les pages entre elles avec `relref` et un **chemin absolu**, qui garde la langue et vérifie le lien à la construction : `[aide Huawei]({{</* relref "/step-challenge/help/huawei" */>}})`.
4. Vérifier avec `hugo server` que la page existe dans les deux langues et que le drapeau mène à la bonne page.

Le HTML brut est désactivé dans le Markdown (`unsafe = false`) : un besoin de mise en forme particulière passe par un gabarit ou un shortcode.

## Déploiement

La GitHub Action [`deploy.yml`](.github/workflows/deploy.yml) :

- sur une **pull request** : construit le site et vérifie la présence des pages déclarées aux magasins (contrôle seulement) ;
- sur un **push sur `main`** (ou lancement manuel) : construit, puis envoie `public/` chez OVH en **SFTP** avec [`scripts/deploy-sftp.sh`](scripts/deploy-sftp.sh) (lftp).

Tant que la configuration ci-dessous n'est pas complète, l'envoi est **sauté** (avec un avertissement) : la construction tourne, rien n'est envoyé.

### Comment se passe l'envoi

- **Chiffré et authentifié** : SFTP (port 22), et le serveur est reconnu par sa clé d'hôte (`SFTP_KNOWN_HOSTS`) ; une clé différente fait échouer l'envoi.
- **Miroir** : le dossier distant devient identique à `public/`. Les fichiers qui ne sont plus dans le site sont **supprimés** côté serveur.
- **Garde-fou** : le site contient un fichier `.architech-sport-site`. Le script refuse d'envoyer dans un dossier distant qui n'est ni vide ni marqué par ce fichier : une erreur de `SITE_REMOTE_DIR` ne peut pas effacer un autre site (par exemple celui de `step.architech.lu`).
- **Rien n'est commité** par l'action.

### Secrets et variables à créer

GitHub → dépôt → Settings → Secrets and variables → Actions :

| Nom | Type | Valeur |
|---|---|---|
| `FTP_SERVER` | Secret | Serveur SFTP de l'hébergement OVH (espace client OVH → Hébergements → onglet FTP - SSH, « Serveur FTP et SFTP »), sans `sftp://` ni port |
| `FTP_USERNAME` | Secret | Utilisateur FTP/SFTP |
| `FTP_PASSWORD` | Secret | Mot de passe de cet utilisateur |
| `SITE_REMOTE_DIR` | Variable | Dossier distant du site, relatif au dossier de connexion : `sport`. Doit être la racine du multisite `sport.architech.lu` dans OVH |
| `SFTP_KNOWN_HOSTS` | Variable | Clé d'hôte du serveur, obtenue une fois depuis un poste de confiance : `ssh-keyscan -p 22 <serveur>` (coller toutes les lignes). Ce n'est pas un secret |

Les secrets sont les mêmes que ceux du dépôt Step Challenge (même hébergement) ; seul `SITE_REMOTE_DIR` change.

### Envoyer à la main

Avec lftp installé, après `hugo --minify` :

```bash
export SFTP_HOST=… SFTP_USER=… REMOTE_DIR=sport
export SFTP_KNOWN_HOSTS="$(ssh-keyscan -p 22 "$SFTP_HOST")"
read -rs LFTP_PASSWORD && export LFTP_PASSWORD
scripts/deploy-sftp.sh
```

### Vérifier après le premier déploiement

```bash
SITE=https://sport.architech.lu
curl -sI $SITE/                                  # 200, accueil anglais
curl -sI $SITE/fr/                               # 200, accueil français
curl -sI $SITE/countrep/privacy.html             # 200, sans redirection
curl -sI $SITE/countrep/delete-account.html      # 200, sans redirection
curl -sI $SITE/step-challenge/privacy.html       # 200
```
