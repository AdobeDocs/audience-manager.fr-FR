---
description: Décrit les étapes obligatoires et facultatives qui vous permettent de créer un modèle algorithmique dans le créateur de modèles.
keywords: déterminer comment fonctionne
seo-description: Décrit les étapes obligatoires et facultatives qui vous permettent de créer un modèle algorithmique dans le créateur de modèles.
seo-title: Création d'un modèle algorithmique
solution: Audience Manager
title: Création d'un modèle algorithmique
topic: API DIL
uuid: ccf 4 fc 4 e-cf 92-445 f-b 2 d 9-71 c 3 ca 624 e 26
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create an Algorithmic Model {#create-an-algorithmic-model}

Describes the required and optional steps that let you create an algorithmic model in [!UICONTROL Model Builder].

## Build a Model {#build-model}

<!-- t_model_build.xml -->

### Section Créateur de modèles

[!UICONTROL Model Builder] se compose des sections [!UICONTROL Basic Information] et [!UICONTROL Configuration] des sections. Pour créer un modèle, renseignez les champs obligatoires de ces deux sections. Enregistrez votre modèle pour démarrer l&#39;algorithme. [!DNL Audience Manager] vous envoie une notification automatisée une fois les premières données exécutées. After you receive the email, you can go to [Trait Builder](../../features/traits/about-trait-builder.md) and create algorithmic traits.

>[!NOTE]
>
>* Le processus de modélisation ne s&#39;exécute qu&#39;une seule fois si vous créez un modèle et ne créez aucune caractéristique avec lui.
>* Créez des modèles à partir des sources de données qui contiennent une quantité significative d&#39;informations. Les modèles dont les données sont insuffisantes s&#39;exécuteront, mais ils ne retourneront aucun résultat.
>* *Ne* créez pas de modèles avec d&#39;autres caractéristiques ou segments algorithmiques.
>* La notification électronique automatisée est envoyée une seule fois (après la première exécution de données).


### Créer le modèle

To build a model, go to the [!UICONTROL Models] section and click **[!UICONTROL Add New]** and follow the steps below:

1. In the [Basic Information](../../features/algorithmic-models/create-model.md#basic-information) section
   * Nommez le modèle.
   * *(Facultatif)* Fournissez une brève description du modèle.
   * Set the status for the model to **[!UICONTROL Active]** or **[!UICONTROL Inactive]**. Les modèles inactifs ne s&#39;exécuteront pas et ne produisent aucune donnée.
1. In the [Configuration](../../features/algorithmic-models/create-model.md#configuration) section:
   * Click **[!UICONTROL Browse All Traits]** or **[!UICONTROL Browse All Segments]** to select a trait or segment you want to model against. Sélectionnez une caractéristique intégrée, une caractéristique basée sur des règles ou un segment comme ligne de base. Sinon, vos modèles ne seront pas exécutés.
   * Choisissez une période de consultation de 30, 60 ou 90 jours. Cette opération définit une période pour le modèle.
   * The [!UICONTROL TraitWeight] algorithm is selected by default.
   * Select a data source from the [!UICONTROL Available Data] list.
   * Click **[!UICONTROL Save]** when done.

## Basic Information for Algorithmic Models {#basic-information}

<!-- r_model_basic.xml -->

In [!UICONTROL Model Builder], the [!UICONTROL Basic Information] settings let you create new or edit existing models. To create a new model, provide a name and move on to the [!UICONTROL Configuration] settings. Le champ Description est facultatif.

| Champ | Description |
|---|---|
| **[!UICONTROL Name]** | Donnez à votre modèle un nom court et court qui décrit sa fonction ou son rôle. Evitez les abréviations, les caractères spéciaux et les accents. |
| **[!UICONTROL Description]** | Champ pour obtenir des informations descriptives supplémentaires sur le modèle. |
| **[!UICONTROL Status]** | Active ou désactive le modèle (actif par défaut). |

## Configuration {#configuration}

In [!UICONTROL Model Builder], the [!UICONTROL Configuration] section lets you add traits or segments to the model. Dans cette section, sélectionnez une caractéristique ou un segment de base, une période de consultation et des données issues de vos sources de données Première et Tierce.

<!-- r_model_configuration.xml -->

### Conditions préalables

Complete the required fields in the [!UICONTROL Basic Information] section first.

![](assets/lam_exclude_traits_numbered.png)

<table id="table_7A6BE5E5498D4776A30323B743954150"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Sélectionner une caractéristique ou un segment de ligne de base (1)</b> </p> </td> 
   <td colname="col2"> <p>Cliquez sur le bouton de caractéristique ou de segment pour afficher la liste de toutes vos caractéristiques ou de vos segments. Le segment ou la caractéristique sélectionné devient la ligne de base utilisée par les algorithmes système pour la modélisation. </p> <p> <p><b>Remarque</b>: Sélectionnez une caractéristique intégrée, une caractéristique basée sur des règles ou un segment comme ligne de base. Sinon, vos modèles ne seront pas exécutés. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Sélectionner une période de recherche (2)</b> </p> </td> 
   <td colname="col2"> <p>Définit une période pour le modèle. Selon votre sélection, l'algorithme comprend et évalue les données des 30, 60 ou 90 derniers jours. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Sélectionner l'algorithme (3)</b> </p> </td> 
   <td colname="col2"> <p>At this time, Model Builder works with our proprietary <span class="keyword"> Trait Weight</span> algorithm only. <span class="keyword"> Audience Manager</span> peut ajouter d'autres fonctions algorithmiques dans les versions suivantes. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Sélectionner des données de modèle dans la source de données (4)</b> </p> </td> 
   <td colname="col2"> <p>Vous permet de sélectionner les sources de données propriétaires et tierces que vous souhaitez utiliser dans le modèle. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exclusions (5)</b> </p> </td> 
   <td colname="col2"> <p>Vous pouvez exclure des caractéristiques des sources de données sélectionnées pour la modélisation. Use the <span class="wintitle"> Exclusions</span> list and read <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> Algorithmic Models: Trait Exclusion</a> to learn more. </p> </td>
  </tr> 
 </tbody>
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Comprendre traitweight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

