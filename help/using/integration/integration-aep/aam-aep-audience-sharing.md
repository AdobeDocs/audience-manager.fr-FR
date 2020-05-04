---
description: Cet article décrit comment les audiences sont partagées entre Audience Manager et Adobe Experience Platform.
seo-description: Cet article décrit comment les audiences sont partagées entre Audience Manager et Adobe Experience Platform.
seo-title: Partage d’Audiences entre Audience Manager et Adobe Experience Platform
solution: Audience Manager
title: Partage d’Audiences entre Audience Manager et Adobe Experience Platform
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
translation-type: tm+mt
source-git-commit: 7dddf19aa3b0fc0655b1b206d9c8f0c772190601

---


# Partage d’Audiences entre Audience Manager et Adobe Experience Platform {#aam-aep-audience-sharing}

>[!NOTE]
>
> Contactez votre représentant commercial Adobe pour déverrouiller l’accès à cette fonctionnalité.

## Aperçu {#overview}

La fonctionnalité de partage d’audiences entre Audience Manager et Adobe Experience Platform vous permet de partager vos caractéristiques et segments Audience Manager sur Adobe Experience Platform et vice versa. Vous avez besoin du connecteur [](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html) Audience Manager pour activer le partage des audiences entre Audience Manager et Adobe Experience Platform.

Vous pouvez utiliser les caractéristiques et segments d’Audience Manager dans Experience Platform pour ajouter des données d’Audience Manager à vos profils clients et bénéficier du service [de](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md)segmentation d’Experience Platform.

