---
description: Renvoie des données sur le nombre d’utilisateurs uniques partagés entre une caractéristique particulière et un segment entier.
seo-description: Returns data on the number of unique users shared between a particular trait and an entire segment.
seo-title: Segment-to-Trait Overlap Report
solution: Audience Manager
title: Rapport de chevauchement de segments et de caractéristiques
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
feature: Overlap Reports
exl-id: 7ce3dd2d-ab22-46f8-90bf-a32222df2e76
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 3%

---

# Rapport de chevauchement de segments et de caractéristiques{#segment-to-trait-overlap-report}

Renvoie des données sur le nombre d’utilisateurs uniques partagés entre une caractéristique particulière et un segment entier.

>[!NOTE]
>
>Les rapports de chevauchement d’Audience Manager respectent les principes du reporting RBAC. Vous ne pouvez afficher que les segments et les caractéristiques des sources de données auxquelles vous avez accès en fonction du [groupe d’utilisateurs RBAC](/help/using/features/administration/administration-overview.md) auquel vous appartenez.

<!-- 

c_segment_trait_overlap.xml

 -->

## Présentation

En tant qu’outil d’optimisation, les rapports [!UICONTROL Segment to Trait Overlap] vous aident à créer des segments très ciblés ou à étendre la portée des segments. Vous pouvez par exemple créer des segments ciblés et des caractéristiques présentant un chevauchement élevé pour atteindre une audience particulière. Cependant, un grand chevauchement peut signifier moins d’utilisateurs uniques (moins de portée). L’exécution de ce rapport permet d’étendre la portée en supprimant les caractéristiques avec un grand chevauchement de segments et en les remplaçant par des caractéristiques qui ont moins de chevauchement.

### Exemple de rapport

L’illustration suivante présente un aperçu général du rapport [!UICONTROL Segment-to-Trait Overlap].

![](assets/segment-to-trait-overlap.png)

### Exploration des points de données individuels

Sélectionnez un point individuel pour afficher les détails des données dans une fenêtre contextuelle. Les actions de clic mettent automatiquement à jour les données affichées dans le rapport.

## Comparaison de segments à des caractéristiques {#comparing-segments-to-traits}

Décrit la manière dont vous pouvez comparer les segments et les caractéristiques afin d’obtenir des informations significatives à partir des résultats.

<!-- 

c_compare_s2t.xml

 -->

### Comparaison des uniques de caractéristiques et de segments : un exemple

À première vue, il peut sembler illogique de comparer les segments aux caractéristiques et d’essayer de tirer des conclusions des résultats. Après tout, les segments et les caractéristiques sont différents, alors comment les données dérivées d’éléments disparates peuvent-elles avoir un sens ? Cependant, dans ce cas, nous ne comparons pas les caractéristiques et les segments, mais le nombre de visiteurs uniques partagés entre eux. Le nombre de visiteurs uniques partagés fournit la valeur commune qui rend possible une comparaison entre les segments et les caractéristiques.

Le diagramme suivant illustre la relation entre une caractéristique et le segment auquel elle appartient. Dans ce cas, nous avons une caractéristique de 10 visiteurs et un segment de 1 000 visiteurs. Ils partagent 3 visiteurs uniques en commun.

![](assets/s2t.png)

Le nombre de visiteurs uniques est la valeur constante commune partagée entre ces différentes classes d’objets. Par conséquent, vous pouvez déterminer la relation du visiteur unique entre eux comme suit :

* La caractéristique partage 30 % de ses visiteurs uniques avec le segment (3/10 = 0,30).
* Le segment partage 0,3 % de ses visiteurs uniques avec la caractéristique (3/1 000 = 0,003).

### Rechercher des valeurs dans les segments par rapport aux comparaisons de caractéristiques

L’examen du chevauchement entre les caractéristiques et les segments peut vous aider à estimer le total du pool de visiteurs disponible (prévision) ou à trouver des segments inefficaces avec trop de chevauchement.

