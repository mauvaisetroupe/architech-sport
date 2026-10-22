---
title: Politique de confidentialité — CountRep
linkTitle: Confidentialité
description: Les données collectées par CountRep, pourquoi, et comment les supprimer.
updated: 22 octobre 2026
---

*Traduction de la version anglaise, qui fait foi en cas de divergence.*

CountRep est une application pour noter ses répétitions quotidiennes
d'exercices au poids du corps et à l'élastique. Elle existe en
application Android et en application web, à l'adresse
[countrep.architech.lu](https://countrep.architech.lu).

## 1. Utiliser CountRep sans compte

CountRep fonctionne entièrement sans compte. Dans ce cas, tout ce que tu
saisis (saisies, séances, choix des exercices, réglages) est enregistré
**uniquement sur ton appareil**, dans le stockage de l'application (ou
celui du navigateur, pour l'application web). Rien n'est envoyé au
serveur de CountRep, et l'application ne lui fait aucune requête.

Ces données restent sur l'appareil jusqu'à ce que tu les effaces, que tu
désinstalles l'application ou que tu effaces les données du navigateur
pour l'application web.

## 2. Données collectées quand tu te connectes

La connexion est facultative. Elle sert à sauvegarder tes données et à
les synchroniser entre tes appareils.

### Informations du compte

La connexion se fait avec un compte Google. À la connexion, Google
transmet à l'application un jeton d'identité signé. De ce jeton, CountRep
ne conserve que :

- l'identifiant technique et stable du compte Google (le « subject »
  OpenID Connect), qui permet de reconnaître l'utilisateur à sa connexion
  suivante ;
- le prénom du compte Google, affiché à l'utilisateur dans les réglages
  de l'application. Il n'est montré à personne d'autre.

CountRep **ne conserve pas** l'adresse e-mail, la photo de profil ni
aucune autre information du compte Google, et n'accède à aucun service
Google au nom de l'utilisateur.

Après la connexion, l'application garde sur l'appareil un jeton de
session, valable 7 jours et renouvelé tant que l'application est
utilisée. Le serveur ne tient pas de liste des sessions.

### Données d'entraînement

Une fois connecté, l'application synchronise avec le serveur de CountRep :

- les **saisies** : l'exercice, le nombre de répétitions (ou de
  secondes), la date et l'heure et, pour une saisie faite pendant une
  séance, l'identifiant et le nom de la séance ;
- les **séances** : leur nom, leur nombre de séries, leurs exercices et
  leurs répétitions ;
- le **choix des exercices** : les exercices proposés sur l'écran de
  saisie, et leur ordre.

CountRep n'accède à aucune autre donnée de santé ou d'activité physique,
et ne lit pas les données d'autres applications.

### Données techniques

Comme tout serveur web, le serveur de CountRep enregistre des journaux
techniques des requêtes reçues (date, adresse demandée, adresse IP, code
de réponse). Ils servent uniquement à faire fonctionner et à sécuriser le
service, et sont conservés pour une durée limitée.

## 3. Utilisation des données

Les données servent uniquement aux fonctions de CountRep : saisie,
journal, statistiques, séances, sauvegarde et synchronisation entre les
appareils de l'utilisateur.

Elles ne servent ni à la publicité, ni au profilage, ni au marketing, ni
à des fins médicales. CountRep ne contient ni publicité, ni statistiques
d'audience, ni pistage par des tiers.

## 4. Partage des données

CountRep ne vend pas de données personnelles et ne les partage ni avec
des annonceurs, ni avec des courtiers en données, ni avec d'autres tiers.

Aucun autre utilisateur ne voit tes données : CountRep n'a pas de
fonction sociale.

Les données peuvent être traitées par les prestataires techniques
nécessaires au service (hébergement et protection du réseau), pour ce
seul usage.

## 5. Conservation et suppression

Les données synchronisées sont conservées tant que le compte existe.

Tu peux supprimer ton compte CountRep à tout moment depuis
l'application : **Réglages → Compte et sécurité → Supprimer mon
compte**. Cela supprime immédiatement et définitivement, sur le serveur,
le compte, son lien avec le compte Google, son prénom et toutes ses
données d'entraînement (saisies, séances, choix des exercices). Les
données enregistrées sur l'appareil sont effacées en même temps.

Les autres appareils encore connectés au compte supprimé sont
déconnectés ; les données qu'ils contiennent restent sur ces appareils.

Sans l'application, tu peux supprimer ton compte depuis l'application
web, ou en faire la demande par e-mail. Les deux démarches sont décrites
sur la [page de suppression de compte]({{< relref "/countrep/delete-account" >}}).

## 6. Sécurité

Les données circulent par des connexions chiffrées (HTTPS). Des mesures
techniques et organisationnelles raisonnables protègent les données de
CountRep contre l'accès, la modification, la divulgation ou la
destruction non autorisés.

## 7. Tes droits

Selon la loi applicable sur la protection des données, tu peux avoir
notamment le droit :

- d'accéder à tes données personnelles ;
- de faire corriger des données inexactes ;
- de faire supprimer tes données personnelles ;
- de retirer ton consentement quand le traitement repose sur celui-ci ;
- de limiter certains traitements ou de t'y opposer ;
- à la portabilité de tes données, le cas échéant.

Pour exercer ces droits, contacte-nous (voir la section Contact).

## 8. Enfants

CountRep n'a pas vocation à collecter sciemment des informations
personnelles d'enfants en violation de la loi applicable.

## 9. Modifications de cette politique

Cette politique peut évoluer quand CountRep ajoute des fonctionnalités ou
quand les exigences légales ou techniques changent.

La dernière version est toujours publiée à l'adresse de la politique de
confidentialité communiquée aux utilisateurs et aux plateformes
d'applications.

## 10. Contact

CountRep est développée et exploitée par **Lionel Coquin**, à titre
personnel, responsable du traitement des données personnelles traitées
par l'application et son serveur.

**CountRep — Lionel Coquin**\
E-mail : **support@architech.lu**
