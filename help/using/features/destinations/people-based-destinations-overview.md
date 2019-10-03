---
description: 'Use people-based destinations to send first-party audience segments to people-based environments. These environments are closed ecosystems belonging to one entity that controls the content that is being displayed within it. They include social platforms such as Facebook, and other platforms that rely on customer accounts to personalize the displayed content. '
seo-description: 'Utilisez des destinations basées sur les personnes pour envoyer des segments d’audience propriétaires vers des environnements basés sur les personnes. Ces environnements sont des écosystèmes fermés appartenant à une entité qui contrôle le contenu affiché à l’intérieur. Elles comprennent des plateformes sociales telles que Facebook et d’autres plateformes qui s’appuient sur des comptes clients pour personnaliser le contenu affiché.  '
seo-title: People-Based Destinations Overview and Use Cases
solution: Audience Manager
title: Présentation et cas d’utilisation
translation-type: tm+mt
source-git-commit: 0eb6a6f67d87377a044b18118fac0185219b0347

---


# Overview and Use Cases {#overview-use-cases}

Servez-vous [!DNL People-Based Destinations] pour envoyer des segments d’audience propriétaires vers des environnements basés sur des personnes. Ces environnements sont des écosystèmes fermés appartenant à une entité qui contrôle le contenu affiché à l’intérieur. Elles comprennent des plateformes sociales telles que [!DNL Facebook]et d’autres plateformes qui s’appuient sur des comptes clients pour personnaliser le contenu affiché.

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans ce document n'est un conseil juridique. Veuillez consulter votre propre conseiller juridique pour obtenir des conseils juridiques.

## Aperçu {#overview}

