---
description: Les étiquettes d’exportation de données fonctionnent avec les contrôles d’exportation que vous définissez sur une source de données. Les étiquettes d’exportation de données vous empêchent d’ajouter des caractéristiques restreintes à un segment et d’envoyer des données de segment à une destination. Vous pouvez définir plusieurs étiquettes d’exportation sur un nouveau cookie ou une destination URL existante ou un cookie ou une destination URL.
seo-description: Les étiquettes d’exportation de données fonctionnent avec les contrôles d’exportation que vous définissez sur une source de données. Les étiquettes d’exportation de données vous empêchent d’ajouter des caractéristiques restreintes à un segment et d’envoyer des données de segment à une destination. Vous pouvez définir plusieurs étiquettes d’exportation sur un nouveau cookie ou une destination URL existante ou un cookie ou une destination URL.
seo-title: Ajout ou modification de segments pour des destinations serveur à serveur
solution: Audience Manager
title: Ajout ou modification de segments pour des destinations serveur à serveur
feature: Destination Basics
translation-type: tm+mt
source-git-commit: 55925e803e16580e0d9357d973405cf39370a8fd
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 8%

---


# Ajout ou modification de segments pour des destinations serveur à serveur {#add-edit-segments}

Vous pouvez uniquement ajouter ou modifier des segments pour une destination serveur à serveur ([!DNL S2S]). Vous ne pouvez pas créer de destinations [!DNL S2S] avec [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md). Contactez votre consultant pour configurer des destinations [!DNL S2S]. Suivez ces instructions pour ajouter ou modifier des segments pour une destination [!DNL S2S].

<!-- destination-s2s-edit.xml -->

Pour ajouter ou modifier des mappages de segments pour une destination [!DNL S2S] :

1. Accédez à **[!UICONTROL Audience Data > Destinations]**. Sélectionnez **Plateformes intégrées > Périphériques** et recherchez la destination [!DNL S2S] avec laquelle vous souhaitez travailler.
2. Dans la colonne [!UICONTROL Action], cliquez sur l&#39;icône représentant un crayon pour modifier la destination.
   * Dans la zone **[!UICONTROL Search and Add Segments]**, le début saisissant le nom d&#39;un segment ou cliquez sur **[!UICONTROL Browse All Segments]** parcourir une liste de segments disponibles.
   * Cliquez sur **[!UICONTROL Add Selected Segments]** lorsque vous trouvez le segment à utiliser. Ajouter un segment ouvre la fenêtre [!UICONTROL Edit Mapping].
   * Dans [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Définissez une valeur pour la valeur de  [clé ](../../features/destinations/key-value-pairs.md) utilisée par cette destination.
      * **[!UICONTROL Start Date]** et  **[!UICONTROL End Date]**: Choisissez un début et une date de fin pour la destination. Si la date de fin est vide, la destination n’expire jamais.
3. Cliquez sur **[!UICONTROL Save]**, puis sur **[!UICONTROL Done]**.