<table id="table_5B211EF95216426299EB20253A5A9C1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cas d’utilisation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Prévisionnel</b> </td> 
   <td colname="col2"> <p>Pour déterminer le pool de visiteurs disponible, additionnez la différence entre le total des caractéristiques (moins de chevauchement) et le total des segments (moins de chevauchement). </p> <p>Cette combinaison segment-caractéristique peut atteindre jusqu’à 1 004 nouveaux utilisateurs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Rechercher des segments inefficaces</b> </td> 
   <td colname="col2"> <p>Si une caractéristique fait partie d’un groupe <span class="wintitle"> ET</span> dans une définition de segment, les visiteurs uniques qui possèdent cette caractéristique sont déjà dans le segment et ne peuvent pas être ajoutés au segment. Vous pouvez utiliser ce rapport pour rechercher des caractéristiques pertinentes avec faible chevauchement et les ajouter à la définition de segment, augmentant ainsi la portée de ce pool d’audiences de ce segment. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Présentation des filtres de données dans le rapport de chevauchement de segments et de caractéristiques {#data-filters-s2t-report}

Décrit le fonctionnement des curseur de pourcentage de chevauchement de caractéristiques et de segments uniques.

<!-- 

r_s2t_sliders.xml

 -->

Le rapport [!UICONTROL Segment-to-Trait overlap] vous permet d’utiliser deux curseurs pour filtrer les données selon le pourcentage de chevauchement par caractéristique ou segment.

* **[!UICONTROL Filter Trait Uniques %:]** Filtre les données en fonction du pourcentage de visiteurs uniques partagés entre la caractéristique et le segment.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** Filtre les données selon le pourcentage de visiteurs uniques partagés entre le segment et la caractéristique.

### Exemple

Le diagramme suivant illustre la différence entre les valeurs uniques des caractéristiques % et les valeurs uniques des segments %. Dans ce cas, la caractéristique et le segment partagent 3 visiteurs uniques. En proportions :

* La caractéristique partage 30 % de ses visiteurs uniques avec le segment (3/10 = 0,30).
* Le segment partage 0,3 % de ses visiteurs uniques avec la caractéristique (3/1 000 = 0,003).

![](assets/s2t.png)

## Définition des champs de variables de données de segment à caractéristique {#fields-defined}

Décrit les mesures affichées dans la fenêtre contextuelle lorsque vous cliquez sur un point de données individuel.

<!-- 

r_s2t_data_pop.xml

 -->

La fenêtre contextuelle du rapport [!UICONTROL Segment-to-Trait Overlap] contient les mesures ci-dessous. Notez que la mesure uniques dans le tableau représente vos *utilisateurs en temps réel*.

<table id="table_4AF72754276242FFB11543635B43AD90"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Identifiant de segment </span></b> </td> 
   <td colname="col2"> Identifiant numérique unique du segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Trait Data Source </span></b> </td> 
   <td colname="col2"> Nom du propriétaire de la caractéristique. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Type de Source de données </span></b> </td> 
   <td colname="col2">Définit le type de fournisseur auquel appartient une caractéristique. Peut être : 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Propriétaire (votre propre caractéristique). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Tiers (provenant d’un partenaire/fournisseur de données externe). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID de caractéristique </span></b> </td> 
   <td colname="col2"> Identifiant numérique unique de la caractéristique. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nom de caractéristique </span></b> </td> 
   <td colname="col2"> Nom de la caractéristique. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Chevauchement des caractéristiques uniques %</span></b> </td> 
   <td colname="col2"> % des visiteurs uniques qu’une caractéristique partage avec le segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Chevauchement de segments uniques %</span></b> </td> 
   <td colname="col2"> % des visiteurs uniques qu’un segment partage avec une caractéristique. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Uniques de chevauchement</span></b> </td> 
   <td colname="col2"> Nombre de visiteurs uniques partagés entre le segment et la caractéristique. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Uniques de segments</span></b> </td> 
   <td colname="col2"> Nombre de visiteurs uniques dans le segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Uniques de caractéristiques</span></b> </td> 
   <td colname="col2"> Nombre de visiteurs uniques dans la caractéristique. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtrage des résultats du rapport avec les curseurs de données](../../reporting/dynamic-reports/data-sliders.md)
>* [Formes, couleurs et tailles utilisées dans les rapports interactifs](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Explication des icônes et outils de rapport](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Rapports de chevauchement : mise à jour des plannings et des tailles de segment minimum](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [ Échantillonnage de données et taux d’erreur dans les rapports d’Audience Manager sélectionnés...](../../reporting/report-sampling.md)
>* [Fichiers CSV pour les rapports de chevauchement](../../reporting/dynamic-reports/overlap-csv-files.md)
