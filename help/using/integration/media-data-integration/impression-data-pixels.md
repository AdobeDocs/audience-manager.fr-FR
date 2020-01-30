---
description: Une méthode d’envoi de données multimédias à Audience Manager utilise des macros de serveur d’annonces pour envoyer des attributs de campagne à Audience Manager.
seo-description: Une méthode d’envoi de données multimédias à Audience Manager utilise des macros de serveur d’annonces pour envoyer des attributs de campagne à Audience Manager.
seo-title: Capture des données d’impression de campagne via des appels de pixel
solution: Audience Manager
title: Capture des données d’impression de campagne via des appels de pixel
uuid: 6ac44100-4c55-4992-8835-0d578bb4e5c2
translation-type: tm+mt
source-git-commit: 776aaad0c063a870ef804d166292228f83575f48

---


# Capture des données d’impression de campagne via des appels de pixel{#capturing-campaign-impression-data-via-pixel-calls}

Une méthode d’envoi de données multimédias à Audience Manager utilise des macros de serveur d’annonces pour envoyer des attributs de campagne à Audience Manager.

Cette méthodologie est souvent appelée &quot;pixellisation du créatif&quot;. Ces points de données sont insérés dynamiquement dans le code de [!DNL Audience Manager] pixels par les macros du serveur d’annonces tiers, qui sont utilisées pour mapper et rapporter toutes les impressions et clics en fonction des attributs de rapports clés de la campagne. Les données agrégées offrent une vue unifiée des performances des campagnes, permettent d’identifier les chemins de conversion personnalisés et aident les clients à améliorer la séquence d’événements de serveur d’annonces qui conduisent à des conversions.

>[!IMPORTANT]
>
>Pour qu’Audience Manager interprète correctement les champs qu’il reçoit dans les appels d’événement et effectue le rendu de vos données de campagne dans les rapports [Optimisation de l’](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md)audience, vous devez envoyer des fichiers de métadonnées qui mappent ces champs à des valeurs lisibles par l’utilisateur. Voir [Présentation et mappages pour les fichiers](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) de métadonnées et contactez votre conseiller Audience Manager ou le service à la clientèle pour configurer un répertoire Amazon S3 pour les fichiers de métadonnées.

## Syntaxe des appels d’événement

>[!NOTE]
>
>Les styles de texte (`monospaced text`, *italiques*, crochets `[ ]` `( )`, etc.) identifient les éléments de code et les options. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../reference/code-style-elements.md).

L’appel d’un événement collecte les données d’impression et de conversion et les envoie aux [!DNL Audience Manager] [serveurs de collecte de données ](/help/using/reference/system-components/components-data-collection.md) ([!UICONTROL DCS]). Ce processus repose sur des serveurs d’annonces tiers qui placent l’appel dans le contenu créatif afin de contrôler le contenu inséré dans le code. Les serveurs d’annonces tiers (par exemple, [!DNL DFA]) peuvent placer ce code dans chaque impression publicitaire. En outre, un appel publicitaire n’utilise pas [!DNL JavaScript] ni n’emploie de techniques de « frame-busting » (destruction de cadres) pour accéder aux données d’éditeur en dehors de la balise publicitaire.

Les appels d’événement se composent de paires clé-valeur qui utilisent la syntaxe suivante :

```
http://clientname.demdex.net/event?d_event=imp&d_src=datasource_id&d_site=siteID&d_creative=<i>creative_id</i>&d_adgroup=<i>adgroup_id</i>&d_placement=<i>placement_id</i>&d_campaign=<i>campaign_id</i>[&d_cid=(GAID|IDFA)%01 DPUUID]&d_bust=cache buster value
```

Dans la paire clé-valeur, la variable valeur est un identifiant ou une macro inséré par le serveur d’annonces. Lorsque la balise publicitaire se charge, elle `%macro%` est remplacée par les valeurs correspondantes requises. Cet appel ne renvoie pas de réponse.

## Paires clés-valeurs prises en charge {#supported-key-value-pairs}

Les appels d’événement d’impression acceptent les données formées en paires clé-valeur. Le tableau suivant répertorie et décrit les clés utilisées pour contenir ces variables. La plupart d’entre eux sont nécessaires pour capturer et analyser des données dans les rapports [Optimisation de l’](../../reporting/audience-optimization-reports/audience-optimization-reports.md)audience.

