---
description: Les étiquettes d’exportation de données fonctionnent avec les contrôles d’exportation que vous définissez sur une source de données. Les étiquettes d’exportation de données vous empêchent d’ajouter des caractéristiques restreintes à un segment et d’envoyer des données de segment à une destination. Vous pouvez définir plusieurs étiquettes d’exportation sur un nouveau cookie ou une destination URL existante ou un cookie ou une destination URL.
seo-description: Les étiquettes d’exportation de données fonctionnent avec les contrôles d’exportation que vous définissez sur une source de données. Les étiquettes d’exportation de données vous empêchent d’ajouter des caractéristiques restreintes à un segment et d’envoyer des données de segment à une destination. Vous pouvez définir plusieurs étiquettes d’exportation sur un nouveau cookie ou une destination URL existante ou un cookie ou une destination URL.
seo-title: Ajout de contrôles des exportations de données vers une destination
solution: Audience Manager
title: Ajout de contrôles des exportations de données vers une destination
feature: Data Export Controls
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 7%

---



# Ajouter des étiquettes d&#39;exportation de données à une destination {#add-data-export-labels}

[!DNL Data Export Labels] travaillez avec les données que  [!DNL Export Controls] vous définissez sur une source de données. [!DNL Data Export Labels] vous empêche d’ajouter des caractéristiques restreintes à un segment et d’envoyer des données de segment à une destination. Vous pouvez définir plusieurs étiquettes d’exportation sur une destination [!DNL cookie] ou [!DNL URL] nouvelle ou existante.

>[!NOTE]
>
>Pour ajouter une étiquette d’exportation, vous avez besoin de droits d’administrateur *ou* suffisants pour créer ou modifier une destination.

<!-- t_export_labels.xml -->

Pour ajouter des étiquettes d’exportation à une destination :

1. Cliquez sur **[!UICONTROL Audience Data]**:
   * Pour les nouvelles destinations : Cliquez sur **[!UICONTROL Create New Destination]**. Renseignez la section [!UICONTROL Basic Information] avant de sélectionner un libellé d’exportation de données. Voir [Création d’une destination de cookie](../../features/destinations/create-cookie-destination.md) ou [Création d’une destination d’URL](../../features/destinations/create-url-destination.md) pour plus d’informations.
   * Pour les destinations existantes : Utilisez la zone [!DNL Search] pour rechercher votre destination ou faire défiler la liste et cliquez sur le nom de la destination pour l&#39;ouvrir.
1. Sélectionnez [!DNL Data Export Label]. Laissez les cases à cocher vides si vous ne souhaitez pas définir de restrictions d’exportation. Les étiquettes d’exportation comportent les options suivantes :
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >Les restrictions d’exportation ne fonctionneront que si vous définissez un [contrôle d’exportation correspondant](../../features/data-export-controls.md) sur une source de données.
1. Cliquez sur **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Création d’une source de données](../../features/manage-datasources.md#create-data-source)