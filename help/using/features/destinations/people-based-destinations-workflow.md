---
description: Les destinations basées sur les personnes offrent plusieurs stratégies de mise en oeuvre, selon la structure de vos données client. Cet article fournit un aperçu des étapes de mise en oeuvre que vous devez suivre pour les destinations basées sur les personnes, selon votre scénario.
seo-description: 'Les destinations basées sur les personnes offrent plusieurs stratégies de mise en oeuvre, selon la structure de vos données client. Cet article fournit un aperçu des étapes de mise en oeuvre que vous devez suivre pour les destinations basées sur les personnes, selon votre scénario.  '
seo-title: Guide de mise en oeuvre des destinations basées sur les personnes
solution: Audience Manager
title: Guide de mise en oeuvre
feature: Destinations basées sur les personnes
exl-id: 224334d5-419c-4bb1-b76c-ce996a543b7a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1381'
ht-degree: 2%

---

# Guide de mise en oeuvre {#implementation-guidance}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans le présent article n&#39;est un avis juridique. Veuillez consulter votre propre service juridique pour obtenir des conseils juridiques.

[!DNL People-Based Destinations] propose plusieurs stratégies de mise en oeuvre, selon la structure de vos données client. Cet article présente les étapes de mise en oeuvre que vous devez suivre pour [!DNL People-Based Destinations], selon votre scénario.

## Présentation {#overview}

La configuration de [!DNL People-Based Destinations] vous guide dans plusieurs sections de l’Audience Manager et nécessite différents paramètres et méthodes d’intégration des données, selon le type de données client dont vous disposez déjà en Audience Manager et le type d’audience que vous souhaitez cibler.

>[!IMPORTANT]
> Avant de configurer [!DNL People-Based Destinations], veillez à lire cet article attentivement et en détail. Après avoir lu ce guide, vous devriez avoir une compréhension claire du scénario que vous activerez via [!DNL People-Based Destinations].

Vous devez clarifier six aspects de mise en oeuvre avant d’utiliser [!DNL People-Based Destinations]. Cet article vous aidera à comprendre la configuration actuelle, afin que vous puissiez suivre correctement les étapes de mise en oeuvre de votre scénario.

![implémentation pbd](assets/pbd-implementation.png)

## 1. Définition de votre cas d’utilisation {#defining-your-use-case}

Avant de commencer à implémenter [!DNL People-Based Destinations], vous devez définir clairement le cas d’utilisation pour lequel vous utiliserez cette fonctionnalité. Vous pouvez utiliser [!DNL People-Based Destinations] pour cibler les audiences de deux manières, en fonction de l’activité de l’audience :

**A) Ciblage des audiences en fonction de votre activité** utilisateur en ligne et hors ligne combinée. Dans ce scénario, vous souhaitez combiner les données d’audience existantes provenant de l’Audience Manager avec les données de votre système [!DNL CRM] interne et envoyer les segments d’audience obtenus à [!DNL People-Based Destinations]. Voici un exemple qui illustre ce scénario :

Votre société, une compagnie aérienne, a différents niveaux de clients (Bronze, Argent et Or) et vous souhaitez fournir à chacun des niveaux des offres personnalisées via des plateformes sociales. Vous utilisez l’Audience Manager pour analyser l’activité des clients sur votre site web. Cependant, tous les clients n’utilisent pas l’application mobile de la compagnie aérienne et certains d’entre eux ne se sont pas connectés au site web de la société. Les données de vos clients se limitent principalement aux ID d’adhésion et aux adresses électroniques.

Pour les cibler sur les médias sociaux et les canaux basés sur des personnes similaires, vous pouvez importer vos [adresses électroniques hachées](people-based-destinations-prerequisites.md) dans l’Audience Manager et les combiner avec vos caractéristiques d’activité en ligne existantes, afin de créer de nouveaux segments d’audience. Vous pouvez ensuite utiliser ces segments pour cibler votre audience par l’intermédiaire de [!DNL People-Based Destinations].

