---
description: Renvoie des données sur le nombre d’utilisateurs uniques partagés entre une caractéristique particulière et un segment entier.
seo-description: Renvoie des données sur le nombre d’utilisateurs uniques partagés entre une caractéristique particulière et un segment entier.
seo-title: Rapport de chevauchement de segments et de caractéristiques
solution: Audience Manager
title: Rapport de chevauchement de segments et de caractéristiques
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 5%

---


# Rapport de chevauchement de segments et de caractéristiques{#segment-to-trait-overlap-report}

Renvoie des données sur le nombre d’utilisateurs uniques partagés entre une caractéristique particulière et un segment entier.

>[!NOTE]
>
>Les rapports de chevauchement en Audience Manager respectent les principes du CCRAC. Vous pouvez uniquement afficher les segments et les caractéristiques des sources de données auxquelles vous avez accès en fonction du groupe [d’utilisateurs](/help/using/features/administration/administration-overview.md) RBAC auquel vous appartenez.

<!-- 

c_segment_trait_overlap.xml

 -->

## Présentation

En tant qu’outil d’optimisation, les [!UICONTROL Segment to Trait Overlap] rapports vous aident à créer des segments très ciblés ou à étendre la portée des segments. Par exemple, vous pouvez créer des segments ciblés et des caractéristiques présentant un chevauchement élevé pour atteindre une audience particulière. Cependant, un grand chevauchement peut signifier moins d&#39;utilisateurs uniques (moins de portée). L’exécution de ce rapport permet d’élargir la portée en supprimant les caractéristiques présentant un fort chevauchement de segments et en les remplaçant par des caractéristiques présentant moins de chevauchement.

### Exemple de rapport

L’illustration suivante présente un aperçu général du [!UICONTROL Segment-to-Trait Overlap] rapport.

![](assets/segment-to-trait-overlap.png)

### Zoom sur les points de données individuels

Sélectionnez un point individuel pour accéder aux détails des données de vue dans une fenêtre contextuelle. Les actions de clic mettent automatiquement à jour les données affichées dans le rapport.

## Comparaison de segments aux caractéristiques {#comparing-segments-to-traits}

Décrit comment comparer des segments et des caractéristiques afin de tirer des informations significatives des résultats.

<!-- 

c_compare_s2t.xml

 -->

### Comparaison des caractéristiques et des segments uniques : Exemple

À première vue, il peut sembler illogique de comparer les segments aux caractéristiques et de tenter de tirer des conclusions des résultats. Après tout, les segments et les caractéristiques sont différents, alors comment les données dérivées d&#39;éléments disparates peuvent-elles avoir un sens ? Cependant, dans ce cas, nous ne comparons pas les caractéristiques et les segments, mais le nombre de visiteurs uniques partagés entre eux. Le nombre de visiteurs uniques partagés fournit la valeur commune qui rend possible une comparaison segment/caractéristique.

Le diagramme suivant illustre la relation entre une caractéristique et le segment auquel elle appartient. Dans ce cas, nous avons un trait avec 10 visiteurs et un segment avec 1000 visiteurs. Ils partagent 3 visiteurs uniques en commun.

![](assets/s2t.png)

Le nombre de visiteurs uniques est la valeur constante commune partagée entre ces différentes classes d’objets. Par conséquent, vous pouvez déterminer la relation de visiteur unique entre eux comme suit :

* La caractéristique partage 30 % de ses visiteurs uniques avec le segment (3/10 = 0,30).
* Le segment partage 0,3 % de ses visiteurs uniques avec la caractéristique (3/1 000 = 0,003)

### Rechercher une valeur dans les comparaisons de segment à caractéristiques

