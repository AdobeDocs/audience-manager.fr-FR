---
description: Cet article explique comment configurer des audiences personnalisées Twitter pour les intégrations nouvelles et existantes.
seo-description: Cet article explique comment configurer des audiences personnalisées Twitter pour les intégrations nouvelles et existantes.
seo-title: Configuration d’audiences personnalisées Twitter en tant que destination en libre-service basée sur un périphérique
solution: Audience Manager
title: Configuration d’audiences personnalisées Twitter en tant que destination en libre-service basée sur un périphérique
translation-type: tm+mt
source-git-commit: 4af2d7a4e2162f8d69273cf76aecb5f1ff00e7b6

---


# Configurer [!DNL Twitter Tailored Audiences] comme destination en libre-service basée sur un périphérique {#configure-twitter}

Cet article explique comment configurer une intégration avec des audiences [personnalisées](https://business.twitter.com/en/targeting/tailored-audiences.html)Twitter.

## Conditions préalables {#prerequisites}

Avant de configurer votre [!DNL Twitter Tailored Audiences] destination, vérifiez les conditions préalables Twitter suivantes que vous devez respecter.

1. Votre [!DNL Twitter Ads] compte doit être éligible à la publicité. Les nouveaux [!DNL Twitter Ads] comptes ne sont pas éligibles à la publicité dans les 2 premières semaines suivant leur création.
2. L’autorisation du gestionnaire [!DNL Twitter] d’audience [partenaire doit être activée pour votre compte](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) utilisateur pour lequel vous avez autorisé l’accès dans Audience Manager.
3. Lors de la création de la première [!DNL Twitter Tailored Audiences] destination dans votre instance Audience Manager, contactez le service de conseil ou le service à la clientèle Adobe pour activer la synchronisation des [!DNL Twitter] identifiants (ID de source de données = 1123) pour votre compte. Ceci est requis pour la synchronisation correcte entre Audience Manager et [!DNL Twitter].

## Ajouter une nouvelle [!DNL Twitter Tailored Audiences] destination {#add-new-twitter-destination}

Cette section décrit les étapes à suivre lors de la configuration d’une nouvelle destination basée sur un périphérique pour [!DNL Twitter Tailored Audiences]. Ce scénario suppose que vous n’avez configuré aucune [!DNL Twitter Tailored Audiences] destination existante par l’intermédiaire de votre conseiller Adobe ou du service à la clientèle.

### Étape 1. Authentifier avec [!DNL Twitter Tailored Audiences]{#step1-authenticate-with-twitter}

Avant de pouvoir ajouter la destination basée sur un périphérique, vous devez lier Audience Manager à votre [!DNL Twitter Tailored Audiences] compte. Voici comment procéder :

1. Connectez-vous à votre compte Audience Manager et accédez à **[!DNL Administration > Integrated Accounts]**. Si vous disposez d’une intégration précédemment configurée avec une plateforme de destination, elle doit apparaître dans cette page. Sinon, la page est vide.
1. Cliquez sur **[!DNL Add Account]**.
1. Sélectionnez [!DNL Twitter Tailored Audiences] puis cliquez **[!DNL Confirm]** pour être redirigé vers la page d’authentification.                     ![plates-formes intégrées](assets/dbd-integrated-platforms.png)
1. Une fois que vous êtes authentifié, vous êtes redirigé vers Audience Manager où vous devriez voir les comptes publicitaires associés. Sélectionnez le compte publicitaire à utiliser, puis cliquez sur **[!DNL Confirm]**.

### Étape 2 : Créer une destination basée sur un périphérique {#step2-create-new-destination}

Après avoir lié Audience Manager et votre [!DNL Twitter Tailored Audiences]application, vous pouvez créer la nouvelle destination. Voici comment procéder :

>[!NOTE]
>
>Vous ne pouvez pas modifier le nom d’une destination existante basée sur un périphérique. Veillez à indiquer un nom qui vous aidera à identifier correctement la destination.

1. Connectez-vous à votre compte Audience Manager, accédez à **[!DNL Audience Data > Destinations]**, puis cliquez sur **[!DNL Create Destination]**.
1. Dans la **[!DNL Basic Information]** section, saisissez un **[!DNL Name]** et **[!DNL Description]** pour votre nouvelle destination, puis utilisez les paramètres ci-dessous : ![configuration](assets/dbd-new-basic.png)
1. Cliquez sur **[!DNL Next]**.
1. Sélectionnez les étiquettes [d’exportation de](/help/using/features/data-export-controls.md#controls-labels) données que vous souhaitez définir pour cette destination.
1. Cliquez sur **[!DNL Save]**.
1. Dans la **[!DNL Segment Mappings]** section, sélectionnez les segments d’audience que vous souhaitez envoyer à cette destination.
1. Enregistrez la destination.

<!--
## Update Existing Twitter Integrations To Self-Service Administration {#update-existing-twitter-integrations}

To improve the user experience and streamline the configuration process, we are upgrading the [!DNL Twitter Tailored Audiences] integration to a self-service model, where you can perform the configuration yourself, from the Audience Manager UI. This section describes the steps you need to take to update your existing Twitter integration.

>[!IMPORTANT]
>
>The steps described below only apply if you have an existing integration with [!DNL Twitter Tailored Audiences], configured by an Audience Manager consultant or Customer Care.
> See item number 3 in [Prerequisites](#prerequisites) before migrating your [!DNL Twitter Tailored Audiences] to the self-service model.

Follow the steps below to migrate your existing [!DNL Twitter Tailored Audiences] destination to the self-service model.

1. Log in to your Audience Manager account and go to **[!DNL Administration > Integrated Accounts]**.
2. Click **[!DNL Add Account]**.
3. Select [!DNL Twitter Tailored Audiences] and click **[!DNL Confirm]** to be redirected to the authentication page. ![integrated-platforms](assets/dbd-integrated-platforms.png)
4. Once you've authenticated with your [!DNL Twitter] account, you are redirected to Audience Manager where you should see your associated advertiser accounts. Select the advertiser account that you want to use and click **[!DNL Confirm]**.
5. Go to **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** and click the Twitter destination that you need to configure.
6. Click **[!UICONTROL Edit]**. In the **[!UICONTROL Basic Information]** section, click the **[!UICONTROL Integrated Account]** drop-down menu and select the [!DNL Twitter] account that you have authenticated with at Step 4.
7. **[!UICONTROL Save]** the destination.

## Validating the Migration to Self-Service Administration {#migration-validation}

The complete migration of existing [!DNL Twitter] integrations to self-service administration can take up to 7 days. Once the migration is complete, Audience Manager shows you a notification in the UI.

You will also see a new set of audiences in your [!DNL Twitter] account, with their names prefixed by [[!DNL Adobe DMP Audience]]. Please allow up to 7 days for the audience population to be completely backfilled. Once the migration is complete, you should use these new audiences instead of the old ones. -->

## Considérations relatives au mappage de segments {#segment-mapping-considerations}

Lors du mappage des segments d’audience sur [!UICONTROL Twitter], assurez-vous de répondre aux exigences d’appellation des segments suivantes :

* Fournissez des noms de mappage de segments lisibles par des personnes. Nous vous recommandons d’utiliser le même nom que celui utilisé pour les segments d’Audience Manager.
* N’utilisez pas de caractères spéciaux (`,``%` `:``;` `@` `/` `=` ) dans les noms de mappage de segments et de segments. `?``$` Si le nom du segment Audience Manager contient ces caractères, supprimez-les avant de mapper le segment à une [!UICONTROL Twitter] destination.

### Exemple

* Nom du segment ou mappage correct : "Acheteurs américains et européens";
* Nom de segment ou de mappage incorrect : "US, Européen 5h0pP3rs".

>[!IMPORTANT]
>
>Vous ne pouvez pas modifier les noms des segments déjà mappés. Audience Manager utilise les noms des segments pour identifier correctement les segments dans l’intégration.

## Considérations relatives aux taux de correspondance {#match-rates-considerations}

* Lors de l’utilisation [!UICONTROL Twitter Tailored Audiences], les [!UICONTROL Segment Addressable Audience] mesures et [!UICONTROL Segment Match Rate] les mesures de la page de destination n’affichent aucune valeur. Il s’agit d’un comportement normal, puisque les correspondances d’audience et les taux de correspondance pour cette destination sont gérés et hébergés par [!UICONTROL Twitter], et non par Adobe.
* Actuellement, l’intégration entre Audience Manager et [!UICONTROL Twitter Tailored Audiences] ne prend pas en charge les renvois d’audience historiques. En d’autres termes, seules les qualifications de segment survenant *après* le mappage du segment à une destination Twitter sont envoyées [!UICONTROL Twitter] en temps réel.
