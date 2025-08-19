---
description: Le rapport de chevauchement des annonces publicitaires s’affiche sous la forme d’un graphique thermique qui met en évidence les chevauchements faibles et élevés entre vos annonces publicitaires.
seo-description: The Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units.
seo-title: Ad Unit Overlap
solution: Audience Manager
title: Chevauchement des unités publicitaires
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: Audience Optimization Reports
exl-id: 08b219c6-bf0c-4473-9459-83b3657dfb15
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# Chevauchement des unités publicitaires{#ad-unit-overlap}

Le rapport **[!UICONTROL Ad Unit Overlap]** s’affiche sous la forme d’un graphique thermique qui met en évidence les chevauchements importants et faibles entre vos annonces.

## Cas d’utilisation {#use-cases}

Grâce au rapport **[!UICONTROL Ad Unit Overlap]**, vous pouvez obtenir des informations sur insight à l’endroit où votre audience chevauche vos propriétés web. Le rapport prend en compte vos 100 propriétés les plus liées et vous montre le chevauchement entre elles.

## Utilisation du rapport de chevauchement des unités publicitaires {#using-the-report}

Utilisez les commandes **[!UICONTROL Top N Base Ad Units]** et **[!UICONTROL Top N Overlapping Ad Units]** pour sélectionner le nombre d’annonces publicitaires souhaité pour le chevauchement. Vous pouvez sélectionner un nombre maximal de 100 éléments pour chacun.

Utilisez les commandes **Plage de jours** et **Période** pour ajuster votre plage d’analyse. Notez que les périodes d’analyse de 7 jours et de 30 jours ne sont disponibles que pour les dates du dimanche.

Utilisez les commandes **[!UICONTROL Base Ad Unit]** et **[!UICONTROL Overlap Ad Unit]** pour sélectionner les annonces publicitaires à afficher dans le rapport de chevauchement.

>[!IMPORTANT]
>
>Lors de l’activation de [!UICONTROL Audience Optimization for Publishers], vous devez inclure des métadonnées descriptives pour [!UICONTROL Ad Unit IDs], comme décrit à l’étape 3 de la section [Importer des fichiers de données Google Ad Manager (anciennement DFP) dans Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Ce faisant, vous vous assurez que le rapport détaille la propriété web comme [!UICONTROL Ad Unit] au lieu de la [!UICONTROL Ad Unit ID].

## Interprétation des résultats {#interpreting-results}

Votre rapport [!UICONTROL Ad Unit Overlap] pourrait ressembler à celui ci-dessous. Pointez sur une cellule pour obtenir plus d’informations sur ce chevauchement particulier. Voir les descriptions pour les informations supplémentaires dans le tableau sous l’exemple de rapport.

![](assets/publisher_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> unité publicitaire de chevauchement</span> </p> </td> 
   <td colname="col2"> <p>Nom de l'article en stock. Il peut s’agir, par exemple, de l’un de vos sites web ou d’un article sur votre site web. Dans l'image ci-dessus, les unités publicitaires de base sont les articles 9 à 18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> l’unité publicitaire de base </span> </p> </td> 
   <td colname="col2"> <p>Nom de l'article en stock. Il peut s’agir, par exemple, de l’un de vos sites web ou d’un article sur votre site web. Dans l'image ci-dessus, les unités publicitaires de base sont les articles 1 à 8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nombre D’Unités Publicitaires Uniques De Chevauchement</span> </p> </td> 
   <td colname="col2"> <p>Nombre de vos utilisateurs et utilisatrices qui ont visité les éléments de l’unité publicitaire 9 à 18. Ces informations sont extraites des journaux Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nombre <span class="wintitle">’Unités publicitaires de base uniques</span> </p> </td> 
   <td colname="col2"> <p>Nombre de vos utilisateurs et utilisatrices qui ont visité les éléments 1 à 8 de l’unité publicitaire. Ces informations sont extraites des journaux Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> nombre d’uniques de chevauchement</span> </p> </td> 
   <td colname="col2"> <p>Chevauchement entre vos utilisateurs et utilisatrices qui ont visité une <span class="wintitle"> unité publicitaire de base</span> et <span class="wintitle">’unité publicitaire de chevauchement</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> pourcentage de chevauchement</span> </p> </td> 
   <td colname="col2"> <p>Chevauchement entre vos utilisateurs et utilisatrices qui ont visité une <span class="wintitle"> unité publicitaire de base</span> et <span class="wintitle">’unité publicitaire de chevauchement</span>. Il s’agit du nombre d’<span class="wintitle"> uniques de chevauchement</span> exprimé en pourcentage de l’unité publicitaire de base <span class="wintitle"></span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
