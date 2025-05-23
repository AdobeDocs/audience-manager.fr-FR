---
description: Ce document décrit le fonctionnement de la gestion du consentement dans Audience Manager.
seo-description: This document explains how consent management works in Audience Manager.
seo-title: Consent Management
solution: Audience Manager
keywords: Interface utilisateur RGPD, API RGPD, CCPA, confidentialité, consentement
title: Gestion du consentement
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: Data Governance & Privacy
exl-id: 9e545e8d-dbe4-4df9-8801-af3c2c73e406
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 98%

---

# Gestion du consentement

## Présentation {#overview}

Dans les cas nécessitant un consentement pour certaines activités de marketing, les clients d’Audience Manager doivent déterminer la portée et la nécessité ou non d’actualiser certains consentements afin de continuer à utiliser les données à l’avenir.

Audience Manager offre des outils qui vous permettent d’obtenir les consentements requis de vos utilisateurs, afin que vous puissiez leur proposer des expériences personnalisées sur différents canaux.

>[!IMPORTANT]
>
> Le contenu de ce document ne constitue pas un avis juridique et ne vise pas à remplacer un avis juridique.
>
> En tant que responsable du traitement des données, Adobe n’est pas en mesure de fournir d’avis juridiques sur l’obtention du consentement. Il est également recommandé de collaborer avec un fournisseur de solution de gestion du consentement, tel qu’[Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) ou [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/), et de consulter le service juridique de votre société pour obtenir des conseils sur le consentement et les pratiques lors de la mise en œuvre de votre accord préalable.

## Service d’accord préalable d’Experience Cloud

Le [service d’accord préalable d’Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=fr) vous permet de configurer des protocoles permettant aux visiteurs de vous aider à déterminer si vous pouvez installer des cookies sur l’appareil ou le navigateur de la personne qui visite votre site.

Il s’agit d’une extension du [!DNL Experience Cloud ID (ECID) Service] conçu pour vous permettre de contrôler l’introduction de cookies par les solutions Experience Cloud sur les pages web pour les visiteurs avant d’avoir eu l’accord de l’utilisateur (ainsi que de désigner les solutions concernées).

Le [service d’accord préalable d’Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=fr) vous permet également de configurer des protocoles à intégrer à votre plateforme de gestion du consentement (CMP) et aux systèmes existants dans le cadre de votre conception globale.

## Gestion de l’accord préalable/Obtention du consentement

Les clients d’Audience Manager peuvent stocker le consentement des utilisateurs pour divers cas d’utilisation, tels que la publicité ou la personnalisation en tant que caractéristiques dans Audience Manager. Les segments que vous créez à l’aide de ces caractéristiques comprennent uniquement les utilisateurs qui donnent leur consentement respectif pour chacun de ces cas d’utilisation. Notez que l’utilisation de cette approche n’empêche pas la collecte de données et n’affecte l’utilisation des données que lorsque vous envoyez des segments pour activation. Lorsque les utilisateurs retirent leur consentement, vous pouvez supprimer ces caractéristiques du profil utilisateur à l’aide du [traitement par lots entrants](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) d’Audience Manager ou du processus d’exclusion d’Audience Manager comme décrit ci-dessous.

## Gestion de l’exclusion/Retrait du consentement

Vous pouvez gérer l’exclusion pour Adobe Experience Cloud via la page [Vos choix en matière de confidentialité](https://www.adobe.com/fr/privacy/opt-out.html#customeruse). Les fonctionnalités en un clic permettent aux utilisateurs finaux de contrôler la collecte de données et de ne pas y participer grâce aux solutions publicitaires d’Adobe Experience Cloud (y compris Audience Manager). Plus précisément, consultez la [section client professionnel](https://www.adobe.com/fr/privacy/opt-out.html#customeruse) de la page Choix de confidentialité. Pour les navigateurs qui ne prennent pas en charge les cookies tiers, consultez [Ciblage des identifiants déclarés](../../features/declared-ids.md#declared-id-targeting). Pour les appareils mobiles, récupérez les identifiants d’Audience Manager appropriés et appelez les API d’exclusion d’Audience Manager comme mentionné dans les [exemples d’exclusion d’identifiants déclarés](../../features/declared-ids.md#opt-out-examples). Ensuite, vous pouvez suspendre la collecte de données pour les utilisateurs disposant des API d’exclusion du SDK Mobile. Consultez [Appareils Android](https://experienceleague.adobe.com/docs/mobile-services/android/gdpr-privacy-android/privacy.html?lang=fr) et [Appareils iOS](https://experienceleague.adobe.com/docs/mobile-services/ios/privacy-gdpr-ios/privacy.html?lang=fr). Vous trouverez des informations supplémentaires sur l’exclusion dans la [documentation sur les requêtes de confidentialité des données](../../overview/data-security-and-privacy/data-privacy-requests.md).

## Gestion du consentement pour les partenaires secondaires

Les partenaires secondaires sont généralement aussi des contrôleurs de données et sont propriétaires du processus d’obtention des consentements nécessaires des titulaires de données pour partager des données avec leurs partenaires de données secondaires. Il vous incombe, en tant que client d’Audience Manager, de déterminer si le partenaire secondaire a obtenu le consentement nécessaire pour votre cas d’utilisation. De plus amples informations sur l’obtention du consentement sont fournies ci-dessus.

## Gestion du consentement pour les partenaires tiers d’Audience Marketplace

Les partenaires tiers d’Audience Marketplace sont également des contrôleurs de données et sont propriétaires du processus d’obtention des consentements et de gestion des demandes d’accès, de suppression et de correction. Adobe demande de manière proactive aux partenaires tiers d’Audience Marketplace de mettre à jour leurs informations de profil de la société dans [Adobe Audience Finder](https://www.adobe-audience-finder.com/) avec des informations supplémentaires sur la collecte de données utilisateur. Les informations sont fournies par les partenaires tiers d’Audience Marketplace et mises à jour régulièrement. Cependant, il appartient à chaque client d’Audience Manager de déterminer si le partenaire tiers d’Audience Marketplace a obtenu le consentement nécessaire pour le cas d’utilisation de ce client. Adobe ne garantit pas la portée ou la validité du consentement obtenu ou rapporté par un partenaire tiers d’Audience Marketplace pour un cas d’utilisation donné.
