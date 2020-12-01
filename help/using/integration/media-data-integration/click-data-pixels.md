---
description: Le suivi des clics permet de mesurer l’engagement des visiteurs tout au long de la campagne, car il enregistre l’activité basée sur les clics pour les créatifs tiers.
seo-description: Le suivi des clics permet de mesurer l’engagement des visiteurs tout au long de la campagne, car il enregistre l’activité basée sur les clics pour les créatifs tiers.
seo-title: Capture des données de clics de campagne via des appels de pixel
solution: Audience Manager
title: Capture des données de clics de campagne via des appels de pixel
uuid: 7c3797f7-9674-493d-972b-38be0584fede
feature: Integration with Campaign
translation-type: tm+mt
source-git-commit: 231d8e537cf5b4f29b1c4f284fe1b3ffe6d187a9
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 11%

---


# Capture des données de clics de campagne via des appels de pixel {#capturing-campaign-click-data-via-pixel-calls}

Le suivi des clics permet de mesurer l’engagement des visiteurs tout au long de la campagne, car il enregistre l’activité basée sur les clics pour les créatifs tiers. Tout comme la [collection d’impressions](/help/using/integration/media-data-integration/impression-data-pixels.md), un appel de événement est envoyé aux serveurs de collecte de données [!DNL Audience Manager] ([!DNL DCS]) pour traitement. Le visiteur est ensuite redirigé vers l’adresse Web prévue.

>[!NOTE]
>
>Veuillez contacter votre [!DNL Audience Manager] consultant ou responsable de compte pour connaître le [!DNL URL] exact spécifique au domaine client.

## Exigences

Les appels de suivi des clics nécessitent les paramètres suivants :

* `d_event=click`: paire clé-valeur qui identifie un appel de événement comme un événement de clic.
* `d_rd=redirect URL`: Paire clé-valeur contenant une redirection codée en doublon  [!DNL URL]. Si vous utilisez un outil de codage en ligne, exécutez la chaîne via l’encodeur, puis codez de nouveau le résultat, afin que la redirection fonctionne.

En outre, l’appel peut contenir des paires clé-valeur qui peuvent être utilisées pour la qualification des caractéristiques ou pour fournir des données et des métadonnées pour d’autres rapports.

## Exemple de demande

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## Réponse

La réponse redirige le navigateur vers le [!DNL URL] spécifié dans le paramètre `d_rd`. La chaîne de réponse peut inclure des valeurs générées par l’une des macros prises en charge répertoriées ci-dessous.

En fonction de l’exemple ci-dessus, le navigateur est redirigé vers le [!DNL URL] suivant :

`https://adobe.com/callback?creative=123`

## Macros prises en charge

