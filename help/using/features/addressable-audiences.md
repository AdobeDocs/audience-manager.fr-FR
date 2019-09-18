---
description: Présentation de la fonctionnalité Audience adressable et des cas d’utilisation.
keywords: DIL 
seo-description: Présentation de la fonctionnalité Audience adressable et des cas d’utilisation.
seo-title: Audiences adressables
solution: Audience Manager
title: Audiences adressables
topic: API DIL
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
translation-type: tm+mt
source-git-commit: b213a1ecde4c85dc66dada24dec602ed1d9b0332

---


# Audience adressable {#addressable-audiences}

Présentation de la fonctionnalité Audience adressable et des cas d’utilisation.

## Qu’est-ce qu’une audience adressable ? {#addressable-audience-description}

La [!UICONTROL Addressable Audiences] fonction montre le chevauchement entre les audiences que vous voyez sur toutes vos propriétés où [!DNL Audience Manager] collectent des données et la destination sélectionnée. Pour vous aider à comprendre ce concept, jetez un coup d'oeil à l'illustration ci-dessous. Le chevauchement entre chaque cercle représente les différents types d’audiences adressables.

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
   <td colname="col1"> <p> <b>Audience adressable d’Audience Manager pour une destination</b> </p> </td> 
   <td colname="col2"> <p>Nombre de tous les périphériques qui ont interagi avec tous les clients d’Audience Manager au niveau de la plate-forme pendant la période de recherche en arrière du rapport et qui peuvent correspondre à la destination choisie. </p> <p>Cette mesure est utile car elle vous montre : </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> Taille de l’audience adressable totale que <span class="keyword"> Audience Manager</span> peut atteindre sur une destination de ciblage particulière. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">Taille du pool de profils d’Audience Manager <span class="keyword"></span> pour une plateforme de ciblage et taille de leurs audiences. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Public total du client</b> </p> </td> 
   <td colname="col2"> <p>Nombre de périphériques qui ont réalisé une caractéristique basée sur des règles sur vos propriétés ou une caractéristique intégrée de vos fichiers hors ligne pendant la fenêtre de recherche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taux de correspondance d’audience adressable</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Nombre de chevauchements de périphériques qui ont réalisé une caractéristique basée sur des règles ou une caractéristique intégrée au cours de la fenêtre de retour arrière et de périphériques sur lesquels nous avons synchronisé un ID avec la destination choisie, quel que soit le moment de la synchronisation. </p> 
    </draft-comment> <p>Cette mesure représente les périphériques qui : 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Ont réalisé une caractéristique basée sur des règles ou intégrée lors de la fenêtre de retour arrière <b>ET</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Synchronisez l’ID avec la destination choisie, quelle que soit l’heure de la synchronisation. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taux de correspondance client</b> </p> </td> 
   <td colname="col2"> <p>Audience adressable au client : audience totale du client exprimée en %. </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <b>Population totale des segments</b> </p> </td> 
   <td colname="col2"> <p>Nombre de tous les périphériques qui étaient membres de votre segment pendant la période de recherche en arrière du rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Public adressable aux segments</b> </p> </td> 
   <td colname="col2"> <p>Nombre d’utilisateurs qui ont appartenu au segment pendant la période de recherche en arrière du rapport et qui ont une synchronisation active des identifiants sur votre site. Les segments peuvent inclure vos propres données propriétaires et vos propres données propriétaires et tierces, par le biais de caractéristiques acquises dans <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>Conseil : Lorsqu’elle est utilisée avec la période de rétrospective d’une journée, cette mesure peut vous aider à comprendre l’état actuel de vos segments. En effet, la mesure Public <span class="wintitle"> adressable</span> au segment représente les utilisateurs qui sont restés dans un segment au cours de la veille. Combinez cela au fait qu’ <span class="keyword"> Audience Manager</span> actualise <span class="wintitle"> quotidiennement les audiences</span> adressables, en combinant cette mesure et cette période de consultation, vous obtenez l’instantané le plus récent de vos segments. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taux de correspondance des segments</b> </p> </td> 
   <td colname="col2"> <p>Public adressable aux segments : Total des segments Population exprimée en %. </p> </td> 
  </tr>  
 </tbody> 
</table>

## Interface d’audience adressable {#addressable-audience-interface}

Cette [!UICONTROL Addressable Audience] fonction transforme ce concept abstrait en données quantifiables. Dans [!DNL Audience Manager]cette fonctionnalité, le chevauchement de l’audience avec les visualisations de données fournit des informations en un coup d’oeil, ainsi que des données numériques sous forme de tableau.

[!UICONTROL Addressable Audiences] se trouve dans **[!UICONTROL Audience Data > Destinations]**. Sélectionnez cette option **[!UICONTROL Integrated Platforms > Device-Based]** pour afficher les mesures d’audiences adressables.

