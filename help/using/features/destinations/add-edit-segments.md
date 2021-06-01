---
description: Les libellés d’exportation de données fonctionnent avec les contrôles d’exportation que vous définissez sur une source de données. Les étiquettes d’exportation de données vous empêchent d’ajouter des caractéristiques restreintes à un segment et d’envoyer des données de segment vers une destination. Vous pouvez définir plusieurs étiquettes d’exportation sur un nouveau cookie ou une destination d’URL existante.
seo-description: Les libellés d’exportation de données fonctionnent avec les contrôles d’exportation que vous définissez sur une source de données. Les étiquettes d’exportation de données vous empêchent d’ajouter des caractéristiques restreintes à un segment et d’envoyer des données de segment vers une destination. Vous pouvez définir plusieurs étiquettes d’exportation sur un nouveau cookie ou une destination d’URL existante.
seo-title: Ajout ou modification de segments pour des destinations serveur à serveur
solution: Audience Manager
title: Ajout ou modification de segments pour des destinations serveur à serveur
feature: Concepts de base des destinations
exl-id: 20124779-e14b-4d17-be4b-9f17ee0dc19e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 8%

---

# Ajout ou modification de segments pour des destinations serveur à serveur {#add-edit-segments}

Vous pouvez uniquement ajouter ou modifier des segments pour une destination serveur à serveur ([!DNL S2S]). Vous ne pouvez pas créer de destinations [!DNL S2S] avec [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md). Contactez votre consultant pour configurer des destinations [!DNL S2S]. Suivez ces instructions pour ajouter ou modifier des segments pour une destination [!DNL S2S].

<!-- destination-s2s-edit.xml -->

Pour ajouter ou modifier des mappages de segments pour une destination [!DNL S2S] :

1. Accédez à **[!UICONTROL Audience Data > Destinations]**. Sélectionnez **Plateformes intégrées > Basée sur un appareil** et recherchez la destination [!DNL S2S] que vous souhaitez utiliser.
2. Dans la colonne [!UICONTROL Action] , cliquez sur l’icône en forme de crayon pour modifier la destination.
   * Dans la zone **[!UICONTROL Search and Add Segments]**, commencez à saisir le nom d’un segment ou cliquez sur **[!UICONTROL Browse All Segments]** parcourir la liste des segments disponibles.
   * Cliquez sur **[!UICONTROL Add Selected Segments]** lorsque vous trouvez le segment à utiliser. L’ajout d’un segment ouvre la fenêtre [!UICONTROL Edit Mapping].
   * Dans [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Définissez une valeur pour la  [clé-valeur ](../../features/destinations/key-value-pairs.md) correspondante pour cette destination.
      * **[!UICONTROL Start Date]** et  **[!UICONTROL End Date]**: Choisissez les dates de début et de fin de la destination. Si la date de fin est vide, la destination n’expire jamais.
3. Cliquez sur **[!UICONTROL Save]**, puis sur **[!UICONTROL Done]**.
