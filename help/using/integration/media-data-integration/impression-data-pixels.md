---
description: L’une des méthodes d’envoi de données multimédias à l’Audience Manager utilise des macros de serveur publicitaire pour envoyer des attributs de campagne à l’Audience Manager.
seo-description: L’une des méthodes d’envoi de données multimédias à l’Audience Manager utilise des macros de serveur publicitaire pour envoyer des attributs de campagne à l’Audience Manager.
seo-title: Capture des données d’impression de campagne via des appels de pixel
solution: Audience Manager
title: Capture des données d’impression de campagne via des appels de pixel
uuid: 6ac44100-4c55-4992-8835-0d578bb4e5c2
feature: Integration with Campaign
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 20%

---


# Capture des données d’impression de campagne via des appels de pixel{#capturing-campaign-impression-data-via-pixel-calls}

L’une des méthodes d’envoi de données multimédias à l’Audience Manager utilise des macros de serveur publicitaire pour envoyer des attributs de campagne à l’Audience Manager.

Cette méthodologie est souvent appelée &quot;pixellisation de la création&quot;. Ces points de données sont insérés dynamiquement dans le code de [!DNL Audience Manager] pixel par les macros du serveur publicitaire tiers, qui sont utilisées pour mapper et rapporter toutes les impressions et clics en fonction des attributs de rapports clés de la campagne. Les données agrégées fournissent une vue unifiée des performances des campagnes, aident à identifier les chemins de conversion personnalisés et aident les clients à améliorer la séquence de événements de serveur d’annonces qui conduisent à des conversions.

## Syntaxe des appels de Événement

>[!NOTE]
>
>Les styles de texte (`monospaced text`, *italiques*, crochets `[ ]` `( )`, etc.) identifient les éléments de code et les options. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../reference/code-style-elements.md).

L’appel d’un événement collecte les données d’impression et de conversion et les envoie aux [!DNL Audience Manager] [serveurs de collecte de données ](/help/using/reference/system-components/components-data-collection.md) ([!DNL DCS]). Ce processus repose sur des serveurs d’annonces tiers qui placent l’appel dans le contenu créatif afin de contrôler le contenu inséré dans le code. Les serveurs d’annonces tiers (par exemple, [!DNL DFA]) peuvent placer ce code dans chaque impression publicitaire. En outre, un appel publicitaire n’utilise pas [!DNL JavaScript] ni n’emploie de techniques de « frame-busting » (destruction de cadres) pour accéder aux données d’éditeur en dehors de la balise publicitaire.

Les appels de Événement se composent de paires clé-valeur qui utilisent la syntaxe suivante :

```
http://clientname.demdex.net/event?d_event=imp&d_src=datasource_id&d_site=siteID&d_creative=<i>creative_id</i>&d_adgroup=<i>adgroup_id</i>&d_placement=<i>placement_id</i>&d_campaign=<i>campaign_id</i>[&d_cid=(GAID|IDFA)%01 DPUUID]&d_bust=cache buster value
```

Dans la paire clé-valeur, la variable valeur est un identifiant ou une macro inséré par le serveur d’annonces. Au chargement de la balise publicitaire, celle-ci `%macro%` est remplacée par les valeurs correspondantes requises. Cet appel ne renvoie pas de réponse.

## Paires clé-valeur prises en charge {#supported-key-value-pairs}

