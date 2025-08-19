---
description: Renvoie des données sur le nombre d’utilisateurs uniques partagés entre une caractéristique particulière et un segment entier.
seo-description: Returns data on the number of unique users shared between a particular trait and an entire segment.
seo-title: Segment-to-Trait Overlap Report
solution: Audience Manager
title: Rapport de chevauchement de segments à caractéristiques
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
feature: Overlap Reports
exl-id: 7ce3dd2d-ab22-46f8-90bf-a32222df2e76
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 3%

---

# Rapport de chevauchement de segments à caractéristiques{#segment-to-trait-overlap-report}

Renvoie des données sur le nombre d’utilisateurs uniques partagés entre une caractéristique particulière et un segment entier.

>[!NOTE]
>
>Les rapports de chevauchement dans Audience Manager respectent les principes RBAC. Vous pouvez uniquement afficher les segments et les caractéristiques des sources de données auxquelles vous avez accès en fonction du [Groupe d’utilisateurs RBAC](/help/using/features/administration/administration-overview.md) auquel vous appartenez.

<!-- 

c_segment_trait_overlap.xml

 -->

## Présentation

En tant qu’outil d’optimisation, les rapports [!UICONTROL Segment to Trait Overlap] vous permettent de créer des segments hautement ciblés ou d’étendre la portée des segments. Par exemple, vous pouvez créer des segments et des caractéristiques ciblés avec un chevauchement élevé pour atteindre une audience particulière. Cependant, un chevauchement important peut signifier moins d’utilisateurs uniques (portée moindre). L’exécution de ce rapport permet d’étendre la portée en supprimant les caractéristiques qui présentent un chevauchement important des segments et en les remplaçant par des caractéristiques qui présentent moins de chevauchement.

### Exemple de rapport

L’illustration suivante présente de manière générale le rapport [!UICONTROL Segment-to-Trait Overlap].

![](assets/segment-to-trait-overlap.png)

### Accéder à des points de données individuels

Sélectionnez un point individuel pour afficher les détails des données dans une fenêtre pop-up. Les actions de clic mettent automatiquement à jour les données affichées dans le rapport.

## Comparaison des segments aux caractéristiques {#comparing-segments-to-traits}

Décrit comment comparer des segments et des caractéristiques afin d’obtenir des informations significatives à partir des résultats.

<!-- 

c_compare_s2t.xml

 -->

### Comparaison des caractéristiques et des segments uniques : exemple

À première vue, il peut sembler illogique de comparer des segments à des caractéristiques et de tenter de tirer des conclusions des résultats. Après tout, les segments et les caractéristiques sont différents, alors comment les données dérivées d’éléments disparates peuvent-elles avoir un sens ? Cependant, dans ce cas, nous ne comparons pas les caractéristiques et les segments, mais le nombre de visiteurs uniques partagés entre eux. Le nombre de visiteurs uniques partagés fournit la valeur commune qui rend possible la comparaison d’un segment à une caractéristique.

Le diagramme suivant illustre la relation entre une caractéristique et le segment auquel elle appartient. Dans ce cas, nous avons une caractéristique avec 10 visiteurs et un segment avec 1 000 visiteurs. Ils partagent 3 visiteurs uniques en commun.

![](assets/s2t.png)

Le nombre de visiteurs uniques est la valeur commune et constante partagée entre ces différentes classes d’objets. Par conséquent, vous pouvez déterminer la relation de visiteur unique entre eux comme suit :

* La caractéristique partage 30 % de ses visiteurs uniques avec le segment (3/10 = 0,30).
* Le segment partage 0,3 % de ses visiteurs uniques avec la caractéristique (3/1 000 = 0,003)

### Rechercher une valeur dans les comparaisons de segments et de caractéristiques

L’examen du chevauchement entre les caractéristiques et les segments peut vous aider à estimer le nombre total de visiteurs disponibles (prévisions) ou à trouver des segments inefficaces présentant un chevauchement trop important.

