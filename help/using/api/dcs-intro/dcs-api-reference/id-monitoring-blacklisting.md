---
description: Le serveur de collecte de données contrôle les identifiants qu’il reçoit et met en liste noire ceux qui sont envoyés à un taux inhabituellement élevé sur une courte période.
keywords: id;surveillance;liste noire;dcs
seo-description: Le serveur de collecte de données contrôle les identifiants qu’il reçoit et met en liste noire ceux qui sont envoyés à un taux inhabituellement élevé sur une courte période.
seo-title: Surveillance des identifiants et liste noire
solution: Audience Manager
title: Surveillance des identifiants et liste noire
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# Surveillance des identifiants et liste noire

Le [!UICONTROL DCS] contrôle les identifiants qu’il reçoit et met en liste noire ceux qui sont envoyés à un taux inhabituellement élevé sur une courte période de temps.

## Aperçu

Pour protéger l’infrastructure d’Audience Manager contre les activités malveillantes, l’ [!UICONTROL DCS] utilisateur utilise un algorithme avancé pour surveiller les identifiants qu’il reçoit. Il peut s’agir [!UICONTROL Data Provider Unique User ID]de[!UICONTROL CRM ID]s ( [!UICONTROL Audience Manager Unique User ID]s),[!UICONTROL AAM UUID]s ( [!UICONTROL Experience Cloud ID]s) ou[!UICONTROL ECID]s (s). Voir [Index des ID dans Audience Manager](../../../reference/ids-in-aam.md) pour obtenir des explications détaillées sur les ID pris en charge par Audience Manager.

Le [!UICONTROL DCS] contrôle la fréquence à laquelle il reçoit ces identifiants pour détecter une activité malveillante potentielle. Lorsque le [!UICONTROL DCS] détecte un nombre inhabituellement élevé de [!UICONTROL DCS] requêtes pour un ID donné en peu de temps, cet ID est mis sur liste noire.

## Codes d’erreur

Vous pouvez identifier les ID placés sur liste noire en fonction des codes d’erreur reçus de la [!UICONTROL DCS]. Les codes d’erreur que vous pouvez recevoir sont les suivants :

* 303 : ID client bloqué ;
* 306 : ID de périphérique déclaré bloqué ;
* 307 : Opération de profil bloquée pour ID.

Pour plus d’informations sur les codes d’erreur que vous pouvez recevoir, voir Codes d’erreur [DCS, Messages et Exemples](dcs-error-codes.md) .

## Annulation de la liste noire

Les identifiants placés sur liste noire ne doivent pas être utilisés dans les futures demandes, car ils conduiront à des rapports de données incorrects. L’ [!UICONTROL DCS] application ne prend pas en charge la non-mise en liste noire des ID.

## Impact sur la synchronisation des identifiants

[!UICONTROL DCS] peuvent inclure un ou plusieurs types d’ID. Les appels contenant un seul ID sont complètement ignorés si cet ID est mis sur liste noire et qu’aucune synchronisation des identifiants ne se produit dans ce cas.

Lorsqu’un appel à plusieurs identifiants inclut également un identifiant sur liste noire, l’ [!UICONTROL DCS] utilisateur ignore l’identifiant sur liste noire et utilise uniquement les identifiants restants non placés sur liste noire pour la synchronisation.

## Causes et correctifs de la liste noire des identifiants

La raison la plus fréquente de la mise sur liste noire des identifiants est la mauvaise intégration entre l’infrastructure du client et Audience Manager. Lorsque vous identifiez un identifiant sur liste noire, veillez à examiner minutieusement vos intégrations d’Audience Manager. Voir les guides **d’** implémentation et d’intégration pour obtenir des explications détaillées sur la configuration d’Audience Manager pour une utilisation avec d’autres solutions Experience Cloud ou des systèmes externes.

Une autre cause fréquente d’ID placés sur liste noire est l’indexation des robots (moteurs de recherche Web), qui entraîne généralement une augmentation du trafic, ce qui entraîne l’envoi multiple des mêmes identifiants [!UICONTROL DCS] . Si vous identifiez les robots d’indexation comme étant la raison de la liste noire des identifiants, vous devez restreindre l’accès des robots à votre site Web.

Si vous avez du mal à identifier les problèmes d’intégration, n’hésitez pas à contacter le service clientèle. Avant d’ouvrir une demande d’assistance, veillez à conserver l’ `.har` archive `HTTP` de votre navigateur prête. Cette archive permet à l’équipe d’assistance d’identifier les raisons pour lesquelles la liste noire des identifiants a eu lieu.