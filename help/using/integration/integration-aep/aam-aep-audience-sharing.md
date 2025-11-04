---
description: Découvrez comment activer le partage de données et comment les audiences sont partagées entre Audience Manager et Adobe Experience Platform
solution: Audience Manager
title: Partage de segments Experience Platform avec Audience Manager et d’autres solutions Experience Cloud
keywords: partage d’audiences AEP, segments AEP, segments Platform, partage de segments, partage d’audiences, partage de segments, partage de segments, partage de segments AAM AEP
feature: Experience Platform Integration
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '1799'
ht-degree: 1%

---

# Partage de segments Experience Platform avec Audience Manager et d’autres solutions Experience Cloud

## Présentation {#overview}

La fonctionnalité de partage d’audiences entre Audience Manager et Adobe Experience Platform vous permet de partager vos caractéristiques et segments Audience Manager avec Adobe Experience Platform et vos segments Experience Platform avec Audience Manager.

Vous avez besoin de la [[!DNL Audience Manager source connector]](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=fr) et de la destination [Audiences Experience Cloud](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html?lang=fr) dans Experience Platform pour activer le partage d’audience entre Audience Manager et Adobe Experience Platform.

Vous pouvez utiliser les caractéristiques et segments Audience Manager dans Experience Platform pour ajouter des données Audience Manager à vos profils clients et bénéficier du service de segmentation d’Experience Platform [segmentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=fr).

Dans Audience Manager, vous pouvez utiliser les segments Experience Platform pour les cas d’utilisation de la plateforme de gestion des données, tels que :

