---
description: Les composants de la gestion des balises d'Audience Manager comprennent le portail client, Adobe Tag Manager (obsolète en faveur d'Adobe Dynamic Tag Manager et Adobe Launch), DIL, Akamai et la base de données de contrôle.
seo-description: Les composants de la gestion des balises d'Audience Manager comprennent le portail client, Adobe Tag Manager (obsolète en faveur d'Adobe Dynamic Tag Manager et Adobe Launch), DIL, Akamai et la base de données de contrôle.
seo-title: Composants de la gestion des balises
solution: Audience Manager
title: Composants de la gestion des balises
uuid: e 5059478-6 ba 7-4 e 1 a-afec-e 41 ad 7 a 27750
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Tag Management Components{#tag-management-components}

Les composants de la gestion des balises d'Audience Manager comprennent le portail client, Adobe Tag Manager (obsolète en faveur d'Adobe Dynamic Tag Manager et Adobe Launch), DIL, Akamai et la base de données de contrôle.

<!-- 

c_comptag.xml

 -->

Audience Manager contient les composants suivants :

* [Portail client](../../reference/system-components/components-tag-management.md#client-portal)
* [Conteneur DIL/TIM](../../reference/system-components/components-tag-management.md#dil-tim)
* [Bibliothèque d'informations de données (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Base de données de contrôle](../../reference/system-components/components-tag-management.md#control-database)

## Client Portal {#client-portal}

Le portail client est l'interface utilisateur principale pour la gestion des balises et des données. Les clients utilisent le portail pour travailler avec des balises, créer des caractéristiques et des segments, configurer les destinations et contrôler les performances des campagnes avec les rapports.

## DIL/TIM Container {#dil-tim}

[!UICONTROL DIL] Le conteneur aide à déployer [!DNL Audience Manager] le code de collecte de données sur votre site Web. [!UICONTROL TIM] est le Gestionnaire d'insertion de balises obsolète. It is no longer used by [!DNL Audience Manager]. Instead, you use [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/) or the [!DNL Audience Manager] extension in [Adobe Launch](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) to configure and generate container code that you place on pages in your inventory. [!UICONTROL DTM] Le conteneur fonctionne avec la [!UICONTROL Data Information Library (DIL)] collecte des données de votre site et l'envoie [!DNL Audience Manager].

## Bibliothèque d’intégration des données (DIL){#dil} 

The [Data Information Library](../../dil/dil-overview.md) (DIL) is a self-contained API module that collects data from your website. [!UICONTROL DIL] aide à éliminer la nécessité d'écrire du code spécial pour la collecte de données, l'intégration, la lecture des valeurs de cookie et la récupération des données de la page. [!UICONTROL DIL] effectue automatiquement ces actions. Additionally, [!UICONTROL DIL] is compact. Il s'agit d'une bibliothèque de code autonome qui permet de réduire la quantité de code nécessaire à la collecte d'informations. Finally, [!UICONTROL DIL] helps you integrate [!DNL Audience Manager] with other products in the [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] utilise [Akamai](https://www.akamai.com/html/about/index.html) pour héberger et diffuser le code de conteneur de notre propre plateforme de gestion des balises connue sous le nom [!UICONTROL TIM (Tag Insertion Manager)]de. However, code deployment with [!UICONTROL TIM] has been phased out in favor of [!UICONTROL Adobe Dynamic Tag Management] and [!UICONTROL Adobe Launch].

## Control Database {#control-database}

La base de données de contrôle :

* Traite les données client du portail (par exemple, création de caractéristiques et de destinations).
* Transmet les données à Akamai, qui inclut les données utilisées pour construire le modèle de conteneur et l'iframe de publication de destination.
* Renvoie les données des systèmes de création de rapports IU.

