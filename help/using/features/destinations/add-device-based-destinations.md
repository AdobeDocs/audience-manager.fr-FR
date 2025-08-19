---
description: Cet article explique comment configurer de nouvelles destinations basées sur des appareils à partir de l’interface utilisateur d’Audience Manager.
seo-description: This article explains how to configure new device-based destinations from the Audience Manager user interface.
seo-title: Add New Device-Based Destinations
solution: Audience Manager
title: Ajouter De Nouvelles Destinations Basées Sur Un Appareil
feature: Destination Basics
exl-id: c5d7de2e-085d-48b9-a596-381503c79f55
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 2%

---

# Ajouter De Nouvelles Destinations Basées Sur Un Appareil {#add-new-device-based-destinations}

Cet article explique comment configurer de nouvelles destinations basées sur des appareils à partir de l’interface utilisateur d’Audience Manager.

>[!IMPORTANT]
>
>Actuellement, la plupart des destinations basées sur des appareils ne sont pas éligibles au workflow de configuration en libre-service. Si la destination basée sur l’appareil que vous devez ajouter ne s’affiche pas dans la liste des destinations, contactez votre consultant Adobe ou le service clientèle pour obtenir de l’aide.

## Présentation {#overview}

Le processus d’ajout d’une nouvelle destination basée sur un appareil se compose de deux étapes principales. Tout d’abord, vous devez configurer l’intégration entre Audience Manager et le partenaire de destination. Une fois cette opération effectuée, vous pouvez créer une nouvelle destination basée sur un appareil.

## Conditions préalables {#prerequisites}

Lors de la création de la première destination basée sur un appareil avec une plateforme intégrée, contactez Adobe Consulting ou l’assistance clientèle pour activer la synchronisation des identifiants entre Audience Manager et la plateforme intégrée pour votre compte. Cela est nécessaire à la synchronisation correcte entre Audience Manager et la plateforme de destination.

## Étape 1 : Authentification avec une plateforme de destination {#step1}

Avant de pouvoir créer une destination basée sur un appareil, vous devez configurer l’intégration entre Audience Manager et la plateforme de destination. Procédez comme suit :

1. Connectez-vous à votre compte Audience Manager et accédez à **[!DNL Administration > Integrated Accounts]**. Si vous avez déjà configuré une intégration à une plateforme de destination, elle est répertoriée sur cette page. Dans le cas contraire, la page est vide.
1. Cliquez sur **[!DNL Add Account]**.
1. Sélectionnez la plateforme de destination avec laquelle vous souhaitez vous authentifier et cliquez sur **[!DNL Confirm]** pour être redirigé vers la page d’authentification de la plateforme sélectionnée.

   ![plateformes-intégrées](assets/dbd-integrated-platforms.png)

1. Une fois que vous êtes authentifié sur votre compte de plateforme de destination, vous êtes redirigé vers Audience Manager, où vous devriez voir les comptes publicitaires associés. Sélectionnez le compte publicitaire que vous souhaitez utiliser, puis cliquez sur **[!DNL Confirm]**.

## Étape 2 : Création d’une destination basée sur un appareil {#step2}

Après avoir configuré l’intégration de la plateforme de destination, vous pouvez créer la nouvelle destination. Procédez comme suit :

>[!NOTE]
>
>Vous ne pouvez pas modifier le nom d’une destination existante basée sur un appareil. Veillez à fournir un nom qui vous aidera à identifier correctement la destination.

1. Connectez-vous à votre compte Audience Manager, accédez à **[!DNL Audience Data > Destinations]**, puis cliquez sur **[!DNL Create Destination]**.
1. Dans la section **[!DNL Basic Information]** , saisissez un **[!DNL Name]** et un **[!DNL Description]** pour votre nouvelle destination, puis utilisez les paramètres de la liste ci-dessous :

   ![configuration](assets/dbd-new-basic.png)

   * **[!DNL Category]** : [!DNL Integrated Platforms] ;
   * **[!DNL Type]** : [!DNL Device-Based] ;
   * **[!DNL Platform]** : sélectionnez la plateforme de destination vers laquelle vous souhaitez envoyer des segments d’audience.
   * **[!DNL Account]** : sélectionnez le compte de l’annonceur souhaité associé à la plateforme sélectionnée.
1. Cliquez sur **[!DNL Next]**.
1. Choisissez les [libellés d’exportation des données](/help/using/features/data-export-controls.md#controls-labels) que vous souhaitez définir pour cette destination.
1. Cliquez sur **[!DNL Save]**.
1. Dans la section **[!DNL Segment Mappings]** , sélectionnez les segments d’audience à envoyer à cette destination.
1. Enregistrez la destination.
