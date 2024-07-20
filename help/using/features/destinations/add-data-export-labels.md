---
description: Les libellés d’exportation de données fonctionnent avec les contrôles d’exportation que vous définissez sur une source de données. Les étiquettes d’exportation de données vous empêchent d’ajouter des caractéristiques restreintes à un segment et d’envoyer des données de segment vers une destination. Vous pouvez définir plusieurs étiquettes d’exportation sur un nouveau cookie ou une destination d’URL existante.
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add Data Export Controls to a Destination
solution: Audience Manager
title: Ajout de contrôles des exportations de données vers une destination
feature: Data Export Controls
exl-id: 12cfd2cc-b343-4dd1-a188-acbfc5cd25a2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 2%

---

# Ajout de libellés d’exportation de données à une destination {#add-data-export-labels}

[!DNL Data Export Labels] fonctionne avec le [!DNL Export Controls] que vous avez défini sur une source de données. [!DNL Data Export Labels] vous empêche d’ajouter des caractéristiques restreintes à un segment et d’envoyer des données de segment à une destination. Vous pouvez définir plusieurs étiquettes d’exportation sur une destination [!DNL cookie] ou [!DNL URL] nouvelle ou existante.

>[!NOTE]
>
>Pour ajouter une étiquette d’exportation, vous avez besoin d’autorisations d’administrateur *ou de* autorisations suffisantes pour créer ou modifier une destination.

<!-- t_export_labels.xml -->

Pour ajouter des libellés d’exportation à une destination :

1. Cliquez sur **[!UICONTROL Audience Data]** :
   * Pour les nouvelles destinations : cliquez sur **[!UICONTROL Create New Destination]**. Renseignez la section [!UICONTROL Basic Information] avant de sélectionner un libellé d’exportation de données. Pour plus d’informations, voir [Création d’une destination de cookie](../../features/destinations/create-cookie-destination.md) ou [Création d’une destination d’URL](../../features/destinations/create-url-destination.md) .
   * Pour les destinations existantes : utilisez la zone [!DNL Search] pour trouver votre destination ou faites défiler la liste et cliquez sur le nom de la destination pour l’ouvrir.
1. Sélectionnez un [!DNL Data Export Label]. Laissez les cases vides si vous ne souhaitez définir aucune restriction d’exportation. Les libellés d’exportation incluent les options suivantes :
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Les restrictions d’exportation ne fonctionneront pas, sauf si vous définissez un [contrôle d’exportation correspondant](../../features/data-export-controls.md) sur une source de données.
1. Cliquez sur **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Création d’une source de données](../../features/manage-datasources.md#create-data-source)
