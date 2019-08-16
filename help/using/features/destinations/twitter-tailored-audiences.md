---
description: Cet article explique comment configurer les audiences personnalisées Twitter pour les intégrations nouvelles et existantes.
seo-description: Cet article explique comment configurer les audiences personnalisées Twitter pour les intégrations nouvelles et existantes.
seo-title: Configuration des audiences personnalisées Twitter en tant que destination basée sur un périphérique en libre-service
solution: Audience Manager
title: Configuration des audiences personnalisées Twitter en tant que destination basée sur un périphérique en libre-service
translation-type: tm+mt
source-git-commit: 0ca286bd391c9c3a5298508ecc5a42ec61a64044

---


# Configurer [!DNL Twitter Tailored Audiences] comme destination basée sur un périphérique libre-service {#configure-twitter}

Cet article explique comment configurer [les audiences personnalisées Twitter](https://business.twitter.com/en/targeting/tailored-audiences.html) pour les intégrations nouvelles et existantes.

## Conditions préalables {#prerequisites}

Avant de configurer [!DNL Twitter Tailored Audiences] votre destination, veillez à passer en revue les conditions préalables Twitter suivantes que vous devez respecter.

1. Votre [!DNL Twitter Ads] compte doit être éligible pour la publication. Les nouveaux [!DNL Twitter Ads] comptes ne peuvent pas être publiés dans les deux semaines qui suivent leur création.
2. Votre compte utilisateur Twitter autorisé à accéder à Audience Manager doit activer l'autorisation [du gestionnaire](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) d'audience de partenaire.
3. Si vous [mettez à jour votre intégration Twitter existante dans une administration en libre-service](#update-existing-twitter-integrations), l'autorisation du gestionnaire [de publicités doit être activée pour votre](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) compte utilisateur Twitter.



## Ajouter une [!DNL Twitter Tailored Audiences] nouvelle destination {#add-new-twitter-destination}

Cette section décrit les étapes à suivre lors de la configuration d'une nouvelle destination basée sur un périphérique. [!DNL Twitter Tailored Audiences] Ce scénario suppose que vous n'avez pas [!DNL Twitter Tailored Audiences] de destination existante configurée par l'intermédiaire de votre conseiller Adobe ou du service d'assistance clientèle.

### Étape 1. Authentifier avec [!DNL Twitter Tailored Audiences]{#step1-authenticate-with-twitter}

Avant de pouvoir ajouter la destination basée sur un périphérique, vous devez lier Audience Manager et votre [!DNL Twitter Tailored Audiences] compte. Voici comment procéder :

1. Connectez-vous à votre compte Audience Manager et accédez **[!DNL Administration > Integrated Accounts]**&#x200B;à. Si vous avez déjà configuré une intégration avec une plateforme de destination, vous devriez la voir dans cette page. Sinon, la page est vide.
2. Cliquez sur **[!DNL Add Account]**.
3. Sélectionnez [!DNL Twitter Tailored Audiences] et cliquez **[!DNL Confirm]** pour être redirigé vers la page d'authentification. ![plateformes intégrées](assets/dbd-integrated-platforms.png)
4. Une fois que vous êtes authentifié, vous êtes redirigé vers Audience Manager, où vos comptes publicitaires associés doivent être affichés. Sélectionnez le compte publicitaire à utiliser, puis cliquez **[!DNL Confirm]** sur.

### Étape 2 : Créer une destination basée sur un périphérique {#step2-create-new-destination}

Après avoir lié Audience Manager et votre compte [!DNL Twitter Tailored Audiences], vous pouvez créer la nouvelle destination. Voici comment procéder :

>[!NOTE]
>
>Vous ne pouvez pas modifier le nom d'une destination existante basée sur un périphérique. Veillez à fournir un nom qui vous aidera à identifier correctement la destination.

1. Connectez-vous à votre compte Audience Manager, puis **[!DNL Audience Data > Destinations]** cliquez **[!DNL Create Destination]** sur.
2. Dans **[!DNL Basic Information]** la section, saisissez a **[!DNL Name]** et **[!DNL Description]** pour la nouvelle destination et utilisez les paramètres ci-dessous : ![configuration](assets/dbd-new-basic.png)
3. Cliquez sur **[!DNL Next]**.
4. Choisissez [les étiquettes](/help/using/features/data-export-controls.md#controls-labels) d'exportation de données à définir pour cette destination.
5. Cliquez sur **[!DNL Save]**.
6. Dans **[!DNL Segment Mappings]** la section, sélectionnez les segments d'audience à envoyer à cette destination.
7. Enregistrez la destination.

## Mise à jour des intégrations Twitter existantes en administration libre {#update-existing-twitter-integrations}

Pour améliorer l'expérience des utilisateurs et simplifier le processus de configuration, nous mettons à niveau l' [!DNL Twitter Tailored Audiences] intégration vers un modèle en libre-service, où vous pouvez effectuer la configuration vous-même, depuis l'interface utilisateur d'Audience Manager. Cette section décrit les étapes à suivre pour mettre à jour votre intégration Twitter existante.

>[!IMPORTANT]
>
>Les étapes décrites ci-dessous s'appliquent uniquement si vous disposez d'une intégration [!DNL Twitter Tailored Audiences]existante, configurée par un consultant Audience Manager ou un service d'assistance clientèle. Le processus de mise à niveau complet de votre destination vers le modèle en libre-service peut prendre jusqu'à 5 jours ouvrés. En attendant, votre destination est toujours active et Audience Manager continue à l'envoyer.
> Reportez-vous à la section Numéro 3 dans [les conditions préalables](#prerequisites) avant de migrer vers [!DNL Twitter Tailored Audiences] le modèle libre-service.

Procédez comme suit pour migrer votre destination existante [!DNL Twitter Tailored Audiences] vers le modèle libre-service.

1. Connectez-vous à votre compte Audience Manager et accédez **[!DNL Administration > Integrated Accounts]**&#x200B;à.
2. Cliquez sur **[!DNL Add Account]**.
3. Sélectionnez [!DNL Twitter Tailored Audiences] et cliquez **[!DNL Confirm]** pour être redirigé vers la page d'authentification. ![plateformes intégrées](assets/dbd-integrated-platforms.png)
4. Une fois que vous êtes authentifié auprès de votre compte Twitter, vous êtes redirigé vers Audience Manager, où vos comptes publicitaires associés doivent apparaître. Sélectionnez le compte publicitaire à utiliser, puis cliquez **[!DNL Confirm]** sur.

## Considérations relatives au mappage des segments {#segment-mapping-considerations}

Lors du mappage des segments d'audience sur Twitter, veillez à respecter les exigences d'attribution de nom des segments suivantes :

* Fournissez des noms de mappage de segments lisibles. Nous vous recommandons d'utiliser le même nom que celui utilisé pour les segments Audience Manager.
* N'utilisez pas de virgules dans les noms de mappage des segments et des segments.

**Exemple**

* Segment correct ou nom de mappage : « Acheteurs E.U. et européens » ;
* Segment ou nom de mappage incorrect : « US, Europe 5 h 0 pP 3 rs ».

>[!IMPORTANT]
>
>Vous ne pouvez pas modifier le nom des segments déjà mappés. Audience Manager utilise les noms de segment pour identifier correctement les segments dans l'intégration.