---
description: Les étiquettes d’exportation de données fonctionnent avec les contrôles d’exportation que vous définissez sur une source de données. Les étiquettes d’exportation de données vous empêchent d’ajouter des caractéristiques restreintes à un segment et d’envoyer des données de segment vers une destination. Vous pouvez définir plusieurs étiquettes d’exportation sur un nouveau cookie ou une destination URL existante ou sur un cookie ou une destination URL existant.
seo-description: Les étiquettes d’exportation de données fonctionnent avec les contrôles d’exportation que vous définissez sur une source de données. Les étiquettes d’exportation de données vous empêchent d’ajouter des caractéristiques restreintes à un segment et d’envoyer des données de segment vers une destination. Vous pouvez définir plusieurs étiquettes d’exportation sur un nouveau cookie ou une destination URL existante ou sur un cookie ou une destination URL existant.
seo-title: Ajouter des contrôles d’exportation de données à une destination
solution: Audience Manager
title: Ajouter des contrôles d’exportation de données à une destination
translation-type: tm+mt
source-git-commit: 96bf2e5fe403a550a4c1cc290381d2705629dbd3

---


# Ajout ou modification de segments pour les destinations serveur à serveur {#add-edit-segments}

Vous pouvez uniquement ajouter ou modifier des segments pour une destination serveur à serveur ([!DNL S2S]). Vous ne pouvez pas créer [!DNL S2S] de destinations avec [!UICONTROL [Destination Builder](/help/using/features/destinations/destination-builder.md)]. Contactez votre consultant pour configurer [!DNL S2S] des destinations. Suivez ces instructions pour ajouter ou modifier des segments pour une [!DNL S2S] destination.

<!-- destination-s2s-edit.xml -->

Pour ajouter ou modifier des mappages de segments pour une [!DNL S2S] destination :

1. Allez-y **[!UICONTROL Audience Data > Destinations]**. Sélectionnez Plateformes **intégrées &gt; Basées sur** les périphériques et recherchez la [!DNL S2S] destination à utiliser.
2. Dans la [!UICONTROL Action] colonne, cliquez sur l’icône représentant un crayon pour modifier la destination.
   * Dans la **[!UICONTROL Search and Add Segments]** zone, commencez à saisir le nom d’un segment ou cliquez sur **[!UICONTROL Browse All Segments]** Parcourir la liste des segments disponibles.
   * Cliquez **[!UICONTROL Add Selected Segments]** lorsque vous trouvez le segment à utiliser. L’ajout d’un segment ouvre la [!UICONTROL Edit Mapping] fenêtre.
   * Dans [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Définissez une valeur pour la paire [](../../features/destinations/key-value-pairs.md) clé-valeur utilisée par cette destination.
      * **[!UICONTROL Start Date]** et **[!UICONTROL End Date]**: Choisissez une date de début et de fin pour la destination. Si la date de fin est vide, la destination n’expire jamais.
3. Cliquez sur **[!UICONTROL Save]** , puis sur **[!UICONTROL Done]**.