---
description: Le serveur de collecte de données contrôle les identifiants qu’il reçoit et ajoute ceux qui sont envoyés à un taux inhabituellement élevé sur une courte période à une liste bloquée.
keywords: id;monitoring;dcs
seo-description: Le serveur de collecte de données contrôle les identifiants qu’il reçoit et ajoute ceux qui sont envoyés à un taux inhabituellement élevé sur une courte période à une liste bloquée.
seo-title: Surveillance et Liste bloquée des identifiants
solution: Audience Manager
title: Surveillance et Liste bloquée des identifiants
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# Surveillance et Liste bloquée des identifiants

[!DNL DCS] contrôle les identifiants qu’il reçoit et ajoute ceux qui sont envoyés à un taux inhabituellement élevé sur une courte période à une liste bloquée.

## Présentation

Pour protéger l&#39;infrastructure d&#39;Audience Manager contre les activités malveillantes, [!DNL DCS] utilise un algorithme avancé pour surveiller les identifiants qu&#39;il reçoit. Il peut s&#39;agir de [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) ou [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Voir [Index des identifiants dans Audience Manager](../../../reference/ids-in-aam.md) pour obtenir des explications détaillées sur les identifiants pris en charge par l&#39;Audience Manager.

[!DNL DCS] surveille la fréquence à laquelle il reçoit ces identifiants pour détecter une activité malveillante potentielle. Lorsque [!DNL DCS] détecte un nombre inhabituellement important de demandes [!DNL DCS] pour un identifiant donné en peu de temps, cet identifiant est ajouté à une liste bloquée.

## Codes d’erreur

Vous pouvez identifier les identifiants ajoutés à une liste bloquée par les codes d&#39;erreur reçus de [!DNL DCS]. Les codes d&#39;erreur que vous pouvez recevoir sont les suivants :

* 303 : ID client bloqué ;
* 306 : ID de périphérique déclaré bloqué ;
* 307 : Opération de profil bloquée pour ID.

Voir [Codes d’erreur, messages et exemples du serveur de collecte de données](dcs-error-codes.md) pour plus d’informations sur les codes d’erreur que vous pouvez recevoir.

## Suppression d’identifiants des listes bloquées

Les identifiants qui ont été ajoutés aux listes bloquées ne doivent pas être utilisés dans les futures requêtes, car ils conduiront à un rapports de données incorrect. [!DNL DCS] ne prend pas en charge la suppression des identifiants des listes bloquées.

## Impact sur la synchronisation des identifiants

[!DNL DCS] les appels peuvent inclure un ou plusieurs types d’ID. Les appels contenant un seul ID sont complètement ignorés si cet ID est ajouté à une liste bloquée et qu’aucune synchronisation d’ID ne se produit dans ce cas.

Lorsqu’un appel à plusieurs identifiants inclut également un identifiant placé sur la liste bloquée, [!DNL DCS] ignore l’identifiant refusé et n’utilise que les autres identifiants autorisés pour la synchronisation.

## Causes et correctifs pour l’Liste bloquée des identifiants

La cause la plus fréquente d’ajout d’identifiants aux listes bloquées est la mauvaise intégration entre l’infrastructure client et l’Audience Manager. Lorsque vous identifiez un identifiant placé sur la liste bloquée, veillez à examiner minutieusement vos intégrations d’Audiences Manager. Voir **Guides d&#39;implémentation et d&#39;intégration** pour obtenir des explications détaillées sur la manière de configurer l&#39;Audience Manager pour qu&#39;elle fonctionne avec d&#39;autres solutions Experience Cloud ou systèmes externes.

Les robots d’indexation (moteurs de balayage Web) sont une autre cause fréquente d’ajout d’identifiants aux listes bloquées, ce qui entraîne généralement une augmentation du trafic, entraînant l’envoi multiple des mêmes identifiants à [!DNL DCS]. Si vous identifiez les robots d’indexation comme la raison pour laquelle des identifiants sont ajoutés aux listes bloquées, vous devez limiter l’accès des robots à votre site Web.

Si vous avez du mal à identifier les problèmes d’intégration, n’hésitez pas à contacter le service d’assistance clientèle. Avant d&#39;ouvrir une demande d&#39;assistance, veillez à conserver l&#39;archive `.har` `HTTP` de votre navigateur. Cette archive permet à l’équipe d’assistance d’identifier la raison pour laquelle l’identifiant a été ajouté à une liste bloquée.