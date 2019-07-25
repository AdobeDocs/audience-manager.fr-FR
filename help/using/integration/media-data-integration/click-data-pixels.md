---
description: valeur nulle
seo-description: valeur nulle
seo-title: Capture des données de clic de campagne par appels de pixels
solution: Audience Manager
title: Capture des données de clic de campagne par appels de pixels
uuid: 7 c 3797 f 7-9674-493 d -972 b -38 be 0584 fede
translation-type: tm+mt
source-git-commit: c79c2311c3ea76ce2450dc1b84a7a22b60a6edb7

---


# Capturing Campaign Click Data via Pixel Calls {#capturing-campaign-click-data-via-pixel-calls}

Le suivi des clics permet la mesure de l'engagement des visiteurs tout au long de votre campagne, puisqu'il enregistre l'activité basée sur les clics pour les créations tierces. Similar to impressions collection, an event call is sent to the Audience Manager data collection servers ([!UICONTROL DCS]) for processing. Le visiteur est ensuite redirigé vers l'adresse Web prévue.

## Conditions

Les appels de suivi des clics nécessitent les paramètres suivants :

* `d_event=click`: Paire clé-valeur qui identifie un appel d'événement comme événement click.
* `d_rd=redirect URL`: Paire clé-valeur contenant une redirection [!DNL URL]codée.

En outre, l'appel peut contenir des paires clé-valeur qui peuvent être utilisées pour la qualification des caractéristiques ou fournir des données et des métadonnées pour d'autres rapports.

## Exemple de demande

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## Réponse

The response redirects the browser to the [!DNL URL] specified in the `d_rd` parameter. La chaîne de réponse peut inclure des valeurs générées par l'une des macros prises en charge ci-dessous.

Based on the above example, the browser is redirected to the following [!DNL URL]:

[!DNL `https://adobe.com/callback?creative=123`]

## Macros prises en charge

Les événements de clic prennent en charge les macros répertoriées dans le tableau suivant. Une macro est une petite unité d'auto-code qui s'active lorsque la balise publicitaire se charge pour le suivi des campagnes et des utilisateurs. The macros will be passed along with the destination [!DNL URL], as long as they are marked with the following format: `%macro%`. Certaines clés ne comportent pas de macros et acceptent plutôt une valeur d'ID codée en dur. Keys that accept hard coded values are required if you want to analyze data in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

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
   <td colname="col1"> <p> <code> d_ adgroup</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ adgroup %</code> </p> </td> 
   <td colname="col2"> <p>Identifiant de groupe publicitaire numérique à partir du serveur d'annonces. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ adsrc</code> </p> </td> 
   <td colname="col02"> <p>Aucune macro. </p> <p>Accepte une valeur d'ID codée en dur. </p> </td> 
   <td colname="col2"> <p> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> ID ou</a> code d'intégration de source de données pour votre annonceur. </p> <p> Required for <span class="wintitle"> Audience Optimization</span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ bu</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ bu %</code> </p> </td> 
   <td colname="col2"> <p>Identifiant numérique de l'unité opérationnelle. </p> <p> Required for <span class="wintitle"> Audience Optimization</span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ campaign %</code> </p> </td> 
   <td colname="col2"> <p>Identifiant de campagne numérique du serveur d'annonces. </p> <p> Required for <span class="wintitle"> Audience Optimization</span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ creative</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ creative %</code> </p> </td> 
   <td colname="col2"> <p>Identifiant créatif numérique à partir du serveur d'annonces. </p> <p>Obligatoire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ id %</code> </p> </td> 
   <td colname="col2"> <p>Identifiant du fournisseur de données. </p> <p>Often used with <code> d_dpuuid</code> to link a data provider ID to a user ID. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ dpuuid %</code> </p> </td> 
   <td colname="col2"> <p>Utilisateur unique - id fourni par le fournisseur de données. </p> <p>Often used with <code> d_dpid</code> to link a user ID to a data provider ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Experience Cloud ID (ECID). </span> For more information about the ECID, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ placement</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ placement %</code> </p> </td> 
   <td colname="col2"> <p>Identifiant de placement numérique à partir du serveur d'annonces. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ region</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ region %</code> </p> </td> 
   <td colname="col2"> <p>Identifiant de région numérique de la grappe DCS qui reçoit une requête. For more information about the DCS, see <a href="../../reference/system-components/components-data-collection.md"> Data Collection Components</a>. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_ rand</code> </p> </td> 
   <td colname="col02"> <p> <code> % r_ rand %</code> </p> </td> 
   <td colname="col2"> <p>Nombre aléatoire utilisé pour la mise en cache. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ site</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ site %</code> </p> </td> 
   <td colname="col2"> <p>Identifiant de site numérique à partir du serveur d'annonces. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ src</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ src %</code> </p> </td> 
   <td colname="col2"> <p>DPID de la source à partir duquel Audience Manager extrait les métadonnées. </p> <p>Obligatoire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ uuid %</code> </p> </td> 
   <td colname="col2"> <p>Indiquez l'ID du visiteur directement dans l'URL plutôt que de dépendre du cookie Demdex. </p> <p>Facultatif. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>% gdpr_ apply %</code> </p> </td> 
   <td colname="col2"> <p>En lien avec le <a href="../../overview/aam-gdpr/aam-iab-plugin.md">module externe Audience Manager pour IAB TCF.</a> </p><p><code>gdpr</code> peut être 0 (GDPR ne s'applique pas) ou 1 (GDPR s'applique).</p> <p>La valeur par défaut est 0.</p><p>Facultatif.</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_ permission</code> </p> </td> 
   <td colname="col02"> <p> <code>% gdpr_ permission %</code> </p> </td> 
   <td colname="col2"> <p>En lien avec le <a href="../../overview/aam-gdpr/aam-iab-plugin.md">module externe Audience Manager pour IAB TCF.</a></p><p> Si <code>gdpr=1</code>, alors <code>%gdpr_consent%</code> est remplacé par la chaîne <code>gdpr_consent</code> (voir les <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external">spécifications IAB</a>).</p> <p>La valeur par défaut est 0.</p><p>Facultatif.</p></td> 
  </tr> 
 </tbody> 
</table>

## Exemple de macros

Cet exemple illustre la transmission des macros creative, adgroup et placement. Elle suppose que les valeurs de chaque paramètre sont transmises dans la portion non redirection de l'appel de suivi des clics.

<ul class="simplelist"> 
 <li> <code> creative = 1235 </code> </li> 
 <li> <code> campaign = 4709 </code> </li> 
 <li> <code> adgroup = 3408 </code> </li> 
 <li> <code> placement = 1001 </code> </li> 
 <li> <code> src = 203 </code> </li> 
</ul>

## Demande

```
https://client.demdex.net/event?d_event=click&d_creative=1235&d_src=203&d_campaign=4709&d_adgroup=3408&d_placement=1001&
d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25%26campaign%3D%25d_campaign%25%26adgroup%3D%25
d_adgroup%25%26d_placement%3D%25placement%25%26src%3D%25d_src%25
```

## Réponse

Based on the above example, the browser is redirected to the following [!DNL URL]:

[!DNL `https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`]

>[!MORE_ LIKE_ THIS]
>
>* [Fichiers de données et de métadonnées pour les rapports Optimisation d'audience](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

