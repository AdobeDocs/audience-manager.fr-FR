---
description: Décrit l’intégration d’Audience Manager et la conformité aux bonnes pratiques généralement admises en ce qui concerne la confidentialité des consommateurs et les procédures d’opposition.
seo-description: Décrit l’intégration d’Audience Manager et la conformité aux bonnes pratiques généralement admises en ce qui concerne la confidentialité des consommateurs et les procédures d’opposition.
seo-title: Présentation de la confidentialité des données
solution: Audience Manager
title: Présentation de la confidentialité des données
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 78%

---


# Présentation de la confidentialité des données {#data-privacy}

## Présentation

The Data Privacy documentation describes [!DNL Audience Manager] integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.

[!DNL Audience Manager] reconnaît l’importance des relations entre les consommateurs et les marques en ligne avec lesquelles ils interagissent. Les deux parties bénéficient d’un échange transparent d’éléments de données pseudonymes :

* Les consommateurs reçoivent du contenu personnalisé, des offres de produits à prix réduit et des expériences utilisateur simplifiées.
* Les marques reçoivent des flux de revenus vitaux qui prennent en charge plusieurs modèles de commerce en ligne.

In our continuing support of this model, [!DNL Audience Manager] remains committed to providing you with the tools to help support your ability to provide  transparency and control to your consumers, while delivering personalized ads subject to the [Online Behavioral Advertising (OBA) Self-Regulatory Principles](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/).

## [!DNL GDPR] {#gdpr}

Le [règlement général sur la protection des données (RGPD)](https://eugdpr.org/) a introduit plusieurs nouveaux droits à la confidentialité des données pour les membres de l’Union européenne, y compris le **droit d’accès** et le **droit à l’oubli**. This means that any [!DNL EU] citizen whose personal data has been collected by your business can request to access or delete their data at any time. Le non-respect de ces requêtes par votre organisation peut être sanctionné par des amendes de plusieurs millions de dollars.

To comply with [!DNL GDPR], [!DNL Audience Manager] supports data access and delete [requests](data-privacy-requests.md).

## [!DNL CCPA] {#ccpa}

La [California Consumer Privacy Act (CCPA)](https://www.caprivacy.org/about), entrée en vigueur le 1er janvier 2020, accorde aux résidents de Californie de nouveaux droits sur leurs informations personnelles et impose des responsabilités en matière de protection des données à certaines entités qui exercent leurs activités en Californie.

[!DNL CCPA]La accorde de nouveaux droits à la confidentialité des données aux résidents de Californie, notamment le droit d’accéder à leurs données personnelles et de les supprimer, mais aussi de savoir si celles-ci sont vendues ou divulguées (et si oui, à qui). To comply with [!DNL CCPA], [!DNL Audience Manager] supports [!DNL CCPA] access and delete [requests](data-privacy-requests.md).

Pour plus d’informations, consultez le [Centre de traitement des données personnelles d’Adobe](https://www.adobe.com/fr/privacy/opt-out.html).

## Conformité aux réglementations {#compliance}

[!DNL Audience Manager] vous permet de respecter vos obligations en vertu de certaines réglementations de confidentialité, grâce à des outils de confidentialité comme [Adobe Experience Platform Privacy Service](https://docs.adobe.com/content/help/fr-FR/experience-platform/privacy/home.html) pour les requêtes d’accès aux données et de suppression des données.

Ce service fournit une [!DNL RESTful API] et une interface utilisateur pour vous aider à gérer les requêtes de données des consommateurs. [Privacy Service](https://docs.adobe.com/content/help/fr-FR/experience-platform/privacy/home.html) vous permet d’envoyer des requêtes d’accès aux données personnelles et de suppression de celles-ci, sur la base d’une requête individuelle de consommateur, ce qui contribue à automatiser cette partie de vos obligations de conformité.

Bien que [Privacy Service](https://docs.adobe.com/content/help/fr-FR/experience-platform/privacy/home.html) gère les requêtes d’accès aux données et de suppression des données, les [demandes d’exclusion](data-privacy-requests.md#opt-out-requests) sont actuellement prises en charge par l’[API DCS](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md). Pour plus d’informations, consultez [Requêtes de confidentialité des données](data-privacy-requests.md).

## Concepts associés {#related-concepts}

* [Requêtes de confidentialité des données](data-privacy-requests.md)
* [Gestion du consentement](data-privacy-consent.md)
* [Module d’Audience Manager pour le TCF de l’IAB](aam-iab-plugin.md)
* [Identifiants Audience Manager](data-privacy-ids.md)
* [Glossaire de la CCPA](aam-ccpa-glossary.md)
* [Glossaire du RGPD](aam-gdpr-glossary.md)
* [Considérations relatives au RGPD pour les destinations](aam-gdpr-partners.md)
* [Guide de préparation au RGPD pour les clients d’Audience Manager](aam-gdpr-readiness.md)
* [Gouvernance des données](data-governance.md)
* [FAQ sur la rétention des données et la confidentialité](../../faq/faq-privacy.md)