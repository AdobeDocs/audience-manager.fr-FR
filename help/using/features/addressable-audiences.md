---
description: Présentation de la fonction d'audience adressable et des cas d'utilisation.
keywords: DIL 
seo-description: Présentation de la fonction d'audience adressable et des cas d'utilisation.
seo-title: Audiences adressables
solution: Audience Manager
title: Audiences adressables
topic: API DIL
uuid: 3 eb 1335 a -6949-452 b-b 77 a -697 c 22856 cb 3
translation-type: tm+mt
source-git-commit: b213a1ecde4c85dc66dada24dec602ed1d9b0332

---


# Addressable Audience {#addressable-audiences}

Présentation de la fonction d'audience adressable et des cas d'utilisation.

## What is an Addressable Audience? {#addressable-audience-description}

The [!UICONTROL Addressable Audiences] feature shows you the overlap between the audiences you see across all of your properties where [!DNL Audience Manager] collects data and your selected destination. Pour vous aider à comprendre ce concept, observez l'illustration ci-dessous. Le chevauchement entre chaque cercle représente les différents types d'audiences adressables.

![](assets/addressableAudienceVenn.png)

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
    <tr> 
   <td colname="col1"> <p> <b>Audience adressable d'Audience Manager pour une destination</b> </p> </td> 
   <td colname="col2"> <p>Nombre de périphériques qui ont interagi avec tous les clients Audience Manager au niveau de la plate-forme durant la période de consultation du rapport et qui peuvent être correspondances avec la destination choisie. </p> <p>Cette mesure est utile car elle vous montre : </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> The size of the total addressable audience that <span class="keyword"> Audience Manager</span> can reach on a particular targeting destination. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">How big the <span class="keyword"> Audience Manager</span> profile pool is for a targeting platform and the size of their audiences. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audience totale du client</b> </p> </td> 
   <td colname="col2"> <p>Nombre de périphériques qui ont réalisé une caractéristique basée sur des règles sur vos propriétés ou une caractéristique intégrée à partir de vos fichiers hors ligne pendant la fenêtre de recherche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taux de correspondance d'audience adressable</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Nombre de superpositions de périphériques qui ont réalisé une caractéristique basée sur des règles ou une caractéristique intégrée au cours de la fenêtre de recherche et des périphériques que nous avons une synchronisation des identifiants avec la destination choisie, quel que soit le temps de synchronisation. </p> 
    </draft-comment> <p>Cette mesure représente les dispositifs qui : 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Have realized either a rule-based or an onboarded trait during the look-back window <b>AND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Avoir une synchronisation des identifiants avec la destination choisie, quelle que soit la durée de synchronisation. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taux de correspondance client</b> </p> </td> 
   <td colname="col2"> <p>Audience adressable client ÷ Audience totale du client exprimée en %. </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <b>Population totale de segments</b> </p> </td> 
   <td colname="col2"> <p>Nombre de tous les périphériques qui appartenaient à votre segment durant la période de consultation du rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Public adressable de segment</b> </p> </td> 
   <td colname="col2"> <p>Nombre d'utilisateurs qui ont participé au segment pendant la période de consultation du rapport et ont une synchronisation active des identifiants sur votre site. Segments can include your own first-party data and second party and third party data, via traits acquired in the <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>Conseil : Utilisée avec la période d'observation de 1 jour, cette mesure peut vous aider à comprendre l'état actuel de vos segments. This is because the <span class="wintitle"> Segment Addressable Audience</span> metric represents the users who stayed in a segment throughout the previous day. Combine this with the fact that <span class="keyword"> Audience Manager</span> refreshes <span class="wintitle"> Addressable Audiences</span> daily, combining this metric and lookback period provides the most up-to-date snapshot of your segments. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taux de correspondance des segments</b> </p> </td> 
   <td colname="col2"> <p>Audience adressable de segment ÷ Population totale de segments exprimée en %. </p> </td> 
  </tr>  
 </tbody> 
</table>

## Addressable Audience Interface {#addressable-audience-interface}

The [!UICONTROL Addressable Audience] feature turns this abstract concept into quantifiable data. In [!DNL Audience Manager], this feature displays audience overlap with data visualizations that provide at-a-glance information along with numeric data in tabular form.

[!UICONTROL Addressable Audiences] se trouve **[!UICONTROL Audience Data > Destinations]** dans. Select **[!UICONTROL Integrated Platforms > Device-Based]** to see addressable audiences metrics.

