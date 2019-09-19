---
description: Les composants de la gestion des balises d’Audience Manager comprennent le portail client, Adobe Tag Manager (obsolète en faveur d’Adobe Dynamic Tag Manager et d’Adobe Launch), DIL, Akamai et la base de données de contrôle.
seo-description: Les composants de la gestion des balises d’Audience Manager comprennent le portail client, Adobe Tag Manager (obsolète en faveur d’Adobe Dynamic Tag Manager et d’Adobe Launch), DIL, Akamai et la base de données de contrôle.
seo-title: Composants de la gestion des balises
solution: Audience Manager
title: Composants de la gestion des balises
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Composants de la gestion des balises{#tag-management-components}

Les composants de la gestion des balises d’Audience Manager comprennent le portail client, Adobe Tag Manager (obsolète en faveur d’Adobe Dynamic Tag Manager et d’Adobe Launch), DIL, Akamai et la base de données de contrôle.

<!-- 

c_comptag.xml

 -->

Audience Manager contient les composants suivants :

* [Portail client](../../reference/system-components/components-tag-management.md#client-portal)
* [Conteneur DIL/TIM](../../reference/system-components/components-tag-management.md#dil-tim)
* [Bibliothèque d’informations sur les données (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Base de données de contrôle](../../reference/system-components/components-tag-management.md#control-database)

## Portail client {#client-portal}

Le portail client est l’interface utilisateur principale pour la gestion des balises et des données. Les clients utilisent le portail pour travailler avec des balises, créer des caractéristiques et des segments, configurer des destinations et surveiller les performances des campagnes avec des rapports.

## Conteneur DIL/TIM {#dil-tim}

Le [!UICONTROL DIL] conteneur permet de déployer [!DNL Audience Manager] le code de collecte de données sur votre site Web. [!UICONTROL TIM] est le Gestionnaire d’insertion de balises obsolète. Il n'est plus utilisé par [!DNL Audience Manager]les. Vous utilisez plutôt la gestion [dynamique des balises](https://marketing.adobe.com/resources/help/en_US/dtm/) ou l’ [!DNL Audience Manager] extension dans [Adobe Launch](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) pour configurer et générer le code conteneur que vous placez sur les pages de votre inventaire. Le [!UICONTROL DTM] conteneur travaille avec [!UICONTROL Data Information Library (DIL)] pour collecter des données de votre site et les envoyer à [!DNL Audience Manager].

## Bibliothèque d’intégration des données (DIL){#dil} 

La bibliothèque [d’informations](../../dil/dil-overview.md) de données (DIL) est un module API autonome qui collecte des données à partir de votre site Web. [!UICONTROL DIL] évite d’écrire du code spécial pour la collecte de données, l’intégration, la lecture des valeurs de cookie et la récupération des données de page. [!UICONTROL DIL] exécute ces actions automatiquement. De plus, [!UICONTROL DIL] est compact. Il s’agit d’une bibliothèque de code autonome qui aide à réduire la quantité de code nécessaire pour collecter des informations. Enfin, [!UICONTROL DIL] vous permet de vous intégrer [!DNL Audience Manager] à d’autres produits dans [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] utilise [Akamai](https://www.akamai.com/html/about/index.html) pour héberger et diffuser le code de conteneur à partir de notre propre plateforme de gestion des balises connue sous le nom [!UICONTROL TIM (Tag Insertion Manager)]. Cependant, le déploiement du code avec [!UICONTROL TIM] a été progressivement abandonné au profit de [!UICONTROL Adobe Dynamic Tag Management] et [!UICONTROL Adobe Launch].

## Base de données de contrôle {#control-database}

La base de données de contrôle :

* Traite les entrées du client à partir du portail (par exemple, création de caractéristiques et de destinations).
* Transmet les données à Akamai, qui inclut les données utilisées pour créer le modèle de conteneur et l’iFrame de publication de destination.
* Renvoie des données pour les systèmes de rapports de l’interface utilisateur.