Les appels de événement d’impression acceptent les données formées en paires clé-valeur. Le tableau suivant liste et décrit les clés utilisées pour contenir ces variables. La plupart d&#39;entre eux sont nécessaires pour capturer et analyser des données dans les rapports [Optimisation des](../../reporting/audience-optimization-reports/audience-optimization-reports.md)Audiences.

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
   <td colname="col2"> <p>Identifiant du groupe publicitaire numérique du serveur d’annonces. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_adsrc </code> </td> 
   <td colname="col2"> <p>ID de source de données ou code d’intégration pour votre annonceur. </p> <p>Requis pour les <span class="wintitle"> rapports Optimisation des </span> Audiences. </p> <p>Facultatif.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_bu </code> </td> 
   <td colname="col2"> <p>ID de source de données ou code d’intégration pour votre unité opérationnelle. </p> <p>Requis pour les <span class="wintitle"> rapports Optimisation des </span> Audiences. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bust </code> </p> </td> 
   <td colname="col2"> <p>Valeur de blocage du cache. <span class="keyword"> L’Audience Manager </span> envoie automatiquement des en-têtes de contrôle du cache qui sont respectés par la plupart des navigateurs et des serveurs proxy. Si vous souhaitez exécuter une autre opération de contournement du cache, incluez ce paramètre dans un appel de événement, suivi d’une chaîne aléatoire. </p> <p> Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_campaign </code> </td> 
   <td colname="col2"> <p>Identifiant de campagne numérique du serveur d’annonces. </p> <p>Requis pour les <span class="wintitle"> rapports Optimisation des </span> Audiences. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>Dans ce contexte, <code> d_cid </code> instancie une paire clé-valeur qui vous permet d’associer un type de périphérique mobile à un ID utilisateur unique (DPUUID). Un ID fixe détermine le type de périphérique mobile. La valeur, qui correspond à l’ID utilisateur, peut varier. Séparez la paire clé-valeur par <code> %01 </code>, qui est un caractère de contrôle non imprimable. Ce paramètre accepte les clés suivantes : </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">20914 : Identifie un périphérique Android (GAID). Par exemple, <code> d_cid = 20914 %01 1234 </code> indique que l’utilisateur 1234 est associé à un périphérique Android. </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">20915 : Identifie un périphérique iOS (IDFA). Par exemple, <code> d_cid = 20915 %01 5678 </code> indique que l’utilisateur 5678 est associé à un périphérique iOS. </li> 
    </ul> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_creative </code> </td> 
   <td colname="col2"> <p>Identifiant créatif numérique du serveur d’annonces. </p> <p>Requis pour les <span class="wintitle"> rapports Optimisation des </span> Audiences. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_event=imp </code> </td> 
   <td colname="col2"> <p>Identifie un appel de événement en tant que événement d’impression. </p> <p>Obligatoire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_placement </code> </td> 
   <td colname="col2"> <p>Identifiant de placement numérique du serveur d’annonces. </p> <p> Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_site </code> </td> 
   <td colname="col2"> <p>Identifiant de site numérique du serveur d’annonces. </p> <p>Requis pour les <span class="wintitle"> rapports Optimisation des </span> Audiences. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_src </code> </td> 
   <td colname="col2"> <p>ID de source de données ou code d’intégration de la plateforme fournissant les métadonnées (par exemple, DFA, Atlas, GBM, Media Math, etc.). </p> <p>Requis pour les <span class="wintitle"> rapports Optimisation des </span> Audiences. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code>gdpr</code>  </td> 
   <td colname="col2"> <p>En lien avec le <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">module externe Audience Manager pour IAB TCF.</a></p> <p><code>gdpr</code> peut être 0 (le RGPD ne s'applique pas) ou 1 (le RGPD s'applique).</p> <p>La valeur par défaut est 0.</p><p>Facultatif.</p><p>Si <code>gdpr=1</code>le paramètre <code>gdpr_consent</code> doit contenir le paramètre de consentement TC de l'IAB pour traiter les données avec succès. Sinon, toutes les données seront ignorées.</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_consent</code> </td> 
   <td colname="col2"> <p>En lien avec le <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">module externe Audience Manager pour IAB TCF.</a></p><p> Si <code>gdpr=1</code>vous le souhaitez, <code>${gdpr_consent_XXXX}</code> est remplacé par la <code>gdpr_consent</code> chaîne et l’identifiant du fournisseur (voir la spécification <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"></a>IAB).</p> <p>La valeur par défaut est 0.</p><p>Facultatif.</p></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Veuillez contacter votre conseiller d&#39;Adobe Audience Manager ou votre responsable de compte pour connaître l&#39;URL exacte propre au domaine client.

## Autres fonctionnalités - [!DNL Audience Optimization Reports] {#additional-functionality-aor}

Vous pouvez utiliser des appels en pixels pour alimenter les rapports [Optimisation des](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md)Audiences. Voir [Aperçu et mappages des fichiers](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) de métadonnées si vous souhaitez utiliser des pixels pour alimenter les rapports.

>[!MORELIKETHIS]
>
>* [Fichiers de données et de métadonnées pour les rapports d’optimisation d’Audience](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

