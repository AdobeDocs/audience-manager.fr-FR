---
description: Présentation générale de la manière dont Audience Manager échange des informations avec d’autres fournisseurs et systèmes de données.
seo-description: A high-level overview of how Audience Manager exchanges information with other data providers and systems.
seo-title: Data Integration Methods
solution: Audience Manager
title: Méthodes d’intégration des données
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
feature: Third-party Integration
exl-id: 26225461-c35c-4db1-9517-99e82ce163b9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 0%

---

# Méthodes d’intégration des données {#data-integration-methods}

Présentation générale de la manière dont Audience Manager échange des informations avec d’autres fournisseurs et systèmes de données.

## Méthodes d’intégration de données prises en charge : temps réel et [!DNL Server-to-Server] {#supported-methods}

Le choix de la méthode d’intégration appropriée dépend de la combinaison des besoins de l’entreprise et des capacités techniques de votre partenaire de données. Audience Manager échange des informations sur les visiteurs avec d’autres fournisseurs de données par l’une des méthodes suivantes :

* **Temps réel :** transfère immédiatement les données lorsqu’un utilisateur visite votre site. Cette méthode est également appelée intégration *`synchronous`*.
* **Lot ([!DNL Server-to-Server]) :** transfère les données entre les serveurs selon un planning défini après qu’un visiteur a quitté la page. Cette méthode est également appelée intégration *`out-of-band`* ou *`asynchronous`*.

## Conditions préalables : créer une taxonomie de caractéristiques {#prereqs}

