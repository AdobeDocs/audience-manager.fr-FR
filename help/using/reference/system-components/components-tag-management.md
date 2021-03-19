---
description: Les composants de la gestion des balises d’Audience Manager incluent le portail client, Adobe Tag Manager (obsolète en faveur de Adobe Dynamic Tag Manager et Adobe Experience Platform Launch), DIL, Akamai et la base de données de contrôle.
seo-description: Les composants de la gestion des balises d’Audience Manager incluent le portail client, Adobe Tag Manager (obsolète en faveur de Adobe Dynamic Tag Manager et Adobe Experience Platform Launch), DIL, Akamai et la base de données de contrôle.
seo-title: Composants de la gestion des balises
solution: Audience Manager
title: Composants de la gestion des balises
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: composants système
translation-type: tm+mt
source-git-commit: 65598677498ede26e4961cd4849c9b655dac38dc
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 5%

---


# Composants de la gestion des balises{#tag-management-components}

Les composants de la gestion des balises d’Audience Manager incluent le portail client, Adobe Tag Manager (obsolète en faveur de Adobe Dynamic Tag Manager et Adobe Experience Platform Launch), DIL, Akamai et la base de données de contrôle.

<!-- 

c_comptag.xml

 -->

L’Audience Manager contient les composants suivants :

* [Portail client](../../reference/system-components/components-tag-management.md#client-portal)
* [CONTENEUR DIL/TIM](../../reference/system-components/components-tag-management.md#dil-tim)
* [Bibliothèque d’informations sur les données (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Base de données de contrôle](../../reference/system-components/components-tag-management.md#control-database)

## Portail client {#client-portal}

Le portail client est l’interface utilisateur Principale pour les balises et les datas Management. Les clients utilisent le portail pour manipuler les balises, créer des caractéristiques et des segments, configurer des destinations et contrôler les performances des campagnes à l’aide de rapports.

## CONTENEUR DIL/TIM {#dil-tim}

Le conteneur [!UICONTROL DIL] permet de déployer le code de collecte de données [!DNL Audience Manager] sur votre site Web. [!UICONTROL TIM] est le Gestionnaire d&#39;insertion de balises obsolète. Il n&#39;est plus utilisé par [!DNL Audience Manager]. Vous utilisez plutôt [la gestion dynamique des balises](https://docs.adobe.com/content/help/fr-FR/dtm/using/dtm-home.html) ou l&#39;extension [!DNL Audience Manager] dans [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html) pour configurer et générer le code de conteneur que vous placez sur les pages de votre inventaire. Le conteneur [!UICONTROL DTM] travaille avec [!UICONTROL Data Information Library (DIL)] pour collecter les données de votre site et les envoyer à [!DNL Audience Manager].

##  Data Integration Library (DIL) {#dil}

La [bibliothèque d’informations sur les données](../../dil/dil-overview.md) (DIL) est un module d’API autonome qui collecte des données de votre site Web. [!UICONTROL DIL] aide à éliminer la nécessité d’écrire du code spécial pour la collecte de données, l’intégration, la lecture des valeurs de cookie et la récupération des données de page. [!UICONTROL DIL] exécute ces actions automatiquement. De plus, [!UICONTROL DIL] est compact. Il s’agit d’une bibliothèque de code autonome qui aide à réduire la quantité de code nécessaire pour collecter des informations. Enfin, [!UICONTROL DIL] vous aide à intégrer [!DNL Audience Manager] à d&#39;autres produits dans l&#39;Experience Cloud [!DNL Adobe].

## Akamai {#akamai}

[!DNL Audience Manager] utilise l’hôte  [](https://www.akamai.com/us/en/about/) Akamaito et fournit le code de conteneur de notre propre plateforme de gestion des balises, appelée  [!UICONTROL TIM (Tag Insertion Manager)]. Cependant, le déploiement du code avec [!UICONTROL TIM] a été progressivement abandonné en faveur de [!DNL Adobe Dynamic Tag Management] et [!DNL Adobe Experience Platform Launch].

## Base de données de contrôle {#control-database}

La base de données de contrôle :

* Traite les entrées du client à partir du portail (par exemple, la création de caractéristiques et de destinations).
* Transmet les données à Akamai, qui inclut les données utilisées pour créer le modèle de conteneur et l’iFrame de publication de destination.
* Renvoie des données pour les systèmes de rapports d’interface utilisateur.

