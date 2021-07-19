---
description: Utilisez le tableau de bord pour afficher des informations sur le nombre de visiteurs uniques de vos partenaires ventilé par types de caractéristiques et par segments pendant une période spécifiée.
seo-description: Utilisez le tableau de bord pour afficher des informations sur le nombre de visiteurs uniques de vos partenaires ventilé par types de caractéristiques et par segments pendant une période spécifiée.
seo-title: Tableau de bord de rapports
solution: Audience Manager
title: Tableau de bord de rapports
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
feature: Référence de création de rapports
exl-id: 1ca0280a-d67b-46f7-9c58-effc5be4e38f
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 1%

---

# Tableau de bord de rapports {#reports-dashboard}

Utilisez le tableau de bord pour afficher des informations sur le nombre de visiteurs uniques ventilé par types de caractéristiques et par segments, pour une période spécifiée.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] utilise  [!UICONTROL Role Based Access Control]  ([!UICONTROL RBAC]) pour étendre les autorisations des groupes d’utilisateurs à  [!UICONTROL Dashboard]. Les utilisateurs ne peuvent afficher que les informations du tableau de bord qu’ils sont autorisés à afficher. [!UICONTROL RBAC] permet de contrôler les données de rapport que les équipes internes peuvent afficher.

Par exemple, une agence qui gère différents comptes publicitaires peut configurer des autorisations de groupe d’utilisateurs de sorte qu’une équipe qui gère le compte de l’annonceur A ne puisse pas consulter les données de rapport de l’annonceur B. Ce tableau de bord peut être utilisé pour résoudre les problèmes de diffusion des données.

Par exemple, si vous constatez une baisse ou un pic du nombre total d’utilisateurs uniques avec la ventilation du type d’utilisateur unique (basé sur des règles ou intégré), vous disposez d’un meilleur point de départ pour détecter un problème potentiel de remise des données. Si vous constatez un creux dans le nombre total d’utilisateurs uniques et d’utilisateurs uniques intégrés, vous pouvez accéder au rapport [!UICONTROL On-boarding Status] pour voir si un problème s’est produit avec un fichier entrant.

**Pour accéder au tableau de bord :**

1. Dans le menu de navigation supérieur, cliquez sur **[!UICONTROL Dashboard]**.
2. ** Facultatif : sélectionnez la période souhaitée à partir de la date du dernier rapport dans la liste déroulante (7 jours, 14 jours (valeur par défaut), 30 jours ou 60 jours).

   Selon la période sélectionnée, le changement différentiel dans les panneaux [!UICONTROL Largest Traits] > [!UICONTROL Most Changed Traits] et [!UICONTROL Largest Segments] > [!UICONTROL Most Changed Segments] affiche le changement dans les visiteurs uniques de l’audience sur la période se terminant aujourd’hui par rapport à la période précédente de même durée. Si, par exemple, vous sélectionnez 7 jours, le delta compare les visiteurs uniques des sept jours se terminant aujourd’hui par rapport aux visiteurs uniques des sept jours se terminant il y a sept jours.

   >[!NOTE]
   >
   >Vous pouvez étudier une modification delta qui semble hors de l’ordinaire en exécutant un rapport [!UICONTROL Trend]. Par exemple, si vous constatez une modification delta inhabituellement importante au cours des sept derniers jours, vous pouvez exécuter un rapport [!UICONTROL Trend] pour les 14 derniers jours (2 x 7) afin de mieux comprendre les chiffres.

   Selon les autorisations de l’utilisateur connecté, les panneaux suivants s’affichent :

   * [Partenaires uniques](../reporting/reports-dashboard.md#partner-uniques)
   * [Caractéristiques les plus grandes/caractéristiques les plus modifiées](../reporting/reports-dashboard.md#largest-traits)
   * [Segments les plus grands/segments les plus modifiés](../reporting/reports-dashboard.md#most-changed-segments)

3. ** FacultatifCliquez  **[!UICONTROL Normalize]** au-dessus d’un graphique pour afficher toutes les données à la même échelle. Vous pouvez également placer le pointeur de la souris sur un point de données pour afficher plus d’informations.

## Partenaires uniques {#partner-uniques}

Autorisation requise pour l’affichage : [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

Ce panneau affiche le nombre de visiteurs uniques au cours de la période spécifiée. Les lignes individuelles codées par couleur représentent le nombre total de visiteurs uniques et le nombre de visiteurs uniques capturés à l’aide de caractéristiques algorithmiques, basées sur des règles et intégrées.

>[!NOTE]
>
>Le nombre total de visiteurs uniques représente les visiteurs capturés au moyen de caractéristiques basées sur des règles ou intégrées. Cependant, le nombre total de visiteurs uniques n’est pas égal à la somme des visiteurs uniques capturés à l’aide des caractéristiques basées sur des règles et intégrées. Un même utilisateur unique peut être représenté dans l’un de ces deux types de caractéristiques.

## Caractéristiques les plus grandes/caractéristiques les plus modifiées {#largest-traits}

Autorisation requise pour l’affichage : [!UICONTROL View Traits].

![](assets/largest_traits.png)

Ce panneau affiche le nombre de visiteurs uniques capturés par différentes caractéristiques.

Utilisez la liste déroulante **[!UICONTROL Show]** pour afficher des informations sur différents types de caractéristiques : [!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded] ou [!UICONTROL Rule-Based].

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
   <td colname="col2"> <p>Affiche des informations sur le nombre de visiteurs uniques triés selon le changement différentiel. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segments les plus grands/segments les plus modifiés {#most-changed-segments}

Autorisation requise pour l’affichage : [!UICONTROL View Segments].

![](assets/largest_segments.png)

Ce panneau affiche en temps réel le nombre de visiteurs uniques capturés par différents segments.

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
   <td colname="col1"> <p><span class="wintitle"> Segments les plus volumineux</span> </p> </td> 
   <td colname="col2"> <p>Affiche des informations sur le nombre de visiteurs uniques et le changement différentiel de visiteurs uniques au cours de la période spécifiée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segments les plus modifiés</span> </p> </td> 
   <td colname="col2"> <p>Affiche des informations sur le nombre de visiteurs uniques triés selon le changement différentiel. </p> </td> 
  </tr> 
 </tbody> 
</table>
