---
description: Présentation de la fonctionnalité Audience adressable et des cas d’utilisation.
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
source-wordcount: '1831'
ht-degree: 0%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Présentation de la fonctionnalité [!UICONTROL Addressable Audience] et des cas d’utilisation.

## Qu&#39;est-ce qu&#39;un [!UICONTROL Addressable Audience] ? {#addressable-audience-description}

La fonction [!UICONTROL Addressable Audiences] vous montre le chevauchement entre les audiences que vous voyez dans toutes vos propriétés où [!DNL Audience Manager] collecte des données et la destination sélectionnée. Pour mieux comprendre ce concept, jetez un coup d’œil à l’illustration ci-dessous. Le chevauchement entre chaque cercle représente les différents types d’audiences adressables.

![](assets/addressableAudienceVenn.png)


| Mesure | Description |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] pour un [!UICONTROL Destination] | Nombre de tous les appareils qui ont interagi avec tous les clients [!DNL Audience Manager] au niveau de la plateforme pendant la période de recherche en amont du rapport et qui peuvent être associés au [!UICONTROL destination] choisi. <br><br>Cette mesure est utile, car elle vous indique : <ul><li>Taille du [!UICONTROL addressable audience] total que [!DNL Audience Manager] pouvez atteindre sur un [!UICONTROL destination] de ciblage particulier.</li><li>La taille du pool de profils [!DNL Audience Manager] pour une plateforme de ciblage et la taille de leurs audiences.</li></ul> |
| [!UICONTROL Customer Total Audience] | Nombre d’appareils qui ont réalisé un [!UICONTROL rule-based trait] sur vos propriétés ou un [!UICONTROL onboarded trait] de vos fichiers hors ligne pendant l’intervalle de recherche en amont. |
| [!UICONTROL Customer Addressable Audience] | Nombre de chevauchements d’appareils qui ont réalisé une [!UICONTROL rule-based trait] ou une [!UICONTROL onboarded trait] pendant l’intervalle de recherche en amont et d’appareils pour lesquels nous avons une synchronisation des identifiants avec le [!UICONTROL destination] choisi, quelle que soit l’heure des synchronisations.<br><br>Cette mesure représente les appareils qui :<ul><li>Ont réalisé une [!UICONTROL rule-based] ou une [!UICONTROL onboarded trait] pendant l’`AND` de l’intervalle de recherche en amont</li><li>disposer d’une synchronisation des identifiants avec le [!UICONTROL destination] choisi, quelle que soit l’heure des synchronisations ;</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] exprimé en pourcentage. |
| [!UICONTROL Total Segment Population] | Nombre de tous les appareils qui étaient membres de votre [!UICONTROL segment] pendant la période de recherche en amont du rapport. |
| [!UICONTROL Segment Addressable Audience] | Nombre d’utilisateurs et d’utilisatrices qui ont appartenu au [!UICONTROL segment] pendant la période de recherche en amont du rapport et qui ont une synchronisation des identifiants active sur votre site. [!UICONTROL Segments] pouvez inclure vos propres données propriétaires et vos propres données secondaires et tierces, par le biais de [!UICONTROL traits] acquises dans [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Conseil : lorsqu’elle est utilisée avec la période de recherche arrière d’un jour, cette mesure peut vous aider à comprendre l’état actuel de votre [!UICONTROL segments]. En effet, la mesure [!UICONTROL Segment Addressable Audience] représente les utilisateurs qui sont restés dans un [!UICONTROL segment] tout au long de la journée précédente. Ajoutez à cela le fait que [!DNL Audience Manager] actualise [!UICONTROL Addressable Audiences] tous les jours. La combinaison de cette mesure et de cette période de recherche en amont fournit l’instantané le plus à jour de votre [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] exprimé en pourcentage. |

## Interface [!UICONTROL Addressable Audiences] {#addressable-audience-interface}

La fonction [!UICONTROL Addressable Audience] transforme ce concept abstrait en données quantifiables. En [!DNL Audience Manager], cette fonctionnalité affiche le chevauchement des audiences avec des visualisations de données qui fournissent des informations en un coup d’œil ainsi que des données numériques sous forme tabulaire.

[!UICONTROL Addressable Audiences] se trouve dans **[!UICONTROL Audience Data > Destinations]**. Sélectionnez **[!UICONTROL Integrated Platforms > Device-Based]** pour afficher les mesures d’audiences adressables.

![](assets/addressable-audiences-landing.png)

Les trois mesures affichées sur la page de destination [!UICONTROL Addressable Audiences] représentent :

| Mesure | Description |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Cette mesure représente la [!UICONTROL Customer Addressable Audience] (décrite dans le tableau ci-dessus) *pour les 30 derniers jours*. |
| **[!UICONTROL Match Rate]** | Cette mesure représente la [!UICONTROL Addressable Audience Match Rate] (décrite dans le tableau ci-dessus) *pour les 30 derniers jours*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Nombre de tous les appareils qui ont interagi avec tous les clients [!DNL Audience Manager] au niveau de la plateforme pendant la période de recherche en amont du rapport et qui peuvent être associés à cette [!UICONTROL destination]. Voir [Mesures au niveau de la plateforme](/help/using/features/addressable-audiences.md#platform-level-metrics) pour plus d’informations. |

Cliquez sur le nom d’un [!UICONTROL server-to-server destination] pour afficher les données de votre audience adressable. Notez que cette fonctionnalité renvoie des données pour [!UICONTROL server-to-server destinations] uniquement et que l’accès nécessite des autorisations d’administrateur.

![](assets/addressableAudiences.png)

L’examen de ces données peut vous aider à :

* **Prévision et planification :** les données [!UICONTROL Segment Addressable Audience] vous donnent plus de granularité dans les segments que vous prévoyez d’envoyer à une destination pour le ciblage et l’activation des audiences.

* **Examens des performances :** la fonctionnalité [!UICONTROL Addressable Audiences] est également un outil de dépannage. Il vous permet de passer en revue les performances de la campagne, de comprendre la portée de la campagne et de vérifier auprès des partenaires de ciblage/activation si les résultats attendus ne s’affichent pas.

### Prospection à l’aide de données tierces et implications pour les taux de correspondance

Avant d’acheter des données tierces pour l’acquisition d’audiences, les clients peuvent valider le chevauchement avec d’autres fournisseurs de données. Cela peut vous aider à prendre une décision éclairée avant d’acheter de nouvelles données. Les synchronisations des identifiants pour les données tierces achetées reposent non seulement sur le chevauchement de vos données, mais également sur les empreintes des fournisseurs tiers avec tous les autres clients [!DNL Audience Manager]. Votre consultant [!DNL Adobe] peut vous aider à identifier d’autres sources de données pertinentes afin d’optimiser les campagnes de prospection.

### Utilisateurs mobiles et taux de correspondance

Il existe des lacunes lors de la tentative de connexion des utilisateurs d’applications [!DNL Safari] ou mobiles lorsqu’aucun [!DNL cookies] tiers n’est présent. Cela rend difficile la synchronisation des utilisateurs avec certains partenaires, car seuls les identifiants [!DNL Adobe] pour les [!DNL cookies] tiers synchronisés sont fournis dans les logs de diffusion multimédia. C’est une raison pour laquelle les [taux de correspondance faibles](../features/addressable-audiences.md#low-match-rates) s’affichent pour votre [!UICONTROL destinations].

## Périodes dans [!UICONTROL Addressable Audiences] et [!UICONTROL Destinations] {#date-ranges}

Lisez les sections ci-dessous pour connaître les périodes disponibles et la manière dont les données vieillissent sur chaque intervalle dans les rapports pour une [!UICONTROL Addressable Audience] ou une [!UICONTROL Destination].

## Périodes et fuseaux horaires disponibles {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Les rapports pour vos [!UICONTROL Addressable Audiences] et [Destinations](../features/destinations/destinations.md) utilisent les mêmes intervalles de période. Les options de période incluent :

* [!UICONTROL Last 1 Day] (cet intervalle s’étend de minuit à minuit de la période de 24 heures précédente. Il ne s’agit pas d’une mesure en temps réel ou en temps actuel.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Toutes les dates et périodes sont définies dans le fuseau horaire [!DNL UTC]. Voir [Fuseaux horaires dans Audience Manager](../reference/aam-time-zones.md).

## Données dans les intervalles de périodes {#date-range-intervals}

Les mesures [!UICONTROL Addressable Audience] et [!UICONTROL Destination] renvoient un nombre d’utilisateurs uniques pour l’intervalle de temps sélectionné. Par exemple, un visiteur n’est comptabilisé qu’une seule fois, même s’il se rend plusieurs fois sur votre site. La première visite est la visite unique et est enregistrée. Les visites suivantes sont des visites récurrentes et ne sont pas comptabilisées, car elles ne sont pas uniques.

Les périodes contiennent des données pour l’intervalle de temps sélectionné ou une période antérieure. De plus, les données vieillissent de chaque intervalle de rapport au fil du temps. Supposons, par exemple, que vous voyiez 2 visiteurs après avoir choisi l’option [!UICONTROL Last 30 Days] . Dans les rapports, ces visiteurs et visiteuses :

* *Sera* inclus dans les résultats renvoyés par les intervalles de temps plus longs (60 jours, 90 jours et durée de vie).
* *Ne sera pas* inclus dans les intervalles plus courts qui précèdent l’option [!UICONTROL Last 30 Day] (En cours, 7 jours et 14 jours).

De plus, au jour 31, ces visiteurs ne s’affichent que dans les résultats sur 60 jours, 90 jours et [!UICONTROL Lifetime]. Ils ont vieilli sur l&#39;intervalle de 30 jours. L’âge des visiteurs n’est pas en dehors de l’intervalle [!UICONTROL Lifetime].

## Mesures [!UICONTROL Addressable Audiences] {#addressable-audience-metrics}

Cette section décrit les types de mesures fournis par [!UICONTROL Addressable Audiences].

### Mesures au niveau du client {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Ces mesures renvoient des données pour les caractéristiques réalisées lorsque des visiteurs se rendent sur votre site ou lorsque vous envoyez des fichiers de données entrants à [!DNL Audience Manager]. Ces mesures fournissent une vue complète de la taille de l’audience de votre compte.

| Mesure | Description |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Nombre d’appareils qui se chevauchent et qui ont réalisé une [!UICONTROL rule-based trait] ou une [!UICONTROL onboarded trait] pendant l’intervalle de recherche en amont, et d’appareils pour lesquels nous avons une synchronisation des identifiants avec la destination choisie, quelle que soit l’heure des synchronisations.<br><br>Cette mesure représente les appareils qui :<ul><li>Ont réalisé une [!UICONTROL rule-based] ou une [!UICONTROL onboarded trait] pendant l’`AND` de l’intervalle de recherche en amont</li><li>disposer d’une synchronisation des identifiants avec le [!UICONTROL destination] choisi, quelle que soit l’heure des synchronisations ;</li></ul> |
| [!UICONTROL Customer Total Audience] | Nombre d’appareils qui ont réalisé un [!UICONTROL rule-based trait] sur vos propriétés ou un [!UICONTROL onboarded trait] de vos fichiers hors ligne pendant l’intervalle de recherche en amont. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] exprimé en pourcentage. |

### Mesures de correspondance au niveau du segment {#segment-level-metrics}

Ces mesures renvoient des données sur l’appartenance à un [!UICONTROL segment]. Ils permettent de fournir une vue plus granulaire et plus précise de la taille de l’audience pour chacun de vos [!UICONTROL segments].

>[!NOTE]
>
>La façon dont l’intervalle de recherche en amont est appliqué au niveau du [!UICONTROL segment] est différente de celle appliquée au niveau du client. Les visiteurs peuvent se rendre sur le site et réaliser un [!UICONTROL trait] il y a 10 jours, et ils pourraient se qualifier pour un [!UICONTROL segment] depuis et abandonner le [!UICONTROL segment] il y a 2 jours. Lorsque la recherche arrière de 7 jours est appliquée, ces visiteurs sont comptabilisés au niveau de la [!UICONTROL segment], mais pas au niveau du client.

| Mesure | Description |
|---|---|
| [!UICONTROL Segment Addressable Audience] | Nombre d’utilisateurs et d’utilisatrices qui ont appartenu au [!UICONTROL segment] pendant la période de recherche en amont du rapport et qui ont une synchronisation des identifiants active sur votre site. Les segments peuvent inclure vos propres données propriétaires et vos propres données tierces et secondaires, via des [!UICONTROL traits] acquises dans [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Conseil : lorsqu’elle est utilisée avec la période de recherche arrière d’un jour, cette mesure peut vous aider à comprendre l’état actuel de votre [!UICONTROL segments]. En effet, la mesure [!UICONTROL Segment Addressable Audience] représente les utilisateurs qui sont restés dans un [!UICONTROL segment] tout au long de la journée précédente. Ajoutez à cela le fait que [!DNL Audience Manager] actualise [!UICONTROL Addressable Audiences] tous les jours. La combinaison de cette mesure et de cette période de recherche en amont fournit l’instantané le plus à jour de votre [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Nombre de tous les appareils qui étaient membres de votre [!UICONTROL segment] pendant la période de recherche en amont du rapport. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] exprimé en pourcentage. |

### Mesures au niveau de la plateforme {#platform-level-metrics}

Cette mesure renvoie des données sur les activités collectées auprès de tous les clients [!DNL Audience Manager]. Ils peuvent fournir une vue plus large de l’audience du client par rapport aux clients [!DNL Audience Manager] agrégés.

| Mesure | Description |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Nombre de tous les appareils qui ont interagi avec tous les clients [!DNL Audience Manager] au niveau de la plateforme pendant la période de recherche en amont du rapport et qui peuvent être associés au [!UICONTROL destination] choisi. <br><br>Cette mesure est utile, car elle vous indique :<ul><li>Taille de la [!UICONTROL total addressable audience] que [!DNL Audience Manager] pouvez atteindre sur une destination de ciblage particulière.</li><li>La taille du pool de profils [!DNL Audience Manager] pour une plateforme de ciblage et la taille de leurs audiences.</li></ul> |

## Comparaison des [!UICONTROL Customer] et des [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

Vous ne devriez pas comparer les mesures [!UICONTROL Customer Addressable Audience] et [!UICONTROL Segment Addressable Audience] pour déterminer si l’une est plus importante que l’autre. Il s’agit de mesures distinctes, différentes et indépendantes. Comme décrit dans les définitions ci-dessus, chacun de ces éléments est dérivé de différents ensembles de données. Ainsi, vous devez éviter de tirer des conclusions si une mesure est plus grande que l’autre. Tout ce que vous pouvez dire en les comparant est que :

* [!UICONTROL Customer Addressable Audiences] est basé sur [!UICONTROL trait] réalisations *pour vos propres données propriétaires*. Cette mesure fournit une vue d’ensemble de votre intégration à un partenaire de données.

* [!UICONTROL Segment Addressable Audiences] est basé sur les qualifications de segment *pour vos propres données propriétaires, ainsi que vos données secondaires et tierces*. Cette mesure fournit une vue plus granulaire et plus précise de vos [!UICONTROL addressable audiences] dans une plateforme de ciblage.

## Causes des faibles taux de correspondance pour les [!UICONTROL Addressable Audiences] {#low-match-rates}

Éléments courants responsables de faibles taux de correspondance [!UICONTROL Addressable Audience] ou d’écarts dans les nombres signalés.

| Cause | Description |
|---|---|
| Trafic mobile | La plupart des intégrations [!UICONTROL server-to-server] reposent sur des processus de synchronisation facilités par des [!DNL cookies] tiers. Toutefois, les environnements mobiles n’utilisent pas de [!DNL cookies] tiers. Par conséquent, vos nombres de [!UICONTROL Addressable Audiences] peuvent sembler faibles par rapport à la taille de l’[!UICONTROL segment]. <br><br>Depuis janvier 2018, vous pouvez activer les audiences mobiles dans les mêmes [!DNL Google] et [!DNL Adobe Advertising Cloud] destinations configurées pour les audiences [!UICONTROL cookie-based]. Cela signifie que vous pouvez envoyer des [!UICONTROL segments] avec une combinaison d’appartenance aux [!DNL cookie] et aux identifiants mobiles vers vos destinations [!DNL Google] et [!DNL Advertising Cloud], mais gardez à l’esprit que les [!UICONTROL Addressable Audiences] n’affichent que le chevauchement entre les identifiants [!DNL cookie] et les destinations. [!DNL Audience Manager] envoie 100 % des audiences mobiles vers [!UICONTROL destinations], mais les audiences mobiles ne sont pas mesurées par la mesure [!UICONTROL Addressable Audience] . <br><br>**Remarque** : par exemple, prenez un [!UICONTROL segment] avec une population de 1 000 000. Si vous mappez ce [!UICONTROL segment] à une destination [!DNL Google] ou [!DNL Adobe Advertising Cloud], vous pouvez voir un [!UICONTROL Addressable Audience] de 700 000 appareils et un [!UICONTROL Match Rate] de 70 %. Les 700 000 membres sont constitués d’identifiants [!DNL cookie] qui ont une synchronisation d’identifiant avec le [!UICONTROL destination]. Votre [!UICONTROL Addressable Audience] peut en fait être beaucoup plus élevé, car les identifiants mobiles adressables n’apparaissent pas dans cette mesure. |
| Trafic [!DNL Safari] | [!DNL Safari] bloque les [!DNL cookies] tiers. Cela empêche [!DNL Audience Manager] de synchroniser les identifiants avec le [!UICONTROL destination]. Avec l’introduction d’[ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), vous pouvez vous attendre à ce que votre [!UICONTROL addressable audiences] n’inclue pas les utilisateurs [!DNL Safari]. |
| Impressions multimédia suivies | En raison des bonnes pratiques du serveur de publicités, les synchronisations des identifiants ne sont pas effectuées dans les balises de publicités. Les clients qui effectuent un grand nombre de publicités hors site ne synchroniseront pas les utilisateurs avec des intégrations tierces dans ces environnements. En outre, une grande quantité de données d’impressions multimédia collectées pourrait réduire le nombre de [!UICONTROL addressable audience]. |

## Résolution des problèmes liés à [!UICONTROL Addressable Audiences] {#troubleshooting}

Outre l’affichage des taux de correspondance, vous pouvez également utiliser [!UICONTROL Addressable Audiences] comme outil de dépannage.

Supposons, par exemple, que vous envoyiez un segment à un [!UICONTROL destination] et que ce [!UICONTROL destination] affiche de faibles nombres de rapports. La vérification des résultats [!UICONTROL Addressable Audience] vous indiquera s’il s’agit d’un problème technique ou simplement d’un cas de faible taux de correspondance. Un faible taux de correspondance indique que votre [!UICONTROL destination] n’est pas très adapté aux segments sélectionnés. Cependant, une différence dans les nombres de [!UICONTROL total addressable audience] entre [!DNL Audience Manager] et le [!UICONTROL destination] indique une intégration, une synchronisation ou un autre problème technique. Dans ce cas, contactez votre gestionnaire de compte.
