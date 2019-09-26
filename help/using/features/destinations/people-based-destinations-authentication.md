---
description: 'Cette page contient des conseils sur la configuration et la gestion de l’intégration entre Audience Manager et les plateformes basées sur les personnes. '
seo-description: 'Cette page contient des conseils sur la configuration et la gestion de l’intégration entre Audience Manager et les plateformes basées sur les personnes. '
seo-title: Authentification avec des plateformes basées sur les personnes
solution: Audience Manager
title: Authentification avec des plateformes basées sur les personnes
translation-type: tm+mt
source-git-commit: f500b4a763f1639392253b7e5f209395a978e45e

---


# Authentification avec des plateformes basées sur les personnes {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans ce document n'est un conseil juridique. Veuillez consulter votre propre conseiller juridique pour obtenir des conseils juridiques.

Cette page contient des conseils sur la manière de configurer et de gérer votre intégration entre Audience Manager et les plateformes basées sur les personnes.

>[!NOTE]
>Il s’agit d’une étape obligatoire pour les destinations basées sur les personnes, quel que soit votre scénario d’implémentation.

## Configuration de l’authentification de plateformes basées sur le personnel {#configure-authentication}

1. Connectez-vous à votre compte Audience Manager et accédez à **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Si vous avez déjà configuré une intégration avec une plateforme sociale, elle doit apparaître dans cette page. Sinon, la page est vide.
   ![intégration basée sur les personnes](assets/pbd-config.png)
2. Cliquez sur **[!UICONTROL Add Account]**.
3. Utilisez le menu **[!UICONTROL People-Based Platform]** déroulant pour sélectionner la plateforme avec laquelle vous souhaitez configurer l’intégration.
   ![plate-forme à base de personnes](assets/pbd-add.png)
4. Cliquez **[!UICONTROL Confirm]** pour être redirigé vers la page d'authentification de la plateforme sélectionnée.
5. Une fois que vous êtes authentifié sur votre compte de plateforme sociale, vous êtes redirigé vers Audience Manager où vous devriez voir les comptes publicitaires associés. Sélectionnez le compte publicitaire à utiliser, puis cliquez sur **[!UICONTROL Confirm]**.
6. Audience Manager affiche une notification en haut de la page pour vous indiquer si le compte a bien été ajouté. La notification vous permet également d’ajouter une adresse électronique de contact pour recevoir des notifications d’Adobe lorsque l’authentification de la plateforme sociale est sur le point d’expirer.

## Expiration du jeton d’authentification et gestion des notifications {#token-expiration-notification}

Audience Manager gère votre intégration aux plateformes sociales au moyen de jetons d’authentification qui expirent après un certain temps. La durée de validité du jeton est soumise aux règles d’intégration de chaque plateforme sociale. Une fois le jeton d’authentification arrivé à expiration, Audience Manager ne peut plus envoyer les segments d’audience vers votre destination. Pour éviter ce scénario, nous vous recommandons d’ajouter au moins une adresse électronique de contact à votre intégration, afin que vous soyez averti dès que le jeton d’authentification arrive à expiration. Dans ce cas, vous pouvez vous reconnecter pour vous assurer que la destination continue de recevoir les segments d’audience.

Voici comment ajouter des adresses électroniques aux intégrations existantes :

1. Connectez-vous à votre compte Audience Manager et accédez à **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**.
1. Identifiez l’intégration pour laquelle vous souhaitez recevoir des notifications d’expiration de jeton, puis cliquez sur l’ **[!UICONTROL Edit]** icône .
1. Entrez les adresses électroniques auxquelles vous souhaitez recevoir des notifications d’expiration de jeton, séparées par des virgules.
1. Cliquez sur **[!UICONTROL Save]**.

## Renouvellement du jeton d’authentification {#token-renewal}

Lorsqu’un jeton d’authentification expire, l’intégration entre Audience Manager et la plateforme sociale correspondante est interrompue. Audience Manager ne peut donc plus envoyer de segments d’audience vers la destination. La [!UICONTROL Integrated Accounts] page indique l’état d’expiration de chaque intégration dans la [!UICONTROL Expiration] colonne et vous permet de renouveler l’authentification à tout moment.

Voici comment renouveler une authentification expirée ou sur le point d’expirer :
1. Connectez-vous à votre compte Audience Manager et accédez à **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**.
1. Identifiez l’intégration pour laquelle vous devez renouveler l’authentification. Les authentifications arrivées à expiration sont marquées comme [!UICONTROL Expired], tandis que les authentifications qui arrivent à expiration prochainement indiquent le nombre restant de jours authentifiés.
1. Cliquez sur l’ **[!UICONTROL Renew]** icône correspondante dans la [!UICONTROL Expiration] colonne. Cela déclenche le **[!UICONTROL Renew Account]** flux de travaux, qui vous ramène à la page d’authentification de la plateforme sociale. Une fois que vous vous êtes authentifié, le jeton est renouvelé avec la nouvelle date d’expiration.
   ![pbd-renouveler](assets/pbd-renew.png)
