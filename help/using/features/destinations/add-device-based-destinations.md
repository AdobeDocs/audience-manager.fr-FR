---
description: Cet article explique comment configurer de nouvelles destinations basées sur un périphérique à partir de l’interface utilisateur d’Audience Manager.
seo-description: Cet article explique comment configurer de nouvelles destinations basées sur un périphérique à partir de l’interface utilisateur d’Audience Manager.
seo-title: Ajouter nouvelles destinations basées sur les dispositifs
solution: Audience Manager
title: Ajouter nouvelles destinations basées sur les dispositifs
translation-type: tm+mt
source-git-commit: 69fb3601ac9de300032abc8730a40c41abc12d97
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 1%

---


# Ajouter nouvelles destinations basées sur les dispositifs {#add-new-device-based-destinations}

Cet article explique comment configurer de nouvelles destinations basées sur un périphérique à partir de l’interface utilisateur d’Audience Manager.

>[!IMPORTANT]
>
>Actuellement, la plupart des destinations basées sur un périphérique ne sont pas éligibles au flux de travail de configuration en libre-service. Si la destination basée sur le périphérique que vous devez ajouter n’est pas affichée dans la liste de destination, contactez votre conseiller Adobe ou l’assistance clientèle pour obtenir de l’aide.

## Aperçu {#overview}

Le processus d’ajout d’une nouvelle destination basée sur un périphérique comprend deux étapes principales. Tout d’abord, vous devez configurer l’intégration entre Audience Manager et le partenaire de destination. Une fois que vous avez effectué cette opération, vous pouvez créer une nouvelle destination basée sur un périphérique.

## Conditions préalables {#prerequisites}

Lors de la création de la première destination basée sur un périphérique avec une plateforme intégrée, contactez le service de conseil ou le service à la clientèle d’Adobe pour activer la synchronisation des identifiants entre Audience Manager et la plate-forme intégrée pour votre compte. Ceci est nécessaire pour une synchronisation correcte entre Audience Manager et la plateforme de destination.

## Étape 1. Authentification avec une plateforme de destination {#step1}

Avant de pouvoir créer une destination basée sur un périphérique, vous devez configurer l’intégration entre Audience Manager et la plateforme de destination. Voici comment procéder :

1. Connectez-vous à votre compte Audience Manager et accédez à **[!DNL Administration > Integrated Accounts]**. Si vous disposez d’une intégration précédemment configurée avec une plateforme de destination, elle doit apparaître dans cette page. Sinon, la page est vide.
1. Cliquez sur **[!DNL Add Account]**.
1. Sélectionnez la plate-forme de destination avec laquelle vous souhaitez vous authentifier, puis cliquez sur **[!DNL Confirm]** pour la redirection vers la page d&#39;authentification de la plate-forme sélectionnée.

   ![plates-formes intégrées](assets/dbd-integrated-platforms.png)

1. Une fois que vous êtes authentifié sur votre compte de plateforme de destination, vous êtes redirigé vers Audience Manager où vous devriez voir vos comptes d’annonceurs associés. Sélectionnez le compte publicitaire à utiliser, puis cliquez sur **[!DNL Confirm]**.

## Étape 2 : Créer une destination basée sur un périphérique {#step2}

Après avoir configuré l’intégration de la plateforme de destination, vous pouvez créer la nouvelle destination. Voici comment procéder :

>[!NOTE]
>
>Vous ne pouvez pas modifier le nom d’une destination existante basée sur un périphérique. Veillez à fournir un nom qui vous aidera à identifier correctement la destination.

1. Connectez-vous à votre compte Audience Manager, accédez à **[!DNL Audience Data > Destinations]**, puis cliquez sur **[!DNL Create Destination]**.
1. Dans la **[!DNL Basic Information]** section, entrez un **[!DNL Name]** et **[!DNL Description]** pour votre nouvelle destination, puis utilisez les paramètres de la liste ci-dessous :

   ![configuration](assets/dbd-new-basic.png)

   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**: sélectionnez la plateforme de destination vers laquelle vous souhaitez envoyer des segments d’audience.
   * **[!DNL Account]**: sélectionnez le compte publicitaire souhaité associé à la plateforme sélectionnée.
1. Cliquez sur **[!DNL Next]**.
1. Sélectionnez les étiquettes [d&#39;exportation de](/help/using/features/data-export-controls.md#controls-labels) donnéesque vous souhaitez définir pour cette destination.
1. Cliquez sur **[!DNL Save]**.
1. Dans la **[!DNL Segment Mappings]** section, sélectionnez les segments d’audience à envoyer à cette destination.
1. Enregistrez la destination.
