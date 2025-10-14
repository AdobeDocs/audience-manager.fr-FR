---
description: Une approche pour l’envoi de données multimédia à Audience Manager utilise des macros de serveur de publicités pour envoyer des attributs de campagne à Audience Manager.
seo-description: One approach for sending media data to Audience Manager uses ad server macros to send campaign attributes to Audience Manager.
seo-title: Capturing Campaign Impression Data via Pixel Calls
solution: Audience Manager
title: Capture de données d’impression de campagne par le biais d’appels de pixels
uuid: 6ac44100-4c55-4992-8835-0d578bb4e5c2
feature: Adobe Campaign Integration
exl-id: 04e6f1e5-5075-4221-a310-deb3717458ad
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 14%

---

# Capture de données d’impression de campagne par le biais d’appels de pixels{#capturing-campaign-impression-data-via-pixel-calls}

Une approche pour l’envoi de données multimédia à Audience Manager utilise des macros de serveur de publicités pour envoyer des attributs de campagne à Audience Manager.

Cette méthodologie est souvent appelée « pixellisation de la création ». Ces points de données sont insérés dynamiquement dans le code en pixels [!DNL Audience Manager] par les macros des serveurs de publicités tiers, qui sont utilisées pour mapper et générer des rapports sur toutes les impressions et tous les clics en fonction des attributs de rapports clés de la campagne. Les données agrégées fournissent une vue unifiée des performances de la campagne, permettent d’identifier les chemins de conversion personnalisés et aident les clients à améliorer la séquence des événements du serveur de publicités qui conduisent aux conversions.

## Syntaxe de l’appel d’événement

>[!NOTE]
>
>Les styles de texte (`monospaced text`, *italique*, crochets `[ ]` `( )`, etc.) indiquent les éléments de code et les options. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../reference/code-style-elements.md).

L’appel d’événement collecte les données d’impression et de conversion et les envoie aux [!DNL Audience Manager] [serveurs de collecte de données](/help/using/reference/system-components/components-data-collection.md) ([!DNL DCS]). Ce processus repose sur des serveurs d’annonces tiers qui placent l’appel dans le contenu créatif afin de contrôler le contenu inséré dans le code. Les serveurs d’annonces tiers (par exemple, [!DNL DFA]) peuvent placer ce code dans chaque impression publicitaire. En outre, un appel publicitaire n’utilise pas [!DNL JavaScript] ni n’emploie de techniques de « frame-busting » (destruction de cadres) pour accéder aux données d’éditeur en dehors de la balise publicitaire.

Les appels d’événement se composent de paires clé-valeur qui utilisent la syntaxe suivante :

```
https://clientname.demdex.net/event?d_event=imp&d_src=datasource_id&d_site=siteID&d_creative=<i>creative_id</i>&d_adgroup=<i>adgroup_id</i>&d_placement=<i>placement_id</i>&d_campaign=<i>campaign_id</i>[&d_cid=(GAID|IDFA)%01 DPUUID]&d_bust=cache buster value
```

Dans la paire clé-valeur, la variable valeur est un identifiant ou une macro inséré par le serveur de publicités. Lorsque la balise d’annonce publicitaire se charge, cette `%macro%` est remplacée par les valeurs correspondantes requises. Cet appel ne renvoie pas de réponse.

## Paires Clé-Valeur Prises En Charge {#supported-key-value-pairs}

