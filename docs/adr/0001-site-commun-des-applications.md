# 1. Un site commun pour les applications de sport

- Statut : Accepté
- Date : 2026-10-22

## Contexte

Lionel Coquin publie deux applications de sport :

- **Step Challenge** : défis de pas entre amis, sur Google Play en test fermé. Son site (Hugo) est dans son dépôt (`site/`) et publié sur l'hébergement OVH sous `step.architech.lu` (ADR 0005 de Step Challenge) : présentation, aide, FAQ, pages légales, plus la page des liens d'invitation (`/i/<code>`) et le fichier `/.well-known/assetlinks.json` des App Links.
- **CountRep** : saisie des répétitions quotidiennes, application web et bientôt application Android sur Google Play. Google Play demande une politique de confidentialité et une page de suppression de compte, accessibles sans l'application (ADR 0016 de CountRep). CountRep n'a pas encore de site.

Faire un deuxième site sur le modèle du premier dupliquerait les gabarits, le style et le déploiement, et chaque nouvelle application en ajouterait un.

Contraintes de Step Challenge :

- les App Links `https://step.architech.lu/i/…` sont compilés dans l'application : ce nom doit continuer à servir `/i/` et `assetlinks.json` ;
- les URL des pages légales de `step.architech.lu` sont déclarées dans la Play Console et chez Huawei, dont un examen est en cours : elles ne doivent pas changer avant d'avoir été remplacées dans ces consoles.

## Décision

1. **Un site commun, `sport.architech.lu`**, dans un dépôt public dédié (`architech-sport`), généré par Hugo avec les gabarits, le style et le déploiement repris du site de Step Challenge.
2. **Une section par application** (`/countrep/`, `/step-challenge/`), avec sa présentation, son aide et ses pages légales. L'en-tête du fichier `_index` de la section décrit l'application (logo, liens, mentions) ; l'en-tête et le pied de page des pages de la section en dépendent. L'accueil présente les applications.
3. **Mêmes règles que le site de Step Challenge** : anglais à la racine et français sous `/fr/`, adresses en `.html`, sitemap unique, aucun service tiers (ni statistiques, ni polices, ni scripts externes, ni cookie), contenu en Markdown sans HTML brut.
4. **Hébergement** : multisite OVH, dossier `sport`, déployé par une GitHub Action en SFTP, avec le même garde-fou (fichier marqueur propre à ce site).
5. **`step.architech.lu` reste en place pour l'instant**, publié depuis le dépôt de Step Challenge : liens d'invitation, App Links et pages légales déclarées. Le contenu de Step Challenge est aussi publié sous `sport.architech.lu/step-challenge/`. La bascule (déclarer les nouvelles URL dans les consoles, puis réduire `step.architech.lu` aux liens d'invitation, aux App Links et à des redirections) fera l'objet d'un ADR distinct, une fois l'examen Huawei terminé.
6. **Contact commun** : `support@architech.lu`.

## Conséquences

- Une nouvelle application demande seulement une section, son logo et son texte.
- CountRep a ses pages légales sans attendre : `https://sport.architech.lu/countrep/privacy.html` et `…/countrep/delete-account.html`, à déclarer dans la Play Console et dans l'écran de consentement Google.
- **Pendant la transition, le contenu de Step Challenge existe en deux exemplaires** (`step-challenge/site` et ce dépôt) : une modification doit être faite dans les deux, jusqu'à la bascule.
- Les URL de ce site sont déclarées aux magasins d'applications : un changement de structure doit garder les anciennes adresses.
