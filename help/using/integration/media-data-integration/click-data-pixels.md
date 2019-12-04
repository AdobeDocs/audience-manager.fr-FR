---
description: valeur nulle
seo-description: valeur nulle
seo-title: Capture des données des clics sur les campagnes par appels de pixels
solution: Audience Manager
title: Capture des données des clics sur les campagnes par appels de pixels
uuid: 7c3797f7-9674-493d-972b-38be0584fede
translation-type: tm+mt
source-git-commit: 8d31bc79fd221cffd33969278eade93a4b32a4d5

---


# Capturing Campaign Click Data via Pixel Calls {#capturing-campaign-click-data-via-pixel-calls}

Le suivi des clics permet de mesurer l’engagement des visiteurs tout au long de votre campagne, car il enregistre l’activité basée sur les clics pour les créatifs tiers. Comme pour la collecte des impressions, un appel d’événement est envoyé aux serveurs de collecte de données ([!UICONTROL DCS]) d’Audience Manager pour traitement. Le visiteur est ensuite redirigé vers l’adresse Web prévue.

## Conditions

Les appels de suivi des clics nécessitent les paramètres suivants :

* `d_event=click`: Paire clé-valeur qui identifie un appel d’événement en tant qu’événement de clic.
* `d_rd=redirect URL`: Paire clé-valeur contenant une redirection codée en double [!DNL URL]. Si vous utilisez un outil de codage en ligne, exécutez la chaîne à travers l’encodeur, puis codez de nouveau le résultat, afin que la redirection fonctionne.

En outre, l’appel peut contenir des paires clé-valeur qui peuvent être utilisées pour la qualification des caractéristiques ou pour fournir des données et des métadonnées pour d’autres rapports.

## Exemple de demande

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## Réponse

La réponse redirige le navigateur vers la [!DNL URL] valeur spécifiée dans le `d_rd` paramètre. La chaîne de réponse peut inclure des valeurs générées par l’une des macros prises en charge répertoriées ci-dessous.

Selon l’exemple ci-dessus, le navigateur est redirigé vers ce qui suit [!DNL URL]:

[!DNL `https://adobe.com/callback?creative=123`]

## Macros prises en charge

Les événements de clic prennent en charge les macros répertoriées dans le tableau suivant. Une macro est une petite unité de code autonome qui s’active lorsque la balise publicitaire se charge pour le suivi des campagnes et des utilisateurs. Les macros sont transmises avec la destination [!DNL URL], à condition qu’elles soient marquées du format suivant : `%macro%`. Certaines clés n’ont pas de macros et acceptent plutôt une valeur d’ID codée en dur. Les clés qui acceptent les valeurs codées en dur sont requises si vous souhaitez analyser les données dans les rapports [Optimisation de l’](../../reporting/audience-optimization-reports/audience-optimization-reports.md)audience.

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
   <td colname="col2"> <p>Identifiant du groupe publicitaire numérique à partir du serveur publicitaire. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col02"> <p>Aucune macro. </p> <p>Accepte une valeur d’ID codée en dur. </p> </td> 
   <td colname="col2"> <p>Identifiant publicitaire.</p> <p>Code d’intégration de la source de données de l’annonceur. Notez que ceci n’est pas lié aux sources de données Audience Manager.</p> <p> Requis pour les rapports Optimisation <span class="wintitle"> de l’</span> audience. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>ID numérique de l'unité opérationnelle. </p> <p> Requis pour les rapports Optimisation <span class="wintitle"> de l’</span> audience. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>Identifiant de campagne numérique du serveur d’annonces. </p> <p> Requis pour les rapports Optimisation <span class="wintitle"> de l’</span> audience. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>Identifiant créatif numérique du serveur d’annonces. </p> <p>Obligatoire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_id%</code> </p> </td> 
   <td colname="col2"> <p>ID du fournisseur de données. </p> <p>Souvent utilisé pour <code> d_dpuuid</code> lier un ID de fournisseur de données à un ID d’utilisateur. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_dpuuid%</code> </p> </td> 
   <td colname="col2"> <p>ID utilisateur unique fourni par le fournisseur de données. </p> <p>Souvent utilisé pour lier <code> d_dpid</code> un ID d’utilisateur à un ID de fournisseur de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Experience Cloud ID (ECID). </span> For more information about the ECID, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>Identifiant de placement numérique du serveur d’annonces. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>ID de région numérique de la grappe DCS qui traite une requête. Pour plus d’informations sur le serveur de collecte de données, voir Composants <a href="../../reference/system-components/components-data-collection.md"></a>de collecte de données. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_rand</code> </p> </td> 
   <td colname="col02"> <p> <code> %r_rand%</code> </p> </td> 
   <td colname="col2"> <p>Nombre aléatoire utilisé pour la déformation du cache. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_site</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_site%</code> </p> </td> 
   <td colname="col2"> <p>Identifiant numérique du site à partir du serveur d’annonces. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_src%</code> </p> </td> 
   <td colname="col2"> <p>DPID de la source à partir de laquelle Audience Manager extrait les métadonnées. </p> <p>Obligatoire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_uuid%</code> </p> </td> 
   <td colname="col2"> <p>Indiquez l’identifiant du visiteur directement dans l’URL au lieu de compter sur le cookie Demdex. </p> <p>Facultatif. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>%gdpr_applies%</code> </p> </td> 
   <td colname="col2"> <p>En lien avec le <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">module externe Audience Manager pour IAB TCF.</a> </p><p><code>gdpr</code> peut être 0 (le RGMD ne s’applique pas) ou 1 (le RGMD s’applique).</p> <p>La valeur par défaut est 0.</p><p>Facultatif.</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consent</code> </p> </td> 
   <td colname="col02"> <p> <code>%gdpr_consent%</code> </p> </td> 
   <td colname="col2"> <p>En lien avec le <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">module externe Audience Manager pour IAB TCF.</a></p><p> Si <code>gdpr=1</code>, alors <code>%gdpr_consent%</code> est remplacé par la chaîne <code>gdpr_consent</code> (voir les <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external">spécifications IAB</a>).</p> <p>La valeur par défaut est 0.</p><p>Facultatif.</p></td> 
  </tr> 
 </tbody> 
</table>

## Exemple de macros

Cet exemple montre comment transmettre les macros de création, de groupe et de placement. Elle suppose que les valeurs de chaque paramètre sont transmises dans la partie non redirection de l’appel de suivi des clics.

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

Selon l’exemple ci-dessus, le navigateur est redirigé vers ce qui suit [!DNL URL]:

[!DNL `https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`]

>[!MORELIKETHIS]
>
>* [Fichiers de données et de métadonnées pour les rapports Optimisation de l’audience](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

