---
description: Destinations basées sur les personnes offre plusieurs stratégies d’implémentation, en fonction de la structure des données client. Cet article présente une vue d’ensemble des étapes de mise en oeuvre que vous devez suivre pour les destinations basées sur les personnes, selon votre scénario.
seo-description: 'Destinations basées sur les personnes offre plusieurs stratégies d’implémentation, en fonction de la structure des données client. Cet article présente une vue d’ensemble des étapes de mise en oeuvre que vous devez suivre pour les destinations basées sur les personnes, selon votre scénario.  '
seo-title: Guide de mise en oeuvre des destinations basées sur les personnes
solution: Audience Manager
title: Guide de mise en oeuvre
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1379'
ht-degree: 0%

---


# Guide de mise en oeuvre {#implementation-guidance}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonction. Rien dans ce document n&#39;est un conseil juridique. Veuillez consulter votre propre conseiller juridique pour obtenir des conseils juridiques.

[!DNL People-Based Destinations] offre plusieurs stratégies d’implémentation, en fonction de la structure des données client. Cet article présente une vue d’ensemble des étapes de mise en oeuvre que vous devez suivre [!DNL People-Based Destinations]en fonction de votre scénario.

## Aperçu {#overview}

La configuration de [!DNL People-Based Destinations] vous guide dans plusieurs sections de l&#39;Audience Manager et requiert différents paramètres et méthodes d&#39;intégration des données, en fonction du type de données client que vous avez déjà en Audience Manager et du type d&#39;audience de ciblage que vous souhaitez effectuer.

>[!IMPORTANT]
> Avant de procéder à la configuration [!DNL People-Based Destinations], veillez à lire cet article attentivement et complètement. Après avoir lu ce guide, vous devez avoir une bonne compréhension du scénario que vous allez activer par le biais de [!DNL People-Based Destinations].

Vous devez clarifier six aspects d’implémentation avant de les utiliser [!DNL People-Based Destinations]. Cet article vous aidera à comprendre quelle est votre configuration actuelle, afin que vous puissiez suivre correctement les étapes de mise en oeuvre de votre scénario.

![mise en oeuvre de pbd](assets/pbd-implementation.png)

## 1. Définition de votre cas d’utilisation {#defining-your-use-case}

Avant de commencer la mise en oeuvre [!DNL People-Based Destinations], vous devez définir clairement le cas d’utilisation pour lequel vous utiliserez cette fonctionnalité. Vous pouvez utiliser [!DNL People-Based Destinations] les audiences de cible de deux manières, en fonction de l’activité de l’audience :

**A) Ciblage des Audiences en fonction de l’activité** combinée des utilisateurs en ligne et hors ligne. Dans ce scénario, vous souhaitez combiner les données d&#39;audience existantes provenant de l&#39;Audience Manager avec celles provenant de votre [!DNL CRM] système interne et envoyer les segments d&#39;audience résultants vers [!DNL People-Based Destinations]. Voici un exemple qui illustre ce scénario :

Votre société, une compagnie aérienne, a différents niveaux de clients (Bronze, Argent et Or), et vous voulez fournir à chacun des niveaux des offres personnalisées via des plateformes sociales. Vous utilisez l’Audience Manager pour analyser l’activité des clients sur votre site Web. Cependant, tous les clients n’utilisent pas l’application mobile de la compagnie aérienne et certains d’entre eux ne se sont pas connectés au site Web de la société. Les données de vos clients sont principalement limitées aux ID d’adhésion et aux adresses électroniques.

Pour les cible sur les réseaux sociaux et les canaux similaires basés sur des personnes, vous pouvez importer vos adresses [électroniques](people-based-destinations-prerequisites.md) hachées en Audience Manager et les combiner avec vos caractéristiques d’activité en ligne existantes, afin de créer de nouveaux segments d’audience. Vous pouvez ensuite utiliser ces segments pour cible votre audience jusqu’à [!DNL People-Based Destinations].

