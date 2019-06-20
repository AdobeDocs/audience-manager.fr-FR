---
description: Renvoie des données sur le nombre d'utilisateurs uniques partagés entre une caractéristique particulière et un segment entier.
seo-description: Renvoie des données sur le nombre d'utilisateurs uniques partagés entre une caractéristique particulière et un segment entier.
seo-title: Rapport de chevauchement de segments et de caractéristiques
solution: Audience Manager
title: Rapport de chevauchement de segments et de caractéristiques
uuid: a 6 b 3 dd 21-332 e -449 f-aa 01-2 beb 47 f 1794 e
translation-type: tm+mt
source-git-commit: 8f2ec880cbbe2f516ebc240a712337dc09c4e7f7

---


# Rapport de chevauchement de segments et de caractéristiques{#segment-to-trait-overlap-report}

Renvoie des données sur le nombre d&#39;utilisateurs uniques partagés entre une caractéristique particulière et un segment entier.

>[!NOTE]
>
>Les rapports de chevauchement dans Audience Manager respectent les principes RBAC. You can only see segments and traits from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

<!-- 

c_segment_trait_overlap.xml

 -->

## Aperçu

As an optimization tool, the [!UICONTROL Segment to Trait Overlap] reports helps you build highly focused segments or expand segment reach. Par exemple, vous pouvez créer des segments et caractéristiques ciblés avec un chevauchement élevé pour atteindre une audience particulière. Cependant, un chevauchement important peut impliquer moins d&#39;utilisateurs uniques (moins de portée). L&#39;exécution de ce rapport pour accroître la portée en supprimant les caractéristiques avec un fort chevauchement de segments et en les remplaçant par des caractéristiques qui se chevauchent moins.

### Exemple de rapport

The following illustration provides a high-level overview of the [!UICONTROL Segment-to-Trait Overlap] report.

![](assets/segment-to-trait-overlap.png)

### Exploration des points de données individuels

Sélectionnez un point individuel pour afficher les détails des données dans une fenêtre contextuelle. Les actions de clic mettent automatiquement à jour les données affichées dans le rapport.

## Comparing Segments to Traits {#comparing-segments-to-traits}

Décrit la manière dont vous pouvez comparer des segments et des caractéristiques afin de déduire des informations significatives à partir des résultats.

<!-- 

c_compare_s2t.xml

 -->

### Comparaison des caractéristiques et des segments uniques : Un exemple

À première vue, il peut sembler illogique de comparer les segments aux caractéristiques et de tenter de dessiner des conclusions à partir des résultats. Après tout, les segments et caractéristiques sont différents. Par conséquent, comment les données dérivées des éléments disparates ont-elles des significations ? Dans ce cas, toutefois, nous ne comparons pas les caractéristiques et les segments, mais le nombre de visiteurs uniques partagés entre eux. Le nombre de visiteurs uniques partagé fournit la valeur courante qui rend un segment possible de comparer les caractéristiques possibles.

Le diagramme suivant illustre la relation entre une caractéristique et le segment auquel elle appartient. Dans ce cas, nous avons une caractéristique avec 10 visiteurs et un segment avec 1 000 visiteurs. Ils partagent 3 visiteurs uniques en commun.

![](assets/s2t.png)

Le nombre de visiteurs uniques est la valeur constante commune partagée entre ces différentes classes d&#39;objets. Par conséquent, vous pouvez déterminer la relation des visiteurs uniques entre eux, comme suit :

* La caractéristique partage 30 % de ses visiteurs uniques avec le segment (3/10 = 0.30).
* Le segment partage 0,3 % de ses visiteurs uniques avec la caractéristique (1 000 = 0,003)

### Rechercher une valeur dans les comparaisons de caractéristiques

L&#39;examen du chevauchement entre les caractéristiques et les segments peut vous aider à estimer le pool de visiteurs total disponible (prévisions) ou à trouver des segments inefficaces avec trop de chevauchement.

