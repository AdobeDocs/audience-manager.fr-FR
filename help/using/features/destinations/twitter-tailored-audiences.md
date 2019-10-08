---
description: Cet article explique comment configurer des audiences personnalisées Twitter pour les intégrations nouvelles et existantes.
seo-description: Cet article explique comment configurer des audiences personnalisées Twitter pour les intégrations nouvelles et existantes.
seo-title: Configuration d’audiences personnalisées Twitter en tant que destination en libre-service basée sur un périphérique
solution: Audience Manager
title: Configuration d’audiences personnalisées Twitter en tant que destination en libre-service basée sur un périphérique
translation-type: tm+mt
source-git-commit: 7966cac59b982b5f36af6975607df64545b74058

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

## Mettre À Jour Les Intégrations Twitter Existantes Vers L’Administration En Libre-Service {#update-existing-twitter-integrations}

Pour améliorer l’expérience utilisateur et simplifier le processus de configuration, nous mettons à niveau l’ [!DNL Twitter Tailored Audiences] intégration vers un modèle en libre-service, où vous pouvez effectuer vous-même la configuration, à partir de l’interface utilisateur d’Audience Manager. Cette section décrit les étapes à suivre pour mettre à jour votre intégration Twitter existante.

>[!IMPORTANT]
>
>Les étapes décrites ci-dessous ne s’appliquent que si vous disposez d’une intégration existante avec [!DNL Twitter Tailored Audiences], configurée par un consultant d’Audience Manager ou le service à la clientèle.
> Voir l’élément 3 dans [Conditions préalables](#prerequisites) avant de migrer [!DNL Twitter Tailored Audiences] vers le modèle de libre-service.

Suivez les étapes ci-dessous pour migrer votre [!DNL Twitter Tailored Audiences] destination existante vers le modèle en libre-service.

1. Connectez-vous à votre compte Audience Manager et accédez à **[!DNL Administration > Integrated Accounts]**.
1. Cliquez sur **[!DNL Add Account]**.
1. Sélectionnez [!DNL Twitter Tailored Audiences] puis cliquez **[!DNL Confirm]** pour être redirigé vers la page d’authentification. ![plates-formes intégrées](assets/dbd-integrated-platforms.png)
1. Une fois que vous êtes authentifié avec votre [!DNL Twitter] compte, vous êtes redirigé vers Audience Manager où vous devriez voir les comptes publicitaires associés. Sélectionnez le compte publicitaire à utiliser, puis cliquez sur **[!DNL Confirm]**.
1. Accédez à **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]** et cliquez sur la destination Twitter à configurer.
1. Cliquez sur **[!UICONTROL Edit]**. Dans la **[!UICONTROL Basic Information]** section, cliquez sur le menu **[!UICONTROL Integrated Account]** déroulant et sélectionnez le [!DNL Twitter] compte avec lequel vous vous êtes authentifié à l’étape 4.
1. **[!UICONTROL Save]** la destination.

<!-- ## Validating the Migration to Self-Service Administration {#migration-validation}

The complete migration of existing [!DNL Twitter] integrations to self-service administration can take up to 7 days. Once the migration is complete, Audience Manager shows you a notification in the UI.

You will also see a new set of audiences in your [!DNL Twitter] account, with their names prefixed by [[!DNL Adobe DMP Audience]]. Please allow up to 7 days for the audience population to be completely backfilled. Once the migration is complete, you should use these new audiences instead of the old ones. -->

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
