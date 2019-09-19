---
description: Décrit le logiciel sous-jacent qui alimente les rapports interactifs et le calendrier de mise à jour des données.
seo-description: Décrit le logiciel sous-jacent qui alimente les rapports interactifs et le calendrier de mise à jour des données.
seo-title: Technologie des rapports
solution: Audience Manager
title: Technologie des rapports
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
translation-type: tm+mt
source-git-commit: b5a962381780f1a1627e39b59e3ca86fd51763b5

---


# Technologie des rapports{#report-technology}

Décrit le logiciel sous-jacent qui alimente les rapports interactifs et le calendrier de mise à jour des données.

<!-- 

c_report_technology.xml

 -->

## Les Rapports Interactifs Utilisent La Technologie Tableau

[!DNL Audience Manager] utilise le logiciel [Tableau](https://www.tableausoftware.com/) pour afficher les données dans les rapports interactifs. Avec [!DNL Tableau], les [!UICONTROL Delivery and Overlap] rapports utilisent des repères visuels et des symboles qui vous aident à :

* Trouvez des caractéristiques de performances élevées et faibles.
* Présente les caractéristiques et les segments avec un chevauchement de visiteurs uniques faible et élevé.
* Utilisez les données de chevauchement pour créer des segments ciblés.
* Élargissez la portée en identifiant les caractéristiques apparentées avec un faible chevauchement.

## Calendrier de mise à jour des données

Les données du rapport sont mises à jour chaque dimanche chaque semaine. La mise à jour traite les données du samedi (veille) jusqu’au dimanche précédent.

## Formes, couleurs et tailles utilisées dans les rapports interactifs {#shapes-colors-sizes}

La plupart des rapports interactifs affichent des résultats avec des formes de tailles et de couleurs différentes. Ce format d’affichage est conçu pour vous aider à comprendre visuellement les données sans avoir à parcourir les lignes et les colonnes de nombres.

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
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">Les cercles indiquent vos propres caractéristiques de premier niveau. </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">Les carrés indiquent des caractéristiques tierces. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Couleurs</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">Les tons rouges indiquent un <i>faible</i> chevauchement. </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">Les tons verts indiquent un <i>chevauchement élevé</i> . </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Taille</b> </td> 
   <td colname="col2"> La taille augmente ou diminue dans la proportion directe à atteindre (le nombre ou le pourcentage de clics ou d’utilisateurs uniques dans une caractéristique ou un segment). </td> 
  </tr> 
 </tbody> 
</table>

## Explication des icônes et des outils du rapport {#icons-tools-explained}

Décrit comment rechercher et utiliser les différents outils d’icône utilisés dans les rapports dynamiques.

<!-- 

r_icons.xml

 -->

### Icônes et outils de données

Les icônes-outils suivants sont disponibles au bas de chaque fenêtre de rapport dynamique. L’illustration suivante fournit plus d’informations sur ces outils.

![](assets/tools_icons90.png)

### Exporter des données

Ces outils vous permettent d’exporter des données du rapport dans 4 formats différents.

| Option d’exportation | Exporte des données |
|---|---|
| **[!UICONTROL Image]** | En tant que fichier image (.png). Utile lorsque vous souhaitez télécharger et partager des données de rapport dans leur format graphique d’origine. |
| **[!UICONTROL PDF]** | En tant que fichier PDF. |
| **[!UICONTROL Data]** | Dans une nouvelle fenêtre du navigateur sous forme de données numériques dans des colonnes et des lignes. |
| **[!UICONTROL Crosstab]** | En tant que fichier .csv. |

### Annuler les modifications

Sélectionnez cet outil pour annuler les modifications de clics interactifs que vous avez pu effectuer sur le rapport.

### Mises à jour automatiques

Les [!UICONTROL Delivery-Performance] rapports et [!UICONTROL Trait-to-Trait Overlap] les rapports sont des rapports dynamiques qui répondent et changent en fonction des actions de clics des utilisateurs.

Supposons, par exemple, que vous souhaitiez sélectionner plusieurs annonceurs dans le [!UICONTROL Overlap] rapport. Lorsqu’elle est activée, les mises à jour automatiques commencent à renvoyer des données dès que vous cochez une case. Ce comportement dynamique peut interrompre votre flux de travail, car vous devez attendre que le rapport termine son traitement avant de sélectionner un autre annonceur. Utilisez cet outil pour désactiver (puis réactiver) cette fonction selon vos besoins.

### Actualiser les données

Cliquez sur l'icône Actualiser pour exécuter un rapport ou recharger votre jeu de données. Lorsque les mises à jour automatiques sont désactivées, cliquez sur Actualiser pour exécuter ou mettre à jour le rapport.

### Outil Recherche

La recherche est représentée par une icône de loupe générique (non affichée). Le champ de recherche est masqué jusqu’à ce que vous cliquiez sur les étiquettes de sélection sur le côté gauche de l’écran. Le tableau ci-dessous décrit l'emplacement de l'outil de recherche pour chaque rapport.

| Rapport | Pour rechercher, passez la souris sur |
|---|---|
| [!UICONTROL Delivery and Performance] rapport | Libellé "Nom de l’annonceur". |
| [!UICONTROL Overlap] rapports | Libellé "Nom SID". |
