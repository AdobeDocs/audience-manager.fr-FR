---
description: Destinations basées sur les personnes offre plusieurs stratégies d’implémentation, en fonction de la structure des données client. Cet article présente une vue d’ensemble des étapes de mise en oeuvre que vous devez suivre pour les destinations basées sur les personnes, selon votre scénario.
seo-description: 'Destinations basées sur les personnes offre plusieurs stratégies d’implémentation, en fonction de la structure des données client. Cet article présente une vue d’ensemble des étapes de mise en oeuvre que vous devez suivre pour les destinations basées sur les personnes, selon votre scénario.  '
seo-title: Guide de mise en oeuvre des destinations basées sur les personnes
solution: Audience Manager
title: Guide de mise en oeuvre
feature: Destinations basées sur des personnes
exl-id: 224334d5-419c-4bb1-b76c-ce996a543b7a
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1381'
ht-degree: 2%

---

# Guide de mise en oeuvre {#implementation-guidance}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonction. Rien dans ce document n&#39;est un conseil juridique. Veuillez consulter votre propre conseiller juridique pour obtenir des conseils juridiques.

[!DNL People-Based Destinations] offre plusieurs stratégies d’implémentation, en fonction de la structure des données client. Cet article présente les étapes de mise en oeuvre que vous devez suivre pour [!DNL People-Based Destinations], en fonction de votre scénario.

## Présentation {#overview}

La configuration de [!DNL People-Based Destinations] vous guide dans plusieurs sections de l&#39;Audience Manager et requiert différents paramètres et méthodes d&#39;intégration des données, en fonction du type de données client que vous avez déjà en Audience Manager et du type d&#39;audience de ciblage que vous souhaitez effectuer.

>[!IMPORTANT]
> Avant de configurer [!DNL People-Based Destinations], veillez à lire cet article attentivement et en détail. Après avoir lu ce guide, vous devez avoir une bonne compréhension du scénario que vous allez activer via [!DNL People-Based Destinations].

Vous devez clarifier six aspects d&#39;implémentation avant d&#39;utiliser [!DNL People-Based Destinations]. Cet article vous aidera à comprendre quelle est votre configuration actuelle, afin que vous puissiez suivre correctement les étapes de mise en oeuvre de votre scénario.

![mise en oeuvre de pbd](assets/pbd-implementation.png)

## 1. Définition de votre cas d&#39;utilisation {#defining-your-use-case}

Avant de commencer à implémenter [!DNL People-Based Destinations], vous devez définir clairement le cas d&#39;utilisation pour lequel vous utiliserez cette fonctionnalité. Vous pouvez utiliser [!DNL People-Based Destinations] pour cible les audiences de deux manières, en fonction de l&#39;activité de l&#39;audience :

**A) Ciblage des Audiences en fonction de l’activité** combinée des utilisateurs en ligne et hors ligne. Dans ce scénario, vous souhaitez combiner les données d&#39;audience existantes provenant de l&#39;Audience Manager avec les données provenant de votre système interne [!DNL CRM] et envoyer les segments d&#39;audience résultants à [!DNL People-Based Destinations]. Voici un exemple qui illustre ce scénario :

Votre société, une compagnie aérienne, a différents niveaux de clients (Bronze, Argent et Or), et vous voulez fournir à chacun des niveaux des offres personnalisées via des plateformes sociales. Vous utilisez l’Audience Manager pour analyser l’activité des clients sur votre site Web. Cependant, tous les clients n’utilisent pas l’application mobile de la compagnie aérienne et certains d’entre eux ne se sont pas connectés au site Web de la société. Les données de vos clients sont principalement limitées aux ID d’adhésion et aux adresses électroniques.

Pour les cible sur les réseaux sociaux et les canaux similaires basés sur des personnes, vous pouvez importer vos [adresses électroniques hachées](people-based-destinations-prerequisites.md) en Audience Manager et les combiner avec vos caractéristiques d’activité en ligne existantes, afin de créer de nouveaux segments d’audience. Vous pouvez ensuite utiliser ces segments pour cible votre audience jusqu&#39;à [!DNL People-Based Destinations].

