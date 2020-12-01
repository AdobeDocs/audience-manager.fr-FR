---
description: Présentation générale de la manière dont l’Audience Manager échange des informations avec d’autres fournisseurs et systèmes de données.
seo-description: Présentation générale de la manière dont l’Audience Manager échange des informations avec d’autres fournisseurs et systèmes de données.
seo-title: Méthodes d’intégration des données
solution: Audience Manager
title: Méthodes d’intégration des données
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1085'
ht-degree: 1%

---


# Méthodes d’intégration des données {#data-integration-methods}

Présentation générale de la manière dont l’Audience Manager échange des informations avec d’autres fournisseurs et systèmes de données.

## Méthodes d’intégration des données prises en charge : Temps réel et [!DNL Server-to-Server] {#supported-methods}

Le choix de la bonne méthode d’intégration dépend de la combinaison des exigences de l’entreprise et des capacités techniques de votre partenaire de données. L’Audience Manager échange des informations du visiteur avec d’autres fournisseurs de données par l’une des méthodes suivantes :

* **Temps réel :** transfère les données immédiatement lorsqu’un utilisateur visite votre site. Cette méthode est également appelée intégration *`synchronous`*.
* **Lot ([!DNL Server-to-Server]) :** transfère les données entre les serveurs selon un calendrier défini après qu’un visiteur ait quitté la page. Cette méthode est également appelée intégration *`out-of-band`* ou *`asynchronous`*.

## Conditions préalables : Créer une taxonomie de caractéristiques {#prereqs}

