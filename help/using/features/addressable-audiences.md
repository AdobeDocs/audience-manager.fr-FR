---
description: Présentation de la fonction Audience adressable et des cas pratiques.
keywords: DIL
seo-description: An overview of the Addressable Audience feature and use cases.
seo-title: Addressable Audiences
solution: Audience Manager
title: Audiences adressables
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
source-git-commit: cecdc0b0f43a146e11f7d23eb21a06146496ac2d
workflow-type: tm+mt
source-wordcount: '1813'
ht-degree: 1%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Une vue d’ensemble de [!UICONTROL Addressable Audience] et cas d’utilisation.

## Qu’est-ce qu’une [!UICONTROL Addressable Audience]? {#addressable-audience-description}

Le [!UICONTROL Addressable Audiences] Cette fonctionnalité vous montre le chevauchement entre les audiences que vous voyez dans toutes vos propriétés où [!DNL Audience Manager] collecte des données et la destination sélectionnée. Pour vous aider à comprendre ce concept, consultez l’illustration ci-dessous. Le chevauchement entre chaque cercle représente les différents types d’audiences adressables.

![](assets/addressableAudienceVenn.png)


| Mesure | Description |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] pour un [!UICONTROL Destination] | Comptage de tous les appareils qui ont interagi avec tous les [!DNL Audience Manager] clients au niveau de la plateforme pendant la période de recherche en amont des rapports et qui peuvent être associés à votre choix ; [!UICONTROL destination]. <br><br>Cette mesure s’avère utile, car elle vous présente les éléments suivants : <ul><li>Taille du total [!UICONTROL addressable audience] that [!DNL Audience Manager] peut atteindre un ciblage particulier ; [!UICONTROL destination].</li><li>Quelle taille a la variable [!DNL Audience Manager] le pool de profils est destiné à une plateforme de ciblage et à la taille de leurs audiences.</li></ul> |
| [!UICONTROL Customer Total Audience] | Nombre de périphériques qui ont généré une [!UICONTROL rule-based trait] sur vos propriétés ou une [!UICONTROL onboarded trait] de vos fichiers hors ligne pendant la fenêtre rétroactive. |
| [!UICONTROL Customer Addressable Audience] | Nombre de chevauchements des appareils qui ont généré une [!UICONTROL rule-based trait] ou [!UICONTROL onboarded trait] pendant la fenêtre rétroactive et les appareils que nous avons synchronisés avec les identifiants avec le [!UICONTROL destination] quelle que soit l’heure des synchronisations.<br><br>Cette mesure représente les appareils qui :<ul><li>ont réalisé soit une [!UICONTROL rule-based] ou [!UICONTROL onboarded trait] pendant la fenêtre rétroactive `AND`</li><li>Synchroniser l’identifiant avec le choix [!UICONTROL destination] quelle que soit l’heure des synchronisations.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] exprimé en pourcentage. |
| [!UICONTROL Total Segment Population] | Comptage de tous les appareils qui étaient membres de votre [!UICONTROL segment] pendant la période d’analyse du rapport. |
| [!UICONTROL Segment Addressable Audience] | Nombre d’utilisateurs qui ont appartenu au [!UICONTROL segment] pendant la période d’analyse du rapport et synchronisez les identifiants principal sur votre site. [!UICONTROL Segments] peut inclure vos propres données propriétaires et des données de deuxième et de troisième niveau, via [!UICONTROL traits] acquis dans la variable [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Conseil : Utilisée avec la période de recherche en amont d’un jour, cette mesure peut vous aider à comprendre l’état actuel de votre [!UICONTROL segments]. En effet, la variable [!UICONTROL Segment Addressable Audience] représente les utilisateurs qui sont restés dans une [!UICONTROL segment] tout au long de la journée précédente. Combinez cela au fait que : [!DNL Audience Manager] actualise [!UICONTROL Addressable Audiences] quotidien, la combinaison de cette mesure et de la période de recherche permet d’obtenir l’instantané le plus récent de votre [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] exprimé en pourcentage. |

## [!UICONTROL Addressable Audiences] Interface {#addressable-audience-interface}

Le [!UICONTROL Addressable Audience] transforme ce concept abstrait en données quantifiables. Dans [!DNL Audience Manager], cette fonctionnalité affiche le chevauchement des audiences avec des visualisations de données qui fournissent des informations en un coup d’oeil, ainsi que des données numériques sous forme tabulaire.

[!UICONTROL Addressable Audiences] se trouve dans **[!UICONTROL Audience Data > Destinations]**. Sélectionner **[!UICONTROL Integrated Platforms > Device-Based]** pour afficher les mesures d’audiences adressables.

![](assets/addressable-audiences-landing.png)

Les trois mesures que vous pouvez voir sur la variable [!UICONTROL Addressable Audiences] représente la page d’entrée :

| Mesure | Description |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Cette mesure représente la variable [!UICONTROL Customer Addressable Audience] (décrit dans le tableau ci-dessus) *pour les 30 derniers jours.* |
| **[!UICONTROL Match Rate]** | Cette mesure représente la variable [!UICONTROL Addressable Audience Match Rate] (décrit dans le tableau ci-dessus) *pour les 30 derniers jours*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Comptage de tous les appareils qui ont interagi avec tous les [!DNL Audience Manager] clients au niveau de la plateforme pendant la période de recherche en amont des rapports et qui peuvent être associés à cette [!UICONTROL destination]. Voir [Mesures au niveau de la plateforme](/help/using/features/addressable-audiences.md#platform-level-metrics) pour plus d’informations. |

Cliquez sur le nom d’un [!UICONTROL server-to-server destination] pour afficher vos données d’audience adressables. Remarque : cette fonctionnalité renvoie des données pour [!UICONTROL server-to-server destinations] uniquement et l’accès nécessite des autorisations d’administrateur.

![](assets/addressableAudiences.png)

La vérification de ces données peut vous aider à :

* **Prévisions et planification :** [!UICONTROL Segment Addressable Audience] Les données vous donnent plus de granularité dans les segments que vous prévoyez d’envoyer vers une destination pour le ciblage et l’activation des audiences.

* **Études de performances :** Le [!UICONTROL Addressable Audiences] est également un outil de dépannage. Il vous permet de passer en revue les performances de la campagne, de comprendre la portée de la campagne et de vérifier avec les partenaires de ciblage/d’activation si vous ne voyez pas les résultats attendus.

### Planification avec des données tierces et implications pour les taux de correspondance

Avant d’acheter des données tierces pour l’acquisition d’audiences, les clients peuvent valider le chevauchement avec d’autres fournisseurs de données. Cela peut vous aider à prendre une décision éclairée avant d’acheter de nouvelles données. Les synchronisations des identifiants pour les données tierces achetées reposent non seulement sur le chevauchement de vos données, mais également sur l’empreinte des fournisseurs tiers sur toutes les autres données. [!DNL Audience Manager] clients. Votre [!DNL Adobe] Il peut vous aider à identifier d’autres sources de données pertinentes afin d’optimiser les campagnes de prospection.

### Utilisateurs mobiles et taux de correspondance

Il y a des lacunes lors de la tentative de connexion. [!DNL Safari] ou les utilisateurs d’applications mobiles sans tiers ; [!DNL cookies] présente. Cela rend difficile la synchronisation des utilisateurs avec certains partenaires, car seuls ceux-ci [!DNL Adobe] ID pour les tiers synchronisés [!DNL cookies] sont fournis dans les logs de diffusion du média. C’est la raison pour laquelle vous pouvez voir [faibles taux de correspondance](../features/addressable-audiences.md#low-match-rates) pour votre [!UICONTROL destinations].

## Périodes dans [!UICONTROL Addressable Audiences] et [!UICONTROL Destinations] {#date-ranges}

Lisez les sections ci-dessous pour connaître les plages de dates disponibles et la façon dont les données sortent de chaque intervalle dans les rapports pour une [!UICONTROL Addressable Audience] ou [!UICONTROL Destination].

## Périodes disponibles et fuseaux horaires {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Rapports pour votre [!UICONTROL Addressable Audiences] et [Destinations](../features/destinations/destinations.md) utilisent les mêmes intervalles de période. Les options de période incluent :

* [!UICONTROL Last 1 Day] (Cet intervalle s’étend de minuit à minuit de la période de 24 heures précédente. Il ne s’agit pas d’une mesure en temps réel ou en temps réel.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Toutes les dates et plages de dates sont définies dans la variable [!DNL UTC] fuseau horaire. Voir [Fuseaux horaires en Audience Manager](../reference/aam-time-zones.md).

## Données aux intervalles de période {#date-range-intervals}

Le [!UICONTROL Addressable Audience] et [!UICONTROL Destination] les mesures renvoient un nombre d’utilisateurs uniques pour l’intervalle de temps sélectionné. Par exemple, un visiteur n’est comptabilisé qu’une seule fois, même s’il se rend plusieurs fois sur votre site. La première visite est la visite unique et est enregistrée. Les visites suivantes renvoient des visites et ne sont pas comptabilisées car elles ne sont pas uniques.

Les plages de dates contiennent des données pour l’intervalle de temps sélectionné ou plus ancien. De plus, les données vieillissent à chaque intervalle de rapport au fil du temps. Supposons, par exemple, que vous voyiez 2 visiteurs après avoir choisi la variable [!UICONTROL Last 30 Days] . Dans les rapports, ces visiteurs :

* *Will* inclus dans les résultats renvoyés par les intervalles de temps plus longs (60 jours, 90 jours et Durée de vie).
* *Ne sera pas* inclus dans les intervalles plus courts qui précèdent la variable [!UICONTROL Last 30 Day] (Actuel, 7 jours et 14 jours).

Et, au 31° jour, ces visiteurs n’apparaissent que dans les 60, 90 et [!UICONTROL Lifetime] résultats. Ils ont vieilli sur l’intervalle de 30 jours. Les visiteurs ne sont pas lassés du [!UICONTROL Lifetime] intervalle.

## [!UICONTROL Addressable Audiences] Mesures {#addressable-audience-metrics}

Cette section décrit les types de mesures fournis par [!UICONTROL Addressable Audiences].

### Mesures au niveau du client {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Ces mesures renvoient des données pour les caractéristiques réalisées lorsque des visiteurs se rendent sur votre site ou lorsque vous envoyez des fichiers de données entrants à [!DNL Audience Manager]. Ces mesures fournissent une vue complète de la taille de l’audience de votre compte.

| Mesure | Description |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Nombre de chevauchements des appareils qui ont généré une [!UICONTROL rule-based trait] ou [!UICONTROL onboarded trait] pendant la fenêtre rétroactive et les appareils pour lesquels nous avons une synchronisation des identifiants avec la destination choisie, quelle que soit l’heure de la synchronisation.<br><br>Cette mesure représente les appareils qui :<ul><li>ont réalisé soit une [!UICONTROL rule-based] ou [!UICONTROL onboarded trait] pendant la fenêtre rétroactive `AND`</li><li>Synchroniser l’identifiant avec le choix [!UICONTROL destination] quelle que soit l’heure des synchronisations.</li></ul> |
| [!UICONTROL Customer Total Audience] | Nombre de périphériques qui ont généré une [!UICONTROL rule-based trait] sur vos propriétés ou une [!UICONTROL onboarded trait] de vos fichiers hors ligne pendant la fenêtre rétroactive. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] exprimé en pourcentage. |

### Mesures de correspondance au niveau du segment {#segment-level-metrics}

Ces mesures renvoient des données sur [!UICONTROL segment] abonnement. Elles vous aident à obtenir une vue plus précise et plus granulaire de la taille de l’audience pour chacune de vos [!UICONTROL segments].

>[!NOTE]
>
>La manière dont la fenêtre rétroactive est appliquée au [!UICONTROL segment] est différent de celui du niveau client. Les visiteurs peuvent se rendre sur le site et réaliser une [!UICONTROL trait] Il y a 10 jours, et ils pouvaient avoir droit à un [!UICONTROL segment] depuis lors, et ont abandonné l’ [!UICONTROL segment] Il y a 2 jours. Lorsque la recherche en amont de 7 jours est appliquée, ces visiteurs sont comptabilisés au [!UICONTROL segment] mais pas au niveau du client.

| Mesure | Description |
|---|---|
| [!UICONTROL Segment Addressable Audience] | Nombre d’utilisateurs qui ont appartenu au [!UICONTROL segment] pendant la période d’analyse du rapport et synchronisez les identifiants principal sur votre site. Les segments peuvent inclure vos propres données propriétaires, ainsi que des données de deuxième et de troisième niveau, via [!UICONTROL traits] acquis dans la variable [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Conseil : Utilisée avec la période de recherche en amont d’un jour, cette mesure peut vous aider à comprendre l’état actuel de votre [!UICONTROL segments]. En effet, la variable [!UICONTROL Segment Addressable Audience] représente les utilisateurs qui sont restés dans une [!UICONTROL segment] tout au long de la journée précédente. Combinez cela au fait que : [!DNL Audience Manager] actualise [!UICONTROL Addressable Audiences] quotidien, la combinaison de cette mesure et de la période de recherche permet d’obtenir l’instantané le plus récent de votre [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Comptage de tous les appareils qui étaient membres de votre [!UICONTROL segment] pendant la période d’analyse du rapport. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] exprimé en pourcentage. |

### Mesures au niveau de la plateforme {#platform-level-metrics}

Cette mesure renvoie les données sur les activités collectées dans toutes les [!DNL Audience Manager] clients. Elles peuvent fournir une vue plus large de l’audience du client par rapport aux données agrégées. [!DNL Audience Manager] clients.

| Mesure | Description |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Comptage de tous les appareils qui ont interagi avec tous les [!DNL Audience Manager] clients au niveau de la plateforme pendant la période de recherche en amont des rapports et qui peuvent être associés à votre choix ; [!UICONTROL destination]. <br><br>Cette mesure s’avère utile, car elle vous présente les éléments suivants :<ul><li>La taille de la variable [!UICONTROL total addressable audience] that [!DNL Audience Manager] peut atteindre une destination de ciblage particulière.</li><li>Quelle taille a la variable [!DNL Audience Manager] le pool de profils est destiné à une plateforme de ciblage et à la taille de leurs audiences.</li></ul> |

## Comparaison [!UICONTROL Customer] et [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

Vous ne devriez pas comparer la variable [!UICONTROL Customer Addressable Audience] et [!UICONTROL Segment Addressable Audience] pour déterminer si l’une est plus significative que l’autre. Il s’agit de mesures distinctes, différentes et indépendantes. Comme décrit dans les définitions ci-dessus, chacune de ces variables est dérivée de différents jeux de données. Dans ce contexte, vous devez éviter de déduire des conclusions si une mesure est supérieure à l’autre. Tout ce que vous pouvez dire en comparant ces éléments est :

* [!UICONTROL Customer Addressable Audiences] est basé sur [!UICONTROL trait] réalisations *pour vos propres données propriétaires*. Cette mesure offre une vue large et complète de votre intégration à un partenaire de données.

* [!UICONTROL Segment Addressable Audiences] est basé sur les qualifications de segments ; *pour vos propres données propriétaires, ainsi que des données de deuxième et de troisième niveau*. Cette mesure offre une vue granulaire et plus précise de votre [!UICONTROL addressable audiences] dans une plateforme de ciblage.

## Causes des faibles taux de correspondance pour [!UICONTROL Addressable Audiences] {#low-match-rates}

Éléments communs responsables de faibles [!UICONTROL Addressable Audience] taux de correspondance ou incohérences entre les nombres signalés.

| Cause | Description |
|---|---|
| Trafic mobile | Le plus [!UICONTROL server-to-server] les intégrations reposent sur des processus de synchronisation facilités par des tiers. [!DNL cookies]. Toutefois, les environnements mobiles n’utilisent pas de tiers [!DNL cookies]. Par conséquent, votre [!UICONTROL Addressable Audiences] les nombres peuvent sembler faibles par rapport aux [!UICONTROL segment] taille. <br><br>Depuis janvier 2018, vous pouvez activer les audiences mobiles dans la même [!DNL Google] et [!DNL Adobe Advertising Cloud] destinations configurées pour [!UICONTROL cookie-based] audiences. Cela signifie que vous pouvez envoyer [!UICONTROL segments] combiné [!DNL cookie] et l’appartenance à votre identifiant mobile [!DNL Google] et [!DNL Advertising Cloud] destinations, gardez à l’esprit que : [!UICONTROL Addressable Audiences] afficher uniquement le chevauchement entre [!DNL cookie] ID et destinations. [!DNL Audience Manager] envoie 100 % des audiences mobiles à [!UICONTROL destinations], mais les audiences mobiles ne sont pas mesurées par la variable [!UICONTROL Addressable Audience] mesure. <br><br>**Remarque**: Par exemple, prenez une [!UICONTROL segment] avec une population de 1.000.000. Si vous mappez ceci [!UICONTROL segment] à [!DNL Google] ou [!DNL Adobe Advertising Cloud] destination, une [!UICONTROL Addressable Audience] de 700 000 appareils et une [!UICONTROL Match Rate] de 70 %. Les 700 000 membres se composent de [!DNL cookie] ID synchronisés avec le [!UICONTROL destination]. Votre [!UICONTROL Addressable Audience] peut, en fait, être beaucoup plus élevé, car les identifiants mobiles adressables n’apparaissent pas dans cette mesure. |
| [!DNL Safari] Trafic | [!DNL Safari] bloque tiers [!DNL cookies]. Cela empêche [!DNL Audience Manager] lors de la synchronisation des identifiants avec le [!UICONTROL destination]. Avec l’introduction de [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), vous pouvez vous attendre à ce que [!UICONTROL addressable audiences] ne pas inclure [!DNL Safari] utilisateurs. |
| Impressions de médias suivies | En raison des bonnes pratiques relatives au serveur d’annonces, les synchronisations des identifiants ne sont pas effectuées dans les balises d’annonce. Les clients qui effectuent une grande quantité de publicité hors site ne synchronisent pas les utilisateurs avec les intégrations tierces dans ces environnements. En outre, une grande quantité de données d’impression multimédia collectées pourrait réduire les [!UICONTROL addressable audience] nombres. |

## Dépannage avec [!UICONTROL Addressable Audiences] {#troubleshooting}

Outre les taux de correspondance affichés, vous pouvez également utiliser [!UICONTROL Addressable Audiences] comme outil de dépannage.

Par exemple, supposons que vous envoyiez un segment à un [!UICONTROL destination] et que [!UICONTROL destination] affiche de faibles nombres de rapports. Vérifiez les [!UICONTROL Addressable Audience] les résultats vous indiquent s’il s’agit d’un problème technique ou simplement d’un cas de faibles taux de correspondance. Un taux de correspondance faible affiche votre [!UICONTROL destination] n’est pas si génial pour vos segments sélectionnés. Cependant, une différence dans la variable [!UICONTROL total addressable audience] nombres entre [!DNL Audience Manager] et le [!UICONTROL destination] indique un problème d’intégration, de synchronisation ou tout autre problème technique. Dans ce cas, contactez votre gestionnaire de compte.
