---
description: Cet article explique comment configurer des audiences personnalisées Twitter pour les nouvelles intégrations et les intégrations existantes.
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: Configuration d’audiences personnalisées Twitter en tant que destination basée sur un appareil en libre-service
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 72be9e032ec3c92cf09a5286baa872b884feaaa0
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 1%

---

# Configurer [!DNL Twitter Custom Audiences] comme destination en libre-service basée sur un appareil {#configure-twitter}

Cet article explique comment configurer une intégration avec [Twitter d’audiences personnalisées](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html).

## Conditions préalables {#prerequisites}

Avant de configurer votre destination [!DNL Twitter Custom Audiences], assurez-vous de respecter les conditions préalables suivantes.

* Votre compte [!DNL Twitter Ads] doit être éligible à la publicité. Les nouveaux comptes [!DNL Twitter Ads] ne sont pas éligibles à la publicité dans les 2 premières semaines suivant leur création.
* Votre compte utilisateur [!DNL Twitter] pour lequel vous avez autorisé l’accès en Audience Manager doit avoir l’autorisation [Partner audience manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) activée.
* Lors de la création de la première destination [!DNL Twitter Custom Audiences] dans votre instance d’Audience Manager, contactez Adobe Consulting ou l’assistance clientèle pour activer la synchronisation des identifiants [!DNL Twitter] (identifiant de Source de données = 1123) pour votre compte. Ceci est requis pour la synchronisation correcte entre l’Audience Manager et [!DNL Twitter].

## Ajout d’une nouvelle destination [!DNL Twitter Custom Audiences] {#add-new-twitter-destination}

Cette section décrit les étapes à suivre lors de la configuration d’une nouvelle destination basée sur un appareil pour [!DNL Twitter Custom Audiences]. Ce scénario suppose qu’aucune destination [!DNL Twitter Custom Audiences] existante n’est configurée par l’intermédiaire de votre conseiller en Adobe ou de l’assistance clientèle.

### Étape 1 : Authentification avec [!DNL Twitter Custom Audiences] {#step1-authenticate-with-twitter}

Avant de pouvoir ajouter la destination basée sur l’appareil, vous devez lier l’Audience Manager à votre compte [!DNL Twitter Custom Audiences]. Procédez comme suit :

1. Connectez-vous à votre compte d’Audience Manager et accédez à **[!DNL Administration > Integrated Accounts]**. Si vous disposez d’une intégration configurée précédemment avec une plateforme de destination, elle doit apparaître dans cette page. Sinon, la page est vide.
1. Cliquez sur **[!DNL Add Account]**.
1. Sélectionnez [!DNL Twitter Custom Audiences] et cliquez sur **[!DNL Confirm]** pour accéder à la page d’authentification.

   ![integrated-platforms](assets/dbd-integrated-platforms.png)

1. Une fois que vous êtes authentifié, vous êtes redirigé vers l’Audience Manager dans laquelle vos comptes publicitaires associés doivent apparaître. Sélectionnez le compte de l&#39;annonceur que vous souhaitez utiliser et cliquez sur **[!DNL Confirm]**.

### Étape 2 : Création d’une destination basée sur un appareil {#step2-create-new-destination}

Après avoir lié l’Audience Manager et votre [!DNL Twitter Custom Audiences], vous pouvez créer la nouvelle destination. Procédez comme suit :

>[!NOTE]
>
>Vous ne pouvez pas modifier le nom d’une destination existante basée sur un appareil. Veillez à fournir un nom qui vous aidera à identifier correctement la destination.

1. Connectez-vous à votre compte d’Audience Manager, accédez à **[!DNL Audience Data > Destinations]**, puis cliquez sur **[!DNL Create Destination]**.
1. Dans la section **[!DNL Basic Information]** , saisissez un **[!DNL Name]** et un **[!DNL Description]** pour votre nouvelle destination, puis utilisez les paramètres ci-dessous : ![setup](assets/dbd-new-basic.png)
1. Cliquez sur **[!DNL Next]**.
1. Sélectionnez les [libellés d’exportation de données](/help/using/features/data-export-controls.md#controls-labels) que vous souhaitez définir pour cette destination.
1. Cliquez sur **[!DNL Save]**.
1. Dans la section **[!DNL Segment Mappings]** , sélectionnez les segments d’audience que vous souhaitez envoyer à cette destination.
1. Enregistrez la destination.

## Considérations relatives au mappage de segments {#segment-mapping-considerations}

Lors du mappage des segments d’audience sur [!UICONTROL Twitter], assurez-vous de respecter les exigences d’attribution de noms de segment suivantes :

* Fournir des noms de mappage de segments lisibles par l’utilisateur. Nous vous recommandons d’utiliser le même nom que celui utilisé pour les segments d’Audience Manager.
* N’utilisez pas de caractères spéciaux (`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`) dans les noms de mappage de segments et de segments. Si le nom du segment de votre Audience Manager contient ces caractères, supprimez-les avant de mapper le segment à une destination [!UICONTROL Twitter].

### Exemple

* Nom correct du segment ou mappage : &quot;Acheteurs américains et européens&quot;;
* Nom de segment ou mappage incorrect : &quot;US, Européen 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>Vous ne pouvez pas modifier les noms des segments déjà mappés. Audience Manager utilise les noms de segment pour identifier correctement les segments dans l’intégration.

## Considérations sur les taux de correspondance {#match-rates-considerations}

* L’intégration entre l’Audience Manager et [!UICONTROL Twitter Custom Audiences] prend en charge les renvoi d’audience historiques. Toutes les qualifications de segment sont envoyées à [!UICONTROL Twitter] lorsque vous créez la destination.

## Dépannage {#troubleshooting}

Lors de la configuration ou de l’envoi de données à la destination Audiences personnalisées du Twitter, vous pouvez rencontrer les erreurs décrites ci-dessous. Cette section explique ce qui peut entraîner des erreurs et comment les corriger.

| Message d’erreur | Occurrence/raison | Résolution |
|---|---|---|
| `Internal server error` | Ce message d’erreur s’affiche dans l’interface utilisateur d’Audience Manager lors de la tentative d’ajout d’un nouveau compte [!DNL Twitter] à l’aide d’une version obsolète de l’API Twitter. | Contactez l’assistance clientèle d’Adobe. |
| `Twitter Error: This request is not properly authenticated` | Ce message d’erreur s’affiche dans l’interface utilisateur d’Audience Manager lors de la tentative de mappage de segments avec des noms de segment non pris en charge sur la destination. | Vérifiez les noms de segment mappés et assurez-vous qu’ils ne contiennent pas de caractères non pris en charge. Voir [considérations sur le mappage des segments](#segment-mapping-considerations) pour obtenir la liste des caractères non pris en charge. |
| `Twitter Error: Account XXXXXXXXX was not found` | Ce message d’erreur s’affiche dans l’interface utilisateur de l’Audience Manager lorsque les informations d’identification configurées pour la destination ne sont pas autorisées à accéder au compte Ads de Twitter correspondant. | <ul><li>Assurez-vous que les informations d’identification du compte que vous utilisez répondent aux [conditions préalables](#prerequisites).</li><li>Accédez à l’interface utilisateur Twitter Ads à l’aide des mêmes informations d’identification et vérifiez si les audiences correctes sont affichées sous le compte `XXXXXXXXX` correspondant. </li></ul> |