<table id="table_5B211EF95216426299EB20253A5A9C1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cas d’utilisation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Prévisions</b> </td> 
   <td colname="col2"> <p>Pour déterminer le pool de visiteurs disponible, additionnez la différence entre la caractéristique totale (moins superposée) et le total du segment (moins de chevauchement). </p> <p>Cette combinaison de caractéristique de segment peut atteindre jusqu'à 1004 nouveaux utilisateurs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Rechercher des segments inefficaces</b> </td> 
   <td colname="col2"> <p>If a trait is part of an <span class="wintitle"> AND</span> group in a segment definition, the unique visitors who have that trait are already in the segment and not available for adding to the segment. Vous pouvez utiliser ce rapport pour rechercher des caractéristiques pertinentes avec un chevauchement faible et les ajouter à la définition de segment, augmentant ainsi la portée du pool d'audiences du segment. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Understanding the Data Filters in the Segment-to-Trait Overlap Report {#data-filters-s2t-report}

Décrit le fonctionnement de la caractéristique et le chevauchement des % curseurs uniques.

<!-- 

r_s2t_sliders.xml

 -->

The [!UICONTROL Segment-to-Trait overlap] report lets you use two sliders to filter data by the overlap % by trait or segment.

* **[!UICONTROL Filter Trait Uniques %:]** Filtre les données par pourcentage de visiteurs uniques partagés entre la caractéristique et le segment.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** Filtre les données par pourcentage de visiteurs uniques partageant le segment et la caractéristique.

### Exemple

Le diagramme suivant illustre la différence entre la caractéristique % et le segment %. Dans ce cas, la caractéristique et le segment partagent 3 visiteurs uniques. En tant que proportions :

* La caractéristique partage 30 % de ses visiteurs uniques avec le segment (3/10 = 0.30).
* Le segment partage 0,3 % de ses visiteurs uniques avec la caractéristique (1 000 = 0,003)

![](assets/s2t.png)

## Segment-to-Trait Data Pop Fields Defined {#fields-defined}

Décrit les mesures affichées dans la fenêtre contextuelle lorsque vous cliquez sur un point de données individuel.

<!-- 

r_s2t_data_pop.xml

 -->

The popup for the [!UICONTROL Segment-to-Trait Overlap] report contains the metrics below. Note that the uniques metric in the table represents your *real-time users*.

<table id="table_4AF72754276242FFB11543635B43AD90"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID de segment</span></b> </td> 
   <td colname="col2"> Identifiant numérique unique du segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nom du fournisseur de données</span></b> </td> 
   <td colname="col2"> Nom du propriétaire du segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Type de fournisseur de données</span></b> </td> 
   <td colname="col2">Définit le type de fournisseur auquel appartient une caractéristique. Peut être : 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Propriétaire (votre propre caractéristique). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Tiers (auprès d'un partenaire/fournisseur de données externe). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> SID</span></b> </td> 
   <td colname="col2"> Identifiant numérique unique du segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nom du SID</span></b> </td> 
   <td colname="col2"> Nom du segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Chevauchement des caractéristiques % %</span></b> </td> 
   <td colname="col2"> % des visiteurs uniques partagent une caractéristique avec le segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Chevauchement des valeurs uniques % %</span></b> </td> 
   <td colname="col2"> % des visiteurs uniques qu'un segment partage avec une caractéristique. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Chevauchement uniques</span></b> </td> 
   <td colname="col2"> Nombre de visiteurs uniques partagés entre le segment et la caractéristique. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Segments uniques</span></b> </td> 
   <td colname="col2"> Nombre de visiteurs uniques dans le segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Caractéristiques uniques</span></b> </td> 
   <td colname="col2"> Nombre de visiteurs uniques dans la caractéristique. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Filtrage des résultats du rapport avec les curseurs de données](../../reporting/dynamic-reports/data-sliders.md)
>* [Formes, couleurs et tailles utilisées dans les rapports interactifs](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Icônes de rapport et outils expliqués](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Rapports de chevauchement : Mettre à jour la planification et la taille minimale du segment](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Taux d&#39;échantillonnage des données et taux d&#39;erreur dans les rapports Audience Manager sélectionnés…](../../reporting/report-sampling.md)
>* [Fichiers CSV pour les rapports de chevauchement](../../reporting/dynamic-reports/overlap-csv-files.md)