Dans Audience Manager, vous pouvez utiliser les segments de la plate-forme d’expérience pour les cas d’utilisation de Data Management Platform, tels que :
* Ajouter des données [](/help/using/overview/data-types-collected.md#third-party-data) tierces à vos segments ;
* [Modélisation algorithmique](/help/using/features/algorithmic-models/understanding-models.md);
* Activez vos segments vers des destinations qui ne sont pas encore prises en charge dans le catalogue [de](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)destinations de la plate-forme d’expérience.

De plus, vos segments de plateforme d’expérience sont partagés avec d’autres solutions Experience Cloud, via les services [](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html)principaux.

<br> 

Consultez le tableau ci-dessous pour une vue d’ensemble des cas d’utilisation du partage d’audiences :

| **Cas d’utilisation** | **Adobe Experience Platform** | **Audience Manager** | **Principaux services** |
---------|----------|---------|---------
| **Partage des Audiences** | <ul><li>Enrichir les profils clients avec les données Audience Manager</li><li>Utilisation des données d’Audience Manager dans la segmentation de la plateforme d’expérience</li></ul> | <ul><li>Ajouter de données tierces aux segments</li><li>Modélisation algorithmique</li><li>Activation vers d’autres destinations</li></ul> | Utilisez les segments de plateforme d’expérience dans d’autres solutions Experience Cloud, telles qu’Adobe Cible ou Analytics. |

<br> 

## Segments et caractéristiques d’Audience Manager dans Adobe Experience Platform {#aam-segments-traits-in-aep}

Vos caractéristiques et segments d’Audience Manager apparaissent dans la plateforme d’expérience en tant qu’Audiences **** dans le processus des segments. Pour plus d’informations sur vos segments et caractéristiques Audience Manager dans la plateforme d’expérience, voir :

* [Présentation du service de segmentation](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Guide de l’utilisateur du créateur de segments de plateforme d’expérience](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Connecteur Audience Manager](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

<br> 

## Segments Adobe Experience Platform dans Audience Manager {#aep-segments-in-aam}

Les segments que vous créez dans la plate-forme d’expérience apparaissent dans l’interface d’Audience Manager sous la forme de caractéristiques et de segments, avec les règles de composition suivantes :
* Caractéristique : La règle de caractéristiques est l’identifiant du segment de la plateforme d’expérience.
* Segment : Le segment est constitué de la caractéristique décrite ci-dessus.

### Caractéristiques {#aep-segments-as-aam-traits}

Audience Manager crée automatiquement un dossier de caractéristiques appelé Caractéristiques **de la plate-forme** d’expérience dans votre enregistrement de caractéristiques.

![Caractéristiques du tableau de bord de plateformes d’expérience](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Vous pouvez utiliser des caractéristiques créées automatiquement dans des segments à côté d’autres caractéristiques. Par exemple, vous pouvez mélanger des caractéristiques créées à partir de segments de la plateforme d’expérience avec des caractéristiques tierces acquises via [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Pour un exemple de caractéristique créée automatiquement à partir d’un segment de plateforme d’expérience, voir la capture d’écran ci-dessous :

![Caractéristique de la plateforme d’expérience](/help/using/integration/integration-aep/assets/aep-trait.png)


| Numéro d&#39;article | Nom | Description |
---------|----------|---------
| 1 | [!UICONTROL Trait Type] | Les caractéristiques créées à partir des segments de plateforme d’expérience sont créées sous la forme de caractéristiques intégrées dans Audience Manager. |
| 2 | [!UICONTROL Data Source] | Créé automatiquement. Toutes les caractéristiques et tous les segments créés automatiquement à partir des segments de la plate-forme d’expérience sont stockés dans la source de données **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | Le code d’intégration correspond à l’ID de segment dans la plate-forme d’expérience. |
| 4 | [!UICONTROL Trait Expression] | L&#39;expression de la caractéristique est `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Un segment créé automatiquement qui utilise cette caractéristique comme composition. |

<br> 

### Segments {#aep-segments-as-aam-segments}

Audience Manager crée automatiquement un dossier de segments intitulé Segments **de la plate-forme** d’expérience dans votre enregistrement de segments.

![Capture d&#39;écran du tableau de bord](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Pour un exemple de segment créé automatiquement à partir d’un segment de plateforme d’expérience, voir la capture d’écran ci-dessous :

![Capture d&#39;écran du segment](/help/using/integration/integration-aep/assets/aep-segment.png)

| Numéro d&#39;article | Nom | Description |
---------|----------|---------
| 1 | [!UICONTROL Integration Code] | Le code d’intégration correspond à l’ID de segment dans la plate-forme d’expérience. |
| 2 | [!UICONTROL Data Source] | Créé automatiquement. Toutes les caractéristiques et tous les segments créés automatiquement à partir des segments de la plate-forme d’expérience sont stockés dans la source de données **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** indique que les segments créés automatiquement suivent la stratégie de fusion définie dans la plate-forme d’expérience. |
| 4 | [!UICONTROL Segment Rule] | Le segment est constitué de la caractéristique décrite dans la section [](#aep-segments-as-aam-traits)Caractéristiques. |

## Comprendre les différences de population de segments entre Audience Manager et Experience Platform

Les nombres de population de segments peuvent varier selon vos segments Audience Manager et Experience Platform. Bien que les chiffres des segments pour des audiences similaires ou identiques soient proches, les différences de populations peuvent être dues :

* Les tâches de segmentation s’exécutent parfois. Audience Manager exécute une tâche de segmentation qui met à jour les nombres dans l’interface une fois par jour. Cette tâche s’aligne rarement avec les tâches de segmentation dans la plate-forme d’expérience.
* [Les règles](/help/using/features/profile-merge-rules/merge-rules-overview.md) de fusion de Profils dans Audience Manager et les stratégies [de](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) fusion dans la plate-forme d’expérience fonctionnent différemment et le graphique d’identité utilisé pour chacune d’elles varie. C’est pourquoi on s’attend à ce que certaines différences entre les populations de segments soient observées.

>[!MORELIKETHIS]
>
>* [Présentation du service de segmentation](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Guide de l’utilisateur du créateur de segments de plateforme d’expérience](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Connecteur Audience Manager](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)