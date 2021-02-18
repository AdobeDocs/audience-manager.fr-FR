---
description: Cet article décrit comment les audiences sont partagées entre Audience Manager et Adobe Experience Platform.
seo-description: Cet article décrit comment les audiences sont partagées entre Audience Manager et Adobe Experience Platform.
seo-title: Partage d’audiences entre Audience Manager et Adobe Experience Platform
solution: Audience Manager
title: Partage d’audiences entre Audience Manager et Adobe Experience Platform
keywords: Partage des audiences AEP, segments AEP, segments de plateforme, partage de segments, partage d’audiences, partage de segments
feature: Integration with Platform
translation-type: tm+mt
source-git-commit: 62938e95fa9eed3e747fa4dabf8695c5dbefde17
workflow-type: tm+mt
source-wordcount: '1504'
ht-degree: 2%

---


# Partage de segments Experience Platform avec l’Audience Manager et d’autres solutions Experience Cloud {#aam-aep-audience-sharing}

>[!NOTE]
>
> Contactez votre représentant commercial d’Adobe pour déverrouiller l’accès à cette fonctionnalité.

## Présentation {#overview}

La fonctionnalité de partage d&#39;audiences entre l&#39;Audience Manager et Adobe Experience Platform vous permet de partager vos caractéristiques d&#39;Audience Manager et segments avec Adobe Experience Platform et vice versa. Vous avez besoin de [[!DNL Audience Manager Connector]](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html) pour activer le partage des audiences entre l’Audience Manager et Adobe Experience Platform.

Vous pouvez utiliser les caractéristiques et les segments d’Audience Manager dans l’Experience Platform pour ajouter des données d’Audience Manager à vos profils clients et pour bénéficier du service de segmentation [Experience Platform](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md).

