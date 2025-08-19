---
description: Utilisez le tableau de bord pour afficher des informations sur le nombre de visiteurs uniques de vos partenaires, ventilées par type de caractéristique et par segment pendant une période spécifiée.
seo-description: Use the Dashboard to view information about your partners' unique visitor counts broken down by trait types and segments for a specified time frame.
seo-title: Reports Dashboard
solution: Audience Manager
title: Tableau de bord des rapports
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
feature: Reporting Reference
exl-id: 1ca0280a-d67b-46f7-9c58-effc5be4e38f
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 0%

---

# Tableau de bord des rapports {#reports-dashboard}

Utilisez le tableau de bord pour afficher des informations sur le nombre de visiteurs uniques répartis par type de caractéristiques et par segment, pour une période spécifiée.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] utilise [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) pour étendre les autorisations du groupe d’utilisateurs à l’[!UICONTROL Dashboard]. Les utilisateurs ne peuvent afficher que les informations du tableau de bord qu’ils sont autorisés à consulter. [!UICONTROL RBAC] fonctionnalité vous permet de contrôler les données de rapport que les équipes internes peuvent afficher.

Par exemple, une agence qui gère différents comptes d’annonceurs peut configurer des autorisations de groupe d’utilisateurs afin qu’une équipe qui gère le compte de l’annonceur A ne puisse pas voir les données de rapports de l’annonceur B. Ce tableau de bord peut être utilisé pour résoudre les problèmes de diffusion des données.

Par exemple, si vous constatez une baisse ou une hausse du nombre total d’utilisateurs uniques avec la répartition du type d’utilisateur unique (basé sur des règles et intégré), vous disposez d’un meilleur point de départ pour détecter un problème potentiel de diffusion des données. Si vous constatez une baisse du nombre total d’utilisateurs uniques et d’utilisateurs uniques intégrés, vous pouvez accéder au rapport [!UICONTROL On-boarding Status] pour voir s’il y a eu un problème avec un fichier entrant.

**Pour accéder au tableau de bord :**

1. Dans le menu de navigation supérieur, cliquez sur **[!UICONTROL Dashboard]**.
2. *Facultatif* Sélectionnez la période souhaitée à partir de la dernière date de création de rapports dans la liste déroulante (7 jours, 14 jours (par défaut), 30 jours ou 60 jours).

   Selon la période sélectionnée, la modification delta dans les panneaux [!UICONTROL Largest Traits] > [!UICONTROL Most Changed Traits] et [!UICONTROL Largest Segments] > [!UICONTROL Most Changed Segments] affiche la modification du nombre de visiteurs uniques dans l’audience sur la période se terminant aujourd’hui par rapport à la période précédente de même durée. Par exemple, si vous sélectionnez 7 jours, le delta compare les visiteurs uniques des sept jours précédents se terminant aujourd’hui aux visiteurs uniques des sept jours se terminant il y a sept jours.

   >[!NOTE]
   >
   >Vous pouvez rechercher une modification delta qui semble inhabituelle en exécutant un rapport [!UICONTROL Trend]. Par exemple, si vous constatez une modification delta anormalement importante au cours des sept derniers jours, vous pouvez exécuter un rapport [!UICONTROL Trend] sur les 14 derniers jours (2 x 7) pour mieux comprendre les chiffres.

   Selon les autorisations de l’utilisateur connecté, les panneaux suivants s’affichent :

   * [Partenaires uniques](../reporting/reports-dashboard.md#partner-uniques)
   * [Caractéristiques les plus grandes/caractéristiques les plus modifiées](../reporting/reports-dashboard.md#largest-traits)
   * [Segments Les Plus Grands/Segments Les Plus Modifiés](../reporting/reports-dashboard.md#most-changed-segments)

3. *Facultatif* Cliquez sur **[!UICONTROL Normalize]** au-dessus d’un graphique pour afficher toutes les données à la même échelle. Vous pouvez également placer le pointeur de la souris sur n’importe quel point de données pour afficher plus d’informations.

## Partenaires uniques {#partner-uniques}

Autorisation requise pour afficher : [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

Ce panneau affiche le nombre de visiteurs uniques pendant la période spécifiée. Les lignes individuelles, avec un code couleur, représentent le nombre total de visiteurs uniques et le nombre de visiteurs uniques capturés à l’aide de caractéristiques algorithmiques, basées sur des règles et intégrées.

>[!NOTE]
>
>Le nombre total de visiteurs uniques représente les visiteurs capturés par le biais de caractéristiques basées sur des règles ou intégrées. Cependant, le nombre total de visiteurs uniques n’est pas égal à la somme des visiteurs uniques capturés à l’aide des caractéristiques basées sur des règles et intégrées. Le même utilisateur unique peut être représenté dans l’un de ces deux types de caractéristiques.

## Caractéristiques les plus grandes/caractéristiques les plus modifiées {#largest-traits}

Autorisation requise pour afficher : [!UICONTROL View Traits].

![](assets/largest_traits.png)

Ce panneau affiche le nombre de visiteurs uniques capturés par diverses caractéristiques.

Utilisez la liste déroulante **[!UICONTROL Show]** pour afficher des informations sur les différents types de caractéristiques : [!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded] ou [!UICONTROL Rule-Based].

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
   <td colname="col1"> <p><span class="wintitle"> caractéristiques les plus importantes </span> </p> </td> 
   <td colname="col2"> <p>Affiche des informations sur le nombre de visiteurs uniques triés par nombre (du plus élevé au plus bas) et répertorie également la modification delta de visiteurs uniques pendant la période spécifiée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> caractéristiques les plus modifiées </span> </p> </td> 
   <td colname="col2"> <p>Affiche des informations sur le nombre de visiteurs uniques triés par modification delta. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segments Les Plus Grands/Segments Les Plus Modifiés {#most-changed-segments}

Autorisation requise pour afficher : [!UICONTROL View Segments].

![](assets/largest_segments.png)

Ce panneau affiche le nombre de visiteurs uniques capturés par divers segments en temps réel.

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
   <td colname="col1"> <p><span class="wintitle"> Segments Les Plus Volumineux </span> </p> </td> 
   <td colname="col2"> <p>Affiche des informations sur le nombre de visiteurs uniques et le changement différentiel de visiteurs uniques au cours de la période spécifiée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segments Les Plus Modifiés </span> </p> </td> 
   <td colname="col2"> <p>Affiche des informations sur le nombre de visiteurs uniques triés par modification delta. </p> </td> 
  </tr> 
 </tbody> 
</table>
