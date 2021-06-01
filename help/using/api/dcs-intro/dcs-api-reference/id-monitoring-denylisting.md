---
description: Le serveur de collecte de données surveille les ID qu’il reçoit et ajoute à une liste bloquée ceux qui sont envoyés à un taux exceptionnellement élevé sur une courte période.
keywords: id;monitoring;dcs
seo-description: Le serveur de collecte de données surveille les ID qu’il reçoit et ajoute à une liste bloquée ceux qui sont envoyés à un taux exceptionnellement élevé sur une courte période.
seo-title: Surveillance et Liste bloquée des identifiants
solution: Audience Manager
title: Surveillance et Liste bloquée des identifiants
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
exl-id: 8fd31b00-a822-4fd5-b6f5-7f20546da1d9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 0%

---

# Surveillance et Liste bloquée des identifiants

[!DNL DCS] surveille les ID qu’il reçoit et ajoute à une liste bloquée ceux qui sont envoyés à un taux exceptionnellement élevé sur une courte période.

## Présentation

Pour protéger l’infrastructure de l’Audience Manager contre les activités malveillantes, [!DNL DCS] utilise un algorithme avancé pour surveiller les identifiants qu’il reçoit. Il peut s’agir de [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), de [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) ou de [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Voir [Index des ID en Audience Manager](../../../reference/ids-in-aam.md) pour obtenir des explications détaillées sur les ID pris en charge par l’Audience Manager.

[!DNL DCS] surveille la fréquence à laquelle il reçoit ces ID pour détecter une activité malveillante potentielle. Lorsque [!DNL DCS] détecte un nombre inhabituellement important de requêtes [!DNL DCS] pour un ID donné dans un court laps de temps, cet ID est ajouté à une liste bloquée.

## Codes d’erreur

Vous pouvez identifier les identifiants ajoutés à une liste bloquée par les codes d’erreur reçus de [!DNL DCS]. Les codes d’erreur que vous pouvez recevoir sont les suivants :

* 303 : ID de client bloqué ;
* 306 : ID d’appareil déclaré bloqué ;
* 307 : Opération de profil bloquée pour l’ID.

Voir [Codes d’erreur, messages et exemples DCS](dcs-error-codes.md) pour plus d’informations sur les codes d’erreur que vous pouvez recevoir.

## Suppression d’identifiants des listes bloquées

Les identifiants qui ont été ajoutés aux listes bloquées ne doivent plus être utilisés dans les futures demandes, car ils généreront des rapports de données incorrects. [!DNL DCS] ne prend pas en charge la suppression des identifiants des listes bloquées.

## Impact sur la synchronisation des identifiants

[!DNL DCS] Les appels peuvent inclure un ou plusieurs types d’ID. Les appels contenant un seul identifiant sont complètement ignorés si cet identifiant est ajouté à une liste bloquée et qu’aucune synchronisation des identifiants ne se produit dans ce cas.

Lorsqu’un appel à plusieurs identifiants inclut également un identifiant placé sur la liste bloquée, la balise [!DNL DCS] ignore l’identifiant refusé et utilise uniquement les identifiants autorisés restants pour la synchronisation.

## Causes et correctifs de l’Liste bloquée des identifiants

La cause la plus fréquente d’ajout d’ID à des listes bloquées est la mauvaise intégration entre l’infrastructure client et l’Audience Manager. Lorsque vous identifiez un ID placé sur la liste bloquée, veillez à passer en revue minutieusement les intégrations de vos Audiences Manager. Voir les **Guides d’implémentation et d’intégration** pour obtenir des explications détaillées sur la manière de configurer l’Audience Manager pour qu’elle fonctionne avec d’autres solutions ou systèmes externes Experience Cloud.

Une autre cause fréquente d’ajouts d’ID aux listes bloquées est l’indexation des robots (moteurs de recherche Web), qui entraîne généralement une augmentation du trafic, entraînant l’envoi multiple des mêmes ID à [!DNL DCS]. Si vous identifiez des robots d’indexation comme motif de l’ajout d’identifiants à des listes bloquées, vous devez restreindre l’accès des robots à votre site web.

Si vous avez des difficultés à identifier les problèmes d’intégration, n’hésitez pas à contacter le service clientèle. Avant d’ouvrir une demande d’assistance, veillez à conserver l’archive `.har` `HTTP` de votre navigateur prête à l’emploi. Cette archive permet à l’équipe d’assistance d’identifier la raison pour laquelle l’identifiant a été ajouté à une liste bloquée.
