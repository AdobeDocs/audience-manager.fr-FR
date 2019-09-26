---
description: Les destinations basées sur les personnes proposent plusieurs stratégies d’implémentation, selon la structure des données client. Cet article présente les étapes de mise en oeuvre que vous devez suivre pour les destinations basées sur les personnes, selon votre scénario.
seo-description: 'Les destinations basées sur les personnes proposent plusieurs stratégies d’implémentation, selon la structure des données client. Cet article présente les étapes de mise en oeuvre que vous devez suivre pour les destinations basées sur les personnes, selon votre scénario.  '
seo-title: Guide de mise en oeuvre des destinations basées sur les personnes
solution: Audience Manager
title: Guide de mise en oeuvre
translation-type: tm+mt
source-git-commit: 6093def9c5853572c064a4e398d5e328bcb9d181

---


# Guide de mise en oeuvre {#implementation-guidance}

[!DNL People-Based Destinations] propose plusieurs stratégies d’implémentation, en fonction de la structure des données client. Cet article présente les étapes de mise en oeuvre que vous devez suivre [!DNL People-Based Destinations], selon votre scénario.

## Aperçu {#overview}

La configuration d’Audience Manager [!DNL People-Based Destinations] vous guide dans plusieurs sections d’Audience Manager et requiert différents paramètres et méthodes d’intégration des données, selon le type de données client que vous avez déjà dans Audience Manager et le type de ciblage d’audience que vous souhaitez effectuer.

>[!IMPORTANT]
> Avant de procéder à la configuration [!DNL People-Based Destinations], assurez-vous de lire cet article attentivement et en détail. Après avoir lu ce guide, vous devez avoir une bonne compréhension du scénario que vous allez activer par le biais de [!DNL People-Based Destinations].

Vous devez clarifier six aspects de l’implémentation avant d’utiliser [!DNL People-Based Destinations]. Cet article vous aidera à comprendre la configuration actuelle, afin que vous puissiez suivre correctement les étapes de mise en oeuvre de votre scénario.

![implémentation pbd](assets/pbd-implementation.png)

## 1. Définition de votre cas d’utilisation {#defining-your-use-case}

Avant de commencer la mise en oeuvre [!DNL People-Based Destinations], vous devez définir clairement le cas d’utilisation pour lequel vous utiliserez cette fonctionnalité. Vous pouvez utiliser [!DNL People-Based Destinations] pour cibler les audiences de deux manières, en fonction de l’activité de l’audience :

**A) Ciblage de l’audience en fonction de l’activité** combinée des utilisateurs en ligne et hors ligne. Dans ce scénario, vous souhaitez combiner les données d’audience existantes d’Audience Manager avec les données de votre [!DNL CRM] système interne et envoyer les segments d’audience résultants vers [!DNL People-Based Destinations]. Voici un exemple qui illustre ce scénario :

Votre entreprise, une compagnie aérienne, a différents niveaux de clients (Bronze, Argent et Or) et vous souhaitez fournir à chacun des niveaux des offres personnalisées via des plateformes sociales. Vous utilisez Audience Manager pour analyser l’activité des clients sur votre site Web. Cependant, tous les clients n’utilisent pas l’application mobile de la compagnie aérienne et certains d’entre eux ne se sont pas connectés au site Web de la compagnie. Les données de vos clients sont essentiellement limitées aux ID d’adhésion et aux adresses électroniques.

Pour les cibler sur les médias sociaux et les canaux basés sur des personnes similaires, vous pouvez importer vos adresses [électroniques](people-based-destinations-prerequisites.md) hachées dans Audience Manager et les combiner avec vos caractéristiques d’activité en ligne existantes, afin de créer de nouveaux segments d’audience. Vous pouvez ensuite utiliser ces segments pour cibler votre audience par le biais de [!DNL People-Based Destinations].