Cliquez sur événements pour prendre en charge les macros répertoriées dans le tableau suivant. Une macro est une petite unité de code autonome qui s’active lorsque la balise publicitaire se charge pour le suivi des campagnes et des utilisateurs. Les macros seront transmises avec la destination [!DNL URL], à condition d’être marquées au format suivant : `%macro%`. Certaines clés n’ont pas de macros et acceptent plutôt une valeur d’identifiant codée en dur. Les clés qui acceptent les valeurs codées en dur sont nécessaires pour analyser les données dans les [rapports d&#39;Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_6EB65C3B7D0E49C59AA6C932549E33FC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Clé </th> 
   <th colname="col02" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_adgroup</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_adgroup%</code> </p> </td> 
   <td colname="col2"> <p>Identifiant du groupe publicitaire numérique du serveur d’annonces. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col02"> <p>Aucune macro. </p> <p>Accepte une valeur d’ID codée en dur. </p> </td> 
   <td colname="col2"> <p>Identifiant publicitaire.</p> <p>Code d’intégration de la source de données de l’annonceur. Notez que ceci n’est pas lié aux sources de données d’Audience Manager.</p> <p> Requis pour les rapports <span class="wintitle"> Audience Optimization</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>ID numérique de l'unité opérationnelle. </p> <p> Requis pour les rapports <span class="wintitle"> Audience Optimization</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>Identifiant de campagne numérique du serveur d’annonces. </p> <p> Requis pour les rapports <span class="wintitle"> Audience Optimization</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>Identifiant créatif numérique du serveur d’annonces. </p> <p>Obligatoire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_id%</code> </p> </td> 
   <td colname="col2"> <p>ID du fournisseur de données. </p> <p>Souvent utilisée avec <code> d_dpuuid</code> pour lier un ID de fournisseur de données à un ID d’utilisateur. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_dpuuid%</code> </p> </td> 
   <td colname="col2"> <p>ID utilisateur unique fourni par le fournisseur de données. </p> <p>Souvent utilisé avec <code> d_dpid</code> pour lier un ID d’utilisateur à un ID de fournisseur de données. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"></span> Experience Cloud ID (ECID). Pour plus d’informations sur l’ECID, voir les <a href="https://docs.adobe.com/content/help/fr-FR/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies et l’ID d’Experience Cloud</a>. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>Identifiant de placement numérique du serveur d’annonces. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>ID de région numérique de la grappe DCS qui traite une requête. Pour plus d’informations sur le serveur de collecte de données, voir <a href="../../reference/system-components/components-data-collection.md"> Data Collection Components</a>. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_rand</code> </p> </td> 
   <td colname="col02"> <p> <code> %r_rand%</code> </p> </td> 
   <td colname="col2"> <p>Nombre aléatoire utilisé pour brouiller le cache. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_site</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_site%</code> </p> </td> 
   <td colname="col2"> <p>Identifiant de site numérique du serveur d’annonces. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_src%</code> </p> </td> 
   <td colname="col2"> <p>DPID de la source d’où l’Audience Manager extrait les métadonnées. </p> <p>Obligatoire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_uuid%</code> </p> </td> 
   <td colname="col2"> <p>Indiquez l’identifiant du visiteur directement dans l’URL au lieu de dépendre du cookie Demdex. </p> <p>Facultatif. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr}</code> </p> </td> 
   <td colname="col2"> <p>En lien avec le <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">module externe Audience Manager pour IAB TCF.</a> </p><p><code>gdpr</code> peut être 0 (le RGPD ne s'applique pas) ou 1 (le RGPD s'applique).</p> <p>La valeur par défaut est 0.</p><p>Facultatif.</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consent</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr_consent_XXXX}</code> </p> </td> 
   <td colname="col2"> <p>En lien avec le <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">module externe Audience Manager pour IAB TCF.</a></p><p> Si <code>gdpr=1</code>, <code>${gdpr_consent_XXXX}</code> est remplacé par la chaîne <code>gdpr_consent</code> et l'identifiant du fournisseur (voir <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> spécification IAB</a>).</p> <p>La valeur par défaut est 0.</p><p>Facultatif.</p></td> 
  </tr> 
 </tbody> 
</table>

## Exemple de macros

Cet exemple montre comment transmettre les macros de création, de groupe publicitaire et de placement. Il suppose que les valeurs de chaque paramètre sont transmises dans la partie non redirection de l’appel de suivi des clics.

<ul class="simplelist"> 
 <li> <code> creative=1235 </code> </li> 
 <li> <code> campaign=4709 </code> </li> 
 <li> <code> adgroup=3408 </code> </li> 
 <li> <code> placement=1001 </code> </li> 
 <li> <code> src=203 </code> </li> 
</ul>

## Demande

```
https://client.demdex.net/event?d_event=click&d_creative=1235&d_src=203&d_campaign=4709&d_adgroup=3408&d_placement=1001&
d_rd%3Dhttp%253A%252F%252Fadobe.com%252Fcallback%253Fcreative%253D%2525d_creative%2525%2526campaign%253D%2525d_campaign%2525%2526adgroup%253D%2525%0Ad_adgroup%2525%2526d_placement%253D%2525placement%2525%2526src%253D%2525d_src%2525
```

## Réponse

En fonction de l’exemple ci-dessus, le navigateur est redirigé vers le [!DNL URL] suivant :

`https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`

## Fonctionnalités supplémentaires - [!UICONTROL Audience Optimization Reports]

Vous pouvez utiliser des appels de pixels pour alimenter les [rapports d&#39;Audience Optimization](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md). Voir [Présentation et mappages des fichiers de métadonnées](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) si vous souhaitez utiliser des pixels pour alimenter les rapports.


>[!MORELIKETHIS]
>
>* [Fichiers de données et de métadonnées pour les rapports d’Audience Optimization](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

