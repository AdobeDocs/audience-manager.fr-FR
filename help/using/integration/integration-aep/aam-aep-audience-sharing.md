---
description: Découvrez comment activer le partage de données et comment les audiences sont partagées entre Audience Manager et Adobe Experience Platform
solution: Audience Manager
title: Partage de segments Experience Platform avec Audience Manager et d’autres solutions Experience Cloud
keywords: Partage d’audiences AEP, segments AEP, segments Platform, partage de segments, partage d’audiences, partage de segments, partage de segments AAM partage de segments AEP
feature: Experience Platform Integration
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: d21d0574ee0338dbd5e11c60e0d64042182aa18b
workflow-type: tm+mt
source-wordcount: '1953'
ht-degree: 1%

---

# Partage de segments Experience Platform avec Audience Manager et d’autres solutions Experience Cloud

## Présentation {#overview}

La fonctionnalité de partage d’audience entre Audience Manager et Adobe Experience Platform vous permet de partager vos caractéristiques et segments d’Audience Manager avec Adobe Experience Platform et les segments Experience Platform avec Audience Manager.

Vous avez besoin de [[!DNL Audience Manager source connector]](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html) et la variable [Audiences Experience Cloud](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html) destination dans Experience Platform pour activer le partage d’audiences entre Audience Manager et Adobe Experience Platform.

Vous pouvez utiliser les caractéristiques et segments d’Audience Manager dans Experience Platform pour ajouter des données d’Audience Manager à vos profils client et bénéficier de l’Experience Platform. [service de segmentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=en).

