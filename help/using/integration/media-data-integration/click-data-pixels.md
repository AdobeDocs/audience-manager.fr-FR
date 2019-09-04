---
description: valeur nulle
seo-description: valeur nulle
seo-title: Capture des données de clic de campagne par appels de pixels
solution: Audience Manager
title: Capture des données de clic de campagne par appels de pixels
uuid: 7 c 3797 f 7-9674-493 d -972 b -38 be 0584 fede
translation-type: tm+mt
source-git-commit: dbc96973ed2214d171fe32b7e1314d40c22c2d79

---


# Capturing Campaign Click Data via Pixel Calls {#capturing-campaign-click-data-via-pixel-calls}

Le suivi des clics permet la mesure de l'engagement des visiteurs tout au long de votre campagne, puisqu'il enregistre l'activité basée sur les clics pour les créations tierces. Tout comme la collection d'impressions, un appel d'événement est envoyé aux serveurs de collecte de données Audience Manager ([!UICONTROL DCS]) pour traitement. Le visiteur est ensuite redirigé vers l'adresse Web prévue.

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

La réponse redirige le navigateur vers le [!DNL URL] paramètre spécifié dans `d_rd` le paramètre. La chaîne de réponse peut inclure des valeurs générées par l'une des macros prises en charge ci-dessous.

Selon l'exemple ci-dessus, le navigateur est redirigé vers [!DNL URL]les éléments suivants :

[!DNL `https://adobe.com/callback?creative=123`]

## Macros prises en charge

Les événements de clic prennent en charge les macros répertoriées dans le tableau suivant. Une macro est une petite unité d'auto-code qui s'active lorsque la balise publicitaire se charge pour le suivi des campagnes et des utilisateurs. Les macros sont transmises avec la destination [!DNL URL], dès lors qu'elles sont marquées du format suivant : `%macro%`. Certaines clés ne comportent pas de macros et acceptent plutôt une valeur d'ID codée en dur. Les clés qui acceptent les valeurs codées en dur sont requises si vous souhaitez analyser les données dans les rapports Optimisation [de l'audience](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

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
   <td colname="col2"> <p>Identifiant publicitaire.</p> <p>Code d'intégration de la source de données de votre annonceur. Notez que cela n'est pas lié aux sources de données d'Audience Manager.</p> <p> Requis pour <span class="wintitle"> les rapports Optimisation</span> d'audience. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ bu</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ bu %</code> </p> </td> 
   <td colname="col2"> <p>Identifiant numérique de l'unité opérationnelle. </p> <p> Requis pour <span class="wintitle"> les rapports Optimisation</span> d'audience. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ campaign %</code> </p> </td> 
   <td colname="col2"> <p>Identifiant de campagne numérique du serveur d'annonces. </p> <p> Requis pour <span class="wintitle"> les rapports Optimisation</span> d'audience. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ creative</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ creative %</code> </p> </td> 
   <td colname="col2"> <p>Identifiant créatif numérique à partir du serveur d'annonces. </p> <p>Obligatoire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ id %</code> </p> </td> 
   <td colname="col2"> <p>Identifiant du fournisseur de données. </p> <p>Souvent utilisé avec <code> d_ dpuuid</code> pour lier un identifiant de fournisseur de données à un utilisateur - id. </p> <p>Facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ dpuuid %</code> </p> </td> 
   <td colname="col2"> <p>Utilisateur unique - id fourni par le fournisseur de données. </p> <p>Souvent utilisé avec <code> d_ dpid</code> pour lier un utilisateur - id à un identifiant de fournisseur de données. </p> </td> 
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
   <td colname="col2"> <p>Identifiant de région numérique de la grappe DCS qui reçoit une requête. Pour plus d'informations sur le serveur de collecte de données, voir <a href="../../reference/system-components/components-data-collection.md"> Composants de collecte de données</a>. </p> <p>Facultatif. </p> </td> 
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

Selon l'exemple ci-dessus, le navigateur est redirigé vers [!DNL URL]les éléments suivants :

[!DNL `https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`]

>[!MORE_ LIKE_ THIS]
>
>* [Fichiers de données et de métadonnées pour les rapports Optimisation d'audience](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

