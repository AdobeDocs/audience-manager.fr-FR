---
description: Décrit l’intégration d’Audience Manager et la conformité aux bonnes pratiques généralement admises en ce qui concerne la confidentialité des consommateurs et les procédures d’opposition.
seo-description: Describes Audience Manager integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.
seo-title: Data Privacy Overview
solution: Audience Manager
title: Présentation de la confidentialité des données
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
feature: Data Governance & Privacy
exl-id: 051de369-e762-49fb-b65f-6faf94db48a4
source-git-commit: 8bee593d0359f87f030840f87d70025dd5ea33ed
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 52%

---

# Présentation de la confidentialité des données {#data-privacy}

## Présentation

La documentation relative à la Confidentialité des données décrit l’intégration de [!DNL Audience Manager] et la conformité aux bonnes pratiques généralement acceptées en ce qui concerne la confidentialité des consommateurs et les procédures d’exclusion.

[!DNL Audience Manager] reconnaît l’importance de la relation entre les consommateurs et les marques en ligne avec lesquelles ils interagissent. Les deux parties bénéficient d’un échange transparent d’éléments de données pseudonymes :

* Les consommateurs reçoivent du contenu personnalisé, des offres de produits à prix réduit et des expériences utilisateur simplifiées.
* Les marques reçoivent des flux de revenus vitaux qui prennent en charge plusieurs modèles de commerce en ligne.

Dans le cadre de la prise en charge continue de ce modèle, [!DNL Audience Manager] s&#39;engage à vous fournir les outils qui vous permettront d&#39;offrir transparence et contrôle à vos clients, tout en proposant des publicités personnalisées soumises aux [ principes d&#39;autoréglementation d&#39;Advertising comportementale en ligne (OBA)](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/).

## [!DNL GDPR] {#gdpr}

Le [règlement général sur la protection des données (RGPD)](https://gdpr.eu/data-privacy/) a introduit plusieurs nouveaux droits à la confidentialité des données pour les membres de l’Union européenne, y compris le **droit d’accès** et le **droit à l’oubli**. Cela signifie que tout citoyen [!DNL EU] dont les données personnelles ont été collectées par votre entreprise peut demander à accéder à ses données ou à les supprimer à tout moment. Le non-respect de ces requêtes par votre organisation peut être sanctionné par des amendes de plusieurs millions de dollars.

Pour se conformer à [!DNL GDPR], [!DNL Audience Manager] prend en charge l’accès aux données et la suppression des [requêtes](data-privacy-requests.md).

## [!DNL CCPA] {#ccpa}

La [California Consumer Privacy Act (CCPA)](https://www.caprivacy.org/about), entrée en vigueur le 1er janvier 2020, accorde aux résidents de Californie de nouveaux droits sur leurs informations personnelles et impose des responsabilités en matière de protection des données à certaines entités qui exercent leurs activités en Californie.

[!DNL CCPA] accorde de nouveaux droits à la confidentialité des données aux résidents de Californie, notamment le droit d’accéder à leurs données personnelles et de les supprimer, ainsi que de savoir si leurs données personnelles sont vendues ou divulguées (et à qui). Pour se conformer à [!DNL CCPA], [!DNL Audience Manager] prend en charge [!DNL CCPA] l’accès et la suppression de [requêtes](data-privacy-requests.md).

Pour plus d’informations, consultez le [Centre de traitement des données personnelles d’Adobe](https://www.adobe.com/fr/privacy/opt-out.html).

## Conformité aux réglementations {#compliance}

[!DNL Audience Manager] vous aide à respecter vos obligations en vertu de certaines réglementations de confidentialité, par le biais d’outils de confidentialité comme le [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=fr) pour les demandes d’accès et de suppression de données.

Ce service fournit une [!DNL RESTful API] et une interface utilisateur pour vous aider à gérer les requêtes de données des consommateurs. [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=fr) vous permet d’envoyer des requêtes d’accès aux données personnelles et de suppression de celles-ci, sur la base d’une requête individuelle de consommateur, ce qui contribue à automatiser cette partie de vos obligations de conformité.

Bien que les demandes d’accès et de suppression des données soient gérées par le Privacy Service, les [demandes d’exclusion](data-privacy-requests.md#opt-out-requests) sont actuellement prises en charge par le biais de l’ [’&rbrace;API DCS](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md). Pour plus d’informations, consultez [Requêtes de confidentialité des données](data-privacy-requests.md).

## Concepts associés {#related-concepts}

* [Requêtes de confidentialité des données](data-privacy-requests.md)
* [Gestion du consentement](data-privacy-consent.md)
* [Module d’Audience Manager pour le TCF de l’IAB](aam-iab-plugin.md)
* [Identifiants d’Audience Manager](data-privacy-ids.md)
* [Glossaire de la CCPA](aam-ccpa-glossary.md)
* [Glossaire du RGPD](aam-gdpr-glossary.md)
* [Considérations relatives au RGPD pour les destinations](aam-gdpr-partners.md)
* [Guide de préparation au RGPD pour les clients d’Audience Manager](aam-gdpr-readiness.md)
* [Gouvernance des données](data-governance.md)
* [FAQ sur la rétention des données et la confidentialité](../../faq/faq-privacy.md)
