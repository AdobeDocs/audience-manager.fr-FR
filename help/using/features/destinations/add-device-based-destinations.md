---
description: Cet article explique comment configurer de nouvelles destinations basées sur des appareils à partir de l’interface utilisateur d’Audience Manager.
seo-description: This article explains how to configure new device-based destinations from the Audience Manager user interface.
seo-title: Add New Device-Based Destinations
solution: Audience Manager
title: Ajouter De Nouvelles Destinations Basées Sur Un Appareil
feature: Destination Basics
exl-id: c5d7de2e-085d-48b9-a596-381503c79f55
TQID: https://experienceleague.adobe.com/E8htvz6eNU2PBT3d-oCbQDzrFRf28-Wlb3HES8n69DE
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: c814092e-2730-45e8-a12d-e084529f52cb
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: c138d302-73f0-4186-93ea-10c4ba52f943
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 420
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
