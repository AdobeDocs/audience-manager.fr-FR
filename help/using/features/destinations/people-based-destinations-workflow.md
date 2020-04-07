---
description: Destinations basées sur les personnes   plusieurs stratégies d’implémentation, selon la structure des données client. Cet article présente les étapes de mise en oeuvre que vous devez suivre pour les destinations basées sur les personnes, selon votre scénario.
seo-description: 'Destinations basées sur les personnes   plusieurs stratégies d’implémentation, selon la structure des données client. Cet article présente les étapes de mise en oeuvre que vous devez suivre pour les destinations basées sur les personnes, selon votre scénario.  '
seo-title: Guide de mise en oeuvre des destinations basées sur les personnes
solution: Audience Manager
title: Guide de mise en oeuvre
translation-type: tm+mt
source-git-commit: 8493705b0f200b5b43d937dfd452210403a52b33

---


# Guide de mise en oeuvre {#implementation-guidance}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans ce document n&#39;est un conseil juridique. Veuillez consulter votre propre conseiller juridique pour obtenir des conseils juridiques.

[!DNL People-Based Destinations]   plusieurs stratégies d’implémentation, selon la structure des données client. Cet article présente une vue d’ensemble des étapes de mise en oeuvre que vous devez suivre [!DNL People-Based Destinations], selon votre scénario.

## Aperçu {#overview}

La configuration de [!DNL People-Based Destinations] vous guide dans plusieurs sections de  Gestionnaire de  de et requiert différents paramètres et méthodes d&#39;intégration des données, selon le type de données client que vous avez déjà dans le Gestionnaire de de  et le type de ciblage deque vous souhaitez effectuer.

>[!IMPORTANT]
> Avant de procéder à la configuration [!DNL People-Based Destinations], assurez-vous de lire cet article attentivement et en détail. Après avoir lu ce guide, vous devez avoir une bonne compréhension du scénario que vous allez activer par le biais de [!DNL People-Based Destinations].

Vous devez clarifier six aspects de l’implémentation avant d’utiliser [!DNL People-Based Destinations]. Cet article vous aidera à comprendre la configuration actuelle, afin que vous puissiez suivre correctement les étapes de mise en oeuvre de votre scénario.

![implémentation pbd](assets/pbd-implementation.png)

## 1. Définition de votre cas d’utilisation {#defining-your-use-case}

Avant de commencer la mise en oeuvre [!DNL People-Based Destinations], vous devez définir clairement le cas d’utilisation pour lequel vous utiliserez cette fonctionnalité. Vous pouvez l’utiliser [!DNL People-Based Destinations] pour      de deux manières, en fonction des de de de :

**A)  ciblage  en fonction de votre** combiné d’utilisateurs en ligne et hors ligne. Dans ce scénario, vous souhaitez combiner les données  existantes  du Gestionnaire de de l’ de l’ avec les données de votre [!DNL CRM] système interne, et envoyer les segments de [!DNL People-Based Destinations]résultants vers. Voici un exemple qui illustre ce scénario :

Votre, une compagnie aérienne, a des niveaux de clients différents (Bronze, Argent et Or), et vous voulez fournir à chacun des niveaux des  personnalisés via des plateformes sociales. Vous utilisez  Gestionnaire  de pour analyser les de vos clients sur votre site Web. Toutefois, tous les clients n’utilisent pas l’application mobile de la compagnie aérienne et certains d’entre eux ne se sont pas connectés au site Web du . Les données de vos clients sont essentiellement limitées aux ID d’adhésion et aux adresses électroniques.

Pour les  sur les médias sociaux et les de personnes similaires, vous pouvez importer vos adresses [de courriel](people-based-destinations-prerequisites.md) hachées dans le Gestionnaire dede  et les combiner avec vos caractéristiques de en ligne existantes, afin de créer de nouveaux segments de dehachage. Ensuite, vous pouvez utiliser ces segments pour  votre   par le biais de [!DNL People-Based Destinations].