L’examen du chevauchement entre les caractéristiques et les segments peut vous aider à estimer le pool de visiteurs (prévisions) disponible total ou à trouver des segments inefficaces avec trop de chevauchements.

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
   <td colname="col2"> <p>Pour déterminer le pool de visiteurs disponible, additionnez la différence entre le total des caractéristiques (moins de chevauchement) et le total des segments (moins de chevauchement). </p> <p>Cette combinaison segment-caractéristique peut atteindre jusqu’à 1 004 nouveaux utilisateurs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Rechercher des segments inefficaces</b> </td> 
   <td colname="col2"> <p>Si une caractéristique fait partie d’un groupe <span class="wintitle"> ET</span> dans une définition de segment, les visiteurs uniques qui en ont font partie se trouvent déjà dans le segment et ne peuvent pas être ajoutés au segment. Vous pouvez utiliser ce rapport pour trouver des caractéristiques pertinentes avec un faible chevauchement et les ajouter à la définition de segment, augmentant ainsi la portée de ce pool d’audiences de segment. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Présentation des Filtres de données dans le rapport de chevauchement segment-à-caractéristique {#data-filters-s2t-report}

Décrit le fonctionnement des curseurs % de chevauchement de caractéristiques et de segments uniques.

<!-- 

r_s2t_sliders.xml

 -->

Le [!UICONTROL Segment-to-Trait overlap] rapport vous permet d’utiliser deux curseurs pour filtrer les données selon le pourcentage de chevauchement par caractéristique ou segment.

* **[!UICONTROL Filter Trait Uniques %:]** Filtres les données en fonction du pourcentage de visiteurs uniques partagés entre la caractéristique et le segment.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** Filtres les données selon le pourcentage de visiteurs uniques qui se partagent entre le segment et la caractéristique.

### Exemple

Le diagramme suivant illustre la différence entre le pourcentage de caractéristiques et le pourcentage de segments. Dans ce cas, la caractéristique et le segment partagent 3 visiteurs uniques. En proportions :

* La caractéristique partage 30 % de ses visiteurs uniques avec le segment (3/10 = 0,30).
* Le segment partage 0,3 % de ses visiteurs uniques avec la caractéristique (3/1 000 = 0,003)

![](assets/s2t.png)

## Définition des champs de fenêtre contextuelle de données segment-à-caractéristique {#fields-defined}

Décrit les mesures affichées dans la fenêtre contextuelle lorsque vous cliquez sur un point de données individuel.

<!-- 

r_s2t_data_pop.xml

 -->

La fenêtre contextuelle du [!UICONTROL Segment-to-Trait Overlap] rapport contient les mesures ci-dessous. Notez que les mesures uniques du tableau représentent vos utilisateurs ** en temps réel.

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
   <td colname="col2"> ID numérique unique du segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Source de données de caractéristiques </span></b> </td> 
   <td colname="col2"> Nom du propriétaire de la caractéristique. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Type de source de données</span></b> </td> 
   <td colname="col2">Définit le type de fournisseur auquel appartient une caractéristique. Peut être : 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Propriétaire (votre propre caractéristique). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Tiers (provenant d’un partenaire/fournisseur de données externe). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID de caractéristique</span></b> </td> 
   <td colname="col2"> ID numérique unique de la caractéristique. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nom du trait</span></b> </td> 
   <td colname="col2"> Nom de la caractéristique. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Pourcentage de chevauchement des caractéristiques uniques</span></b> </td> 
   <td colname="col2"> % des visiteurs uniques qu’une caractéristique partage avec le segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> % de chevauchement des segments uniques</span></b> </td> 
   <td colname="col2"> % des visiteurs uniques qu’un segment partage avec une caractéristique. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Chevauchement de valeurs uniques</span></b> </td> 
   <td colname="col2"> Nombre de visiteurs uniques partagés entre le segment et la caractéristique. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Uniques de segments</span></b> </td> 
   <td colname="col2"> Nombre de visiteurs uniques dans le segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Caractéristiques uniques</span></b> </td> 
   <td colname="col2"> Nombre de visiteurs uniques dans la caractéristique. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtrage des résultats du rapport avec les curseurs de données](../../reporting/dynamic-reports/data-sliders.md)
>* [Formes, couleurs et tailles utilisées dans les rapports interactifs](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Explication des icônes et outils du rapport](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Rapports de chevauchement : mise à jour des plannings et des tailles de segment minimum](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Échantillonnage de données et taux d’erreur dans les rapports Audience Manager sélectionnés...](../../reporting/report-sampling.md)
>* [Fichiers CSV pour les rapports de chevauchement](../../reporting/dynamic-reports/overlap-csv-files.md)