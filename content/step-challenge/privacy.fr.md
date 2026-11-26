---
title: Politique de confidentialité — Step Challenge
linkTitle: Confidentialité
description: Les données collectées par Step Challenge, pourquoi, et comment les supprimer.
updated: 25 novembre 2026
---

*Traduction de la version anglaise, qui fait foi en cas de divergence.*

Step Challenge est une application de comptage de pas et de défis qui
permet à ses utilisateurs de suivre leurs pas quotidiens et de
participer à des défis de pas.

## 1. Données collectées

Step Challenge ne collecte que les données nécessaires à la fourniture
de ses services.

### Informations de compte

Les utilisateurs se connectent à Step Challenge avec leur compte Google.
Lors de la connexion, Google fournit à l'application un jeton d'identité
signé. De ce jeton, Step Challenge ne conserve que :

- l'identifiant technique et stable du compte Google (le « subject »
  OpenID Connect), qui sert à reconnaître l'utilisateur à sa connexion
  suivante ;
- un nom affiché choisi par l'utilisateur, visible des autres
  participants. L'application propose le prénom du compte Google, que
  l'utilisateur peut modifier avant de l'enregistrer, puis à tout
  moment.

Step Challenge ne conserve **pas** l'adresse e-mail de l'utilisateur, sa
photo de profil ni aucune autre information de son compte Google, et
n'accède à aucun service Google en son nom.

Après la connexion, l'application conserve un jeton de session dans le
stockage sécurisé de l'appareil (Android Keystore). Le serveur ne
conserve qu'une empreinte cryptographique de ce jeton.

### Données de pas

Avec l'autorisation de l'utilisateur, Step Challenge peut lire le nombre
de pas enregistré par la plateforme de santé disponible sur son
appareil.

Sur Android, Step Challenge utilise **Santé Connect** (Health Connect)
pour lire les pas enregistrés par le téléphone ou par des appareils et
applications compatibles (par exemple Garmin, Samsung ou Xiaomi). Step
Challenge ne demande qu'un accès en lecture aux données de pas. Avec
l'autorisation de l'utilisateur (« Accès aux données en arrière-plan »),
il les lit aussi environ toutes les 6 heures quand l'application n'est
pas ouverte, pour que les amis voient des pas à jour dans le classement.
Cette autorisation peut être retirée à tout moment dans les paramètres
de Santé Connect.

L'utilisateur peut choisir à la place **HUAWEI Health**,
qui reçoit les pas des montres et bracelets qui s'y synchronisent, sur tout téléphone
Android. Step Challenge lit alors les pas par **HUAWEI Health Kit** (voir
la section 3). Une seule source est utilisée à la fois, au choix de
l'utilisateur dans les paramètres de l'application.

Sur les appareils Android sans Santé Connect (par exemple les téléphones
Huawei), la version distribuée sur Huawei AppGallery peut lire à la
place le **podomètre du téléphone** (un capteur du téléphone), avec
l'autorisation de l'utilisateur (« Activité physique »). Step Challenge
ne le lit que lorsque l'application est ouverte, et ne garde sur le
téléphone que le dernier relevé et le total du jour ; seul le nombre de
pas quotidien est envoyé au serveur. Cette autorisation peut être
retirée à tout moment dans les paramètres Android de l'application.

Les données de pas peuvent comprendre :

- le nombre de pas enregistré pour une journée donnée ;
- la date associée à ce nombre de pas ;
- pour une journée, ses minutes actives, très actives et inactives,
  calculées sur le téléphone à partir des pas de chaque minute. Les pas
  minute par minute restent sur le téléphone : seuls ces trois totaux
  par jour sont envoyés au serveur.

Step Challenge ne demande pas l'accès à d'autres informations de santé,
comme la fréquence cardiaque, le sommeil, la tension artérielle, les
mesures corporelles ou des informations médicales, sauf si un tel accès
est explicitement décrit dans une version future de l'application.

### Amis, invitations et blocages

Pour que chaque utilisateur ne voie que les pas de ses amis, le serveur
conserve :

- les amitiés entre deux comptes, et leur date de création ;
- les invitations : leur auteur, leurs dates de création et d'expiration
  (7 jours) et leur nombre d'utilisations. Seule une empreinte
  cryptographique du code d'invitation est conservée, jamais le code
  lui-même ;