![](assets/addressable-audiences-landing.png)

Les trois mesures affichées sur la page d'entrée Audiences adressables représentent :

| Mesure | Description |
---------|----------|
| **Public adressable (périphériques)** | This metric represents the Customer Addressable Audience (described in the table above) *for the last 30 days.* |
| **Taux de correspondance** | This metric represents the Addressable Audience Match Rate (described in the table above) *for the last 30 days*. |
| **Public adressable sur la durée de vie (dispositifs)** | Nombre de tous les périphériques qui ont interagi avec tous les clients Audience Manager au niveau de la plateforme durant la période de consultation du rapport et qui peuvent être correspondances avec cette destination. See [Platform-Level Metrics](/help/using/features/addressable-audiences.md#platform-level-metrics) for more information. |

Cliquez sur le nom d'une destination de serveur à serveur pour afficher les données de votre audience adressable. Remarque : cette fonctionnalité renvoie des données pour les destinations serveur à serveur uniquement et l'accès requiert des autorisations de l'administrateur.

![](assets/addressableAudiences.png)

La revue de ces données peut vous aider à :

* **Prévisions et planification :**[!UICONTROL Segment Addressable Audience] Les données vous donnent plus de granularité dans les segments que vous prévoyez d'envoyer à une destination pour le ciblage et l'activation d'audience.

* **Évaluations des performances :** Cette [!UICONTROL Addressable Audiences] fonctionnalité est également un outil de dépannage. Il vous permet de vérifier les performances des campagnes, de comprendre la portée de la campagne et d'effectuer des vérifications croisées avec les partenaires de ciblage/activation si vous ne voyez pas les résultats attendus.

### Prospection avec données et implications tierces pour les taux de correspondance

Avant d'acheter des données tierces pour l'acquisition d'audiences, les clients peuvent valider le chevauchement avec d'autres fournisseurs de données. Cela peut vous aider à prendre une décision informée avant d'acheter de nouvelles données. The ID syncs for purchased third-party data rely not only on the overlap of your data but also on third-party providers’ footprints with all other [!DNL Audience Manager] customers. Your [!DNL Adobe] consultant can help you identify additional relevant data sources to optimize prospecting campaigns.

### Utilisateurs mobiles et taux de correspondance

There are gaps when trying to connect [!DNL Safari] or mobile app users where there are no third-party cookies present. That makes it difficult to sync users with some partners because only those [!DNL Adobe] IDs for synced third-party cookies are provided in the media delivery logs. This is a reason why you might see [low match rates](../features/addressable-audiences.md#low-match-rates) for your destinations.

## Date Ranges in Addressable Audiences and Destinations {#date-ranges}

Read the sections below for available date ranges and how data ages out of each interval in the reports for an [!UICONTROL Addressable Audience] or [!UICONTROL Destination].

## Available Date Ranges and Time Zones {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Reports for your [!UICONTROL Addressable Audiences] and [Destinations](../features/destinations/destinations.md) use the same date range intervals. Les options de plage de dates incluent :

* [!UICONTROL Last 1 Day] (Cet intervalle s'exécute de minuit à minuit de la période de 24 heures précédente. Il ne s'agit pas d'une mesure réelle ou d'heure actuelle.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

All dates and date ranges are set in the [!DNL UTC] time zone. See [Time Zones in Audience Manager](../reference/aam-time-zones.md).

## Data in Date Range Intervals {#date-range-intervals}

The [!UICONTROL Addressable Audience] and [!UICONTROL Destination] metrics return a count of unique users for the selected time interval. Par exemple, un visiteur n'est comptabilisé qu'une seule fois, même s'il se rend sur votre site plusieurs fois. La première visite est la visite unique et est enregistrée. Les visites suivantes retournent des visites et ne sont pas comptabilisées car elles ne sont pas uniques.

Les plages de dates contiennent des données pour l'intervalle sélectionné ou plus ancien. Et les âges des données sont prêts à partir de chaque intervalle de rapport au fil du temps. For example, let's assume you see 2 visitors after choosing the [!UICONTROL Last 30 Days] option. Dans les rapports, ces visiteurs :

* *Seront inclus* dans les résultats renvoyés par des intervalles plus longs (60 jours, 90 jours et durée de vie).
* *Ne* sera pas inclus à des intervalles plus courts qui précèdent l' [!UICONTROL Last 30 Day] option (Actuel, 7 jours et 14 jours).

And, on day 31, these visitors only show up in the 60 day, 90 day, and [!UICONTROL Lifetime] results. Ils ont dépassé l'intervalle de 30 jours. Visitors do not age out of the [!UICONTROL Lifetime] interval.

## Addressable Audience Metrics {#addressable-audience-metrics}

This section describes the types of metrics provided by [!UICONTROL Addressable Audiences].

### Customer-Level Metrics {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

These metrics return data for traits realized when visitors come to your site or when you send inbound data files to [!DNL Audience Manager]. Ces mesures fournissent une vue d'ensemble complète de la taille de l'audience pour votre compte.

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audience adressable par le client</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Nombre de superpositions de périphériques qui ont réalisé une caractéristique basée sur des règles ou une caractéristique intégrée au cours de la fenêtre de recherche et des périphériques que nous avons une synchronisation des identifiants avec la destination choisie, quel que soit le temps de synchronisation. </p> 
    </draft-comment> <p>Cette mesure représente les dispositifs qui : 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Have realized either a rule-based or an onboarded trait during the look-back window <b>AND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Avoir une synchronisation des identifiants avec la destination choisie, quelle que soit la durée de synchronisation. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audience totale du client</b> </p> </td> 
   <td colname="col2"> <p>Nombre de périphériques qui ont réalisé une caractéristique basée sur des règles sur vos propriétés ou une caractéristique intégrée à partir de vos fichiers hors ligne pendant la fenêtre de recherche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taux de correspondance client</b> </p> </td> 
   <td colname="col2"> <p>Audience adressable client ÷ Audience totale du client exprimée en %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Segment-Level Match Metrics {#segment-level-metrics}

Ces mesures renvoient des données sur l'appartenance au segment. Ils offrent une vue plus granulaire et précise de la taille de l'audience pour chacun de vos segments.

>[!NOTE]
>
>La manière dont la fenêtre de recherche est appliquée au niveau du segment est différente de celle au niveau du client. Les visiteurs peuvent venir sur le site et réaliser une caractéristique il y a 10 jours ; ils peuvent alors remplir un segment depuis qu'ils ont quitté le segment il y a 2 jours. Lorsque la recherche de 7 jours est appliquée, ces visiteurs sont comptabilisés au niveau du segment mais pas au niveau du client.

<table id="table_4185AA02CC774B6C93B02E45F88BBBD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Public adressable de segment</b> </p> </td> 
   <td colname="col2"> <p>Nombre d'utilisateurs qui ont participé au segment pendant la période de consultation du rapport et ont une synchronisation active des identifiants sur votre site. Segments can include your own first-party data and second party and third party data, via traits acquired in the <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>Conseil : Utilisée avec la période d'observation de 1 jour, cette mesure peut vous aider à comprendre l'état actuel de vos segments. This is because the <span class="wintitle"> Segment Addressable Audience</span> metric represents the users who stayed in a segment throughout the previous day. Combine this with the fact that <span class="keyword"> Audience Manager</span> refreshes <span class="wintitle"> Addressable Audiences</span> daily, combining this metric and lookback period provides the most up-to-date snapshot of your segments. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Population totale de segments</b> </p> </td> 
   <td colname="col2"> <p>Nombre de tous les périphériques qui appartenaient à votre segment durant la période de consultation du rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taux de correspondance des segments</b> </p> </td> 
   <td colname="col2"> <p>Audience adressable de segment ÷ Population totale de segments exprimée en %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Platform-Level Metrics {#platform-level-metrics}

Cette mesure renvoie les données sur les activités collectées pour tous les clients Audience Manager. Elles offrent une vue plus large de l'audience du client par rapport aux clients Audience Manager agrégés.

<table id="table_B6654D9858FF46AF95B1C181D4608D26"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audience adressable d'Audience Manager</b> </p> </td> 
   <td colname="col2"> <p>Nombre de périphériques qui ont interagi avec tous les clients Audience Manager au niveau de la plate-forme durant la période de consultation du rapport et qui peuvent être correspondances avec la destination choisie. </p> <p>Cette mesure est utile car elle vous montre : </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> The size of the total addressable audience that <span class="keyword"> Audience Manager</span> can reach on a particular targeting destination. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">How big the <span class="keyword"> Audience Manager</span> profile pool is for a targeting platform and the size of their audiences. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Comparing Customer and Segment Addressable Audiences{#comparing-metrics}

You shouldn't compare the [!UICONTROL Customer Addressable Audience] and [!UICONTROL Segment Addressable Audience] metrics to determine if one is more significant than the other. Il s'agit de mesures distinctes, différentes et indépendantes. Comme décrit dans les définitions ci-dessus, chacune d'elles est dérivée de différents ensembles de données. Dans ce cas, évitez de déduire les conclusions si une mesure est plus grande que l'autre. Tout ce que vous pouvez dire lors de la comparaison, c'est que :

* [!UICONTROL Customer Addressable Audiences] est basée sur des realizations de caractéristiques *pour vos propres données propriétaires*. Cette mesure fournit une vue exhaustive et exhaustive de votre intégration avec un partenaire de données.

* [!UICONTROL Segment Addressable Audiences] est basée sur les qualifications des segments *pour vos propres données propriétaires, plus les données deuxième et tierce*. Cette mesure fournit une vue granulaire et plus précise des audiences adressables dans une plateforme de ciblage.

## Causes of Low Match Rates for Addressable Audiences {#low-match-rates}

Common elements responsible for low [!UICONTROL Addressable Audience] match rates or discrepancies in reported numbers.

<!-- addressable-audiences.xml -->

<table id="table_895D536F69134330A4F13887ECAFD4F5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cause </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Trafic mobile</b> </p> </td> 
   <td colname="col2"> <p>La plupart des intégrations serveur/serveur reposent sur des processus de synchronisation facilités par les cookies tiers. Toutefois, les environnements mobiles n'utilisent pas de cookies tiers. Par conséquent, les chiffres d'audience adressable peuvent sembler faibles par rapport à la taille du segment. </p> <p>Depuis janvier 2018, vous pouvez activer les audiences mobiles dans les mêmes destinations Google et Adobe Advertizing Cloud pour les audiences basées sur les cookies. Cela signifie que vous pouvez envoyer des segments avec des cookies combinés et des identifiants d'ID mobiles dans vos destinations Google et de publication Cloud, mais gardez à l'esprit que les audiences adressables affichent uniquement le chevauchement entre les ID de cookie et les destinations. Audience Manager envoie 100 % des audiences mobiles aux destinations, mais les audiences mobiles ne sont pas mesurées par la mesure d'audience adressable. </p> <p> <p><b>Remarque</b>: Prenons par exemple un segment dont la population est de 1 000 000. Si vous mappez ce segment sur une destination Google ou Adobe de publication Cloud, une audience adressable de 700 000 appareils et un taux de correspondance de 70 % s'affichent. L'adhésion de 700 000 est composée d'identifiants de cookie dont la synchronisation est identifiée avec la destination. En fait, votre audience adressable peut être beaucoup plus élevée, car les identifiants mobiles adressables n'apparaissent pas dans cette mesure. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Trafic Safari</b> </p> </td> 
   <td colname="col2"> <p>Safari bloque les cookies tiers. Ceci empêche Audience Manager de synchroniser les identifiants avec la destination. With the introduction of <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, you can expect your addressable audiences not to include Safari users. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Impressions de médias suivies</b> </p> </td> 
   <td colname="col2"> <p>En raison des bonnes pratiques du serveur d'annonces, les synchronisations d'ID ne sont pas effectuées dans des balises publicitaires. Les clients qui effectuent une grande quantité de publicités hors site ne synchronisent pas les utilisateurs vers des intégrations tierces dans ces environnements. En outre, une grande quantité de données d'impression de médias collectées peut réduire la numérotation des audiences. </p> </td>
  </tr> 
 </tbody> 
</table>

## Troubleshooting with Addressable Audiences {#troubleshooting}

In addition to surfacing match rates, you can also use [!UICONTROL Addressable Audiences] as a troubleshooting tool.

<!-- addressable-audiences-troubleshooting.xml -->

Par exemple, supposons que vous envoyez un segment à une destination et que cette destination affiche un nombre de rapports faible. Checking the [!UICONTROL Addressable Audience] results will show you if this is a technical problem or just a case of low match rates. Un faible taux de correspondance indique que votre destination n'est pas tout aussi grande pour les segments que vous avez sélectionnés. Toutefois, une différence dans le nombre total d'audiences adressables entre Audience Manager et la destination indique une intégration, une synchronisation ou d'autres problèmes techniques. Dans ce cas, contactez votre gestionnaire de compte.