**B) Ciblage de l’audience basé exclusivement sur votre activité** d’utilisateur hors ligne. Dans ce scénario, votre [!DNL CRM] système contient les adresses électroniques de vos clients et d’autres attributs du client, mais les clients n’ont pas du tout interagi avec votre site Web. Vous n’avez donc aucune activité de client dans Audience Manager. Voici un exemple qui illustre ce scénario :

Votre entreprise, fournisseur de services de télécommunication, conserve les données client telles que les adresses électroniques et achète les forfaits de télécommunication en interne [!DNL CRM]. Vous souhaitez cibler les clients existants sur les plateformes sociales afin de leur proposer des packs de mise à niveau en fonction de leurs abonnements existants. Pour ce faire, vous pouvez assimiler les adresses électroniques de vos clients hachés dans Audience Manager et créer des segments en fonction des abonnements des clients existants. Ensuite, vous pouvez envoyer ces segments pour [!DNL People-Based Destinations] cibler vos clients avec des offres personnalisées.

## 2. Définir le type d'adresses électroniques ciblées {#define-target-email}

La deuxième étape de la définition de votre stratégie d’implémentation consiste à déterminer le type d’adresse électronique du client que vous souhaitez cibler.

**A) Ciblage de l’audience en fonction de vos adresses**&#x200B;électroniques authentifiées. Dans ce scénario, vos utilisateurs disposent de plusieurs comptes associés à plusieurs adresses électroniques et vous souhaitez les cibler avec des offres personnalisées, basées uniquement sur l’adresse électronique qu’ils authentifient sur votre site Web, en temps réel.

**B) Ciblage de l’audience en fonction de toutes les adresses**&#x200B;électroniques associées. Dans ce scénario, vos utilisateurs disposent de plusieurs comptes associés à plusieurs adresses électroniques et vous souhaitez les cibler sur l’ensemble de leurs adresses électroniques associées, quelle que soit l’activité authentifiée.

## 3. Identifier le type d’ID de client (ID CRM) que vous possédez {#identify-customer-id}

Le ciblage des audiences dans [!DNL People-Based Destinations] exige que vous envoyiez des versions hachées [](people-based-destinations-prerequisites.md) SHA256 de vos adresses électroniques client. Selon la configuration d’Audience Manager existante, vous pouvez vous trouver dans l’un des deux scénarios suivants :

**A) Vos ID de client Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) sont déjà des adresses** de messagerie en minuscules hachées. Dans ce scénario, vous pouvez utiliser ces identifiants existants pour cibler vos audiences dans [!DNL People-Based Destinations].

**B) Vos ID de client Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) ne sont pas des adresses**&#x200B;électroniques en minuscules hachées. Dans ce scénario, vos ID de client existants ne peuvent pas être envoyés à [!DNL People-Based Destinations]. Pour l’utiliser [!DNL People-Based Destinations], vous devez effectuer une synchronisation des identifiants entre vos ID de client existants et les versions en minuscules hachées des adresses électroniques de vos clients. Pour ce faire, vous devez synchroniser [les identifiants](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) fichier ou utiliser des identifiants [](../declared-ids.md)déclarés.

## 4. Qualification de caractéristiques {#trait-qualification}

Pour cibler précisément votre audience dans [!DNL People-Based Destinations], vos utilisateurs doivent être qualifiés pour des caractéristiques basées sur des règles ou intégrées, selon le type de ciblage d’audience que vous souhaitez effectuer.

