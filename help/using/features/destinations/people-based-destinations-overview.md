---
description: 'Utilisez des destinations basées sur les personnes pour envoyer des segments d’audience propriétaires à des environnements basés sur les personnes. Ces environnements sont des écosystèmes fermés appartenant à une entité qui contrôle le contenu affiché à l''intérieur de celle-ci. Il s’agit notamment des plateformes sociales telles que Facebook et d’autres plates-formes reposant sur des comptes clients pour personnaliser le contenu affiché. '
seo-description: 'Utilisez des destinations basées sur les personnes pour envoyer des segments d’audience propriétaires à des environnements basés sur les personnes. Ces environnements sont des écosystèmes fermés appartenant à une entité qui contrôle le contenu affiché à l''intérieur de celle-ci. Il s’agit notamment des plateformes sociales telles que Facebook et d’autres plates-formes reposant sur des comptes clients pour personnaliser le contenu affiché.  '
seo-title: Présentation et cas d’utilisation des destinations basées sur les personnes
solution: Audience Manager
title: Présentation et cas d’utilisation
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 0%

---


# Présentation et cas d’utilisation {#overview-use-cases}

Servez-vous [!DNL People-Based Destinations] d’envoyer des segments d’audience propriétaires aux environnements basés sur des personnes. Ces environnements sont des écosystèmes fermés appartenant à une entité qui contrôle le contenu affiché à l&#39;intérieur de celle-ci. Il s’agit notamment de plateformes sociales telles que [!DNL Facebook]et d’autres plates-formes reposant sur des comptes clients pour personnaliser le contenu affiché.

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonction. Rien dans ce document n&#39;est un conseil juridique. Veuillez consulter votre propre conseiller juridique pour obtenir des conseils juridiques.

## Aperçu {#overview}

