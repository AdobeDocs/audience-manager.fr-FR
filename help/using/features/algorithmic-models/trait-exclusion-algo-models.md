---
description: L’exclusion des caractéristiques fournit des commandes supplémentaires dans votre processus de modélisation, vous permettant d’ajouter les rails de garde nécessaires au modèle, en fonction de votre expertise en matière de domaine et des exigences réglementaires. Utilisez l’option Exclusions pour sélectionner les caractéristiques à ignorer lors de la création de modèles à partir d’une ou de plusieurs sources de données.
seo-description: L’exclusion des caractéristiques fournit des commandes supplémentaires dans votre processus de modélisation, vous permettant d’ajouter les rails de garde nécessaires au modèle, en fonction de votre expertise en matière de domaine et des exigences réglementaires. Utilisez l’option Exclusions pour sélectionner les caractéristiques à ignorer lors de la création de modèles à partir d’une ou de plusieurs sources de données.
seo-title: Exclusion des caractéristiques des modèles algorithmiques
title: Exclusion des caractéristiques des modèles algorithmiques
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
translation-type: tm+mt
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

---


# Algorithmic Models: Trait Exclusion {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] provides additional controls in your modeling workflow, allowing you to add the necessary guard rails to the model, based on your domain expertise and regulatory requirements. Use the [!UICONTROL Exclusions] option to select which traits to ignore when creating models from one or more data sources.

## Cas d’utilisation {#use-cases}

Here are some use cases you can address with [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] enables you to exclude certain catch-all traits, such as site visitor traits, so you don't bias the model, leading to flat results.
* You can remove traits that you don't know about or you don't trust from a data source, to better understand the influential traits.
* You can exclude certain traits, such as demographic traits, to help with any compliance obligations you may have.

>[!IMPORTANT]
>
>An important note on the third use case. If the third-party data provider adds a new demographic trait to the data feed after you created the model, the trait is automatically picked up by the model. ** You cannot exclude traits from modeling after creating the model. See [Important Aspects &amp; Limitations](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). Please exercise caution when using this feature and work with the data provider to ensure you are informed of any changes to the feed structure.

![](assets/lam_exclude_traits.png)

## How to Use Trait Exclusions {#how-to-use}

Utilisez le processus [Créer un modèle](../../features/algorithmic-models/create-model.md#build-model) pour créer de nouveaux modèles algorithmiques.

1. La [!UICONTROL Exclusions] sélection est grisée jusqu’à ce que vous sélectionniez une ou plusieurs sources de données pour la modélisation.
2. After selecting one or more data sources for modeling, press .**[!UICONTROL Browse All Traits]**
3. Dans la **[!UICONTROL Select Traits to Exclude]** fenêtre, vous pouvez voir toutes les caractéristiques associées aux sources de données que vous avez sélectionnées précédemment. Sélectionnez les caractéristiques à exclure.
4. Vous pouvez filtrer les caractéristiques par type de caractéristique ou parcourir les dossiers de caractéristiques. Notez que les dossiers de caractéristiques affichent uniquement les caractéristiques associées aux sources de données sélectionnées.
5. Appuyez **[!UICONTROL Exclude Selected Traits]**.

>[!TIP]
>
>Vous pouvez exclure des dossiers entiers en excluant la caractéristique de dossier au lieu d’exclure les caractéristiques du dossier, une par une. Par exemple, dans un dossier comportant 20 caractéristiques, vous devez uniquement exclure la caractéristique de dossier au lieu d’exclure toutes les caractéristiques une par une.

Si vous préférez les didacticiels vidéo, regardez notre démonstration vidéo pour l’exclusion des caractéristiques :

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12&captions=fre_fr)

## Aspects importants et limites {#important-aspects-and-limitations}

Veuillez prendre note des aspects et limitations suivants liés à [!UICONTROL Trait Exclusion]:

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Caractéristiques exclues dans l’affichage récapitulatif des modèles </p> </td>
   <td colname="col2"> <p>Les caractéristiques exclues <i>ne s’affichent</i> pas dans la vue Résumé des modèles. Vous pouvez afficher les caractéristiques exclues uniquement dans le flux de travail <b><span class="uicontrol"> Modifier le modèle</span></b> . </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contrôles d’accès basés sur les rôles (RBAC) </p> </td>
   <td colname="col2"> <p>Notez les restrictions suivantes pour les entreprises qui utilisent <a href="../../features/administration/administration-overview.md#administration"> RBAC</a>: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">Si vous n’avez pas accès à l’affichage d’une caractéristique, vous <i>ne pouvez pas</i> sélectionner cette caractéristique à exclure du modèle. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">Si vous n’avez pas accès à l’affichage d’une caractéristique, vous <i>ne pouvez pas</i> l’afficher dans la liste des caractéristiques exclues. </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modifier les caractéristiques exclues après l'enregistrement du modèle </p> </td>
   <td colname="col2"> <p>Vous ne pouvez pas modifier les caractéristiques exclues après avoir créé et enregistré un modèle. Si vous souhaitez modifier les résultats, vous pouvez cloner le modèle et modifier les caractéristiques exclues. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nombre maximal de caractéristiques que vous pouvez exclure </p> </td>
   <td colname="col2"> <p>Le nombre maximal de caractéristiques que vous pouvez exclure d’un modèle est de 500. Utilisez les caractéristiques des dossiers pour optimiser vos exclusions. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exclure la caractéristique de ligne de base </p> </td>
   <td colname="col2"> <p>La caractéristique de ligne de base est exclue par défaut, de sorte qu’elle ne s’affiche pas dans la liste <b><span class="uicontrol"> Exclusions</span></b> lors de la création du modèle. </p> </td>
  </tr>
 </tbody>
</table>

Regardez la vidéo ci-dessous pour savoir comment et pourquoi exclure des caractéristiques spécifiques d'une [!UICONTROL Look-Alike Model].

>[!VIDEO](https://video.tv.adobe.com/v/25569/?captions=fre_fr)

## Liens connexes

* [A propos des caractéristiques algorithmiques](/help/using/features/algorithmic-models/understanding-models.md)
* [Exclusion de caractéristiques - Didacticiel](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)