**B) Ciblage des Audiences basé exclusivement sur votre activité** d’utilisateur hors ligne. Dans ce scénario, votre [!DNL CRM] système contient les adresses électroniques de vos clients et d’autres attributs du client, mais les clients n’ont pas interagi avec votre site Web, de sorte que vous n’avez aucune activité de client en Audience Manager. Voici un exemple qui illustre ce scénario :

Votre société, un fournisseur de services de télécommunication, conserve les données client comme les adresses électroniques et les plans de télécommunications achetés en interne [!DNL CRM]. Vous souhaitez cible les clients existants sur les plateformes sociales afin de les offre à mettre à niveau des packs en fonction de leurs abonnements existants. Pour ce faire, vous pouvez assimiler vos adresses électroniques de clients hachées à l’Audience Manager et créer des segments en fonction des abonnements de clients existants. Ensuite, vous pouvez envoyer ces segments à [!DNL People-Based Destinations] la cible de vos clients avec des offres personnalisées.

## 2. Définir le type d&#39;adresses électroniques ciblées {#define-target-email}

La deuxième étape de la définition de votre stratégie d’implémentation consiste à déterminer le type d’adresse électronique du client que vous souhaitez cible.

**A) Ciblage des Audiences en fonction de vos adresses**&#x200B;électroniques authentifiées. Dans ce scénario, vos utilisateurs disposent de plusieurs comptes associés à plusieurs adresses électroniques et vous souhaitez les cible d’offres personnalisées, basées uniquement sur l’adresse électronique qu’ils authentifient sur votre site Web, en temps réel.

**B) Ciblage des Audiences en fonction de toutes les adresses**&#x200B;électroniques associées. Dans ce scénario, vos utilisateurs disposent de plusieurs comptes associés à plusieurs adresses électroniques et vous souhaitez les cible sur toutes les adresses électroniques associées, quelle que soit l’activité authentifiée.

## 3. Identifiez le type d’ID de client (ID CRM) que vous possédez. {#identify-customer-id}

Les audiences de ciblage dans [!DNL People-Based Destinations] exigent que vous envoyiez des versions hachées [](people-based-destinations-prerequisites.md) SHA256 de vos adresses électroniques client. Selon la configuration de votre Audience Manager existante, vous pouvez vous trouver dans l’un des deux scénarios suivants :

**A) Vos identifiants de client d&#39;Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) sont déjà en minuscules adresses**&#x200B;électroniques hachées. Dans ce scénario, vous pouvez utiliser ces identifiants existants pour cible de vos audiences dans [!DNL People-Based Destinations].

**B) Vos identifiants de client d&#39;Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) ne sont pas des adresses** de messagerie en minuscules hachées. Dans ce scénario, vos identifiants de client existants ne peuvent pas être envoyés à [!DNL People-Based Destinations]. Pour l’utiliser [!DNL People-Based Destinations], vous devez effectuer une synchronisation des identifiants entre vos identifiants de client existants et les versions en minuscules hachées des adresses électroniques de vos clients. Pour ce faire, vous devez effectuer une synchronisation [des identifiants basée sur](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) des fichiers ou utiliser des identifiants [](../declared-ids.md)déclarés.

## 4. Qualification des caractéristiques {#trait-qualification}

Pour cible précisément votre audience dans [!DNL People-Based Destinations], vos utilisateurs doivent être inclus dans les caractéristiques basées sur des règles ou intégrées, selon le type de ciblage d’audience que vous souhaitez effectuer.