**B) Ciblage des Audiences basé exclusivement sur votre activité** d’utilisateur hors ligne. Dans ce scénario, votre système [!DNL CRM] contient vos adresses électroniques de client et d’autres attributs de client, mais les clients n’ont pas interagi avec votre site Web du tout, de sorte que vous n’avez aucune activité de client en Audience Manager. Voici un exemple qui illustre ce scénario :

Votre société, un fournisseur de services de télécommunication, conserve les données client comme les adresses électroniques et les plans de télécommunications achetés dans un [!DNL CRM] interne. Vous souhaitez cible les clients existants sur les plateformes sociales afin de les offre à mettre à niveau des packs en fonction de leurs abonnements existants. Pour ce faire, vous pouvez assimiler vos adresses électroniques de clients hachées à l’Audience Manager et créer des segments en fonction des abonnements de clients existants. Ensuite, vous pouvez envoyer ces segments à [!DNL People-Based Destinations] pour cible vos clients avec des offres personnalisées.

## 2. Définir le type d&#39;adresses électroniques ciblées {#define-target-email}

La deuxième étape de la définition de votre stratégie d’implémentation consiste à déterminer le type d’adresse électronique du client que vous souhaitez cible.

**A) Ciblage des Audiences en fonction de vos adresses** électroniques authentifiées. Dans ce scénario, vos utilisateurs disposent de plusieurs comptes associés à plusieurs adresses électroniques et vous souhaitez les cible d’offres personnalisées, basées uniquement sur l’adresse électronique qu’ils authentifient sur votre site Web, en temps réel.

**B) Ciblage des Audiences en fonction de toutes les adresses** électroniques associées. Dans ce scénario, vos utilisateurs disposent de plusieurs comptes associés à plusieurs adresses électroniques et vous souhaitez les cible sur toutes les adresses électroniques associées, quelle que soit l’activité authentifiée.

## 3. Identifiez le type d’ID de client (ID CRM) que vous possédez {#identify-customer-id}.

Les audiences de ciblage dans [!DNL People-Based Destinations] nécessitent que vous envoyiez des versions [hachées SHA256](people-based-destinations-prerequisites.md) de vos adresses électroniques de client. Selon la configuration de votre Audience Manager existante, vous pouvez vous trouver dans l’un des deux scénarios suivants :

**A) Vos identifiants de client d&#39;Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) sont déjà en minuscules adresses** électroniques hachées. Dans ce scénario, vous pouvez utiliser ces identifiants existants pour cible vos audiences dans [!DNL People-Based Destinations].

**B) Vos identifiants de client d&#39;Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) ne sont pas des adresses** de messagerie en minuscules hachées. Dans ce scénario, vos ID de client existants ne peuvent pas être envoyés à [!DNL People-Based Destinations]. Pour utiliser [!DNL People-Based Destinations], vous devez synchroniser les identifiants entre vos identifiants de client existants et les versions en minuscules hachées des adresses électroniques de vos clients. Pour ce faire, vous devez synchroniser [les identifiants basés sur des fichiers](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) ou utiliser [les identifiants déclarés](../declared-ids.md).

## 4. Qualification des caractéristiques {#trait-qualification}

Pour cible précisément votre audience dans [!DNL People-Based Destinations], vos utilisateurs doivent être qualifiés pour des caractéristiques basées sur des règles ou intégrées, selon le type de ciblage d’audience que vous souhaitez effectuer.

