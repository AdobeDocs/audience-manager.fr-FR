---
description: Le suivi des clics permet de mesurer l’engagement des visiteurs tout au long de votre campagne, car il enregistre l’activité basée sur les clics pour les contenus publicitaires tiers.
seo-description: Click tracking enables measurement of visitor engagement throughout your campaign, as it records click-based activity for third-party creatives.
seo-title: Capturing Campaign Click Data via Pixel Calls
solution: Audience Manager
title: Capture des données de clics Campaign via des appels de pixels
uuid: 7c3797f7-9674-493d-972b-38be0584fede
feature: Adobe Campaign Integration
exl-id: 41b169bf-3727-4ed7-b74f-fea75244d2cb
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 6%

---

# Capture des données de clics Campaign via des appels de pixels {#capturing-campaign-click-data-via-pixel-calls}

Le suivi des clics permet de mesurer l’engagement des visiteurs tout au long de votre campagne, car il enregistre l’activité basée sur les clics pour les contenus publicitaires tiers. Tout comme pour la [collecte d’impressions](/help/using/integration/media-data-integration/impression-data-pixels.md), un appel d’événement est envoyé aux serveurs de collecte de données [!DNL Audience Manager] ([!DNL DCS]) pour traitement. Le visiteur est ensuite redirigé vers l’adresse web prévue.

>[!NOTE]
>
>Veuillez contacter votre consultant [!DNL Audience Manager] ou votre responsable de compte pour obtenir les [!DNL URL] exactes spécifiques au domaine client.

## Exigences

Les appels de suivi des clics nécessitent les paramètres suivants :

* `d_event=click` : paire clé-valeur qui identifie un appel d’événement comme un événement de clic.
* `d_rd=redirect URL` : paire clé-valeur contenant un [!DNL URL] de redirection codé en double. Si vous utilisez un outil d’encodage en ligne, exécutez la chaîne à travers l’encodeur, puis codez à nouveau le résultat, pour que la redirection fonctionne.

En outre, l’appel peut contenir des paires clé-valeur qui peuvent être utilisées pour la qualification de caractéristique ou pour fournir des données et des métadonnées pour d’autres rapports.

## Exemple de requête

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## Réponse

La réponse redirige le navigateur vers la [!DNL URL] spécifiée dans le paramètre `d_rd` . La chaîne de réponse peut inclure des valeurs générées par l’une des macros prises en charge répertoriées ci-dessous.

En fonction de l’exemple ci-dessus, le navigateur est redirigé vers le [!DNL URL] suivant :

`https://adobe.com/callback?creative=123`

## Macros prises en charge

