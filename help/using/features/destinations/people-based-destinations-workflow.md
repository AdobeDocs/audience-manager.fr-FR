---
description: Les destinations basées sur les personnes proposent plusieurs stratégies d'implémentation, selon la structure de vos données client. Cet article présente les étapes de mise en œuvre que vous devez suivre pour les destinations basées sur les personnes, selon votre scénario.
seo-description: 'Les destinations basées sur les personnes proposent plusieurs stratégies d''implémentation, selon la structure de vos données client. Cet article présente les étapes de mise en œuvre que vous devez suivre pour les destinations basées sur les personnes, selon votre scénario.  '
seo-title: Conseils pour la mise en œuvre des destinations basées sur les personnes
solution: Audience Manager
title: Guide de mise en œuvre
translation-type: tm+mt
source-git-commit: a3380b9019cfc22b020aacc313eafc409486b0c5

---


# Guide de mise en œuvre {#implementation-guidance}

[!DNL People-Based Destinations] propose plusieurs stratégies d'implémentation, selon la structure de vos données client. Cet article présente les étapes de mise en œuvre que vous devez [!DNL People-Based Destinations]suivre, selon votre scénario.

## Aperçu {#overview}

La configuration de [!DNL People-Based Destinations] vous parcourez plusieurs sections d'Audience Manager et requiert différents paramètres et méthodes d'intégration des données, selon le type de données client déjà présentes dans Audience Manager et le type de ciblage d'audience que vous souhaitez effectuer.

>[!IMPORTANT]
> Avant de procéder à la configuration [!DNL People-Based Destinations], veillez à lire cet article avec soin et précision. Après avoir lu ce guide, vous devez comprendre clairement le scénario que [!DNL People-Based Destinations]vous souhaitez activer.

Vous devez clarifier six aspects d'implémentation avant d'utiliser [!DNL People-Based Destinations]. Cet article vous aidera à comprendre la configuration actuelle, de sorte que vous puissiez suivre correctement les étapes de mise en œuvre de votre scénario.

![pbd-implementation](assets/pbd-implementation.png)

## 1. Définition de votre cas d'utilisation {#defining-your-use-case}

Avant de commencer la mise en œuvre [!DNL People-Based Destinations], vous devez définir clairement le cas d'utilisation auquel vous utiliserez cette fonctionnalité. Vous pouvez utiliser [!DNL People-Based Destinations] pour cibler les audiences de deux façons, en fonction de l'activité de l'audience :

**A) Ciblage d'audience basé sur une activité d'utilisateur en ligne et hors ligne combinée**. Dans ce scénario, vous souhaitez combiner les données d'audience existantes d'Audience Manager avec les données provenant de votre [!DNL CRM] système interne et envoyer les segments d'audience résultants à [!DNL People-Based Destinations]. Voici un exemple illustrant ce scénario :

Votre société, une compagnie aérienne, possède différents niveaux de clients (bronze, argent et or) et vous souhaitez fournir chacun des niveaux avec des offres personnalisées via des plateformes sociales. Utilisez Audience Manager pour analyser l'activité des clients sur votre site Web. Cependant, tous les clients n'utilisent pas l'application mobile de la compagnie aérienne, et certains d'entre eux n'ont jamais consulté le site Web de l'entreprise. Vos données client sont principalement limitées aux ID d'adhésion et aux adresses électroniques.

Pour les cibler sur des réseaux sociaux et des canaux tiers similaires, vous pouvez placer les [adresses électroniques hachées](people-based-destinations-prerequisites.md) dans Audience Manager et les associer aux caractéristiques d'activité en ligne existantes pour créer de nouveaux segments d'audience. Vous pouvez ensuite utiliser ces segments pour cibler votre public.[!DNL People-Based Destinations]

**B) Ciblage d'audience exclusivement basé sur l'activité des utilisateurs hors ligne**. Dans ce scénario, [!DNL CRM] votre système contient les adresses électroniques des clients et d'autres attributs du client, mais les clients n'ont pas interagi avec votre site Web, de sorte que vous n'avez aucune activité client dans Audience Manager. Voici un exemple illustrant ce scénario :

