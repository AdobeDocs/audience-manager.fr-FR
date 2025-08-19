---
description: Cet article explique comment configurer les audiences personnalisées Twitter pour les intégrations nouvelles et existantes.
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: Configuration des audiences personnalisées Twitter en tant que destination en libre-service basée sur un appareil
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 72be9e032ec3c92cf09a5286baa872b884feaaa0
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 1%

---

# Configurer [!DNL Twitter Custom Audiences] comme destination basée sur un appareil en libre-service {#configure-twitter}

Cet article explique comment configurer une intégration avec [audiences personnalisées Twitter](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html).

## Conditions préalables {#prerequisites}

Avant de configurer votre destination [!DNL Twitter Custom Audiences], veillez à respecter les conditions préalables suivantes.

* Votre compte [!DNL Twitter Ads] doit être éligible à la publicité. Les nouveaux comptes [!DNL Twitter Ads] ne sont pas éligibles à la publicité au cours des 2 premières semaines suivant leur création.
* Le compte utilisateur [!DNL Twitter] pour lequel vous avez autorisé l’accès dans Audience Manager doit disposer de l’autorisation [Partner audience manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) activée.
* Lors de la création de la première destination [!DNL Twitter Custom Audiences] dans votre instance Audience Manager, contactez Adobe Consulting ou l’assistance clientèle pour activer la synchronisation des identifiants [!DNL Twitter] (identifiant de Source de données = 1123) pour votre compte. Cela est nécessaire à la synchronisation correcte entre Audience Manager et [!DNL Twitter].

## Ajouter une nouvelle destination [!DNL Twitter Custom Audiences] {#add-new-twitter-destination}

Cette section décrit les étapes à suivre lors de la configuration d’une nouvelle destination basée sur un appareil pour [!DNL Twitter Custom Audiences]. Ce scénario suppose que vous n’avez aucune destination [!DNL Twitter Custom Audiences] existante configurée par l’intermédiaire de votre consultant Adobe ou de l’assistance clientèle.

### Étape 1 : S’authentifier avec [!DNL Twitter Custom Audiences] {#step1-authenticate-with-twitter}

Avant de pouvoir ajouter la destination basée sur un appareil, vous devez lier Audience Manager et votre compte [!DNL Twitter Custom Audiences]. Procédez comme suit :

1. Connectez-vous à votre compte Audience Manager et accédez à **[!DNL Administration > Integrated Accounts]**. Si vous avez déjà configuré une intégration à une plateforme de destination, elle est répertoriée sur cette page. Dans le cas contraire, la page est vide.
1. Cliquez sur **[!DNL Add Account]**.
1. Sélectionnez [!DNL Twitter Custom Audiences] et cliquez sur **[!DNL Confirm]** pour être redirigé vers la page d’authentification.

   ![plateformes-intégrées](assets/dbd-integrated-platforms.png)

1. Une fois authentifié, vous êtes redirigé vers Audience Manager, où vous devriez voir les comptes publicitaires associés. Sélectionnez le compte publicitaire que vous souhaitez utiliser, puis cliquez sur **[!DNL Confirm]**.

### Étape 2 : Création d’une destination basée sur un appareil {#step2-create-new-destination}

Après avoir lié Audience Manager et votre [!DNL Twitter Custom Audiences], vous pouvez créer la nouvelle destination. Procédez comme suit :

>[!NOTE]
>
>Vous ne pouvez pas modifier le nom d’une destination existante basée sur un appareil. Veillez à fournir un nom qui vous aidera à identifier correctement la destination.

1. Connectez-vous à votre compte Audience Manager, accédez à **[!DNL Audience Data > Destinations]**, puis cliquez sur **[!DNL Create Destination]**.
1. Dans la section **[!DNL Basic Information]** , saisissez un **[!DNL Name]** et un **[!DNL Description]** pour votre nouvelle destination, puis utilisez les paramètres ci-dessous : ![configuration](assets/dbd-new-basic.png)
1. Cliquez sur **[!DNL Next]**.
1. Choisissez les [libellés d’exportation des données](/help/using/features/data-export-controls.md#controls-labels) que vous souhaitez définir pour cette destination.
1. Cliquez sur **[!DNL Save]**.
1. Dans la section **[!DNL Segment Mappings]** , sélectionnez les segments d’audience à envoyer à cette destination.
1. Enregistrez la destination.

## Considérations relatives au mappage des segments {#segment-mapping-considerations}

Lors du mappage des segments d’audience aux [!UICONTROL Twitter], veillez à respecter les exigences de dénomination de segment suivantes :

* Fournissez des noms de mappage de segments lisibles par l’utilisateur. Nous vous recommandons d’utiliser le même nom que celui des segments Audience Manager.
* N’utilisez pas de caractères spéciaux (`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`) dans les noms de mappage de segments et de segments. Si le nom de votre segment Audience Manager contient ces caractères, supprimez-les avant de mapper le segment à une destination [!UICONTROL Twitter].

### Exemple

* Nom correct du segment ou du mappage : « Acheteurs américains et européens » ;
* Nom de segment ou de mappage incorrect : « US, European 5h0pP3rs ».

>[!IMPORTANT]
>
>Vous ne pouvez pas modifier les noms des segments déjà mappés. Audience Manager utilise les noms de segment pour identifier correctement les segments dans l’intégration.

## Considérations relatives aux taux de correspondance {#match-rates-considerations}

* L’intégration entre Audience Manager et [!UICONTROL Twitter Custom Audiences] prend en charge les renvois d’audience historiques. Toutes les qualifications de segment sont envoyées à [!UICONTROL Twitter] lorsque vous créez la destination.

## Dépannage {#troubleshooting}

Pendant la configuration ou l’envoi de données à la destination Audiences personnalisées de Twitter, vous pouvez rencontrer les erreurs décrites ci-dessous. Cette section explique les causes possibles des erreurs et comment les corriger.

| Message d’erreur | Occurrence/Raison | Résolution |
|---|---|---|
| `Internal server error` | Ce message d’erreur s’affiche dans l’interface utilisateur d’Audience Manager lors de la tentative d’ajout d’un nouveau compte [!DNL Twitter] à l’aide d’une version obsolète de l’API Twitter. | Contactez l’assistance clientèle d’Adobe. |
| `Twitter Error: This request is not properly authenticated` | Ce message d’erreur s’affiche dans l’interface utilisateur d’Audience Manager lors du mappage de segments dont les noms de segment ne sont pas pris en charge vers la destination. | Passez en revue les noms de segment mappés et assurez-vous qu’ils ne contiennent pas de caractères non pris en charge. Pour obtenir la liste des caractères non pris en charge, voir [considérations relatives au mappage des segments](#segment-mapping-considerations). |
| `Twitter Error: Account XXXXXXXXX was not found` | Ce message d’erreur s’affiche dans l’interface utilisateur d’Audience Manager lorsque les informations d’identification configurées pour la destination ne sont pas autorisées à accéder au compte Twitter Ads correspondant. | <ul><li>Assurez-vous que les informations d’identification de compte que vous utilisez sont conformes aux [conditions préalables](#prerequisites).</li><li>Accédez à l’interface utilisateur des publicités Twitter à l’aide des mêmes informations d’identification et vérifiez si les audiences correctes s’affichent sous le compte `XXXXXXXXX` correspondant. </li></ul> |