---
description: Les composants de la gestion des balises d’Audience Manager incluent le portail client, Adobe Tag Manager (obsolète en faveur de Adobe Dynamic Tag Manager et de Adobe Experience Platform Launch), DIL, Akamai et la base de données de contrôle.
seo-description: Les composants de la gestion des balises d’Audience Manager incluent le portail client, Adobe Tag Manager (obsolète en faveur de Adobe Dynamic Tag Manager et de Adobe Experience Platform Launch), DIL, Akamai et la base de données de contrôle.
seo-title: Composants de la gestion des balises
solution: Audience Manager
title: Composants de la gestion des balises
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 5%

---


# Composants de la gestion des balises{#tag-management-components}

Les composants de la gestion des balises d’Audience Manager incluent le portail client, Adobe Tag Manager (obsolète en faveur de Adobe Dynamic Tag Manager et de Adobe Experience Platform Launch), DIL, Akamai et la base de données de contrôle.

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

Le portail client est l’interface utilisateur principale pour les balises et les datas Management. Les clients utilisent le portail pour manipuler les balises, créer des caractéristiques et des segments, configurer des destinations et contrôler les performances des campagnes à l’aide de rapports.

## Conteneur DIL/TIM {#dil-tim}

Le [!UICONTROL DIL] conteneur permet de déployer [!DNL Audience Manager] le code de collecte de données sur votre site Web. [!UICONTROL TIM] est le Gestionnaire d&#39;insertion de balises obsolète. Il n&#39;est plus utilisé par [!DNL Audience Manager]les. Vous utilisez plutôt la gestion [](https://docs.adobe.com/content/help/fr-FR/dtm/using/dtm-home.html) dynamique des balises ou l’ [!DNL Audience Manager] extension dans Lancement [d’](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) Adobe Experience Platform pour configurer et générer le code de conteneur que vous placez sur les pages de votre stock. Le [!UICONTROL DTM] conteneur travaille avec le [!UICONTROL Data Information Library (DIL)] pour collecter des données de votre site et les envoyer à [!DNL Audience Manager].

##  Data Integration Library (DIL) {#dil}

La bibliothèque [d’informations](../../dil/dil-overview.md) de données (DIL) est un module d’API autonome qui collecte des données à partir de votre site Web. [!UICONTROL DIL] aide à éliminer la nécessité d’écrire du code spécial pour la collecte de données, l’intégration, la lecture des valeurs de cookie et la récupération des données de page. [!UICONTROL DIL] exécute ces actions automatiquement. De plus, [!UICONTROL DIL] est compact. Il s’agit d’une bibliothèque de code autonome qui aide à réduire la quantité de code nécessaire pour collecter des informations. Enfin, [!UICONTROL DIL] vous aide à vous intégrer [!DNL Audience Manager] à d’autres produits dans l’ [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] utilise [Akamai](https://www.akamai.com/html/about/index.html) pour héberger et diffuser du code de conteneur à partir de notre propre plateforme de gestion des balises connue sous le nom [!UICONTROL TIM (Tag Insertion Manager)]. Cependant, le déploiement du code avec [!UICONTROL TIM] a été progressivement supprimé au profit de [!DNL Adobe Dynamic Tag Management] et [!DNL Adobe Experience Platform Launch].

## Base de données de contrôle {#control-database}

La base de données de contrôle :

* Traite les entrées du client à partir du portail (par exemple, la création de caractéristiques et de destinations).
* Transmet les données à Akamai, qui inclut les données utilisées pour créer le modèle de conteneur et l’iFrame de publication de destination.
* Renvoie des données pour les systèmes de rapports d’interface utilisateur.