Votre entreprise, prestataire de services téléphoniques, conserve les données client comme les adresses électroniques et les plans de télécoms dans un interne [!DNL CRM]. Vous souhaitez cibler les clients existants dans les plateformes sociales pour leur proposer de mettre à niveau les packs en fonction de leurs abonnements existants. Pour ce faire, vous pouvez assimiler des adresses électroniques de client hachées dans Audience Manager et créer des segments basés sur les abonnements clients existants. Vous pouvez ensuite envoyer ces segments pour [!DNL People-Based Destinations] cibler vos clients avec des offres personnalisées.

## 2. Définition du type d'adresses électroniques ciblées {#define-target-email}

La deuxième étape de la définition de votre stratégie de mise en œuvre consiste à déterminer le type d'adresses électroniques de client à cibler.

**A) Ciblage d'audience basé sur des adresses électroniques authentifiées**. Dans ce scénario, vos utilisateurs disposent de plusieurs comptes associés à plusieurs adresses électroniques et vous souhaitez les cibler avec des offres personnalisées, en fonction de l'adresse électronique qu'ils authentifient sur votre site Web, en réel réel.

**B) Ciblage d'audience basé sur toutes les adresses électroniques associées**. Dans ce scénario, vos utilisateurs ont plusieurs comptes associés à plusieurs adresses électroniques et vous souhaitez les cibler sur toutes leurs adresses électroniques associées, quelle que soit l'activité authentifiée.

## 3. Identifier le type d'ID de client (identifiants de gestion de la relation client) que vous avez {#identify-customer-id}

Le ciblage des audiences dans nécessite [!DNL People-Based Destinations] que vous envoyiez [des versions hachées](people-based-destinations-prerequisites.md) SHA 256 de vos adresses de courriel client. Selon la configuration existante d'Audience Manager, vous pouvez vous trouver dans l'un des deux scénarios suivants :

**R) Les identifiants de client Audience Manager ([dpuuid](../../reference/ids-in-aam.md)) sont déjà en minuscules, avec des adresses électroniques hachées**. Dans [!DNL People-Based Destinations]ce scénario, vous pouvez utiliser ces ID existants pour cibler vos audiences.

**B) Les identifiants de client Audience Manager ([dpuuid](../../reference/ids-in-aam.md)) ne sont pas des adresses électroniques hachées en minuscules**. Dans ce scénario, les ID de client existants ne peuvent [!DNL People-Based Destinations]pas être envoyés. Pour ce [!DNL People-Based Destinations]faire, vous devez effectuer une synchronisation des identifiants entre vos ID de client existants et les versions en minuscules et hachées des adresses électroniques des clients. Vous effectuez cette opération soit par la [synchronisation](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) des identifiants basés sur un fichier, soit par l'utilisation [d'ID déclarés](../declared-ids.md).

## 4. Qualification des caractéristiques {#trait-qualification}

Pour cibler précisément votre public dans [!DNL People-Based Destinations], vos utilisateurs doivent remplir les critères des caractéristiques articulées autour des règles ou des règles, selon le type de ciblage d'audience que vous souhaitez effectuer.

**A) Qualifiez les ID de client et les ID de périphérique en temps réel pour les caractéristiques basées sur des règles**. Cette option s'applique pour utiliser A à partir [d '1. Définition de votre cas d'utilisation](people-based-destinations-workflow.md#defining-your-use-case). Si vous prévoyez de cibler des audiences en fonction d'activités en ligne et hors ligne, il est probable que vous qualifiiez déjà votre audience pour des caractéristiques [basées sur des règles](../traits/trait-qualification-reference.md).

