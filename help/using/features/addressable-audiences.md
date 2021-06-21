---
description: Présentation de la fonction Audience adressable et des cas pratiques.
keywords: DIL
seo-description: Présentation de la fonction Audience adressable et des cas pratiques.
seo-title: Audiences adressables
solution: Audience Manager
title: Audiences adressables
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Taux de correspondance
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1827'
ht-degree: 1%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Présentation de la fonction [!UICONTROL Addressable Audience] et des cas pratiques.

## Qu’est-ce qu’une [!UICONTROL Addressable Audience]? {#addressable-audience-description}

La fonction [!UICONTROL Addressable Audiences] indique le chevauchement entre les audiences que vous voyez dans toutes vos propriétés où [!DNL Audience Manager] collecte des données et la destination sélectionnée. Pour vous aider à comprendre ce concept, consultez l’illustration ci-dessous. Le chevauchement entre chaque cercle représente les différents types d’audiences adressables.

![](assets/addressableAudienceVenn.png)


| Mesure | Description |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] pour un  [!UICONTROL Destination] | Comptage de tous les appareils qui ont interagi avec tous les clients [!DNL Audience Manager] au niveau de la plateforme au cours de la période d’analyse du rapport et qui peuvent être mis en correspondance avec la [!UICONTROL destination] de votre choix. <br><br>Cette mesure s’avère utile, car elle vous présente les éléments suivants : <ul><li>Taille de la [!UICONTROL addressable audience] totale que [!DNL Audience Manager] peut atteindre sur un ciblage particulier [!UICONTROL destination].</li><li>Taille du pool de profils [!DNL Audience Manager] pour une plateforme de ciblage et la taille de leurs audiences.</li></ul> |
| [!UICONTROL Customer Total Audience] | Nombre de périphériques qui ont généré soit une [!UICONTROL rule-based trait] sur vos propriétés, soit une [!UICONTROL onboarded trait] à partir de vos fichiers hors ligne pendant la fenêtre rétroactive. |
| [!UICONTROL Addressable Audience Match Rate] | Nombre de chevauchements des appareils qui ont créé une balise [!UICONTROL rule-based trait] ou [!UICONTROL onboarded trait] pendant la fenêtre rétroactive et des appareils dont l’identifiant est synchronisé avec la balise [!UICONTROL destination] sélectionnée, quelle que soit l’heure de la synchronisation.<br><br>Cette mesure représente les appareils qui :<ul><li>ont réalisé une balise [!UICONTROL rule-based] ou [!UICONTROL onboarded trait] au cours de la fenêtre rétroactive `AND` ;</li><li>disposer d’une synchronisation des identifiants avec la balise [!UICONTROL destination] choisie, quelle que soit l’heure de la synchronisation.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷  [!UICONTROL Customer Total Audience] exprimé en pourcentage. |
| [!UICONTROL Total Segment Population] | Comptage de tous les appareils qui ont été membres de votre [!UICONTROL segment] pendant la période d’analyse du rapport. |
| [!UICONTROL Segment Addressable Audience] | Nombre d’utilisateurs qui ont appartenu à [!UICONTROL segment] au cours de la période de recherche en amont du rapport et qui disposent d’une synchronisation d’identifiant principale sur votre site. [!UICONTROL Segments] peuvent inclure vos propres données propriétaires et des données de deuxième et de troisième niveau, via  [!UICONTROL traits] acquises dans l’ [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Conseil : Utilisée avec la période de recherche en amont d’un jour, cette mesure peut vous aider à comprendre l’état actuel de votre  [!UICONTROL segments]. Cela est dû au fait que la mesure [!UICONTROL Segment Addressable Audience] représente les utilisateurs qui sont restés dans une balise [!UICONTROL segment] au cours de la journée précédente. Combinez cela au fait que [!DNL Audience Manager] actualise [!UICONTROL Addressable Audiences] quotidiennement, en combinant cette mesure et cette période de recherche arrière pour obtenir l’instantané le plus récent de votre [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷  [!UICONTROL Total Segment Population] exprimé en pourcentage. |

## [!UICONTROL Addressable Audiences] Interface {#addressable-audience-interface}

La fonction [!UICONTROL Addressable Audience] transforme ce concept abstrait en données quantifiables. Dans [!DNL Audience Manager], cette fonctionnalité affiche le chevauchement des audiences avec des visualisations de données qui fournissent des informations en un coup d’oeil, ainsi que des données numériques sous forme tabulaire.

[!UICONTROL Addressable Audiences] se trouve dans  **[!UICONTROL Audience Data > Destinations]**. Sélectionnez **[!UICONTROL Integrated Platforms > Device-Based]** pour afficher les mesures d’audiences adressables.

![](assets/addressable-audiences-landing.png)

Les trois mesures que vous pouvez voir sur la page d’entrée [!UICONTROL Addressable Audiences] représentent :

| Mesure | Description |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Cette mesure représente la valeur [!UICONTROL Customer Addressable Audience] (décrite dans le tableau ci-dessus) *pour les 30 derniers jours.* |
| **[!UICONTROL Match Rate]** | Cette mesure représente la valeur [!UICONTROL Addressable Audience Match Rate] (décrite dans le tableau ci-dessus) *pour les 30 derniers jours*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Comptage de tous les appareils qui ont interagi avec tous les clients [!DNL Audience Manager] au niveau de la plateforme pendant la période d’analyse du rapport et qui peuvent être associés à cette [!UICONTROL destination]. Voir [Mesures au niveau de la plateforme](/help/using/features/addressable-audiences.md#platform-level-metrics) pour plus d’informations. |

Cliquez sur le nom d’une [!UICONTROL server-to-server destination] pour afficher vos données d’audience adressables. Remarque : cette fonctionnalité renvoie des données pour [!UICONTROL server-to-server destinations] uniquement et l’accès nécessite des autorisations d’administrateur.

![](assets/addressableAudiences.png)

La vérification de ces données peut vous aider à :

* **Prévisions et planification :** [!UICONTROL Segment Addressable Audience]  les données vous donnent plus de granularité dans les segments que vous prévoyez d’envoyer vers une destination pour le ciblage et l’activation des audiences.

* **Études de performances :** la  [!UICONTROL Addressable Audiences] fonctionnalité est également un outil de dépannage. Il vous permet de passer en revue les performances de la campagne, de comprendre la portée de la campagne et de vérifier avec les partenaires de ciblage/d’activation si vous ne voyez pas les résultats attendus.

### Planification avec des données tierces et implications pour les taux de correspondance

Avant d’acheter des données tierces pour l’acquisition d’audiences, les clients peuvent valider le chevauchement avec d’autres fournisseurs de données. Cela peut vous aider à prendre une décision éclairée avant d’acheter de nouvelles données. Les synchronisations des identifiants pour les données tierces achetées reposent non seulement sur le chevauchement de vos données, mais également sur l’empreinte des fournisseurs tiers sur tous les autres clients [!DNL Audience Manager]. Votre [!DNL Adobe] consultant peut vous aider à identifier d’autres sources de données pertinentes pour optimiser les campagnes de prospection.

### Utilisateurs mobiles et taux de correspondance

Il existe des lacunes lors de la tentative de connexion des utilisateurs [!DNL Safari] ou d’applications mobiles où il n’existe pas de [!DNL cookies] tiers. Il est donc difficile de synchroniser les utilisateurs avec certains partenaires, car seuls les [!DNL Adobe] identifiants des [!DNL cookies] tiers synchronisés sont fournis dans les logs de diffusion multimédia. C’est la raison pour laquelle [les taux de correspondance faibles](../features/addressable-audiences.md#low-match-rates) peuvent apparaître pour votre [!UICONTROL destinations].

## Périodes dans [!UICONTROL Addressable Audiences] et [!UICONTROL Destinations] {#date-ranges}

Lisez les sections ci-dessous pour connaître les plages de dates disponibles et la façon dont les données sortent de chaque intervalle dans les rapports pour une [!UICONTROL Addressable Audience] ou [!UICONTROL Destination].

## Périodes disponibles et fuseaux horaires {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Les rapports pour vos [!UICONTROL Addressable Audiences] et [destinations](../features/destinations/destinations.md) utilisent les mêmes intervalles de période. Les options de période incluent :

* [!UICONTROL Last 1 Day] (Cet intervalle s’étend de minuit à minuit de la période de 24 heures précédente. Il ne s’agit pas d’une mesure en temps réel ou en temps réel.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Toutes les dates et plages de dates sont définies dans le [!DNL UTC] fuseau horaire. Voir [Fuseaux horaires en Audience Manager](../reference/aam-time-zones.md).

## Données des intervalles de plage de dates {#date-range-intervals}

Les mesures [!UICONTROL Addressable Audience] et [!UICONTROL Destination] renvoient un nombre d’utilisateurs uniques pour l’intervalle de temps sélectionné. Par exemple, un visiteur n’est comptabilisé qu’une seule fois, même s’il se rend plusieurs fois sur votre site. La première visite est la visite unique et est enregistrée. Les visites suivantes renvoient des visites et ne sont pas comptabilisées car elles ne sont pas uniques.

Les plages de dates contiennent des données pour l’intervalle de temps sélectionné ou plus ancien. De plus, les données vieillissent à chaque intervalle de rapport au fil du temps. Supposons, par exemple, que vous ayez 2 visiteurs après avoir choisi l’option [!UICONTROL Last 30 Days]. Dans les rapports, ces visiteurs :

* *Seront* inclus dans les résultats renvoyés par les intervalles de temps plus longs (60 jours, 90 jours et Durée de vie).
* *Ne sera pas* inclus dans les intervalles plus courts qui précèdent l’ [!UICONTROL Last 30 Day] option (En cours, 7 jours et 14 jours).

Et, le 31 jour, ces visiteurs ne s’affichent que dans les résultats de 60 jours, 90 jours et [!UICONTROL Lifetime]. Ils ont vieilli sur l’intervalle de 30 jours. Les visiteurs ne vieillissent pas dans l’intervalle [!UICONTROL Lifetime].

## [!UICONTROL Addressable Audiences] Mesures {#addressable-audience-metrics}

Cette section décrit les types de mesures fournis par [!UICONTROL Addressable Audiences].

### Mesures au niveau du client {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Ces mesures renvoient des données pour les caractéristiques réalisées lorsque les visiteurs se rendent sur votre site ou lorsque vous envoyez des fichiers de données entrants à [!DNL Audience Manager]. Ces mesures fournissent une vue complète de la taille de l’audience de votre compte.

| Mesure | Description |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Nombre de chevauchements des appareils qui ont créé [!UICONTROL rule-based trait] ou [!UICONTROL onboarded trait] pendant la période d’analyse et des appareils dont l’identifiant est synchronisé avec la destination choisie, quelle que soit l’heure de la synchronisation.<br><br>Cette mesure représente les appareils qui :<ul><li>ont réalisé une balise [!UICONTROL rule-based] ou [!UICONTROL onboarded trait] au cours de la fenêtre rétroactive `AND` ;</li><li>disposer d’une synchronisation des identifiants avec la balise [!UICONTROL destination] choisie, quelle que soit l’heure de la synchronisation.</li></ul> |
| [!UICONTROL Customer Total Audience] | Nombre de périphériques qui ont généré soit une [!UICONTROL rule-based trait] sur vos propriétés, soit une [!UICONTROL onboarded trait] à partir de vos fichiers hors ligne pendant la fenêtre rétroactive. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷  [!UICONTROL Customer Total Audience] exprimé en pourcentage. |

### Mesures de correspondance au niveau du segment {#segment-level-metrics}

Ces mesures renvoient des données sur l’appartenance à [!UICONTROL segment]. Elles vous aident à obtenir une vue plus granulaire et plus précise de la taille de l’audience pour chacune de vos [!UICONTROL segments].

>[!NOTE]
>
>La façon dont la fenêtre rétroactive est appliquée au niveau [!UICONTROL segment] est différente de celle appliquée au niveau du client. Les visiteurs peuvent se rendre sur le site et réaliser un [!UICONTROL trait] il y a 10 jours, et ils peuvent être admissibles à une [!UICONTROL segment] depuis lors et ont abandonné l’attribut [!UICONTROL segment] il y a 2 jours. Lorsque la recherche en amont de 7 jours est appliquée, ces visiteurs sont comptabilisés au niveau [!UICONTROL segment] mais pas au niveau client.

| Mesure | Description |
|---|---|
| [!UICONTROL Segment Addressable Audience] | Nombre d’utilisateurs qui ont appartenu à [!UICONTROL segment] au cours de la période de recherche en amont du rapport et qui disposent d’une synchronisation d’identifiant principale sur votre site. Les segments peuvent inclure vos propres données propriétaires, ainsi que des données de deuxième et de troisième niveau, par l’intermédiaire de [!UICONTROL traits] acquis dans l’[Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Conseil : Utilisée avec la période de recherche en amont d’un jour, cette mesure peut vous aider à comprendre l’état actuel de votre  [!UICONTROL segments]. Cela est dû au fait que la mesure [!UICONTROL Segment Addressable Audience] représente les utilisateurs qui sont restés dans une balise [!UICONTROL segment] au cours de la journée précédente. Combinez cela au fait que [!DNL Audience Manager] actualise [!UICONTROL Addressable Audiences] quotidiennement, en combinant cette mesure et cette période de recherche arrière pour obtenir l’instantané le plus récent de votre [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Comptage de tous les appareils qui ont été membres de votre [!UICONTROL segment] pendant la période d’analyse du rapport. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷  [!UICONTROL Total Segment Population] exprimé en pourcentage. |

### Mesures au niveau de la plateforme {#platform-level-metrics}

Cette mesure renvoie des données sur les activités collectées pour tous les clients [!DNL Audience Manager]. Ils peuvent fournir une vue plus large de l’audience du client par rapport aux clients [!DNL Audience Manager] agrégés.

| Mesure | Description |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Comptage de tous les appareils qui ont interagi avec tous les clients [!DNL Audience Manager] au niveau de la plateforme au cours de la période d’analyse du rapport et qui peuvent être mis en correspondance avec la [!UICONTROL destination] de votre choix. <br><br>Cette mesure s’avère utile, car elle vous présente les éléments suivants :<ul><li>Taille de [!UICONTROL total addressable audience] que [!DNL Audience Manager] peut atteindre sur une destination de ciblage particulière.</li><li>Taille du pool de profils [!DNL Audience Manager] pour une plateforme de ciblage et la taille de leurs audiences.</li></ul> |

## Comparaison de [!UICONTROL Customer] et [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

Vous ne devez pas comparer les mesures [!UICONTROL Customer Addressable Audience] et [!UICONTROL Segment Addressable Audience] pour déterminer si l’une est plus significative que l’autre. Il s’agit de mesures distinctes, différentes et indépendantes. Comme décrit dans les définitions ci-dessus, chacune de ces variables est dérivée de différents jeux de données. Dans ce contexte, vous devez éviter de déduire des conclusions si une mesure est supérieure à l’autre. Tout ce que vous pouvez dire en comparant ces éléments est :

* [!UICONTROL Customer Addressable Audiences] est basé sur  [!UICONTROL trait] des réalisations  *pour vos propres données* propriétaires. Cette mesure offre une vue large et complète de votre intégration à un partenaire de données.

* [!UICONTROL Segment Addressable Audiences] est basé sur les qualifications de segments  *pour vos propres données propriétaires, plus les données* de deuxième et de troisième niveau. Cette mesure fournit une vue granulaire et plus précise de votre [!UICONTROL addressable audiences] dans une plateforme de ciblage.

## Causes des faibles taux de correspondance pour [!UICONTROL Addressable Audiences] {#low-match-rates}

Éléments courants responsables de faibles taux de correspondance ou d’incohérences entre les nombres signalés.[!UICONTROL Addressable Audience]

| Cause | Description |
|---|---|
| Trafic mobile | La plupart des intégrations [!UICONTROL server-to-server] reposent sur des processus de synchronisation facilités par [!DNL cookies] tiers. Cependant, les environnements mobiles n’utilisent pas la balise [!DNL cookies] tierce. Par conséquent, vos nombres [!UICONTROL Addressable Audiences] peuvent sembler faibles par rapport à la taille [!UICONTROL segment]. <br><br>Depuis janvier 2018, vous pouvez activer les audiences mobiles dans les mêmes  [!DNL Google] et les  [!DNL Adobe Advertising Cloud] destinations configurées pour les  [!UICONTROL cookie-based] audiences. Bien que cela signifie que vous pouvez envoyer [!UICONTROL segments] avec l’appartenance à [!DNL cookie] et l’identifiant mobile combinés à vos destinations [!DNL Google] et [!DNL Advertising Cloud], gardez à l’esprit que [!UICONTROL Addressable Audiences] n’affiche que le chevauchement entre les [!DNL cookie] identifiants et les destinations. [!DNL Audience Manager] envoie 100 % des audiences mobiles à  [!UICONTROL destinations], mais les audiences mobiles ne sont pas mesurées par la  [!UICONTROL Addressable Audience] mesure. <br><br>**Remarque** : Par exemple, prenez un  [!UICONTROL segment] avec une population de 1 000 000. Si vous mappez cette [!UICONTROL segment] à une destination [!DNL Google] ou [!DNL Adobe Advertising Cloud], il se peut que [!UICONTROL Addressable Audience] de 700 000 périphériques et [!UICONTROL Match Rate] de 70 %. Les 700 000 membres se composent d’identifiants [!DNL cookie] synchronisés avec l’identifiant [!UICONTROL destination]. Votre [!UICONTROL Addressable Audience] peut, en fait, être beaucoup plus élevé, car les identifiants mobiles adressables n’apparaissent pas dans cette mesure. |
| [!DNL Safari] Trafic | [!DNL Safari] bloque les cookies tiers  [!DNL cookies]. Cela empêche [!DNL Audience Manager] de synchroniser les identifiants avec la balise [!UICONTROL destination]. Avec l’introduction de [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), vous pouvez vous attendre à ce que votre [!UICONTROL addressable audiences] ne contienne pas d’utilisateurs [!DNL Safari]. |
| Impressions de médias suivies | En raison des bonnes pratiques relatives au serveur d’annonces, les synchronisations des identifiants ne sont pas effectuées dans les balises d’annonce. Les clients qui effectuent une grande quantité de publicité hors site ne synchronisent pas les utilisateurs avec les intégrations tierces dans ces environnements. En outre, une grande quantité de données d’impression multimédia collectées pourrait réduire les [!UICONTROL addressable audience] nombres. |

## Dépannage avec [!UICONTROL Addressable Audiences] {#troubleshooting}

Outre les taux de correspondance de surface, vous pouvez également utiliser [!UICONTROL Addressable Audiences] comme outil de dépannage.

Par exemple, supposons que vous envoyiez un segment à [!UICONTROL destination] et que [!UICONTROL destination] affiche des nombres de rapports faibles. Si vous consultez les résultats [!UICONTROL Addressable Audience] , vous verrez s’il s’agit d’un problème technique ou simplement d’un cas de faibles taux de correspondance. Un faible taux de correspondance indique que votre [!UICONTROL destination] n’est pas très bon pour les segments sélectionnés. Cependant, une différence dans les nombres [!UICONTROL total addressable audience] entre [!DNL Audience Manager] et [!UICONTROL destination] indique une intégration, une synchronisation ou un autre problème technique. Dans ce cas, contactez votre gestionnaire de compte.