Avant de commencer le processus d’intégration, pensez à [créer des caractéristiques](../features/traits/create-onboarded-rule-based-traits.md) et une [structure de dossiers](../features/traits/trait-storage.md#create-trait-storage-folder) dans l’interface utilisateur de [!DNL Audience Manager]. La taxonomie contiendra tous vos [!UICONTROL traits] organisés dans une hiérarchie logique.

## Cas d’utilisation de l’intégration {#integration-use-cases}

Résumé du cas d’utilisation des méthodes d’intégration de données d’Audience Manager, ainsi que les avantages et les inconvénients de chacune d’elles.

### Intégrations Real-Time [!DNL Server-to-Server]

<!-- c_int_types_use_cases.xml -->

Une intégration de données [!DNL server-to-server] en temps réel synchronise rapidement les données utilisateur entre les serveurs Audience Manager et un autre système de ciblage. Dans la plupart des cas, l’échange de données a lieu en quelques secondes ou minutes, selon la fréquence de rafraîchissement du système de ciblage. Notez toutefois que le système ciblé détermine cet intervalle d’actualisation, et non Audience Manager. De plus, le taux de rafraîchissement peut varier d&#39;un système à l&#39;autre. Une intégration [!UICONTROL server-to-server] en temps réel est le type d’intégration préféré pour les échanges de données. Audience Manager utilise cette méthode chaque fois que les partenaires de ciblage peuvent la prendre en charge.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>Avantages : </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">Permet de qualifier des utilisateurs pour des segments sans les revoir sur la page, dans un lecteur vidéo, etc. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> Réduit le nombre d’appels HTTP de la page. Moins d’appels permet de préserver l’expérience utilisateur. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">Aide avec le ciblage sensible au temps afin que vous puissiez agir rapidement sur un utilisateur qualifié. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">Utile lors du déplacement vers un DSP pour le ciblage hors site. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Inconvénients :</td>
  <td class="stentry"> Moins utile pour le ciblage sur site lorsque vous devez cibler l’utilisateur sur la même page ou la page suivante, en fonction de la qualification d’un utilisateur pour ce segment.</td>
 </tr>
</table>

### Intégrations par lots [!DNL Server-to-Server]

Une intégration par lots [!DNL server-to-server] regroupe les données et les envoie à d’autres systèmes à des intervalles définis plutôt qu’en temps quasi réel. Les intervalles de transfert de données commencent à 24 heures. Certains fournisseurs de données prennent uniquement en charge ce type d’intégration. Cependant, nous avons constaté une tendance générale des intégrations par lots vers des méthodologies d’intégration en temps réel.

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>Avantages : </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">Permet de qualifier des utilisateurs pour des segments sans les revoir sur la page, dans un lecteur vidéo, etc. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">Utile pour le ciblage qui n’est pas sensible au temps. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Inconvénients :</td>
  <td class="stentry"> L’intervalle de synchronisation peut retarder le ciblage par rapport aux données les plus récentes.</td>
 </tr>
</table>

### Appels en temps réel

Les appels en temps réel échangent immédiatement des données avec Audience Manager lorsqu’un utilisateur visite votre site ou effectue une action sur la page. Grâce à cette méthode, les systèmes de ciblage obtiennent les données de qualification de segment les plus récentes et peuvent prendre en compte ces informations lors d’une décision de diffusion de contenu ou d’annonce publicitaire. En outre, ce processus fonctionne avec les serveurs de publicités de l’éditeur où nous mettons à jour les segments qualifiés vers un cookie propriétaire qui est lu dans un appel publicitaire sous la forme de paires clé-valeur. Actuellement, Audience Manager utilise des appels en temps réel pour s’intégrer à [!DNL Adobe Target] et à d’autres systèmes de gestion de contenu.

<table> 
 <tr>
  <td> <p>Avantages : </p></td>
  <td> <p> Vous permet de cibler la page, la zone de contenu ou l’impression publicitaire suivante en fonction de la qualification du segment la plus récente. </p></td> 
 </tr> 
 <tr>
  <td> <p>Inconvénients : </p></td>
  <td> <p>Ajoute un appel à Audience Manager depuis la page.</p></td>
 </tr> 
</table>


### Synchronisation des pixels avec les systèmes de ciblage

La synchronisation des pixels mappe les segments aux pixels sur la page. Le pixel se déclenche et transmet des données lorsqu’un utilisateur remplit les conditions pour un segment particulier. La synchronisation des pixels est un mécanisme de transfert de données rudimentaire et peu fiable. Les fournisseurs de données et les systèmes de premier plan les utilisent rarement.

<table id="simpletable_39E4CD139CCF4417842AA28CDFFB6EB1"> 
 <tr class="strow">
  <td class="stentry"> <p>Avantages : </p></td>
  <td class="stentry"> <p> Transferts de données en temps réel. </p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>Inconvénients : </p></td>
  <td class="stentry"> 
   <ul id="ul_5217EDC82434401493C2C96823C068E9"> 
    <li id="li_26EB0458CA1844908C005A47F55E50AC">Peut ajouter de nombreux appels côté client à partir de la page. </li>
    <li id="li_CD91F3DC92F2429293787D61506E5E04">Non fiable pour la transmission de données. Une perte de 5 à 20% est normale. </li>
   </ul></td>
 </tr> 
</table>

## Choix d’une méthode de diffusion des données {#data-delivery-choices}

Décrit les raisons techniques et commerciales de l’envoi de données par le biais de méthodologies synchrones (temps réel) ou asynchrones (serveur à serveur).

<!-- c_int_delivery_choices.xml -->

### Sélection d’un type de diffusion de données

* **Considérations techniques :** la diffusion des données dépend des capacités techniques du partenaire de données. Audience Manager peut envoyer/recevoir des données en temps réel à partir du navigateur ou par mises à jour par lots via des processus de communication serveur à serveur hors ligne.
* **Considérations commerciales :** les raisons commerciales de sélectionner une méthode de diffusion ou une autre dépendent des capacités techniques de votre partenaire de destination et de la manière dont vous souhaitez utiliser ces données. En règle générale, les transferts de données synchrones s’avèrent utiles lorsque vous devez agir immédiatement sur les données utilisateur. Les transferts de données asynchrones peuvent s’avérer utiles lorsqu’une action immédiate n’est pas nécessaire et lorsque vous avez le temps de créer des profils d’utilisateur plus détaillés pour une utilisation ultérieure.

## Processus De Transfert De Données En Temps Réel {#real-time-data-transfer-process}

Présentation générale de la manière dont Audience Manager effectue un échange de données synchrone avec un fournisseur tiers.

### Transfert De Données En Temps Réel

<!-- c_int_overview_sync.xml -->

Les transferts de données en temps réel envoient et reçoivent des identifiants de segment lorsqu’un utilisateur visite votre site ou y effectue une action. En règle générale, les transferts de données synchrones sont utiles lorsque vous devez qualifier ou segmenter les utilisateurs immédiatement, lorsqu’ils parcourent votre inventaire.

### Étapes D’Intégration Des Données En Temps Réel

Le processus d’intégration des données en temps réel fonctionne comme suit :

1. Un utilisateur visite le site d’un client qui contient du code Audience Manager.
1. Audience Manager charge un Iframe et effectue un appel au [!UICONTROL Data Collection Server] ([!DNL DCS]).
1. Le [!DNL DCS] appelle le serveur tiers (en temps réel) pour vérifier si le fournisseur dispose d’informations sur les segments de l’utilisateur.
1. Le tiers renvoie des informations sur le segment de cet utilisateur à Audience Manager.
1. Audience Manager ingère les informations sur les segments et les rend disponibles pour le ciblage.

![](assets/rt_reduce70.png)

## Processus de transfert de données par lots {#batch-data-transfer-process}

Présentation générale de la manière dont Audience Manager échange des données de manière synchrone (en temps réel) avec un fournisseur tiers.

### Intégration de données par lots

<!-- c_int_overview_async.xml -->

Le processus d’intégration des données par lot ([!DNL server-to-server]) suit la plupart des étapes décrites dans le processus de transfert de données en temps réel. Cependant, au lieu de renvoyer immédiatement les identifiants de segment, les informations utilisateur sont enregistrées sur nos serveurs et synchronisées à intervalles réguliers avec un fournisseur de données tiers. Le processus de transfert de données asynchrone est utile lorsque :

* Les transferts de données immédiats ne sont pas requis.
* Collecte de données pour créer un grand pool d’utilisateurs segmentés.
* Vous souhaitez réduire les incohérences de données et les appels `HTTP` du navigateur.

### Étapes d’intégration des données par lots

1. Un utilisateur visite un site client.
1. Audience Manager et le fournisseur de données tiers attribuent au visiteur un identifiant unique (généralement avec un cookie).
1. Audience Manager appelle le fournisseur de données tiers pour qu’il corresponde aux identifiants visiteur.
1. Une requête planifiée, généralement à intervalle quotidien, échange des données de segment visiteur entre Audience Manager et votre fournisseur de données tiers.

![](assets/s2s_70.png)

[!DNL Server-to-Server] Pour plus d’informations sur les délais de traitement des transferts de fichiers entrants et sortants ([!UICONTROL S2S]) par Audience Manager, voir [Instructions relatives aux délais de reporting et de transfert de fichiers](../reference/reporting-file-transfer-timeframe.md).
