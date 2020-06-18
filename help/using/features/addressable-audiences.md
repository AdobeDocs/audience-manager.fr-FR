---
description: Présentation de la fonction d’Audience adressable et des cas d’utilisation.
keywords: DIL
seo-description: Présentation de la fonction d’Audience adressable et des cas d’utilisation.
seo-title: Audiences adressables
solution: Audience Manager
title: Audiences adressables
topic: DIL API
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '2059'
ht-degree: 0%

---


# Audience adressable {#addressable-audiences}

Présentation des cas d’ [!UICONTROL Addressable Audience] utilisation et des fonctionnalités.

## Qu&#39;est-ce qu&#39;une Audience adressable ? {#addressable-audience-description}

La [!UICONTROL Addressable Audiences] fonction vous montre le chevauchement entre les audiences que vous voyez sur toutes vos propriétés où [!DNL Audience Manager] collecte des données et la destination sélectionnée. Pour vous aider à comprendre ce concept, jetez un coup d&#39;oeil à l&#39;illustration ci-dessous. Le chevauchement entre chaque cercle représente les différents types d&#39;audiences adressables.

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
   <td colname="col1"> <p> <b>Audience adressable à une Audience Manager pour une destination</b> </p> </td> 
   <td colname="col2"> <p>Nombre de tous les périphériques qui ont interagi avec tous les clients d’Audience Manager au niveau de la plate-forme pendant la période de recherche en arrière-plan du rapport et qui peuvent correspondre à la destination choisie. </p> <p>Cette mesure est utile car elle vous montre : </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> Taille de l’audience adressable totale que <span class="keyword"> l’Audience Manager</span> peut atteindre sur une destination de ciblage particulière. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">La taille du pool de profils <span class="keyword"> d’Audience Manager</span> pour une plateforme de ciblage et la taille de leurs audiences. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audience totale du client</b> </p> </td> 
   <td colname="col2"> <p>Nombre de périphériques qui ont réalisé une caractéristique basée sur des règles sur vos propriétés ou une caractéristique intégrée de vos fichiers hors ligne pendant la fenêtre de recherche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taux de correspondance des Audiences adressables</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Nombre de chevauchements de périphériques ayant réalisé une caractéristique basée sur des règles ou une caractéristique intégrée pendant la fenêtre de retour arrière et de périphériques sur lesquels nous avons synchronisé un identifiant avec la destination choisie, quelle que soit l’heure de la synchronisation. </p> 
    </draft-comment> <p>Cette mesure représente les périphériques qui : 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Ont réalisé une caractéristique basée sur des règles ou une caractéristique intégrée lors de la fenêtre de retour arrière <b>ET</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Synchronisez l’ID avec la destination choisie, quelle que soit l’heure de la synchronisation. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taux de correspondance client</b> </p> </td> 
   <td colname="col2"> <p>Audience adressable au client : Audience totale du client exprimée en %. </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <b>Population totale des segments</b> </p> </td> 
   <td colname="col2"> <p>Nombre de tous les périphériques qui ont été membres de votre segment pendant la période de recherche en arrière du rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audience des segments adressables</b> </p> </td> 
   <td colname="col2"> <p>Nombre d’utilisateurs ayant appartenu au segment au cours de la période de recherche en arrière du rapport et ayant une synchronisation active des identifiants sur votre site. Les segments peuvent inclure vos propres données propriétaires et les données tierces et tierces, au moyen de caractéristiques acquises dans l’ <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>Conseil : Lorsqu’elle est utilisée avec la période de recherche en amont d’un jour, cette mesure peut vous aider à comprendre l’état actuel de vos segments. En effet, la mesure Audience <span class="wintitle"> adressable</span> Segment représente les utilisateurs qui sont restés dans un segment au cours de la journée précédente. Combinez cela au fait que <span class="keyword"> l’Audience Manager</span> actualise quotidiennement les Audiences <span class="wintitle"></span> adressables, en combinant cette mesure et cette période de recherche, vous obtenez l’instantané le plus à jour de vos segments. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taux de correspondance des segments</b> </p> </td> 
   <td colname="col2"> <p>Audience des segments adressables : Total de la population des segments exprimé en %. </p> </td> 
  </tr>  
 </tbody> 