[!DNL People-Based Destinations] vous permet d’appliquer la segmentation aux données en ligne et hors ligne afin de créer des segments d’audience basés sur des identifiants [](people-based-destinations-prerequisites.md#hashing-requirements)hachés, tels que des adresses électroniques ou des numéros de téléphone. Ensuite, vous pouvez envoyer ces segments vers des &quot;jardins muraux&quot; tels que [!DNL Facebook], où vous pouvez cible votre audience sur les plateformes sociales. [!DNL People-Based Destinations] peut vous aider :

* Cible des audiences hors ligne et en ligne sur des plateformes telles que [!DNL Facebook]les adresses électroniques hachées ;
* compléter les capacités de ciblage des dispositifs et des cookies existantes de l&#39;Audience Manager ;
* Éliminer les coûts associés aux solutions d&#39;intégration de données tierces ;
* Éliminer les coûts liés à l&#39;élaboration de workflows d&#39;intégration de données personnalisés ;
* audiences Cibles dans des environnements sans cookie ;
* Cible des audiences en dédupliquant les adresses électroniques hachées correspondaient aux ID de client.

Vous pouvez les utiliser [!DNL People-Based Destinations] pour segmenter et cible les clients à forte valeur ajoutée qui n’ont peut-être pas visité votre site Web ou arrêter de cibler ceux qui ont déjà effectué une conversion hors ligne. De plus, vous pouvez exploiter [!DNL Profile Merge Rules] les données propriétaires hors ligne pour associer vos données propriétaires en ligne, y compris les données client provenant d’autres solutions Adobe Experience Cloud, afin d’optimiser vos efforts publicitaires sur les réseaux sociaux.

![pbd-overview](assets/pbd-overview.png)

## Availability {#availability}

[!DNL People-Based Destinations] est une intégration d’Audiences Manager de premier ordre. Veuillez contacter votre représentant Adobe pour profiter de cette fonctionnalité haut de gamme.

## Pourquoi utiliser des destinations basées sur des personnes {#why-use}

**Proposez à vos clients des expériences intercanaux cohérentes en gérant l’ensemble de la segmentation de vos audiences depuis l’Audience Manager.**

Si vous n’activez pas vos segments d’audience dans des canaux basés sur des personnes par le biais de l’Audience Manager, vous obtenez des expériences disjointes entre ce que voient vos clients lors de leur visite sur votre site Web et ce qu’ils voient, par exemple, dans leurs [!DNL Facebook] flux. Un ciblage cohérent sur plusieurs canaux peut augmenter vos recettes publicitaires tout en optimisant vos dépenses publicitaires.

**Atteindre les audiences dans les canaux basés sur les personnes sans avoir besoin d&#39;une solution d&#39;intégration de données dédiée ou de workflows personnalisés pour envoyer des audiences.**

La méthode la plus &quot;traditionnelle&quot; de ciblage des audiences sur des canaux basés sur des personnes implique que vous deviez exporter vos données de client dans un format accepté par la plateforme sur laquelle vous souhaitez les publier, puis utiliser la méthode d&#39;intégration des données dédiées de la plate-forme pour apporter vos données de client à votre compte d&#39;annonceur. Il s&#39;agit d&#39;un travail manuel que vous devez effectuer pour chaque plate-forme sur laquelle vous souhaitez faire de la publicité. En outre, différentes plateformes peuvent avoir des exigences de format de données différentes, ce qui rend le processus encore plus fastidieux.

![pbd-overview](assets/pbd-diagram.png)

Grâce à [!DNL People-Based Destinations]l’Audience Manager, vous pouvez centraliser vos données client, créer des segments d’audience et les activer sur plusieurs canaux basés sur des personnes. Pour ce faire, vous pouvez utiliser l’interface utilisateur de l’Audience Manager, ce qui vous évite de devoir charger manuellement les données sur chaque plate-forme, ce qui vous permet de gagner du temps.

**Créez et activez des segments d’audience à partir de profils purement hors ligne.**

[!DNL People-Based Destinations] résoudre le problème qui, auparavant, ne permettait d’activer que les segments d’audience en fonction de l’activité du périphérique. Avec [!DNL People-Based Destinations], vous pouvez créer des segments à partir de données purement hors ligne à partir de vos propres données [!DNL CRM]et les activer dans des plateformes basées sur des personnes. De plus, vous pouvez corréler vos données hors ligne avec les données de périphérique que vous avez déjà en Audience Manager.

**Exploiter les contrôles de gouvernance et de confidentialité des données des Audiences Manager pour gérer en toute sécurité les données des clients.**

[!DNL People-Based Destinations] requiert que vous utilisiez uniquement des identifiants avec hachage irréversible. Cela réduit le risque associé au transfert manuel des données client vers chaque plateforme de destination.

Regardez la vidéo ci-dessous pour obtenir un aperçu du flux de données lors de l’utilisation [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## Cas d’utilisation {#use-cases}

Pour vous aider à mieux comprendre comment et quand utiliser [!DNL People-Based Destinations]cette fonctionnalité, voici deux exemples de cas d&#39;utilisation que les clients d&#39;Audience Manager peuvent résoudre en utilisant cette fonction.

### Use Case #1 {#use-case-1}

Un détaillant en ligne souhaite atteindre les clients existants par le biais de plateformes sociales et leur montrer des offres personnalisées en fonction de leurs commandes précédentes. Grâce à [!DNL People-Based Destinations]elle, le détaillant en ligne peut assimiler des adresses électroniques hachées de son site [!DNL CRM] à son Audience Manager, créer des segments à partir de ses propres données hors ligne et envoyer ces segments aux plateformes sociales sur lesquelles il souhaite faire de la publicité, en optimisant ainsi ses dépenses publicitaires.

### Use Case #2 {#use-case-2}

Une compagnie aérienne a différents niveaux de clients (Bronze, Argent et Or) et veut fournir à chacun des niveaux des offres personnalisées via des plateformes sociales. La société utilise l’Audience Manager pour analyser l’activité des clients sur le site Web. Cependant, tous les clients n’utilisent pas l’application mobile de la compagnie aérienne et certains d’entre eux ne se sont pas connectés au site Web de la société. Les seuls identifiants dont dispose la société à propos de ces clients sont les identifiants d’adhésion et les adresses électroniques.

Pour les cible sur les réseaux sociaux et les canaux similaires basés sur des personnes, ils peuvent embarquer les données client de leur [!DNL CRM] dans l’Audience Manager, en utilisant les adresses électroniques hachées comme identifiants.

Ensuite, ils peuvent combiner leurs données hors ligne avec leurs caractéristiques d&#39;activité en ligne existantes, afin de créer de nouveaux segments d&#39;audience qu&#39;ils peuvent cible à travers [!DNL People-Based Destinations].