- les surnoms qu'un utilisateur donne à ses amis, visibles de lui seul ;
- les blocages : le compte bloqué et son nom affiché au moment du
  blocage.

### Signalements

Lorsqu'un utilisateur en signale un autre, le serveur conserve les
comptes de l'auteur du signalement et de la personne signalée, le nom
affiché signalé au moment du signalement, le motif, un commentaire
facultatif rédigé par l'auteur et, le cas échéant, l'invitation par
laquelle la personne signalée a été vue. Les signalements servent
uniquement à la modération du service. La personne signalée n'est pas
prévenue, et ne sait jamais qui l'a signalée.

## 2. Utilisation des données de pas

Les données de pas servent uniquement au fonctionnement de Step
Challenge, notamment :

- afficher le nombre de pas quotidien de l'utilisateur ;
- afficher l'historique et les statistiques de pas ;
- calculer les minutes actives et le score d'activité ;
- calculer les résultats des défis et des classements ;
- synchroniser les nombres de pas avec le service Step Challenge.

Les données de pas ne sont utilisées ni à des fins de publicité, ni de
profilage, ni de marketing, ni à des fins médicales.

Les données de pas obtenues par HUAWEI Health Kit ne sont ni vendues ni
partagées avec des tiers pour leurs propres besoins de publicité ou de
profilage.

## 3. HUAWEI Health Kit