[!DNL People-Based Destinations] vous permet d’appliquer la segmentation aux données en ligne et hors ligne afin de créer des segments d’audience en fonction d’identifiants [](people-based-destinations-prerequisites.md#hashing-requirements)hachés, tels que des adresses électroniques ou des numéros de téléphone. Ensuite, vous pouvez envoyer ces segments aux "jardins muraux", tels que [!DNL Facebook], où vous pouvez cibler votre public sur les plateformes sociales. [!DNL People-Based Destinations] peut vous aider :

* ciblez les audiences hors ligne et en ligne sur des plateformes telles que [!DNL Facebook], en fonction des adresses électroniques hachées ;
* Compléter les fonctionnalités de ciblage de périphériques et de cookies existantes d’Audience Manager ;
* éliminer les coûts associés aux solutions d'intégration de données tierces ;
* Éliminez les coûts associés au développement de flux de travail personnalisés d'intégration de données ;
* Ciblez les audiences dans des environnements sans cookie ;
* Ciblez les audiences en dédupliquant les adresses électroniques associées aux ID de client.

Vous pouvez les utiliser [!DNL People-Based Destinations] pour segmenter et cibler les clients à forte valeur ajoutée qui n’ont peut-être pas visité votre site Web ou arrêter de cibler ceux qui ont déjà effectué une conversion hors ligne. De plus, vous pouvez tirer parti [!DNL Profile Merge Rules] de la combinaison de vos données propriétaires hors ligne avec vos données propriétaires en ligne, y compris les données client provenant d’autres solutions Adobe Experience Cloud, pour optimiser vos efforts publicitaires sur les médias sociaux.

![pbd-overview](assets/pbd-overview.png)

## Availability {#availability}

[!DNL People-Based Destinations] est une intégration Premium d’Audience Manager. Contactez votre représentant Adobe pour profiter de cette fonctionnalité de qualité supérieure.

## Pourquoi Utiliser Des Destinations Basées Sur Les Personnes {#why-use}

**Proposez à vos clients des expériences cross-canal cohérentes en gérant l’ensemble de la segmentation de l’audience depuis Audience Manager.**

Si vous n’activez pas les segments d’audience dans les canaux basés sur les personnes par le biais d’Audience Manager, vous obtenez des expériences incohérentes entre ce que voient vos clients lorsqu’ils visitent votre site Web et ce qu’ils voient, par exemple, dans leurs [!DNL Facebook] flux. Le ciblage cohérent sur plusieurs canaux peut augmenter les recettes publicitaires tout en optimisant les dépenses publicitaires.

**Ciblez les audiences dans les canaux basés sur les personnes sans avoir besoin d’une solution d’intégration de données dédiée ni de processus personnalisés pour envoyer des audiences.**

The more "traditional" way of targeting audiences across people-based channels involves you having to export your customer data in a format accepted by the platform that you want to advertise on, and then using the platform's dedicated data onboarding method to bring your customer data to your advertiser account. Il s'agit d'un travail manuel que vous devez effectuer pour chaque plateforme sur laquelle vous souhaitez publier de l'information. En outre, différentes plateformes peuvent avoir des exigences de format de données différentes, ce qui rend le processus encore plus fastidieux.

![pbd-overview](assets/pbd-diagram.png)

Through , Audience Manager helps you centralize your customer data, build audience segments, and activate them across multiple people-based channels. [!DNL People-Based Destinations] You can do this all from within the Audience Manager UI, avoiding the additional work of manually uploading data to each platform, saving you valuable time in the process.

**Create and activate audience segments from purely offline profiles.**

[!DNL People-Based Destinations] solve the issue that previously, you could only activate audience segments based on device activity. With , you can create segments from purely offline data from your own , and activate them in people-based platforms. [!DNL People-Based Destinations][!DNL CRM] Additionally, you can correlate your offline data with device data that you already have in Audience Manager.

**Leverage Audience Manager's data governance and privacy controls to safely handle customer data.**

[!DNL People-Based Destinations] requires that you only use irreversibly hashed identifiers. This reduces the risk associated with manually uploading customer data into each destination platform.

Regardez la vidéo ci-dessous pour obtenir un aperçu du flux de données lors de l’utilisation [!UICONTROL People-Based Destinations].

[!VIDEO](https://video.tv.adobe.com/v/28968/?captions=fre_fr)

## Cas d’utilisation {#use-cases}

Pour vous aider à mieux comprendre comment et quand utiliser [!DNL People-Based Destinations], voici deux exemples d’utilisation que les clients d’Audience Manager peuvent résoudre à l’aide de cette fonctionnalité.

### Use Case #1 {#use-case-1}

An online retailer wants to reach existing customers through social platforms and show them personalized offers based on their previous orders. Avec [!DNL People-Based Destinations]cela, le détaillant en ligne peut assimiler des adresses électroniques hachées de son propre [!DNL CRM] à Audience Manager, créer des segments à partir de ses propres données hors ligne et envoyer ces segments aux plateformes sociales sur lesquelles il souhaite faire de la publicité, en optimisant ainsi ses dépenses publicitaires.

### Use Case #2 {#use-case-2}

Une compagnie aérienne a des niveaux de clients différents (Bronze, Argent et Or) et veut fournir à chacun des niveaux des offres personnalisées via des plateformes sociales. L’entreprise utilise Audience Manager pour analyser l’activité des clients sur le site Web. Cependant, tous les clients n’utilisent pas l’application mobile de la compagnie aérienne et certains d’entre eux ne se sont pas connectés au site Web de la compagnie. Les seuls identifiants dont dispose l’entreprise concernant ces clients sont les identifiants d’adhésion et les adresses électroniques.

Pour les cibler sur les réseaux sociaux et les canaux de personnes similaires, ils peuvent embarquer les données client de leur [!DNL CRM] compte dans Audience Manager, en utilisant les adresses électroniques hachées comme identifiants.

Ensuite, ils peuvent combiner leurs données hors ligne avec leurs caractéristiques d’activité en ligne existantes, afin de créer de nouveaux segments d’audience qu’ils peuvent cibler via [!DNL People-Based Destinations].
