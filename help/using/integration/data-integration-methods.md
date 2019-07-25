---
description: Présentation générale de la manière dont Audience Manager échange les informations avec d'autres fournisseurs et systèmes de données.
seo-description: Présentation générale de la manière dont Audience Manager échange les informations avec d'autres fournisseurs et systèmes de données.
seo-title: Méthodes d’intégration des données
solution: Audience Manager
title: Méthodes d’intégration des données
uuid: 17 a 4179 a-e 99 b -49 eb -8 f 45-f 2946 afbd 27 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Méthodes d’intégration des données {#data-integration-methods}

Présentation générale de la manière dont Audience Manager échange les informations avec d'autres fournisseurs et systèmes de données.

## Supported Data Integration Methods: Real-Time and Server-to-Server {#supported-methods}

Choisir la méthode d'intégration appropriée dépend de la combinaison des besoins commerciaux et des fonctionnalités techniques de votre partenaire de données. Audience Manager échange les informations sur les visiteurs avec d'autres fournisseurs de données selon l'une des méthodes suivantes :

* **Real - time :** Transfère les données immédiatement lorsqu'un utilisateur visite votre site. This method is also known as a *`synchronous`* integration.
* **Batch (serveur-to-server) :** Transfère les données entre les serveurs dans un calendrier défini après la sortie de la page par un visiteur. This method is also known as an *`out-of-band`* or *`asynchronous`* integration.

## Prerequisites: Create a Trait Taxonomy {#prereqs}

Before the integration process begins, remember to [create traits](../features/traits/create-onboarded-rule-based-traits.md) and a [folder structure](../features/traits/trait-storage.md#create-trait-storage-folder) in the [!DNL Audience Manager] UI. La taxonomie contiendra toutes vos caractéristiques organisées dans une hiérarchie logique.

## Integration Use Cases {#integration-use-cases}

Résumé de cas d'utilisation des méthodes d'intégration des données Audience Manager, ainsi que des avantages et inconvénients de chacun d'eux.

### Real - Time Server-to-Server Integrations

<!-- c_int_types_use_cases.xml -->

Une intégration de données serveur à serveur en temps réel synchronise rapidement les données utilisateur entre les serveurs Audience Manager et un autre système de ciblage. Dans la plupart des cas, l'échange de données a lieu en quelques secondes ou minutes, selon le taux d'actualisation du système de ciblage. Notez toutefois que le système ciblé détermine cet intervalle d'actualisation et non Audience Manager. De plus, le taux d'actualisation peut varier d'un système à l'autre. Une intégration serveur à serveur en temps réel est le type d'intégration préféré pour les échanges de données. Audience Manager utilise cette méthode chaque fois que des partenaires de ciblage peuvent le prendre en charge.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>Avantages: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">Vous permet de qualifier les utilisateurs des segments sans les voir à nouveau sur la page, dans un lecteur vidéo, etc. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> Réduit le nombre d'appels HTTP à partir de la page. Moins d'appels permettent de conserver l'expérience de l'utilisateur. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">Facilite le ciblage temporel afin que vous puissiez agir rapidement sur un utilisateur qualifié. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">Utile lorsque vous passez à un DSP pour le ciblage hors offsite. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Inconvénients :</td>
  <td class="stentry"> Moins utile pour le ciblage sur site lorsque vous devez cibler l'utilisateur sur la même page ou la page suivante, en fonction de la qualification d'un utilisateur pour ce segment.</td>
 </tr>
</table>

### Intégrations par lots de serveur à serveur

Un groupe d'intégration de lot serveur à serveur regroupe les données et les envoie à d'autres systèmes à des intervalles définis plutôt qu'en temps réel. Les intervalles de transfert de données commencent à partir de 24 heures. Certains fournisseurs de données prennent uniquement en charge ce type d'intégration. Toutefois, nous avons vu une tendance générale par rapport aux intégrations par lots à des méthodologies d'intégration en temps réel.

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>Avantages: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">Vous permet de qualifier les utilisateurs des segments sans les voir à nouveau sur la page, dans un lecteur vidéo, etc. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">Utile pour le ciblage qui n'est pas sensible à l'heure. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Inconvénients :</td>
  <td class="stentry"> L'intervalle de synchronisation peut retarder le ciblage par rapport aux données les plus récentes.</td>
 </tr>
</table>

### Appels en temps réel

Les appels en temps réel échangent les données avec Audience Manager immédiatement, lorsqu'un utilisateur visite votre site ou qu'il effectue des actions sur la page. Avec cette méthode, les systèmes de ciblage obtiennent les données de qualification des segments les plus récentes et peuvent prendre en compte ces informations lors d'une décision de diffusion de contenu ou de publicité. Ce processus fonctionne également avec les serveurs d'annonces d'éditeur, où nous mettons à jour les segments qualifiés vers un cookie propriétaire lu dans un appel publicitaire en tant que paires clé-valeur. Currently, Audience Manager uses real-time calls to integrate with [!DNL Target] and other content management systems.

<table> 
 <tr>
  <td> <p>Avantages: </p></td>
  <td> <p> Vous permet de cibler la page suivante, la zone de contenu ou l'impression publicitaire selon la qualification de segment la plus récente. </p></td> 
 </tr> 
 <tr>
  <td> <p>Inconvénients : </p></td>
  <td> <p>Ajoute un appel à Audience Manager à partir de la page.</p></td>
 </tr> 
</table>


### Pixels synchronisés avec les systèmes de ciblage

La synchronisation des pixels associe les segments aux pixels sur la page. Le pixel se déclenche et transmet les données lorsqu'un utilisateur est admissible pour un segment particulier. La synchronisation des pixels est un mécanisme de transfert de données rudimentaire et non fiable. Les fournisseurs et les systèmes de données de niveau supérieur l'utilisent rarement.

<table id="simpletable_39E4CD139CCF4417842AA28CDFFB6EB1"> 
 <tr class="strow">
  <td class="stentry"> <p>Avantages: </p></td>
  <td class="stentry"> <p> Transferts de données en temps réel. </p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>Inconvénients : </p></td>
  <td class="stentry"> 
   <ul id="ul_5217EDC82434401493C2C96823C068E9"> 
    <li id="li_26EB0458CA1844908C005A47F55E50AC">Peut ajouter un grand nombre d'appels côté client à partir de la page. </li>
    <li id="li_CD91F3DC92F2429293787D61506E5E04">Non fiable pour la transmission des données. Une perte de 5 % à 20 % est normale. </li>
   </ul></td>
 </tr> 
</table>

## How to Choose a Data Delivery Method {#data-delivery-choices}

Décrit des raisons techniques et commerciales d'envoi de données par le biais de méthodologies synchrones (en temps réel) ou asynchrones (serveur à serveur).

<!-- c_int_delivery_choices.xml -->

### Sélection d'un type de remise de données

* **Considérations techniques :** La remise des données dépend des fonctionnalités techniques du partenaire de données. Audience Manager peut envoyer/recevoir des données en temps réel depuis le navigateur ou par lots via des processus de communication hors ligne et serveur à serveur.
* **Considérations économiques :** Les raisons commerciales de la sélection d'une méthode de livraison ou d'une autre dépendent des capacités techniques du partenaire de destination et de la manière dont vous souhaitez utiliser ces données. En règle générale, les transferts de données synchrones sont utiles lorsque vous devez agir immédiatement sur les données utilisateur. Les transferts de données asynchrones peuvent s'avérer utiles lorsque l'action immédiate n'est pas nécessaire et lorsque vous avez le temps de créer des profils utilisateur plus profonds pour une utilisation ultérieure.

## Real-Time Data Transfer Process {#real-time-data-transfer-process}

Présentation générale de la manière dont Audience Manager effectue un échange de données synchrones avec un fournisseur tiers.

### Real - Time Data Transfer

<!-- c_int_overview_sync.xml -->

Les données en temps réel permettent de transférer et de recevoir des ID de segment en tant qu'utilisateurs de visites ou d'actions sur votre site. En règle générale, les transferts de données synchrones sont utiles lorsque vous devez qualifier ou segmenter les utilisateurs à droite, à mesure qu'ils naviguent dans votre inventaire.

### Real - Time Data Integration Steps

Le processus d'intégration des données en temps réel fonctionne comme suit :

1. Un utilisateur visite le site d'un client qui contient le code Audience Manager.
1. Audience Manager loads an Iframe and makes a call to the [!UICONTROL Data Collection Server] ([!UICONTROL DCS]).
1. The [!UICONTROL DCS] calls the third-party server (in real time) to check if the vendor has any segment information about the user.
1. Le tiers renvoie les informations de segment relatives à cet utilisateur à Audience Manager.
1. Audience Manager ingère les informations de segment et les rend disponibles pour le ciblage.

![](assets/rt_reduce70.png)

## Batch Data Transfer Process {#batch-data-transfer-process}

Présentation générale de la manière dont Audience Manager échange les données de manière synchrone (en temps réel) avec un fournisseur tiers.

### Intégration de données par lots

<!-- c_int_overview_async.xml -->

Le processus d'intégration de données par lot (serveur à serveur) suit la plupart des étapes décrites dans le processus de transfert des données en temps réel. Toutefois, au lieu de renvoyer immédiatement les ID de segment, les informations utilisateur sont enregistrées sur nos serveurs et synchronisées avec un fournisseur de données tiers à intervalles réguliers. Le processus asynchrone de transfert des données est utile lorsque :

* Les transferts de données immédiats ne sont pas requis.
* Collecte de données pour créer un grand pool d'utilisateurs segmentés.
* You want to reduce data discrepancies and `HTTP` calls from the browser.

### Étapes d'intégration des données par lots

1. Un utilisateur visite un site client.
1. Audience Manager et le fournisseur de données tiers attribuent au visiteur un identifiant unique (généralement avec un cookie).
1. Audience Manager appelle le fournisseur de données tiers pour correspondre aux identifiants des visiteurs.
1. Une requête planifiée, généralement sur une fréquence quotidienne, échange les données de segmentation des visiteurs entre Audience Manager et votre fournisseur de données tiers.

![](assets/s2s_70.png)

For information describing the time frames when Audience Manager processes inbound and outbound Server-to-Server ([!UICONTROL S2S]) file transfers, see [Reporting and File Transfer Time-Frame Guidelines](../reference/reporting-file-transfer-timeframe.md).
