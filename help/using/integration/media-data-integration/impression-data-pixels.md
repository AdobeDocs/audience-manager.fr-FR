---
description: Une approche d'envoi de données de médias à Audience Manager utilise les macros de serveur d'annonces pour envoyer des attributs de campagne à Audience Manager.
seo-description: Une approche d'envoi de données de médias à Audience Manager utilise les macros de serveur d'annonces pour envoyer des attributs de campagne à Audience Manager.
seo-title: Capture des données d’impression de campagne via des appels de pixel
solution: Audience Manager
title: Capture des données d’impression de campagne via des appels de pixel
uuid: 6 ac 44100-4 c 55-4992-8835-0 d 578 bb 4 e 5 c 2
translation-type: tm+mt
source-git-commit: c79c2311c3ea76ce2450dc1b84a7a22b60a6edb7

---


# Capture des données d’impression de campagne via des appels de pixel{#capturing-campaign-impression-data-via-pixel-calls}

Une approche d'envoi de données de médias à Audience Manager utilise les macros de serveur d'annonces pour envoyer des attributs de campagne à Audience Manager.

On parle généralement de « pixellisation du créatif ».  » » Those data points are dynamically inserted into the [!DNL Audience Manager] pixel code by the third-party ad server macros, which are used to map and report all impressions and clicks based on the key reporting attributes of the campaign. Les données agrégées fournissent une vue unifiée des performances de la campagne, permettent d'identifier les chemins de conversion personnalisés et aident les clients à améliorer la séquence des événements de serveur publicitaire qui génèrent des conversions.

## Syntaxe d'appel d'événement

>[!NOTE]
>
>Les styles de texte (`monospaced text`, *italiques*, crochets `[ ]` `( )`, etc.) identifient les éléments de code et les options. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../reference/code-style-elements.md).

L’appel d’un événement collecte les données d’impression et de conversion et les envoie aux [!DNL Audience Manager] [serveurs de collecte de données ](/help/using/reference/system-components/components-data-collection.md) ([!UICONTROL DCS]). Ce processus repose sur des serveurs d’annonces tiers qui placent l’appel dans le contenu créatif afin de contrôler le contenu inséré dans le code. Les serveurs d’annonces tiers (par exemple, [!DNL DFA]) peuvent placer ce code dans chaque impression publicitaire. En outre, un appel publicitaire n’utilise pas [!DNL JavaScript] ni n’emploie de techniques de « frame-busting » (destruction de cadres) pour accéder aux données d’éditeur en dehors de la balise publicitaire.

Les appels d'événement consistent en des paires clé-valeur qui utilisent la syntaxe suivante :

<pre>
http://clientname.demdex.net/event?d_event=imp&amp;d_src=datasource_id&amp;d_site=siteID&amp;
d_creative=<i>creative_id</i>&amp;d_adgroup=<i>adgroup_id</i>&amp;d_placement=<i>placement_id</i>
&amp;d_campaign=<i>campaign_id</i>[&amp;d_cid=(GAID|IDFA)%01 DPUUID]&amp;d_bust=cache buster value
</pre>

Dans la paire clé-valeur, la variable value est un ID ou une macro inséré par le serveur d'annonces. When the ad tag loads, that `%macro%` gets replaced with the required, corresponding values. Cet appel ne renvoie pas de réponse.

## Supported Key-Value Pairs {#supported-key-value-pairs}

Les appels d'événement d'impression acceptent les données formées dans des paires clé-valeur. Le tableau suivant répertorie et décrit les clés utilisées pour les conserver. Many of these are required if you want to capture and analyze data in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_F068C4D49F7D4775924D3CA712BF15BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Clé </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> d_ adgroup </code> </td> 
   <td colname="col2"> <p>Identifiant de groupe publicitaire numérique à partir du serveur d'annonces. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ adsrc </code> </td> 
   <td colname="col2"> <p>ID ou code d'intégration de source de données pour votre annonceur. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ bu </code> </td> 
   <td colname="col2"> <p>ID ou code d'intégration de source de données pour votre unité opérationnelle. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ bust </code> </p> </td> 
   <td colname="col2"> <p>Valeur de la mémoire cache. <span class="keyword"> Audience Manager envoie </span> automatiquement les en-têtes de contrôle du cache qui sont respectés par la plupart des navigateurs et des doublures. Si vous souhaitez effectuer d'autres opérations de cache, incluez ce paramètre dans un appel d'événement suivi d'une chaîne aléatoire. </p> <p> Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ campaign </code> </td> 
   <td colname="col2"> <p>Identifiant de campagne numérique du serveur d'annonces. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>In this context, <code> d_cid </code> instantiates a key-value pair that lets you associate a mobile device type to a unique user ID (DPUUID). Un ID fixe détermine le type de périphérique mobile. La valeur, qui est l'utilisateur - id, peut varier. Separate the key-value pair with <code> %01 </code>, which is a non-printing control character. Ce paramètre accepte les clés suivantes : </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">20914 : Identifie un périphérique Android (GAID). For example, <code> d_cid = 20914 %01 1234 </code> says that user 1234 is associated with an Android device. </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">20915 : Identifie un périphérique ios (IDFA). For example, <code> d_cid = 20915 %01 5678 </code> says that user 5678 is associated with an iOS device. </li> 
    </ul> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ creative </code> </td> 
   <td colname="col2"> <p>Identifiant créatif numérique à partir du serveur d'annonces. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ event = imp </code> </td> 
   <td colname="col2"> <p>Identifie un appel d'événement comme événement d'impression. </p> <p>Obligatoire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ placement </code> </td> 
   <td colname="col2"> <p>Identifiant de placement numérique à partir du serveur d'annonces. </p> <p> Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ site </code> </td> 
   <td colname="col2"> <p>Identifiant de site numérique à partir du serveur d'annonces. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ src </code> </td> 
   <td colname="col2"> <p>ID ou code d'intégration de source de données de la plate-forme fournissant les métadonnées (DFA, Atlas, GBM, Media Math, etc.). </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code><i>gdpr</i></code>  </td> 
   <td colname="col2"> <p>En lien avec le <a href="../../overview/aam-gdpr/aam-iab-plugin.md">module externe Audience Manager pour IAB TCF.</a></p> <p><code>gdpr</code> peut être 0 (GDPR ne s'applique pas) ou 1 (GDPR s'applique).</p> <p>La valeur par défaut est 0.</p><p>Facultatif.</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_ permission</code> </td> 
   <td colname="col2"> <p>En lien avec le <a href="../../overview/aam-gdpr/aam-iab-plugin.md">module externe Audience Manager pour IAB TCF.</a></p><p> Si <code>gdpr=1</code>, alors <code>%gdpr_consent%</code> est remplacé par la chaîne <code>gdpr_consent</code> (voir les <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external">spécifications IAB</a>).</p> <p>La valeur par défaut est 0.</p><p>Facultatif.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Veuillez contacter vos consultants ou votre compte Adobe Audience Manager pour connaître l'URL exacte spécifique au domaine client.

>[!MORE_ LIKE_ THIS]
>
>* [Fichiers de données et de métadonnées pour les rapports Optimisation d'audience](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