Avant de commencer le processus d’intégration, veillez à [créer des caractéristiques](../features/traits/create-onboarded-rule-based-traits.md) et à créer une structure de dossiers [](../features/traits/trait-storage.md#create-trait-storage-folder) dans l’interface utilisateur [!DNL Audience Manager]. La taxonomie contiendra tous vos [!UICONTROL traits] organisés dans une hiérarchie logique.

## Cas d’utilisation d’intégration {#integration-use-cases}

Résumé du cas d’utilisation des méthodes d’intégration des données d’Audience Manager avec les avantages et les inconvénients de chacune.

### Intégrations [!DNL Server-to-Server] en temps réel

<!-- c_int_types_use_cases.xml -->

Une intégration de données [!DNL server-to-server] en temps réel synchronise rapidement les données utilisateur entre les serveurs d’Audience Manager et un autre système de ciblage. Dans la plupart des cas, l’échange de données a lieu en quelques secondes ou minutes, selon le taux d’actualisation du système de ciblage. Notez toutefois que le système ciblé détermine cet intervalle d’actualisation et non l’Audience Manager. En outre, le taux de rafraîchissement peut varier selon les systèmes. Une intégration [!UICONTROL server-to-server] en temps réel est le type d’intégration préféré pour les échanges de données. L’Audience Manager utilise cette méthode chaque fois que des partenaires de ciblage peuvent la prendre en charge.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>Avantages: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">Vous permet de définir les segments des utilisateurs sans les revoir sur la page, dans un lecteur vidéo, etc. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> Réduit le nombre d’appels HTTP de la page. Un nombre moins élevé d’appels permet de préserver l’expérience de l’utilisateur. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">Aide le ciblage temporel afin que vous puissiez agir rapidement sur un utilisateur qualifié. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">Utile lors du passage à un DSP pour le ciblage hors site. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Inconvénients :</td>
  <td class="stentry"> Moins utile pour le ciblage sur site lorsque vous devez cible l’utilisateur sur la même page, ou sur la page suivante, en fonction de la qualification d’un utilisateur pour ce segment.</td>
 </tr>
</table>

### [!DNL Server-to-Server] Intégrations par lots

Une intégration par lot [!DNL server-to-server] regroupe les données et les envoie à d&#39;autres systèmes à intervalles définis plutôt qu&#39;en temps quasi réel. Les intervalles de transfert de données début à partir de 24 heures. Certains fournisseurs de données prennent uniquement en charge ce type d’intégration. Cependant, nous avons observé une tendance générale à l&#39;abandon des intégrations par lots vers des méthodologies d&#39;intégration en temps réel.

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>Avantages: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">Vous permet de définir les segments des utilisateurs sans les revoir sur la page, dans un lecteur vidéo, etc. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">Utile pour le ciblage qui n’est pas sensible au temps. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Inconvénients :</td>
  <td class="stentry"> L’intervalle de synchronisation peut retarder le ciblage des données les plus récentes.</td>
 </tr>
</table>

### Appels en temps réel

Les appels en temps réel échangent immédiatement des données avec l’Audience Manager, lorsqu’un utilisateur visite votre site ou agit sur la page. Grâce à cette méthode, les systèmes de ciblage obtiennent les données de qualification de segment les plus mises à jour et peuvent prendre ces informations en compte lors d’une décision de contenu ou de diffusion publicitaire. En outre, ce processus fonctionne avec les serveurs d’annonces d’éditeurs sur lesquels nous mettons à jour des segments qualifiés vers un cookie propriétaire qui est lu dans un appel d’annonce en tant que paires clé-valeur. Actuellement, l&#39;Audience Manager utilise des appels en temps réel pour s&#39;intégrer à [!DNL Adobe Target] et à d&#39;autres systèmes de gestion de contenu.

<table> 
 <tr>
  <td> <p>Avantages: </p></td>
  <td> <p> Permet de cible la page suivante, la zone de contenu ou l’impression publicitaire en fonction de la dernière qualification de segment. </p></td> 
 </tr> 
 <tr>
  <td> <p>Inconvénients : </p></td>
  <td> <p>Ajoute un appel à l’Audience Manager à partir de la page.</p></td>
 </tr> 
</table>


### Synchronisation des pixels avec les systèmes de ciblage

La synchronisation des pixels mappe les segments aux pixels sur la page. Le pixel se déclenche et transmet des données lorsqu’un utilisateur est admissible pour un segment particulier. La synchronisation des pixels est un mécanisme rudimentaire et peu fiable de transfert de données. Les fournisseurs et systèmes de données de haut niveau l’utilisent rarement.

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

## Comment choisir une méthode de Diffusion de données {#data-delivery-choices}

Décrit les raisons techniques et commerciales d’envoi des données au moyen de méthodologies synchrones (en temps réel) ou asynchrones (serveur à serveur).

<!-- c_int_delivery_choices.xml -->

### Sélection d&#39;un type de Diffusion de données

* **Considérations techniques :** La diffusion des données dépend des capacités techniques du partenaire de données. L’Audience Manager peut envoyer/recevoir des données en temps réel à partir du navigateur ou par le biais de mises à jour par lots par le biais de processus de communication serveur à serveur hors ligne.
* **Considérations commerciales :** Les raisons commerciales de la sélection d’une méthode de diffusion ou d’une autre dépendent des capacités techniques de votre partenaire de destination et de la manière dont vous souhaitez utiliser ces données. En règle générale, les transferts de données synchrones sont utiles lorsque vous devez agir immédiatement sur les données utilisateur. Les transferts de données asynchrones peuvent s’avérer utiles lorsque l’action immédiate n’est pas requise et lorsque vous avez le temps de créer des profils utilisateur plus approfondis pour une utilisation ultérieure.

## Processus de transfert de données en temps réel {#real-time-data-transfer-process}

Présentation générale de la manière dont l’Audience Manager effectue un échange de données synchrone avec un fournisseur tiers.

### Transfert de données en temps réel

<!-- c_int_overview_sync.xml -->

Les transferts de données en temps réel envoient et reçoivent des ID de segment lors de la visite d’un utilisateur ou d’une action sur votre site. En règle générale, les transferts de données synchrones sont utiles lorsque vous devez qualifier ou segmenter immédiatement les utilisateurs lorsqu’ils naviguent dans votre inventaire.

### Étapes d’intégration des données en temps réel

Le processus d’intégration des données en temps réel fonctionne comme suit :

1. Un utilisateur visite le site d’un client qui contient le code d’Audience Manager.
1. L&#39;Audience Manager charge un Iframe et appelle [!UICONTROL Data Collection Server] ([!DNL DCS]).
1. [!DNL DCS] appelle le serveur tiers (en temps réel) pour vérifier si le fournisseur dispose d&#39;informations de segment sur l&#39;utilisateur.
1. Le tiers renvoie à l’Audience Manager les informations de segment concernant cet utilisateur.
1. L’Audience Manager ingère des informations sur les segments et les rend disponibles pour le ciblage.

![](assets/rt_reduce70.png)

## Processus de transfert de données par lots {#batch-data-transfer-process}

Présentation générale de la manière dont l’Audience Manager échange les données de manière synchrone (en temps réel) avec un fournisseur tiers.

### Intégration des données par lot

<!-- c_int_overview_async.xml -->

Le processus d’intégration des données par lot ([!DNL server-to-server]) suit la plupart des étapes décrites dans le processus de transfert des données en temps réel. Cependant, au lieu de renvoyer immédiatement les ID de segment, les informations utilisateur sont enregistrées sur nos serveurs et synchronisées avec un fournisseur de données tiers à intervalles réguliers. Le processus de transfert de données asynchrone est utile lorsque :

* Les transferts de données immédiats ne sont pas nécessaires.
* Collecte de données pour créer un grand groupe d’utilisateurs segmentés.
* Vous souhaitez réduire les incohérences de données et les appels `HTTP` à partir du navigateur.

### Etapes d’intégration des données par lot

1. Un utilisateur visite un site client.
1. L’Audience Manager et le fournisseur de données tiers attribuent au visiteur un identifiant unique (généralement avec un cookie).
1. L’Audience Manager appelle le fournisseur de données tiers pour qu’il corresponde aux ID de visiteur.
1. Une demande planifiée, généralement à intervalles quotidiens, échange des données de segment de visiteur entre l’Audience Manager et votre fournisseur de données tiers.

![](assets/s2s_70.png)

Pour plus d&#39;informations sur les périodes pendant lesquelles l&#39;Audience Manager traite les transferts de fichiers entrants et sortants [!DNL Server-to-Server] ([!UICONTROL S2S]), voir [Lignes directrices sur les délais de Rapports et de transfert de fichiers](../reference/reporting-file-transfer-timeframe.md).
