---
title: Configuration d’une source de données pour les processus de courrier électronique haché
description: Découvrez comment créer une source de données pour stocker les emails hachés pour les workflows de messagerie hachée.
solution: Audience Manager
feature: Data Sources
source-git-commit: b88f180808ec9723a2a5324441733f6383f6302d
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---


# Configuration d’une source de données pour les processus de courrier électronique haché

Les processus de courrier électronique haché, tels que les destinations basées sur les personnes, nécessitent que vous créiez une source de données pour stocker les adresses électroniques hachées.

Suivez les étapes ci-dessous pour créer et configurer une source de données pour les courriers électroniques hachés.

1. Connectez-vous à votre compte Audience Manager et accédez à **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**, puis cliquez sur **[!UICONTROL Add New]**.
1. Saisissez un **[!UICONTROL Name]** et **[!UICONTROL Description]** pour votre nouvelle source de données.
1. Dans le **[!UICONTROL ID Type]** menu déroulant, sélectionnez **[!UICONTROL Cross Device]**.
   ![Image de l’interface utilisateur d’Audience Manager affichant la section des détails de la source de données.](../features/assets/create-hashed-email-data-source.png)
1. Dans le **[!UICONTROL Data Source Settings]** , sélectionnez les deux options **[!UICONTROL Inbound]** et **[!UICONTROL Outbound]** et activez la variable **[!UICONTROL Share associated cross-device IDs in people-based destinations]** .
1. Utilisez le menu déroulant pour sélectionner la variable **[!UICONTROL Emails(SHA256, lowercased)]** libellé de cette source de données.

   >[!IMPORTANT]
   >
   >Cette option désigne uniquement la source de données comme contenant des données hachées avec cet algorithme spécifique. L’Audience Manager ne hachage pas les données à cette étape. Assurez-vous que les adresses électroniques que vous prévoyez de stocker dans cette source de données sont déjà hachées avec le [!DNL SHA256] algorithme. Sinon, vous ne pourrez pas l’utiliser pour les workflows de messagerie hachée.

   ![Image de l’interface utilisateur d’Audience Manager présentant la section des paramètres de source de données.](../features/assets/data-source-settings.png)


