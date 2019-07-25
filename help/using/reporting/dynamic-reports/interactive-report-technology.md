---
description: Décrit le logiciel sous-jacent qui alimente les rapports interactifs et le calendrier de mise à jour des données.
seo-description: Décrit le logiciel sous-jacent qui alimente les rapports interactifs et le calendrier de mise à jour des données.
seo-title: Technologie des rapports
solution: Audience Manager
title: Technologie des rapports
uuid: 5 f 3 d 815 b-e 1 e 6-42 f 2-b 848-ac 035 a 5 aa 77 d
translation-type: tm+mt
source-git-commit: b5a962381780f1a1627e39b59e3ca86fd51763b5

---


# Report Technology{#report-technology}

Décrit le logiciel sous-jacent qui alimente les rapports interactifs et le calendrier de mise à jour des données.

<!-- 

c_report_technology.xml

 -->

## Rapports interactifs Utilisez la technologie Tableau

[!DNL Audience Manager] utilise [le logiciel Tableau](https://www.tableausoftware.com/) pour afficher les données dans les rapports interactifs. With [!DNL Tableau], the [!UICONTROL Delivery and Overlap] reports use visual cues and symbols that help you:

* Recherchez des caractéristiques hautes et faibles.
* Les caractéristiques de spot et les segments dont le visiteur unique est faible et élevé se chevauchent.
* Utilisez des données de chevauchement pour créer des segments ciblés.
* Augmentez la portée en identifiant les caractéristiques associées avec un chevauchement faible.

## Planification de la mise à jour des données

Les données du rapport sont mises à jour chaque dimanche. La mise à jour traite les données du samedi (jour précédent) au dimanche précédent.

## Shapes, Colors, and Sizes Used in Interactive Reports {#shapes-colors-sizes}

La plupart des rapports interactifs affichent des résultats à l'aide de formes de tailles et de couleurs différentes. Ce format d'affichage est conçu pour vous aider à maîtriser visuellement les données sans avoir à parcourir les lignes et colonnes de nombres.

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
     <li id="li_371331AE984A4A999CE0596EA13987E0">Les carrés indiquent des caractéristiques tierces. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Couleurs</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">Red shades indicate <i>low</i> overlap. </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">Green shades indicate <i>high</i> overlap. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Taille</b> </td> 
   <td colname="col2"> La taille augmente ou diminue proportionnellement à la portée (nombre ou pourcentage de clics ou d'utilisateurs uniques dans une caractéristique ou un segment). </td> 
  </tr> 
 </tbody> 
</table>

## Report Icons and Tools Explained {#icons-tools-explained}

Décrit la recherche et l'utilisation des différents outils d'icône utilisés dans les rapports dynamiques.

<!-- 

r_icons.xml

 -->

### Icônes et outils de données

Les icônes ci-dessous sont disponibles au bas de chaque fenêtre de rapport dynamique. L'illustration suivante fournit davantage d'informations sur ces outils.

![](assets/tools_icons90.png)

### Exporter des données

Grâce à ces outils, vous pouvez exporter des données du rapport dans 4 formats différents.

| Option d'exportation | Exporte les données |
|---|---|
| **[!UICONTROL Image]** | En tant qu'image (. png). Utile lorsque vous souhaitez télécharger et partager des données de rapport dans son format graphique d'origine. |
| **[!UICONTROL PDF]** | Au format PDF. |
| **[!UICONTROL Data]** | Dans une nouvelle fenêtre de navigateur sous forme de données numériques en colonnes et lignes. |
| **[!UICONTROL Crosstab]** | Au format. csv. |

### Rétablir les modifications

Sélectionnez cet outil pour annuler toute modification interactive de clic que vous avez effectuée sur le rapport.

### Mises à jour automatiques

The [!UICONTROL Delivery-Performance] and [!UICONTROL Trait-to-Trait Overlap] reports are dynamic reports that respond and change based on user click actions.

For example, say you want to select several advertisers in the [!UICONTROL Overlap] report. Lorsque cette option est activée, les mises à jour automatiques commencent à renvoyer des données dès que vous cochez une case. Ce comportement dynamique peut interrompre votre flux de travail, car vous devez attendre le traitement du rapport avant de sélectionner un autre annonceur. Utilisez cet outil pour désactiver cette fonction (et de nouveau) si nécessaire.

### Actualiser les données

Cliquez sur l'icône d'actualisation pour exécuter un rapport ou recharger votre jeu de données. Lorsque les mises à jour automatiques sont désactivées, cliquez sur Actualiser pour exécuter ou mettre à jour le rapport.

### Outil Rechercher

La recherche est représentée par une loupe générique - icône en verre (pas affichée). Le champ de recherche est masqué jusqu'à ce que vous cliquiez sur les étiquettes de sélection sur le côté gauche de l'écran. Le tableau ci-dessous décrit l'emplacement de l'outil de recherche pour chaque rapport.

| Rapport | Pour rechercher la recherche, passez la souris sur |
|---|---|
| [!UICONTROL Delivery and Performance] rapport | Libellé « Nom du publicitaire ». |
| [!UICONTROL Overlap] rapports | Libellé « nom SID ». |