</table>

## Interface d&#39;Audience adressable {#addressable-audience-interface}

Cette [!UICONTROL Addressable Audience] caractéristique transforme ce concept abstrait en données quantifiables. Dans [!DNL Audience Manager]cette fonction, les audiences se chevauchent avec les visualisations de données qui fournissent des informations en un coup d’oeil ainsi que des données numériques sous forme de tableau.

[!UICONTROL Addressable Audiences] se trouve dans **[!UICONTROL Audience Data > Destinations]**. Sélectionnez cette option **[!UICONTROL Integrated Platforms > Device-Based]** pour afficher les mesures d’audiences adressables.

![](assets/addressable-audiences-landing.png)

Les trois mesures que vous pouvez voir sur le [!UICONTROL Addressable Audiences] landing page représentent :

| Mesure | Description |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Cette mesure représente la [!UICONTROL Customer Addressable Audience] (décrite dans le tableau ci-dessus) *pour les 30 derniers jours.* |
| **[!UICONTROL Match Rate]** | Cette mesure représente la [!UICONTROL Addressable Audience Match Rate] (décrite dans le tableau ci-dessus) *pour les 30 derniers jours*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Nombre de tous les périphériques qui ont interagi avec tous les [!DNL Audience Manager] clients au niveau de la plate-forme au cours de la période de recherche en arrière-plan du rapport et qui peuvent correspondre à cette destination. Voir Mesures [de niveau](/help/using/features/addressable-audiences.md#platform-level-metrics) Platform pour en savoir plus. |

Cliquez sur le nom d&#39;une destination serveur à serveur pour vue vos données d&#39;audience adressables. Remarque : cette fonctionnalité renvoie uniquement des données pour les destinations serveur à serveur et l’accès nécessite des autorisations d’administrateur.

![](assets/addressableAudiences.png)

La révision de ces données peut vous aider à :

* **Prévisions et planification :** [!UICONTROL Segment Addressable Audience] les données vous donnent plus de granularité dans les segments que vous prévoyez d’envoyer à une destination pour le ciblage et l’activation des audiences.

* **Évaluations de performances :** Cette [!UICONTROL Addressable Audiences] fonctionnalité est également un outil de dépannage. Il vous permet d’examiner les performances des campagnes, de comprendre la portée des campagnes et de vérifier avec les partenaires de ciblage/d’activation si vous ne voyez pas les résultats attendus.

### Prospection avec des données tierces et implications pour les taux de correspondance

Avant d’acheter des données tierces pour l’acquisition d’audiences, les clients peuvent valider le chevauchement avec d’autres fournisseurs de données. Cela peut vous aider à prendre une décision éclairée avant d&#39;acheter de nouvelles données. La synchronisation des identifiants pour les données tierces achetées repose non seulement sur le chevauchement de vos données, mais également sur les empreintes des fournisseurs tiers par rapport à tous les autres [!DNL Audience Manager] clients. Votre [!DNL Adobe] consultant peut vous aider à identifier d’autres sources de données pertinentes pour optimiser les campagnes de prospection.

### Utilisateurs mobiles et taux de correspondance

Il existe des lacunes lors de la tentative de connexion [!DNL Safari] d’utilisateurs d’applications mobiles lorsqu’il n’existe aucun cookie tiers. Il est donc difficile de synchroniser les utilisateurs avec certains partenaires, car seuls les [!DNL Adobe] identifiants des cookies tiers synchronisés sont fournis dans les logs de diffusion multimédias. C’est la raison pour laquelle vous pouvez constater des taux [de correspondance](../features/addressable-audiences.md#low-match-rates) faibles pour vos destinations.

## Plages de dates dans les Audiences et destinations adressables {#date-ranges}

Lisez les sections ci-dessous pour connaître les plages de dates disponibles et la façon dont les données s’échelonnent au-delà de chaque intervalle dans les rapports pour une période [!UICONTROL Addressable Audience] ou [!UICONTROL Destination].

## Plages de dates et fuseaux horaires disponibles {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Les rapports pour vos [!UICONTROL Addressable Audiences] et [Destinations](../features/destinations/destinations.md) utilisent les mêmes intervalles de plage de dates. Les options de plage de dates sont les suivantes :

* [!UICONTROL Last 1 Day] (Cet intervalle s’étend de minuit à minuit de la période précédente de 24 heures. Il ne s’agit pas d’une mesure en temps réel ou en cours.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Toutes les dates et plages de dates sont définies dans le [!DNL UTC] fuseau horaire. Voir [Fuseaux horaires en Audience Manager](../reference/aam-time-zones.md).

## Données dans les intervalles de plage de dates {#date-range-intervals}

Les [!UICONTROL Addressable Audience] mesures et [!UICONTROL Destination] les mesures renvoient un nombre d’utilisateurs uniques pour l’intervalle de temps sélectionné. Par exemple, un visiteur n’est comptabilisé qu’une seule fois, même s’il vient plusieurs fois sur votre site. La première visite est la visite unique et est enregistrée. Les visites suivantes reviennent sur le site et ne sont pas comptabilisées car elles ne sont pas uniques.

Les plages de dates contiennent des données pour l’intervalle de temps sélectionné ou plus ancien. De plus, les données vieillissent au fil de chaque intervalle de rapport au fil du temps. Supposons, par exemple, que vous voyiez 2 visiteurs après avoir choisi l’ [!UICONTROL Last 30 Days] option. Dans les rapports, ces visiteurs :

* *Sera* inclus dans les résultats renvoyés par les intervalles de temps plus longs (60 jours, 90 jours et Durée de vie).
* *Ne sera pas* inclus dans les intervalles plus courts qui précèdent l’ [!UICONTROL Last 30 Day] option (Actuel, 7 et 14 jours).

Et, au 31° jour, ces visiteurs n&#39;apparaissent que dans les 60, 90 jours, et les [!UICONTROL Lifetime] résultats. Ils ont vieilli sur l&#39;intervalle de 30 jours. Les Visiteurs ne vieillissent pas en dehors de l&#39; [!UICONTROL Lifetime] intervalle.

## Mesures d&#39;Audience adressables {#addressable-audience-metrics}

Cette section décrit les types de mesures fournis par [!UICONTROL Addressable Audiences].

### Mesures au niveau du client {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Ces mesures renvoient des données pour les caractéristiques réalisées lorsque des visiteurs se rendent sur votre site ou lorsque vous envoyez des fichiers de données entrants à [!DNL Audience Manager]. Ces mesures fournissent une vue complète de la taille de l’audience pour votre compte.

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
     <p>Nombre de chevauchements de périphériques ayant réalisé une caractéristique basée sur des règles ou une caractéristique intégrée pendant la fenêtre de retour arrière et de périphériques sur lesquels nous avons synchronisé un identifiant avec la destination choisie, quelle que soit l’heure de la synchronisation. </p> 
    </draft-comment> <p>Cette mesure représente les périphériques qui : 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Ont réalisé une caractéristique basée sur des règles ou une caractéristique intégrée lors de la fenêtre de retour arrière <b>ET</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Synchronisez l’ID avec la destination choisie, quelle que soit l’heure de la synchronisation. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audience totale du client</b> </p> </td> 
   <td colname="col2"> <p>Nombre de périphériques qui ont réalisé une caractéristique basée sur des règles sur vos propriétés ou une caractéristique intégrée de vos fichiers hors ligne pendant la fenêtre de recherche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taux de correspondance client</b> </p> </td> 
   <td colname="col2"> <p>Audience adressable au client : Audience totale du client exprimée en %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Mesures de correspondance au niveau du segment {#segment-level-metrics}

Ces mesures renvoient des données sur l’appartenance à un segment. Elles vous aident à obtenir une vue plus précise et plus précise de la taille de l’audience pour chacun de vos segments.

>[!NOTE]
>
>La manière dont la fenêtre de recherche en amont est appliquée au niveau du segment est différente de celle appliquée au niveau du client. Les Visiteurs peuvent venir sur le site et réaliser une caractéristique il y a 10 jours, et ils pourraient être inclus dans un segment depuis lors et ont abandonné le segment il y a 2 jours. Lorsque la recherche en amont de 7 jours est appliquée, ces visiteurs sont comptabilisés au niveau du segment mais pas au niveau du client.

<table id="table_4185AA02CC774B6C93B02E45F88BBBD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audience des segments adressables</b> </p> </td> 
   <td colname="col2"> <p>Nombre d’utilisateurs ayant appartenu au segment au cours de la période de recherche en arrière du rapport et ayant une synchronisation active des identifiants sur votre site. Les segments peuvent inclure vos propres données propriétaires et les données tierces et tierces, au moyen de caractéristiques acquises dans l’ <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>Conseil : Lorsqu’elle est utilisée avec la période de recherche en amont d’un jour, cette mesure peut vous aider à comprendre l’état actuel de vos segments. En effet, la mesure Audience <span class="wintitle"> adressable</span> Segment représente les utilisateurs qui sont restés dans un segment au cours de la journée précédente. Combinez cela au fait que <span class="keyword"> l’Audience Manager</span> actualise quotidiennement les Audiences <span class="wintitle"></span> adressables, en combinant cette mesure et cette période de recherche, vous obtenez l’instantané le plus à jour de vos segments. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Population totale des segments</b> </p> </td> 
   <td colname="col2"> <p>Nombre de tous les périphériques qui ont été membres de votre segment pendant la période de recherche en arrière du rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Taux de correspondance des segments</b> </p> </td> 
   <td colname="col2"> <p>Audience des segments adressables : Total de la population des segments exprimé en %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Mesures de niveau Platform {#platform-level-metrics}

Cette mesure renvoie des données sur les activités collectées pour tous les [!DNL Audience Manager] clients. Elles peuvent fournir une vue plus large de l&#39;audience du client par rapport aux [!DNL Audience Manager] clients agrégés.

<table id="table_B6654D9858FF46AF95B1C181D4608D26"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audience adressable aux Audiences Manager</b> </p> </td> 
   <td colname="col2"> <p>Nombre de tous les périphériques qui ont interagi avec tous les clients d’Audience Manager au niveau de la plate-forme pendant la période de recherche en arrière-plan du rapport et qui peuvent correspondre à la destination choisie. </p> <p>Cette mesure est utile car elle vous montre : </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> Taille de l’audience adressable totale que <span class="keyword"> l’Audience Manager</span> peut atteindre sur une destination de ciblage particulière. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">La taille du pool de profils <span class="keyword"> d’Audience Manager</span> pour une plateforme de ciblage et la taille de leurs audiences. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Comparaison des Audiences adressables aux clients et aux segments{#comparing-metrics}

Vous ne devriez pas comparer les [!UICONTROL Customer Addressable Audience] mesures et [!UICONTROL Segment Addressable Audience] les mesures pour déterminer si l’une est plus significative que l’autre. Il s’agit de mesures distinctes, différentes et indépendantes. Comme indiqué dans les définitions ci-dessus, chacune de ces variables est dérivée de différents ensembles de données. Dans ce contexte, évitez de tirer des conclusions si une mesure est supérieure à l’autre. Tout ce que vous pouvez dire en comparant ces éléments est :

* [!UICONTROL Customer Addressable Audiences] est basée sur les personnalisations *de vos propres données* propriétaires. Cette mesure fournit une vue large et complète de votre intégration à un partenaire de données.

* [!UICONTROL Segment Addressable Audiences] repose sur les qualifications des segments *pour vos propres données propriétaires, ainsi que sur les données* tierces et secondaires. Cette mesure fournit une vue plus précise et granulaire de vos audiences adressables dans une plateforme de ciblage.

## Causes des faibles taux de correspondance pour les Audiences adressables {#low-match-rates}

Éléments communs à l&#39;origine de faibles taux de [!UICONTROL Addressable Audience] correspondance ou d&#39;écarts dans les chiffres signalés.

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
   <td colname="col2"> <p>La plupart des intégrations serveur à serveur reposent sur des processus de synchronisation facilités par des cookies tiers. Cependant, les environnements mobiles n’utilisent pas de cookies tiers. Par conséquent, vos numéros d'Audience adressables peuvent sembler faibles par rapport à la taille du segment. </p> <p>Depuis janvier 2018, vous pouvez activer les audiences mobiles dans les mêmes destinations Google et Adobe Advertising Cloud configurées pour les audiences basées sur les cookies. Cela signifie que vous pouvez envoyer des segments avec un cookie combiné et un ID mobile à vos destinations Google et Advertising Cloud, mais gardez à l’esprit que les Audiences adressables n’affichent que le chevauchement entre les identifiants de cookie et les destinations. L’Audience Manager envoie 100 % des audiences mobiles vers les destinations, mais les audiences mobiles ne sont pas mesurées par la mesure Audience adressable. </p> <p> <p><b>Remarque</b>:  Par exemple, prenez un segment avec une population de 1 000 000. Si vous mappez ce segment à une destination Google ou Adobe Advertising Cloud, vous verrez peut-être une Audience adressable de 700 000 périphériques et un taux de correspondance de 70 %. Les 700 000 membres sont composés d’ID de cookie qui ont un ID synchronisé avec la destination. Votre Audience adressable peut, en fait, être beaucoup plus élevée, car les identifiants mobiles adressables n’apparaissent pas dans cette mesure. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Trafic Safari</b> </p> </td> 
   <td colname="col2"> <p>Safari bloque les cookies tiers. Cela empêche l’Audience Manager de synchroniser les identifiants avec la destination. Avec l'introduction de <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, vous pouvez vous attendre à ce que vos audiences adressables n'incluent pas les utilisateurs Safari. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Impressions de médias suivies</b> </p> </td> 
   <td colname="col2"> <p>En raison des bonnes pratiques du serveur d’annonces, les synchronisations d’ID ne sont pas effectuées dans les balises d’annonce. Les clients qui effectuent une grande quantité de publicité hors site ne synchronisent pas les utilisateurs avec les intégrations tierces dans ces environnements. En outre, une grande quantité de données d'impression des médias collectées pourrait réduire le nombre d'audiences adressables. </p> </td>
  </tr> 
 </tbody> 
</table>

## Dépannage avec des Audiences adressables {#troubleshooting}

Outre les taux de correspondance de surface, vous pouvez également utiliser [!UICONTROL Addressable Audiences] comme outil de dépannage.

<!-- addressable-audiences-troubleshooting.xml -->

Supposons, par exemple, que vous envoyiez un segment vers une destination et que cette destination affiche un nombre de rapports faible. Si vous vérifiez les [!UICONTROL Addressable Audience] résultats, vous verrez s&#39;il s&#39;agit d&#39;un problème technique ou simplement d&#39;un cas de faible taux de correspondance. Un faible taux de correspondance indique que votre destination n’est pas tout à fait idéale pour les segments sélectionnés. Cependant, une différence dans le nombre total d’audiences adressables entre [!DNL Audience Manager] et la destination indique un problème d’intégration, de synchronisation ou autre problème technique. Dans ce cas, contactez votre gestionnaire de compte.