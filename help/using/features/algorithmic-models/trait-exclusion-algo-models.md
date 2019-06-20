---
description: L'exclusion de caractéristiques fournit des contrôles supplémentaires dans le processus de modélisation, ce qui vous permet d'ajouter les rails de garde nécessaires au modèle, en fonction de l'expertise de votre domaine et des exigences réglementaires. Utilisez l'option Exclusions pour sélectionner les caractéristiques à ignorer lors de la création de modèles à partir d'une ou de plusieurs sources de données.
seo-description: L'exclusion de caractéristiques fournit des contrôles supplémentaires dans le processus de modélisation, ce qui vous permet d'ajouter les rails de garde nécessaires au modèle, en fonction de l'expertise de votre domaine et des exigences réglementaires. Utilisez l'option Exclusions pour sélectionner les caractéristiques à ignorer lors de la création de modèles à partir d'une ou de plusieurs sources de données.
seo-title: Exclusion des modèles algorithmiques
title: Exclusion des modèles algorithmiques
uuid: 1359800 b -6 e 6 c -41 e 1-88 b 4-23 d 31952 abb 3
translation-type: tm+mt
source-git-commit: f324838a5649722545ff36faba92bf3a13c2e805

---


# Algorithmic Models: Trait Exclusion {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] fournit des contrôles supplémentaires dans votre flux de modélisation, ce qui vous permet d&#39;ajouter les rails de garde nécessaires au modèle, en fonction de l&#39;expertise de votre domaine et des exigences réglementaires. Use the [!UICONTROL Exclusions] option to select which traits to ignore when creating models from one or more data sources.

## Cas d’utilisation {#use-cases}

Here are some use cases you can address with [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] vous permet d&#39;exclure certaines caractéristiques fourre-toutes, telles que les caractéristiques du visiteur du site, de sorte que vous ne démentiez pas le modèle, ce qui entraîne des résultats plats.
* Vous pouvez supprimer des caractéristiques que vous ne connaissez pas ou que vous ne faites pas confiance à une source de données pour mieux comprendre les caractéristiques influentes.
* Vous pouvez exclure certaines caractéristiques, telles que des caractéristiques démographiques, pour faciliter les obligations de conformité éventuelles.

>[!IMPORTANT]
>
>Remarque importante au troisième cas d&#39;utilisation. If the third-party data provider adds a new demographic trait to the data feed *after you created the model*, the trait is automatically picked up by the model. Vous ne pouvez pas exclure les caractéristiques de la modélisation après la création du modèle. See [Important Aspects &amp; Limitations](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). Soyez prudent lorsque vous utilisez cette fonctionnalité et travaillez avec le fournisseur de données pour vous assurer de toute modification apportée à la structure du flux.

![](assets/lam_exclude_traits.png)

## How to Use Trait Exclusions {#how-to-use}

Use the [Build a model](../../features/algorithmic-models/create-model.md#build-model) workflow to build new algorithmic models.

1. [!UICONTROL Exclusions] La sélection est grisée jusqu&#39;à ce que vous sélectionniez une ou plusieurs sources de données pour la modélisation.
2. After selecting one or more data sources for modeling, press **[!UICONTROL Browse All Traits]**.
3. In the **[!UICONTROL Select Traits to Exclude]** window, you can see all traits associated with the data sources you selected previously. Sélectionnez les caractéristiques à exclure.
4. Vous pouvez filtrer les caractéristiques par type de caractéristique ou parcourir les dossiers de caractéristiques. Notez que les dossiers de caractéristiques affichent uniquement les caractéristiques associées aux sources de données sélectionnées.
5. Press **[!UICONTROL Exclude Selected Traits]**.

>[!TIP]
>
>Vous pouvez exclure des dossiers entiers en excluant la caractéristique du dossier au lieu d&#39;exclure les caractéristiques du dossier, un par un. Par exemple, dans un dossier comportant 20 caractéristiques, vous devez uniquement exclure la caractéristique du dossier plutôt que d&#39;exclure toutes les caractéristiques un par un.

Si vous préférez des didacticiels vidéo, regardez notre démonstration vidéo relative à l&#39;exclusion de caractéristiques :

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12&captions=fre_fr)

## Important Aspects &amp; Limitations {#important-aspects-and-limitations}

Please take note of the following aspects and limitations related to [!UICONTROL Trait Exclusion]:

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Caractéristiques exclues dans la vue Résumé des modèles </p> </td>
   <td colname="col2"> <p>The excluded traits <i>do not show up</i> in the Models Summary view. You can see the excluded traits only in the <b><span class="uicontrol"> Edit Model</span></b> workflow. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>RBAC (Role-Based Access Controls) </p> </td>
   <td colname="col2"> <p>Note the following limitations for companies using <a href="../../features/administration/administration-overview.md#administration"> RBAC</a>: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">If you don't have access to view a trait, you <i>cannot</i> select that trait to be excluded from the model. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">If you don't have access to view a trait, you <i>cannot</i> view that trait in the excluded traits list. </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modification des caractéristiques exclues après l'enregistrement du modèle </p> </td>
   <td colname="col2"> <p>Vous ne pouvez pas modifier les caractéristiques exclues après avoir créé et enregistré un modèle. Si vous souhaitez affiner les résultats, vous pouvez cloner le modèle et modifier les caractéristiques exclues. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nombre maximum de caractéristiques que vous pouvez exclure </p> </td>
   <td colname="col2"> <p>Le nombre maximal de caractéristiques que vous pouvez exclure d'un modèle est de 500. Utilisez des caractéristiques de dossier pour maximiser les exclusions. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exclure la caractéristique de ligne de base </p> </td>
   <td colname="col2"> <p>The baseline trait is excluded by default, so it does not show up in the <b><span class="uicontrol"> Exclusions</span></b> list, when building the model. </p> </td>
  </tr>
 </tbody>
</table>

## Liens associés

* [A propos des caractéristiques algorithmiques](/help/using/features/algorithmic-models/understanding-models.md)
* [Exclusion de caractéristiques - Didacticiel](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)