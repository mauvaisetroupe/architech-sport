---
title: Santé Connect
description: Autoriser Step Challenge à lire tes pas dans Santé Connect, sur n'importe quel téléphone Android.
weight: 1
---

Sur Android, Step Challenge lit tes pas dans **Santé Connect** (Health
Connect), le point central des données de santé d'Android. Santé Connect
rassemble les pas comptés par ton téléphone et par les applications de
montres et de sport qui y écrivent (Garmin Connect, Samsung Health,
Zepp, Mi Fitness et bien d'autres).

Step Challenge demande seulement à **lire tes pas** : aucune autre donnée
de santé.

## 1. Vérifier que Santé Connect est disponible

- **Android 14 et plus récent** : Santé Connect fait partie du système.
  Tu le trouves dans les paramètres du téléphone (cherche « Santé
  Connect »).
- **Android 13 et plus ancien** : installe
  l'[application Santé Connect](https://play.google.com/store/apps/details?id=com.google.android.apps.healthdata)
  depuis Google Play.

## 2. Autoriser l'accès à tes pas

La première fois que Step Challenge lit tes pas, Android affiche l'écran
d'autorisation de Santé Connect. Autorise **Pas**.

Si tu as refusé, ou pour vérifier :

1. Ouvre **Santé Connect** (paramètres du téléphone, puis cherche « Santé
   Connect »).
2. Va dans **Autorisations des applis**, puis **Step Challenge**.
3. Active **Pas**.

Le nom des menus peut varier légèrement selon la marque du téléphone et
la version d'Android.

## 3. Laisser ta montre écrire dans Santé Connect

Si tu comptes tes pas avec une montre, son application doit **envoyer**
tes pas à Santé Connect. Dans l'application de la montre (Garmin Connect,
Samsung Health, Zepp, Mi Fitness…), cherche Santé Connect dans les
paramètres et autorise l'écriture des **Pas**.

> **Tes pas sont dans HUAWEI Health ?** HUAWEI Health n'envoie pas ses données à Santé
> Connect. Consulte l'[aide HUAWEI Health]({{< relref "/step-challenge/help/huawei" >}}).

## 4. Vérifier dans l'application

- L'ouverture de l'application met à jour les pas du jour. L'application
  synchronise aussi en arrière-plan, environ toutes les 6 heures.
- S'il manque des pas : onglet **Plus**, **Diagnostic**, **Lancer le
  diagnostic**. Il vérifie Santé Connect, l'autorisation et
  la connexion au serveur.

## 5. Mes pas sont comptés en double

Certains jours, Step Challenge affiche bien plus de pas que l'application
de ta montre (par exemple 50 000 au lieu de 16 000) ? Step Challenge
recopie ce que contient Santé Connect : c'est là que les pas sont en
trop. Pour le vérifier, ouvre **Santé Connect**, **Données et accès**,
**Pas**, et regarde le jour concerné.

La cause la plus fréquente : l'application de la montre compte **aussi**
les pas du téléphone, et additionne les deux avant de les envoyer à
Santé Connect. Santé Connect ne peut alors plus les départager.

1. **Ne laisse que la montre dans son application.** Retire-lui le
   podomètre du téléphone : paramètres du téléphone, **Applications**,
   l'application de la montre (Mi Fitness, par exemple), **Autorisations**,
   **Activité physique**, **Ne pas autoriser**. Si le téléphone apparaît
   parmi ses appareils, retire-le aussi.
2. **Laisse Santé Connect départager.** Si tu veux aussi les pas du
   téléphone (les jours sans montre), qu'il les envoie lui-même à Santé
   Connect. Puis dans **Santé Connect**, **Données et accès**,
   **Activité**, **Pas**, **Sources et priorité des données**, mets
   l'application de la montre en premier : Santé Connect garde ses pas
   et ne prend ceux du téléphone que lorsque la montre n'a rien compté.
3. **Supprime les pas en trop.** Dans Santé Connect, retire d'abord à
   l'application de la montre l'autorisation d'écrire les pas (sinon elle
   peut les réécrire), supprime ses pas des jours concernés, puis rends-lui
   l'autorisation et synchronise la montre.
4. **Corrige Step Challenge.** Onglet **Plus**, **Source des pas**,
   **Relire mes 30 derniers jours** : Step Challenge te montre les jours
   qui changent, même à la baisse, et ne remplace qu'après ton accord.
   Pour un jour plus ancien, écris-nous.

Toujours bloqué ? Consulte la [FAQ]({{< relref "/step-challenge/faq" >}}) ou écris à
[support@architech.lu](mailto:support@architech.lu).
