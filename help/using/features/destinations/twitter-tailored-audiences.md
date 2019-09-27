---
description: Cet article explique comment configurer des audiences personnalisées Twitter pour les intégrations nouvelles et existantes.
seo-description: Cet article explique comment configurer des audiences personnalisées Twitter pour les intégrations nouvelles et existantes.
seo-title: Configuration d’audiences personnalisées Twitter en tant que destination en libre-service basée sur un périphérique
solution: Audience Manager
title: Configuration d’audiences personnalisées Twitter en tant que destination en libre-service basée sur un périphérique
translation-type: tm+mt
source-git-commit: c6318921b49603015b4670a361ec85ffa29abb30

---


# Configurer [!DNL Twitter Tailored Audiences] comme destination en libre-service basée sur un périphérique {#configure-twitter}

Cet article explique comment configurer des audiences [personnalisées](https://business.twitter.com/en/targeting/tailored-audiences.html) Twitter pour les intégrations nouvelles et existantes.

## Conditions préalables {#prerequisites}

Avant de configurer votre [!DNL Twitter Tailored Audiences] destination, vérifiez les conditions préalables Twitter suivantes que vous devez respecter.

1. Votre [!DNL Twitter Ads] compte doit être éligible à la publicité. Les nouveaux [!DNL Twitter Ads] comptes ne sont pas éligibles à la publicité dans les 2 premières semaines suivant leur création.
1. L’autorisation du gestionnaire [d’audience](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) partenaire doit être activée pour votre compte utilisateur Twitter pour lequel vous avez autorisé l’accès dans Audience Manager.
1. Si vous [mettez à jour votre intégration Twitter existante vers l’administration](#update-existing-twitter-integrations)en libre-service, l’autorisation du gestionnaire [d’](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) annonces doit être activée pour votre compte utilisateur Twitter.
1. Lors de la création de la première [!DNL Twitter Tailored Audiences] destination dans votre instance Audience Manager, contactez le service de conseil ou le service à la clientèle Adobe pour activer la synchronisation des [!DNL Twitter] identifiants (ID de source de données = 1123) pour votre compte. Ceci est requis pour la synchronisation correcte entre Audience Manager et [!DNL Twitter].

## Ajouter une nouvelle [!DNL Twitter Tailored Audiences] destination {#add-new-twitter-destination}

Cette section décrit les étapes à suivre lors de la configuration d’une nouvelle destination basée sur un périphérique pour [!DNL Twitter Tailored Audiences]. Ce scénario suppose que vous n’avez configuré aucune [!DNL Twitter Tailored Audiences] destination existante par l’intermédiaire de votre conseiller Adobe ou du service à la clientèle.

### Étape 1. Authentifier avec [!DNL Twitter Tailored Audiences]{#step1-authenticate-with-twitter}

Avant de pouvoir ajouter la destination basée sur un périphérique, vous devez lier Audience Manager à votre [!DNL Twitter Tailored Audiences] compte. Voici comment procéder :

1. Connectez-vous à votre compte Audience Manager et accédez à **[!DNL Administration > Integrated Accounts]**. Si vous disposez d’une intégration précédemment configurée avec une plateforme de destination, elle doit apparaître dans cette page. Sinon, la page est vide.
2. Cliquez sur **[!DNL Add Account]**.
3. Sélectionnez [!DNL Twitter Tailored Audiences] puis cliquez **[!DNL Confirm]** pour être redirigé vers la page d’authentification.                     ![plates-formes intégrées](assets/dbd-integrated-platforms.png)
4. Une fois que vous êtes authentifié, vous êtes redirigé vers Audience Manager où vous devriez voir les comptes publicitaires associés. Sélectionnez le compte publicitaire à utiliser, puis cliquez sur **[!DNL Confirm]**.

### Étape 2 : Créer une destination basée sur un périphérique {#step2-create-new-destination}

Après avoir lié Audience Manager et votre [!DNL Twitter Tailored Audiences]application, vous pouvez créer la nouvelle destination. Voici comment procéder :

>[!NOTE]
>
>You cannot change the name of an existing device-based destination. Veillez à indiquer un nom qui vous aidera à identifier correctement la destination.

1. Log in to your Audience Manager account, go to **[!DNL Audience Data > Destinations]**, and click **[!DNL Create Destination]**.
2. In the  section, enter a  and  for your new destination, and use the settings below: setup **[!DNL Basic Information]****[!DNL Name]****[!DNL Description]**![](assets/dbd-new-basic.png)
3. Cliquez sur **[!DNL Next]**.
4. Choose the [Data Export Labels](/help/using/features/data-export-controls.md#controls-labels) that you want to set for this destination.
5. Cliquez sur **[!DNL Save]**.
6. In the  section, select the audience segments that you want to send to this destination.**[!DNL Segment Mappings]**
7. Save the destination.

## Update Existing Twitter Integrations To Self-Service Administration {#update-existing-twitter-integrations}

To improve the user experience and streamline the configuration process, we are upgrading the  integration to a self-service model, where you can perform the configuration yourself, from the Audience Manager UI. [!DNL Twitter Tailored Audiences] This section describes the steps you need to take to update your existing Twitter integration.

>[!IMPORTANT]
>
>The steps described below only apply if you have an existing integration with , configured by an Audience Manager consultant or Customer Care. [!DNL Twitter Tailored Audiences] The full upgrade process of your destination to the self-service model may take up to 5 business days. In the meantime, your destination is still active and Audience Manager continues to send audiences to it.
> See item number 3 in Prerequisites before migrating your  to the self-service model.[](#prerequisites)[!DNL Twitter Tailored Audiences]

Follow the steps below to migrate your existing  destination to the self-service model.[!DNL Twitter Tailored Audiences]

1. Log in to your Audience Manager account and go to .**[!DNL Administration > Integrated Accounts]**
1. Cliquez sur **[!DNL Add Account]**.
1. Sélectionnez [!DNL Twitter Tailored Audiences] puis cliquez **[!DNL Confirm]** pour être redirigé vers la page d’authentification. ![plates-formes intégrées](assets/dbd-integrated-platforms.png)
1. Une fois que vous êtes authentifié avec votre [!DNL Twitter] compte, vous êtes redirigé vers Audience Manager où vous devriez voir les comptes publicitaires associés. Sélectionnez le compte publicitaire à utiliser, puis cliquez sur **[!DNL Confirm]**.
1. Accédez à **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]** et cliquez sur la destination Twitter à configurer.
1. Cliquez sur **[!UICONTROL Edit]**. Dans la **[!UICONTROL Basic Information]** section, cliquez sur le menu **[!UICONTROL Integrated Account]** déroulant et sélectionnez le [!DNL Twitter] compte avec lequel vous vous êtes authentifié à l’étape 4.
1. **[!UICONTROL Save]** la destination.

## Validation de la migration vers l’administration en libre-service {#migration-validation}

La migration complète des [!DNL Twitter] intégrations existantes vers l’administration en libre-service peut prendre jusqu’à 7 jours. Une fois la migration terminée, Audience Manager affiche une notification dans l’interface utilisateur.

Vous verrez également un nouveau groupe d’audiences dans votre [!DNL Twitter] compte, dont le nom est précédé du préfixe [[!DNL Adobe DMP Audience]]. Veuillez prévoir jusqu'à 7 jours pour que le public soit complètement renversé. Une fois la migration terminée, vous devez utiliser ces nouveaux publics plutôt que les anciens.

## Considérations relatives au mappage de segments {#segment-mapping-considerations}

Lors du mappage des segments d’audience sur Twitter, veillez à respecter les exigences de nommage de segment suivantes :

* Fournissez des noms de mappage de segments lisibles par des personnes. Nous vous recommandons d’utiliser le même nom que celui utilisé pour les segments d’Audience Manager.
* N’utilisez pas de virgules dans les noms de mappage de segments et de segments.

### Exemple

* Nom du segment ou mappage correct : "Acheteurs américains et européens";
* Nom de segment ou de mappage incorrect : "US, Européen 5h0pP3rs".

>[!IMPORTANT]
>
>Vous ne pouvez pas modifier les noms des segments déjà mappés. Audience Manager utilise les noms des segments pour identifier correctement les segments dans l’intégration.

## Considérations relatives aux taux de correspondance {#match-rates-considerations}

Lors de l’utilisation [!UICONTROL Twitter Tailored Audiences], les [!UICONTROL Segment Addressable Audience] mesures et [!UICONTROL Segment Match Rate] les mesures de la page de destination n’affichent aucune valeur. Il s’agit d’un comportement normal, puisque les correspondances d’audience et les taux de correspondance pour cette destination sont gérés et hébergés par [!UICONTROL Twitter], et non par Adobe.