**B) Ciblage d’audience basé exclusivement sur votre activité** d’utilisateur hors ligne. Dans ce scénario, votre système [!DNL CRM] contient les adresses électroniques de vos clients et d’autres attributs du client, mais les clients n’ont pas du tout interagi avec votre site web. Vous n’avez donc aucune activité client en Audience Manager. Voici un exemple qui illustre ce scénario :

Votre entreprise, qui est un fournisseur de services de télécommunication, conserve les données client comme les adresses électroniques et achète des plans de télécommunications dans une [!DNL CRM] interne. Vous souhaitez cibler les clients existants dans les plateformes sociales afin de leur proposer des packages de mise à niveau en fonction de leurs abonnements existants. Pour ce faire, vous pouvez ingérer vos adresses électroniques client hachées dans Audience Manager et créer des segments en fonction des abonnements des clients existants. Vous pouvez ensuite envoyer ces segments à [!DNL People-Based Destinations] pour cibler vos clients avec des offres personnalisées.

## 2. Définition du type d’adresses électroniques ciblées {#define-target-email}

La deuxième étape de la définition de votre stratégie de mise en oeuvre consiste à décider du type d’adresses électroniques de clients que vous souhaitez cibler.

**A) Ciblage des audiences en fonction de vos adresses** électroniques authentifiées. Dans ce scénario, plusieurs comptes sont associés à plusieurs adresses électroniques et vous souhaitez les cibler avec des offres personnalisées, basées uniquement sur l’adresse électronique qu’ils authentifient sur votre site web, en temps réel.

**B) Ciblage de l’audience basé sur toutes les adresses** électroniques associées. Dans ce scénario, plusieurs comptes sont associés à plusieurs adresses électroniques et vous souhaitez les cibler sur toutes les adresses électroniques associées, indépendamment de l’activité authentifiée.

## 3. Identifiez le type d’ID de client (ID CRM) que vous possédez {#identify-customer-id}

Le ciblage des audiences dans [!DNL People-Based Destinations] nécessite l’envoi de versions [SHA256 hachées](people-based-destinations-prerequisites.md) des adresses électroniques de vos clients. Selon la configuration de votre Audience Manager existante, vous pouvez vous trouver dans l’un des deux scénarios suivants :

**A) Les ID de client de votre Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) sont déjà des adresses électroniques hachées en minuscules**. Dans ce scénario, vous pouvez utiliser ces identifiants existants pour cibler vos audiences dans [!DNL People-Based Destinations].

**B) Les ID de client d’Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) ne sont pas des adresses électroniques hachées en minuscules**. Dans ce scénario, vos ID de client existants ne peuvent pas être envoyés à [!DNL People-Based Destinations]. Pour utiliser [!DNL People-Based Destinations], vous devez effectuer une synchronisation des identifiants entre vos ID de client existants et les versions hachées en minuscules de vos adresses électroniques de client. Pour ce faire, procédez soit par [synchronisation des identifiants basée sur un fichier](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md), soit en utilisant [les identifiants déclarés](../declared-ids.md).

## 4. Qualification des caractéristiques {#trait-qualification}

Pour cibler précisément votre audience dans [!DNL People-Based Destinations], vos utilisateurs doivent être qualifiés pour des caractéristiques basées sur des règles ou intégrées, selon le type de ciblage d’audience que vous souhaitez réaliser.

