---
description: Cet article explique comment configurer de nouvelles destinations basées sur un périphérique à partir de l'interface utilisateur d'Audience Manager.
seo-description: Cet article explique comment configurer de nouvelles destinations basées sur un périphérique à partir de l'interface utilisateur d'Audience Manager.
seo-title: Ajouter de nouvelles destinations basées sur un périphérique
solution: Audience Manager
title: Ajouter de nouvelles destinations basées sur un périphérique
translation-type: tm+mt
source-git-commit: d185a1d418e99abb99c36b28dfb419a1fb3b60f5

---


# Ajouter de nouvelles destinations basées sur un périphérique {#add-new-device-based-destinations}

Cet article explique comment configurer de nouvelles destinations basées sur un périphérique à partir de l'interface utilisateur d'Audience Manager.

## Aperçu {#overview}

Le processus d'ajout d'une nouvelle destination basée sur un périphérique consiste en deux étapes principales. Tout d'abord, vous devez configurer l'intégration entre Audience Manager et le partenaire de destination. Vous pouvez ensuite créer une destination basée sur un périphérique.

>[!IMPORTANT]
>
>Toutes les destinations basées sur un périphérique ne sont pas éligibles pour le processus de configuration en libre-service. Si la destination basée sur un périphérique que vous devez ajouter ne s'affiche pas dans la liste des destinations, contactez votre consultant Adobe ou le service clientèle pour obtenir de l'aide.

## Étape 1. Authentifier à l'aide d'une plateforme de destination {#step1}

Avant de pouvoir créer une destination basée sur un périphérique, vous devez configurer l'intégration entre Audience Manager et la plateforme de destination. Voici comment procéder :

1. Connectez-vous à votre compte Audience Manager et accédez **[!DNL Administration > Integrated Accounts]**&#x200B;à. Si vous avez déjà configuré une intégration avec une plateforme de destination, vous devriez la voir dans cette page. Sinon, la page est vide.
2. Cliquez sur **[!DNL Add Account]**.
3. Sélectionnez la plateforme de destination à authentifier, puis cliquez sur **[!DNL Confirm]** pour être redirigé vers la page d'authentification de la plateforme sélectionnée. ![plateformes intégrées](assets/dbd-integrated-platforms.png)
4. Une fois que vous êtes authentifié sur votre compte de plate-forme de destination, vous êtes redirigé vers Audience Manager, où vos comptes publicitaires associés doivent être affichés. Sélectionnez le compte publicitaire à utiliser, puis cliquez **[!DNL Confirm]** sur.

## Étape 2 : Créer une destination basée sur un périphérique {#step2}

Après avoir configuré l'intégration de la plateforme de destination, vous pouvez créer la nouvelle destination. Voici comment procéder :

>[!NOTE]
>
>Vous ne pouvez pas modifier le nom d'une destination existante basée sur un périphérique. Veillez à fournir un nom qui vous aidera à identifier correctement la destination.

1. Connectez-vous à votre compte Audience Manager, puis **[!DNL Audience Data > Destinations]** cliquez **[!DNL Create Destination]** sur.
2. Dans **[!DNL Basic Information]** la section, saisissez a **[!DNL Name]** et **[!DNL Description]** pour la nouvelle destination et utilisez les paramètres de la liste ci-dessous : ![configuration](assets/dbd-new-basic.png)
   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**: sélectionnez la plateforme de destination à laquelle vous voulez envoyer les segments d'audience.
   * **[!DNL Account]**: sélectionnez un compte publicitaire associé à la plateforme sélectionnée.
3. Cliquez sur **[!DNL Next]**.
4. Choisissez [les étiquettes](/help/using/features/data-export-controls.md#controls-labels) d'exportation de données à définir pour cette destination.
5. Cliquez sur **[!DNL Save]**.
6. Dans **[!DNL Segment Mappings]** la section, sélectionnez les segments d'audience à envoyer à cette destination.
7. Enregistrez la destination.

