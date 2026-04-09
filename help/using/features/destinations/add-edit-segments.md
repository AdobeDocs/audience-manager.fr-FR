---
description: Les libellés d’exportation de données fonctionnent avec les contrôles d’exportation que vous définissez sur une source de données. Les libellés d’exportation de données vous empêchent d’ajouter des caractéristiques restreintes à un segment et d’envoyer des données de segment vers une destination. Vous pouvez définir plusieurs libellés d’exportation vers une destination de cookie ou d’URL nouvelle ou existante.
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add or Edit Segments for Server-to-Server Destinations
solution: Audience Manager
title: Ajouter ou modifier des segments pour les destinations de serveur à serveur
feature: Destination Basics
exl-id: 20124779-e14b-4d17-be4b-9f17ee0dc19e
TQID: https://experienceleague.adobe.com/3bcMGBGMb4HtnPA8yFvO4UzfGXmpvM2Drs427ztfWDc
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2: id: c138d302-73f0-4186-93ea-10c4ba52f943id: e7029888-c8b0-46a7-849a-cf132a1559bf
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 202
ht-degree: 0%

---

# Ajouter ou modifier des segments pour les destinations de serveur à serveur {#add-edit-segments}

Vous pouvez uniquement ajouter ou modifier des segments pour une destination serveur à serveur ([!DNL S2S]). Vous ne pouvez pas créer de destinations [!DNL S2S] avec [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md). Contactez votre consultant pour configurer des destinations [!DNL S2S]. Suivez ces instructions pour ajouter ou modifier des segments pour une destination [!DNL S2S].

<!-- destination-s2s-edit.xml -->

Pour ajouter ou modifier des mappages de segments pour une destination [!DNL S2S] :

1. Accédez à **[!UICONTROL Audience Data > Destinations]**. Sélectionnez **Plateformes intégrées > Basées sur l’appareil** et recherchez la destination [!DNL S2S] avec laquelle vous souhaitez travailler.
2. Dans la colonne [!UICONTROL Action], cliquez sur l’icône en forme de crayon pour modifier la destination.
   * Dans la zone de **[!UICONTROL Search and Add Segments]**, commencez à saisir le nom d’un segment ou cliquez **[!UICONTROL Browse All Segments]** parcourir une liste de segments disponibles.
   * Cliquez sur **[!UICONTROL Add Selected Segments]** lorsque vous trouvez le segment que vous souhaitez utiliser. L’ajout d’un segment ouvre la fenêtre de [!UICONTROL Edit Mapping].
   * En [!UICONTROL Edit Mapping] :
      * **[!UICONTROL Mappings]** : définissez une valeur pour la [ paire clé-valeur ](../../features/destinations/key-value-pairs.md) utilisée par cette destination.
      * **[!UICONTROL Start Date]** et **[!UICONTROL End Date]** : choisissez des dates de début et de fin pour la destination. Si la date de fin est vide, la destination n’expire jamais.
3. Cliquez sur **[!UICONTROL Save]**, puis sur **[!UICONTROL Done]**.
