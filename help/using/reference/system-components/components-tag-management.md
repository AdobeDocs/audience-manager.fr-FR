---
description: Les composants de gestion des balises Audience Manager comprennent le portail client, Adobe Tag Manager (obsolète au profit d’Adobe Experience Platform Launch), DIL, Akamai et la base de données de contrôle.
seo-description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Experience Platform Launch), DIL, Akamai, and the control database.
seo-title: Tag Management Components
solution: Audience Manager
title: Composants Tag Management
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: System Components
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 1%

---

# Composants Tag Management{#tag-management-components}

Les composants de gestion des balises Audience Manager comprennent le portail client, Adobe Tag Manager (obsolète au profit de balises Adobe Experience Platform), DIL, Akamai et la base de données de contrôle.

<!-- 

c_comptag.xml

 -->

Audience Manager contient les composants suivants :

* [Portail client](../../reference/system-components/components-tag-management.md#client-portal)
* Conteneur DIL/TIM [&#128279;](../../reference/system-components/components-tag-management.md#dil-tim)
* [Bibliothèque d’informations sur les données (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [ Akamai ](../../reference/system-components/components-tag-management.md#akamai)
* [Base de données de contrôle](../../reference/system-components/components-tag-management.md#control-database)

## Portail client {#client-portal}

Le portail client est l’interface utilisateur principale pour la gestion des balises et des données. Les clients utilisent le portail pour utiliser les balises, créer des caractéristiques et des segments, configurer des destinations et surveiller les performances des campagnes à l’aide de rapports.

## Conteneur DIL/TIM {#dil-tim}

Le conteneur [!UICONTROL DIL] permet de déployer [!DNL Audience Manager] code de collecte de données sur votre site web. [!UICONTROL TIM] est le gestionnaire d’insertion de balises obsolète. Il n’est plus utilisé par les [!DNL Audience Manager]. Au lieu de cela, vous utilisez l’extension [!DNL Audience Manager] dans [Adobe Experience Platform Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) pour configurer et générer le code de conteneur que vous placez sur les pages de votre inventaire.

## Bibliothèque d’intégration de données (DIL) {#dil}

La [bibliothèque d’informations sur les données](../../dil/dil-overview.md) (DIL) est un module d’API autonome qui collecte des données à partir du site Web. [!UICONTROL DIL] permet d’éviter d’écrire du code spécial pour la collecte de données, l’intégration, la lecture des valeurs de cookie et la récupération des données de page. [!UICONTROL DIL] effectue automatiquement ces actions. De plus, [!UICONTROL DIL] est compact. Il s’agit d’une bibliothèque de code autonome qui permet de réduire la quantité de code requise pour collecter des informations. Enfin, [!UICONTROL DIL] vous aide à intégrer [!DNL Audience Manager] à d’autres produits de la [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] utilise [Akamai](https://www.akamai.com/us/en/about/) pour héberger et diffuser du code de conteneur à partir de notre propre plateforme de gestion des balises appelée [!UICONTROL TIM (Tag Insertion Manager)]. Cependant, le déploiement du code avec [!UICONTROL TIM] a été progressivement abandonné au profit de [!DNL Adobe Experience Platform Tags].

## Base de données de contrôle {#control-database}

La base de données de pilotage :

* Traite les entrées client à partir du portail (par exemple, la création de caractéristiques et de destinations).
* Transmet des données à Akamai, qui inclut les données utilisées pour créer le modèle de conteneur et l’iFrame de publication de destination.
* Renvoie des données pour les systèmes de rapports de l’interface utilisateur.
