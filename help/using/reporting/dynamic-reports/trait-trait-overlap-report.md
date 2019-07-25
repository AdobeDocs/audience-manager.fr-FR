---
description: Renvoie des données sur le nombre d'utilisateurs uniques partagés parmi toutes vos première et tierce caractéristiques.
seo-description: Renvoie des données sur le nombre d'utilisateurs uniques partagés parmi toutes vos première et tierce caractéristiques.
seo-title: Rapport de chevauchement de caractéristiques
solution: Audience Manager
title: Rapport de chevauchement de caractéristiques
uuid: 7 fb 3 fc 9 e -0 e 0 b -492 a -9 c 3 a -04356 afb 19 c 7
translation-type: tm+mt
source-git-commit: 4dc8aad623198cbc24c5c76ac3818d7ee00e9a5e

---


# Rapport de chevauchement de caractéristiques{#trait-to-trait-overlap-report}

Renvoie des données sur le nombre d'utilisateurs uniques partagés parmi toutes vos première et tierce caractéristiques.

>[!NOTE]
>
>Les rapports de chevauchement dans Audience Manager respectent les principes RBAC. You can only see traits from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

<!-- 

c_overlap_reports.xml

 -->

## Aperçu

[!UICONTROL Trait-to-Trait Overlap] Le rapport renvoie des données sur le pourcentage d'utilisateurs uniques partagés entre toutes vos propres caractéristiques et vos caractéristiques tierces. En tant qu'outil d'optimisation, ce rapport vous aide à :

* Créez des segments avec un chevauchement élevé ou élevé, en fonction de vos besoins. Les caractéristiques présentant un chevauchement élevé vous donnent une audience ciblée, mais moins de visiteurs uniques. Les caractéristiques présentant un chevauchement faible peuvent s'avérer utiles pour atteindre un jeu de visiteurs unique plus large.
* Validation des données de caractéristiques tierces : Un chevauchement fort entre des caractéristiques tierces similaires et des caractéristiques tierces suggère que la caractéristique de votre partenaire de données est précise et fiable. Inversement, un chevauchement faible peut indiquer qu'une caractéristique tierce peut ne pas contenir les mêmes informations que votre propre caractéristique de propriétaire similaire.
* Recherchez un chevauchement inattendu entre les caractéristiques et utilisez ces informations pour créer des segments innovants.

## Exemple de rapport

The following illustration provides a high-level overview of elements in the [!UICONTROL Trait-to-Trait Overlap] report.

>[!NOTE]
>
>The [!UICONTROL Trait-to-Trait Overlap] report returns an empty field when it compares the same trait to itself.

![](assets/trait-to-trait-overlap.png)

## Exploration des points de données individuels

Sélectionnez un point individuel pour afficher les détails des données dans une fenêtre contextuelle. Les actions de clic mettent automatiquement à jour les données affichées dans le rapport.

## Trait-to-Trait Overlap Data Pop Fields Defined {#field-definitions}

Décrit les mesures affichées dans la fenêtre contextuelle lorsque vous cliquez sur un point de données individuel.

<!-- 

r_t2t_data_pop.xml

 -->

The popup for the [!UICONTROL Trait-to-Trait Overlap] report contains the metrics below. Note that the uniques metric in the table represents your *real-time users*.

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nom du fournisseur de données</span></b> </td> 
   <td colname="col2"> Nom du propriétaire de la caractéristique. </td> 
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
   <td colname="col1"><b><span class="wintitle"> ID de caractéristique</span></b> </td> 
   <td colname="col2"> Identifiant numérique unique pour cette caractéristique. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nom de la caractéristique</span></b> </td> 
   <td colname="col2"> Nom de la caractéristique. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Chevauchement %</span></b> </td> 
   <td colname="col2"> Affiche le pourcentage de chevauchement unique entre les caractéristiques (chevauchement uniques/caractéristiques uniques). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Chevauchement uniques</span></b> </td> 
   <td colname="col2"> <p>Pour obtenir le chevauchement %, Audience Manager utilise la formule suivante :</p> <p>Chevauchement des valeurs uniques/(segment de base + chevauchement des segments - uniques se chevauchant)</p> </td> 
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
>* [Formes, couleurs et tailles utilisées dans les rapports dynamiques](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Icônes de rapport et outils expliqués](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Rapports de chevauchement : Mettre à jour la planification et la taille minimale du segment](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Taux d'échantillonnage des données et taux d'erreur dans les rapports Audience Manager sélectionnés…](../../reporting/report-sampling.md)
>* [Fichiers CSV pour les rapports de chevauchement](../../reporting/dynamic-reports/overlap-csv-files.md)