![](assets/addressable-audiences-landing.png)

Les trois mesures que vous pouvez voir sur la page d’entrée Audiences adressables représentent :

| Mesure | Description |
---------|----------|
| **Audience adressable (périphériques)** | Cette mesure représente l’audience adressable au client (décrite dans le tableau ci-dessus) *pour les 30 derniers jours.* |
| **Taux de correspondance** | Cette mesure représente le taux de correspondance d’audience adressable (décrit dans le tableau ci-dessus) *pour les 30 derniers jours*. |
| **Audience adressable sur la durée de vie (périphériques)** | Nombre de tous les périphériques qui ont interagi avec tous les clients d’Audience Manager au niveau de la plate-forme pendant la période de recherche en arrière du rapport et qui peuvent correspondre à cette destination. Voir Mesures [au niveau de la](/help/using/features/addressable-audiences.md#platform-level-metrics) plateforme pour plus d’informations. |

Cliquez sur le nom d’une destination serveur à serveur pour afficher les données d’audience adressables. Remarque : cette fonctionnalité renvoie des données pour les destinations serveur à serveur uniquement et l’accès requiert des autorisations d’administrateur.

![](assets/addressableAudiences.png)

L’examen de ces données peut vous aider à :

* **** Prévisions et planification : Les [!UICONTROL Segment Addressable Audience] données vous donnent plus de granularité dans les segments que vous prévoyez d’envoyer vers une destination pour le ciblage et l’activation de l’audience.

* **** Évaluations de performances : Cette [!UICONTROL Addressable Audiences] fonctionnalité est également un outil de dépannage. Il vous permet d’examiner les performances des campagnes, de comprendre la portée des campagnes et de comparer les résultats attendus aux partenaires de ciblage/activation si vous ne voyez pas les résultats attendus.

### Prospection avec des données tierces et implications pour les taux de correspondance

Avant d’acheter des données tierces pour l’acquisition d’audiences, les clients peuvent valider le chevauchement avec d’autres fournisseurs de données. Cela peut vous aider à prendre une décision éclairée avant d’acheter de nouvelles données. Les synchronisations d’ID pour les données tierces achetées reposent non seulement sur le chevauchement de vos données, mais également sur les empreintes des fournisseurs tiers avec tous les autres [!DNL Audience Manager] clients. Votre [!DNL Adobe] consultant peut vous aider à identifier d’autres sources de données pertinentes afin d’optimiser les campagnes de prospection.

### Utilisateurs mobiles et taux de correspondance

Il existe des lacunes lors de la tentative de connexion des utilisateurs [!DNL Safari] d’applications mobiles lorsqu’il n’existe aucun cookie tiers. Il est donc difficile de synchroniser les utilisateurs avec certains partenaires, car seuls les [!DNL Adobe] identifiants des cookies tiers synchronisés sont fournis dans les journaux de diffusion multimédia. C’est la raison pour laquelle vous pouvez constater des taux [de correspondance](../features/addressable-audiences.md#low-match-rates) faibles pour vos destinations.

## Plages de dates dans les audiences et destinations adressables {#date-ranges}

Lisez les sections ci-dessous pour connaître les plages de dates disponibles et la façon dont les données sortent de chaque intervalle dans les rapports pour une période [!UICONTROL Addressable Audience] ou [!UICONTROL Destination].

## Plages de dates et fuseaux horaires disponibles {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Les rapports pour vos [!UICONTROL Addressable Audiences] et [Destinations](../features/destinations/destinations.md) utilisent les mêmes intervalles de plage de dates. Les options de plage de dates incluent :

* [!UICONTROL Last 1 Day] (Cet intervalle s’étend de minuit à minuit de la période précédente de 24 heures. Il ne s’agit pas d’une mesure en temps réel ou en cours.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Toutes les dates et plages de dates sont définies dans le [!DNL UTC] fuseau horaire. Voir Fuseaux [horaires dans Audience Manager](../reference/aam-time-zones.md).

## Données dans les intervalles de plage de dates {#date-range-intervals}

Les [!UICONTROL Addressable Audience] mesures et [!UICONTROL Destination] les mesures renvoient un nombre d’utilisateurs uniques pour l’intervalle de temps sélectionné. Par exemple, un visiteur n’est comptabilisé qu’une seule fois, même s’il vient plusieurs fois sur votre site. La première visite est la visite unique et est enregistrée. Les visites suivantes sont des visites de retour et ne sont pas comptabilisées car elles ne sont pas uniques.

Les plages de dates contiennent des données pour l’intervalle de temps sélectionné ou plus ancien. Et les données sortent de chaque intervalle de rapport au fil du temps. Supposons, par exemple, que deux visiteurs s’affichent après avoir choisi l’ [!UICONTROL Last 30 Days] option. Dans les rapports, ces visiteurs :

* *Sera* inclus dans les résultats renvoyés par les intervalles de temps plus longs (60 jours, 90 jours et Durée de vie).
* *Ne sera* pas inclus dans les intervalles plus courts qui précèdent l’ [!UICONTROL Last 30 Day] option (Actuel, 7 et 14 jours).

Et le 31, ces visiteurs ne s'affichent que dans les 60 jours, 90 jours et [!UICONTROL Lifetime] les résultats. Ils ont vieilli sur l'intervalle de 30 jours. Les visiteurs ne sortent pas de l’ [!UICONTROL Lifetime] intervalle.

## Mesures d’audience adressables {#addressable-audience-metrics}

Cette section décrit les types de mesures fournis par [!UICONTROL Addressable Audiences].

### Mesures au niveau du client {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Ces mesures renvoient des données pour les caractéristiques réalisées lorsque les visiteurs se rendent sur votre site ou lorsque vous envoyez des fichiers de données entrants [!DNL Audience Manager]. Ces mesures fournissent une vue d’ensemble de la taille de l’audience pour votre compte.

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audience adressable au client</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Nombre de chevauchements de périphériques qui ont réalisé une caractéristique basée sur des règles ou une caractéristique intégrée au cours de la fenêtre de retour arrière et de périphériques sur lesquels nous avons synchronisé un ID avec la destination choisie, quel que soit le moment de la synchronisation. </p> 
    </draft-comment> <p>Cette mesure représente les périphériques qui : 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Ont réalisé une caractéristique basée sur des règles ou intégrée lors de la fenêtre de retour arrière <b>ET</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Synchronisez l’ID avec la destination choisie, quelle que soit l’heure de la synchronisation. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Public total du client</b> </p> </td> 
   <td colname="col2"> <p>Nombre de périphériques qui ont réalisé une caractéristique basée sur des règles sur vos propriétés ou une caractéristique intégrée de vos fichiers hors ligne pendant la fenêtre de recherche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taux de correspondance client</b> </p> </td> 
   <td colname="col2"> <p>Audience adressable au client : audience totale du client exprimée en %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Mesures de correspondance au niveau du segment {#segment-level-metrics}

Ces mesures renvoient des données sur l’appartenance à un segment. Elles vous aident à obtenir une vue plus précise et plus précise de la taille de l’audience pour chacun de vos segments.

>[!NOTE]
>
>La manière dont la fenêtre de recherche en arrière est appliquée au niveau du segment est différente de celle appliquée au niveau du client. Les visiteurs peuvent venir sur le site et réaliser une caractéristique il y a 10 jours, et ils peuvent être inclus dans un segment depuis lors et ont abandonné le segment il y a 2 jours. Lorsque la recherche en amont de 7 jours est appliquée, ces visiteurs sont comptabilisés au niveau du segment, mais pas au niveau du client.

<table id="table_4185AA02CC774B6C93B02E45F88BBBD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Public adressable aux segments</b> </p> </td> 
   <td colname="col2"> <p>Nombre d’utilisateurs qui ont appartenu au segment pendant la période de recherche en arrière du rapport et qui ont une synchronisation active des identifiants sur votre site. Les segments peuvent inclure vos propres données propriétaires et vos propres données propriétaires et tierces, par le biais de caractéristiques acquises dans <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>Conseil : Lorsqu’elle est utilisée avec la période de rétrospective d’une journée, cette mesure peut vous aider à comprendre l’état actuel de vos segments. En effet, la mesure Public <span class="wintitle"> adressable</span> au segment représente les utilisateurs qui sont restés dans un segment au cours de la veille. Combinez cela au fait qu’ <span class="keyword"> Audience Manager</span> actualise <span class="wintitle"> quotidiennement les audiences</span> adressables, en combinant cette mesure et cette période de consultation, vous obtenez l’instantané le plus récent de vos segments. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Population totale des segments</b> </p> </td> 
   <td colname="col2"> <p>Nombre de tous les périphériques qui étaient membres de votre segment pendant la période de recherche en arrière du rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taux de correspondance des segments</b> </p> </td> 
   <td colname="col2"> <p>Public adressable aux segments : Total des segments Population exprimée en %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Mesures au niveau de la plateforme {#platform-level-metrics}

Cette mesure renvoie des données sur les activités collectées auprès de tous les clients d’Audience Manager. Ils peuvent offrir une vue plus large du public du client par rapport aux clients d’Audience Manager agrégés.

<table id="table_B6654D9858FF46AF95B1C181D4608D26"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audience adressable d’Audience Manager</b> </p> </td> 
   <td colname="col2"> <p>Nombre de tous les périphériques qui ont interagi avec tous les clients d’Audience Manager au niveau de la plate-forme pendant la période de recherche en arrière du rapport et qui peuvent correspondre à la destination choisie. </p> <p>Cette mesure est utile car elle vous montre : </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> Taille de l’audience adressable totale que <span class="keyword"> Audience Manager</span> peut atteindre sur une destination de ciblage particulière. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">Taille du pool de profils d’Audience Manager <span class="keyword"></span> pour une plateforme de ciblage et taille de leurs audiences. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Comparaison des audiences adressables au client et au segment{#comparing-metrics}

Vous ne devez pas comparer les [!UICONTROL Customer Addressable Audience] mesures et [!UICONTROL Segment Addressable Audience] les mesures pour déterminer si l’une est plus importante que l’autre. Il s’agit de mesures distinctes, différentes et indépendantes. Comme nous l'avons vu dans les définitions ci-dessus, chacune d'elles provient de différents ensembles de données. Dans ces conditions, évitez de tirer des conclusions si une mesure est plus importante que l’autre. Tout ce que vous pouvez dire en comparant ces éléments est :

* [!UICONTROL Customer Addressable Audiences] est basée sur les personnalisations *de vos propres données* propriétaires. Cette mesure offre une vue d’ensemble et exhaustive de votre intégration à un partenaire de données.

* [!UICONTROL Segment Addressable Audiences] est basée sur les qualifications de segment *pour vos propres données propriétaires, ainsi que sur les données* tierces et secondaires. Cette mesure fournit une vue granulaire et plus précise de vos audiences adressables dans une plateforme de ciblage.

## Causes des taux de faible correspondance pour les audiences adressables {#low-match-rates}

Éléments communs responsables des faibles taux de [!UICONTROL Addressable Audience] correspondance ou des écarts dans les nombres signalés.

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
   <td colname="col2"> <p>La plupart des intégrations serveur à serveur reposent sur des processus de synchronisation facilités par des cookies tiers. Toutefois, les environnements mobiles n’utilisent pas de cookies tiers. Par conséquent, les nombres d’audiences adressables peuvent sembler faibles par rapport à la taille du segment. </p> <p>Depuis janvier 2018, vous pouvez activer les audiences mobiles dans les mêmes destinations Google et Adobe Advertising Cloud configurées pour les audiences basées sur des cookies. Cela signifie que vous pouvez envoyer des segments avec un cookie combiné et l’appartenance à un ID mobile à vos destinations Google et Advertising Cloud, mais gardez à l’esprit que les audiences adressables affichent uniquement le chevauchement entre les identifiants de cookie et les destinations. Audience Manager envoie 100 % des audiences mobiles vers des destinations, mais les audiences mobiles ne sont pas mesurées par la mesure Audience adressable. </p> <p> <p><b>Remarque</b>:  Par exemple, prenez un segment avec une population de 1 000 000. Si vous mappez ce segment à une destination Google ou Adobe Advertising Cloud, vous verrez peut-être une audience adressable de 700 000 périphériques et un taux de correspondance de 70 %. L’adhésion de 700 000 membres se compose d’identifiants de cookie synchronisés avec la destination. Votre audience adressable peut, en fait, être beaucoup plus élevée, car les identifiants mobiles adressables n’apparaissent pas dans cette mesure. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Trafic Safari</b> </p> </td> 
   <td colname="col2"> <p>Safari bloque les cookies tiers. Cela empêche Audience Manager de synchroniser les identifiants avec la destination. Avec l’introduction de <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, vous pouvez vous attendre à ce que vos audiences adressables n’incluent pas les utilisateurs Safari. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Impressions de médias surveillées</b> </p> </td> 
   <td colname="col2"> <p>En raison des bonnes pratiques du serveur d’annonces, les synchronisations d’ID ne sont pas effectuées dans les balises publicitaires. Les clients qui font une grande quantité de publicité hors site ne synchronisent pas les utilisateurs avec les intégrations tierces dans ces environnements. En outre, une grande quantité de données d’impression multimédia collectées pourrait réduire le nombre d’audiences adressables. </p> </td>
  </tr> 
 </tbody> 
</table>

## Dépannage des audiences adressables {#troubleshooting}

Outre les taux de correspondance de surface, vous pouvez également utiliser [!UICONTROL Addressable Audiences] comme outil de dépannage.

<!-- addressable-audiences-troubleshooting.xml -->

Supposons, par exemple, que vous envoyiez un segment vers une destination et que cette destination affiche de faibles nombres de rapports. La vérification des [!UICONTROL Addressable Audience] résultats vous montrera s'il s'agit d'un problème technique ou simplement d'un cas de faible taux de correspondance. Un faible taux de correspondance indique que votre destination n’est pas tout à fait idéale pour les segments sélectionnés. Cependant, une différence dans le nombre total d’audiences adressables entre Audience Manager et la destination indique un problème d’intégration, de synchronisation ou autre problème technique. Dans ce cas, contactez votre gestionnaire de compte.