**A) Qualifiez vos ID de client et identifiants d’appareil en temps réel pour les caractéristiques** basées sur des règles. Cette option s’applique au cas d’utilisation A de [1. Définition de votre cas d’utilisation](people-based-destinations-workflow.md#defining-your-use-case). Si votre projet consiste à cibler des audiences en fonction de l’activité en ligne et hors ligne, vous qualifiez probablement déjà votre audience de [caractéristiques basées sur des règles](../traits/trait-and-segment-qualification-reference.md).

**B) Caractéristiques intégrées par rapport à vos ID de client via des fichiers** de données entrants. Cette option s’applique au cas d’utilisation B de [1. Définition de votre cas d’utilisation](people-based-destinations-workflow.md#defining-your-use-case). Lorsque vous ciblez votre audience en fonction d’une activité purement hors ligne, vous devez qualifier les identifiants de client pour les caractéristiques intégrées par le biais de [fichiers de données entrants](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

## 5. Créer ou étiqueter des sources de données et des adresses électroniques hachées intégrées {#create-label-data-sources}

Selon le type d’ID de client que vous avez en Audience Manager (voir [3. Identifiez le type d’ID de client (ID CRM) que vous possédez ](people-based-destinations-workflow.md#identify-customer-id). Vous vous retrouverez dans l’un des scénarios suivants :

**A) Étiqueter une source** de données existante. Cette option s’applique au scénario où les ID de client de votre Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) sont déjà des adresses électroniques hachées en minuscules. Dans ce cas, vous devez étiqueter votre source de données dans laquelle vous stockez les ID en tant que source de données [!DNL PII]. Voir [Paramètres de source de données](../datasources-list-and-settings.md) pour plus d’informations sur les paramètres de source de données. Vous devez vous assurer que l’option Ne pas être lié aux informations d’identification personnelle n’est pas cochée.

**B) Créez une source** de données. Cette option s’applique au scénario où les ID de client de votre Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) ne sont pas des adresses électroniques hachées. Dans ce cas, vous devez créer une source de données multi-appareils et intégrer vos adresses électroniques hachées à cette source. Vous pouvez le faire de deux façons :

* Utilisez la synchronisation d’identifiants basée sur le fichier. Consultez [les exigences en matière de contenu pour les fichiers de synchronisation d’identifiants](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) pour obtenir des informations sur ce à quoi les fichiers de synchronisation d’identifiants doivent ressembler. Lorsque vous utilisez cette méthode, vous pouvez cibler toutes vos adresses électroniques hachées à partir de votre base de données [!DNL CRM].
* Utilisez [les ID déclarés](../declared-ids.md) pour déclarer vos adresses électroniques hachées lors de la transmission des ID de client authentifiés. Lors de l’utilisation de cette méthode, l’Audience Manager, en votre nom, cible uniquement les adresses électroniques hachées des utilisateurs qui se sont authentifiés en ligne. Les adresses électroniques ciblées dans les canaux basés sur les personnes ne sont que celles des appels d’événement d’identifiant déclaré. Les autres adresses électroniques associées à l’identifiant du client ne sont pas activées en temps réel.

## 6. Utilisation d’une stratégie de fusion de profils pour la segmentation {#use-profile-merge-rules}

Selon votre cas d’utilisation (voir [1. La définition de votre cas d’utilisation ](people-based-destinations-workflow.md#defining-your-use-case)), il existe deux façons d’utiliser [!DNL Profile Merge Rules] pour la segmentation.

**A) Utiliser la[!DNL Profile Merge Rules]** version existante. Cette option s’applique au premier cas d’utilisation (ciblage d’audience basé sur une activité d’utilisateur en ligne et hors ligne combinée). Dans ce scénario, vous avez une activité client existante en Audience Manager et vous avez déjà défini au moins une stratégie de fusion de profils que vous avez utilisée dans la segmentation. Dans ce cas, vous n’avez pas besoin de créer de [!DNL Profile Merge Rules].

**B) Créez une  [!DNL All Cross-Device Profiles] règle de fusion**. Cette option s’applique au second cas d’utilisation (ciblage d’audience basé exclusivement sur une activité d’utilisateur hors ligne). Dans ce scénario, vous amenez en Audience Manager vos données client hors ligne de votre [!DNL CRM] et souhaitez créer des segments à partir de ces données. Pour ce faire, [!DNL People-Based Destinations] introduit une nouvelle quatrième stratégie de fusion de profils, appelée **[!DNL All Cross-Device Profiles]**. Il s’agit de la règle que vous devez utiliser lors de la segmentation de données purement hors ligne.
