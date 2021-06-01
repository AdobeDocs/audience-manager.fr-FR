---
description: Cet article décrit le partage des audiences entre Audience Manager et Adobe Experience Platform.
seo-description: Cet article décrit le partage des audiences entre Audience Manager et Adobe Experience Platform.
seo-title: Partage d’audiences entre Audience Manager et Adobe Experience Platform
solution: Audience Manager
title: Partage d’audiences entre Audience Manager et Adobe Experience Platform
keywords: Partage d’audiences AEP, segments AEP, segments Platform, partage de segments, partage d’audiences, partage de segments
feature: Intégration de Platform
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: 8dabdc08a58ece28162c70aefb392ff36f5fbc89
workflow-type: tm+mt
source-wordcount: '1465'
ht-degree: 3%

---

# Partage de segments Experience Platform avec Audience Manager et d’autres solutions Experience Cloud {#aam-aep-audience-sharing}

>[!NOTE]
>
> Contactez votre représentant commercial Adobe pour déverrouiller l’accès à cette fonctionnalité.

## Présentation {#overview}

La fonctionnalité de partage d’audience entre Audience Manager et Adobe Experience Platform vous permet de partager vos caractéristiques et segments d’Audience Manager avec Adobe Experience Platform et vice versa. Vous avez besoin de [[!DNL Audience Manager Connector]](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html) pour activer le partage d’audience entre l’Audience Manager et Adobe Experience Platform.

Vous pouvez utiliser les caractéristiques et les segments d’Audience Manager dans Experience Platform pour ajouter des données d’Audience Manager à vos profils client et bénéficier du [service de segmentation](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md) Experience Platform.

