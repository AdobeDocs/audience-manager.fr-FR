---
description: Les étiquettes d’exportation de données fonctionnent avec les contrôles d’exportation que vous définissez sur une source de données. Les étiquettes d’exportation de données vous empêchent d’ajouter des caractéristiques restreintes à un segment et d’envoyer des données de segment à une destination. Vous pouvez définir plusieurs étiquettes d’exportation sur un nouveau cookie ou une destination URL existante ou un cookie ou une destination URL.
seo-description: Les étiquettes d’exportation de données fonctionnent avec les contrôles d’exportation que vous définissez sur une source de données. Les étiquettes d’exportation de données vous empêchent d’ajouter des caractéristiques restreintes à un segment et d’envoyer des données de segment à une destination. Vous pouvez définir plusieurs étiquettes d’exportation sur un nouveau cookie ou une destination URL existante ou un cookie ou une destination URL.
seo-title: Ajouter ou modifier des segments pour les destinations serveur à serveur
solution: Audience Manager
title: Ajouter ou modifier des segments pour les destinations serveur à serveur
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---


# Ajouter ou modifier des segments pour les destinations serveur à serveur {#add-edit-segments}

Vous pouvez uniquement ajouter ou modifier des segments pour une destination ([!DNL S2S]) serveur à serveur. Vous ne pouvez pas créer [!DNL S2S] de destinations avec [ !UICONTROL [Destination Builder](/help/using/features/destinations/destination-builder.md)]. Contactez votre consultant pour configurer [!DNL S2S] des destinations. Suivez ces instructions pour ajouter ou modifier des segments pour une [!DNL S2S] destination.

<!-- destination-s2s-edit.xml -->

Pour ajouter ou modifier des mappages de segments pour une [!DNL S2S] destination :

1. Allez à **[!UICONTROL Audience Data > Destinations]**. Sélectionnez Plateformes **intégrées > Basé sur** les périphériques et recherchez la destination [!DNL S2S] à utiliser.
2. Dans la [!UICONTROL Action] colonne, cliquez sur l’icône représentant un crayon pour modifier la destination.
   * Dans la **[!UICONTROL Search and Add Segments]** zone, début en saisissant le nom d’un segment ou en cliquant sur **[!UICONTROL Browse All Segments]** parcourir une liste de segments disponibles.
   * Cliquez **[!UICONTROL Add Selected Segments]** lorsque vous trouvez le segment à utiliser. Ajouter un segment ouvre la [!UICONTROL Edit Mapping] fenêtre.
   * Dans [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Définissez une valeur pour la paire [](../../features/destinations/key-value-pairs.md) clé-valeur utilisée par cette destination.
      * **[!UICONTROL Start Date]** et **[!UICONTROL End Date]**: Choisissez un début et une date de fin pour la destination. Si la date de fin est vide, la destination n’expire jamais.
3. Cliquez sur **[!UICONTROL Save]** , puis sur **[!UICONTROL Done]**.