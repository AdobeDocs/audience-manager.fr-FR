---
description: Cet article explique comment configurer de nouvelles destinations basées sur un périphérique à partir de l’interface utilisateur d’Audience Manager.
seo-description: Cet article explique comment configurer de nouvelles destinations basées sur un périphérique à partir de l’interface utilisateur d’Audience Manager.
seo-title: Ajouter de nouvelles destinations basées sur un périphérique
solution: Audience Manager
title: Ajouter de nouvelles destinations basées sur un périphérique
translation-type: tm+mt
source-git-commit: 4cc7077cd5911bc603db254d9b55f129ce8f6cd5

---


# Ajouter de nouvelles destinations basées sur un périphérique {#add-new-device-based-destinations}

Cet article explique comment configurer de nouvelles destinations basées sur un périphérique à partir de l’interface utilisateur d’Audience Manager.

>[!IMPORTANT]
>
>Actuellement, la plupart des destinations basées sur un périphérique ne sont pas éligibles au flux de travail de configuration en libre-service. Si la destination basée sur un périphérique que vous devez ajouter ne s’affiche pas dans la liste des destinations, contactez votre conseiller Adobe ou le service clientèle pour obtenir de l’aide.

## Aperçu {#overview}

Le processus d’ajout d’une nouvelle destination basée sur un périphérique se compose de deux étapes principales. Tout d’abord, vous devez configurer l’intégration entre Audience Manager et le partenaire de destination. Une fois que vous avez effectué cette opération, vous pouvez créer une destination basée sur un périphérique.

## Conditions préalables {#prerequisites}

Lors de la création de la première destination basée sur un périphérique avec une plateforme intégrée, contactez le service de conseil ou le service à la clientèle d’Adobe pour activer la synchronisation des identifiants entre Audience Manager et la plateforme intégrée pour votre compte. Ceci est nécessaire pour une synchronisation correcte entre Audience Manager et la plateforme de destination.



## Étape 1. Authentifier avec une plateforme de destination {#step1}

Avant de pouvoir créer une destination basée sur un périphérique, vous devez configurer l’intégration entre Audience Manager et la plateforme de destination. Voici comment procéder :

1. Connectez-vous à votre compte Audience Manager et accédez à **[!DNL Administration > Integrated Accounts]**. Si vous disposez d’une intégration précédemment configurée avec une plateforme de destination, elle doit apparaître dans cette page. Sinon, la page est vide.
1. Cliquez sur **[!DNL Add Account]**.
1. Sélectionnez la plateforme de destination avec laquelle vous souhaitez vous authentifier, puis cliquez sur **[!DNL Confirm]**pour la rediriger vers la page d’authentification de la plateforme sélectionnée.![plates-formes intégrées](assets/dbd-integrated-platforms.png)
1. Une fois que vous êtes authentifié sur votre compte de plateforme de destination, vous êtes redirigé vers Audience Manager où vous devriez voir les comptes publicitaires associés. Sélectionnez le compte publicitaire à utiliser, puis cliquez sur **[!DNL Confirm]**.

## Étape 2 : Créer une destination basée sur un périphérique {#step2}

Après avoir configuré l’intégration de la plateforme de destination, vous pouvez créer la nouvelle destination. Voici comment procéder :

>[!NOTE]
>
>Vous ne pouvez pas modifier le nom d’une destination existante basée sur un périphérique. Veillez à indiquer un nom qui vous aidera à identifier correctement la destination.

1. Connectez-vous à votre compte Audience Manager, accédez à **[!DNL Audience Data > Destinations]**, puis cliquez sur**[!DNL Create Destination]**.
1. Dans la **[!DNL Basic Information]**section, saisissez un**[!DNL Name]** et **[!DNL Description]**pour votre nouvelle destination, puis utilisez les paramètres de la liste ci-dessous :![configuration](assets/dbd-new-basic.png)
   * **[!DNL Category]**:[!DNL Integrated Platforms];
   * **[!DNL Type]**:[!DNL Device-Based];
   * **[!DNL Platform]**: sélectionnez la plateforme de destination à laquelle vous souhaitez envoyer des segments d’audience.
   * **[!DNL Account]**: sélectionnez le compte publicitaire souhaité associé à la plateforme sélectionnée.
1. Cliquez sur **[!DNL Next]**.
1. Sélectionnez les étiquettes [d’exportation de](/help/using/features/data-export-controls.md#controls-labels) données que vous souhaitez définir pour cette destination.
1. Cliquez sur **[!DNL Save]**.
1. Dans la **[!DNL Segment Mappings]**section, sélectionnez les segments d’audience que vous souhaitez envoyer à cette destination.
1. Enregistrez la destination.