**A) Qualifiez vos ID de client et d’appareil en temps réel pour les caractéristiques** basées sur des règles. Cette option s’applique au cas d’utilisation A de [1. Définition De Votre Cas](people-based-destinations-workflow.md#defining-your-use-case)D’Utilisation. Si votre plan consiste à cible des audiences en fonction de l&#39;activité en ligne et hors ligne, vous êtes probablement déjà en train de qualifier votre audience pour des caractéristiques [basées sur des](../traits/trait-and-segment-qualification-reference.md)règles.

**B) Caractéristiques intégrées par rapport à vos identifiants de client via des fichiers** de données entrants. Cette option s’applique au cas d’utilisation B à partir de [1. Définition De Votre Cas](people-based-destinations-workflow.md#defining-your-use-case)D’Utilisation. Lorsque vous ciblez votre audience en fonction d’une activité purement hors ligne, vous devez définir les identifiants de client pour les caractéristiques intégrées par le biais de fichiers [de données](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)entrants.

## 5. Créez ou étiquetez les sources de données et les adresses électroniques hachées intégrées. {#create-label-data-sources}

Selon le type d’ID de client que vous avez en Audience Manager (voir [3). Identifiez le type d’ID de client (ID de gestion de la relation client) que vous possédez](people-based-destinations-workflow.md#identify-customer-id). Vous vous retrouverez dans l’un des scénarios suivants :

**A) Étiqueter une source** de données existante. Cette option s’applique au scénario où vos identifiants de client d’Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) sont déjà en minuscules, avec des adresses électroniques hachées. Dans ce cas, il vous faut étiqueter la source de données dans laquelle vous stockez les ID en tant que source de [!DNL PII] données. Voir Paramètres [de la source de](../datasources-list-and-settings.md) données pour en savoir plus sur les paramètres de la source de données. Vous devez vous assurer que l’option Ne pas être lié à des informations d’identification personnelle n’est pas cochée.

**B) Créer une source** de données. Cette option s’applique au scénario où vos identifiants de client d’Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) ne sont pas hachés. Dans ce cas, vous devez créer une source de données multipériphériques et embarquer vos adresses électroniques hachées à l’encontre de celle-ci. Vous pouvez le faire de deux manières :

* Utilisez la synchronisation des identifiants basée sur des fichiers. Voir Exigences en matière de [nom et de contenu pour les fichiers](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) de synchronisation des identifiants pour en savoir plus sur les fichiers de synchronisation des identifiants. Lorsque vous utilisez cette méthode, vous pouvez cible toutes vos adresses électroniques hachées à partir de votre [!DNL CRM] base de données.
* Utilisez des ID [](../declared-ids.md) déclarés pour déclarer vos adresses électroniques hachées lors de la transmission d’identifiants de client authentifiés. Lors de l’utilisation de cette méthode, l’Audience Manager, en votre nom, ne cible que les adresses électroniques hachées des utilisateurs qui se sont authentifiés en ligne. Les adresses électroniques ciblées dans les canaux basés sur des personnes ne sont que celles des appels de événement d’ID déclarés. Les autres adresses électroniques associées à l’ID de client ne sont pas activées en temps réel.

## 6. Utilisation d’une règle de fusion de Profils pour la segmentation {#use-profile-merge-rules}

Selon votre cas d’utilisation (voir [1). Définition de votre cas](people-based-destinations-workflow.md#defining-your-use-case)d’utilisation), il existe deux façons d’utiliser [!DNL Profile Merge Rules] la segmentation.

**A) Utiliser les[!DNL Profile Merge Rules]**ressources existantes. Cette option s’applique au premier cas d’utilisation (ciblage des audiences basé sur l’activité combinée des utilisateurs en ligne et hors ligne). Dans ce scénario, vous avez une activité client existante en Audience Manager et vous avez déjà défini au moins une règle de fusion de Profils que vous avez utilisée dans la segmentation. Dans ce cas, vous n’avez pas besoin de créer de nouveau[!DNL Profile Merge Rules].

**B) Créer une nouvelle règle[!DNL All Cross-Device Profiles]** de fusion. Cette option s’applique au second cas d’utilisation (ciblage des audiences basé exclusivement sur l’activité des utilisateurs hors ligne). Dans ce scénario, vous amenez les données client hors ligne de votre [!DNL CRM] site dans l’Audience Manager et souhaitez créer des segments à partir de ces données. Pour ce faire, [!DNL People-Based Destinations] introduit une nouvelle règle de fusion du quatrième Profil, appelée **[!DNL All Cross-Device Profiles]**. Il s’agit de la règle à utiliser lors de la segmentation de données purement hors ligne.
