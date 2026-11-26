---
title: HUAWEI Health
description: Lire dans Step Challenge les pas synchronisés avec HUAWEI Health, sur un téléphone Android de n'importe quelle marque.
weight: 2
---

La plupart des montres envoient leurs pas à Santé Connect, où Step
Challenge les lit (voir l'[aide Santé Connect]({{< relref "/step-challenge/help/health-connect" >}})).
**HUAWEI Health, non** : ses données restent dans le cloud de Huawei.
Step Challenge peut les y lire, avec ton autorisation : c'est la source
**HUAWEI Health**.

Cette page s'adresse aux personnes dont la montre ou le bracelet se
synchronise avec **HUAWEI Health**, sur un téléphone Huawei ou d'une autre marque (Samsung, Google
Pixel, Xiaomi…).

## 1. Installer les applications de Huawei

Tu les as sans doute déjà, puisqu'elles servent à la montre :

1. **AppGallery**, la boutique d'applications de Huawei. Sur un téléphone
   d'une autre marque, télécharge-la depuis le site officiel de Huawei,
   [appgallery.huawei.com](https://appgallery.huawei.com/), puis
   installe-la (Android te demande d'autoriser l'installation depuis ton
   navigateur).
2. **HUAWEI Health**, depuis AppGallery : l'application
   qui associe et synchronise ta montre.
3. **HMS Core** (Huawei Mobile Services), depuis AppGallery. Il sert à te
   connecter à ton compte HUAWEI depuis Step Challenge. Il est souvent
   installé avec HUAWEI Health : vérifie qu'il est présent et à jour.

## 2. Vérifier que tes pas arrivent dans le cloud de Huawei

Step Challenge lit tes pas dans le cloud de Huawei, pas dans la montre.

1. Ouvre **HUAWEI Health** et vérifie que les pas de ta montre y
   apparaissent.
2. Dans HUAWEI Health, **Moi → Gestion de la confidentialité** : active
   la synchronisation avec le cloud.

## 3. Choisir HUAWEI Health dans Step Challenge

1. Onglet **Plus**, **Source des pas**.
2. Choisis **HUAWEI Health**, puis confirme.
3. Connecte-toi avec ton **compte HUAWEI** et autorise la lecture des
   pas. Seul le nombre de pas est lu, comme le décrit la
   [politique de confidentialité]({{< relref "/step-challenge/privacy" >}}).

Si HUAWEI Health est installé sur ton téléphone, l'Accueil de Step
Challenge te le propose aussi : **Utiliser HUAWEI Health**.

Les pas des 30 derniers jours sont relus dans HUAWEI Health. Un jour déjà
envoyé avec plus de pas garde sa valeur.

## Ce qui change avec HUAWEI Health

- Tes pas arrivent quand HUAWEI Health se synchronise avec le cloud,
  parfois avec quelques minutes de retard sur la montre. Ouvre HUAWEI
  Health si un chiffre te semble en retard.
- Step Challenge lit tes pas **quand tu l'ouvres** (et quand tu tires
  l'écran vers le bas pour actualiser) : pas encore en arrière-plan.
- Le détail minute par minute (courbe de la journée, inactivité,
  minutes actives) n'est pas disponible : Step Challenge le dit à chaque
  endroit concerné.

## Arrêter d'utiliser HUAWEI Health

Onglet **Plus**, **Source des pas**, **Retirer l'accès à HUAWEI
Health** (ou choisis **Santé Connect**). Step Challenge retire son accès
et relit tes pas dans Santé Connect. S'il n'y arrive pas, il te le dit :
retire-le toi-même dans HUAWEI Health, **Moi → Gestion de la
confidentialité**, dans les applications autorisées.

Les pas déjà envoyés restent dans Step Challenge ; pour les effacer,
supprime ton compte (**Plus**, **Compte**).

## Ça ne marche pas ?

- **Aucun pas, ou seulement ceux d'aujourd'hui** : vérifie l'étape 2,
  puis attends que HUAWEI Health se synchronise.
- **La connexion HUAWEI échoue** : mets à jour HMS Core depuis
  AppGallery, puis réessaie.
- **« Step Challenge n'a pas accès à tes pas dans HUAWEI Health »** :
  l'autorisation a été retirée dans HUAWEI Health, refusée, ou donnée
  sans la case des pas. Touche **Autoriser HUAWEI Health** et coche les
  pas.
- **« HUAWEI Health Kit est désactivé »** : dans HUAWEI Health, **Moi →
  Gestion de la confidentialité**, active **HUAWEI Health Kit**, puis
  touche **Réessayer**.
- **Pour aller plus loin** : onglet **Plus**, **Diagnostic**, **Lancer le
  diagnostic**. Il teste la connexion HUAWEI et la lecture des pas ; tu
  peux copier le résultat et l'envoyer au support.

Toujours bloqué ? Écris à [support@architech.lu](mailto:support@architech.lu).
