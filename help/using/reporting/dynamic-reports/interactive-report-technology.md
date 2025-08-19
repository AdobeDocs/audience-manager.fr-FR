---
description: Décrit le logiciel sous-jacent qui alimente les rapports interactifs et le planning de mise à jour des données.
seo-description: Describes the underlying software that powers the interactive reports and the data update schedule.
seo-title: Report Technology
solution: Audience Manager
title: Technologie de rapports
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
feature: Overlap Reports
exl-id: 59d875d6-a630-4795-93a7-1d432860f0a1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 0%

---

# Technologie de rapports{#report-technology}

Décrit le logiciel sous-jacent qui alimente les rapports interactifs et le planning de mise à jour des données.

<!-- 

c_report_technology.xml

 -->

## Les rapports interactifs utilisent la technologie Tableau

[!DNL Audience Manager] utilise le logiciel [Tableau](https://www.tableausoftware.com/) pour afficher les données dans les rapports interactifs. Avec [!DNL Tableau], les rapports [!UICONTROL Delivery and Overlap] utilisent des repères visuels et des symboles qui vous aident à :

* Recherchez les caractéristiques de performances élevées et faibles.
* Repérer les caractéristiques et les segments avec un chevauchement faible et élevé des visiteurs uniques.
* Utilisez les données de chevauchement pour créer des segments ciblés.
* Élargissez la portée en identifiant les caractéristiques associées avec un faible chevauchement.

## Planning de mise à jour des données

Les données du rapport sont mises à jour chaque dimanche. La mise à jour traite les données du samedi (jour précédent) au dimanche précédent.

## Formes, couleurs et tailles utilisées dans les rapports interactifs {#shapes-colors-sizes}

La plupart des rapports interactifs affichent les résultats sous forme de formes de tailles et de couleurs différentes. Ce format d’affichage est conçu pour vous aider à donner un sens aux données visuellement, sans avoir à parcourir des lignes et des colonnes de nombres.

<!-- 

r_legend.xml

 -->

### Légende du rapport

Le tableau suivant définit les formes, tailles et couleurs utilisées dans les rapports dynamiques.

<table id="table_EC180A96E3784FC6B81FCFB546C4A3FA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément de données </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Formes</b> </td> 
   <td colname="col2"> 
    <ul id="ul_076773ABD0BB4CE6834ACFA8B3D6AC2E"> 
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">Les cercles indiquent vos propres caractéristiques propriétaires. </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">Les carrés indiquent les caractéristiques tierces. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> Couleurs </b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">Les tons rouges indiquent un chevauchement <i> faible </i>. </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">Les tons verts indiquent un chevauchement <i>élevé</i>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Taille</b> </td> 
   <td colname="col2"> La taille augmente ou diminue en proportion directe par rapport à l’atteinte (nombre ou pourcentage de clics ou d’utilisateurs et utilisatrices uniques sur une caractéristique ou un segment). </td> 
  </tr> 
 </tbody> 
</table>

## Documentation Tableau {#tableau-documentation}

Pour en savoir plus sur les contrôles Tableau visibles dans nos rapports interactifs, reportez-vous à la documentation officielle de [Tableau Server sous Linux 2018.2](https://help.tableau.com/v2018.2/server-linux/en-us/get_started_server.htm)