Lorsque l'utilisateur choisit HUAWEI Health comme source de ses pas, il
se connecte avec son compte HUAWEI et autorise Step Challenge à lire ses
pas. Cette connexion passe par HMS Core, l'application de services de
Huawei, et demande l'identifiant du compte HUAWEI, son profil de base,
la lecture des pas et, si l'utilisateur l'accepte, la lecture des pas du
mois précédant son autorisation (sans elle, HUAWEI Health ne donne que
les pas enregistrés depuis l'autorisation). Step Challenge ne demande
aucune autre donnée de HUAWEI Health.

Les pas sont lus dans le cloud de Huawei, où l'application HUAWEI Health
les a synchronisés, par l'interface de HUAWEI Health Kit. Step Challenge
les lit à l'ouverture de l'application, et peut aussi les lire
régulièrement quand elle n'est pas ouverte, pour que les amis voient des
pas à jour. Pour la courbe d'une journée dans les statistiques, elle lit
aussi les pas heure par heure de cette journée, quand l'appareil qui
compte les pas les a envoyés à HUAWEI Health ; ce détail est affiché sur
le téléphone et n'est pas envoyé au serveur.

La lecture se fait sur le téléphone. Le jeton d'accès délivré par Huawei
y reste : il n'est jamais envoyé au serveur de Step Challenge. Step
Challenge ne conserve ni l'identifiant ni le profil du compte HUAWEI :
seuls les nombres de pas quotidiens sont envoyés au serveur, comme avec
Santé Connect.

Les données traitées par Huawei (compte HUAWEI, HUAWEI Health, cloud de
Huawei) relèvent de la politique de confidentialité de Huawei.

L'utilisateur peut retirer cette autorisation dans les paramètres de
confidentialité et d'autorisations de HUAWEI Health ou de son compte
HUAWEI, ou revenir à Santé Connect dans les paramètres de Step
Challenge.

Si l'autorisation est refusée ou retirée, Step Challenge ne peut plus
récupérer de nouvelles données de pas depuis HUAWEI Health Kit. Les
données déjà synchronisées peuvent rester conservées par Step Challenge
jusqu'à leur suppression conformément à la présente politique.

## 4. Synchronisation avec les serveurs de Step Challenge

Lorsque la synchronisation est activée, Step Challenge envoie les
nombres de pas quotidiens de l'utilisateur, et les minutes actives, très
actives et inactives des derniers jours, au serveur de Step Challenge.

Le serveur conserve les nombres de pas associés au compte Step Challenge
de l'utilisateur, afin que l'application puisse :

- synchroniser les données entre appareils ;
- tenir l'historique des pas et du score d'activité ;
- calculer les défis ;
- fournir les classements.

Le serveur ne reçoit pas l'ensemble de la base de données HUAWEI Health
de l'utilisateur. Step Challenge ne traite que les informations de pas
nécessaires à l'application.

## 5. Partage des données

Step Challenge ne vend pas de données personnelles.

Dans l'application, le nom affiché et les nombres de pas quotidiens d'un
utilisateur ne sont visibles que de ses amis, de même que ses badges et
son niveau, calculés à partir de ses pas. Le nom affiché est aussi
visible de toute personne qui ouvre un de ses liens d'invitation. Les
minutes actives et le score d'activité ne sont visibles que de
l'utilisateur.

Step Challenge ne partage pas les données de pas avec des annonceurs,
des courtiers en données ou d'autres tiers à des fins de publicité ou de
profilage.

Les données de pas peuvent être traitées par les prestataires techniques
nécessaires au fonctionnement de l'application et de son
infrastructure, le cas échéant, et uniquement pour les besoins de la
fourniture du service.

## 6. Durée de conservation

Step Challenge ne conserve les données de pas synchronisées que le temps
nécessaire au fonctionnement de l'application, notamment l'historique
des pas, les défis et les statistiques.

L'utilisateur peut supprimer son compte Step Challenge à tout moment
depuis l'application : **Plus → Compte → Supprimer mon compte**. Cette
action supprime immédiatement et définitivement, sur le serveur, le
compte, son nom affiché, son lien avec le compte Google, ses sessions,
tout son historique de pas et ses badges. Les données de pas enregistrées dans Santé
Connect ou HUAWEI Health sur l'appareil ne sont pas concernées.

La suppression du compte supprime aussi ses amitiés, les surnoms qu'il a
donnés et reçus, ses invitations et ses blocages.

Les signalements traités sont supprimés 12 mois après leur traitement.
Les signalements faits par un compte supprimé, ou le concernant, sont
conservés jusque-là sans lien avec ce compte ; ils contiennent toujours
le nom affiché signalé et le commentaire.

L'utilisateur qui n'a plus accès à l'application peut demander la
suppression de son compte et des données associées sur le serveur par
e-mail (voir la section Contact). Les deux procédures sont décrites sur
la [page de suppression de compte]({{< relref "/step-challenge/delete-account" >}}).

Les données conservées localement sur l'appareil de l'utilisateur
peuvent aussi être supprimées en désinstallant l'application ou en
utilisant les fonctions de suppression de données qu'elle propose.

## 7. Sécurité

Des mesures techniques et organisationnelles raisonnables protègent les
données de Step Challenge contre l'accès, la modification, la
divulgation ou la destruction non autorisés.

## 8. Tes droits

Selon la législation applicable en matière de protection des données,
les utilisateurs peuvent disposer notamment des droits suivants :

- accès à leurs données personnelles ;
- rectification des données inexactes ;
- effacement de leurs données personnelles ;
- retrait du consentement lorsque le traitement repose sur le
  consentement ;
- limitation de certains traitements ou opposition à ceux-ci ;
- portabilité des données, le cas échéant.

Les utilisateurs peuvent aussi retirer à Step Challenge l'accès aux
données de HUAWEI Health dans les paramètres d'autorisations de HUAWEI
Health ou de l'appareil.

## 9. Protection des enfants

Step Challenge n'a pas vocation à collecter sciemment des informations
personnelles d'enfants en violation de la législation applicable.

## 10. Modifications de cette politique

Cette politique de confidentialité peut être mise à jour lorsque Step
Challenge introduit de nouvelles fonctionnalités ou lorsque les
exigences légales ou techniques évoluent.

La dernière version est toujours publiée à l'adresse de la politique de
confidentialité communiquée aux utilisateurs et aux plateformes de
distribution d'applications.

## 11. Contact

Pour toute question sur cette politique de confidentialité, sur les
données personnelles ou pour toute demande concernant tes données,
contacte :

Step Challenge est développé et exploité par **Lionel Coquin**, à titre
de particulier, responsable du traitement des données personnelles
traitées par l'application et son serveur.

**Step Challenge — Lionel Coquin**\
E-mail : **support@architech.lu**

## 12. Open source

Le code source de l'application et du serveur Step Challenge est public,
sous licence GNU Affero General Public License (AGPL-3.0), afin que
chacun puisse vérifier la façon dont les données sont traitées :
[github.com/mauvaisetroupe/step-challenge](https://github.com/mauvaisetroupe/step-challenge).
