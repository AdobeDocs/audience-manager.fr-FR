---
description: Utilisez des destinations basées sur des personnes pour envoyer des segments d’audience propriétaires à des environnements basés sur des personnes. Ces environnements sont des écosystèmes fermés appartenant à une entité qui contrôle le contenu affiché à l’intérieur. Il s’agit notamment de plateformes sociales telles que Facebook, ainsi que d’autres plateformes reposant sur des comptes clients afin de personnaliser le contenu affiché.
seo-description: Use people-based destinations to send first-party audience segments to people-based environments. These environments are closed ecosystems belonging to one entity that controls the content that is being displayed within it. They include social platforms such as Facebook, and other platforms that rely on customer accounts to personalize the displayed content.
seo-title: People-Based Destinations Overview and Use Cases
solution: Audience Manager
title: Présentation et cas d’utilisation
feature: People-based Destinations
exl-id: 2edbda3b-e2a3-4a92-965b-206a21764cc8
source-git-commit: ab3361a0a54a7200d2f0c03a82ae6ef61a755be9
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 0%

---

# Présentation et cas d’utilisation {#overview-use-cases}

Utilisez [!DNL People-Based Destinations] pour envoyer des segments d’audience propriétaires à des environnements basés sur des personnes. Ces environnements sont des écosystèmes fermés appartenant à une entité qui contrôle le contenu affiché à l’intérieur. Elles comprennent des plateformes sociales telles que [!DNL Facebook] et d’autres plateformes qui reposent sur des comptes clients pour personnaliser le contenu affiché.

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans le présent article n&#39;est un avis juridique. Veuillez consulter votre propre service juridique pour obtenir des conseils juridiques.

## Présentation {#overview}

