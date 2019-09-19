---
description: Les étiquettes d’exportation de données fonctionnent avec les contrôles d’exportation que vous définissez sur une source de données. Les étiquettes d’exportation de données vous empêchent d’ajouter des caractéristiques restreintes à un segment et d’envoyer des données de segment vers une destination. Vous pouvez définir plusieurs étiquettes d’exportation sur un nouveau cookie ou une destination URL existante ou sur un cookie ou une destination URL existant.
seo-description: Les étiquettes d’exportation de données fonctionnent avec les contrôles d’exportation que vous définissez sur une source de données. Les étiquettes d’exportation de données vous empêchent d’ajouter des caractéristiques restreintes à un segment et d’envoyer des données de segment vers une destination. Vous pouvez définir plusieurs étiquettes d’exportation sur un nouveau cookie ou une destination URL existante ou sur un cookie ou une destination URL existant.
seo-title: Ajouter des contrôles d’exportation de données à une destination
solution: Audience Manager
title: Ajouter des contrôles d’exportation de données à une destination
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---



# Ajouter des étiquettes d’exportation de données à une destination {#add-data-export-labels}

[!DNL Data Export Labels] travaillez avec le [!DNL Export Controls] que vous avez défini sur une source de données. [!DNL Data Export Labels] vous empêche d’ajouter des caractéristiques restreintes à un segment et d’envoyer des données de segment vers une destination. Vous pouvez définir plusieurs étiquettes d’exportation sur une nouvelle destination [!DNL cookie] ou une destination existante ou [!DNL URL] .

>[!NOTE]
>
>Pour ajouter une étiquette d’exportation, vous avez besoin de droits d’administrateur *ou de droits suffisants pour* créer ou modifier une destination.

<!-- t_export_labels.xml -->

Pour ajouter des libellés d’exportation à une destination :

1. Cliquez sur **[!UICONTROL Audience Data]**:
   * Pour les nouvelles destinations : Cliquez sur **[!UICONTROL Create New Destination]**. Renseignez la [!UICONTROL Basic Information] section avant de sélectionner un libellé d’exportation de données. Pour plus d’informations, voir [Création d’une destination](../../features/destinations/create-cookie-destination.md) de cookie ou [Création d’une destination](../../features/destinations/create-url-destination.md) URL.
   * Pour les destinations existantes : Utilisez la [!DNL Search] zone pour trouver votre destination ou faites défiler la liste et cliquez sur le nom de la destination pour l’ouvrir.
1. Sélectionnez [!DNL Data Export Label]. Laissez les cases à cocher vides si vous ne souhaitez définir aucune restriction d’exportation. Les étiquettes d’exportation comprennent les options suivantes :
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Les restrictions d’exportation ne fonctionneront pas, sauf si vous définissez un contrôle [d’exportation](../../features/data-export-controls.md) correspondant sur une source de données.
1. Cliquez sur **[!UICONTROL Save]**.

>[!MORE_LIKE_This]
>
>* [Création d’une source de données](../../features/manage-datasources.md#create-data-source)