**B)  ciblage des  basé exclusivement sur votre** de  hors ligne. Dans ce scénario, votre [!DNL CRM] système contient vos adresses électroniques de client et d’autres attributs de client, mais les clients n’ont pas du tout interagi avec votre site Web. Vous n’avez donc aucun  de client  dans le Gestionnaire de de . Voici un exemple qui illustre ce scénario :

Votre, un fournisseur de services de télécommunication, conserve les données client telles que les adresses électroniques et les forfaits de télécommunications achetés en interne [!DNL CRM]. Vous souhaitez  clients existants dans les plateformes sociales pour  leur, leur faire mettre à niveau des packages en fonction de leurexistant. Pour ce faire, vous pouvez assimiler vos adresses électroniques de clients hachés dans  Gestionnaire de  de et créer des segments en fonction du de  de clients existants. Ensuite, vous pouvez envoyer ces segments à [!DNL People-Based Destinations] vos clients pour qu’ils  avec des   personnalisées.

## 2. Définir le type d&#39;adresses électroniques ciblées {#define-target-email}

La deuxième étape de la définition de votre stratégie d’implémentation consiste à déterminer le type d’adresse électronique du client que vous souhaitez .

**A)  ciblage  basé sur vos adresses** de messagerie authentifiées. Dans ce scénario, vos utilisateurs disposent de plusieurs comptes associés à plusieurs adresses électroniques et vous souhaitez les avec des  d’personnalisés, uniquement en fonction de l’adresse électronique qu’ils authentifient sur votre site Web, en temps réel.

**B)  ciblage des  en fonction de toutes les adresses** de courriel associées. Dans ce scénario, vos utilisateurs disposent de plusieurs comptes associés à plusieurs adresses électroniques et vous souhaitez les  à l’échelle de toutes les adresses électroniques associées, quelle que soit l’ d’ authentifiée.

## 3. Identifier le type d’ID de client (ID CRM) que vous possédez {#identify-customer-id}

Le ciblage   dans [!DNL People-Based Destinations] nécessite l’envoi de versions hachées [](people-based-destinations-prerequisites.md) SHA256 des adresses électroniques de vos clients. Selon la configuration de votre Gestionnaire de  de  existante, vous pouvez vous trouver dans l’un des deux scénarios suivants :

**A) Vos identifiants de client   Manager ([DPUUID](../../reference/ids-in-aam.md)) sont déjà des adresses** de messagerie en minuscules hachées. Dans ce scénario, vous pouvez utiliser ces identifiants existants pour  votre  d’ dans [!DNL People-Based Destinations].

**B) Vos ID de client   Manager ([DPUUID](../../reference/ids-in-aam.md)) ne sont pas des adresses** de courriel hachées en minuscules. Dans ce scénario, vos ID de client existants ne peuvent pas être envoyés à [!DNL People-Based Destinations]. Pour l’utiliser [!DNL People-Based Destinations], vous devez effectuer une synchronisation des identifiants entre vos identifiants de client existants et les versions en minuscules hachées des adresses électroniques de vos clients. Pour ce faire, vous devez synchroniser [les identifiants](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) par fichier ou utiliser des identifiants [](../declared-ids.md)déclarés.

## 4. Qualification de caractéristiques {#trait-qualification}

Pour précis de vos  de   de la  dans [!DNL People-Based Destinations], vos utilisateurs doivent être qualifiés pour des caractéristiques basées sur des règles ou des caractéristiques intégrées, selon le type de ciblage de que vous souhaitez effectuer.