Les appels d’événements d’impression acceptent les données formées en paires clé-valeur. Le tableau suivant répertorie et décrit les clés utilisées pour contenir ces variables. La plupart de ces éléments sont nécessaires si vous souhaitez capturer et analyser des données dans les [rapports Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

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
   <td colname="col2"> <p>ID de groupe publicitaire numérique du serveur de publicités. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_adsrc </code> </td> 
   <td colname="col2"> <p>Identifiant de source de données ou code d’intégration pour votre annonceur. </p> <p>Obligatoire pour les rapports <span class="wintitle"> Audience Optimization </span>. </p> <p>Facultatif.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_bu </code> </td> 
   <td colname="col2"> <p>Identifiant de source de données ou code d’intégration de votre unité opérationnelle. </p> <p>Obligatoire pour les rapports <span class="wintitle"> Audience Optimization </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bust </code> </p> </td> 
   <td colname="col2"> <p>Valeur de démantèlement du cache. <span class="keyword">’</span> Audience Manager envoie automatiquement les en-têtes de contrôle du cache qui sont respectés par la plupart des navigateurs et des proxys. Si vous souhaitez effectuer un contournement supplémentaire du cache, incluez ce paramètre dans un appel d’événement, suivi d’une chaîne aléatoire. </p> <p> Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_campaign </code> </td> 
   <td colname="col2"> <p>Identifiant de campagne numérique du serveur de publicités. </p> <p>Obligatoire pour les rapports <span class="wintitle"> Audience Optimization </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>Dans ce contexte, <code> d_cid </code> instancie une paire clé-valeur qui vous permet d’associer un type d’appareil mobile à un ID utilisateur unique (DPUUID). Un identifiant fixe détermine le type d’appareil mobile. La valeur, qui correspond à l’ID utilisateur, peut varier. Séparez la paire clé-valeur par <code> %01 </code>, qui est un caractère de contrôle non imprimable. Ce paramètre accepte les clés suivantes : </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">20914 : identifie un appareil Android (GAID). Par exemple, <code> d_cid = 20914 %01 1234 </code> indique que l’utilisateur 1234 est associé à un appareil Android. </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">20915 : identifie un appareil iOS (IDFA). Par exemple, <code> d_cid = 20915 %01 5678 </code> indique que l’utilisateur 5678 est associé à un appareil iOS. </li> 
    </ul> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_creative </code> </td> 
   <td colname="col2"> <p>Identifiant créatif numérique du serveur de publicités. </p> <p>Obligatoire pour les rapports <span class="wintitle"> Audience Optimization </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_event=imp </code> </td> 
   <td colname="col2"> <p>Identifie un appel d’événement en tant qu’événement d’impression. </p> <p>Obligatoire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_placement </code> </td> 
   <td colname="col2"> <p>Identifiant d’emplacement numérique du serveur de publicités. </p> <p> Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_site </code> </td> 
   <td colname="col2"> <p>Identifiant numérique du site à partir du serveur de publicités. </p> <p>Obligatoire pour les rapports <span class="wintitle"> Audience Optimization </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_src </code> </td> 
   <td colname="col2"> <p>Identifiant de la source de données ou code d’intégration de la plateforme fournissant les métadonnées (par exemple, DFA, Atlas, GBM, Media Math, etc.). </p> <p>Obligatoire pour les rapports <span class="wintitle"> Audience Optimization </span>. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code>gdpr</code>  </td> 
   <td colname="col2"> <p>En lien avec le <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">module externe Audience Manager pour IAB TCF.</a></p> <p><code>gdpr</code> peut être 0 (le RGPD ne s’applique pas) ou 1 (le RGPD s’applique).</p> <p>La valeur par défaut est 0.</p><p>Facultatif.</p><p>Si <code>gdpr=1</code>, le paramètre <code>gdpr_consent</code> doit contenir le paramètre de consentement IAB TC pour traiter les données avec succès. Dans le cas contraire, toutes les données seront ignorées.</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_consent</code> </td> 
   <td colname="col2"> <p>En lien avec le <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">module externe Audience Manager pour IAB TCF.</a></p><p> Si <code>gdpr=1</code>, <code>${gdpr_consent_XXXX}</code> est remplacé par la chaîne <code>gdpr_consent</code> et l’ID fournisseur (voir Spécification <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external">’IAB</a>).</p> <p>La valeur par défaut est 0.</p><p>Facultatif.</p></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Veuillez contacter votre consultant Adobe Audience Manager ou votre responsable de compte pour obtenir l’URL exacte spécifique au domaine client.

## Fonctionnalités supplémentaires - [!DNL Audience Optimization Reports] {#additional-functionality-aor}

Vous pouvez utiliser des appels de pixels pour alimenter les [rapports Audience Optimization](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md). Consultez [&#x200B; Présentation et mappages des fichiers de métadonnées &#x200B;](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) si vous souhaitez utiliser des pixels pour alimenter les rapports.

>[!MORELIKETHIS]
>
>* [Fichiers de données et de métadonnées pour les rapports Audience Optimization](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)