* Ajouter des [données tierces](/help/using/overview/data-types-collected.md#third-party-data) à vos segments ;
* [modélisation algorithmique](/help/using/features/algorithmic-models/understanding-models.md);
* Activez vos segments vers des destinations qui ne sont pas encore prises en charge dans le [catalogue des destinations](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html?lang=fr) d’Experience Platform.

En outre, vos segments Experience Platform sont partagés avec d’autres solutions Experience Cloud, via [Core Services](https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html?lang=fr).

>[!IMPORTANT]
>
> * Vous avez besoin d’une licence Audience Manager pour activer les cas pratiques de la plateforme de gestion des données mentionnés ci-dessus.
> * Vous *pas besoin* d’une licence Audience Manager pour partager des segments Experience Platform avec Adobe Advertising Cloud, Adobe Target, Marketo et d’autres solutions Experience Cloud, via l’intégration des services principaux.

Consultez le tableau ci-dessous pour obtenir un aperçu des cas d’utilisation du partage d’audience :

| **Cas d’utilisation** | **Adobe Experience Platform** | **Audience Manager** | **Principaux services** |
|---------|----------|---------|---------|
| **Partage d’audiences** | <ul><li>Enrichissement des profils clients avec des données Audience Manager</li><li>Utilisation des données Audience Manager dans la segmentation Experience Platform</li></ul> | <ul><li>Ajout de données tierces aux segments</li><li>Modélisation algorithmique</li><li>Activation vers des destinations supplémentaires</li></ul> | Utilisez les segments Experience Platform dans d’autres solutions Experience Cloud, telles qu’Adobe Target, Advertising Cloud ou Marketo. |

{style="table-layout:auto"}

## Segments et caractéristiques Audience Manager dans Adobe Experience Platform {#aam-segments-traits-in-aep}

Les sections ci-dessous décrivent comment activer le partage de données d’Audience Manager vers Experience Platform et comment utiliser les caractéristiques et segments Audience Manager dans Experience Platform.

### Activer le partage de données d’Audience Manager vers Experience Platform {#enable-aam-to-aep-data}

Pour envoyer des segments et des caractéristiques d’Audience Manager vers Experience Platform, vous devez configurer le connecteur source Audience Manager dans le catalogue des sources Experience Platform. Il s’agit d’un workflow en libre-service qui ne nécessite pas l’implication de l’assistance clientèle ou des équipes d’ingénierie Adobe. Pour configurer le connecteur source Audience Manager, lisez :

* [Source Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=fr)
* [Créer une connexion source Adobe Audience Manager dans l’interface utilisateur](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/audience-manager.html?lang=fr)

>[!IMPORTANT]
>
>Adobe incite les clients à configurer la connexion sans sélectionner les options **[!UICONTROL Select all segments]** et **[!UICONTROL Select all traits]**, comme illustré ci-dessous. L’ingestion de populations de segments Audience Manager importantes a un impact direct sur le nombre total de profils lorsque vous envoyez un segment Audience Manager pour la première fois à Platform à l’aide de la source Audience Manager. Cela signifie que la sélection de tous les segments peut potentiellement entraîner un nombre de profils supérieur à vos droits d’utilisation de licence.
>
>![Capture d’écran affichant les options Sélectionner tous les segments et Sélectionner toutes les caractéristiques décochées dans le workflow pour se connecter au connecteur source Audience Manager.](/help/using/integration/integration-aep/assets/select-all-segments-traits-unchecked.png)

### Utilisation des caractéristiques et des segments Audience Manager dans Experience Platform {#use-aam-data-in-aep}

Une fois que vous avez configuré le connecteur source Audience Manager pour importer des caractéristiques et des segments depuis Audience Manager, vos données Audience Manager apparaissent dans Experience Platform sous la forme **audiences** dans le workflow de segments. Pour plus d’informations sur vos segments et caractéristiques Audience Manager dans Experience Platform, lisez :

* [Présentation de Segmentation Service](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=fr#audiences)
* [Guide de l’utilisateur du créateur de segments d’Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=fr#audiences)

## Segments Adobe Experience Platform dans Audience Manager {#aep-segments-in-aam}

Les sections ci-dessous décrivent comment activer le partage de données d’Experience Platform vers Audience Manager et comment utiliser les segments Experience Platform dans Audience Manager.

### Activer le partage de données d’Experience Platform vers Audience Manager {#enable-aep-to-aam-data}

>[!IMPORTANT]
>
> Cette section décrit l’ancienne intégration du partage de segments d’Experience Platform vers Audience Manager. Vous pouvez désormais configurer cette intégration sans assistance de la part des représentants du client Adobe. Pour plus d’informations, consultez la documentation sur la destination [Audiences Experience Cloud](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html?lang=fr).

>[!NOTE]
>
> Contactez votre responsable du succès client ou l’assistance clientèle d’Adobe pour déverrouiller l’accès à cette fonctionnalité.

Pour envoyer des segments d’Experience Platform vers Audience Manager, vous devez contacter l’assistance clientèle ou votre responsable du succès client. Les équipes d’assistance clientèle et de gestion du service clientèle doivent enregistrer un ticket (voir le modèle de ticket AAM-52354) pour activer la connexion de Platform à Audience Manager.

Veillez à partager les plans pour les données allant de Platform à Audience Manager, afin de vous assurer que la connexion est correctement configurée. Par exemple, si vous avez besoin que des données régionales soient partagées pour les segments envoyés à Adobe Target, ces informations doivent être communiquées dans le ticket. La connexion de partage de données entre Experience Platform et Audience Manager est établie dans les six jours ouvrables suivant l’envoi de la demande.

### Utilisation des segments Experience Platform dans Audience Manager {#use-aep-data-in-aam}

Les segments que vous créez dans Experience Platform apparaissent dans votre interface Audience Manager sous la forme de signaux, caractéristiques et segments, avec les règles de composition suivantes :

* Signal : pour chaque segment Experience Platform, vous devriez voir des signaux dans le formulaire `segID = segment ID`.
* Caractéristique : la règle de caractéristique est l’identifiant du segment Experience Platform.
* Segment : le segment est constitué de la caractéristique décrite ci-dessus.

### Signaux {#aep-segments-as-aam-signals}

Sélectionnez **[!UICONTROL Audience Data > Signals > General Online Data]** et effectuez une recherche par `SegId` pour rechercher les signaux provenant d’Experience Platform. Vous pouvez utiliser cet écran à des fins de débogage, pour vérifier si l&#39;intégration entre Experience Platform et Audience Manager a été correctement configurée.

![Voir Signaux Experience Platform dans Audience Manager dans le tableau de bord Signaux](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Caractéristiques {#aep-segments-as-aam-traits}

Audience Manager crée automatiquement un dossier de caractéristiques appelé **Caractéristiques Experience Platform** dans votre stockage de caractéristiques.

![Caractéristiques du tableau de bord Experience Platform](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Vous pouvez utiliser les caractéristiques créées automatiquement dans les segments avec d’autres caractéristiques. Par exemple, vous pouvez combiner des caractéristiques créées à partir de segments Experience Platform avec des caractéristiques tierces acquises via [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Pour un exemple de caractéristique créée automatiquement à partir d’un segment Experience Platform, reportez-vous à la capture d’écran ci-dessous :

![Caractéristique d’Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Numéro d&#39;article | Nom | Description |
|---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | Les caractéristiques créées à partir des segments Experience Platform sont créées en tant que caractéristiques intégrées dans Audience Manager. |
| 2 | [!UICONTROL Data Source] | Création automatique. Toutes les caractéristiques et tous les segments créés automatiquement à partir des segments Experience Platform sont stockés dans le **[!UICONTROL Adobe Experience Platform Audience Sharing]** de source de données. |
| 3 | [!UICONTROL Integration Code] | Le code d’intégration correspond à l’identifiant de segment dans Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | L’expression de la caractéristique est `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Segment créé automatiquement qui utilise cette caractéristique comme composition. |

{style="table-layout:auto"}

### Segments {#aep-segments-as-aam-segments}

Audience Manager crée automatiquement un dossier de segments appelé **Segments Experience Platform** dans votre stockage de segments.

![Capture d’écran du tableau de bord](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Pour obtenir un exemple de segment créé automatiquement à partir d’un segment Experience Platform, reportez-vous à la capture d’écran ci-dessous :

![Capture d’écran du segment](/help/using/integration/integration-aep/assets/aep-segment.png)

| Numéro d&#39;article | Nom | Description |
|---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | Le code d’intégration correspond à l’identifiant de segment dans Experience Platform. |
| 2 | [!UICONTROL Data Source] | Création automatique. Toutes les caractéristiques et tous les segments créés automatiquement à partir des segments Experience Platform sont stockés dans le **[!DNL Adobe Experience Platform Audience Sharing]** de source de données. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** indique que les segments créés automatiquement suivent la politique de fusion configurée dans Experience Platform. |
| 4 | [!UICONTROL Segment Rule] | Le segment est constitué de la caractéristique décrite dans la [section Caractéristiques](#aep-segments-as-aam-traits). |

{style="table-layout:auto"}

## Prise en charge du contrôle de l’exportation des données Audience Manager dans Experience Platform {#aam-data-export-control-in-aep}

Afin d’appliquer la conformité d’utilisation des données dans Experience Platform, tous les jeux de données et champs applicables doivent recevoir les [&#x200B; libellés d’utilisation des données](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html?lang=fr) appropriés. En outre, les [politiques d’utilisation des données](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=fr) doivent être activées pour des actions marketing spécifiques par rapport à ces libellés, comme indiqué par le cadre [DULE (Data Usage Labeling and Enforcement)](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=fr#dule-framework).

Dans le processus de partage d’audiences entre Audience Manager et Experience Platform, tous les contrôles d’exportation de données appliqués aux segments Audience Manager sont traduits en libellés équivalents et en actions marketing reconnues par la gouvernance des données d’Experience Platform, et vice versa.

>[!NOTE]
>
>Pour des informations plus générales sur les contrôles d’exportation de données, reportez-vous à la documentation [&#x200B; Contrôles d’exportation de données &#x200B;](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html?lang=fr).
>
>Ce document fournit une référence sur la manière dont des contrôles d’exportation de données Audience Manager spécifiques se mappent aux libellés d’utilisation des données et aux actions marketing dans Platform.

### Contrôles d’exportation de données vers des libellés d’utilisation des données

Le tableau suivant décrit comment des contrôles d’exportation de données spécifiques se mappent à des libellés d’utilisation de données reconnus :

| Contrôle d’exportation des données | Libellé d’utilisation des données |
| --- | --- |
| Ne peut pas être utilisé avec des informations d’identification personnelle | C3 : les données ne peuvent pas être combinées ou autrement utilisées avec des informations directement identifiables |
| Ne peut pas être utilisé pour le ciblage d’annonces hors site | C5 : les données ne peuvent pas être utilisées pour le ciblage intersite par centre d’intérêt de contenu ou d’annonces |
| Ne peut pas être utilisé pour le ciblage d’annonces sur site | C6 : les données ne peuvent pas être utilisées pour le ciblage d’annonces sur site |
| Ne peut pas être utilisé pour la personnalisation sur site | C7 : les données ne peuvent pas être utilisées pour le ciblage de contenu sur site |

{style="table-layout:auto"}

### Contrôles d’exportation de données vers des actions marketing

Le tableau suivant décrit comment des libellés d’exportation de données spécifiques se mappent aux actions marketing reconnues :

| Libellé d’exportation des données | Action marketing |
| --- | --- |
| Cette destination peut permettre une combinaison avec des informations d’identification personnelle (PII) | Combinaison avec les PII |
| Cette destination peut être utilisée pour le ciblage publicitaire hors site | Ciblage intersite |
| Cette destination peut être utilisée pour le ciblage d’annonces sur site | Advertising sur site |
| Cette destination peut être utilisée pour la personnalisation de l’annonce sur site | Personalization sur site |

{style="table-layout:auto"}

## Comprendre les différences de population de segments entre Audience Manager et Experience Platform {#aep-aam-segment-population-differences}

Les nombres de populations de segments peuvent varier entre vos segments Audience Manager et Experience Platform. Bien que les numéros de segment pour des audiences similaires ou identiques doivent être proches, des différences dans les populations peuvent être dues aux facteurs répertoriés ci-dessous.

### Évaluation des segments dans Experience Platform

Audience Manager met à jour les numéros de reporting dans l&#39;interface une fois par jour. La durée de cette mise à jour correspond rarement à celle de l’évaluation des segments dans Experience Platform.

### Différences entre les règles de fusion de profil et les politiques de fusion

Les [[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) dans Audience Manager et les [[!UICONTROL Merge Policies]](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/merge-policies.html?lang=fr) dans Experience Platform fonctionnent différemment et le graphique d’identité utilisé pour chacune d’elles varie. Pour cette raison, certaines différences entre les populations de segments sont attendues.

>[!NOTE]
>
> Lors du partage de segments d’Experience Platform vers Audience Manager, votre organisation Platform [politique de fusion par défaut](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=fr#default-merge-policy) est prioritaire sur la [politique de fusion utilisée par le segment](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=fr#merge-policies) partagée avec Audience Manager. Par exemple, si la politique de fusion du segment partagé permet le [regroupement d’identifiants](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=fr#configure), mais pas la politique de fusion par défaut de l’organisation, cela peut entraîner des différences de population entre Platform et Audience Manager.

### Composition des segments dans Experience Platform

L’intégration entre Adobe Experience Platform et Audience Manager partage un certain nombre d’[espaces de noms d’identité](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=fr#identity-types) standard pour tous les clients : ECID, IDFA, GAID, adresses e-mail hachées (EMAIL_LC_SHA256), AdCloud ID. Si vos segments Experience Platform utilisent l’une de ces options comme identité principale pour les profils qualifiés, les profils sont comptabilisés dans les caractéristiques et les segments Audience Manager.

>[!NOTE]
>
> Les audiences dans Experience Platform dont les identités ont été désactivées des e-mails bruts n’apparaissent jamais dans Audience Manager.

Par exemple, si vous disposez d’un segment Experience Platform « Tous mes clients » et que les profils qualifiés sont les identifiants CRM, les ECID, les IDFA, les adresses e-mail brutes et hachées, le segment correspondant dans Audience Manager n’inclurait que les profils désactivés des adresses e-mail ECID, IDFA et hachées. La population de segments dans Audience Manager serait plus petite que celle dans Experience Platform.

![Partage de segments Experience Platform vers Audience Manager - composition de segments](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Présentation de Segmentation Service](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=fr#audiences)
>* [Guide de l’utilisateur du créateur de segments d’Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=fr#audiences)
>* [Connecteur Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=fr)
