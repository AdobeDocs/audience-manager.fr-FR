---
description: Utilisez le tableau de bord pour afficher des informations sur le nombre de visiteurs uniques de vos partenaires ventilées par types et segments de caractéristiques pour une période donnée.
seo-description: Utilisez le tableau de bord pour afficher des informations sur le nombre de visiteurs uniques de vos partenaires ventilées par types et segments de caractéristiques pour une période donnée.
seo-title: Tableau de bord Rapports
solution: Audience Manager
title: Tableau de bord Rapports
uuid: 350 eee 2 d -72 f 7-42 a 7-916 b -60 f 9 a 362 c 5 cf
translation-type: tm+mt
source-git-commit: ad4721cd2ff1f4b2b7cb814cbafdef1f59138a26

---


# Reports Dashboard {#reports-dashboard}

Utilisez le tableau de bord pour afficher les informations sur le nombre de visiteurs uniques ventilées par types et segments de caractéristiques, pour une période spécifiée.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] uses [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) pour étendre les autorisations de groupe d&#39;utilisateurs à [!UICONTROL Dashboard]la fonction. Les utilisateurs peuvent afficher uniquement les informations sur le tableau de bord à afficher. [!UICONTROL RBAC] vous permet de contrôler quelles données de rapport les équipes internes peuvent afficher.

Par exemple, une agence qui gère différents comptes publicitaires peut configurer les autorisations des groupes d&#39;utilisateurs de sorte qu&#39;une équipe qui gère le compte publicitaire A ne puisse pas voir les données de rapport de l&#39;annonceur B. Ce tableau de bord peut être utilisé pour résoudre les problèmes de remise des données.

Par exemple, si vous observez un creux ou un pic, dans le total des utilisateurs uniques avec la ventilation du type d&#39;utilisateur unique (selon les règles par rapport à l&#39;intégration), vous disposez d&#39;un meilleur point de départ pour suivre un problème potentiel de diffusion de données. If you notice a dip in total unique users and in on-boarded unique users, you can go to the [!UICONTROL On-boarding Status] report to see if there was an issue with an inbound file.

**Pour accéder au tableau de bord :**

1. In the top navigation menu, click **[!UICONTROL Dashboard]**.
2. *Facultatif* Sélectionnez la période souhaitée à partir de la dernière date de rapport dans la liste déroulante (7 jours, 14 jours (valeur par défaut), 30 jours ou 60 jours).

   Depending on the period selected, the delta change in the [!UICONTROL Largest Traits] &gt; [!UICONTROL Most Changed Traits] and [!UICONTROL Largest Segments] &gt; [!UICONTROL Most Changed Segments] panels displays the change in unique visitors in the audience over the period ending today vs. the prior period of the same length. Par exemple, si vous sélectionnez 7 jours, le delta compare les visiteurs uniques au cours des sept jours écoulés qui se terminent aujourd&#39;hui par rapport aux visiteurs uniques pour les sept jours qui se sont achevés auparavant.

   >[!NOTE]
   >
   >You can investigate a delta change that seems out of the ordinary by running a [!UICONTROL Trend] report. For example, if you see an unusually large delta change during the last seven days, you could run a [!UICONTROL Trend] report for the last 14 days (2 x 7) to better understand the numbers.

   Selon les autorisations de l&#39;utilisateur connecté, les panneaux suivants s&#39;affichent :

   * [Partenaires uniques](../reporting/reports-dashboard.md#partner-uniques)
   * [Caractéristiques plus grandes/Caractéristiques les plus modifiées](../reporting/reports-dashboard.md#largest-traits)
   * [Segments plus grands/Segments les plus modifiés](../reporting/reports-dashboard.md#most-changed-segments)

3. *Cliquez en option* **[!UICONTROL Normalize]** sur un graphique pour afficher toutes les données de la même échelle. Vous pouvez également pointer sur un point de données pour afficher plus d&#39;informations.

## Partner Uniques {#partner-uniques}

Permission Required to View: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

Ce panneau affiche le nombre de visiteurs uniques au cours de la période spécifiée. Les lignes codées par couleur représentent le nombre total de visiteurs uniques et le nombre de visiteurs uniques capturés à l&#39;aide de caractéristiques algorithmiques, basées sur des règles et intégrées.

>[!NOTE]
>
>Le nombre total de visiteurs uniques représente les visiteurs capturés par l&#39;intermédiaire de caractéristiques basées sur des règles ou intégrées. Cependant, le nombre total de visiteurs uniques n&#39;est pas égal à la somme des visiteurs uniques capturés à l&#39;aide des caractéristiques basées sur des règles et intégrées. Le même utilisateur unique peut être représenté dans l&#39;un de ces deux types de caractéristiques.

## Largest Traits/Most Changed Traits {#largest-traits}

Permission Required to View: [!UICONTROL View Traits].

![](assets/largest_traits.png)

Ce panneau affiche le nombre de visiteurs uniques capturés par diverses caractéristiques.

Use the **[!UICONTROL Show]** drop-down list to display information about different types of traits: [!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded], or [!UICONTROL Rule-Based].

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
   <td colname="col1"> <p><span class="wintitle"> Principales caractéristiques</span> </p> </td> 
   <td colname="col2"> <p>Affiche des informations sur le nombre de visiteurs uniques triés par nombre (le plus élevé au plus faible) et répertorie également le changement delta des visiteurs uniques pendant la période spécifiée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Caractéristiques les plus modifiées</span> </p> </td> 
   <td colname="col2"> <p>Affiche des informations sur le nombre de visiteurs uniques triés par modification du delta. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Largest Segments/Most Changed Segments {#most-changed-segments}

Permission Required to View: [!UICONTROL View Segments].

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
   <td colname="col1"> <p><span class="wintitle"> Segments les plus importants</span> </p> </td> 
   <td colname="col2"> <p>Affiche des informations sur le nombre de visiteurs uniques et le changement delta de visiteurs uniques au cours de la période spécifiée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segments les plus modifiés</span> </p> </td> 
   <td colname="col2"> <p>Affiche des informations sur le nombre de visiteurs uniques triés par modification du delta. </p> </td> 
  </tr> 
 </tbody> 
</table>