Les événements Click prennent en charge les macros répertoriées dans le tableau suivant. Une macro est une petite unité de code autonome qui s’active lors du chargement de la balise publicitaire pour le suivi de la campagne et des utilisateurs. Les macros sont transmises avec les [!DNL URL] de destination, à condition qu’elles soient marquées avec le format suivant : `%macro%`. Certaines clés ne comportent pas de macros et acceptent plutôt une valeur d’identifiant codée en dur. Les clés qui acceptent des valeurs codées en dur sont requises si vous souhaitez analyser les données dans les [rapports Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

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
   <td colname="col2"> <p>ID de groupe publicitaire numérique du serveur de publicités. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col02"> <p>Pas de macro. </p> <p>Accepte une valeur d’identifiant codée en dur. </p> </td> 
   <td colname="col2"> <p>ID publicitaire.</p> <p>Code d’intégration de la source de données de l’annonceur. Notez que cela n’est pas lié aux sources de données Audience Manager.</p> <p> Obligatoire pour <span class="wintitle"> rapports Audience Optimization</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>Identifiant numérique de l'unité opérationnelle. </p> <p> Obligatoire pour <span class="wintitle"> rapports Audience Optimization</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>Identifiant de campagne numérique du serveur de publicités. </p> <p> Obligatoire pour <span class="wintitle"> rapports Audience Optimization</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>Identifiant créatif numérique du serveur de publicités. </p> <p>Obligatoire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_id%</code> </p> </td> 
   <td colname="col2"> <p>Identifiant du fournisseur de données. </p> <p>Souvent utilisé avec <code> d_dpuuid</code> pour lier un ID de fournisseur de données à un ID d’utilisateur. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_dpuuid%</code> </p> </td> 
   <td colname="col2"> <p>ID d’utilisateur unique fourni par le fournisseur de données. </p> <p>Souvent utilisé avec <code> d_dpid</code> pour lier un ID utilisateur à un ID de fournisseur de données. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Experience Cloud</span> ID (ECID). Pour plus d’informations sur l’ECID, voir Cookies <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=fr" format="https" scope="external"> et Experience Cloud ID </a>. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>Identifiant d’emplacement numérique du serveur de publicités. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>Identifiant de région numérique pour le cluster DCS qui traite une requête. Pour plus d’informations sur le serveur de collecte de données, voir <a href="../../reference/system-components/components-data-collection.md"> des composants de collecte de données</a>. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_rand</code> </p> </td> 
   <td colname="col02"> <p> <code> %r_rand%</code> </p> </td> 
   <td colname="col2"> <p>Nombre aléatoire utilisé pour le démantèlement du cache. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_site</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_site%</code> </p> </td> 
   <td colname="col2"> <p>Identifiant numérique du site à partir du serveur de publicités. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_src%</code> </p> </td> 
   <td colname="col2"> <p>DPID de la source à partir de laquelle Audience Manager extrait les métadonnées. </p> <p>Obligatoire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_uuid%</code> </p> </td> 
   <td colname="col2"> <p>Indiquez l’identifiant du visiteur directement dans l’URL au lieu de faire appel au cookie Demdex. </p> <p>Facultatif. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr}</code> </p> </td> 
   <td colname="col2"> <p>En lien avec le <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">module externe Audience Manager pour IAB TCF.</a> </p><p><code>gdpr</code> peut être 0 (le RGPD ne s’applique pas) ou 1 (le RGPD s’applique).</p> <p>La valeur par défaut est 0.</p><p>Facultatif.</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consent</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr_consent_XXXX}</code> </p> </td> 
   <td colname="col2"> <p>En lien avec le <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">module externe Audience Manager pour IAB TCF.</a></p><p> Si <code>gdpr=1</code>, <code>${gdpr_consent_XXXX}</code> est remplacé par la chaîne <code>gdpr_consent</code> et l’ID fournisseur (voir Spécification <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external">’IAB</a>).</p> <p>La valeur par défaut est 0.</p><p>Facultatif.</p></td> 
  </tr> 
 </tbody> 
</table>

## Exemple de macros

Cet exemple illustre la transmission des macros creative, adgroup et placement. Il suppose que les valeurs de chaque paramètre sont transmises dans la partie sans redirection de l’appel de suivi des clics.

<ul class="simplelist"> 
 <li> <code> creative=1235 </code> </li> 
 <li> <code> campaign=4709 </code> </li> 
 <li> <code> adgroup=3408 </code> </li> 
 <li> <code> placement=1001 </code> </li> 
 <li> <code> src=203 </code> </li> 
</ul>

## Requête

```
https://client.demdex.net/event?d_event=click&d_creative=1235&d_src=203&d_campaign=4709&d_adgroup=3408&d_placement=1001&
d_rd%3Dhttp%253A%252F%252Fadobe.com%252Fcallback%253Fcreative%253D%2525d_creative%2525%2526campaign%253D%2525d_campaign%2525%2526adgroup%253D%2525%0Ad_adgroup%2525%2526d_placement%253D%2525placement%2525%2526src%253D%2525d_src%2525
```

## Réponse

En fonction de l’exemple ci-dessus, le navigateur est redirigé vers le [!DNL URL] suivant :

`https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`

## Fonctionnalités supplémentaires - [!UICONTROL Audience Optimization Reports]

Vous pouvez utiliser des appels de pixels pour alimenter les [rapports Audience Optimization](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md). Consultez [ Présentation et mappages des fichiers de métadonnées ](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) si vous souhaitez utiliser des pixels pour alimenter les rapports.


>[!MORELIKETHIS]
>
>* [Fichiers de données et de métadonnées pour les rapports Audience Optimization](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)
