---
description: Les destinations basées sur les personnes offrent plusieurs stratégies d’implémentation, selon la structure de vos données client. Cet article présente un aperçu des étapes d’implémentation que vous devez suivre pour les destinations basées sur les personnes, en fonction de votre scénario.
seo-description: People-Based Destinations offers multiple implementation strategies, depending on how your customer data is structured. This article provides an overview of the implementation steps that you need to follow for People-Based Destinations, depending on your scenario.
seo-title: People-Based Destinations Implementation Guidance
solution: Audience Manager
title: Guide de mise en œuvre
feature: People-based Destinations
exl-id: 224334d5-419c-4bb1-b76c-ce996a543b7a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1350'
ht-degree: 2%

---

# Guide de mise en œuvre {#implementation-guidance}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans le présent document n&#39;est un avis juridique. Veuillez consulter votre propre service juridique pour obtenir des conseils juridiques.

[!DNL People-Based Destinations] propose plusieurs stratégies d’implémentation, selon la structure de vos données client. Cet article présente un aperçu des étapes d’implémentation que vous devez suivre pour [!DNL People-Based Destinations], en fonction de votre scénario.

## Présentation {#overview}

La configuration d’[!DNL People-Based Destinations] vous fait parcourir plusieurs sections d’Audience Manager et nécessite différents paramètres et méthodes d’intégration des données, en fonction du type de données client que vous possédez déjà dans Audience Manager et du type de ciblage d’audience que vous souhaitez effectuer.

>[!IMPORTANT]
> Avant de configurer [!DNL People-Based Destinations], lisez attentivement et entièrement cet article. Après avoir lu ce guide, vous devriez avoir une compréhension claire du scénario que vous activerez via [!DNL People-Based Destinations].

Vous devez clarifier six aspects de mise en œuvre avant d’utiliser [!DNL People-Based Destinations]. Cet article vous aidera à comprendre quelle est votre configuration actuelle afin que vous puissiez suivre correctement les étapes d’implémentation de votre scénario.

![pbd-implementation](assets/pbd-implementation.png)

## &#x200B;1. Définition De Votre Cas D’Utilisation {#defining-your-use-case}

Avant de commencer l’implémentation de [!DNL People-Based Destinations], vous devez définir clairement le cas d’utilisation pour lequel vous utiliserez cette fonctionnalité. Vous pouvez utiliser [!DNL People-Based Destinations] pour cibler des audiences de deux manières, en fonction de l’activité de l’audience :

A **Ciblage des audiences en fonction de l’activité combinée des utilisateurs et utilisatrices en ligne et hors ligne**. Dans ce scénario, vous souhaitez combiner les données d’audience existantes d’Audience Manager avec les données de votre système de [!DNL CRM] interne, et envoyer les segments d’audience résultants à [!DNL People-Based Destinations]. Voici un exemple illustrant ce scénario :

Votre entreprise, une compagnie aérienne, a différents niveaux de clients (Bronze, Argent et Or) et vous souhaitez fournir à chacun des niveaux des offres personnalisées via des plateformes sociales. Vous utilisez Audience Manager pour analyser l’activité des clients sur votre site web. Cependant, tous les clients n&#39;utilisent pas l&#39;application mobile de la compagnie aérienne et certains d&#39;entre eux ne se sont pas connectés au site Web de la compagnie. Les données de vos clients se limitent principalement aux identifiants d’abonnement et aux adresses e-mail.

Pour les cibler sur les médias sociaux et les canaux similaires basés sur les personnes, vous pouvez importer vos adresses e-mail [ hachées](people-based-destinations-prerequisites.md) dans Audience Manager et les combiner avec vos caractéristiques d’activité en ligne existantes, afin de créer de nouveaux segments d’audience. Vous pouvez ensuite utiliser ces segments pour cibler votre audience par le biais de [!DNL People-Based Destinations].

