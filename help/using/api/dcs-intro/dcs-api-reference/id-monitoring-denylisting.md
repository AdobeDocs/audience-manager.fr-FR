---
description: Le serveur de collecte de données surveille les identifiants qu’il reçoit et ajoute à une liste bloquée ceux qui sont envoyés à un débit anormalement élevé sur une courte période.
keywords: id;surveillance;dcs
seo-description: The DCS monitors the IDs it receives and adds those that are being sent at an unusually high rate over a short period of time to a deny list.
seo-title: ID Monitoring and Denylisting
solution: Audience Manager
title: Surveillance et Liste bloquée des identifiants
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
exl-id: 8fd31b00-a822-4fd5-b6f5-7f20546da1d9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 0%

---

# Surveillance et Liste bloquée des identifiants

Le [!DNL DCS] surveille les identifiants qu’il reçoit et ajoute à une liste bloquée ceux qui sont envoyés à un taux anormalement élevé sur une courte période.

## Présentation

Pour protéger l’infrastructure d’Audience Manager contre les activités malveillantes, le [!DNL DCS] utilise un algorithme avancé pour surveiller les identifiants qu’il reçoit. Il peut s’agir de [!UICONTROL Data Provider Unique User ID]s) ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s) ([!UICONTROL AAM UUID]s) ou [!UICONTROL Experience Cloud ID]&#x200B;(s) ([!UICONTROL ECID]s). Voir [Index des identifiants dans Audience Manager](../../../reference/ids-in-aam.md) pour des explications détaillées des identifiants pris en charge par Audience Manager.

Le [!DNL DCS] surveille la fréquence à laquelle il reçoit ces identifiants pour détecter toute activité malveillante potentielle. Lorsque l’[!DNL DCS] détecte un nombre inhabituellement élevé de requêtes [!DNL DCS] pour un identifiant donné en peu de temps, cet identifiant est ajouté à une liste bloquée.

## Codes d’erreur

Vous pouvez identifier les identifiants ajoutés à une liste bloquée par les codes d’erreur reçus de l’[!DNL DCS]. Les codes d’erreur que vous pouvez recevoir sont les suivants :

* 303 : ID de client bloqué ;
* 306 : ID d’appareil déclaré bloqué ;
* 307 : opération de profil bloquée pour l’ID.

Voir [Codes d’erreur, messages et exemples DCS](dcs-error-codes.md) pour plus d’informations sur les codes d’erreur que vous pouvez recevoir.

## Suppression d’identifiants des listes bloquées

Les identifiants qui ont été ajoutés aux listes bloquées ne doivent pas être utilisés dans les futures demandes, car ils entraîneront des rapports de données incorrects. Le [!DNL DCS] ne prend pas en charge la suppression des identifiants des listes bloquées.

## Impact sur la synchronisation des identifiants

[!DNL DCS] appels peuvent inclure un ou plusieurs types d’ID. Les appels contenant un seul ID sont complètement ignorés si cet ID est ajouté à une liste bloquée, et aucune synchronisation d’ID ne se produit dans cette situation.

Lorsqu’un appel à identifiants multiples inclut également un identifiant placé sur la liste bloquée, le [!DNL DCS] ignore l’identifiant refusé et utilise uniquement les identifiants autorisés restants pour la synchronisation.

## Causes et correctifs de la Liste bloquée de l’ID

La cause la plus fréquente de l’ajout d’identifiants aux listes bloquées est l’intégration incorrecte entre l’infrastructure client et Audience Manager. Lorsque vous identifiez un identifiant placé sur la liste bloquée, veillez à passer en revue minutieusement vos intégrations Audience Manager. Consultez les **Guides de mise en œuvre et d’intégration** pour obtenir des explications détaillées sur la manière de configurer Audience Manager pour qu’il fonctionne avec d’autres solutions Experience Cloud ou systèmes externes.

Les robots d’indexation (robots d’exploration web) sont une autre cause fréquente d’ajout d’identifiants aux listes bloquées. Cela entraîne généralement une augmentation du trafic, ce qui entraîne l’envoi multiple des mêmes identifiants au [!DNL DCS]. Si vous identifiez les robots d’indexation comme la raison pour laquelle des identifiants sont ajoutés aux listes bloquées, vous devez restreindre l’accès des robots à votre site web.

Si vous avez du mal à identifier les problèmes d’intégration, n’hésitez pas à contacter le service clientèle. Avant d’ouvrir une demande d’assistance, veillez à conserver l’archive `.har` `HTTP` de votre navigateur prête. Cette archive permet à l’équipe d’assistance d’identifier la raison pour laquelle l’ID a été ajouté à une liste bloquée.
