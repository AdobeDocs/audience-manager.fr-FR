---
description: Ce document explique le fonctionnement de la gestion du consentement dans Audience Manager.
seo-description: Ce document explique le fonctionnement de la gestion du consentement dans Audience Manager.
seo-title: Gestion du consentement
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: Gestion du consentement
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 9004dc46c0ac431e9f193467a2147a2d9ac36cdc

---


# Gestion du consentement

## Aperçu {#overview}

Dans les cas où le consentement est nécessaire pour certaines activités marketing, les clients d’Audience Manager doivent déterminer la portée et l’étendue de certaines autorisations et déterminer s’ils doivent être actualisés pour pouvoir continuer à utiliser les données à l’avenir.

Audience Manager vous propose des outils pour vous aider à obtenir le consentement de vos utilisateurs, afin que vous puissiez leur proposer des expériences personnalisées sur plusieurs canaux.

>[!IMPORTANT]
>
> Le contenu de ce document n'est pas un avis juridique et n'est pas destiné à se substituer aux conseils juridiques.
>
> En tant que traitement de données, Adobe n’est pas en mesure de fournir des conseils juridiques sur l’obtention du consentement. Vous pouvez également envisager de travailler avec un fournisseur de solution de gestion du consentement, tel qu’ [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) ou [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/), et consulter le service juridique de votre entreprise pour obtenir des conseils sur le consentement et les pratiques lors de la configuration de votre mise en oeuvre d’inclusion.

## Service d’inscription Experience Cloud

The [Experience Cloud Opt-in Service](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) lets you set up protocols for the visitor to assist you in determining if you can set a cookie on the individual's device or browser when visiting your site.

This is an extension of the [!DNL Experience Cloud ID (ECID) Service], designed to let you control whether and which Experience Cloud solutions can place cookies on web pages for visitors prior to user consent.

Le service [d’inclusion d’](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) Experience Cloud vous permet également de définir des protocoles à intégrer à votre plateforme de gestion de contenu (CMP) et aux systèmes existants dans le cadre de votre conception plus large.

## Gestion de l’inclusion / Obtention du consentement

Les clients d’Audience Manager peuvent stocker le consentement de l’utilisateur pour divers cas d’utilisation, tels que la publicité ou la personnalisation en tant que caractéristiques dans Audience Manager. Les segments que vous créez avec ces caractéristiques incluent alors uniquement les utilisateurs qui donnent leur consentement pour chacun de ces cas d’utilisation. Notez que l’utilisation de cette approche n’arrête pas la collecte des données, mais n’affecte l’utilisation des données que lorsque vous envoyez des segments pour activation. Lorsque les utilisateurs retirent leur consentement, vous pouvez supprimer ces caractéristiques du profil utilisateur à l’aide du processus [de traitement par lots](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) entrant d’Audience Manager ou du processus d’exclusion d’Audience Manager, comme indiqué ci-dessous.

## Gestion des exclusions / Retrait du consentement

L’exclusion peut être gérée pour Adobe Experience Cloud via la page [Vos choix](https://www.adobe.com/privacy/opt-out.html#customeruse) de confidentialité. Les fonctionnalités d’un clic permettent aux utilisateurs finaux de contrôler et d’exclure la collecte de données par les solutions publicitaires Adobe Experience Cloud (y compris Audience Manager). En particulier, consultez la section [clients](https://www.adobe.com/privacy/opt-out.html#customeruse) professionnels de la page Choix de confidentialité. Pour les navigateurs qui ne prennent pas en charge les cookies tiers, voir Ciblage des identifiants [déclarés](../../features/declared-ids.md#declared-id-targeting). Pour les périphériques mobiles, récupérez les identifiants Audience Manager appropriés et appelez les API d’exclusion d’Audience Manager comme indiqué dans les exemples [d’exclusion d’ID](../../features/declared-ids.md#opt-out-examples)déclarés. Par la suite, vous pouvez mettre fin à la collecte de données pour les utilisateurs qui utilisent les API d’exclusion du kit SDK Mobile - voir Périphériques [](https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html) Android et périphériques [](https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html)iOS. Vous trouverez des informations supplémentaires sur l’exclusion dans la documentation [des requêtes de confidentialité des](../../overview/data-security-and-privacy/data-privacy-requests.md)données.

## Gestion du consentement pour les partenaires tiers

Les partenaires tiers sont généralement aussi des contrôleurs de données et sont propriétaires du processus permettant d'obtenir le consentement nécessaire de la personne concernée pour partager les données avec ses partenaires tiers. En tant que Client d’Audience Manager, il vous incombe de déterminer si le Partenaire tiers a obtenu le consentement nécessaire pour votre cas d’utilisation. Plus de détails sur l'obtention du consentement sont traités ci-dessus.

## Gestion du consentement pour Audience Marketplace Partenaires tiers

Les partenaires tiers Audience Marketplace sont également des contrôleurs de données et possèdent leur processus d’obtention du consentement et de gestion des demandes d’accès, de suppression et de correction. Adobe demande de manière proactive aux partenaires tiers Audience Marketplace de mettre à jour leurs informations de profil d’entreprise dans [Adobe Audience Finder](https://www.adobe-audience-finder.com/) avec des informations supplémentaires sur la collecte de données utilisateur. Les informations seront obtenues auprès des partenaires tiers Audience Marketplace et sont mises à jour régulièrement. Il appartient toutefois à chaque client Audience Manager de déterminer que le partenaire tiers Audience Marketplace a obtenu le consentement nécessaire pour l’utilisation de ce client. Adobe ne fait aucune déclaration sur la portée ou la validité du consentement obtenu ou rapporté par un partenaire tiers Audience Marketplace pour un cas d’utilisation donné.
