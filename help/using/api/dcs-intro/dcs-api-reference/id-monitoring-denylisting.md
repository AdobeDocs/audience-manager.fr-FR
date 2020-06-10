---
description: Le serveur de collecte de données contrôle les identifiants qu’il reçoit et ajoute ceux qui sont envoyés à un taux inhabituellement élevé sur une courte période à une liste de refus.
keywords: id;monitoring;dcs
seo-description: Le serveur de collecte de données contrôle les identifiants qu’il reçoit et ajoute ceux qui sont envoyés à un taux inhabituellement élevé sur une courte période à une liste de refus.
seo-title: Surveillance des identifiants et refus d’inscription
solution: Audience Manager
title: Surveillance des identifiants et refus d’inscription
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 92751df14777335744db69bfb0c9b7b2f9088785
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# Surveillance des identifiants et refus d’inscription

Il contrôle les identifiants qu’il reçoit et ajoute ceux qui sont envoyés à un taux inhabituellement élevé sur une courte période à une liste de refus. [!UICONTROL DCS]

## Aperçu

Pour protéger l’infrastructure d’Audience Manager contre les activités malveillantes, l’ [!UICONTROL DCS] utilisateur utilise un algorithme avancé pour surveiller les identifiants qu’il reçoit. Il peut s’agir [!UICONTROL Data Provider Unique User ID]de s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) ou [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Voir [Index des identifiants dans Audience Manager](../../../reference/ids-in-aam.md) pour obtenir des explications détaillées sur les identifiants pris en charge par Audience Manager.

Le [!UICONTROL DCS] contrôle la fréquence à laquelle il reçoit ces identifiants pour détecter une activité malveillante potentielle. Lorsque l’ [!UICONTROL DCS] utilisateur détecte un nombre inhabituellement élevé de [!UICONTROL DCS] requêtes pour un identifiant donné en peu de temps, cet identifiant est ajouté à une liste de refus.

## Codes d’erreur

Vous pouvez identifier les identifiants ajoutés à une liste de refus par les codes d’erreur reçus de la [!UICONTROL DCS]. Les codes d&#39;erreur que vous pouvez recevoir sont les suivants :

* 303 : ID client bloqué ;
* 306 : ID de périphérique déclaré bloqué ;
* 307 : Opération de profil bloquée pour ID.

Voir Codes, messages et exemples [d’erreur](dcs-error-codes.md) DCS pour en savoir plus sur les codes d’erreur que vous pouvez recevoir.

## Suppression d’identifiants des listes de refus

Les identifiants qui ont été ajoutés pour refuser des listes ne doivent pas être utilisés dans les futures requêtes, car ils conduiront à un rapports de données incorrect. Le [!UICONTROL DCS] ne prend pas en charge la suppression des identifiants des listes de refus.

## Impact sur la synchronisation des identifiants

[!UICONTROL DCS] les appels peuvent inclure un ou plusieurs types d’ID. Les appels contenant un seul ID sont complètement ignorés si cet ID est ajouté à une liste de refus et qu’aucune synchronisation d’ID ne se produit dans ce cas.

Lorsqu’un appel à plusieurs identifiants inclut également un identifiant de liste de refus, celui-ci [!UICONTROL DCS] ignore l’identifiant refusé et n’utilise que les autres identifiants autorisés pour la synchronisation.

## Causes et correctifs de la désinscription des identifiants

La cause la plus fréquente d’ajout d’identifiants pour refuser des listes est la mauvaise intégration entre l’infrastructure client et Audience Manager. Lorsque vous identifiez un identifiant de liste refusée, veillez à examiner minutieusement vos intégrations Audience Manager. Voir les guides **d’** implémentation et d’intégration pour obtenir des explications détaillées sur la configuration d’Audience Manager pour une utilisation avec d’autres solutions ou systèmes externes Experience Cloud.

Une autre cause fréquente d’ajout d’identifiants pour refuser des listes est l’indexation des robots (moteurs de balayage Web), qui entraîne généralement une augmentation du trafic, ce qui entraîne l’envoi à [!UICONTROL DCS] plusieurs reprises des mêmes identifiants. Si vous identifiez les robots d’indexation comme la raison pour laquelle des identifiants ont été ajoutés pour refuser des listes, vous devez limiter l’accès des robots à votre site Web.

Si vous avez du mal à identifier les problèmes d’intégration, n’hésitez pas à contacter le service d’assistance clientèle. Avant d&#39;ouvrir une demande d&#39;assistance, veillez à conserver l&#39; `.har` archive `HTTP` de votre navigateur prête. Cette archive permet à l’équipe d’assistance d’identifier la raison pour laquelle l’identifiant a été ajouté à une liste de refus.