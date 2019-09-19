---
description: Le rapport Chevauchement d’unité publicitaire s’affiche sous forme de graphique thermique qui met en évidence les chevauchements élevés et faibles entre vos unités publicitaires.
seo-description: Le rapport Chevauchement d’unité publicitaire s’affiche sous forme de graphique thermique qui met en évidence les chevauchements élevés et faibles entre vos unités publicitaires.
seo-title: Chevauchement d’unité publicitaire
solution: Audience Manager
title: Chevauchement d’unité publicitaire
uuid: e4467e81-acbf-474e-b501-89d57395651f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Chevauchement d’unité publicitaire{#ad-unit-overlap}

Le **[!UICONTROL Ad Unit Overlap]** rapport s’affiche sous la forme d’un graphique thermique qui met en évidence les chevauchements élevés et faibles entre vos unités publicitaires.

## Cas d’utilisation {#use-cases}

Grâce au **[!UICONTROL Ad Unit Overlap]** rapport, vous pouvez savoir où votre audience chevauche vos propriétés Web. Le rapport prend en compte vos 100 principales propriétés liées et vous montre le chevauchement entre elles.

## Utilisation du rapport Chevauchement d’unité publicitaire {#using-the-report}

Utilisez les commandes **[!UICONTROL Top N Base Ad Units]** et **[!UICONTROL Top N Overlapping Ad Units]** pour sélectionner le nombre d’unités publicitaires souhaité pour le chevauchement. Vous pouvez sélectionner un nombre maximum de 100 éléments pour chaque élément.

Utilisez les commandes **Plage** de jour et **Date jusqu’au bout** pour ajuster la plage de retour arrière. Notez que les périodes de 7 jours et de 30 jours sont disponibles uniquement pour les dates du dimanche.

Utilisez les **[!UICONTROL Base Ad Unit]** commandes et les **[!UICONTROL Overlap Ad Unit]** commandes pour sélectionner les unités publicitaires à afficher dans le rapport de chevauchement.

>[!IMPORTANT]
>
>Lors de l’activation [!UICONTROL Audience Optimization for Publishers], vous devez inclure des métadonnées descriptives pour [!UICONTROL Ad Unit IDs], comme décrit à l’étape 3 de l’ [importation de fichiers de données DFP dans Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Vous garantissez ainsi que le rapport indique la propriété web comme [!UICONTROL Ad Unit] au lieu de la propriété [!UICONTROL Ad Unit ID].

## Interprétation des résultats {#interpreting-results}

Votre [!UICONTROL Ad Unit Overlap] rapport pourrait ressembler à celui ci-dessous. Passez la souris sur une cellule pour obtenir plus d’informations sur ce chevauchement particulier. Voir la description des informations supplémentaires dans le tableau ci-dessous.

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
   <td colname="col1"> <p><span class="wintitle"> Unité publicitaire de chevauchement</span> </p> </td> 
   <td colname="col2"> <p>Nom de votre article de stock. Par exemple, il peut s’agir de l’un de vos sites Web ou d’un article de votre site Web. Dans l'image ci-dessus, les unités publicitaires de base sont les articles 9 à 18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Unité d'annonce de base</span> </p> </td> 
   <td colname="col2"> <p>Nom de votre article de stock. Par exemple, il peut s’agir de l’un de vos sites Web ou d’un article de votre site Web. Dans l'image ci-dessus, les unités publicitaires de base sont les articles 1 à 8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nombre d'unités publicitaires de chevauchement</span> </p> </td> 
   <td colname="col2"> <p>Nombre d’utilisateurs qui ont consulté les éléments 9 à 18 de l’unité publicitaire. Ces informations sont extraites des journaux DFP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nombre d'unités d'annonce de base uniques</span> </p> </td> 
   <td colname="col2"> <p>Nombre d’utilisateurs qui ont consulté les éléments 1 à 8 de l’unité publicitaire. Ces informations sont extraites des journaux DFP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nombre de chevauchements uniques</span> </p> </td> 
   <td colname="col2"> <p>chevauchement entre vos utilisateurs qui ont visité une unité <span class="wintitle"> publicitaire</span> de base et une unité <span class="wintitle"></span>publicitaire de chevauchement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Pourcentage de chevauchement</span> </p> </td> 
   <td colname="col2"> <p>chevauchement entre vos utilisateurs qui ont visité une unité <span class="wintitle"> publicitaire</span> de base et une unité <span class="wintitle"></span>publicitaire de chevauchement. Il s’agit du nombre <span class="wintitle"> unique de chevauchement</span>, exprimé en pourcentage de l’unité <span class="wintitle"> publicitaire</span>de base. </p> </td> 
  </tr> 
 </tbody> 
</table>