**A) Qualifiez vos ID de client et d’appareil en temps réel pour les caractéristiques** basées sur des règles. Cette option s’applique au cas d’utilisation A de [1. Définition de votre cas d’utilisation](people-based-destinations-workflow.md#defining-your-use-case). Si votre plan consiste à cible des audiences en fonction de l&#39;activité en ligne et hors ligne, vous êtes probablement déjà en train de qualifier votre audience pour [des caractéristiques basées sur des règles](../traits/trait-and-segment-qualification-reference.md).

**B) Caractéristiques intégrées par rapport à vos identifiants de client via des fichiers** de données entrants. Cette option s’applique au cas d’utilisation B de [1. Définition de votre cas d’utilisation](people-based-destinations-workflow.md#defining-your-use-case). Lorsque vous ciblez votre audience en fonction d’une activité purement hors ligne, vous devez qualifier les identifiants de client pour les caractéristiques intégrées par le biais de [fichiers de données entrants](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

## 5. Créer ou étiqueter des sources de données et des adresses électroniques hachées à bord {#create-label-data-sources}

Selon le type d’ID de client que vous avez en Audience Manager (voir [3. Identifiez le type d’ID de client (ID CRM) que vous possédez](people-based-destinations-workflow.md#identify-customer-id). Vous vous retrouverez dans l’un des scénarios suivants :

**A) Étiqueter une source** de données existante. Cette option s’applique au scénario où les identifiants de client de votre Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) sont déjà en minuscules, avec des adresses électroniques hachées. Dans ce cas, il vous faut étiqueter la source de données dans laquelle vous stockez les ID en tant que source de données [!DNL PII]. Voir [Paramètres de la source de données](../datasources-list-and-settings.md) pour plus d’informations sur les paramètres de la source de données. Vous devez vous assurer que l’option Ne pas être lié à des informations d’identification personnelle n’est pas cochée.

**B) Créer une source** de données. Cette option s’applique au scénario où les identifiants de client de votre Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) ne sont pas des adresses électroniques hachées. Dans ce cas, vous devez créer une source de données multipériphériques et embarquer vos adresses électroniques hachées à l’encontre de celle-ci. Vous pouvez le faire de deux manières :

* Utilisez la synchronisation d’identifiants basée sur le fichier. Consultez [les exigences en matière de contenu pour les fichiers de synchronisation d’identifiants](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) pour obtenir des informations sur ce à quoi les fichiers de synchronisation d’identifiants doivent ressembler. Lorsque vous utilisez cette méthode, vous pouvez cible toutes vos adresses électroniques hachées à partir de votre base de données [!DNL CRM].
* Utilisez [les identifiants déclarés](../declared-ids.md) pour déclarer vos adresses électroniques hachées lors de la transmission des identifiants de client authentifiés. Lors de l’utilisation de cette méthode, l’Audience Manager, en votre nom, ne cible que les adresses électroniques hachées des utilisateurs qui se sont authentifiés en ligne. Les adresses électroniques ciblées dans les canaux basés sur des personnes ne sont que celles des appels de événement d’ID déclarés. Les autres adresses électroniques associées à l’identifiant du client ne sont pas activées en temps réel.

## 6. Utilisez une règle de fusion de Profil pour la segmentation {#use-profile-merge-rules}

Selon votre cas d&#39;utilisation (voir [1). Définition de votre cas d’utilisation ](people-based-destinations-workflow.md#defining-your-use-case)) : il existe deux façons d’utiliser [!DNL Profile Merge Rules] pour la segmentation.

**A) Utiliser les[!DNL Profile Merge Rules]** ressources existantes. Cette option s’applique au premier cas d’utilisation (ciblage des audiences basé sur l’activité combinée des utilisateurs en ligne et hors ligne). Dans ce scénario, vous avez une activité client existante en Audience Manager et vous avez déjà défini au moins une règle de fusion de Profils que vous avez utilisée dans la segmentation. Dans ce cas, vous n’avez pas besoin de créer de nouveau [!DNL Profile Merge Rules].

**B) Créez une nouvelle règle [!DNL All Cross-Device Profiles]  de** fusion. Cette option s’applique au second cas d’utilisation (ciblage des audiences basé exclusivement sur l’activité des utilisateurs hors ligne). Dans ce scénario, vous amenez en Audience Manager vos données client hors ligne de votre [!DNL CRM] et souhaitez créer des segments à partir de ces données. Pour ce faire, [!DNL People-Based Destinations] introduit une nouvelle règle de fusion du quatrième Profil, appelée **[!DNL All Cross-Device Profiles]**. Il s’agit de la règle à utiliser lors de la segmentation de données purement hors ligne.
