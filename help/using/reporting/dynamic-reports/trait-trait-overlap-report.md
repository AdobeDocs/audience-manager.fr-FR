---
description: Renvoie des données sur le nombre d’utilisateurs uniques partagés entre toutes vos caractéristiques propriétaires et tierces.
seo-description: Renvoie des données sur le nombre d’utilisateurs uniques partagés entre toutes vos caractéristiques propriétaires et tierces.
seo-title: Rapport de chevauchement de caractéristiques
solution: Audience Manager
title: Rapport de chevauchement de caractéristiques
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
feature: Rapports de chevauchement
exl-id: cbc933bb-f2af-4ad0-8eb9-cbec1ee952e0
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 8%

---

# Rapport de chevauchement de caractéristiques{#trait-to-trait-overlap-report}

Renvoie des données sur le nombre d’utilisateurs uniques partagés entre toutes vos caractéristiques propriétaires et tierces.

>[!NOTE]
>
>Les rapports de chevauchement en Audience Manager respectent les principes du CCRAC. Vous ne pouvez afficher que les caractéristiques des sources de données auxquelles vous avez accès en fonction du [groupe d’utilisateurs RBAC](/help/using/features/administration/administration-overview.md) auquel vous appartenez.

<!-- 

c_overlap_reports.xml

 -->

## Présentation

Le rapport [!UICONTROL Trait-to-Trait Overlap] renvoie des données sur le pourcentage d&#39;utilisateurs uniques partagés entre vos propres caractéristiques et celles de vos tiers. En tant qu&#39;outil d&#39;optimisation, ce rapport vous aide à :

* Créez des segments présentant un chevauchement élevé ou faible, en fonction de vos besoins. Les caractéristiques avec un chevauchement élevé vous donnent une audience ciblée, mais moins de visiteurs uniques. Les caractéristiques présentant un faible chevauchement peuvent s’avérer utiles pour atteindre un ensemble de visiteurs unique plus grand.
* Valider les données de caractéristiques tierces : Un fort chevauchement entre des caractéristiques propriétaires et tierces similaires suggère que la caractéristique de votre partenaire de données est précise et fiable. Inversement, un faible chevauchement peut indiquer qu’une caractéristique tierce peut ne pas contenir les mêmes informations que votre propre caractéristique propriétaire similaire.
* Trouvez un chevauchement inattendu entre les caractéristiques et utilisez ces informations pour créer des segments innovants.

## Exemple de rapport

L&#39;illustration suivante présente un aperçu général des éléments du rapport [!UICONTROL Trait-to-Trait Overlap].

>[!NOTE]
>
>Le rapport [!UICONTROL Trait-to-Trait Overlap] renvoie un champ vide lorsqu&#39;il compare le même trait à lui-même.

![](assets/trait-to-trait-overlap.png)

## Zoom sur les points de données individuels

Sélectionnez un point individuel pour accéder aux détails des données de vue dans une fenêtre contextuelle. Les actions de clic mettent automatiquement à jour les données affichées dans le rapport.

## Champs de la fenêtre contextuelle Données de chevauchement caractéristiques à caractéristiques définis {#field-definitions}

Décrit les mesures affichées dans la fenêtre contextuelle lorsque vous cliquez sur un point de données individuel.

<!-- 

r_t2t_data_pop.xml

 -->

La fenêtre contextuelle du rapport [!UICONTROL Trait-to-Trait Overlap] contient les mesures ci-dessous. Notez que la mesure unique dans le tableau représente vos *utilisateurs en temps réel*.

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> % de chevauchement</span></b> </td> 
   <td colname="col2"> Indique le pourcentage de chevauchement unique entre les caractéristiques comparées (valeurs uniques de chevauchement/caractéristiques uniques). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Type de source de données</span></b> </td> 
   <td colname="col2">Définit le type de source de données auquel appartient une caractéristique. Peut être : 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Propriétaire (votre propre caractéristique). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Tiers (provenant d’un partenaire/fournisseur de données externe). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID de caractéristique se chevauchant</span></b> </td> 
   <td colname="col2"> ID numérique unique pour la caractéristique qui se chevauche. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nom de caractéristique en chevauchement</span></b> </td> 
   <td colname="col2"> Nom de la caractéristique qui se superpose. </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle"> ID de caractéristique 2</span></b> </td> 
   <td colname="col2"> Identifiant numérique unique pour la caractéristique de votre source de données de base. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nom de la caractéristique 2</span></b> </td> 
   <td colname="col2"> Nom de la caractéristique de votre source de données de base. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Chevauchement de valeurs uniques</span></b> </td> 
   <td colname="col2"> <p>Pour obtenir le pourcentage de chevauchement, l’Audience Manager utilise la formule suivante :</p> <p>Uniques superposées / (Uniques de caractéristiques de base + Uniques de caractéristiques superposées - Uniques superposées)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Uniques de caractéristiques superposées</span></b> </td> 
   <td colname="col2"> Nombre de visiteurs uniques provenant d’une caractéristique qui se chevauche. </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle"> Uniques de caractéristiques de base</span></b> </td> 
   <td colname="col2"> Nombre de visiteurs uniques provenant de la caractéristique de base. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtrage des résultats du rapport avec les curseurs de données](../../reporting/dynamic-reports/data-sliders.md)
>* [Formes, couleurs et tailles utilisées dans les rapports dynamiques](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Explication des icônes et outils du rapport](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Rapports de chevauchement : mise à jour des plannings et des tailles de segment minimum](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Échantillonnage de données et taux d’erreur dans les rapports Audience Manager sélectionnés...](../../reporting/report-sampling.md)
>* [Fichiers CSV pour les rapports de chevauchement](../../reporting/dynamic-reports/overlap-csv-files.md)

