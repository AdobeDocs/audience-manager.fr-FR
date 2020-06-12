---
description: Ce document explique comment fonctionne la gestion des autorisations dans Audience Manager.
seo-description: Ce document explique comment fonctionne la gestion des autorisations dans Audience Manager.
seo-title: Gestion du consentement
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: Gestion du consentement
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 34af220db2cf23ccde225eb1e05af7ce0e1513b7
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 0%

---


# Gestion du consentement

## Aperçu {#overview}

Dans les cas où l’autorisation est nécessaire pour certaines activités marketing, les clients d’Audience Manager doivent déterminer la portée et l’étendue de l’opération et déterminer si certains consentements doivent être actualisés pour pouvoir continuer à utiliser les données à l’avenir.

Audience Manager vous offre des outils pour vous aider à obtenir le consentement requis de vos utilisateurs, afin que vous puissiez leur proposer des expériences personnalisées sur plusieurs canaux.

>[!IMPORTANT]
>
> Le contenu de ce document n&#39;est pas un avis juridique et n&#39;est pas destiné à se substituer à un avis juridique.
>
> En tant que traitement de données, Adobe n&#39;est pas en mesure de fournir des conseils juridiques sur l&#39;obtention du consentement. Vous pouvez également envisager de travailler avec un fournisseur de solution de gestion du consentement, tel qu’ [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) ou [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/), et consulter le service juridique de votre société pour obtenir des conseils sur le consentement et les pratiques lors de la configuration de votre mise en oeuvre de l’inclusion.

## Service d’inclusion d’Experience Cloud

The [Experience Cloud Opt-in Service](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) lets you set up protocols for the visitor to assist you in determining if you can set a cookie on the individual&#39;s device or browser when visiting your site.

This is an extension of the [!DNL Experience Cloud ID (ECID) Service], designed to let you control whether and which Experience Cloud solutions can place cookies on web pages for visitors prior to user consent.

Le service [d’inclusion](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) Experience Cloud vous permet également de définir des protocoles à intégrer à votre plateforme de gestion du consentement (CMP) et aux systèmes existants dans le cadre de votre conception plus large.

## Gestion de l&#39;inscription / Obtention du consentement

Les clients d’Audience Manager peuvent stocker le consentement des utilisateurs pour divers cas d’utilisation, tels que la publicité ou la personnalisation en tant que caractéristiques dans Audience Manager. Les segments que vous créez à l’aide de ces caractéristiques incluent alors uniquement les utilisateurs qui donnent leur consentement pour chacun de ces cas d’utilisation. Notez que l&#39;utilisation de cette approche n&#39;arrête pas la collecte de données, mais n&#39;affecte l&#39;utilisation des données que lorsque vous envoyez des segments pour activation. Lorsque les utilisateurs retirent leur consentement, vous pouvez supprimer ces caractéristiques du profil d’utilisateurs à l’aide du processus [](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) de traitement par lot d’entrée d’Audience Manager ou du processus d’exclusion d’Audience Manager, comme indiqué ci-dessous.

## Gestion de l&#39;exclusion / Retrait du consentement

Vous pouvez gérer l’exclusion pour Adobe Experience Cloud via la page [Vos choix](https://www.adobe.com/privacy/opt-out.html#customeruse) de confidentialité. Les fonctionnalités d’un clic permettent aux utilisateurs finaux de contrôler la collecte de données et de s’exclure de celle-ci par les solutions publicitaires Adobe Experience Cloud (y compris Audience Manager). En particulier, consultez la section [clients](https://www.adobe.com/privacy/opt-out.html#customeruse) professionnels de la page Choix de confidentialité. Pour les navigateurs qui ne prennent pas en charge les cookies tiers, voir Ciblage [des identifiants](../../features/declared-ids.md#declared-id-targeting)déclarés. Pour les périphériques mobiles, récupérez les identifiants Audience Manager appropriés et appelez les API d’exclusion d’Audience Manager comme mentionné dans les exemples [d’exclusion d’ID](../../features/declared-ids.md#opt-out-examples)déclarés. Par la suite, vous pouvez arrêter la collecte de données pour les utilisateurs qui utilisent les API opt-out à partir du SDK Mobile - reportez-vous à la page Périphériques [](https://docs.adobe.com/content/help/en/mobile-services/android/gdpr-privacy-android/privacy.html) Android et périphériques [](https://docs.adobe.com/content/help/en/mobile-services/ios/privacy-gdpr-ios/privacy.html)iOS. Vous trouverez des informations supplémentaires sur l’exclusion dans la documentation [des requêtes de confidentialité des](../../overview/data-security-and-privacy/data-privacy-requests.md)données.

## Gestion du consentement pour les partenaires tiers

Les partenaires de deuxième partie sont généralement aussi des contrôleurs de données et sont propriétaires du processus d&#39;obtention du consentement nécessaire des personnes concernées pour partager les données avec leurs partenaires de données de deuxième partie. En tant que Client Audience Manager, vous avez la responsabilité de déterminer si le partenaire tiers a obtenu le consentement nécessaire pour votre utilisation. Plus de détails sur l&#39;obtention du consentement sont traités ci-dessus.

## Gestion du consentement pour Audience Marketplace Partenaires tiers

Audience Marketplace Les partenaires tiers sont également des contrôleurs de données et sont propriétaires de leur processus d’obtention du consentement et de gestion des demandes d’accès/suppression/correction. Adobe demande de manière proactive que les partenaires tiers Audience Marketplace mettent à jour leurs informations de profil de société dans [Adobe Audience Finder](https://www.adobe-audience-finder.com/) avec des informations supplémentaires sur la collecte de données utilisateur. Les informations seront fournies par les partenaires tiers Audience Marketplace et sont mises à jour régulièrement. Cependant, il appartient à chaque client Audience Manager de déterminer que le partenaire tiers Audience Marketplace a obtenu le consentement nécessaire pour l’utilisation de ce client. Adobe ne fait aucune déclaration sur la portée ou la validité du consentement obtenu ou rapporté par un partenaire tiers Audience Marketplace pour un cas d’utilisation donné.
