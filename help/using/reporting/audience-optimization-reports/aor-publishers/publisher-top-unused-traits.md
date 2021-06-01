---
description: Les principales caractéristiques inutilisées sont représentées sous la forme d’un diagramme de dispersion des caractéristiques qui ne sont pas encore membres d’un segment, en fonction du type de caractéristique, de la source de données et des performances.
seo-description: Les principales caractéristiques inutilisées sont représentées sous la forme d’un diagramme de dispersion des caractéristiques qui ne sont pas encore membres d’un segment, en fonction du type de caractéristique, de la source de données et des performances.
seo-title: Principales caractéristiques inutilisées
solution: Audience Manager
title: Principales caractéristiques inutilisées
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
feature: Rapports d’Audience Optimization
exl-id: d0ae72c0-1fb1-423a-a7e6-de955bd7f3c5
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 2%

---

# Principales caractéristiques inutilisées{#top-unused-traits}

Les principales caractéristiques inutilisées sont représentées sous la forme d’un diagramme de dispersion des caractéristiques qui ne sont pas encore membres d’un segment, en fonction du type de caractéristique, de la source de données et des performances.

## Cas d’utilisation {#use-cases}

Avec le rapport [!UICONTROL Top Unused Traits] , vous pouvez analyser et comparer les performances des caractéristiques propriétaires et tierces qui ne sont actuellement pas mappées à un segment. Cette vue peut indiquer les meilleures caractéristiques à utiliser dans un segment d’audience pour l’optimisation des campagnes ou les nouvelles opportunités.

## Utilisation du rapport Principales caractéristiques inutilisées {#using-the-report}

Utilisez les contrôles **[!UICONTROL Data Provider Type]** pour basculer entre les caractéristiques propriétaires et tierces. Sélectionnez **[!UICONTROL All]** pour renvoyer les caractéristiques propriétaires et tierces dans le rapport.

Avec le curseur **[!UICONTROL Impressions]**, vous pouvez sélectionner une valeur minimale et une valeur maximale pour les impressions renvoyées. Les caractéristiques responsables de plus ou moins de que les limites que vous avez définies ne s’affichent pas dans le rapport.

Utilisez les commandes **[!UICONTROL Day Range]** et **[!UICONTROL Date Through]** pour ajuster la plage de recherche arrière. Notez que seule la période d’analyse de 30 jours est disponible pour ce rapport.

Utilisez la liste déroulante **[!UICONTROL Order]** pour sélectionner les propriétés web de votre portefeuille pour lesquelles vous souhaitez renvoyer des informations.

Dans la liste déroulante **[!UICONTROL Data Provider]**, sélectionnez les sources de données contenant les caractéristiques que vous souhaitez voir dans le rapport.

Utilisez la liste déroulante **[!UICONTROL Traits]** pour sélectionner les caractéristiques à afficher dans le rapport.

>[!IMPORTANT]
>
>Lors de l’activation de [!UICONTROL Audience Optimization for Publishers], vous devez inclure des métadonnées descriptives pour [!UICONTROL Order IDs], comme décrit à l’étape 3 de la section [Importation de fichiers de données Google Ad Manager (anciennement DFP) dans l’Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Vous pouvez ainsi vous assurer que le rapport présente la propriété web sous la forme [!UICONTROL Order] au lieu de [!UICONTROL Order ID].

## Interprétation des résultats {#interpreting-results}

**Exemple de rapport**

Votre rapport [!UICONTROL Top Unused Traits] pourrait ressembler à celui ci-dessous. Dans votre rapport, cliquez sur une bulle pour afficher les données sous-jacentes.

Consultez les descriptions des informations supplémentaires dans le tableau ci-dessous de l’exemple de rapport.

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
   <td colname="col2"> <p>L’identifiant unique de cette caractéristique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nom de la caractéristique</span> </p> </td> 
   <td colname="col2"> <p>Nom alphanumérique que vous ou le fournisseur de données avez attribué à cette caractéristique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Commande</span> </p> </td> 
   <td colname="col2"> <p>La propriété web pour laquelle ce rapport s’affiche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressions</span> </p> </td> 
   <td colname="col2"> <p>Nombre de fois où des membres de cette caractéristique ont été exposés à votre inventaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Caractéristiques uniques</span> </p> </td> 
   <td colname="col2"> <p>Nombre de membres de la caractéristique au cours des 30 derniers jours. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

La position de vos caractéristiques dans un rapport peut vous en apprendre beaucoup sur les caractéristiques que vous pouvez utiliser pour optimiser les segments d’audience existants.

Les caractéristiques situées plus haut sur l’axe Impressions sont celles que vous souhaitez utiliser dans vos campagnes. Pour les caractéristiques comportant un faible nombre d’impressions, il est peu probable que vous atteigniez cette audience sur votre propriété web, en fonction de vos données [!DNL Google Ad Manager].

Reportez-vous à gauche de l’axe [!UICONTROL Unique Trait Realizations] pour connaître les caractéristiques les plus précises et à droite pour les caractéristiques qui peuvent générer l’échelle.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Position </th> 
   <th colname="col2" class="entry"> Indicateur de référencement </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Haut à gauche</b> </p> </td> 
   <td colname="col2"> <p>Nombre élevé d’impressions, faible nombre de réalisations de caractéristiques. </p> <p>Il s’agit d’une audience hautement précise qui n’est pas encore membre d’un segment. Prenez en compte pour le ciblage. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Bas à gauche</b> </p> </td> 
   <td colname="col2"> <p>Faible nombre d’impressions, faible nombre de réalisations de caractéristiques. </p> <p> Éliminez ces caractéristiques, car les membres ne contribuent pas aux impressions sur vos propriétés web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Haut à droite</b> </p> </td> 
   <td colname="col2"> <p>Nombre élevé d’impressions, nombre élevé de réalisations de caractéristiques. </p> <p>Portée élevée par rapport à une audience qui n’est pas encore indiquée dans un segment. Ce public est un candidat idéal pour le ciblage en raison du nombre élevé d’impressions et de l’échelle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Bas à droite</b> </p> </td> 
   <td colname="col2"> <p>Faible nombre d’impressions, grand nombre de réalisations de caractéristiques. </p> <p> Vous pouvez exclure ces caractéristiques, car les membres ne contribuent pas aux impressions sur vos propriétés web. </p> </td> 
  </tr> 
 </tbody> 
</table>
