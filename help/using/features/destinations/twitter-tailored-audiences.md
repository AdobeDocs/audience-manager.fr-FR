---
description: Cet article explique comment configurer des audiences personnalisées Twitter pour les nouvelles intégrations et les intégrations existantes.
seo-description: Cet article explique comment configurer des audiences personnalisées Twitter pour les nouvelles intégrations et les intégrations existantes.
seo-title: Configuration d’audiences personnalisées Twitter en tant que destination basée sur un appareil en libre service
solution: Audience Manager
title: Configuration d’audiences personnalisées Twitter en tant que destination basée sur un appareil en libre service
feature: Destinations basées sur les personnes
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 4%

---

# Configuration de [!DNL Twitter Tailored Audiences] en tant que destination basée sur un appareil en libre-service {#configure-twitter}

Cet article explique comment configurer une intégration avec les [audiences personnalisées Twitter](https://business.twitter.com/en/targeting/tailored-audiences.html).

## Conditions préalables {#prerequisites}

Avant de configurer votre destination [!DNL Twitter Tailored Audiences], vérifiez les conditions préalables Twitter suivantes que vous devez remplir.

1. Votre compte [!DNL Twitter Ads] doit être éligible à la publicité. Les nouveaux comptes [!DNL Twitter Ads] ne sont pas éligibles à la publicité dans les 2 premières semaines qui suivent leur création.
2. Votre compte utilisateur [!DNL Twitter] pour lequel vous avez autorisé l’accès en Audience Manager doit disposer de l’autorisation [Partner audience manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) activée.
3. Lors de la création de la première destination [!DNL Twitter Tailored Audiences] dans votre instance d’Audience Manager, contactez le conseiller d’Adobe ou l’assistance clientèle pour activer la synchronisation des identifiants [!DNL Twitter] (ID de source de données = 1123) pour votre compte. Ceci est nécessaire pour une synchronisation correcte entre l’Audience Manager et [!DNL Twitter].

## Ajouter une nouvelle [!DNL Twitter Tailored Audiences] destination {#add-new-twitter-destination}

Cette section décrit les étapes à suivre lors de la configuration d’une nouvelle destination basée sur un appareil pour [!DNL Twitter Tailored Audiences]. Ce scénario suppose qu’aucune destination [!DNL Twitter Tailored Audiences] existante n’est configurée via votre conseiller en Adobe ou l’assistance clientèle.

### Étape 1. Authentifiez-vous avec [!DNL Twitter Tailored Audiences] {#step1-authenticate-with-twitter}

Avant de pouvoir ajouter la destination basée sur l’appareil, vous devez lier l’Audience Manager et votre compte [!DNL Twitter Tailored Audiences]. Procédez comme suit :

1. Connectez-vous à votre compte d’Audience Manager et accédez à **[!DNL Administration > Integrated Accounts]**. Si vous disposez d’une intégration configurée précédemment avec une plateforme de destination, elle doit apparaître dans cette page. Sinon, la page est vide.
1. Cliquez sur **[!DNL Add Account]**.
1. Sélectionnez [!DNL Twitter Tailored Audiences] et cliquez sur **[!DNL Confirm]** pour accéder à la page d’authentification.                     ![Plateformes intégrées](assets/dbd-integrated-platforms.png)
1. Une fois que vous êtes authentifié, vous êtes redirigé vers l’Audience Manager dans laquelle vos comptes publicitaires associés doivent apparaître. Sélectionnez le compte de l’annonceur que vous souhaitez utiliser, puis cliquez sur **[!DNL Confirm]**.

### Étape 2 : Création d’une destination basée sur un appareil {#step2-create-new-destination}

Une fois que vous avez lié l’Audience Manager et votre [!DNL Twitter Tailored Audiences], vous pouvez créer la nouvelle destination. Procédez comme suit :

>[!NOTE]
>
>Vous ne pouvez pas modifier le nom d’une destination existante basée sur un appareil. Veillez à fournir un nom qui vous aidera à identifier correctement la destination.

1. Connectez-vous à votre compte d’Audience Manager, accédez à **[!DNL Audience Data > Destinations]**, puis cliquez sur **[!DNL Create Destination]**.
1. Dans la section **[!DNL Basic Information]** , saisissez **[!DNL Name]** et **[!DNL Description]** pour votre nouvelle destination, puis utilisez les paramètres ci-dessous : ![setup](assets/dbd-new-basic.png)
1. Cliquez sur **[!DNL Next]**.
1. Sélectionnez les [Étiquettes d’exportation de données](/help/using/features/data-export-controls.md#controls-labels) que vous souhaitez définir pour cette destination.
1. Cliquez sur **[!DNL Save]**.
1. Dans la section **[!DNL Segment Mappings]** , sélectionnez les segments d’audience que vous souhaitez envoyer à cette destination.
1. Enregistrez la destination.

## Considérations relatives au mappage de segments {#segment-mapping-considerations}

Lors du mappage des segments d’audience sur [!UICONTROL Twitter], assurez-vous de respecter les exigences d’attribution de noms de segment suivantes :

* Fournir des noms de mappage de segments lisibles par l’utilisateur. Nous vous recommandons d’utiliser le même nom que celui utilisé pour les segments d’Audience Manager.
* N’utilisez pas de caractères spéciaux (`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`) dans les noms de mappage de segments et de segments. Si le nom du segment de votre Audience Manager contient ces caractères, supprimez-les avant de mapper le segment à une destination [!UICONTROL Twitter].

### Exemple

* Nom correct du segment ou du mappage : &quot;Acheteurs américains et européens&quot;;
* Nom de segment ou mappage incorrect : &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>Vous ne pouvez pas modifier les noms des segments déjà mappés. Audience Manager utilise les noms de segment pour identifier correctement les segments dans l’intégration.

## Considérations sur les taux de correspondance {#match-rates-considerations}

* L’intégration entre l’Audience Manager et [!UICONTROL Twitter Tailored Audiences] prend en charge les renvoi d’audience historiques. Toutes les qualifications de segment sont envoyées à [!UICONTROL Twitter] lorsque vous créez la destination.