**B) Le ciblage d’audience basé exclusivement sur votre activité utilisateur hors ligne**. Dans ce scénario, votre système [!DNL CRM] contient les adresses e-mail de vos clients et d’autres attributs du client, mais les clients n’ont pas du tout interagi avec votre site web, de sorte que vous n’avez aucune activité client dans Audience Manager. Voici un exemple illustrant ce scénario :

Votre entreprise, un fournisseur de services de télécommunication, conserve les données des clients telles que les adresses électroniques et les plans de télécommunication achetés dans un [!DNL CRM] interne. Vous souhaitez cibler les clients existants sur les plateformes sociales pour leur proposer des packages de mise à niveau en fonction de leurs abonnements existants. Pour ce faire, vous pouvez ingérer les adresses e-mail de vos clients hachées dans Audience Manager et créer des segments en fonction des abonnements des clients existants. Vous pouvez ensuite envoyer ces segments à [!DNL People-Based Destinations] pour cibler vos clients avec des offres personnalisées.

## &#x200B;2. Définir le type d’adresses e-mail ciblées {#define-target-email}

La deuxième étape de la définition de votre stratégie d’implémentation consiste à choisir le type d’adresses e-mail du client que vous souhaitez cibler.

A **Ciblage de l’audience en fonction de vos adresses e-mail authentifiées**. Dans ce scénario, vos utilisateurs disposent de plusieurs comptes associés à plusieurs adresses e-mail et vous souhaitez les cibler avec des offres personnalisées, basées uniquement sur l’adresse e-mail qu’ils authentifient sur votre site web, en temps réel.

**B) Le ciblage de l’audience en fonction de toutes les adresses e-mail associées**. Dans ce scénario, vos utilisateurs disposent de plusieurs comptes associés à plusieurs adresses e-mail et vous souhaitez les cibler sur toutes leurs adresses e-mail associées, quelle que soit l’activité authentifiée.

## &#x200B;3. Identifier le type d’ID de client (ID CRM) dont vous disposez {#identify-customer-id}

Pour cibler des audiences dans [!DNL People-Based Destinations], vous devez envoyer des versions hachées [SHA256 de vos adresses e-mail ](people-based-destinations-prerequisites.md) client. Selon la configuration d’Audience Manager que vous possédez déjà, il se peut que vous vous trouviez dans l’un des deux scénarios suivants :

**A) Vos ID de client Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) sont déjà des adresses e-mail hachées en minuscules**. Dans ce scénario, vous pouvez utiliser ces identifiants existants pour cibler vos audiences dans [!DNL People-Based Destinations].

**B) Vos ID de client Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) ne sont pas des adresses e-mail hachées en minuscules**. Dans ce scénario, vos ID de client existants ne peuvent pas être envoyés à [!DNL People-Based Destinations]. Pour utiliser [!DNL People-Based Destinations], vous devez effectuer une synchronisation des identifiants entre vos ID client existants et les versions en minuscules et hachées des adresses e-mail de vos clients. Pour ce faire, vous devez utiliser la [synchronisation des identifiants basée sur des fichiers](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) ou les [identifiants déclarés](../declared-ids.md).

## &#x200B;4. Qualification de la caractéristique {#trait-qualification}

Pour cibler précisément votre audience dans [!DNL People-Based Destinations], vos utilisateurs doivent se qualifier pour les caractéristiques basées sur des règles ou intégrées, selon le type de ciblage d’audience que vous souhaitez effectuer.

