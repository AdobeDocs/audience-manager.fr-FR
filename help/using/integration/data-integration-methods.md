---
description: Présentation générale de la manière dont Audience Manager échange des informations avec d’autres fournisseurs et systèmes de données.
seo-description: Présentation générale de la manière dont Audience Manager échange des informations avec d’autres fournisseurs et systèmes de données.
seo-title: Méthodes d’intégration des données
solution: Audience Manager
title: Méthodes d’intégration des données
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Méthodes d’intégration des données {#data-integration-methods}

Présentation générale de la manière dont Audience Manager échange des informations avec d’autres fournisseurs et systèmes de données.

## Méthodes d’intégration des données prises en charge : Temps réel et serveur à serveur {#supported-methods}

Le choix de la bonne méthode d’intégration dépend de la combinaison des exigences de l’entreprise et des capacités techniques de votre partenaire de données. Audience Manager échange les informations sur les visiteurs avec d’autres fournisseurs de données en utilisant l’une des méthodes suivantes :

* **** Temps réel : Transfère les données immédiatement lorsqu’un utilisateur visite votre site. Cette méthode est également connue sous le nom d’ *`synchronous`* intégration.
* **** Batch (serveur à serveur) : Transfère les données entre les serveurs selon un calendrier défini une fois qu’un visiteur a quitté la page. Cette méthode est également connue sous le nom d’intégration *`out-of-band`* ou *`asynchronous`* .

## Conditions préalables : Créer une taxonomie de caractéristiques {#prereqs}

Avant de commencer le processus d’intégration, pensez à [créer des caractéristiques](../features/traits/create-onboarded-rule-based-traits.md) et une structure [de](../features/traits/trait-storage.md#create-trait-storage-folder) dossiers dans l’ [!DNL Audience Manager] interface utilisateur. La taxonomie contiendra toutes vos caractéristiques organisées dans une hiérarchie logique.

## Cas d’utilisation d’intégration {#integration-use-cases}

Résumé du cas d’utilisation des méthodes d’intégration des données d’Audience Manager, ainsi que des avantages et inconvénients de chacune d’elles.

### Intégrations serveur à serveur en temps réel

<!-- c_int_types_use_cases.xml -->

Une intégration de données serveur à serveur en temps réel synchronise rapidement les données utilisateur entre les serveurs Audience Manager et un autre système de ciblage. Dans la plupart des cas, l’échange de données a lieu en quelques secondes ou minutes, selon le taux d’actualisation du système de ciblage. Notez toutefois que le système ciblé détermine cet intervalle d’actualisation et non Audience Manager. De plus, le taux d'actualisation peut varier selon les systèmes. Une intégration serveur à serveur en temps réel est le type d’intégration préféré pour les échanges de données. Audience Manager utilise cette méthode chaque fois que des partenaires de ciblage peuvent la prendre en charge.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>Avantages: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">Vous permet de qualifier les utilisateurs pour les segments sans les revoir sur la page, dans un lecteur vidéo, etc. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> Réduit le nombre d’appels HTTP de la page. Un nombre moins élevé d’appels permet de préserver l’expérience utilisateur. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">Aide le ciblage en fonction du temps afin que vous puissiez agir rapidement sur un utilisateur qualifié. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">Utile lors du passage à un fournisseur de services de données pour le ciblage hors site. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Inconvénients :</td>
  <td class="stentry"> Moins utile pour le ciblage sur site lorsque vous devez cibler l’utilisateur sur la même page, ou sur la page suivante, en fonction de la qualification d’un utilisateur pour ce segment.</td>
 </tr>
</table>

### Intégrations de lots serveur à serveur

Une intégration par lots serveur à serveur regroupe les données et les envoie à d’autres systèmes à intervalles définis plutôt qu’en temps quasi réel. Les intervalles de transfert des données commencent à 24 heures. Certains fournisseurs de données prennent uniquement en charge ce type d’intégration. Cependant, nous avons observé une tendance générale, loin des intégrations par lots, vers des méthodologies d'intégration en temps réel.

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>Avantages: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">Vous permet de qualifier les utilisateurs pour les segments sans les revoir sur la page, dans un lecteur vidéo, etc. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">Utile pour le ciblage qui n’est pas sensible au temps. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Inconvénients :</td>
  <td class="stentry"> L’intervalle de synchronisation peut retarder le ciblage par rapport aux données les plus récentes.</td>
 </tr>
</table>

### Appels en temps réel

Les appels en temps réel échangent immédiatement des données avec Audience Manager, lorsqu’un utilisateur visite votre site ou effectue une action sur la page. Avec cette méthode, les systèmes de ciblage obtiennent les données de qualification de segment les plus mises à jour et peuvent prendre en compte ces informations lors d’une décision de diffusion de contenu ou de publicité. Ce processus fonctionne également avec les serveurs d’annonces d’éditeurs où nous mettons à jour les segments qualifiés vers un cookie propriétaire qui est lu dans un appel publicitaire en tant que paires clé-valeur. Actuellement, Audience Manager utilise des appels en temps réel pour s’intégrer à [!DNL Target] et à d’autres systèmes de gestion de contenu.

<table> 
 <tr>
  <td> <p>Avantages: </p></td>
  <td> <p> Permet de cibler la page suivante, la zone de contenu ou l’impression publicitaire en fonction de la qualification de segment la plus récente. </p></td> 
 </tr> 
 <tr>
  <td> <p>Inconvénients : </p></td>
  <td> <p>Ajoute un appel à Audience Manager à partir de la page.</p></td>
 </tr> 
</table>


### Synchronisation des pixels avec les systèmes de ciblage

La synchronisation des pixels fait correspondre les segments aux pixels de la page. Le pixel se déclenche et transmet des données lorsqu’un utilisateur est admissible pour un segment particulier. La synchronisation des pixels est un mécanisme de transfert de données rudimentaire et peu fiable. Les fournisseurs et systèmes de données de haut niveau l’utilisent rarement.

<table id="simpletable_39E4CD139CCF4417842AA28CDFFB6EB1"> 
 <tr class="strow">
  <td class="stentry"> <p>Avantages: </p></td>
  <td class="stentry"> <p> Transferts de données en temps réel. </p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>Inconvénients : </p></td>
  <td class="stentry"> 
   <ul id="ul_5217EDC82434401493C2C96823C068E9"> 
    <li id="li_26EB0458CA1844908C005A47F55E50AC">Peut ajouter de nombreux appels côté client à partir de la page. </li>
    <li id="li_CD91F3DC92F2429293787D61506E5E04">Non fiable pour la transmission des données. Une perte de 5 à 20 % est normale. </li>
   </ul></td>
 </tr> 
</table>

## Comment choisir un mode de remise des données {#data-delivery-choices}

Décrit les raisons techniques et commerciales de l’envoi de données par le biais de méthodologies synchrones (en temps réel) ou asynchrones (serveur à serveur).

<!-- c_int_delivery_choices.xml -->

### Sélection d'un type de remise des données

* **** Considérations techniques : La remise des données dépend des capacités techniques du partenaire de données. Audience Manager peut envoyer/recevoir des données en temps réel à partir du navigateur ou par le biais de mises à jour par lots au moyen de processus de communication entre serveurs hors ligne.
* **** Considérations commerciales : Les raisons commerciales de la sélection d’un mode de livraison ou d’un autre dépendent des capacités techniques de votre partenaire de destination et de la manière dont vous souhaitez utiliser ces données. En règle générale, les transferts de données synchrones sont utiles lorsque vous devez agir immédiatement sur les données utilisateur. Les transferts de données asynchrones peuvent s’avérer utiles lorsque l’action immédiate n’est pas requise et lorsque vous avez le temps de créer des profils d’utilisateur plus approfondis pour une utilisation ultérieure.

## Processus de transfert de données en temps réel {#real-time-data-transfer-process}

Présentation générale de la manière dont Audience Manager effectue un échange de données synchrone avec un fournisseur tiers.

### Transfert de données en temps réel

<!-- c_int_overview_sync.xml -->

Les transferts de données en temps réel envoient et reçoivent des ID de segment lorsqu’un utilisateur visite votre site ou agit sur votre site. En règle générale, les transferts de données synchrones sont utiles lorsque vous devez immédiatement qualifier ou segmenter les utilisateurs, lorsqu’ils naviguent dans votre inventaire.

### Etapes d’intégration des données en temps réel

Le processus d’intégration des données en temps réel fonctionne comme suit :

1. Un utilisateur visite le site d’un client qui contient le code Audience Manager.
1. Audience Manager charge un Iframe et appelle le [!UICONTROL Data Collection Server] ([!UICONTROL DCS]).
1. L’ [!UICONTROL DCS] opérateur appelle le serveur tiers (en temps réel) pour vérifier si le fournisseur dispose d’informations de segment sur l’utilisateur.
1. Le tiers renvoie les informations de segment sur cet utilisateur à Audience Manager.
1. Audience Manager ingère les informations sur les segments et les rend disponibles pour le ciblage.

![](assets/rt_reduce70.png)

## Processus de transfert de données par lot {#batch-data-transfer-process}

Présentation générale de la manière dont Audience Manager échange les données de manière synchrone (en temps réel) avec un fournisseur tiers.

### Intégration des données par lot

<!-- c_int_overview_async.xml -->

Le processus d’intégration des données par lot (serveur à serveur) suit la plupart des étapes décrites dans le processus de transfert de données en temps réel. Toutefois, au lieu de renvoyer immédiatement les ID de segment, les informations utilisateur sont enregistrées sur nos serveurs et synchronisées avec un fournisseur de données tiers à intervalles réguliers. Le processus de transfert de données asynchrone est utile lorsque :

* Les transferts de données immédiats ne sont pas nécessaires.
* Collecte de données pour créer un grand groupe d’utilisateurs segmentés.
* Vous souhaitez réduire les incohérences de données et `HTTP` les appels du navigateur.

### Etapes d’intégration des données par lot

1. Un utilisateur visite un site client.
1. Audience Manager et le fournisseur de données tiers attribuent au visiteur un identifiant unique (généralement avec un cookie).
1. Audience Manager appelle le fournisseur de données tiers pour qu’il corresponde aux identifiants des visiteurs.
1. Une requête planifiée, généralement sur un intervalle quotidien, échange des données de segmentation des visiteurs entre Audience Manager et votre fournisseur de données tiers.

![](assets/s2s_70.png)

Pour plus d’informations sur les périodes au cours desquelles Audience Manager traite les transferts de fichiers Server vers Server ([!UICONTROL S2S]) entrants et sortants, voir Instructions [relatives aux délais de](../reference/reporting-file-transfer-timeframe.md)création de rapports et de transfert de fichiers.
