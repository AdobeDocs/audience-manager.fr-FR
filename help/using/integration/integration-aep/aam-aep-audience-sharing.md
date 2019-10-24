---
description: Cet article décrit la manière dont les audiences sont partagées entre Audience Manager et Adobe Experience Platform.
seo-description: Cet article décrit la manière dont les audiences sont partagées entre Audience Manager et Adobe Experience Platform.
seo-title: Partage d’audience entre Audience Manager et Adobe Experience Platform
solution: Audience Manager
title: Partage d’audience entre Audience Manager et Adobe Experience Platform
keywords: Partage d’audience AEP, segments AEP, segments de plateforme
translation-type: tm+mt
source-git-commit: e081e31380d4600883f927b5ecef3b38be2a676e

---


# Partage d’audience entre Audience Manager et Adobe Experience Platform {#aam-aep-audience-sharing}

>[!NOTE]
>
>Cette page contient une documentation bêta qui décrit les fonctionnalités disponibles pour les clients d’Audience Manager *et d’Adobe Experience Platform* . Cette documentation peut être modifiée avant la version finale du produit.
>
> Contactez votre représentant commercial Adobe pour déverrouiller l’accès à cette fonctionnalité.

## Aperçu {#overview}

La fonctionnalité de partage d’audience entre Audience Manager et Adobe Experience Platform vous permet de partager vos caractéristiques et segments Audience Manager sur Adobe Experience Platform et vice versa.

Vous pouvez utiliser les caractéristiques et les segments d’Audience Manager dans Experience Platform pour ajouter des données d’Audience Manager à vos profils clients et bénéficier du service [de](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segmentation.md)segmentation de la plateforme d’expérience.

Dans Audience Manager, vous pouvez utiliser les segments de la plateforme d’expérience pour les cas d’utilisation de la plateforme de gestion de données, tels que :
* Ajout de données [tierces](/help/using/overview/data-types-collected.md#third-party-data) à vos segments ;
* [Modélisation algorithmique](/help/using/features/algorithmic-models/understanding-models.md);
* Activation de vos segments vers des destinations qui ne sont pas actuellement prises en charge dans la plateforme d’expérience.

De plus, vos segments de plateforme d’expérience sont partagés avec d’autres solutions Experience Cloud, via les services [principaux](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html).

<br> 

Consultez le tableau ci-dessous pour une présentation des cas d’utilisation du partage d’audience :

| **Cas d’utilisation** | **Adobe Experience Platform** | **Audience Manager** | **Principaux services** |
---------|----------|---------|---------
| **Partage d’audience** | <ul><li>Enrichir les profils client à l’aide des données d’Audience Manager</li><li>Utilisation des données d’Audience Manager dans la segmentation de la plateforme d’expérience</li></ul> | <ul><li>Ajout de données tierces aux segments</li><li>Modélisation algorithmique</li><li>Activation vers d’autres destinations</li></ul> | Utilisez les segments de plateforme d’expérience dans d’autres solutions Experience Cloud, telles qu’Adobe Target ou Analytics. |

<br> 

## Segments et caractéristiques d’Audience Manager dans Adobe Experience Platform {#aam-segments-traits-in-aep}

Vos caractéristiques et segments Audience Manager apparaissent dans la plateforme d’expérience sous forme d’ **audiences** dans le processus des segments. Pour plus d’informations sur vos segments et caractéristiques Audience Manager dans la plateforme d’expérience, voir :

* [Présentation du service de segmentation](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segmentation.md)
* [Guide de l’utilisateur du créateur de segments de plateforme d’expérience](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segment-builder-guide.md)

<br> 

## Segments Adobe Experience Platform dans Audience Manager {#aep-segments-in-aam}

Les segments que vous créez dans la plate-forme d’expérience apparaissent dans l’interface d’Audience Manager sous forme de caractéristiques et de segments, avec les règles de composition suivantes :
* Caractéristique : La règle de caractéristique est l’ID du segment de la plateforme d’expérience.
* Segment : Le segment est constitué de la caractéristique décrite ci-dessus.

### Caractéristiques {#aep-segments-as-aam-traits}

Audience Manager crée automatiquement un dossier de caractéristiques appelé Caractéristiques **de la plate-forme** d’expérience dans votre stockage de caractéristiques.

![Caractéristiques du tableau de bord de la plateforme d’expérience](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Vous pouvez utiliser des caractéristiques créées automatiquement dans des segments aux côtés d’autres caractéristiques. Vous pouvez, par exemple, combiner des caractéristiques créées à partir de segments de plateforme d’expérience avec des caractéristiques tierces acquises via [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Pour un exemple de caractéristique créée automatiquement à partir d’un segment de plateforme d’expérience, voir la capture d’écran ci-dessous :

![Caractéristique de la plateforme d’expérience](/help/using/integration/integration-aep/assets/aep-trait.png)


| Numéro d'article | Nom | Description |
---------|----------|---------
| 1 | Type de caractéristiques | Les caractéristiques créées à partir des segments de plateforme d’expérience sont créées sous forme de caractéristiques intégrées dans Audience Manager. |
| 2 | Source de données | Création automatique. Toutes les caractéristiques et tous les segments créés automatiquement à partir des segments de la plate-forme d’expérience sont stockés dans la source de données **Adobe Experience Platform Audience Sharing**. |
| 3 | Code d’intégration | Le code d’intégration correspond à l’ID de segment dans la plateforme d’expérience. |
| 4 | Expression de trait | L’expression de caractéristique est `segID = segment ID in Experience Platform`. |
| 5 | Segments avec ce trait | Segment créé automatiquement qui utilise cette caractéristique comme composition. |

<br> 

### Segments {#aep-segments-as-aam-segments}

Audience Manager crée automatiquement un dossier de segments appelé Segments **de plateforme d’** expérience dans votre stockage de segments.

![Capture d'écran du tableau de bord](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Pour un exemple de segment créé automatiquement à partir d’un segment de plateforme d’expérience, voir la capture d’écran ci-dessous :

![Capture d'écran du segment](/help/using/integration/integration-aep/assets/aep-segment.png)

| Numéro d'article | Nom | Description |
---------|----------|---------
| 1 | Code d’intégration | Le code d’intégration correspond à l’ID de segment dans la plateforme d’expérience. |
| 2 | Source de données | Création automatique. Toutes les caractéristiques et tous les segments créés automatiquement à partir des segments de la plate-forme d’expérience sont stockés dans la source de données **Adobe Experience Platform Audience Sharing**. |
| 3 | Règle de fusion de profil | **La stratégie** de fusion externe indique que les segments créés automatiquement suivent la stratégie de fusion définie dans la plateforme d’expérience. |
| 4 | Règle de segment | Le segment est constitué de la caractéristique décrite dans la section [](#aep-segments-as-aam-traits)Caractéristiques. |