**A) Qualifiez vos identifiants de client et de périphérique en temps réel pour les caractéristiques** basées sur des règles. Cette option s’applique au cas d’utilisation A à partir de [1. Définition De Votre Cas](people-based-destinations-workflow.md#defining-your-use-case)D’Utilisation. Si votre plan consiste à cibler les audiences en fonction des activités en ligne et hors ligne, vous qualifiez probablement déjà votre audience pour des caractéristiques [basées sur des](../traits/trait-qualification-reference.md)règles.

**B) Caractéristiques embarquées par rapport à vos ID de client via des fichiers** de données entrants. Cette option s’applique au cas d’utilisation B à partir de [1. Définition De Votre Cas](people-based-destinations-workflow.md#defining-your-use-case)D’Utilisation. Lorsque vous ciblez votre audience en fonction d’une activité purement hors ligne, vous devez qualifier les identifiants de client pour les caractéristiques intégrées au moyen de fichiers [de données](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)entrants.

## 5. Créer ou étiqueter des sources de données et des adresses électroniques hachées intégrées {#create-label-data-sources}

Selon le type d’ID de client que vous avez dans Audience Manager (voir [3). Identifiez le type d’ID de client (ID de gestion de la relation client) que vous possédez](people-based-destinations-workflow.md#identify-customer-id). Vous vous retrouverez dans l’un des scénarios suivants :

**A) Étiqueter une source** de données existante. Cette option s’applique au scénario où vos identifiants de client Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) sont déjà des adresses électroniques en minuscules hachées. Dans ce cas, il vous faut étiqueter la source de données dans laquelle vous stockez les ID comme source de [!DNL PII] données. Voir Paramètres [de la source de](../datasources-list-and-settings.md) données pour plus d’informations sur les paramètres de la source de données. Vous devez vous assurer que l’option Ne pas être lié aux informations d’identification personnelle n’est pas cochée.

**B) Créer une source** de données. Cette option s’applique au scénario où vos identifiants de client Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) ne sont pas des adresses électroniques hachées. Dans ce cas, vous devez créer une source de données multipériphériques et y placer les adresses électroniques hachées. Vous pouvez le faire de deux manières :

* Utilisez la synchronisation des identifiants basée sur des fichiers. Pour plus d’informations sur l’aspect des fichiers [de synchronisation des identifiants, reportez-vous à la section](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) Nom et configuration requise du contenu. Lorsque vous utilisez cette méthode, vous pouvez cibler toutes vos adresses électroniques hachées à partir de votre [!DNL CRM] base de données.
* Utilisez des ID [déclarés](../declared-ids.md) pour déclarer vos adresses électroniques hachées lors de la transmission d’ID de client authentifiés. Lors de l’utilisation de cette méthode, Audience Manager, en votre nom, cible uniquement les adresses électroniques hachées des utilisateurs qui se sont authentifiés en ligne. Les adresses électroniques ciblées dans les canaux basés sur les personnes ne sont que celles des appels d’événement d’ID déclarés. Les autres adresses électroniques associées à l’ID de client ne sont pas activées en temps réel.

## 6. Utiliser une règle de fusion de profil pour la segmentation {#use-profile-merge-rules}

Selon le cas d’utilisation (voir [1). Définition de votre cas](people-based-destinations-workflow.md#defining-your-use-case)d’utilisation), il existe deux manières d’utiliser [!DNL Profile Merge Rules] la segmentation.

**A) Utiliser les éléments existants[!DNL Profile Merge Rules]**. Cette option s’applique au premier cas d’utilisation (ciblage de l’audience basé sur l’activité combinée des utilisateurs en ligne et hors ligne). Dans ce scénario, vous avez une activité client existante dans Audience Manager et vous avez déjà défini au moins une règle de fusion de profil que vous avez utilisée dans la segmentation. Dans ce cas, vous n'avez pas besoin de créer de nouveau [!DNL Profile Merge Rules].

**B) Créez une nouvelle règle[!DNL All Cross-Device Profiles]** de fusion. Cette option s’applique au second cas d’utilisation (ciblage d’audience basé exclusivement sur l’activité de l’utilisateur hors ligne). Dans ce scénario, vous amenez vos données client hors ligne de votre [!DNL CRM] compte dans Audience Manager et souhaitez créer des segments à partir de ces données. Pour ce faire, [!DNL People-Based Destinations] introduit une nouvelle quatrième règle de fusion de profil, appelée **[!DNL All Cross-Device Profiles]**. Il s’agit de la règle à utiliser lors de la segmentation de données hors ligne uniquement.