Dans l’Audience Manager, vous pouvez utiliser des segments Experience Platform pour les cas d’utilisation de la plateforme de Data Management, tels que :
* Ajouter [des données tierces](/help/using/overview/data-types-collected.md#third-party-data) à vos segments ;
* [Modélisation algorithmique](/help/using/features/algorithmic-models/understanding-models.md);
* Activez vos segments vers des destinations qui ne sont pas encore prises en charge dans le catalogue de destinations [Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html).

De plus, vos segments Experience Platform sont partagés avec d’autres solutions Experience Cloud, via [les services principaux](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html).

>[!IMPORTANT]
>
> * Vous avez besoin d’une licence d’Audience Manager pour activer les cas d’utilisation de Data Management Platform mentionnés ci-dessus.
> * Vous *n’avez pas besoin* d’une licence d’Audience Manager pour partager des segments Experience Platform avec Adobe Advertising Cloud, Adobe Target, Marketo et d’autres solutions Experience Cloud, via l’intégration des services principaux.


<br> 

Consultez le tableau ci-dessous pour une vue d’ensemble des cas d’utilisation du partage d’audiences :

| **Cas d’utilisation** | **Adobe Experience Platform** | **Audience Manager** | **Principaux services** |
---------|----------|---------|---------
| **Partage des Audiences** | <ul><li>Enrichir les profils clients avec des données d&#39;Audience Manager</li><li>Utiliser les données d’Audience Manager dans la segmentation des Experience Platform</li></ul> | <ul><li>Ajouter des données tierces aux segments</li><li>Modélisation algorithmique</li><li>Activation vers d’autres destinations</li></ul> | Utilisez des segments Experience Platform dans d’autres solutions Experience Cloud, telles que Adobe Target, Advertising Cloud ou Marketo. |

<br> 

## Segments et caractéristiques des Audiences Manager dans Adobe Experience Platform {#aam-segments-traits-in-aep}

Vos caractéristiques et segments d’Audience Manager s’affichent dans l’Experience Platform sous la forme **Audiences** dans le processus des segments. Pour plus d’informations sur les segments et caractéristiques de vos Audiences Manager dans l’Experience Platform, voir :

* [Présentation du service de segmentation](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Guide de l’utilisateur du créateur de segments Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

<br> 

## Segments Adobe Experience Platform dans l’Audience Manager {#aep-segments-in-aam}

Les segments que vous créez dans l’Experience Platform apparaissent dans l’interface d’Audience Manager sous la forme de signaux, de caractéristiques et de segments, avec les règles de composition suivantes :

* Signal : Pour chaque segment d’Experience Platform, vous devriez voir les signaux sous la forme `segID = segment ID`.
* Caractéristique : La règle de caractéristiques est l’identifiant du segment Experience Platform.
* Segment : Le segment est constitué de la caractéristique décrite ci-dessus.

### Signaux {#aep-segments-as-aam-signals}

Sélectionnez **[!UICONTROL Audience Data > Signals > General Online Data]** et recherchez `SegId` pour trouver les signaux provenant de l&#39;Experience Platform. Vous pouvez utiliser cet écran à des fins de débogage pour vérifier si l’intégration entre l’Experience Platform et l’Audience Manager a été correctement configurée.

![Voir Signaux Experience Platform en Audience Manager dans le tableau de bord Signaux](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Caractéristiques {#aep-segments-as-aam-traits}

L’Audience Manager crée automatiquement un dossier de caractéristiques intitulé **Caractéristiques de l’Experience Platform** dans votre enregistrement de caractéristiques.

![Caractéristiques du tableau de bord Experience Platform](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Vous pouvez utiliser des caractéristiques créées automatiquement dans des segments à côté d’autres caractéristiques. Par exemple, vous pouvez mélanger des caractéristiques créées à partir de segments Experience Platform avec des caractéristiques tierces acquises par l&#39;Audience Marketplace [](/help/using/features/audience-marketplace/audience-marketplace.md).

Pour un exemple de caractéristique créée automatiquement à partir d’un segment d’Experience Platform, voir la capture d’écran ci-dessous :

![Caractéristique de l&#39;Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Numéro d&#39;article | Nom | Description |
---------|----------|---------
| 1 | [!UICONTROL Trait Type] | Les caractéristiques créées à partir de segments Experience Platform sont créées en tant que caractéristiques intégrées dans l’Audience Manager. |
| 2 | [!UICONTROL Data Source] | Créé automatiquement. Toutes les caractéristiques et tous les segments créés automatiquement à partir de segments Experience Platform sont stockés dans la source de données **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | Le code d’intégration correspond à l’ID de segment dans l’Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | L’expression de caractéristiques est `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Un segment créé automatiquement qui utilise cette caractéristique comme composition. |

<br> 

### Segments {#aep-segments-as-aam-segments}

L’Audience Manager crée automatiquement un dossier de segments intitulé **Segments Experience Platform** dans votre enregistrement de segments.

![Capture d&#39;écran du tableau de bord](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Pour un exemple de segment créé automatiquement à partir d’un segment Experience Platform, voir la capture d’écran ci-dessous :

![Capture d&#39;écran du segment](/help/using/integration/integration-aep/assets/aep-segment.png)

| Numéro d&#39;article | Nom | Description |
---------|----------|---------
| 1 | [!UICONTROL Integration Code] | Le code d’intégration correspond à l’ID de segment dans l’Experience Platform. |
| 2 | [!UICONTROL Data Source] | Créé automatiquement. Toutes les caractéristiques et tous les segments créés automatiquement à partir de segments Experience Platform sont stockés dans la source de données **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 1 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** indique que les segments créés automatiquement suivent la stratégie de fusion définie dans l’Experience Platform. |
| 4 | [!UICONTROL Segment Rule] | Le segment est constitué de la caractéristique décrite dans la section [Caractéristiques](#aep-segments-as-aam-traits). |

## Prise en charge du contrôle des exportations de données d&#39;Audience Manager dans l&#39;Experience Platform {#aam-data-export-control-in-aep}

Afin d&#39;assurer la conformité de l&#39;utilisation des données dans l&#39;Experience Platform, tous les jeux de données et champs applicables doivent recevoir des [étiquettes d&#39;utilisation des données](https://docs.adobe.com/content/help/en/experience-platform/data-governance/labels/overview.html) appropriées. En outre, [les stratégies d&#39;utilisation des données](https://docs.adobe.com/content/help/en/experience-platform/data-governance/policies/overview.html) doivent être activées pour des actions marketing spécifiques par rapport à ces étiquettes, comme indiqué par la [structure d&#39;étiquetage et d&#39;application de l&#39;utilisation des données (DULE)](https://docs.adobe.com/content/help/en/experience-platform/data-governance/home.html#dule-framework).

Dans le processus de partage des audiences entre l’Audience Manager et l’Experience Platform, tous les contrôles d’exportation de données appliqués aux segments d’Audience Manager sont traduits en étiquettes équivalentes et actions marketing reconnues par la gouvernance des données Experience Platform, et vice versa.

>[!NOTE]
>
>Pour plus d&#39;informations sur les contrôles des exportations de données, consultez la [documentation sur les contrôles des exportations de données](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html).
>
>Ce document fournit une référence sur la manière dont des contrôles d’exportation de données d’Audience Manager spécifiques correspondent aux étiquettes d’utilisation des données et aux actions marketing dans la plateforme.

### Contrôles d’exportation des données vers les étiquettes d’utilisation des données

Le tableau suivant décrit comment des contrôles d’exportation de données spécifiques correspondent à des étiquettes d’utilisation de données reconnues :

| Contrôle des exportations de données | Libellé d’utilisation des données |
| --- | --- |
| Ne peut pas être utilisé avec des informations d&#39;identification personnelle | C3 : Les données ne peuvent pas être combinées ou utilisées autrement avec des informations directement identifiables. |
| Ne peut pas être utilisé pour le ciblage des publicités hors site | C5 : Les données ne peuvent pas être utilisées pour le ciblage intersite du contenu ou des publicités basé sur l’intérêt |
| Impossible d&#39;utiliser le ciblage publicitaire sur site | C6 : Les données ne peuvent pas être utilisées pour le ciblage publicitaire sur site |
| Ne peut pas être utilisé pour la personnalisation sur site | C7 : Les données ne peuvent pas être utilisées pour le ciblage sur site du contenu. |

### Contrôles de l’exportation des données vers les actions marketing

Le tableau suivant décrit comment des étiquettes d’exportation de données spécifiques correspondent à des actions marketing reconnues :

| Étiquette d’exportation de données | Action marketing |
| --- | --- |
| Cette destination peut permettre une combinaison avec des informations d’identification personnelle | Combiner avec les informations d’identification personnelle |
| Cette destination peut être utilisée pour le ciblage publicitaire hors site. | Ciblage sur plusieurs sites |
| Cette destination peut être utilisée pour le ciblage publicitaire sur site. | Publicité sur site |
| Cette destination peut être utilisée pour la personnalisation des publicités sur site | Personnalisation sur site |

## Comprendre les différences de population des segments entre l&#39;Audience Manager et l&#39;Experience Platform {#aep-aam-segment-population-differences}

Les nombres de population de segments peuvent varier selon vos segments d’Audience Manager et d’Experience Platform. Bien que les chiffres des segments pour des audiences similaires ou identiques soient proches, les différences dans les populations peuvent être dues à des facteurs énumérés ci-dessous.

### Évaluation des segments dans l’Experience Platform

L’Audience Manager met à jour les numéros de rapports dans l’interface une fois par jour.   Le timing de cette mise à jour s’aligne rarement avec le moment de l’évaluation du segment dans l’Experience Platform.

### Différences entre les règles de fusion de Profils et les stratégies de fusion

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) en Audience Manager et  [[!UICONTROL Merge Policies]](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) en Experience Platform travaillent différemment, et le graphique d&#39;identité utilisé pour chacun d&#39;eux varie. C’est pourquoi on s’attend à ce que certaines différences entre les populations de segments soient observées.

### Composition de segments dans l’Experience Platform

L&#39;intégration entre Adobe Experience Platform et l&#39;Audience Manager partage un certain nombre d&#39;espaces de nommage d&#39;identité [standard](https://docs.adobe.com/content/help/en/experience-platform/identity/namespaces.html#identity-types) pour tous les clients : ECID, IDFA, GAID, adresses électroniques hachées (EMAIL_LC_SHA256), AdCloud ID. Si vos segments d’Experience Platform utilisent l’un d’eux comme identité Principale pour les profils qualifiés, les profils sont comptabilisés dans les caractéristiques et les segments d’Audience Manager.

En outre, l’Audience Manager peut enregistrer les réalisations entrantes pour tout espace de nommage d’identité personnalisé que vous utilisez dans les segments Experience Platform si :
* l&#39;identité est marquée comme Principale *et*
* vous disposez déjà d’une source de données inter-périphériques correspondante en Audience Manager.

>[!NOTE]
>
> Les Audiences en Experience Platform avec des identités effacées des courriels bruts n&#39;apparaissent jamais en Audience Manager.

Par exemple, si vous aviez un segment Experience Platform &quot;Tous mes clients&quot; et que les profils qualifiés seraient des identifiants de gestion de la relation client, ECID, IDFA, des adresses électroniques brutes et hachées, le segment correspondant dans l’Audience Manager inclurait uniquement les profils des identifiants de gestion de la relation client, ECID, IDFA et les adresses électroniques hachées. La population de segments en Audience Manager serait plus petite que celle en Experience Platform.

![Experience Platform au partage des segments d&#39;Audience Manager - composition des segments](/help/using/integration/integration-aep/assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Présentation du service de segmentation](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Guide de l’utilisateur du créateur de segments Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)