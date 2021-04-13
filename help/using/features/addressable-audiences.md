---
description: Présentation de la fonction d’Audience adressable et des cas d’utilisation.
keywords: DIL
seo-description: Présentation de la fonction d’Audience adressable et des cas d’utilisation.
seo-title: Audiences adressables
solution: Audience Manager
title: Audiences adressables
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Taux de correspondance
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1827'
ht-degree: 1%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Présentation des cas d&#39;utilisation et de fonctionnalités [!UICONTROL Addressable Audience].

## Qu’est-ce qu’une [!UICONTROL Addressable Audience]? {#addressable-audience-description}

La fonction [!UICONTROL Addressable Audiences] montre le chevauchement entre les audiences que vous voyez sur toutes vos propriétés où [!DNL Audience Manager] collecte des données et la destination sélectionnée. Pour vous aider à comprendre ce concept, jetez un coup d&#39;oeil à l&#39;illustration ci-dessous. Le chevauchement entre chaque cercle représente les différents types d&#39;audiences adressables.

![](assets/addressableAudienceVenn.png)


| Mesure | Description |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] pour un  [!UICONTROL Destination] | Nombre de tous les périphériques qui ont interagi avec tous les clients [!DNL Audience Manager] au niveau de la plate-forme au cours de la période de recherche en amont du rapport et qui peuvent correspondre à votre [!UICONTROL destination] choix. <br><br>Cette mesure est utile car elle vous montre : <ul><li>Taille du total [!UICONTROL addressable audience] que [!DNL Audience Manager] peut atteindre sur un ciblage particulier [!UICONTROL destination].</li><li>Taille du pool de profils [!DNL Audience Manager] pour une plateforme de ciblage et taille de leurs audiences.</li></ul> |
| [!UICONTROL Customer Total Audience] | Nombre de périphériques qui ont réalisé un [!UICONTROL rule-based trait] sur vos propriétés ou un [!UICONTROL onboarded trait] à partir de vos fichiers hors ligne pendant la fenêtre de recherche. |
| [!UICONTROL Addressable Audience Match Rate] | Nombre de chevauchements de périphériques qui ont réalisé un [!UICONTROL rule-based trait] ou un [!UICONTROL onboarded trait] au cours de la fenêtre de retour arrière et de périphériques pour lesquels nous avons synchronisé un identifiant avec le [!UICONTROL destination] sélectionné, quel que soit le moment de la synchronisation.<br><br>Cette mesure représente les périphériques qui :<ul><li>Ont réalisé un [!UICONTROL rule-based] ou un [!UICONTROL onboarded trait] au cours de la fenêtre de retour en arrière `AND`</li><li>Ayez un ID synchronisé avec le [!UICONTROL destination] sélectionné, quelle que soit l&#39;heure de la synchronisation.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] :  [!UICONTROL Customer Total Audience] exprimé en pourcentage. |
| [!UICONTROL Total Segment Population] | Nombre de tous les périphériques qui ont été membres de votre [!UICONTROL segment] pendant la période de consultation du rapport. |
| [!UICONTROL Segment Addressable Audience] | Nombre d’utilisateurs qui ont appartenu à [!UICONTROL segment] au cours de la période de recherche en arrière du rapport et qui ont une synchronisation principale de l’identifiant sur votre site. [!UICONTROL Segments] peuvent inclure vos propres données propriétaires et vos propres données propriétaires et tierces, par le biais  [!UICONTROL traits] d’une  [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Conseil : Lorsqu’elle est utilisée avec la période de recherche en amont d’un jour, cette mesure peut vous aider à comprendre l’état actuel de votre  [!UICONTROL segments]application. En effet, la mesure [!UICONTROL Segment Addressable Audience] représente les utilisateurs qui sont restés dans une [!UICONTROL segment] au cours de la journée précédente. Combinez cela au fait que [!DNL Audience Manager] actualise [!UICONTROL Addressable Audiences] quotidiennement, en combinant cette mesure et cette période de recherche, vous obtenez l’instantané le plus récent de votre [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] :  [!UICONTROL Total Segment Population] exprimé en pourcentage. |

## [!UICONTROL Addressable Audiences] Interface {#addressable-audience-interface}

La fonction [!UICONTROL Addressable Audience] transforme ce concept abstrait en données quantifiables. Dans [!DNL Audience Manager], cette fonction présente un chevauchement des audiences avec des visualisations de données qui fournissent des informations d’un coup d’oeil ainsi que des données numériques sous forme de tableau.

[!UICONTROL Addressable Audiences] se trouve dans  **[!UICONTROL Audience Data > Destinations]**. Sélectionnez **[!UICONTROL Integrated Platforms > Device-Based]** pour afficher les mesures d’audiences adressables.

![](assets/addressable-audiences-landing.png)

Les trois mesures que vous pouvez voir sur le landing page [!UICONTROL Addressable Audiences] représentent :

| Mesure | Description |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Cette mesure représente le [!UICONTROL Customer Addressable Audience] (décrit dans le tableau ci-dessus) *pour les 30 derniers jours.* |
| **[!UICONTROL Match Rate]** | Cette mesure représente [!UICONTROL Addressable Audience Match Rate] (décrit dans le tableau ci-dessus) *pour les 30 derniers jours*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Nombre de tous les périphériques qui ont interagi avec tous les clients [!DNL Audience Manager] au niveau de la plate-forme au cours de la période de recherche en amont du rapport et qui peuvent être associés à ce [!UICONTROL destination]. Voir [Mesures au niveau de la plate-forme](/help/using/features/addressable-audiences.md#platform-level-metrics) pour plus d’informations. |

Cliquez sur le nom d&#39;un [!UICONTROL server-to-server destination] pour vue vos données d&#39;audience adressables. Remarque : cette fonctionnalité renvoie uniquement des données pour [!UICONTROL server-to-server destinations] et l’accès nécessite des autorisations d’administrateur.

![](assets/addressableAudiences.png)

La révision de ces données peut vous aider à :

* **Prévision et planification :** [!UICONTROL Segment Addressable Audience] les données vous donnent plus de granularité dans les segments que vous prévoyez d’envoyer à une destination pour le ciblage et l’activation des audiences.

* **Évaluations de performances :** cette  [!UICONTROL Addressable Audiences] fonction est également un outil de dépannage. Il vous permet d’examiner les performances des campagnes, de comprendre la portée des campagnes et de vérifier avec les partenaires de ciblage/d’activation si vous ne voyez pas les résultats attendus.

### Prospection avec des données tierces et implications pour les taux de correspondance

Avant d’acheter des données tierces pour l’acquisition d’audiences, les clients peuvent valider le chevauchement avec d’autres fournisseurs de données. Cela peut vous aider à prendre une décision éclairée avant d&#39;acheter de nouvelles données. La synchronisation des identifiants pour les données tierces achetées repose non seulement sur le chevauchement de vos données, mais également sur les empreintes des fournisseurs tiers avec tous les autres clients [!DNL Audience Manager]. Votre [!DNL Adobe] consultant peut vous aider à identifier d&#39;autres sources de données pertinentes pour optimiser les campagnes de prospection.

### Utilisateurs mobiles et taux de correspondance

Il existe des lacunes lors de la tentative de connexion d&#39;[!DNL Safari] utilisateurs d&#39;applications mobiles lorsqu&#39;il n&#39;existe pas de [!DNL cookies] tiers. Il est donc difficile de synchroniser les utilisateurs avec certains partenaires, car seuls les [!DNL Adobe] identifiants de tiers synchronisés [!DNL cookies] sont fournis dans les logs de diffusion de médias. C&#39;est la raison pour laquelle vous pouvez voir [faibles taux de correspondance](../features/addressable-audiences.md#low-match-rates) pour votre [!UICONTROL destinations].

## Périodes dans [!UICONTROL Addressable Audiences] et [!UICONTROL Destinations] {#date-ranges}

Lisez les sections ci-dessous pour connaître les plages de dates disponibles et comment les données s’écoulent de chaque intervalle dans les rapports pour un [!UICONTROL Addressable Audience] ou [!UICONTROL Destination].

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

Toutes les dates et plages de dates sont définies dans le fuseau horaire [!DNL UTC]. Voir [Fuseaux horaires en Audience Manager](../reference/aam-time-zones.md).

## Données dans les intervalles de plage de dates {#date-range-intervals}

Les mesures [!UICONTROL Addressable Audience] et [!UICONTROL Destination] renvoient un nombre d’utilisateurs uniques pour l’intervalle de temps sélectionné. Par exemple, un visiteur n’est comptabilisé qu’une seule fois, même s’il vient plusieurs fois sur votre site. La première visite est la visite unique et est enregistrée. Les visites suivantes reviennent sur le site et ne sont pas comptabilisées car elles ne sont pas uniques.

Les plages de dates contiennent des données pour l’intervalle de temps sélectionné ou plus ancien. De plus, les données vieillissent au fil de chaque intervalle de rapport au fil du temps. Supposons, par exemple, que vous voyiez 2 visiteurs après avoir choisi l&#39;option [!UICONTROL Last 30 Days]. Dans les rapports, ces visiteurs :

* *Sera* inclus dans les résultats renvoyés par les intervalles de temps plus longs (60 jours, 90 jours et Durée de vie).
* *Ne sera pas* inclus dans les intervalles plus courts qui précèdent l’ [!UICONTROL Last 30 Day] option (Actuel, 7 jours et 14 jours).

Et, au 31° jour, ces visiteurs n&#39;apparaissent que dans les résultats de 60, 90 et [!UICONTROL Lifetime] jours. Ils ont vieilli sur l&#39;intervalle de 30 jours. Les visiteurs ne vieillissent pas dans l’intervalle [!UICONTROL Lifetime].

## [!UICONTROL Addressable Audiences] Mesures {#addressable-audience-metrics}

Cette section décrit les types de mesures fournis par [!UICONTROL Addressable Audiences].

### Mesures au niveau du client {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Ces mesures renvoient des données pour les caractéristiques réalisées lorsque des visiteurs se rendent sur votre site ou lorsque vous envoyez des fichiers de données entrants à [!DNL Audience Manager]. Ces mesures fournissent une vue complète de la taille de l’audience pour votre compte.

| Mesure | Description |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Nombre de chevauchements de périphériques qui ont réalisé un [!UICONTROL rule-based trait] ou un [!UICONTROL onboarded trait] au cours de la fenêtre de retour arrière et de périphériques pour lesquels nous avons synchronisé un identifiant avec la destination choisie, quelle que soit l&#39;heure de la synchronisation.<br><br>Cette mesure représente les périphériques qui :<ul><li>Ont réalisé un [!UICONTROL rule-based] ou un [!UICONTROL onboarded trait] au cours de la fenêtre de retour en arrière `AND`</li><li>Ayez un ID synchronisé avec le [!UICONTROL destination] sélectionné, quelle que soit l&#39;heure de la synchronisation.</li></ul> |
| [!UICONTROL Customer Total Audience] | Nombre de périphériques qui ont réalisé un [!UICONTROL rule-based trait] sur vos propriétés ou un [!UICONTROL onboarded trait] à partir de vos fichiers hors ligne pendant la fenêtre de recherche. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] :  [!UICONTROL Customer Total Audience] exprimé en pourcentage. |

### Mesures de correspondance au niveau du segment {#segment-level-metrics}

Ces mesures renvoient des données sur l&#39;adhésion [!UICONTROL segment]. Ils vous aident à obtenir une vue plus précise et plus précise de la taille de l&#39;audience pour chacun de vos [!UICONTROL segments].

>[!NOTE]
>
>La façon dont la fenêtre de retour en arrière est appliquée au niveau [!UICONTROL segment] est différente de celle appliquée au niveau du client. Les visiteurs peuvent venir sur le site et réaliser un [!UICONTROL trait] il y a 10 jours, et ils pourraient être admissibles à un [!UICONTROL segment] depuis lors et ont abandonné le [!UICONTROL segment] il y a 2 jours. Lorsque la recherche en amont de 7 jours est appliquée, ces visiteurs sont comptabilisés au niveau [!UICONTROL segment] mais pas au niveau client.

| Mesure | Description |
|---|---|
| [!UICONTROL Segment Addressable Audience] | Nombre d’utilisateurs qui ont appartenu à [!UICONTROL segment] au cours de la période de recherche en arrière du rapport et qui ont une synchronisation principale de l’identifiant sur votre site. Les segments peuvent inclure vos propres données propriétaires et les données propriétaires et tierces, par l&#39;intermédiaire de [!UICONTROL traits] acquis dans l&#39;[Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Conseil : Lorsqu’elle est utilisée avec la période de recherche en amont d’un jour, cette mesure peut vous aider à comprendre l’état actuel de votre  [!UICONTROL segments]application. En effet, la mesure [!UICONTROL Segment Addressable Audience] représente les utilisateurs qui sont restés dans une [!UICONTROL segment] au cours de la journée précédente. Combinez cela au fait que [!DNL Audience Manager] actualise [!UICONTROL Addressable Audiences] quotidiennement, en combinant cette mesure et cette période de recherche, vous obtenez l’instantané le plus récent de votre [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Nombre de tous les périphériques qui ont été membres de votre [!UICONTROL segment] pendant la période de consultation du rapport. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] :  [!UICONTROL Total Segment Population] exprimé en pourcentage. |

### Mesures au niveau de la plate-forme {#platform-level-metrics}

Cette mesure renvoie des données sur les activités collectées pour tous les [!DNL Audience Manager] clients. Ils peuvent fournir une vue plus large de l&#39;audience du client par rapport aux [!DNL Audience Manager] clients agrégés.

| Mesure | Description |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Nombre de tous les périphériques qui ont interagi avec tous les clients [!DNL Audience Manager] au niveau de la plate-forme au cours de la période de recherche en amont du rapport et qui peuvent correspondre à votre [!UICONTROL destination] choix. <br><br>Cette mesure est utile car elle vous montre :<ul><li>Taille de [!UICONTROL total addressable audience] que [!DNL Audience Manager] peut atteindre sur une destination de ciblage particulière.</li><li>Taille du pool de profils [!DNL Audience Manager] pour une plateforme de ciblage et taille de leurs audiences.</li></ul> |

## Comparaison de [!UICONTROL Customer] et [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

Vous ne devez pas comparer les mesures [!UICONTROL Customer Addressable Audience] et [!UICONTROL Segment Addressable Audience] pour déterminer si l’une est plus significative que l’autre. Il s’agit de mesures distinctes, différentes et indépendantes. Comme indiqué dans les définitions ci-dessus, chacune de ces variables est dérivée de différents ensembles de données. Dans ce contexte, évitez de tirer des conclusions si une mesure est supérieure à l’autre. Tout ce que vous pouvez dire en comparant ces éléments est :

* [!UICONTROL Customer Addressable Audiences] est basée sur  [!UICONTROL trait] des réalisations  *pour vos propres données* propriétaires. Cette mesure fournit une vue large et complète de votre intégration à un partenaire de données.

* [!UICONTROL Segment Addressable Audiences] repose sur les qualifications des segments  *pour vos propres données propriétaires, ainsi que sur les données* tierces et secondaires. Cette mesure fournit une vue granulaire et plus précise de [!UICONTROL addressable audiences] dans une plateforme de ciblage.

## Causes des taux de faible correspondance pour [!UICONTROL Addressable Audiences] {#low-match-rates}

Éléments communs responsables de faibles taux de correspondance [!UICONTROL Addressable Audience] ou d&#39;écarts dans les nombres signalés.

| Cause | Description |
|---|---|
| Trafic mobile | La plupart des intégrations [!UICONTROL server-to-server] reposent sur des processus de synchronisation facilités par des tiers [!DNL cookies]. Cependant, les environnements mobiles n’utilisent pas [!DNL cookies] tiers. Par conséquent, vos nombres [!UICONTROL Addressable Audiences] peuvent sembler faibles par rapport à la taille [!UICONTROL segment]. <br><br>Depuis janvier 2018, vous pouvez activer les audiences mobiles dans les mêmes  [!DNL Google] et  [!DNL Adobe Advertising Cloud] destinations configurées pour les  [!UICONTROL cookie-based] audiences. Bien que cela signifie que vous pouvez envoyer [!UICONTROL segments] avec un abonnement combiné [!DNL cookie] et un ID mobile à vos destinations [!DNL Google] et [!DNL Advertising Cloud], gardez à l’esprit que [!UICONTROL Addressable Audiences] n’affiche que le chevauchement entre les identifiants [!DNL cookie] et les destinations. [!DNL Audience Manager] envoie 100 % des audiences mobiles à  [!UICONTROL destinations], mais les audiences mobiles ne sont pas mesurées par la  [!UICONTROL Addressable Audience] mesure. <br><br>**Remarque** : Par exemple, prenez une population  [!UICONTROL segment] de 1 000 000 personnes. Si vous mappez cette [!UICONTROL segment] à une destination [!DNL Google] ou [!DNL Adobe Advertising Cloud], vous pouvez voir un [!UICONTROL Addressable Audience] de 700 000 périphériques et un [!UICONTROL Match Rate] de 70 %. Les 700 000 membres sont composés d&#39;ID [!DNL cookie] dont l&#39;ID est synchronisé avec [!UICONTROL destination]. Votre [!UICONTROL Addressable Audience] peut, en fait, être beaucoup plus élevé, car les identifiants mobiles adressables n’apparaissent pas dans cette mesure. |
| [!DNL Safari] Trafic | [!DNL Safari] bloque des tiers  [!DNL cookies]. Cela empêche [!DNL Audience Manager] de synchroniser les ID avec [!UICONTROL destination]. Avec l&#39;introduction de [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), vous pouvez vous attendre à ce que [!UICONTROL addressable audiences] n&#39;inclut pas les utilisateurs [!DNL Safari]. |
| Impressions de médias suivies | En raison des bonnes pratiques du serveur d’annonces, les synchronisations d’ID ne sont pas effectuées dans les balises d’annonce. Les clients qui effectuent une grande quantité de publicité hors site ne synchronisent pas les utilisateurs avec les intégrations tierces dans ces environnements. En outre, une grande quantité de données d&#39;impression des médias collectées pourrait réduire les [!UICONTROL addressable audience] nombres. |

## Dépannage avec [!UICONTROL Addressable Audiences] {#troubleshooting}

Outre les taux de correspondance de surface, vous pouvez également utiliser [!UICONTROL Addressable Audiences] comme outil de dépannage.

Supposons, par exemple, que vous envoyiez un segment à [!UICONTROL destination] et que [!UICONTROL destination] affiche des valeurs de rapports faibles. Si vous vérifiez les résultats [!UICONTROL Addressable Audience], vous verrez s&#39;il s&#39;agit d&#39;un problème technique ou simplement d&#39;un cas de faible taux de correspondance. Un faible taux de correspondance indique que votre [!UICONTROL destination] n&#39;est pas très performant pour les segments sélectionnés. Cependant, une différence dans les nombres [!UICONTROL total addressable audience] entre [!DNL Audience Manager] et [!UICONTROL destination] indique un problème d&#39;intégration, de synchronisation ou autre problème technique. Dans ce cas, contactez votre gestionnaire de compte.
