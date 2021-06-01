---
description: Les composants de la gestion des balises d’Audience Manager comprennent le portail client, Adobe Tag Manager (obsolète en faveur d’Adobe Experience Platform Launch), DIL, Akamai et la base de données de contrôle.
seo-description: Les composants de la gestion des balises d’Audience Manager comprennent le portail client, Adobe Tag Manager (obsolète en faveur d’Adobe Experience Platform Launch), DIL, Akamai et la base de données de contrôle.
seo-title: Composants de la gestion des balises
solution: Audience Manager
title: Composants de la gestion des balises
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: 'Composants système '
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 4%

---

# Composants de la gestion des balises{#tag-management-components}

Les composants de la gestion des balises d’Audience Manager comprennent le portail client, Adobe Tag Manager (obsolète en faveur d’Adobe Experience Platform Launch), DIL, Akamai et la base de données de contrôle.

<!-- 

c_comptag.xml

 -->

L’Audience Manager contient les composants suivants :

* [Portail client](../../reference/system-components/components-tag-management.md#client-portal)
* [Conteneur DIL/TIM](../../reference/system-components/components-tag-management.md#dil-tim)
* [Bibliothèque d’informations sur les données (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Base de données de contrôle](../../reference/system-components/components-tag-management.md#control-database)

## Portail client {#client-portal}

Le portail client est la Principale interface utilisateur (IU) de la gestion des balises et des données. Les clients utilisent le portail pour utiliser des balises, créer des caractéristiques et des segments, configurer des destinations et contrôler les performances des campagnes à l’aide de rapports.

## Conteneur DIL/TIM {#dil-tim}

Le conteneur [!UICONTROL DIL] permet de déployer le code de collecte de données [!DNL Audience Manager] sur votre site web. [!UICONTROL TIM] est le gestionnaire d’insertion de balises obsolète. Il n’est plus utilisé par [!DNL Audience Manager]. Vous utilisez plutôt l’extension [!DNL Audience Manager] dans [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html) pour configurer et générer le code de conteneur que vous placez sur les pages de votre inventaire.

## Bibliothèque d’intégration de données (DIL) {#dil}

La [Data Information Library](../../dil/dil-overview.md) (DIL) est un module d’API autonome qui collecte des données de votre site web. [!UICONTROL DIL] aide à éliminer la nécessité d’écrire du code spécial pour la collecte de données, l’intégration, la lecture des valeurs de cookie et la récupération des données de page. [!UICONTROL DIL] exécute ces actions automatiquement. En outre, [!UICONTROL DIL] est compact. Il s’agit d’une bibliothèque de code autonome qui aide à réduire la quantité de code nécessaire pour collecter des informations. Enfin, [!UICONTROL DIL] vous aide à intégrer [!DNL Audience Manager] à d’autres produits dans l’Experience Cloud [!DNL Adobe].

## Akamai {#akamai}

[!DNL Audience Manager] utilise l’hôte  [](https://www.akamai.com/us/en/about/) Akamaito et diffusez le code de conteneur depuis notre propre plateforme de gestion des balises appelée  [!UICONTROL TIM (Tag Insertion Manager)]. Cependant, le déploiement du code avec [!UICONTROL TIM] a été supprimé progressivement au profit de [!DNL Adobe Experience Platform Launch].

## Base de données de contrôle {#control-database}

La base de données témoin :

* Traite les entrées du client à partir du portail (par exemple, la création de caractéristiques et de destinations).
* Transmet les données à Akamai, qui inclut les données utilisées pour créer le modèle de conteneur et l’iFrame de publication de destination.
* Renvoie des données pour les systèmes de création de rapports de l’interface utilisateur.