Dans Audience Manager, vous pouvez utiliser des segments Experience Platform pour les cas d’utilisation de Data Management Platform, tels que :
* Ajoutez des [données tierces](/help/using/overview/data-types-collected.md#third-party-data) à vos segments ;
* [Modélisation algorithmique](/help/using/features/algorithmic-models/understanding-models.md);
* Activez vos segments vers les destinations qui ne sont pas encore prises en charge dans le catalogue de destinations [Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html).

De plus, vos segments Experience Platform sont partagés avec d’autres solutions Experience Cloud, par l’intermédiaire des [services principaux](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html).

>[!IMPORTANT]
>
> * Vous avez besoin d’une licence d’Audience Manager pour activer les cas d’utilisation de Data Management Platform mentionnés ci-dessus.
> * Vous *n’avez pas besoin* d’une licence d’Audience Manager pour partager des segments Experience Platform avec Adobe Advertising Cloud, Adobe Target, Marketo et d’autres solutions Experience Cloud, via l’intégration des services principaux.


<br> 

Consultez le tableau ci-dessous pour un aperçu des cas d’utilisation du partage d’audience :

| **Cas d’utilisation** | **Adobe Experience Platform** | **Audience Manager** | **Principaux services** |
---------|----------|---------|---------
| **Partage d&#39;audiences** | <ul><li>Enrichir les profils client avec les données d’Audience Manager</li><li>Utiliser les données d’Audience Manager dans la segmentation des Experience Platform</li></ul> | <ul><li>Ajout de données tierces aux segments</li><li>Modélisation algorithmique</li><li>Activation vers d’autres destinations</li></ul> | Utilisez des segments Experience Platform dans d’autres solutions Experience Cloud, telles qu’Adobe Target, Advertising Cloud ou Marketo. |

<br> 

## Segments et caractéristiques d’Audience Manager dans Adobe Experience Platform {#aam-segments-traits-in-aep}

Vos caractéristiques et segments d’Audience Manager apparaissent dans Experience Platform sous la forme **Audiences** dans le processus de segments. Pour plus d’informations sur vos segments et caractéristiques d’Audience Manager dans Experience Platform, voir :

* [Présentation de Segmentation Service](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Guide d’utilisation du créateur de segments Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

<br> 

## Segments Adobe Experience Platform dans l’Audience Manager {#aep-segments-in-aam}

Les segments que vous créez dans Experience Platform apparaissent dans l’interface d’Audience Manager sous la forme de signaux, de caractéristiques et de segments, avec les règles de composition suivantes :

* Signal : Pour chaque segment Experience Platform, vous devriez voir des signaux sous la forme `segID = segment ID`.
* Caractéristique : La règle de caractéristique est l’identifiant du segment Experience Platform.
* Segment : Le segment se compose de la caractéristique décrite ci-dessus.

### Signaux {#aep-segments-as-aam-signals}

Sélectionnez **[!UICONTROL Audience Data > Signals > General Online Data]** et effectuez une recherche par `SegId` pour trouver les signaux provenant d’un Experience Platform. Vous pouvez utiliser cet écran à des fins de débogage pour vérifier si l’intégration entre Experience Platform et Audience Manager a été configurée correctement.

![Reportez-vous à la section Signaux Experience Platform en Audience Manager dans le tableau de bord Signaux](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Caractéristiques {#aep-segments-as-aam-traits}

Audience Manager crée automatiquement un dossier de caractéristiques appelé **Caractéristiques Experience Platform** dans votre stockage de caractéristiques.

![Caractéristiques du tableau de bord Experience Platform](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Vous pouvez utiliser des caractéristiques créées automatiquement dans des segments avec d’autres caractéristiques. Par exemple, vous pouvez mélanger les caractéristiques créées à partir de segments Experience Platform avec des caractéristiques tierces acquises par le biais de l’Audience Marketplace [](/help/using/features/audience-marketplace/audience-marketplace.md).

Pour un exemple de caractéristique créée automatiquement à partir d’un segment Experience Platform, reportez-vous à la capture d’écran ci-dessous :

![Caractéristique de l’Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Numéro de l’élément | Nom | Description |
---------|----------|---------
| 1 | [!UICONTROL Trait Type] | Les caractéristiques créées à partir de segments Experience Platform sont créées en tant que caractéristiques intégrées dans Audience Manager. |
| 2 | [!UICONTROL Data Source] | Créé automatiquement. Toutes les caractéristiques et tous les segments créés automatiquement à partir des segments Experience Platform sont stockés dans la source de données **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | Le code d’intégration correspond à l’identifiant de segment dans Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | L’expression de caractéristique est `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Un segment créé automatiquement qui utilise cette caractéristique comme composition. |

<br> 

### Segments {#aep-segments-as-aam-segments}

Audience Manager crée automatiquement un dossier de segments appelé **Segments Experience Platform** dans votre stockage de segments.

![Capture d&#39;écran du tableau de bord](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Pour un exemple de segment créé automatiquement à partir d’un segment Experience Platform, reportez-vous à la capture d’écran ci-dessous :

![Capture d’écran du segment](/help/using/integration/integration-aep/assets/aep-segment.png)

| Numéro de l’élément | Nom | Description |
---------|----------|---------
| 3 | [!UICONTROL Integration Code] | Le code d’intégration correspond à l’identifiant de segment dans Experience Platform. |
| 2 | [!UICONTROL Data Source] | Créé automatiquement. Toutes les caractéristiques et tous les segments créés automatiquement à partir des segments Experience Platform sont stockés dans la source de données **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** indique que les segments créés automatiquement suivent la stratégie de fusion configurée dans Experience Platform. |
| 4 | [!UICONTROL Segment Rule] | Le segment se compose de la caractéristique décrite dans la [section Caractéristiques](#aep-segments-as-aam-traits). |

## Prise en charge du contrôle de l’exportation des données d’Audience Manager dans Experience Platform {#aam-data-export-control-in-aep}

Afin d’appliquer la conformité de l’utilisation des données dans Experience Platform, tous les jeux de données et champs applicables doivent recevoir les [libellés d’utilisation des données](https://docs.adobe.com/content/help/en/experience-platform/data-governance/labels/overview.html) appropriés. En outre, les [stratégies d’utilisation des données](https://docs.adobe.com/content/help/en/experience-platform/data-governance/policies/overview.html) doivent être activées pour des actions marketing spécifiques par rapport à ces étiquettes, comme indiqué par la [structure Data Usage Labeling and Enforcement (DULE)](https://docs.adobe.com/content/help/en/experience-platform/data-governance/home.html#dule-framework).

Dans le processus de partage d’audience entre Audience Manager et Experience Platform, tous les contrôles des exportations de données appliqués aux segments d’Audience Manager sont traduits en libellés équivalents et actions marketing reconnus par la gouvernance des données des Experience Platform, et vice versa.

>[!NOTE]
>
>Pour plus d’informations sur les contrôles des exportations de données, reportez-vous à la [documentation sur les contrôles des exportations de données](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html).
>
>Ce document fournit une référence sur la manière dont des contrôles des exportations de données d’Audience Manager spécifiques sont associés à des libellés d’utilisation des données et à des actions marketing dans Platform.

### Contrôles des exportations de données vers les libellés d’utilisation des données

Le tableau suivant décrit la manière dont les contrôles des exportations de données spécifiques sont associés à des libellés d’utilisation de données reconnus :

| Contrôle de l’exportation des données | Libellé d’utilisation des données |
| --- | --- |
| Ne peut pas être utilisé avec des informations d’identification personnelle | C3 : Les données ne peuvent pas être combinées ou utilisées d’une autre manière avec des informations directement identifiables. |
| Ne peut pas être utilisé pour le ciblage des publicités hors site | C5 : Les données ne peuvent pas être utilisées pour le ciblage intersite de contenu ou de publicités en fonction des intérêts |
| Ne peut pas être utilisé pour le ciblage des publicités sur site | C6 : Les données ne peuvent pas être utilisées pour le ciblage des publicités sur site |
| Ne peut pas être utilisé pour la personnalisation sur site | C7 : Les données ne peuvent pas être utilisées pour le ciblage de contenu sur site |

### Contrôles des exportations de données vers les actions marketing

Le tableau suivant décrit la manière dont des libellés d’exportation de données spécifiques sont associés à des actions marketing reconnues :

| Étiquette d’exportation de données | Action marketing |
| --- | --- |
| Cette destination peut activer une combinaison avec des informations d’identification personnelle (PII). | Combiner avec les PII |
| Cette destination peut être utilisée pour le ciblage des publicités hors site. | Ciblage intersites |
| Cette destination peut être utilisée pour le ciblage des publicités sur site. | Publicité Onsite |
| Cette destination peut être utilisée pour la personnalisation des publicités sur site. | Personnalisation Onsite |

## Comprendre les différences de population de segment entre l’Audience Manager et l’Experience Platform {#aep-aam-segment-population-differences}

Les nombres de population de segments peuvent varier entre vos segments d’Audience Manager et Experience Platform. Bien que les numéros de segments pour des audiences similaires ou identiques doivent être proches, les différences de populations peuvent être dues à des facteurs répertoriés ci-dessous.

### Évaluation des segments dans Experience Platform

L’Audience Manager met à jour les numéros des rapports dans l’interface une fois par jour.   Le délai de cette mise à jour s’aligne rarement sur le moment de l’évaluation du segment dans Experience Platform.

### Différences entre les stratégies de fusion de profils et les stratégies de fusion

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) dans l’Audience Manager et  [[!UICONTROL Merge Policies]](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) dans l’Experience Platform fonctionnent différemment, et le graphique d’identités utilisé pour chacun varie. Pour cette raison, des différences entre les populations de segments sont attendues.

### Composition de segment dans l’Experience Platform

L’intégration entre Adobe Experience Platform et l’Audience Manager partage un certain nombre d’ [espaces de noms d’identité](https://docs.adobe.com/content/help/en/experience-platform/identity/namespaces.html#identity-types) standard pour tous les clients : ECID, IDFA, GAID, adresses électroniques hachées (EMAIL_LC_SHA256), AdCloud ID. Si vos segments Experience Platform utilisent l’une d’elles comme identité Principale pour les profils qualifiés, les profils sont comptabilisés dans les caractéristiques et les segments d’Audience Manager.

>[!NOTE]
>
> Dans Experience Platform, les audiences dont les identités sont masquées à partir d’emails bruts n’apparaissent jamais dans l’Audience Manager.

Par exemple, si vous aviez un segment Experience Platform &quot;Tous mes clients&quot; et que les profils qualifiés seraient des identifiants CRM, ECID, IDFA, des adresses électroniques brutes et hachées, le segment correspondant dans l’Audience Manager inclurait uniquement les profils masqués à l’extérieur de l’ECID, de l’IDFA et des adresses électroniques hachées. La population du segment en Audience Manager serait plus petite que celle en Experience Platform.

![Experience Platform à l’Audience Manager du partage de segments - composition de segments](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Présentation de Segmentation Service](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Guide d’utilisation du créateur de segments Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