A **Qualifiez vos identifiants de client et d’appareil en temps réel pour les caractéristiques basées sur des règles**. Cette option s’applique au cas d’utilisation A de la version [1. Définition De Votre Cas D’Utilisation](people-based-destinations-workflow.md#defining-your-use-case). Si votre plan consiste à cibler des audiences en fonction de l’activité en ligne et hors ligne, vous êtes probablement déjà en train de qualifier votre audience pour des [caractéristiques basées sur des règles](../traits/trait-and-segment-qualification-reference.md).

**B) Intégrer des caractéristiques à vos ID client via des fichiers de données entrants**. Cette option s’applique au cas d’utilisation B de la version [1. Définition De Votre Cas D’Utilisation](people-based-destinations-workflow.md#defining-your-use-case). Lors du ciblage de votre audience en fonction d’une activité purement hors ligne, vous devez qualifier les ID de client pour les caractéristiques intégrées via [fichiers de données entrants](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

## &#x200B;5. Créer ou étiqueter des sources de données et des adresses e-mail hachées intégrées {#create-label-data-sources}

Selon le type d’ID de client que vous avez dans Audience Manager (voir [3. Identifiez le type d’ID de client (ID CRM) dont vous disposez](people-based-destinations-workflow.md#identify-customer-id) vous vous retrouverez dans l’un des scénarios suivants :

A **Étiqueter une source de données existante**. Cette option s’applique au scénario où vos identifiants de client Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) sont déjà en minuscules et des adresses e-mail hachées. Dans ce cas, il vous suffit d’étiqueter votre source de données dans laquelle vous stockez les identifiants en tant que source de données [!DNL PII]. Voir [Paramètres de Source de données](../datasources-list-and-settings.md) pour plus d’informations sur les paramètres de source de données. Assurez-vous que l’option Ne peut pas être lié à des informations d’identification personnelle n’est pas cochée.

**B) Créez une nouvelle source de données**. Cette option s’applique au scénario où vos ID de client Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) ne sont pas des adresses e-mail hachées. Dans ce cas, vous devez créer une nouvelle source de données inter-appareils et intégrer vos adresses e-mail hachées dans celle-ci. Vous pouvez le faire de deux façons :

* Utilisez la synchronisation des identifiants basée sur des fichiers. Consultez [les exigences en matière de contenu pour les fichiers de synchronisation d’identifiants](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) pour obtenir des informations sur ce à quoi les fichiers de synchronisation d’identifiants doivent ressembler. Lorsque vous utilisez cette méthode, vous pouvez cibler toutes vos adresses e-mail hachées à partir de votre base de données [!DNL CRM].
* Utilisez des [identifiants déclarés](../declared-ids.md) pour déclarer vos adresses e-mail hachées lors de la transmission des ID de client authentifiés. Lorsque vous utilisez cette méthode, Audience Manager, pour votre compte, cible uniquement les adresses e-mail hachées des utilisateurs qui se sont authentifiés en ligne. Les adresses e-mail ciblées dans les canaux basés sur les personnes ne sont que celles des appels d’événement d’ID déclarés. Les autres adresses électroniques associées à l’identifiant du client ne sont pas activées en temps réel.

## &#x200B;6. Utiliser une règle de fusion de profils pour la segmentation {#use-profile-merge-rules}

Selon votre cas d’utilisation (voir [1. Lors de la définition de votre cas d’utilisation](people-based-destinations-workflow.md#defining-your-use-case)), il existe deux manières d’utiliser [!DNL Profile Merge Rules] pour la segmentation.

A **Utiliser les[!DNL Profile Merge Rules]** existants. Cette option s’applique au premier cas d’utilisation (ciblage d’audience basé sur l’activité combinée des utilisateurs en ligne et hors ligne). Dans ce scénario, vous disposez déjà d’une activité client dans Audience Manager et vous avez déjà défini au moins une règle de fusion de profils que vous avez utilisée dans la segmentation. Dans ce cas, vous n’avez pas besoin de créer de [!DNL Profile Merge Rules].

**B) Créez une [!DNL All Cross-Device Profiles] règle de fusion**. Cette option s’applique au deuxième cas d’utilisation (ciblage d’audience basé exclusivement sur l’activité utilisateur hors ligne). Dans ce scénario, vous importez les données clients hors ligne de vos [!DNL CRM] dans Audience Manager et souhaitez créer des segments à partir de ces données. Pour ce faire, [!DNL People-Based Destinations] introduit une quatrième règle de fusion de profils, appelée **[!DNL All Cross-Device Profiles]**. Il s’agit de la règle que vous devez utiliser lors de la segmentation de données purement hors ligne.