[!DNL People-Based Destinations] vous permet d’appliquer une segmentation sur des données en ligne et hors ligne pour créer des segments d’audience basés sur des [ identifiants hachés](people-based-destinations-prerequisites.md#hashing-requirements), tels que des adresses électroniques. Ensuite, vous pouvez envoyer ces segments aux &quot;jardins muraux&quot; tels que [!DNL Facebook], où vous pouvez cibler votre audience sur les plateformes sociales. [!DNL People-Based Destinations] peut vous aider :

* Ciblez les audiences hors ligne et en ligne sur des plateformes telles que [!DNL Facebook], en fonction d’adresses électroniques hachées ;
* compléter les fonctionnalités de ciblage de périphériques et de cookies existantes de l’Audience Manager ;
* Éliminer les coûts associés aux solutions d’intégration de données tierces ;
* Éliminez les coûts liés au développement de workflows d’intégration de données personnalisés ;
* Cibler des audiences dans des environnements sans cookie ;
* Ciblez les audiences en dédupliquant les adresses électroniques hachées associées aux ID de client.

Vous pouvez utiliser [!DNL People-Based Destinations] pour segmenter et cibler les clients à forte valeur ajoutée qui ne se sont pas rendus sur votre site web, ou arrêter de cibler ceux qui ont déjà effectué une conversion hors ligne. De plus, vous pouvez exploiter [!DNL Profile Merge Rules] pour combiner vos données propriétaires hors ligne avec vos données propriétaires en ligne, y compris les données client provenant d’autres solutions Adobe Experience Cloud, afin d’optimiser vos efforts publicitaires sur les médias sociaux.

![pbd-overview](assets/pbd-overview.png)

## Disponibilité {#availability}

[!DNL People-Based Destinations] est une intégration d’Audience Manager premium. Veuillez contacter votre représentant Adobe pour profiter de cette fonctionnalité premium.

## Pourquoi utiliser [!UICONTROL People-Based Destinations] {#why-use}

**Offrez à vos clients des expériences cross-canal cohérentes en gérant l’ensemble de la segmentation de votre audience depuis l’Audience Manager.**

Si vous n’activez pas vos segments d’audience dans des canaux basés sur les personnes par le biais de l’Audience Manager, des expériences disjointes apparaissent entre ce que voient vos clients lorsqu’ils visitent votre site web et ce qu’ils voient, par exemple, dans leurs flux [!DNL Facebook]. Le ciblage cohérent sur l’ensemble des canaux peut augmenter vos recettes publicitaires tout en optimisant vos dépenses publicitaires.

**Atteindre des audiences dans des canaux basés sur des personnes sans avoir besoin d’une solution d’intégration de données dédiée ou de workflows personnalisés pour envoyer des audiences.**

La méthode la plus &quot;traditionnelle&quot; de ciblage des audiences sur des canaux basés sur des personnes implique que vous deviez exporter vos données client dans un format accepté par la plateforme sur laquelle vous souhaitez faire de la publicité, puis utiliser la méthode d’intégration de données dédiée de la plateforme pour importer vos données client dans votre compte publicitaire. Il s’agit d’un travail manuel que vous devez effectuer pour chaque plateforme sur laquelle vous souhaitez faire de la publicité. En outre, différentes plateformes peuvent avoir des exigences de format de données différentes, ce qui rend le processus encore plus fastidieux.

![pbd-overview](assets/pbd-diagram.png)

Grâce à [!DNL People-Based Destinations], Audience Manager vous permet de centraliser vos données client, de créer des segments d’audience et de les activer sur plusieurs canaux basés sur les personnes. Vous pouvez effectuer cette opération depuis l’interface utilisateur d’Audience Manager, en évitant de devoir charger manuellement les données sur chaque plateforme, ce qui vous permet de gagner du temps lors du processus.

**Créez et activez des segments d’audience à partir de profils purement hors ligne.**

[!DNL People-Based Destinations] résout le problème qui, auparavant, permettait d’activer uniquement les segments d’audience en fonction de l’activité de l’appareil. Avec [!DNL People-Based Destinations], vous pouvez créer des segments à partir de données hors ligne provenant uniquement de vos propres [!DNL CRM] et les activer dans des plateformes basées sur des personnes. En outre, vous pouvez mettre en relation vos données hors ligne avec les données de périphérique que vous avez déjà en Audience Manager.

**Tirez parti des contrôles de gouvernance et de confidentialité des données de l&#39;Audience Manager pour gérer en toute sécurité les données des clients.**

[!DNL People-Based Destinations] nécessite que vous utilisiez uniquement des identifiants hachés de manière irréversible. Cela permet de réduire les risques associés au chargement manuel de données client dans chaque plateforme de destination.

Regardez la vidéo ci-dessous pour obtenir un aperçu du flux de données lors de l’utilisation de [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## Cas d’utilisation {#use-cases}

Pour vous aider à mieux comprendre comment et quand vous devez utiliser [!DNL People-Based Destinations], voici deux exemples de cas d’utilisation que les clients d’Audience Manager peuvent résoudre à l’aide de cette fonctionnalité.

### Cas d’utilisation #1 {#use-case-1}

Un détaillant en ligne souhaite atteindre des clients existants par le biais de plateformes sociales et leur présenter des offres personnalisées basées sur leurs commandes précédentes. Avec [!DNL People-Based Destinations], le détaillant en ligne peut ingérer des adresses électroniques hachées de son propre [!DNL CRM] pour l’Audience Manager, créer des segments à partir de ses propres données hors ligne et envoyer ces segments aux plateformes sociales sur lesquelles il souhaite faire de la publicité, en optimisant ses dépenses publicitaires.

### Cas d’utilisation #2 {#use-case-2}

Une compagnie aérienne possède différents niveaux de clients (Bronze, Argent et Or) et souhaite fournir à chacun des niveaux des offres personnalisées via des plateformes sociales. L’entreprise utilise l’Audience Manager pour analyser l’activité des clients sur le site web. Cependant, tous les clients n’utilisent pas l’application mobile de la compagnie aérienne et certains d’entre eux ne se sont pas connectés au site web de la société. Les seuls identifiants de membre et d’adresse électronique de l’entreprise concernant ces clients sont les identifiants de membre et les adresses électroniques.

Pour les cibler sur les médias sociaux et les canaux similaires basés sur des personnes, ils peuvent intégrer les données client de leur [!DNL CRM] dans l’Audience Manager, en utilisant les adresses électroniques hachées comme identifiants.

Ensuite, ils peuvent combiner leurs données hors ligne avec leurs caractéristiques d’activité en ligne existantes, afin de créer de nouveaux segments d’audience qu’ils peuvent cibler via [!DNL People-Based Destinations].
