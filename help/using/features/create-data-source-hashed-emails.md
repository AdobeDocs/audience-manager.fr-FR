---
title: Configuration d’une source de données pour les processus de courrier électronique haché
description: Découvrez comment créer une source de données pour stocker les emails hachés pour les workflows de messagerie hachée.
solution: Audience Manager
feature: Data Sources
exl-id: fb235dcb-e02f-41ac-ba3f-a1feb30b23dd
source-git-commit: d55dbc4f9630e3d22dfb988f6725f33993229c48
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# Configuration d’une source de données pour les processus de courrier électronique haché

Les processus de courrier électronique haché, tels que les destinations basées sur les personnes, nécessitent que vous créiez une source de données pour stocker les adresses électroniques hachées.

Suivez les étapes ci-dessous pour créer et configurer une source de données pour les courriers électroniques hachés.

1. Connectez-vous à votre compte d’Audience Manager et accédez à **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**, puis cliquez sur **[!UICONTROL Add New]**.
1. Saisissez **[!UICONTROL Name]** et **[!UICONTROL Description]** pour votre nouvelle source de données.
1. Dans le menu déroulant **[!UICONTROL ID Type]**, sélectionnez **[!UICONTROL Cross Device]**.
   ![Image de l’interface utilisateur de l’Audience Manager montrant la section des détails de la source de données.](../features/assets/create-hashed-email-data-source.png)
1. Dans la section **[!UICONTROL Data Source Settings]** , sélectionnez les options **[!UICONTROL Inbound]** et **[!UICONTROL Outbound]** et activez l’option **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Utilisez le menu déroulant pour sélectionner le libellé **[!UICONTROL Emails(SHA256, lowercased)]** de cette source de données.

   >[!IMPORTANT]
   >
   >Cette option désigne uniquement la source de données comme contenant des données hachées avec cet algorithme spécifique. L’Audience Manager ne hachage pas les données à cette étape. Assurez-vous que les adresses électroniques que vous prévoyez de stocker dans cette source de données sont déjà hachées avec l’algorithme [!DNL SHA256]. Sinon, vous ne pourrez pas l’utiliser pour les workflows de messagerie hachée.

   ![Image de l’interface utilisateur d’Audience Manager montrant la section des paramètres de source de données.](../features/assets/data-source-settings.png)