<table id="table_5B211EF95216426299EB20253A5A9C1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cas d’utilisation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Prévision</b> </td> 
   <td colname="col2"> <p>Pour déterminer le pool de visiteurs disponible, additionnez la différence entre le total des caractéristiques (moins le chevauchement) et le total des segments (moins le chevauchement). </p> <p>Cette combinaison segment-caractéristique pourrait atteindre jusqu’à 1 004 nouveaux utilisateurs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Rechercher les segments inefficaces</b> </td> 
   <td colname="col2"> <p>Si une caractéristique fait partie d’un groupe ET <span class="wintitle"> dans une définition de segment</span> les visiteurs et visiteuses uniques qui possèdent cette caractéristique se trouvent déjà dans le segment et ne sont pas disponibles pour être ajoutés au segment. Vous pouvez utiliser ce rapport pour trouver les caractéristiques pertinentes avec peu de chevauchement et les ajouter à la définition de segment, augmentant ainsi la portée de ce pool d’audiences de segment. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Comprendre les filtres de données dans le rapport de chevauchement segment à caractéristique {#data-filters-s2t-report}

Décrit le fonctionnement des curseurs % de chevauchement unique des caractéristiques et des segments.

<!-- 

r_s2t_sliders.xml

 -->

Le rapport [!UICONTROL Segment-to-Trait overlap] vous permet d’utiliser deux curseurs pour filtrer les données en fonction du pourcentage de chevauchement par caractéristique ou segment.

* **[!UICONTROL Filter Trait Uniques %:]** Filtre les données en fonction du % de visiteurs uniques partagés entre la caractéristique et le segment.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** Filtre les données en fonction du % de visiteurs uniques qui se partagent le segment et la caractéristique.

### Exemple

Le diagramme suivant illustre la différence entre la caractéristique unique % et le segment unique %. Dans ce cas, la caractéristique et le segment partagent 3 visiteurs uniques. En proportions :

* La caractéristique partage 30 % de ses visiteurs uniques avec le segment (3/10 = 0,30).
* Le segment partage 0,3 % de ses visiteurs uniques avec la caractéristique (3/1 000 = 0,003)

![](assets/s2t.png)

## Champs de pop de données segment à caractéristique définis {#fields-defined}

Décrit les mesures affichées dans la fenêtre contextuelle lorsque vous cliquez sur un point de données individuel.

<!-- 

r_s2t_data_pop.xml

 -->

La fenêtre contextuelle du rapport [!UICONTROL Segment-to-Trait Overlap] contient les mesures ci-dessous. Notez que la mesure uniques du tableau représente vos *utilisateurs en temps réel*.

<table id="table_4AF72754276242FFB11543635B43AD90"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> l’identifiant de segment </span></b> </td> 
   <td colname="col2"> Identifiant numérique unique du segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> </span></b> Trait Data Source </td> 
   <td colname="col2"> Nom du propriétaire de la caractéristique. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> type de Source de données</span></b> </td> 
   <td colname="col2">Définit le type de fournisseur auquel appartient une caractéristique. Peut être : 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Propriétaire (votre propre caractéristique). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Tiers (partenaires/fournisseurs de données externes). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1">ID <b><span class="wintitle"> caractéristique </span></b> </td> 
   <td colname="col2"> ID numérique unique de la caractéristique. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Nom de la caractéristique <b><span class="wintitle"></span></b> </td> 
   <td colname="col2"> Nom de la caractéristique. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Caractéristiques Uniques Se Chevauchent %</span></b> </td> 
   <td colname="col2"> % de visiteurs uniques dont une caractéristique est partagée avec le segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Segments Uniques Se Chevauchent %</span></b> </td> 
   <td colname="col2"> % de visiteurs uniques qu’un segment partage avec une caractéristique. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> les uniques de chevauchement</span></b> </td> 
   <td colname="col2"> Nombre de visiteurs uniques partagés entre le segment et la caractéristique. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> des segments uniques</span></b> </td> 
   <td colname="col2"> Nombre de visiteurs uniques dans le segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> uniques</span></b> </td> 
   <td colname="col2"> Nombre de visiteurs uniques dans la caractéristique. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtrage des résultats du rapport avec les curseurs de données](../../reporting/dynamic-reports/data-sliders.md)
>* [Formes, couleurs et tailles utilisées dans les rapports interactifs](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* Présentation des icônes et des outils de rapport [](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Rapports de chevauchement : mise à jour des plannings et des tailles de segment minimum](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Échantillonnage des données et taux d’erreur dans certains rapports Audience Manager...](../../reporting/report-sampling.md)
>* [Fichiers CSV pour les rapports de chevauchement](../../reporting/dynamic-reports/overlap-csv-files.md)
