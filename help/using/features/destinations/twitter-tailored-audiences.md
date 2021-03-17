---
description: Cet article explique comment configurer des Audiences personnalisées Twitter pour les intégrations nouvelles et existantes.
seo-description: Cet article explique comment configurer des Audiences personnalisées Twitter pour les intégrations nouvelles et existantes.
seo-title: Configuration d’audiences personnalisées Twitter en tant que destination basée sur un appareil en libre service
solution: Audience Manager
title: Configuration d’audiences personnalisées Twitter en tant que destination basée sur un appareil en libre service
feature: Destinations basées sur des personnes
translation-type: tm+mt
source-git-commit: 6716c871562cd0203239897fc096033160e2fc13
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 4%

---


# Configurer [!DNL Twitter Tailored Audiences] comme destination en libre-service basée sur un périphérique {#configure-twitter}

Cet article explique comment configurer une intégration avec [des Audiences personnalisées Twitter](https://business.twitter.com/en/targeting/tailored-audiences.html).

## Conditions préalables {#prerequisites}

Avant de configurer votre destination [!DNL Twitter Tailored Audiences], veillez à vérifier les conditions préalables Twitter suivantes que vous devez respecter.

1. Votre compte [!DNL Twitter Ads] doit être éligible à la publicité. Les nouveaux comptes [!DNL Twitter Ads] ne sont pas éligibles à la publicité dans les 2 premières semaines qui suivent leur création.
2. Votre compte utilisateur [!DNL Twitter] pour lequel vous avez autorisé l&#39;accès en Audience Manager doit avoir l&#39;autorisation [Gestionnaire d&#39;audiences partenaire](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) activée.
3. Lors de la création de la première destination [!DNL Twitter Tailored Audiences] dans votre instance d’Audience Manager, contactez le service conseil en Adobe ou le service à la clientèle pour activer la synchronisation des identifiants [!DNL Twitter] (ID de source de données = 1123) pour votre compte. Ceci est requis pour la synchronisation correcte entre l&#39;Audience Manager et [!DNL Twitter].

## Ajouter une nouvelle destination [!DNL Twitter Tailored Audiences] {#add-new-twitter-destination}

Cette section décrit les étapes à suivre lors de la configuration d&#39;une nouvelle destination basée sur un périphérique pour [!DNL Twitter Tailored Audiences]. Ce scénario suppose que vous n’avez configuré aucune destination [!DNL Twitter Tailored Audiences] existante par l’intermédiaire de votre conseiller en Adobe ou du service d’assistance clientèle.

### Étape 1. Authentifier avec [!DNL Twitter Tailored Audiences] {#step1-authenticate-with-twitter}

Avant de pouvoir ajouter la destination basée sur un périphérique, vous devez lier l&#39;Audience Manager et votre compte [!DNL Twitter Tailored Audiences]. Voici comment procéder :

1. Connectez-vous à votre compte d’Audience Manager et accédez à **[!DNL Administration > Integrated Accounts]**. Si vous disposez d’une intégration précédemment configurée avec une plateforme de destination, elle doit apparaître dans cette page. Sinon, la page est vide.
1. Cliquez sur **[!DNL Add Account]**.
1. Sélectionnez [!DNL Twitter Tailored Audiences] et cliquez sur **[!DNL Confirm]** pour rediriger l’utilisateur vers la page d’authentification.                     ![plates-formes intégrées](assets/dbd-integrated-platforms.png)
1. Une fois que vous êtes authentifié, vous êtes redirigé vers l’Audience Manager dans laquelle vous devriez voir les comptes d’annonceurs associés. Sélectionnez le compte publicitaire à utiliser, puis cliquez sur **[!DNL Confirm]**.

### Étape 2 : Créer une destination basée sur un périphérique {#step2-create-new-destination}

Après avoir lié l&#39;Audience Manager et votre [!DNL Twitter Tailored Audiences], vous pouvez créer la nouvelle destination. Voici comment procéder :

>[!NOTE]
>
>Vous ne pouvez pas modifier le nom d’une destination existante basée sur un périphérique. Veillez à fournir un nom qui vous aidera à identifier correctement la destination.

1. Connectez-vous à votre compte d’Audience Manager, accédez à **[!DNL Audience Data > Destinations]**, puis cliquez sur **[!DNL Create Destination]**.
1. Dans la section **[!DNL Basic Information]**, saisissez **[!DNL Name]** et **[!DNL Description]** pour votre nouvelle destination, puis utilisez les paramètres ci-dessous : ![configuration](assets/dbd-new-basic.png)
1. Cliquez sur **[!DNL Next]**.
1. Sélectionnez les [étiquettes d&#39;exportation de données](/help/using/features/data-export-controls.md#controls-labels) que vous souhaitez définir pour cette destination.
1. Cliquez sur **[!DNL Save]**.
1. Dans la section **[!DNL Segment Mappings]**, sélectionnez les segments d&#39;audience à envoyer à cette destination.
1. Enregistrez la destination.

## Considérations sur le mappage de segments {#segment-mapping-considerations}

Lors du mappage des segments d’audience sur [!UICONTROL Twitter], veillez à respecter les exigences suivantes en matière de nommage des segments :

* Fournissez des noms de mappage de segments lisibles par les utilisateurs. Nous vous recommandons d’utiliser le même nom que celui utilisé pour les segments d’Audience Manager.
* N’utilisez pas de caractères spéciaux (`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`) dans les noms de mappage de segments et de segments. Si le nom du segment d&#39;Audience Manager contient ces caractères, supprimez-les avant de mapper le segment à une destination [!UICONTROL Twitter].

### Exemple

* Corriger le nom du segment ou du mappage : &quot;Acheteurs américains et européens&quot;;
* Nom de segment ou de mappage incorrect : &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>Vous ne pouvez pas modifier les noms des segments déjà mappés. L’Audience Manager utilise les noms de segment pour identifier correctement les segments dans l’intégration.

## Considérations sur les taux de correspondance {#match-rates-considerations}

* L&#39;intégration entre l&#39;Audience Manager et [!UICONTROL Twitter Tailored Audiences] prend en charge les remplissages d&#39;audiences historiques. Toutes les qualifications de segment sont envoyées à [!UICONTROL Twitter] lorsque vous créez la destination.
