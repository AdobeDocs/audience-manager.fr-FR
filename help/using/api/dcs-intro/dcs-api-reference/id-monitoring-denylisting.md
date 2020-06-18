---
description: Le serveur de collecte de données contrôle les identifiants qu’il reçoit et ajoute ceux qui sont envoyés à un taux inhabituellement élevé sur une courte période à une liste bloquée.
keywords: id;monitoring;dcs
seo-description: Le serveur de collecte de données contrôle les identifiants qu’il reçoit et ajoute ceux qui sont envoyés à un taux inhabituellement élevé sur une courte période à une liste bloquée.
seo-title: Surveillance des identifiants et refus d’inscription
solution: Audience Manager
title: Surveillance des identifiants et refus d’inscription
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# Surveillance des identifiants et refus d’inscription

Il [!DNL DCS] contrôle les identifiants qu’il reçoit et ajoute ceux qui sont envoyés à un taux inhabituellement élevé sur une courte période à une liste bloquée.

## Aperçu

Pour protéger l’infrastructure d’Audience Manager contre les activités malveillantes, l’ [!DNL DCS] utilisateur utilise un algorithme avancé pour surveiller les identifiants qu’il reçoit. Il peut s’agir [!UICONTROL Data Provider Unique User ID]de s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) ou [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Voir [Index des identifiants dans l’Audience Manager](../../../reference/ids-in-aam.md) pour obtenir des explications détaillées sur les identifiants pris en charge par l’Audience Manager.

Le [!DNL DCS] contrôle la fréquence à laquelle il reçoit ces identifiants pour détecter une activité malveillante potentielle. Lorsque l’ [!DNL DCS] utilisateur détecte un nombre inhabituellement élevé de [!DNL DCS] requêtes pour un identifiant donné en peu de temps, cet identifiant est ajouté à une liste bloquée.

## Codes d’erreur

Vous pouvez identifier les identifiants ajoutés à une liste bloquée par les codes d’erreur reçus de la [!DNL DCS]. Les codes d&#39;erreur que vous pouvez recevoir sont les suivants :

* 303 : ID client bloqué ;
* 306 : ID de périphérique déclaré bloqué ;
* 307 : Opération de profil bloquée pour ID.

Voir Codes, messages et exemples [d’erreur](dcs-error-codes.md) DCS pour en savoir plus sur les codes d’erreur que vous pouvez recevoir.

## Suppression d’identifiants des listes bloquées

Les identifiants qui ont été ajoutés aux listes bloquées ne doivent pas être utilisés dans les futures requêtes, car ils conduiront à un rapports de données incorrect. Le [!DNL DCS] ne prend pas en charge la suppression des identifiants des listes bloquées.

## Impact sur la synchronisation des identifiants

[!DNL DCS] les appels peuvent inclure un ou plusieurs types d’ID. Les appels contenant un seul ID sont complètement ignorés si cet ID est ajouté à une liste bloquée et qu’aucune synchronisation d’ID ne se produit dans ce cas.

Lorsqu’un appel à plusieurs identifiants inclut également un identifiant de liste de refus, celui-ci [!DNL DCS] ignore l’identifiant refusé et n’utilise que les autres identifiants autorisés pour la synchronisation.

## Causes et correctifs de la désinscription des identifiants

La cause la plus fréquente d’ajout d’identifiants aux listes bloquées est la mauvaise intégration entre l’infrastructure client et l’Audience Manager. Lorsque vous identifiez un identifiant de liste refusée, veillez à examiner minutieusement vos intégrations d’Audiences Manager. Voir les guides **d’** implémentation et d’intégration pour obtenir des explications détaillées sur la manière de configurer l’Audience Manager pour qu’elle fonctionne avec d’autres solutions Experience Cloud ou systèmes externes.

Une autre cause fréquente d’ajout d’identifiants aux listes bloquées est l’indexation des robots (moteurs de balayage Web), qui entraîne généralement une augmentation du trafic, ce qui entraîne l’envoi à [!DNL DCS] plusieurs reprises des mêmes identifiants. Si vous identifiez les robots d’indexation comme la raison pour laquelle des identifiants sont ajoutés aux listes bloquées, vous devez limiter l’accès des robots à votre site Web.

Si vous avez du mal à identifier les problèmes d’intégration, n’hésitez pas à contacter le service d’assistance clientèle. Avant d&#39;ouvrir une demande d&#39;assistance, veillez à conserver l&#39; `.har` archive `HTTP` de votre navigateur prête. Cette archive permet à l’équipe d’assistance d’identifier la raison pour laquelle l’identifiant a été ajouté à une liste bloquée.