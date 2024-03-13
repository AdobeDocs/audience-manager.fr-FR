---
description: Cette page contient des conseils sur la configuration et la gestion de l’intégration entre les plateformes d’Audience Manager et basées sur les personnes.
seo-description: This page contains guidance on how to configure and manage the integration between Audience Manager and people-based platforms.
seo-title: Authentication with People-Based Platforms
solution: Audience Manager
title: Authentification avec des plateformes basées sur des personnes
feature: People-based Destinations
exl-id: d3e136d0-2b06-412a-9b9b-75b661c9aa14
source-git-commit: 1809e9ee0b19a8ffb4bec38162f728d543d13701
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---


# Authentification avec des plateformes basées sur des personnes {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans le présent article n&#39;est un avis juridique. Veuillez consulter votre propre service juridique pour obtenir des conseils juridiques.

Cette page contient des conseils sur la configuration et la gestion de votre intégration entre les plateformes d’Audience Manager et basées sur les personnes.

>[!NOTE]
>Il s’agit d’une étape obligatoire pour les destinations basées sur les personnes, quel que soit votre scénario d’implémentation.

## Configuration de l’authentification de plateforme basée sur les personnes {#configure-authentication}

1. Connectez-vous à votre compte Audience Manager et accédez à **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Si vous avez configuré une intégration avec une plateforme sociale, elle doit apparaître dans cette page. Sinon, la page est vide.
   ![intégration basée sur les personnes](assets/pbd-config.png)
2. Cliquez sur **[!UICONTROL Add Account]**.
3. Utilisez la variable **[!UICONTROL People-Based Platform]** menu déroulant pour sélectionner la plateforme avec laquelle vous souhaitez configurer l’intégration.
   ![plate-forme basée sur les personnes](assets/pbd-add.png)
4. Cliquez sur **[!UICONTROL Confirm]** à rediriger vers la page d&#39;authentification de la plateforme sélectionnée.
5. Une fois que vous êtes authentifié sur votre compte de plateforme sociale, vous êtes redirigé vers l’Audience Manager dans laquelle vos comptes publicitaires associés doivent apparaître. Sélectionnez le compte publicitaire à utiliser, puis cliquez sur **[!UICONTROL Confirm]**.
6. Audience Manager affiche une notification en haut de la page pour vous indiquer si le compte a bien été ajouté. La notification vous permet également d’ajouter une adresse électronique de contact pour recevoir des notifications d’Adobe lorsque l’authentification de la plateforme sociale est sur le point d’expirer.

## Expiration du jeton d’authentification et gestion des notifications {#token-expiration-notification}

Audience Manager gère votre intégration aux plateformes sociales par le biais de jetons d’authentification qui expirent après un certain temps. La durée de validité du jeton est soumise aux règles d&#39;intégration de chaque plateforme sociale. Une fois le jeton d’authentification expiré, l’Audience Manager ne peut pas envoyer vos segments d’audience vers votre destination. Pour éviter ce scénario, nous vous recommandons d’ajouter au moins une adresse électronique de contact à votre intégration, de sorte que vous soyez averti dès que le jeton d’authentification arrive à expiration. Dans ce cas, vous pouvez vous authentifier de nouveau pour vous assurer que la destination continue de recevoir vos segments d’audience.

Procédez comme suit pour ajouter des adresses électroniques aux intégrations existantes :

1. Connectez-vous à votre compte Audience Manager et accédez à **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifiez l’intégration pour laquelle vous souhaitez recevoir des notifications d’expiration de jeton, puis cliquez sur le bouton **[!UICONTROL Edit]** Icône
1. Saisissez les adresses électroniques auxquelles vous souhaitez recevoir des notifications d’expiration de jeton, séparées par des virgules.
1. Cliquez sur **[!UICONTROL Save]**.

## Renouvellement du jeton d’authentification {#token-renewal}

Lorsqu’un jeton d’authentification expire, l’intégration entre l’Audience Manager et la plateforme sociale correspondante est interrompue. Par conséquent, l’Audience Manager ne peut plus envoyer de segments d’audience vers la destination. La variable [!UICONTROL Integrated Accounts] vous indique l’état d’expiration de chaque intégration dans la variable [!UICONTROL Expiration] et vous permet de renouveler l’authentification à tout moment.

Voici comment renouveler une authentification expirée ou sur le point d’expirer :
1. Connectez-vous à votre compte Audience Manager et accédez à **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifiez l’intégration pour laquelle vous devez renouveler l’authentification. Les authentifications expirées sont marquées comme [!UICONTROL Expired], tandis que les authentifications sur le point d’expirer prochainement indiquent le nombre de jours restants d’authentification.
1. Cliquez sur la **[!UICONTROL Renew]** dans le [!UICONTROL Expiration] colonne . Cela déclenche l’événement **[!UICONTROL Renew Account]** qui permet de revenir à la page d’authentification de la plateforme sociale. Une fois que vous vous êtes authentifié, le jeton est renouvelé avec la nouvelle date d’expiration.
   ![pbd-renouveler](assets/pbd-renew.png)
