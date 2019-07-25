---
description: Les principales caractéristiques inutilisées sont représentées sous forme de diagramme de dispersion des caractéristiques qui ne sont pas encore membres d'un segment, en fonction du type de caractéristique, de la source de données et des performances.
seo-description: Les principales caractéristiques inutilisées sont représentées sous forme de diagramme de dispersion des caractéristiques qui ne sont pas encore membres d'un segment, en fonction du type de caractéristique, de la source de données et des performances.
seo-title: Principales caractéristiques inutilisées
solution: Audience Manager
title: Principales caractéristiques inutilisées
uuid: 90 bcd 333-41 b 8-416 e-aa 4 e-a 8661891 df 50
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Top Unused Traits{#top-unused-traits}

Les principales caractéristiques inutilisées sont représentées sous forme de diagramme de dispersion des caractéristiques qui ne sont pas encore membres d'un segment, en fonction du type de caractéristique, de la source de données et des performances.

## Cas d’utilisation {#use-cases}

With the [!UICONTROL Top Unused Traits] report, you can analyze and compare the performance of first and third party traits that are currently not mapped to a segment. Cette vue peut indiquer les meilleures caractéristiques à utiliser dans un segment d'audience pour l'optimisation des campagnes ou les nouvelles opportunités nettes.

## Using the Top Unused Traits Report {#using-the-report}

Use the **[!UICONTROL Data Provider Type]** controls to toggle between first party and third party traits. Select **[!UICONTROL All]** to return first and third party traits in the report.

With the **[!UICONTROL Impressions]** slider, you can select a minimum and maximum value for returned impressions. Toute caractéristique responsable de plus ou moins que les limites définies ne s'affiche pas dans le rapport.

Use the **[!UICONTROL Day Range]** and **[!UICONTROL Date Through]** controls to adjust your look-back range. Notez que seule la période de recherche de 30 jours est disponible pour ce rapport.

Use the **[!UICONTROL Order]** drop-down box to select the web properties in your portfolio for which you want to return information.

In the **[!UICONTROL Data Provider]** drop-down box, select the data sources containing the traits you want to see in the report.

Use the **[!UICONTROL Traits]** drop-down box to select which traits you want to see in the report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Order IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Order] instead of the [!UICONTROL Order ID].

## Interpreting the Results {#interpreting-results}

**Exemple de rapport**

Your [!UICONTROL Top Unused Traits] report could look similar to the one below. Dans le rapport, cliquez sur une bulle pour afficher les données sous-jacentes.

Voir Descriptions pour obtenir des informations supplémentaires dans le tableau sous l'exemple de rapport.

![](assets/publisher_unused_traits.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Type de fournisseur de données</span> </p> </td> 
   <td colname="col2"> <p>Indique si la source de données sélectionnée contient des caractéristiques propriétaires ou tierces. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ID de caractéristique</span> </p> </td> 
   <td colname="col2"> <p>Identifiant unique de cette caractéristique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nom de la caractéristique</span> </p> </td> 
   <td colname="col2"> <p>Nom alphanumérique que vous ou le fournisseur de données avez affecté à cette caractéristique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Commande</span> </p> </td> 
   <td colname="col2"> <p>Propriété web pour laquelle vous voyez ce rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressions</span> </p> </td> 
   <td colname="col2"> <p>Nombre de fois où des membres de cette caractéristique ont été exposés à votre inventaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Caractéristiques uniques</span> </p> </td> 
   <td colname="col2"> <p>Nombre de membres de la caractéristique, au cours des 30 derniers jours. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

La position de vos caractéristiques dans un rapport peut vous indiquer les caractéristiques que vous pouvez utiliser pour optimiser les segments d'audience existants.

Les caractéristiques situées plus haut sur l'axe des impressions sont celles que vous souhaitez utiliser dans vos campagnes. Pour les caractéristiques présentant un faible nombre d'impressions, il est peu probable que vous atteigniez cette audience sur votre propriété Web, en fonction de vos données DFP.

Look to the left of the [!UICONTROL Unique Trait Realizations] axis for highly accurate traits and to the right for traits that can drive scale.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Position </th> 
   <th colname="col2" class="entry"> Emplacement indiqué </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Haut gauche</b> </p> </td> 
   <td colname="col2"> <p>Nombre élevé d'impressions, faible nombre de realizations de caractéristiques. </p> <p>Il s'agit d'une audience très précise qui n'est pas encore membre d'un segment. Envisagez le ciblage. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Bas gauche</b> </p> </td> 
   <td colname="col2"> <p>Faible nombre d'impressions et faible nombre de realizations de caractéristiques. </p> <p> Excluez ces caractéristiques, car les membres ne contribuent pas aux impressions sur vos propriétés Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Haut droite</b> </p> </td> 
   <td colname="col2"> <p>Nombre élevé d'impressions, nombre élevé de realizations de caractéristiques. </p> <p>Une portée élevée par rapport à une audience qui n'est pas encore identifiée dans un segment. Cette audience est un excellent candidat à un ciblage en raison du nombre élevé d'impressions et de l'échelle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Bas droite</b> </p> </td> 
   <td colname="col2"> <p>Faible nombre d'impressions et nombre élevé de realizations de caractéristiques. </p> <p> Vous pouvez exclure ces caractéristiques, car les membres ne contribuent pas aux impressions sur vos propriétés Web. </p> </td> 
  </tr> 
 </tbody> 
</table>