<table id="table_F068C4D49F7D4775924D3CA712BF15BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Clé </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> d_adgroup </code> </td> 
   <td colname="col2"> <p>Identifiant du groupe publicitaire numérique à partir du serveur publicitaire. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_adsrc </code> </td> 
   <td colname="col2"> <p>ID de source de données ou code d’intégration pour votre annonceur. </p> <p>Requis pour les <span class="wintitle"> rapports Optimisation de l’audience </span> . </p> <p>Facultatif.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_bu </code> </td> 
   <td colname="col2"> <p>ID de source de données ou code d’intégration pour votre unité opérationnelle. </p> <p>Requis pour les <span class="wintitle"> rapports Optimisation de l’audience </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bust </code> </p> </td> 
   <td colname="col2"> <p>Valeur de blocage du cache. <span class="keyword"> Audience Manager envoie </span> automatiquement les en-têtes de contrôle du cache qui sont respectés par la plupart des navigateurs et des serveurs proxy. Si vous souhaitez exécuter une autre opération de contournement du cache, incluez ce paramètre dans un appel d’événement, suivi d’une chaîne aléatoire. </p> <p> Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_campaign </code> </td> 
   <td colname="col2"> <p>Identifiant de campagne numérique du serveur d’annonces. </p> <p>Requis pour les <span class="wintitle"> rapports Optimisation de l’audience </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>Dans ce contexte, <code> d_cid </code> instancie une paire clé-valeur qui vous permet d’associer un type de périphérique mobile à un ID utilisateur unique (DPUUID). Un ID fixe détermine le type de périphérique mobile. La valeur (ID utilisateur) peut varier. Séparez la paire clé-valeur par <code> %01 </code>, qui est un caractère de contrôle non imprimable. Ce paramètre accepte les clés suivantes : </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">2014 : Identifie un périphérique Android (GAID). Par exemple, <code> d_cid = 20914 %01 1234 </code> indique que l’utilisateur 1234 est associé à un périphérique Android. </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">2015 : Identifie un périphérique iOS (IDFA). Par exemple, <code> d_cid = 20915 %01 5678 </code> indique que l’utilisateur 5678 est associé à un périphérique iOS. </li> 
    </ul> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_creative </code> </td> 
   <td colname="col2"> <p>Identifiant créatif numérique du serveur d’annonces. </p> <p>Requis pour les <span class="wintitle"> rapports Optimisation de l’audience </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_event=imp </code> </td> 
   <td colname="col2"> <p>Identifie un appel d’événement en tant qu’événement d’impression. </p> <p>Obligatoire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_placement </code> </td> 
   <td colname="col2"> <p>Identifiant de placement numérique du serveur d’annonces. </p> <p> Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_site </code> </td> 
   <td colname="col2"> <p>Identifiant numérique du site à partir du serveur d’annonces. </p> <p>Requis pour les <span class="wintitle"> rapports Optimisation de l’audience </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_src </code> </td> 
   <td colname="col2"> <p>ID de source de données ou code d’intégration de la plateforme fournissant les métadonnées (par exemple, DFA, Atlas, GBM, Media Math, etc.). </p> <p>Requis pour les <span class="wintitle"> rapports Optimisation de l’audience </span> . </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code><i>gdpr</i></code>  </td> 
   <td colname="col2"> <p>En lien avec le <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">module externe Audience Manager pour IAB TCF.</a></p> <p><code>gdpr</code> peut être 0 (le RGMD ne s’applique pas) ou 1 (le RGMD s’applique).</p> <p>La valeur par défaut est 0.</p><p>Facultatif.</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_consent</code> </td> 
   <td colname="col2"> <p>En lien avec le <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">module externe Audience Manager pour IAB TCF.</a></p><p> Si <code>gdpr=1</code>, alors <code>%gdpr_consent%</code> est remplacé par la chaîne <code>gdpr_consent</code> (voir les <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external">spécifications IAB</a>).</p> <p>La valeur par défaut est 0.</p><p>Facultatif.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Veuillez contacter votre conseiller ou responsable de compte Adobe Audience Manager pour connaître l’URL exacte spécifique au domaine client.

>[!MORELIKETHIS]
>
>* [Fichiers de données et de métadonnées pour les rapports Optimisation de l’audience](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

