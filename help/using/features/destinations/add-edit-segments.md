---
description: Les étiquettes d'exportation de données fonctionnent avec les commandes d'exportation que vous avez définies sur une source de données. Les étiquettes d'exportation de données vous empêchent d'ajouter des caractéristiques restreintes à un segment et d'envoyer des données de segment à une destination. Vous pouvez définir plusieurs étiquettes d'exportation dans un cookie ou une destination d'URL nouveau ou existant.
seo-description: Les étiquettes d'exportation de données fonctionnent avec les commandes d'exportation que vous avez définies sur une source de données. Les étiquettes d'exportation de données vous empêchent d'ajouter des caractéristiques restreintes à un segment et d'envoyer des données de segment à une destination. Vous pouvez définir plusieurs étiquettes d'exportation dans un cookie ou une destination d'URL nouveau ou existant.
seo-title: Ajouter des contrôles d'exportation de données à une destination
solution: Audience Manager
title: Ajouter des contrôles d'exportation de données à une destination
translation-type: tm+mt
source-git-commit: 96bf2e5fe403a550a4c1cc290381d2705629dbd3

---


# Ajout ou modification de segments pour les destinations serveur à serveur {#add-edit-segments}

Vous pouvez uniquement ajouter ou modifier des segments pour une destination de serveur à serveur ([!DNL S2S]). Vous ne pouvez pas créer [!DNL S2S] de destinations avec [! UICONPREVDESTINATION [Builder](/help/using/features/destinations/destination-builder.md)]. Contactez votre conseiller pour configurer [!DNL S2S] les destinations. Suivez ces instructions pour ajouter ou modifier des segments pour [!DNL S2S] une destination.

<!-- destination-s2s-edit.xml -->

Pour ajouter ou modifier des correspondances de segments pour [!DNL S2S] une destination :

1. Accédez **[!UICONTROL Audience Data > Destinations]**&#x200B;à. Sélectionnez **Plateformes intégrées &gt; Périphérique et** recherchez [!DNL S2S] la destination avec laquelle vous souhaitez travailler.
2. Dans [!UICONTROL Action] la colonne, cliquez sur l'icône représentant un crayon pour modifier la destination.
   * Dans **[!UICONTROL Search and Add Segments]** la zone, commencez à saisir le nom d'un segment ou cliquez **[!UICONTROL Browse All Segments]** sur Parcourir une liste des segments disponibles.
   * Cliquez **[!UICONTROL Add Selected Segments]** sur le segment que vous souhaitez utiliser. L'ajout d'un segment ouvre [!UICONTROL Edit Mapping] la fenêtre.
   * Dans [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Définissez une valeur pour la paire [clé-valeur](../../features/destinations/key-value-pairs.md) utilisée par cette destination.
      * **[!UICONTROL Start Date]** et **[!UICONTROL End Date]**: Choisissez une date de début et de fin pour la destination. Si la date de fin est vide, la destination n'expire jamais.
3. Cliquez **[!UICONTROL Save]** sur, puis **[!UICONTROL Done]** sur.