---
description: Describes the required and optional steps that let you create an algorithmic model in Model Builder.
keywords: algo how works
seo-description: Describes the required and optional steps that let you create an algorithmic model in Model Builder.
seo-title: Create an Algorithmic Model
solution: Audience Manager
title: Create an Algorithmic Model
topic: DIL API
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
translation-type: tm+mt
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

---


# Create an Algorithmic Model {#create-an-algorithmic-model}

Describes the required and optional steps that let you create an algorithmic model in .[!UICONTROL Model Builder]

## Build a Model {#build-model}

<!-- t_model_build.xml -->

### Model Builder Section

[!UICONTROL Model Builder] consists of the  and  sections. [!UICONTROL Basic Information][!UICONTROL Configuration] To create a model, complete the required fields in these two sections. Enregistrez votre modèle pour démarrer l’algorithme. [!DNL Audience Manager] sends you an automated notification after the first data run completes. Une fois que vous avez reçu le courrier électronique, vous pouvez accéder au créateur de [caractéristiques](../../features/traits/about-trait-builder.md) et créer des caractéristiques algorithmiques.

>[!NOTE]
>
>* Le processus de modélisation ne s’exécute qu’une seule fois si vous créez un modèle et n’en créez aucune caractéristique.
>* Build models from data sources that contain a meaningful amount of information. Les modèles avec des données insuffisantes s’exécuteront, mais ils ne retourneront pas de résultats.
>* *Ne créez pas* de modèles avec d’autres caractéristiques ou segments algorithmiques.
>* La notification électronique automatisée est envoyée une seule fois (après la première exécution des données).


### Créer le modèle

Pour créer un modèle, accédez à la [!UICONTROL Models] section et cliquez **[!UICONTROL Add New]** sur et procédez comme suit :

1. Dans la section Informations [](../../features/algorithmic-models/create-model.md#basic-information) de base
   * Nommez le modèle.
   * *(Facultatif)* Fournissez une brève description du modèle.
   * Définissez l’état du modèle sur **[!UICONTROL Active]** ou **[!UICONTROL Inactive]**. Les modèles inactifs ne s’exécutent pas et ne produisent aucune donnée.
1. Dans la section [Configuration](../../features/algorithmic-models/create-model.md#configuration) :
   * Cliquez sur **[!UICONTROL Browse All Traits]** ou **[!UICONTROL Browse All Segments]** pour sélectionner une caractéristique ou un segment à modéliser.   Sélectionnez une caractéristique intégrée, une caractéristique basée sur des règles ou un segment comme ligne de base. Sinon, vos modèles ne s'exécuteront pas.
   * Choisissez une période de recherche en arrière de 30, 60 ou 90 jours. Définit une période pour le modèle.
   * The [!UICONTROL TraitWeight] algorithm is selected by default.
   * Sélectionnez une source de données dans la [!UICONTROL Available Data] liste.
   * Click **[!UICONTROL Save]** when done.

## Informations de base sur les modèles algorithmiques {#basic-information}

<!-- r_model_basic.xml -->

Dans [!UICONTROL Model Builder]ce cas, les [!UICONTROL Basic Information] paramètres vous permettent de créer ou de modifier des modèles existants. Pour créer un modèle, attribuez un nom et passez aux [!UICONTROL Configuration] paramètres. Le champ de description est facultatif.

| Champ | Description |
|---|---|
| **[!UICONTROL Name]** | Donnez à votre modèle un nom logique et court qui décrit sa fonction ou son objectif. Evitez les abréviations, les caractères spéciaux et les accents. |
| **[!UICONTROL Description]** | Champ permettant d’obtenir des informations descriptives supplémentaires sur le modèle. |
| **[!UICONTROL Status]** | Active ou désactive le modèle (actif par défaut). |

## Configuration {#configuration}

Dans [!UICONTROL Model Builder]la section [!UICONTROL Configuration] , vous pouvez ajouter des caractéristiques ou des segments au modèle. Dans cette section, sélectionnez une caractéristique ou un segment de base, une période de rétrospective et des données provenant de vos sources de données propriétaires et tiers.

<!-- r_model_configuration.xml -->

### Conditions préalables

Complete the required fields in the  section first.[!UICONTROL Basic Information]

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
   <td colname="col1"> <p><b>Select a Baseline Trait or Segment (1)</b> </p> </td> 
   <td colname="col2"> <p>Click the trait or segment button to see a list of all your traits or segments. Your selected segment or trait becomes the baseline that the system algorithms use for modeling. </p> <p> <p><b>Note:  Select an onboarded trait, a rule-based trait, or a segment as baseline. </b> Otherwise, your models will not run. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Select Look Back Period (2)</b> </p> </td> 
   <td colname="col2"> <p>Sets a time range for the model. Based on your selection, the algorithm includes and evaluates data from the previous 30, 60, or 90 days. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Select Algorithm (3)</b> </p> </td> 
   <td colname="col2"> <p>At this time, Model Builder works with our proprietary  Trait Weight algorithm only. <span class="keyword"></span> <span class="keyword"> Audience Manager</span> peut ajouter d’autres fonctions algorithmiques dans les versions suivantes. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Select Model Data from Data Source (4)</b> </p> </td> 
   <td colname="col2"> <p>Permet de sélectionner les sources de données propriétaires et tiers que vous souhaitez utiliser dans le modèle. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exclusions (5)</b> </p> </td> 
   <td colname="col2"> <p>Vous pouvez exclure des caractéristiques des sources de données sélectionnées pour la modélisation. Utilisez la liste <span class="wintitle"> Exclusions</span> et lisez <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> Modèles algorithmiques : Exclusion</a> des caractéristiques pour en savoir plus. </p> </td>
  </tr> 
 </tbody>
</table>

Regardez la vidéo ci-dessous pour découvrir comment créer un modèle à l'apparence unique de premier niveau, afin que vous puissiez trouver davantage de vos propres visiteurs qui ressemblent à vos convertisseurs.

>[!VIDEO](https://video.tv.adobe.com/v/23504/?captions=fre_fr)

>[!MORE_LIKE_This]
>
>* [Présentation de TraitWeight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

