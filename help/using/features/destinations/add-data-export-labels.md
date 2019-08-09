---
description: Les étiquettes d'exportation de données fonctionnent avec les commandes d'exportation que vous avez définies sur une source de données. Les étiquettes d'exportation de données vous empêchent d'ajouter des caractéristiques restreintes à un segment et d'envoyer des données de segment à une destination. Vous pouvez définir plusieurs étiquettes d'exportation dans un cookie ou une destination d'URL nouveau ou existant.
seo-description: Les étiquettes d'exportation de données fonctionnent avec les commandes d'exportation que vous avez définies sur une source de données. Les étiquettes d'exportation de données vous empêchent d'ajouter des caractéristiques restreintes à un segment et d'envoyer des données de segment à une destination. Vous pouvez définir plusieurs étiquettes d'exportation dans un cookie ou une destination d'URL nouveau ou existant.
seo-title: Ajouter des contrôles d'exportation de données à une destination
solution: Audience Manager
title: Ajouter des contrôles d'exportation de données à une destination
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---



# Ajout d'étiquettes d'exportation de données à une destination {#add-data-export-labels}

[!DNL Data Export Labels] travailler avec le jeu [!DNL Export Controls] que vous avez défini sur une source de données. [!DNL Data Export Labels] vous éviter d'ajouter des caractéristiques restreintes à un segment et d'envoyer des données de segment à une destination. Vous pouvez définir plusieurs étiquettes d'exportation dans une nouvelle ou une [!DNL cookie][!DNL URL] nouvelle destination.

>[!NOTE]
>
>Pour ajouter une étiquette d'exportation, vous devez disposer des autorisations *d'administrateur ou* des privilèges suffisants pour créer ou modifier une destination.

<!-- t_export_labels.xml -->

Pour ajouter des étiquettes d'exportation à une destination :

1. Cliquez sur **[!UICONTROL Audience Data]**:
   * Pour les nouvelles destinations : Cliquez **[!UICONTROL Create New Destination]** sur. Remplissez [!UICONTROL Basic Information] la section avant de sélectionner une étiquette d'exportation de données. Voir [Création d'une destination de cookie](../../features/destinations/create-cookie-destination.md) ou [Création d'une destination d'URL](../../features/destinations/create-url-destination.md) pour plus d'informations.
   * Pour les destinations existantes : Utilisez [!DNL Search] la zone pour trouver votre destination ou faites défiler la liste et cliquez sur le nom de la destination pour l'ouvrir.
1. Sélectionnez [!DNL Data Export Label]. Laissez les cases vides si vous ne souhaitez pas définir de restrictions d'exportation. Les étiquettes d'exportation incluent les options suivantes :
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Les restrictions d'exportation ne fonctionnent que si vous définissez un contrôle d'exportation [correspondant](../../features/data-export-controls.md) sur une source de données.
1. Cliquez sur **[!UICONTROL Save]**.

>[!MORE_ LIKE_ THIS]
>
>* [Création d'une source de données](../../features/manage-datasources.md#create-data-source)