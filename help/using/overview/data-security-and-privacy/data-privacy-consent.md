---
description: Ce document explique le fonctionnement de la gestion du consentement dans Audience Manager.
seo-description: Ce document explique le fonctionnement de la gestion du consentement dans Audience Manager.
seo-title: Gestion du consentement
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: Gestion du consentement
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: fbe4e8c912093c495f27ca887a44ac31d394811a

---


# Gestion du consentement

## Aperçu {#overview}

Dans les cas où le consentement est nécessaire pour certaines activités de marketing, le consentement du consommateur doit être actif (p. ex., aucune case à cocher ou silence comme avis conforme), dégroupé et les offres de services ne peuvent être subordonnés au consentement de la personne concernée. Il peut même arriver que certains consentements doivent être actualisés pour pouvoir continuer à utiliser les données.

Audience Manager vous offre les outils nécessaires pour obtenir le consentement requis de vos utilisateurs, afin que vous puissiez leur proposer des expériences personnalisées sur plusieurs canaux.

>[!IMPORTANT]
>
> Le contenu de ce document n'est pas un avis juridique et n'est pas destiné à se substituer aux conseils juridiques.
>
> En tant que traitement de données, Adobe n’est pas en mesure de fournir des conseils juridiques sur l’obtention du consentement. Nous vous recommandons de travailler avec un fournisseur de solutions de gestion du consentement, comme [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) ou [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/), pour recevoir les meilleures recommandations, et de consulter le service juridique de votre entreprise pour obtenir des conseils sur le consentement et les pratiques lors de la configuration de votre mise en oeuvre d’inclusion.

## Service d’inscription Experience Cloud

The [Experience Cloud Opt-in Service](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) service lets you set up protocols for the visitor to determine if you can set a cookie on the user's device or browser when visiting your site.

This is an extension of the [!DNL Experience Cloud ID (ECID) Service], designed to let you control whether and which Experience Cloud solutions can place cookies on web pages for visitors prior to user consent.

Le service [d’inclusion d’](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) Experience Cloud vous permet également de définir des protocoles à intégrer à votre plateforme de gestion de contenu (CMP) et aux systèmes existants dans le cadre de votre conception plus large.

## Gestion de l’inclusion / Obtention du consentement

Les clients d’Audience Manager peuvent stocker le consentement de l’utilisateur pour divers cas d’utilisation, tels que la publicité ou la personnalisation en tant que caractéristiques dans Audience Manager. La création de segments avec ces caractéristiques inclut alors uniquement les utilisateurs qui donnent leur consentement pour chacun de ces cas d’utilisation. Notez que l’utilisation de cette approche n’arrête pas la collecte des données, mais n’affecte l’utilisation des données que lorsque vous envoyez des segments pour activation. Lorsque les utilisateurs retirent leur consentement, vous pouvez supprimer ces caractéristiques du profil utilisateur à l’aide du processus [de traitement par lots](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) entrant d’Audience Manager ou du processus d’exclusion d’Audience Manager, comme indiqué ci-dessous.

## Gestion des exclusions / Retrait du consentement

La désinscription peut être gérée pour Adobe Experience Cloud via la page [Vos choix](https://www.adobe.com/privacy/opt-out.html#customeruse) de confidentialité. Les fonctionnalités d’un clic permettent aux utilisateurs finaux de contrôler la collecte de données et de s’exclure de celle-ci par les solutions publicitaires Adobe Experience Cloud (y compris Audience Manager). En particulier, consultez la section [clients](https://www.adobe.com/privacy/opt-out.html#customeruse) professionnels de la page Choix de confidentialité. Pour les navigateurs qui ne prennent pas en charge les cookies tiers, voir Ciblage des identifiants [déclarés](../../features/declared-ids.md#declared-id-targeting). Pour les périphériques mobiles, récupérez les identifiants Audience Manager appropriés et appelez les API d’exclusion d’Audience Manager comme indiqué dans les exemples [d’exclusion d’ID](../../features/declared-ids.md#opt-out-examples)déclarés. Par la suite, vous pouvez mettre fin à la collecte de données pour les utilisateurs qui utilisent les API d’exclusion du kit SDK Mobile - voir Périphériques [](https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html) Android et périphériques [](https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html)iOS. Vous trouverez des informations supplémentaires sur l’exclusion dans la documentation [des requêtes de confidentialité des](../../overview/data-security-and-privacy/data-privacy-requests.md)données.

## Gestion du consentement pour les fournisseurs de données tiers

Les fournisseurs de données tiers sont généralement également des contrôleurs de données et sont propriétaires du processus permettant d'obtenir le consentement nécessaire de la personne concernée pour partager les données avec leurs partenaires de données tiers. En tant que Client d’Audience Manager, il vous incombe de déterminer si le Fournisseur de données tiers a obtenu le consentement nécessaire pour votre cas d’utilisation. Plus de détails sur l'obtention du consentement sont traités ci-dessus.

## Gestion du consentement pour les fournisseurs de données tiers

Les fournisseurs tiers de données sont également des contrôleurs de données et sont propriétaires de leur processus d’obtention du consentement et de gestion des demandes d’accès, de suppression et de correction. Adobe demande de manière proactive aux fournisseurs de données de mettre à jour les informations de profil de leur entreprise dans [Adobe Audience Finder](https://www.adobe-audience-finder.com/) avec des informations supplémentaires sur la collecte de données utilisateur. Les informations seront obtenues auprès des fournisseurs de données et seront mises à jour régulièrement. Toutefois, il appartient à chaque client Audience Manager de déterminer que le fournisseur de données tiers a obtenu le consentement nécessaire pour le cas d’utilisation de ce client. Adobe ne fait aucune déclaration sur la portée ou la validité du consentement obtenu ou rapporté par un fournisseur de données tiers pour un cas d’utilisation donné.
