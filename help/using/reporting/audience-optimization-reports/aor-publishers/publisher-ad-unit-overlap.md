---
description: Le rapport Chevauchement d’unité publicitaire s’affiche sous forme d’un graphique à chaleur qui présente les chevauchements élevés et faibles entre vos unités publicitaires.
seo-description: Le rapport Chevauchement d’unité publicitaire s’affiche sous forme d’un graphique à chaleur qui présente les chevauchements élevés et faibles entre vos unités publicitaires.
seo-title: Chevauchement d’unité publicitaire
solution: Audience Manager
title: Chevauchement d’unité publicitaire
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: Rapports d’Audience Optimization
exl-id: 08b219c6-bf0c-4473-9459-83b3657dfb15
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 3%

---

# Chevauchement d’unité publicitaire{#ad-unit-overlap}

Le rapport **[!UICONTROL Ad Unit Overlap]** s’affiche sous forme d’un graphique à chaleur qui présente les chevauchements élevés et faibles entre vos unités publicitaires.

## Cas d’utilisation {#use-cases}

Grâce au rapport **[!UICONTROL Ad Unit Overlap]**, vous pouvez mieux comprendre où votre audience se superpose sur vos propriétés web. Le rapport prend en compte vos 100 propriétés les plus liées et vous montre le chevauchement entre elles.

## Utilisation du rapport de chevauchement d’unité publicitaire {#using-the-report}

Utilisez les contrôles **[!UICONTROL Top N Base Ad Units]** et **[!UICONTROL Top N Overlapping Ad Units]** pour sélectionner le nombre d’unités d’annonce souhaité pour le chevauchement. Vous pouvez sélectionner un nombre maximal de 100 éléments pour chaque élément.

Utilisez les commandes **Période** et **Date d’expiration** pour ajuster la période d’analyse. Notez que les périodes d’analyse de 7 et 30 jours ne sont disponibles que pour les dates du dimanche.

Utilisez les contrôles **[!UICONTROL Base Ad Unit]** et **[!UICONTROL Overlap Ad Unit]** pour sélectionner les unités publicitaires à afficher dans le rapport de chevauchement.

>[!IMPORTANT]
>
>Lors de l’activation de [!UICONTROL Audience Optimization for Publishers], vous devez inclure des métadonnées descriptives pour [!UICONTROL Ad Unit IDs], comme décrit à l’étape 3 de la section [Importation de fichiers de données Google Ad Manager (anciennement DFP) dans l’Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Vous pouvez ainsi vous assurer que le rapport présente la propriété web sous la forme [!UICONTROL Ad Unit] au lieu de [!UICONTROL Ad Unit ID].

## Interprétation des résultats {#interpreting-results}

Votre rapport [!UICONTROL Ad Unit Overlap] pourrait ressembler à celui ci-dessous. Passez la souris sur une cellule pour obtenir plus d’informations sur ce chevauchement particulier. Consultez les descriptions des informations supplémentaires dans le tableau ci-dessous de l’exemple de rapport.

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
   <td colname="col1"> <p><span class="wintitle"> Chevauchement de l’unité publicitaire</span> </p> </td> 
   <td colname="col2"> <p>Nom de votre article de stock. Il peut s’agir, par exemple, de l’un de vos sites web ou d’un article de votre site web. Dans l’image ci-dessus, les unités de publicité de base sont les articles 9 à 18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Unité publicitaire de base</span> </p> </td> 
   <td colname="col2"> <p>Nom de votre article de stock. Il peut s’agir, par exemple, de l’un de vos sites web ou d’un article de votre site web. Dans l’image ci-dessus, les unités de publicité de base sont les articles 1 à 8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Chevauchement du nombre d’unités publicitaires uniques</span> </p> </td> 
   <td colname="col2"> <p>Nombre de vos utilisateurs qui ont consulté les éléments 9 à 18 de l’unité publicitaire. Ces informations sont extraites des journaux Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nombre unique d’unités publicitaires de base</span> </p> </td> 
   <td colname="col2"> <p>Nombre de vos utilisateurs qui ont consulté les éléments 1 à 8 de l’unité publicitaire. Ces informations sont extraites des journaux Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nombre unique de chevauchements</span> </p> </td> 
   <td colname="col2"> <p>Chevauchement entre vos utilisateurs qui ont visité une <span class="wintitle"> unité publicitaire de base</span> et <span class="wintitle"> unité publicitaire de chevauchement</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Pourcentage de chevauchement</span> </p> </td> 
   <td colname="col2"> <p>Chevauchement entre vos utilisateurs qui ont visité une <span class="wintitle"> unité publicitaire de base</span> et <span class="wintitle"> unité publicitaire de chevauchement</span>. Il s’agit du <span class="wintitle"> nombre unique de chevauchement</span>, exprimé en pourcentage de l’ <span class="wintitle"> unité publicitaire de base</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
