---
description: Cette page contient des conseils sur la configuration et la gestion de l’intégration entre Audience Manager et les plateformes basées sur les personnes.
seo-description: This page contains guidance on how to configure and manage the integration between Audience Manager and people-based platforms.
seo-title: Authentication with People-Based Platforms
solution: Audience Manager
title: Authentification avec les plateformes basées sur les personnes
feature: People-based Destinations
exl-id: d3e136d0-2b06-412a-9b9b-75b661c9aa14
source-git-commit: 1809e9ee0b19a8ffb4bec38162f728d543d13701
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---


# Authentification avec les plateformes basées sur les personnes {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans le présent document n&#39;est un avis juridique. Veuillez consulter votre propre service juridique pour obtenir des conseils juridiques.

Cette page contient des conseils sur la configuration et la gestion de votre intégration
entre Audience Manager et les plateformes basées sur les personnes.

>[!NOTE]
>Il s’agit d’une étape obligatoire pour les destinations basées sur les personnes, quel que soit votre scénario d’implémentation.

## Configurer L’Authentification De La Plateforme Basée Sur Les Personnes {#configure-authentication}

1. Connectez-vous à votre compte Audience Manager et accédez à **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Si vous avez configuré précédemment une intégration à une plateforme sociale, elle est répertoriée sur cette page. Dans le cas contraire, la page est vide.
   ![intégration basée sur les personnes](assets/pbd-config.png)
2. Cliquez sur **[!UICONTROL Add Account]**.
3. Utilisez le menu déroulant **[!UICONTROL People-Based Platform]** pour sélectionner la plateforme avec laquelle vous souhaitez configurer l’intégration.
   ![plateforme basée sur les personnes](assets/pbd-add.png)
4. Cliquez sur **[!UICONTROL Confirm]** pour être redirigé vers la page d’authentification de la plateforme sélectionnée.
5. Une fois que vous êtes authentifié sur votre compte de plateforme sociale, vous êtes redirigé vers Audience Manager où vous devriez voir les comptes publicitaires associés. Sélectionnez le compte publicitaire que vous souhaitez utiliser, puis cliquez sur **[!UICONTROL Confirm]**.
6. Audience Manager affiche une notification en haut de la page pour vous informer que le compte a bien été ajouté. La notification vous permet également d’ajouter une adresse e-mail de contact pour recevoir des notifications d’Adobe lorsque l’authentification de la plateforme sociale est sur le point d’expirer.

## Expiration des jetons d’authentification et gestion des notifications {#token-expiration-notification}

Audience Manager gère votre intégration aux plateformes sociales par le biais de jetons d’authentification qui expirent après un certain temps. La durée de validité des jetons est soumise aux règles d’intégration de chaque plateforme sociale. Une fois le jeton d’authentification expiré, Audience Manager ne peut plus envoyer les segments d’audience vers la destination. Pour éviter ce scénario, nous vous recommandons d’ajouter au moins une adresse e-mail de contact à votre intégration, de sorte que vous soyez averti dès que le jeton d’authentification est sur le point d’expirer. Lorsque cela se produit, vous pouvez vous réauthentifier pour vous assurer que la destination continue de recevoir vos segments d’audience.

Voici comment ajouter des adresses e-mail aux intégrations existantes :

1. Connectez-vous à votre compte Audience Manager et accédez à **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifiez l’intégration pour laquelle vous souhaitez recevoir des notifications d’expiration de jeton, puis cliquez sur l’icône **[!UICONTROL Edit]** .
1. Saisissez les adresses e-mail auxquelles vous souhaitez envoyer des notifications d’expiration de jeton, en les séparant par des virgules.
1. Cliquez sur **[!UICONTROL Save]**.

## Renouvellement du jeton d’authentification {#token-renewal}

Lorsqu’un jeton d’authentification expire, l’intégration entre Audience Manager et la plateforme sociale correspondante est interrompue, de sorte qu’Audience Manager ne peut plus envoyer de segments d’audience vers la destination. La page [!UICONTROL Integrated Accounts] vous indique le statut d’expiration de chaque intégration dans la colonne [!UICONTROL Expiration] et vous permet de renouveler l’authentification à tout moment.

Voici comment renouveler une authentification arrivée à expiration ou sur le point d’expirer :
1. Connectez-vous à votre compte Audience Manager et accédez à **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifiez l’intégration pour laquelle vous devez renouveler l’authentification. Les authentifications arrivées à expiration sont marquées comme [!UICONTROL Expired], tandis que celles qui sont sur le point d’arriver à expiration indiquent le nombre de jours d’authentification restants.
1. Cliquez sur l’icône de **[!UICONTROL Renew]** correspondante dans la colonne [!UICONTROL Expiration] . Cela déclenche le workflow **[!UICONTROL Renew Account]**, qui vous ramène à la page d’authentification de la plateforme sociale. Une fois que vous vous authentifiez, le jeton est renouvelé avec la nouvelle date d’expiration.
   ![pbd-refresh](assets/pbd-renew.png)
