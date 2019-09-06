---
description: 'Cette page explique comment configurer et gérer l''intégration entre Audience Manager et les plateformes basées sur des personnes. '
seo-description: 'Cette page explique comment configurer et gérer l''intégration entre Audience Manager et les plateformes basées sur des personnes. '
seo-title: Authentification avec plateformes basées sur People
solution: Audience Manager
title: Authentification avec plateformes basées sur People
translation-type: tm+mt
source-git-commit: 05f334dc3d975a0fe18b93c844889e3edb2dfafa

---


# Authentification avec plateformes basées sur People {#authentication-with-people-based-platforms}

Cette page explique comment configurer et gérer l'intégration entre Audience Manager et les plateformes basées sur des personnes.

>[!NOTE]
>Il s'agit d'une étape obligatoire pour les destinations basées sur les personnes, quel que soit le scénario de mise en œuvre.

## Configuration de l'authentification de plateforme basée sur les personnes {#configure-authentication}

1. Connectez-vous à votre compte Audience Manager et accédez **[!UICONTROL Administration]** à &gt; **[!UICONTROL Integrated Accounts]**. Si vous avez déjà configuré une intégration avec une plateforme sociale, vous devriez la voir dans cette page. Sinon, la page est vide.
   ![people-based-integration](assets/pbd-config.png)
1. Cliquez sur **[!UICONTROL Add Account]**.
1. Utilisez le menu **[!UICONTROL People-Based Platform]** déroulant pour sélectionner la plateforme à laquelle vous souhaitez configurer l'intégration.
   ![people-based-platform](assets/pbd-add.png)
1. Cliquez pour **[!UICONTROL Confirm]** être redirigé vers la page d'authentification de la plateforme sélectionnée.
1. Une fois que vous êtes authentifié sur votre compte de plateforme sociale, vous êtes redirigé vers Audience Manager, où vos comptes publicitaires associés doivent apparaître. Sélectionnez le compte publicitaire à utiliser, puis cliquez **[!UICONTROL Confirm]** sur.
1. Audience Manager affiche une notification en haut de la page pour vous informer si le compte a bien été ajouté. La notification vous permet également d'ajouter une adresse électronique de contact à laquelle recevoir des notifications lorsque l'authentification de la plateforme sociale est sur le point d'expirer.

## Expiration du jeton d'authentification et gestion des notifications {#token-expiration-notification}

Audience Manager gère l'intégration avec les plateformes sociales par le biais de jetons d'authentification qui expirent après une certaine durée. La durée de validité du jeton est assujettie aux règles d'intégration de chaque plateforme sociale. Une fois le jeton d'authentification expiré, Audience Manager ne peut pas envoyer vos segments d'audience à votre destination. Pour éviter ce scénario, nous vous recommandons d'ajouter au moins une adresse électronique de contact à votre intégration, de telle sorte que vous soyez averti dès que le jeton d'authentification est sur le point d'expirer. Dans ce cas, vous pouvez vous authentifier de nouveau pour que la destination continue à recevoir vos segments d'audience.

Voici comment ajouter des adresses électroniques aux intégrations existantes :

1. Connectez-vous à votre compte Audience Manager et accédez **[!UICONTROL Administration]** à &gt; **[!UICONTROL Integrated Accounts]**.
1. Identifiez l'intégration à laquelle vous souhaitez recevoir les notifications d'expiration du jeton, puis cliquez sur l **[!UICONTROL Edit]** 'icône.
1. Entrez les adresses électroniques auxquelles vous souhaitez recevoir les notifications d'expiration du jeton, séparées par des virgules.
1. Cliquez sur **[!UICONTROL Save]**.

## Renouvellement du jeton d'authentification {#token-renewal}

Lors de l'expiration d'un jeton d'authentification, l'intégration entre Audience Manager et la plateforme sociale correspondante est interrompue. Audience Manager ne peut donc plus envoyer de segments d'audience à la destination. La [!UICONTROL Integrated Accounts] page indique l'état d'expiration de chaque intégration dans [!UICONTROL Expiration] la colonne et vous permet de renouveler l'authentification à tout moment.

Voici comment renouveler une authentification expirée ou presque arrivée à expiration :
1. Connectez-vous à votre compte Audience Manager et accédez **[!UICONTROL Administration]** à &gt; **[!UICONTROL Integrated Accounts]**.
1. Identifiez l'intégration dont vous avez besoin pour renouveler l'authentification. Les authentifications expirées sont marquées comme étant [!UICONTROL Expired], tandis que les authentifications qui sont sur le point d'expirer rapidement affichent le nombre restant de jours authentifiés.
1. Cliquez sur l'icône correspondante **[!UICONTROL Renew]** dans [!UICONTROL Expiration] la colonne. Cela déclenche **[!UICONTROL Renew Account]** le flux de travail qui vous ramènera à la page d'authentification de la plateforme sociale. Une fois que vous êtes authentifié, le jeton est renouvelé avec la nouvelle date d'expiration.
   ![pbd-renewal](assets/pbd-renew.png)
