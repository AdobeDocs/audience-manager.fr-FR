---
title: Configurer une source de données pour les workflows d’e-mail hachés
description: Découvrez comment créer une source de données pour stocker les e-mails hachés pour les workflows d’e-mail hachés.
solution: Audience Manager
feature: Data Sources
exl-id: fb235dcb-e02f-41ac-ba3f-a1feb30b23dd
TQID: https://experienceleague.adobe.com/dPV7bJC5zIBkj1EX43q4FWU7XP0gs-dhBYTcW8mApL4
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: c814092e-2730-45e8-a12d-e084529f52cb
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 191
ht-degree: 0%

---

# Configurer une source de données pour les workflows d’e-mail hachés

Les workflows d’e-mail hachés, tels que les destinations basées sur les personnes, nécessitent que vous créiez une source de données pour stocker les adresses e-mail hachées.

Suivez les étapes ci-dessous pour créer et configurer une source de données pour les e-mails hachés.

1. Connectez-vous à votre compte Audience Manager, accédez à **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**, puis cliquez sur **[!UICONTROL Add New]**.
1. Saisissez un **[!UICONTROL Name]** et une **[!UICONTROL Description]** pour votre nouvelle source de données.
1. Dans le menu déroulant **[!UICONTROL ID Type]**, sélectionnez **[!UICONTROL Cross Device]**.
   ![Image de l’interface utilisateur d’Audience Manager montrant la section détails de la source de données.](../features/assets/create-hashed-email-data-source.png)
1. Dans la section **[!UICONTROL Data Source Settings]**, sélectionnez les options **[!UICONTROL Inbound]** et **[!UICONTROL Outbound]**, puis activez l’option **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Utilisez le menu déroulant pour sélectionner le libellé de **[!UICONTROL Emails(SHA256, lowercased)]** de cette source de données.

   >[!IMPORTANT]
   >
   >Cette option étiquette uniquement la source de données comme contenant des données hachées avec cet algorithme spécifique. Audience Manager ne hache pas les données à cette étape. Assurez-vous que les adresses e-mail que vous prévoyez de stocker dans cette source de données sont déjà hachées avec l’algorithme [!DNL SHA256]. Sinon, vous ne pourrez pas l’utiliser pour les workflows d’e-mail hachés.

   ![Image de l’interface utilisateur d’Audience Manager montrant la section paramètres de source de données.](../features/assets/data-source-settings.png)
