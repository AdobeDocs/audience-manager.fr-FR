---
description: Utilisez le tableau de bord pour afficher des informations sur le nombre de visiteurs uniques de vos partenaires ventilé par type de caractéristiques et par segments pendant une période donnée.
seo-description: Utilisez le tableau de bord pour afficher des informations sur le nombre de visiteurs uniques de vos partenaires ventilé par type de caractéristiques et par segments pendant une période donnée.
seo-title: Tableau de bord Rapports
solution: Audience Manager
title: Tableau de bord Rapports
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
translation-type: tm+mt
source-git-commit: ad4721cd2ff1f4b2b7cb814cbafdef1f59138a26

---


# Tableau de bord Rapports {#reports-dashboard}

Utilisez le tableau de bord pour afficher des informations sur le nombre de visiteurs uniques ventilé par types de caractéristiques et par segments, pendant une période spécifiée.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] utilise [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) pour étendre les autorisations de groupe d’utilisateurs au [!UICONTROL Dashboard]. Les utilisateurs ne peuvent afficher que les informations qu’ils sont autorisés à afficher sur le tableau de bord. [!UICONTROL RBAC] permet de contrôler les rapports que les équipes internes peuvent afficher.

Par exemple, une agence qui gère différents comptes d’annonceurs peut configurer des autorisations de groupe d’utilisateurs afin qu’une équipe qui gère le compte de l’annonceur A ne puisse pas voir les données de rapport de l’annonceur B. Ce tableau de bord peut être utilisé pour résoudre les problèmes de remise des données.

Par exemple, si vous constatez un creux, ou un pic, dans le nombre total d’utilisateurs uniques avec la ventilation du type d’utilisateur unique (selon des règles ou intégré), vous disposez d’un meilleur point de départ pour détecter un problème potentiel de remise des données. Si vous constatez une diminution du nombre total d’utilisateurs uniques et d’utilisateurs uniques intégrés, vous pouvez accéder au [!UICONTROL On-boarding Status] rapport pour voir s’il y a eu un problème avec un fichier entrant.

**Pour accéder au tableau de bord :**

1. Dans le menu de navigation supérieur, cliquez sur **[!UICONTROL Dashboard]**.
2. *Facultatif* Sélectionnez la période souhaitée à partir de la dernière date du rapport dans la liste déroulante (7 jours, 14 jours (par défaut), 30 jours ou 60 jours).

   En fonction de la période sélectionnée, le changement différentiel dans les panneaux [!UICONTROL Largest Traits] &gt; [!UICONTROL Most Changed Traits] et [!UICONTROL Largest Segments] &gt; [!UICONTROL Most Changed Segments] affiche le changement dans les visiteurs uniques de l’audience au cours de la période se terminant aujourd’hui par rapport à la période précédente de même durée. Si, par exemple, vous sélectionnez 7 jours, le delta compare les visiteurs uniques des sept derniers jours se terminant aujourd’hui aux visiteurs uniques des sept jours se terminant il y a sept jours.

   >[!NOTE]
   >
   >Vous pouvez étudier une modification delta qui semble hors de l’ordinaire en exécutant un [!UICONTROL Trend] rapport. Par exemple, si vous constatez un changement delta anormalement important au cours des sept derniers jours, vous pouvez exécuter un [!UICONTROL Trend] rapport pour les 14 derniers jours (2 x 7) afin de mieux comprendre les chiffres.

   Selon les autorisations de l’utilisateur connecté, les panneaux suivants s’affichent :

   * [Partenaires uniques](../reporting/reports-dashboard.md#partner-uniques)
   * [Caractéristiques les plus grandes/Caractéristiques les plus modifiées](../reporting/reports-dashboard.md#largest-traits)
   * [Segments les plus grands/Segments les plus modifiés](../reporting/reports-dashboard.md#most-changed-segments)

3. *Facultatif* Cliquez **[!UICONTROL Normalize]** au-dessus d’un graphique pour afficher toutes les données sur la même échelle. Vous pouvez également placer le pointeur de la souris sur un point de données pour afficher plus d’informations.

## Partenaires uniques {#partner-uniques}

Autorisation requise pour afficher : [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

Ce panneau affiche le nombre de visiteurs uniques au cours de la période spécifiée. Les lignes individuelles codées par couleur représentent le nombre total de visiteurs uniques et le nombre de visiteurs uniques capturés à l’aide de caractéristiques algorithmiques, basées sur des règles et intégrées.

>[!NOTE]
>
>Le nombre total de visiteurs uniques représente les visiteurs capturés au moyen de caractéristiques basées sur des règles ou intégrées. Cependant, le nombre total de visiteurs uniques n’est pas égal à la somme des visiteurs uniques capturés à l’aide des caractéristiques basées sur des règles et des caractéristiques intégrées. Un même utilisateur unique peut être représenté dans l’un ou l’autre de ces deux types de caractéristiques.

## Caractéristiques les plus grandes/Caractéristiques les plus modifiées {#largest-traits}

Autorisation requise pour afficher : [!UICONTROL View Traits].

![](assets/largest_traits.png)

Ce panneau affiche le nombre de visiteurs uniques capturés par différentes caractéristiques.

Utilisez la liste **[!UICONTROL Show]** déroulante pour afficher des informations sur différents types de caractéristiques : [!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded]ou [!UICONTROL Rule-Based].

Ce panneau contient les onglets suivants :

<table id="table_DA48BDEB4E0143BEA4EB85AC26FF6AE3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tabulation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Caractéristiques les plus grandes</span> </p> </td> 
   <td colname="col2"> <p>Affiche des informations sur le nombre de visiteurs uniques triés par nombre (du plus élevé au plus faible) et répertorie également le changement différentiel de visiteurs uniques au cours de la période spécifiée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Caractéristiques les plus modifiées</span> </p> </td> 
   <td colname="col2"> <p>Affiche des informations sur le nombre de visiteurs uniques triés en fonction du changement delta. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segments les plus grands/Segments les plus modifiés {#most-changed-segments}

Autorisation requise pour afficher : [!UICONTROL View Segments].

![](assets/largest_segments.png)

Ce panneau affiche le nombre de visiteurs uniques capturés par différents segments en temps réel.

Ce panneau contient les onglets suivants :

<table id="table_8E22E0579FA74C5A86CC40B40B2548BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tabulation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segments les plus grands</span> </p> </td> 
   <td colname="col2"> <p>Affiche des informations sur le nombre de visiteurs uniques et le changement différentiel de visiteurs uniques au cours de la période spécifiée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segments les plus modifiés</span> </p> </td> 
   <td colname="col2"> <p>Affiche des informations sur le nombre de visiteurs uniques triés en fonction du changement delta. </p> </td> 
  </tr> 
 </tbody> 
</table>