**B) Caractéristiques au niveau du panorama par rapport aux ID de client via des fichiers de données entrants**. Cette option s'applique à la casse B à partir [d '1. Définition de votre cas d'utilisation](people-based-destinations-workflow.md#defining-your-use-case). Lorsque vous ciblez votre public en fonction d'une activité purement hors ligne, vous devez qualifier les identifiants de client pour les caractéristiques intégrées par le biais [de fichiers de données entrants](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

## 5. Création ou libellé des sources de données et des adresses électroniques hachées onboard {#create-label-data-sources}

Selon le type d'ID de client que vous avez dans Audience Manager (voir [3. Identifiez le type d'ID de client (identifiants de gestion de la relation client) Que vous avez](people-based-destinations-workflow.md#identify-customer-id), vous vous trouvez dans l'un des scénarios suivants :

**A) Etiquette d'une source de données existante**. Cette option s'applique au scénario où les identifiants client d'Audience Manager ([dpuuid](../../reference/ids-in-aam.md)) sont déjà en minuscules et des adresses électroniques hachées. Dans ce cas, ce que vous devez faire est d'étiqueter la source de données que vous stockez comme source [!DNL PII] de données. Pour [plus d'informations sur les paramètres de source de données, voir Paramètres](../datasources-list-and-settings.md) de source de données. Vous devez vous assurer que le lien Ne peut pas être lié à des options d'identification personnelle est désactivé.

**B) Créez une source de données**. Cette option s'applique au scénario où les identifiants client d'Audience Manager ([dpuuid](../../reference/ids-in-aam.md)) ne sont pas des adresses électroniques hachées. Dans ce cas, vous devez créer une source de données sur plusieurs périphériques et y placer les adresses électroniques hachées. Vous pouvez effectuer cette opération de deux manières :

* Utilisez la synchronisation des identifiants basée sur un fichier. Pour plus d'informations sur les fichiers de synchronisation d'ID, reportez-vous à [la section Nom et exigences de contenu pour les fichiers](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) de synchronisation des identifiants. Lorsque vous utilisez cette méthode, vous pouvez cibler toutes les adresses électroniques hachées à partir de votre [!DNL CRM] base de données.
* Utilisez [les ID déclarés](../declared-ids.md) pour déclarer des adresses électroniques hachées lors de la transmission d'identifiants de client authentifiés. Lors de l'utilisation de cette méthode, Audience Manager cible uniquement les adresses électroniques hachées des utilisateurs qui ont authentifié en ligne. Les adresses électroniques ciblées via Facebook ne sont que celles qui figurent dans les appels d'événement d'ID déclarés. Les autres adresses électroniques associées à l'ID de client ne sont pas activées en temps réel.

## 6. Utiliser une règle de fusion de profils pour la segmentation {#use-profile-merge-rules}

Selon votre cas d'utilisation (voir [1. En définissant votre cas d'utilisation](people-based-destinations-workflow.md#defining-your-use-case), vous pouvez utiliser deux méthodes [!DNL Profile Merge Rules] pour la segmentation.

**A) Utilisez le[!DNL Profile Merge Rules]** paramètre existant. Cette option s'applique au premier cas d'utilisation (ciblage d'audience basé sur une activité d'utilisateur en ligne et hors ligne combinée). Dans ce scénario, vous avez déjà une activité client dans Audience Manager et avez déjà défini au moins une règle de fusion de profils que vous avez utilisée dans la segmentation. Dans ce cas, vous n'avez pas besoin de créer de nouveau [!DNL Profile Merge Rules].

**B) Créer une nouvelle règle[!DNL All Cross-Device Profiles]de fusion**. Cette option s'applique au second cas d'utilisation (ciblage d'audience exclusivement basé sur l'activité des utilisateurs hors ligne). Dans ce scénario, vous importez des données client hors ligne dans Audience [!DNL CRM] Manager et vous souhaitez créer des segments à partir de ces données. Pour ce faire [!DNL People-Based Destinations] , introduit une nouvelle règle de fusion de profil appelée **[!DNL All Cross-Device Profiles]**. Il s'agit de la règle à utiliser lors de la segmentation des données purement hors ligne.
