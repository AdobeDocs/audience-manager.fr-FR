---
description: Les principales caractéristiques inutilisées sont représentées sous forme de diagramme de dispersion des caractéristiques qui ne sont pas encore membres d’un segment, en fonction du type de caractéristique, de la source de données et des performances.
seo-description: Les principales caractéristiques inutilisées sont représentées sous forme de diagramme de dispersion des caractéristiques qui ne sont pas encore membres d’un segment, en fonction du type de caractéristique, de la source de données et des performances.
seo-title: Principales caractéristiques inutilisées
solution: Audience Manager
title: Principales caractéristiques inutilisées
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Principales caractéristiques inutilisées{#top-unused-traits}

Les principales caractéristiques inutilisées sont représentées sous forme de diagramme de dispersion des caractéristiques qui ne sont pas encore membres d’un segment, en fonction du type de caractéristique, de la source de données et des performances.

## Cas d’utilisation {#use-cases}

Le [!UICONTROL Top Unused Traits] rapport vous permet d’analyser et de comparer les performances des caractéristiques propriétaires et tierces qui ne sont pas actuellement mises en correspondance avec un segment. Cette vue peut indiquer les meilleures caractéristiques à utiliser dans un segment d’audience pour l’optimisation de la campagne ou pour les nouvelles opportunités nettes.

## Utilisation du rapport Principales caractéristiques inutilisées {#using-the-report}

Utilisez les **[!UICONTROL Data Provider Type]** commandes pour basculer entre les caractéristiques propriétaires et tierces. Sélectionnez **[!UICONTROL All]** pour renvoyer les caractéristiques propriétaires et tiers dans le rapport.

Le **[!UICONTROL Impressions]** curseur vous permet de sélectionner une valeur minimale et maximale pour les impressions renvoyées. Les caractéristiques responsables de moins ou plus de ces limites ne sont pas affichées dans le rapport.

Utilisez les commandes **[!UICONTROL Day Range]** et **[!UICONTROL Date Through]** pour ajuster la plage de recherche en arrière-plan. Notez que seule la période de recherche en arrière de 30 jours est disponible pour ce rapport.

Utilisez la **[!UICONTROL Order]** liste déroulante pour sélectionner les propriétés Web de votre portefeuille pour lesquelles vous souhaitez renvoyer des informations.

Dans la **[!UICONTROL Data Provider]** liste déroulante, sélectionnez les sources de données contenant les caractéristiques à afficher dans le rapport.

Utilisez la **[!UICONTROL Traits]** liste déroulante pour sélectionner les caractéristiques à afficher dans le rapport.

>[!IMPORTANT]
>
>Lors de l’activation [!UICONTROL Audience Optimization for Publishers], vous devez inclure des métadonnées descriptives pour [!UICONTROL Order IDs], comme décrit à l’étape 3 de l’ [importation de fichiers de données DFP dans Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Vous garantissez ainsi que le rapport indique la propriété web comme [!UICONTROL Order] au lieu de la propriété [!UICONTROL Order ID].

## Interprétation des résultats {#interpreting-results}

**Exemple de rapport**

Votre [!UICONTROL Top Unused Traits] rapport pourrait ressembler à celui ci-dessous. Dans votre rapport, cliquez sur une bulle pour afficher les données sous-jacentes.

Voir la description des informations supplémentaires dans le tableau ci-dessous.

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
   <td colname="col2"> <p>Indique si la source de données sélectionnée contient des caractéristiques propriétaires ou tiers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ID de trait</span> </p> </td> 
   <td colname="col2"> <p>ID unique de cette caractéristique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nom du trait</span> </p> </td> 
   <td colname="col2"> <p>Nom alphanumérique que vous ou le fournisseur de données avez attribué à cette caractéristique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Commande</span> </p> </td> 
   <td colname="col2"> <p>Propriété Web pour laquelle vous voyez ce rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressions</span> </p> </td> 
   <td colname="col2"> <p>Nombre de fois où des membres de cette caractéristique ont été exposés à votre inventaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Caractéristiques uniques</span> </p> </td> 
   <td colname="col2"> <p>Nombre de membres de caractéristiques au cours des 30 derniers jours. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

La position de vos caractéristiques dans un rapport peut vous en dire beaucoup sur les caractéristiques que vous pouvez utiliser pour optimiser les segments d’audience existants.

Les caractéristiques situées plus haut sur l’axe Impressions sont celles que vous souhaitez utiliser dans vos campagnes. Pour les caractéristiques avec un faible nombre d’impressions, il est peu probable que vous atteigniez ce public sur votre propriété Web, en fonction de vos données DFP.

Recherchez à gauche de l' [!UICONTROL Unique Trait Realizations] axe les caractéristiques très précises et à droite les caractéristiques qui peuvent entraîner l'échelle.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Position </th> 
   <th colname="col2" class="entry"> Placement indique </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Haut gauche</b> </p> </td> 
   <td colname="col2"> <p>Nombre élevé d’impressions, faible nombre de réalisations de caractéristiques. </p> <p>Il s’agit d’une audience très précise qui n’est pas encore membre d’un segment. Tenez compte du ciblage. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Bas gauche</b> </p> </td> 
   <td colname="col2"> <p>Faible nombre d’impressions, faible nombre de réalisations de caractéristiques. </p> <p> Éliminez ces caractéristiques, car les membres ne contribuent pas aux impressions sur vos propriétés Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>En haut à droite</b> </p> </td> 
   <td colname="col2"> <p>Nombre élevé d’impressions, nombre élevé de réalisations de caractéristiques. </p> <p>Portée élevée par rapport à une audience qui n’est pas encore indiquée dans un segment. Ce public est un candidat idéal pour le ciblage en raison du nombre élevé d’impressions et de l’échelle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Bas droit</b> </p> </td> 
   <td colname="col2"> <p>Faible nombre d’impressions, grand nombre de réalisations de caractéristiques. </p> <p> Vous pouvez exclure ces caractéristiques, car les membres ne contribuent pas aux impressions sur vos propriétés Web. </p> </td> 
  </tr> 
 </tbody> 
</table>
