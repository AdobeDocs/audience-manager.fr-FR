---
description: Cet article explique comment configurer des Audiences personnalisées Twitter pour les intégrations nouvelles et existantes.
seo-description: Cet article explique comment configurer des Audiences personnalisées Twitter pour les intégrations nouvelles et existantes.
seo-title: Configuration d’Audiences personnalisées Twitter en tant que destination en libre-service basée sur un périphérique
solution: Audience Manager
title: Configuration d’Audiences personnalisées Twitter en tant que destination en libre-service basée sur un périphérique
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 1%

---


# Configurer [!DNL Twitter Tailored Audiences] comme destination en libre-service basée sur un périphérique {#configure-twitter}

Cet article explique comment configurer une intégration avec des Audiences [personnalisées](https://business.twitter.com/en/targeting/tailored-audiences.html)Twitter.

## Conditions préalables {#prerequisites}

Avant de configurer votre [!DNL Twitter Tailored Audiences] destination, veillez à vérifier les conditions préalables Twitter suivantes que vous devez respecter.

1. Votre [!DNL Twitter Ads] compte doit être éligible à la publicité. Les nouveaux [!DNL Twitter Ads] comptes ne sont pas éligibles à la publicité dans les 2 premières semaines qui suivent leur création.
2. L&#39;autorisation du gestionnaire [!DNL Twitter] d&#39;audiences [partenaire doit être activée pour votre compte](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) d&#39;utilisateur pour lequel vous avez autorisé l&#39;accès en Audience Manager.
3. Lors de la création de la première [!DNL Twitter Tailored Audiences] destination dans votre instance d’Audience Manager, contactez Adobe Consulting ou le service à la clientèle pour activer la synchronisation des [!DNL Twitter] identifiants (ID de source de données = 1123) pour votre compte. Ceci est nécessaire pour une synchronisation correcte entre l&#39;Audience Manager et [!DNL Twitter]le.

## Ajouter une nouvelle [!DNL Twitter Tailored Audiences] destination {#add-new-twitter-destination}

Cette section décrit les étapes à suivre lors de la configuration d&#39;une nouvelle destination basée sur un périphérique pour [!DNL Twitter Tailored Audiences]. Ce scénario suppose que vous n’avez configuré aucune [!DNL Twitter Tailored Audiences] destination existante par l’intermédiaire de votre consultant Adobe ou du service d’assistance clientèle.

### Étape 1. Authentifier avec [!DNL Twitter Tailored Audiences] {#step1-authenticate-with-twitter}

Avant de pouvoir ajouter la destination basée sur un périphérique, vous devez lier l’Audience Manager et votre [!DNL Twitter Tailored Audiences] compte. Voici comment procéder :

1. Connectez-vous à votre compte d’Audience Manager et accédez à **[!DNL Administration > Integrated Accounts]**. Si vous disposez d’une intégration précédemment configurée avec une plateforme de destination, elle doit apparaître dans cette page. Sinon, la page est vide.
1. Cliquez sur **[!DNL Add Account]**.
1. Sélectionnez [!DNL Twitter Tailored Audiences] puis cliquez **[!DNL Confirm]** pour être redirigé vers la page d’authentification.                     ![plates-formes intégrées](assets/dbd-integrated-platforms.png)
1. Une fois que vous êtes authentifié, vous êtes redirigé vers l’Audience Manager dans laquelle vous devriez voir les comptes d’annonceurs associés. Sélectionnez le compte publicitaire à utiliser, puis cliquez sur **[!DNL Confirm]**.

### Étape 2 : Créer une destination basée sur un périphérique {#step2-create-new-destination}

Une fois que vous avez lié l’Audience Manager et le [!DNL Twitter Tailored Audiences]vôtre, vous pouvez créer la nouvelle destination. Voici comment procéder :

>[!NOTE]
>
>Vous ne pouvez pas modifier le nom d’une destination existante basée sur un périphérique. Veillez à fournir un nom qui vous aidera à identifier correctement la destination.

1. Connectez-vous à votre compte d’Audience Manager, accédez à **[!DNL Audience Data > Destinations]**, puis cliquez sur **[!DNL Create Destination]**.
1. Dans la **[!DNL Basic Information]** section, entrez un **[!DNL Name]** et **[!DNL Description]** pour votre nouvelle destination, puis utilisez les paramètres ci-dessous : ![configuration](assets/dbd-new-basic.png)
1. Cliquez sur **[!DNL Next]**.
1. Sélectionnez les étiquettes [d&#39;exportation de](/help/using/features/data-export-controls.md#controls-labels) donnéesque vous souhaitez définir pour cette destination.
1. Cliquez sur **[!DNL Save]**.
1. Dans la **[!DNL Segment Mappings]** section, sélectionnez les segments d’audience à envoyer à cette destination.
1. Enregistrez la destination.

## Considérations sur le mappage de segments {#segment-mapping-considerations}

Lors du mappage des segments d’audience sur [!UICONTROL Twitter], veillez à respecter les exigences suivantes en matière de nommage des segments :

* Fournissez des noms de mappage de segments lisibles par les utilisateurs. Nous vous recommandons d’utiliser le même nom que celui utilisé pour les segments d’Audience Manager.
* N’utilisez pas de caractères spéciaux (`,` `%` `:``;` `@` `/` `=` ) dans les noms de mappage de segments et de segments. `?``$` Si le nom du segment d&#39;Audience Manager contient ces caractères, supprimez-les avant de mapper le segment à une [!UICONTROL Twitter] destination.

### Exemple

* Corriger le nom du segment ou du mappage : &quot;Acheteurs américains et européens&quot;;
* Nom de segment ou de mappage incorrect : &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>Vous ne pouvez pas modifier les noms des segments déjà mappés. L’Audience Manager utilise les noms de segment pour identifier correctement les segments dans l’intégration.

## Considérations sur les taux de correspondance {#match-rates-considerations}

* Lors de [!UICONTROL Twitter Tailored Audiences]l’utilisation, les [!UICONTROL Segment Addressable Audience] mesures et [!UICONTROL Segment Match Rate] les mesures de la page de destination n’affichent aucune valeur. Il s’agit d’un comportement normal, dans la mesure où les correspondances d’audiences avec les taux de correspondance pour cette destination sont gérées et hébergées par [!UICONTROL Twitter]Adobe, et non par.
* L’intégration entre l’Audience Manager et [!UICONTROL Twitter Tailored Audiences] prend en charge les remplissages d’audiences historiques. Toutes les qualifications de segment sont envoyées à [!UICONTROL Twitter] la création de la destination.