Dans Audience Manager, vous pouvez utiliser des segments Experience Platform pour les cas d’utilisation de Data Management Platform, tels que :
* Ajouter [données tierces](/help/using/overview/data-types-collected.md#third-party-data) à vos segments ;
* [Modélisation algorithmique](/help/using/features/algorithmic-models/understanding-models.md);
* Activation de vos segments vers des destinations qui ne sont pas encore prises en charge dans l’Experience Platform [destinations](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html).

De plus, vos segments Experience Platform sont partagés avec d’autres solutions Experience Cloud, via [Services principaux](https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html).

>[!IMPORTANT]
>
> * Vous avez besoin d’une licence d’Audience Manager pour activer les cas d’utilisation de Data Management Platform mentionnés ci-dessus.
> * You *ne doivent pas* une licence d’Audience Manager permettant de partager des segments Experience Platform avec Adobe Advertising Cloud, Adobe Target, Marketo et d’autres solutions Experience Cloud, via l’intégration des services principaux.

Consultez le tableau ci-dessous pour un aperçu des cas d’utilisation du partage d’audience :

| **Cas d’utilisation** | **Adobe Experience Platform** | **Audience Manager** | **Principaux services** |
|---------|----------|---------|---------|
| **Partage d&#39;audiences** | <ul><li>Enrichir les profils client avec les données d’Audience Manager</li><li>Utiliser les données d’Audience Manager dans la segmentation des Experience Platform</li></ul> | <ul><li>Ajout de données tierces aux segments</li><li>Modélisation algorithmique</li><li>Activation vers d’autres destinations</li></ul> | Utilisez des segments Experience Platform dans d’autres solutions Experience Cloud, telles qu’Adobe Target, Advertising Cloud ou Marketo. |

{style="table-layout:auto"}

## Audience Manager de segments et de caractéristiques dans Adobe Experience Platform {#aam-segments-traits-in-aep}

Les sections ci-dessous décrivent comment activer le partage de données d’Audience Manager à Experience Platform et comment utiliser les caractéristiques d’Audience Manager et les segments dans Experience Platform.

### Activation du partage de données entre les Audiences Manager et les Experience Platform {#enable-aam-to-aep-data}

Pour envoyer des segments et des caractéristiques d’Audience Manager à l’Experience Platform, vous devez configurer le connecteur source d’Audience Manager dans le catalogue de sources Experience Platform. Il s’agit d’un processus en libre-service qui ne nécessite pas l’intervention de l’assistance clientèle ou des équipes d’ingénierie d’Adobe. Pour configurer le connecteur source d’Audience Manager, lisez :

* [Source de l’Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)
* [Création d’une connexion source Adobe Audience Manager dans l’interface utilisateur](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/audience-manager.html?lang=en)

>[!IMPORTANT]
>
>Adobe encourage les clients à configurer la connexion sans sélectionner la variable **[!UICONTROL Select all segments]** et **[!UICONTROL Select all traits]** , comme illustré ci-dessous. L’ingestion de populations de segments d’Audience Manager de taille importante a un impact direct sur le nombre total de profils lorsque vous envoyez un segment d’Audience Manager pour la première fois à Platform à l’aide de la source d’Audience Manager. Cela signifie que la sélection de tous les segments peut potentiellement entraîner un nombre de profils supérieur à vos droits d’utilisation de licence.
>
>![Capture d&#39;écran montrant les options Sélectionner tous les segments et Sélectionner toutes les caractéristiques non cochées dans le workflow pour se connecter au connecteur source d&#39;Audience Manager.](/help/using/integration/integration-aep/assets/select-all-segments-traits-unchecked.png)

### Utilisation des caractéristiques et des segments d’Audience Manager dans Experience Platform {#use-aam-data-in-aep}

Une fois que vous avez configuré le connecteur source d’Audience Manager pour importer des caractéristiques et des segments d’Audience Manager, vos données d’Audience Manager apparaissent dans Experience Platform en tant que **Audiences** dans le processus de segmentation. Pour plus d’informations sur vos segments d’Audience Manager et vos caractéristiques dans Experience Platform, lisez :

* [Présentation de Segmentation Service](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
* [Guide d’utilisation du créateur de segments Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)

## Segments Adobe Experience Platform en Audience Manager {#aep-segments-in-aam}

Les sections ci-dessous décrivent comment activer le partage de données d’Experience Platform à Audience Manager et comment utiliser les segments Experience Platform dans Audience Manager.

### Activation du partage de données entre Experience Platform et Audiences Manager {#enable-aep-to-aam-data}

>[!IMPORTANT]
>
> Cette section décrit l’intégration du partage de segment hérité de Experience Platform à Audience Manager. Vous pouvez désormais configurer cette intégration sans l’aide des représentants des clients d’Adobe. Pour plus d’informations, consultez la section [Audiences Experience Cloud](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html) documentation de destination.

>[!NOTE]
>
> Contactez votre Adobe Customer Success Manager ou l’Assistance clientèle pour déverrouiller l’accès à cette fonctionnalité.

Pour envoyer des segments de l’Experience Platform vers l’Audience Manager, vous devez contacter l’assistance clientèle ou votre responsable du succès client. L’assistance clientèle et les équipes de gestion du service clientèle doivent déposer un ticket (voir le ticket de modèle AAM-52354) pour activer la connexion de Platform à l’Audience Manager.

Veillez à partager les plans relatifs aux données allant de Platform à l’Audience Manager, afin de vous assurer que la connexion est correctement configurée. Par exemple, si vous avez besoin que les données régionales soient partagées pour les segments envoyés à Adobe Target, ces informations doivent être communiquées dans le ticket. La connexion de partage de données entre l’Experience Platform et l’Audience Manager est configurée dans les six jours ouvrables suivant la demande en cours d’envoi.

### Utilisation des segments Experience Platform dans Audience Manager {#use-aep-data-in-aam}

Les segments que vous créez dans Experience Platform apparaissent dans l’interface d’Audience Manager sous la forme de signaux, de caractéristiques et de segments, avec les règles de composition suivantes :

* Signal : pour chaque segment Experience Platform, les signaux doivent s’afficher dans le formulaire. `segID = segment ID`.
* Caractéristique : la règle de caractéristique est l’identifiant du segment Experience Platform.
* Segment : le segment se compose de la caractéristique décrite ci-dessus.

### Signaux {#aep-segments-as-aam-signals}

Sélectionner **[!UICONTROL Audience Data > Signals > General Online Data]** et rechercher par `SegId` pour trouver les signaux provenant d’un Experience Platform. Vous pouvez utiliser cet écran à des fins de débogage pour vérifier si l’intégration entre Experience Platform et Audience Manager a été configurée correctement.

![Reportez-vous à la section Signaux Experience Platform en Audience Manager dans le tableau de bord Signaux](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Caractéristiques  {#aep-segments-as-aam-traits}

L’Audience Manager crée automatiquement un dossier de caractéristiques appelé **Caractéristiques Experience Platform** dans le stockage des caractéristiques.

![Caractéristiques du tableau de bord Experience Platform](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Vous pouvez utiliser des caractéristiques créées automatiquement dans des segments avec d’autres caractéristiques. Par exemple, vous pouvez mélanger les caractéristiques créées à partir de segments Experience Platform avec les caractéristiques tierces acquises au moyen de la variable [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Pour un exemple de caractéristique créée automatiquement à partir d’un segment Experience Platform, reportez-vous à la capture d’écran ci-dessous :

![Caractéristique de l’Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Numéro de l’élément | Nom | Description |
|---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | Les caractéristiques créées à partir de segments Experience Platform sont créées en tant que caractéristiques intégrées dans Audience Manager. |
| 2 | [!UICONTROL Data Source] | Créé automatiquement. Tous les segments et caractéristiques créés automatiquement à partir de segments Experience Platform sont stockés dans la source de données. **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | Le code d’intégration correspond à l’identifiant de segment dans Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | L’expression de caractéristique est `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Un segment créé automatiquement qui utilise cette caractéristique comme composition. |

{style="table-layout:auto"}

### Segments  {#aep-segments-as-aam-segments}

L’Audience Manager crée automatiquement un dossier de segments appelé **Segments Experience Platform** dans le stockage de votre segment.

![Capture d&#39;écran du tableau de bord](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Pour un exemple de segment créé automatiquement à partir d’un segment Experience Platform, reportez-vous à la capture d’écran ci-dessous :

![Capture d’écran du segment](/help/using/integration/integration-aep/assets/aep-segment.png)

| Numéro de l’élément | Nom | Description |
|---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | Le code d’intégration correspond à l’identifiant de segment dans Experience Platform. |
| 2 | [!UICONTROL Data Source] | Créé automatiquement. Tous les segments et caractéristiques créés automatiquement à partir de segments Experience Platform sont stockés dans la source de données. **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** indique que les segments créés automatiquement suivent la stratégie de fusion configurée dans Experience Platform. |
| 4 | [!UICONTROL Segment Rule] | Le segment se compose de la caractéristique décrite dans la variable [Section Caractéristiques](#aep-segments-as-aam-traits). |

{style="table-layout:auto"}

## Prise en charge du contrôle de l’exportation des données d’Audience Manager dans Experience Platform {#aam-data-export-control-in-aep}

Afin d’appliquer la conformité de l’utilisation des données dans Experience Platform, tous les jeux de données et champs applicables doivent être appropriés. [libellés d’utilisation des données](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html). En outre, [stratégies d’utilisation des données](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html) doit être activé pour des actions marketing spécifiques par rapport à ces étiquettes, comme indiqué par la variable [Cadre DULE (Data Usage Labeling and Enforcement)](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html#dule-framework).

Dans le processus de partage d’audience entre Audience Manager et Experience Platform, tous les contrôles des exportations de données appliqués aux segments d’Audience Manager sont traduits en libellés équivalents et actions marketing reconnus par la gouvernance des données des Experience Platform, et vice versa.

>[!NOTE]
>
>Pour plus d’informations sur les contrôles des exportations de données, reportez-vous à la section [Documentation sur les contrôles des exportations de données](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html).
>
>Ce document fournit une référence sur la manière dont des contrôles des exportations de données d’Audience Manager spécifiques sont associés à des libellés d’utilisation des données et à des actions marketing dans Platform.

### Contrôles des exportations de données vers les libellés d’utilisation des données

Le tableau suivant décrit la manière dont les contrôles des exportations de données spécifiques sont associés à des libellés d’utilisation de données reconnus :

| Contrôle de l’exportation des données | Libellé d’utilisation des données |
| --- | --- |
| Ne peut pas être utilisé avec des informations d’identification personnelle | C3 : les données ne peuvent pas être combinées ou utilisées d’une autre manière avec des informations directement identifiables. |
| Ne peut pas être utilisé pour le ciblage des publicités hors site | C5 : Les données ne peuvent pas être utilisées pour le ciblage intersite de contenu ou de publicités en fonction des intérêts |
| Ne peut pas être utilisé pour le ciblage des publicités sur site | C6 : Les données ne peuvent pas être utilisées pour le ciblage des publicités sur site |
| Ne peut pas être utilisé pour la personnalisation sur site | C7 : Les données ne peuvent pas être utilisées pour le ciblage de contenu sur site |

{style="table-layout:auto"}

### Contrôles des exportations de données vers les actions marketing

Le tableau suivant décrit la manière dont des libellés d’exportation de données spécifiques sont associés à des actions marketing reconnues :

| Étiquette d’exportation de données | Action marketing |
| --- | --- |
| Cette destination peut activer une combinaison avec des informations d’identification personnelle (PII). | Combiner avec les PII |
| Cette destination peut être utilisée pour le ciblage des publicités hors site. | Ciblage intersites |
| Cette destination peut être utilisée pour le ciblage des publicités sur site. | Publicité Onsite |
| Cette destination peut être utilisée pour la personnalisation des publicités sur site. | Personnalisation Onsite |

{style="table-layout:auto"}

## Comprendre les différences de population de segment entre Audience Manager et Experience Platform {#aep-aam-segment-population-differences}

Les nombres de population de segments peuvent varier entre vos segments d’Audience Manager et Experience Platform. Bien que les nombres de segments pour des audiences similaires ou identiques doivent être proches, les différences de populations peuvent être dues à des facteurs répertoriés ci-dessous.

### Évaluation des segments dans Experience Platform

L’Audience Manager met à jour les numéros des rapports dans l’interface une fois par jour. Le délai de cette mise à jour s’aligne rarement sur le moment de l’évaluation du segment dans Experience Platform.

### Différences entre les stratégies de fusion de profils et les stratégies de fusion

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) en Audience Manager et [[!UICONTROL Merge Policies]](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/merge-policies.html) dans Experience Platform fonctionnent différemment, et le graphique d’identités utilisé pour chacun d’eux varie. Pour cette raison, des différences entre les populations de segments sont attendues.

>[!NOTE]
>
> Lors du partage de segments de l’Experience Platform vers l’Audience Manager, votre organisation Platform [stratégie de fusion par défaut](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en#default-merge-policy) a la priorité sur [stratégie de fusion utilisée par le segment](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=en#merge-policies) partagé avec l’Audience Manager. Par exemple, si la stratégie de fusion du segment partagé autorise [Combinaison d’identifiants](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=en#configure), mais pas la stratégie de fusion par défaut de l’organisation, cela peut entraîner des différences de population entre Platform et l’Audience Manager.

### Composition de segment dans l’Experience Platform

L’intégration entre Adobe Experience Platform et l’Audience Manager partage un certain nombre de [espaces de noms d’identité](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#identity-types) pour tous les clients : ECID, IDFA, GAID, adresses électroniques hachées (EMAIL_LC_SHA256), AdCloud ID. Si vos segments Experience Platform utilisent l’une de ces identités comme identité principale pour les profils qualifiés, les profils sont comptabilisés dans les caractéristiques et les segments de l’Audience Manager.

>[!NOTE]
>
> Dans Experience Platform, les audiences dont les identités sont masquées à partir d’emails bruts n’apparaissent jamais dans l’Audience Manager.

Si, par exemple, vous disposez d’un segment Experience Platform &quot;Tous mes clients&quot; et que les profils qualifiés sont des identifiants CRM, ECID, IDFA, des adresses électroniques brutes et hachées, le segment correspondant dans l’Audience Manager inclut uniquement les profils masqués à l’extérieur de l’ECID, de l’IDFA et des adresses électroniques hachées. La population du segment en Audience Manager serait plus petite que celle en Experience Platform.

![Experience Platform à l’Audience Manager du partage de segments - composition de segments](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Présentation de Segmentation Service](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
>* [Guide d’utilisation du créateur de segments Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)