**A) Qualifiez vos identifiants de client et de périphérique en temps réel pour les caractéristiques** basées sur des règles. Cette option s’applique au cas d’utilisation A à partir de [1. Définition De Votre Cas](people-based-destinations-workflow.md#defining-your-use-case)D’Utilisation. Si votre plan consiste à   en fonction de l’en ligne et hors ligne, alors vous êtes probablement déjà en train de qualifier votre pour des caractéristiques [basées sur des](../traits/trait-and-segment-qualification-reference.md)règles.

**B) Caractéristiques embarquées par rapport à vos ID de client via des fichiers** de données entrants. Cette option s’applique au cas d’utilisation B à partir de [1. Définition De Votre Cas](people-based-destinations-workflow.md#defining-your-use-case)D’Utilisation. Lorsque vous ciblez vos  de  sur la base d’un de  hors ligne uniquement, vous devez définir les identifiants de client pour les caractéristiques intégrées par le biais de fichiers [de données](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)entrants.

## 5. Créer ou étiqueter des sources de données et des adresses électroniques hachées intégrées {#create-label-data-sources}

Selon le type d’ID de client que vous avez dans  Gestionnaire de  de (voir [3). Identifiez le type d’ID de client (ID de gestion de la relation client) que vous possédez](people-based-destinations-workflow.md#identify-customer-id). Vous vous retrouverez dans l’un des scénarios suivants :

**A) Étiqueter une source** de données existante. Cette option s’applique au scénario où vos ID de client   Manager ([DPUUID](../../reference/ids-in-aam.md)) sont déjà des adresses de messagerie en minuscules hachées. Dans ce cas, il vous faut étiqueter la source de données dans laquelle vous stockez les ID comme source de [!DNL PII] données. Voir Paramètres [de la source de](../datasources-list-and-settings.md) données pour plus d’informations sur les paramètres de la source de données. Vous devez vous assurer que l’option Ne pas être lié à des informations d’identification personnelle n’est pas cochée.

**B) Créer une source** de données. Cette option s’applique au scénario où vos ID de client   Manager ([DPUUID](../../reference/ids-in-aam.md)) ne sont pas des adresses de messagerie hachées. Dans ce cas, vous devez créer une source de données multipériphériques et y placer les adresses électroniques hachées. Vous pouvez procéder de deux manières :

* Utilisez la synchronisation des identifiants basée sur des fichiers. Pour plus d’informations sur l’aspect des fichiers [de synchronisation des identifiants, reportez-vous à la section](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) Nom et contenu requis pour les fichiersde synchronisation des identifiants. Lorsque vous utilisez cette méthode, vous pouvez  toutes vos adresses électroniques hachées à partir de votre [!DNL CRM] base de données.
* Utilisez des ID [déclarés](../declared-ids.md) pour déclarer vos adresses électroniques hachées lors de la transmission d’ID de client authentifiés. Lors de l’utilisation de cette méthode,  Gestionnaire  de, en votre nom, ne que vos adresses électroniques hachées aux utilisateurs qui se sont authentifiés en ligne. Les adresses de courriel ciblées dans les  de personnes ne sont que celles des appels de d’ID déclarés. Les autres adresses électroniques associées à l’ID de client ne sont pas activées en temps réel.

## 6. Utiliser une règle de fusion  pour la segmentation {#use-profile-merge-rules}

Selon le cas d’utilisation (voir [1). Définition de votre cas](people-based-destinations-workflow.md#defining-your-use-case)d’utilisation), il existe deux manières d’utiliser [!DNL Profile Merge Rules] la segmentation.

**A) Utiliser les éléments existants[!DNL Profile Merge Rules]**. Cette option s’applique au premier cas d’utilisation ( ciblage  basé sur les de l’utilisateur en ligne et hors ligne combinés). Dans ce scénario, vous disposez d’un  client existant dans  Gestionnaire de de  et vous avez déjà défini au moins une règle de fusion de que vous avez utilisée dans la segmentation. Dans ce cas, vous n&#39;avez pas besoin de créer de nouveau[!DNL Profile Merge Rules].

**B) Créez une nouvelle règle[!DNL All Cross-Device Profiles]** de fusion. Cette option s’applique au second cas d’utilisation ( ciblage  des basé exclusivement sur les de l’utilisateur hors ligne ). Dans ce scénario, vous importez vos données client hors ligne de votre [!DNL CRM] dans  Gestionnaire de  de et vous souhaitez créer des segments à partir de ces données. Pour ce faire, [!DNL People-Based Destinations] introduit une nouvelle règle de fusion du quatrième, appelée **[!DNL All Cross-Device Profiles]**. Il s’agit de la règle à utiliser lors de la segmentation de données hors ligne uniquement.
