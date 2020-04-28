---
description: Décrit les étapes requises et facultatives permettant de créer un modèle algorithmique dans le créateur de modèles.
keywords: algo how works
seo-description: Décrit les étapes requises et facultatives permettant de créer un modèle algorithmique dans le créateur de modèles.
seo-title: Création d’un modèle algorithmique
solution: Audience Manager
title: Création d’un modèle algorithmique
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
translation-type: tm+mt
source-git-commit: 35bad7e676aa1d4143f5d114a1eff85d6aba5f1d

---


# Créer un modèle similaire {#create-an-algorithmic-model}

Décrit les étapes obligatoires et facultatives permettant de créer une [!UICONTROL Look-Alike Model].

## Section Créateur de modèles

[!UICONTROL Model Builder] se compose des sections [!UICONTROL Basic Information] et [!UICONTROL Configuration] . Pour créer un modèle, renseignez les champs obligatoires de ces deux sections. Enregistrez votre modèle pour  l’algorithme. [!DNL Audience Manager] vous envoie une notification automatisée une fois la première exécution des données terminée. Une fois que vous avez reçu le courrier électronique, vous pouvez accéder au créateur de [caractéristiques](../../features/traits/about-trait-builder.md) et créer des caractéristiques algorithmiques.

>[!NOTE]
>
>* Le processus de modélisation ne s’exécute qu’une seule fois si vous créez un modèle et n’en créez aucune caractéristique.
>* Créez des modèles à partir de sources de données qui contiennent une quantité significative d’informations. Les modèles avec des données insuffisantes s’exécuteront, mais ils ne retourneront pas de résultats.
>* *Ne créez pas* de modèles avec d’autres caractéristiques ou segments algorithmiques.
>* La notification électronique automatisée est envoyée une seule fois (après la première exécution des données).


## Créer le modèle

Suivez les étapes ci-dessous pour créer un [!UICONTROL Look-Alike Model]:

1. Accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** et cliquez **[!UICONTROL Add New]** dans la [!UICONTROL Look-Alike Modeling] section.
   ![look-like-add](assets/look-alike-add.png)
1. Dans la section Informations [](../../features/algorithmic-models/create-model.md#basic-information) de base
   * Nommez le modèle.
   * *(Facultatif)* Fournissez une brève description du modèle.
   * Définissez l’état du modèle sur **[!UICONTROL Active]** ou **[!UICONTROL Inactive]**. Les modèles inactifs ne s’exécuteront pas et ne produiront aucune donnée.
      ![apparence-basique](assets/look-alike-basic.png)
1. Dans la section [Configuration](../../features/algorithmic-models/create-model.md#configuration) :
   * Cliquez sur **[!UICONTROL Browse All Traits]** ou **[!UICONTROL Browse All Segments]** pour sélectionner une caractéristique ou un segment à modéliser. Recherchez les caractéristiques par nom, ID, description ou source de données. Cliquez sur un dossier lors de la recherche pour limiter les résultats à ce dossier et à ses sous-dossiers. Vous pouvez également filtrer les caractéristiques par type de caractéristique ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded]et [!UICONTROL Algorithmic]) ou par type de population (ID[de](../../reference/ids-in-aam.md) [périphérique et ID de périphérique).](../../reference/ids-in-aam.md)
      ![browse-traits](assets/browse-traits.png)
   * Choisissez une période de recherche en arrière de 30, 60 ou 90 jours. Définit une période pour le modèle.
   * The [!UICONTROL TraitWeight] algorithm is selected by default.
   * Sélectionnez une source de données dans le [!UICONTROL Available Data] .
   * Cliquez **[!UICONTROL Save]** une fois terminé.
      ![configuration ressemblante](assets/look-alike-configuration.png)

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

Renseignez d’abord les champs obligatoires de la [!UICONTROL Basic Information] section.

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
   <td colname="col1"> <p><b>Sélectionner un segment ou un trait de ligne de base (1)</b> </p> </td> 
   <td colname="col2"> <p>Cliquez sur le bouton Caractéristique ou Segment pour afficher un  de toutes vos caractéristiques ou segments. Votre segment ou caractéristique sélectionné devient la ligne de base que les algorithmes système utilisent pour la modélisation. </p> <p> <p><b>Remarque</b>:  Sélectionnez une caractéristique intégrée, une caractéristique basée sur des règles ou un segment comme ligne de base. Sinon, vos modèles ne s'exécuteront pas. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Sélectionnez Rechercher la période précédente (2)</b> </p> </td> 
   <td colname="col2"> <p>Définit une période pour le modèle. Selon votre sélection, l’algorithme inclut et évalue les données des 30, 60 ou 90 jours précédents. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Sélectionner un algorithme (3)</b> </p> </td> 
   <td colname="col2"> <p>Pour le moment, Model Builder fonctionne uniquement avec l’algorithme de notre <span class="keyword"></span> de caractéristiques propriétaire. <span class="keyword">  Gestionnaire de</span> de peut ajouter d’autres fonctions algorithmiques dans les versions suivantes. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Sélectionner les données du modèle à partir de la source de données (4)</b> </p> </td> 
   <td colname="col2"> <p>Permet de sélectionner les sources de données propriétaires et tiers que vous souhaitez utiliser dans le modèle. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exclusions (5)</b> </p> </td> 
   <td colname="col2"> <p>Vous pouvez exclure des caractéristiques des sources de données que vous avez sélectionnées pour la modélisation. Utilisez le  <span class="wintitle"> Exclusions</span> et lisez <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> Modèles algorithmiques : Exclusion</a> des caractéristiques pour en savoir plus. </p> </td>
  </tr> 
 </tbody>
</table>

Regardez la vidéo ci-dessous pour apprendre à créer un modèle à l&#39;apparence unique, afin que vous puissiez trouver davantage de vos propres qui ressemblent à vos convertisseurs.

>[!VIDEO](https://video.tv.adobe.com/v/23504/)

>[!MORELIKETHIS]
>
>* [Présentation de TraitWeight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

