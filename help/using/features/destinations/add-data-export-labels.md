---
description: Les libellés d’exportation de données fonctionnent avec les contrôles d’exportation que vous définissez sur une source de données. Les libellés d’exportation de données vous empêchent d’ajouter des caractéristiques restreintes à un segment et d’envoyer des données de segment vers une destination. Vous pouvez définir plusieurs libellés d’exportation vers une destination de cookie ou d’URL nouvelle ou existante.
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add Data Export Controls to a Destination
solution: Audience Manager
title: Ajout de contrôles d’exportation de données à une destination
feature: Data Export Controls
exl-id: 12cfd2cc-b343-4dd1-a188-acbfc5cd25a2
TQID: https://experienceleague.adobe.com/DuvtSxCkPmsqfoRH2MMjqFChFBr7U-x4mKl4sbyAEJQ
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: c814092e-2730-45e8-a12d-e084529f52cb
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 221
ht-degree: 2%

---

# Ajout de libellés d’exportation de données à une destination {#add-data-export-labels}

[!DNL Data Export Labels] utiliser les [!DNL Export Controls] que vous avez définis sur une source de données. [!DNL Data Export Labels] vous empêchent d’ajouter des caractéristiques restreintes à un segment et d’envoyer des données de segment vers une destination. Vous pouvez définir plusieurs libellés d’exportation vers une destination [!DNL cookie] ou [!DNL URL] nouvelle ou existante.

>[!NOTE]
>
>Pour ajouter un libellé d’exportation, vous avez besoin d’autorisations d’administrateur *ou* de privilèges suffisants pour créer ou modifier une destination.

<!-- t_export_labels.xml -->

Pour ajouter des libellés d’exportation à une destination :

1. Cliquez **[!UICONTROL Audience Data]** :

   * Pour les nouvelles destinations : cliquez sur **[!UICONTROL Create New Destination]**. Renseignez la section [!UICONTROL Basic Information] avant de sélectionner un libellé d’exportation de données. Voir [Création d’une destination de cookie](../../features/destinations/create-cookie-destination.md) ou [Création d’une destination d’URL](../../features/destinations/create-url-destination.md) pour plus d’informations.
   * Pour les destinations existantes : utilisez la zone de [!DNL Search] pour trouver votre destination ou faites défiler la liste et cliquez sur le nom de la destination pour l’ouvrir.

1. Sélectionnez un [!DNL Data Export Label]. Ne cochez pas ces cases si vous ne souhaitez pas définir de restrictions d’exportation. Les libellés d’exportation incluent les options suivantes :

   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >Les restrictions d&#39;exportation ne fonctionneront que si vous définissez un [contrôle d&#39;exportation correspondant](../../features/data-export-controls.md) sur une source de données.

1. Cliquez sur **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Création d’une source de données](../../features/manage-datasources.md#create-data-source)
