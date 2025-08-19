---
description: L’exclusion de caractéristiques fournit des commandes supplémentaires dans votre workflow de modélisation, ce qui vous permet d’ajouter les barrières de sécurité nécessaires au modèle, en fonction de votre expertise de domaine et des exigences réglementaires. Utilisez l’option Exclusions pour sélectionner les caractéristiques à ignorer lors de la création de modèles à partir d’une ou de plusieurs sources de données.
seo-description: Trait Exclusion provides additional controls in your modeling workflow, allowing you to add the necessary guard rails to the model, based on your domain expertise and regulatory requirements. Use the Exclusions option to select which traits to ignore when creating models from one or more data sources.
seo-title: Algorithmic Models  Trait Exclusion
title: Exclusion des caractéristiques des modèles algorithmiques
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
feature: Algorithmic Models
exl-id: 7e2df04d-7e07-408d-b82a-9571b5839ff4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 0%

---

# Modélisation analogue : exclusion des caractéristiques {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] fournit des commandes supplémentaires dans votre workflow de modélisation, ce qui vous permet d’ajouter les barrières de sécurité nécessaires au modèle, en fonction de l’expertise de votre domaine et des exigences réglementaires. Utilisez l’option [!UICONTROL Exclusions] pour sélectionner les caractéristiques à ignorer lors de la création de modèles à partir d’une ou de plusieurs sources de données.

## Cas d’utilisation {#use-cases}

Voici quelques cas d’utilisation que vous pouvez résoudre à l’aide de [!UICONTROL Trait Exclusion] :

* [!UICONTROL Trait Exclusion] vous permet d’exclure certaines caractéristiques fourre-tout, telles que les caractéristiques des visiteurs du site, afin de ne pas biaiser le modèle et d’obtenir des résultats stables.
* Vous pouvez supprimer d’une source de données des caractéristiques que vous ne connaissez pas ou auxquelles vous n’avez pas confiance, afin de mieux comprendre les caractéristiques influentes.
* Vous pouvez exclure certaines caractéristiques, telles que les caractéristiques démographiques, afin de vous aider à respecter vos obligations de conformité.

>[!IMPORTANT]
>
>Remarque importante concernant le troisième cas d’utilisation. Si le fournisseur de données tiers ajoute une nouvelle caractéristique démographique au flux de données *après la création du modèle*, la caractéristique est automatiquement récupérée par le modèle. Vous ne pouvez pas exclure des caractéristiques de la modélisation après la création du modèle. Voir [Aspects et limites importants](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). Soyez prudent lorsque vous utilisez cette fonctionnalité et collaborez avec le fournisseur de données pour vous assurer que vous êtes informé de tout changement apporté à la structure du flux.

![](assets/lam_exclude_traits.png)

## Utilisation des exclusions de caractéristiques {#how-to-use}

Utilisez le workflow [Créer un modèle](../../features/algorithmic-models/create-model.md#build-model) pour créer de nouveaux modèles algorithmiques.

1. La sélection de [!UICONTROL Exclusions] est grisée jusqu’à ce que vous sélectionniez une ou plusieurs sources de données pour la modélisation.
2. Après avoir sélectionné une ou plusieurs sources de données pour la modélisation, appuyez sur **[!UICONTROL Browse All Traits]**.
3. Dans la fenêtre **[!UICONTROL Select Traits to Exclude]**, vous pouvez voir toutes les caractéristiques associées aux sources de données que vous avez sélectionnées précédemment. Sélectionnez les caractéristiques à exclure.
4. Vous pouvez filtrer les caractéristiques par type de caractéristique, type de population de caractéristiques ([ID d’appareil](../../reference/ids-in-aam.md) et [ID sur l’ensemble des appareils](../../reference/ids-in-aam.md)) ou parcourir les dossiers de caractéristiques. Notez que les dossiers de caractéristiques n’affichent que les caractéristiques associées aux sources de données sélectionnées.
5. Appuyez sur **[!UICONTROL Exclude Selected Traits]**.

![caractéristiques-exclusions](assets/trait-exclusions-browse-traits.png)

>[!TIP]
>
>Vous pouvez exclure des dossiers entiers en excluant la caractéristique du dossier au lieu d’exclure les caractéristiques du dossier, une par une. Par exemple, dans un dossier avec 20 caractéristiques, il vous suffirait d’exclure la caractéristique du dossier au lieu d’exclure toutes les caractéristiques une par une.

Si vous préférez des tutoriels vidéo, regardez notre démonstration vidéo pour l’exclusion des caractéristiques :

>[!VIDEO](https://video.tv.adobe.com/v/38132/?quality=12&captions=fre_fr)

De plus, regardez la vidéo ci-dessous pour un aperçu détaillé du fonctionnement des mesures sur l’ensemble des appareils.

>[!VIDEO](https://video.tv.adobe.com/v/36727/?quality=12&captions=fre_fr)

## Aspects importants et limites {#important-aspects-and-limitations}

Veuillez prendre note des aspects et limites suivants liés à [!UICONTROL Trait Exclusion] :

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Caractéristiques exclues dans la vue de synthèse des modèles </p> </td>
   <td colname="col2"> <p>Les caractéristiques exclues <i>ne s’affichent pas</i> dans la vue Résumé des modèles . Vous ne pouvez voir les caractéristiques exclues que dans le workflow <b><span class="uicontrol"> Modifier le modèle</span></b> . </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contrôles d’accès basés sur les rôles (RBAC) </p> </td>
   <td colname="col2"> <p>Notez les restrictions suivantes pour les sociétés qui utilisent <a href="../../features/administration/administration-overview.md#administration"> RBAC </a> : </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">Si vous n’avez pas accès à l’affichage d’une caractéristique, vous <i> pouvez pas </i> cette caractéristique à exclure du modèle. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">Si vous n’avez pas accès à l’affichage d’une caractéristique, vous <i> pouvez pas </i> cette caractéristique dans la liste des caractéristiques exclues. </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modifier les caractéristiques exclues après l’enregistrement du modèle </p> </td>
   <td colname="col2"> <p>Vous ne pouvez pas modifier les caractéristiques exclues après avoir créé et enregistré un modèle. Si vous souhaitez ajuster les résultats, vous pouvez cloner le modèle et modifier les caractéristiques exclues. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nombre maximal de caractéristiques à exclure </p> </td>
   <td colname="col2"> <p>Le nombre maximal de caractéristiques que vous pouvez exclure d’un modèle est de 500. Utilisez les caractéristiques de dossier pour optimiser vos exclusions. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exclure la caractéristique de base </p> </td>
   <td colname="col2"> <p>La caractéristique de ligne de base est exclue par défaut ; elle n’apparaît donc pas dans la liste des exclusions de la <b><span class="uicontrol"></span></b> lors de la création du modèle. </p> </td>
  </tr>
 </tbody>
</table>

Regardez la vidéo ci-dessous pour savoir comment et pourquoi exclure des caractéristiques spécifiques d’un [!UICONTROL Look-Alike Model].

>[!VIDEO](https://video.tv.adobe.com/v/38132?captions=fre_fr)

## Liens connexes

* [À propos des caractéristiques algorithmiques](/help/using/features/algorithmic-models/understanding-models.md)
* [Exclusion des caractéristiques - Tutoriel](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)
