---
description: L’exclusion de caractéristiques fournit des contrôles supplémentaires dans votre processus de modélisation, vous permettant d’ajouter les rails de garde nécessaires au modèle, en fonction de votre expertise en matière de domaine et des exigences réglementaires. Utilisez l’option Exclusions pour sélectionner les caractéristiques à ignorer lors de la création de modèles à partir d’une ou de plusieurs sources de données.
seo-description: L’exclusion de caractéristiques fournit des contrôles supplémentaires dans votre processus de modélisation, vous permettant d’ajouter les rails de garde nécessaires au modèle, en fonction de votre expertise en matière de domaine et des exigences réglementaires. Utilisez l’option Exclusions pour sélectionner les caractéristiques à ignorer lors de la création de modèles à partir d’une ou de plusieurs sources de données.
seo-title: Exclusion des caractéristiques des modèles algorithmiques
title: Exclusion des caractéristiques des modèles algorithmiques
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 56f3b605b434f18c07d36196fd6ae21743401294
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 1%

---


# Modélisation analogue : exclusion de caractéristiques {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] fournit des contrôles supplémentaires dans votre processus de modélisation, vous permettant d&#39;ajouter les rails de garde nécessaires au modèle, en fonction de votre expertise en matière de domaine et des exigences réglementaires. Utilisez l&#39;option [!UICONTROL Exclusions] pour sélectionner les caractéristiques à ignorer lors de la création de modèles à partir d&#39;une ou de plusieurs sources de données.

## Cas d’utilisation {#use-cases}

Voici quelques cas d&#39;utilisation que vous pouvez traiter avec [!UICONTROL Trait Exclusion] :

* [!UICONTROL Trait Exclusion] vous permet d’exclure certaines caractéristiques fourre-tout, telles que les caractéristiques des visiteurs du site, afin de ne pas biaiser le modèle et d’obtenir des résultats plats.
* Vous pouvez supprimer des caractéristiques que vous ne connaissez pas ou auxquelles vous n’avez pas confiance d’une source de données, afin de mieux comprendre les caractéristiques influentes.
* Vous pouvez exclure certaines caractéristiques, telles que les caractéristiques démographiques, pour vous aider à respecter les obligations que vous pourriez avoir en matière de conformité.

>[!IMPORTANT]
>
>Une note importante sur le troisième cas d&#39;utilisation. Si le fournisseur de données tiers ajoute une nouvelle caractéristique démographique au flux de données *après avoir créé le modèle*, la caractéristique est automatiquement reprise par le modèle. Vous ne pouvez pas exclure les caractéristiques de la modélisation après avoir créé le modèle. Voir [Aspects et limites importants](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). Soyez prudent lorsque vous utilisez cette fonctionnalité et demandez au fournisseur de données de vous assurer que vous êtes informé de toute modification apportée à la structure du flux.

![](assets/lam_exclude_traits.png)

## Utilisation des exclusions de caractéristiques {#how-to-use}

Utilisez le processus [Créer un modèle](../../features/algorithmic-models/create-model.md#build-model) pour créer de nouveaux modèles algorithmiques.

1. La sélection [!UICONTROL Exclusions] est grisée jusqu’à ce que vous sélectionniez une ou plusieurs sources de données pour la modélisation.
2. Après avoir sélectionné une ou plusieurs sources de données pour la modélisation, appuyez sur **[!UICONTROL Browse All Traits]**.
3. Dans la fenêtre **[!UICONTROL Select Traits to Exclude]**, vous pouvez afficher toutes les caractéristiques associées aux sources de données que vous avez sélectionnées précédemment. Sélectionnez les caractéristiques à exclure.
4. Vous pouvez filtrer les caractéristiques par type de caractéristique, type de population de caractéristiques ([ID de périphérique](../../reference/ids-in-aam.md) et [ID de plusieurs périphériques](../../reference/ids-in-aam.md)) ou parcourir les dossiers de caractéristiques. Notez que les dossiers de caractéristiques affichent uniquement les caractéristiques associées aux sources de données sélectionnées.
5. Appuyez sur **[!UICONTROL Exclude Selected Traits]**.

![exclusions de caractéristiques](assets/trait-exclusions-browse-traits.png)

>[!TIP]
>
>Vous pouvez exclure des dossiers entiers en excluant la caractéristique de dossier au lieu d’exclure les caractéristiques du dossier, une par une. Par exemple, dans un dossier contenant 20 caractéristiques, il vous suffit d’exclure la caractéristique de dossier au lieu d’exclure toutes les caractéristiques une par une.

Si vous préférez les didacticiels vidéo, regardez notre démonstration vidéo pour l’exclusion des caractéristiques :

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12)

En outre, regardez la vidéo ci-dessous pour obtenir un aperçu détaillé du fonctionnement des mesures sur plusieurs périphériques.

>[!VIDEO](https://video.tv.adobe.com/v/33445/?quality=12)

## Aspects importants et limites {#important-aspects-and-limitations}

Veuillez prendre note des aspects et limitations suivants liés à [!UICONTROL Trait Exclusion] :

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Caractéristiques exclues dans la Vue de résumé des modèles </p> </td>
   <td colname="col2"> <p>Les caractéristiques exclues <i>n'apparaissent pas</i> dans la vue de résumé des modèles. Vous pouvez afficher les caractéristiques exclues uniquement dans le flux de travaux <b><span class="uicontrol"> Modifier le modèle</span></b>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contrôles d'accès basés sur les rôles (RBAC) </p> </td>
   <td colname="col2"> <p>Notez les restrictions suivantes pour les sociétés utilisant <a href="../../features/administration/administration-overview.md#administration"> RBAC</a> : </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">Si vous n'avez pas accès à la vue d'une caractéristique, vous <i>ne pouvez pas </i> sélectionner cette caractéristique à exclure du modèle. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">Si vous n'avez pas accès à la vue d'une caractéristique, vous <i>ne pouvez pas </i> vue cette caractéristique dans la liste des caractéristiques exclues. </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modifier les caractéristiques exclues après l'enregistrement du modèle </p> </td>
   <td colname="col2"> <p>Vous ne pouvez pas modifier les caractéristiques exclues après avoir créé et enregistré un modèle. Si vous souhaitez modifier les résultats, vous pouvez cloner le modèle et modifier les caractéristiques exclues. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nombre maximal de caractéristiques que vous pouvez exclure </p> </td>
   <td colname="col2"> <p>Le nombre maximal de caractéristiques que vous pouvez exclure d’un modèle est de 500. Utilisez les caractéristiques des dossiers pour maximiser vos exclusions. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exclure la caractéristique de ligne de base </p> </td>
   <td colname="col2"> <p>La caractéristique de ligne de base est exclue par défaut, de sorte qu’elle ne s’affiche pas dans la liste <b><span class="uicontrol"> Exclusions</span></b> lors de la création du modèle. </p> </td>
  </tr>
 </tbody>
</table>

Regardez la vidéo ci-dessous pour savoir comment et pourquoi exclure des caractéristiques spécifiques d&#39;un [!UICONTROL Look-Alike Model].

>[!VIDEO](https://video.tv.adobe.com/v/25569/)

## Liens connexes

* [A propos des caractéristiques algorithmiques](/help/using/features/algorithmic-models/understanding-models.md)
* [Exclusion de caractéristiques - Didacticiel](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)