---
description: Cet article décrit comment les  de  sont partagées entre  Manager et Adobe Experience Platform.
seo-description: Cet article décrit comment les  de  sont partagées entre  Manager et Adobe Experience Platform.
seo-title: '  de partage de entre  Gestionnaire de et Adobe Experience Platform'
solution: Audience Manager
title: '  de partage de entre  Gestionnaire de et Adobe Experience Platform'
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
translation-type: tm+mt
source-git-commit: efc07cb0aacc31f3708c98e1c82c195c202c10ef

---


#   de partage de entre  Gestionnaire de et Adobe Experience Platform {#aam-aep-audience-sharing}

>[!NOTE]
>
> Contactez votre représentant commercial Adobe pour déverrouiller l’accès à cette fonctionnalité.

## Aperçu {#overview}

La fonctionnalité de partage de  de  entre  Gestionnaire de et Adobe Experience Platform vous permet de partager vos caractéristiques et segments du Gestionnaire de sur Adobe Experience Platform et vice versa. Vous avez besoin du connecteur [de  Manager](https://docs.adobe.com/content/help/en/experience-platform/source-connectors/adobe-applications/audience-manager.html) pour activer le partage de  entre le Gestionnaire de de et Adobe Experience Platform.

Vous pouvez utiliser  caractéristiques et segments  Manager dans Experience Platform pour ajouter des données  Manager à votre client et bénéficier du service [de](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md)segmentation de la plateforme d’expérience.

Dans  Gestionnaire de  de, vous pouvez utiliser les segments de la plateforme d’expérience pour les cas d’utilisation de la plateforme, tels que :
* Ajouter de données [tierces](/help/using/overview/data-types-collected.md#third-party-data) à vos segments ;
* [Modélisation algorithmique](/help/using/features/algorithmic-models/understanding-models.md);
* Activez vos segments vers des destinations qui ne sont pas encore prises en charge dans le catalogue [des](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)destinations de la plateforme d’expérience.

De plus, vos segments de plateforme d’expérience sont partagés avec d’autres solutions Experience Cloud, via les services [principaux](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html).

<br> 

Consultez le tableau ci-dessous pour une présentation des cas d’utilisation du partage de   :

| **Cas d’utilisation** | **Adobe Experience Platform** | **Audience Manager** | **Principaux services** |
---------|----------|---------|---------
| **Partage de** | <ul><li>Enrichir les  des clients avec  données du Gestionnaire de </li><li>Utilisation des données   Manager dans la segmentation de la plateforme d’expérience</li></ul> | <ul><li>Ajouter de données tierces aux segments</li><li>Modélisation algorithmique</li><li> de  vers d&#39;autres destinations</li></ul> | Utilisez les segments de plateforme d’expérience dans d’autres solutions Experience Cloud, telles qu’ Adobe ou Analytics. |

<br> 

##  segments et caractéristiques de  Manager dans Adobe Experience Platform {#aam-segments-traits-in-aep}

Vos caractéristiques et segments   Manager apparaissent dans la plate-forme d’expérience sous la forme d’un **** de  dans le flux de travaux des segments. Pour plus d’informations sur vos segments et caractéristiques   Manager dans Experience Platform, voir :

* [Présentation du service de segmentation](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Guide de l’utilisateur du créateur de segments de plateforme d’expérience](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [ Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/source-connectors/adobe-applications/audience-manager.html)

<br> 

## Segments de la plate-forme Adobe Experience Platform dans  Gestionnaire  de {#aep-segments-in-aam}

Les segments que vous créez dans la plateforme d’expérience apparaissent dans votre interface  Gestionnaire de  de sous forme de caractéristiques et de segments, avec les règles de composition suivantes :
* Caractéristique : La règle de caractéristique est l’ID du segment de la plateforme d’expérience.
* Segment : Le segment est constitué de la caractéristique décrite ci-dessus.

### Caractéristiques {#aep-segments-as-aam-traits}

 Gestionnaire de  de  crée automatiquement un dossier de caractéristiques appelé Caractéristiques **de la plate-forme** d’expérience dans votre de caractéristiques.

![Caractéristiques du de plateformes d’expérience](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Vous pouvez utiliser des caractéristiques créées automatiquement dans des segments aux côtés d’autres caractéristiques. Vous pouvez, par exemple, combiner des caractéristiques créées à partir de segments de plateforme d’expérience avec des caractéristiques tierces acquises par l’intermédiaire de la   de marché [](/help/using/features/audience-marketplace/audience-marketplace.md).

Pour un exemple de caractéristique créée automatiquement à partir d’un segment de plateforme d’expérience, voir la capture d’écran ci-dessous :

![Caractéristique de la plateforme d’expérience](/help/using/integration/integration-aep/assets/aep-trait.png)


| Numéro d&#39;article | Nom | Description |
---------|----------|---------
| 1 | Type de caractéristiques | Les caractéristiques créées à partir des segments de plateforme d’expérience sont créées sous forme de caractéristiques intégrées dans  Gestionnaire de  de. |
| 2 | Source de données | Création automatique. Toutes les caractéristiques et tous les segments créés automatiquement à partir des segments de la plate-forme d’expérience sont stockés dans la source de données **Adobe Experience Platform  le partage** de . |
| 3 | Code d’intégration | Le code d’intégration correspond à l’ID de segment dans la plateforme d’expérience. |
| 4 |  de caractéristiques  | Le trait  est `segID = segment ID in Experience Platform`. |
| 5 | Segments avec ce trait | Segment créé automatiquement qui utilise cette caractéristique comme composition. |

<br> 

### Segments {#aep-segments-as-aam-segments}

 Gestionnaire de  de segments crée automatiquement un dossier de segments appelé Segments **de plateforme d’** expérience dans votre de  de segments.

![Capture d&#39;écran de](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Pour un exemple de segment créé automatiquement à partir d’un segment de plateforme d’expérience, voir la capture d’écran ci-dessous :

![Capture d&#39;écran du segment](/help/using/integration/integration-aep/assets/aep-segment.png)

| Numéro d&#39;article | Nom | Description |
---------|----------|---------
| 1 | Code d’intégration | Le code d’intégration correspond à l’ID de segment dans la plateforme d’expérience. |
| 2 | Source de données | Création automatique. Toutes les caractéristiques et tous les segments créés automatiquement à partir des segments de la plate-forme d’expérience sont stockés dans la source de données **Adobe Experience Platform  le partage** de . |
| 3 | Règle de fusion  | **La stratégie** de fusion externe indique que les segments créés automatiquement suivent la stratégie de fusion définie dans la plateforme d’expérience. |
| 4 | Règle de segment | Le segment est constitué de la caractéristique décrite dans la section [](#aep-segments-as-aam-traits)Caractéristiques. |
