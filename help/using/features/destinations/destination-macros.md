---
description: Décrit les macros que vous pouvez ajouter à une URL de destination.
seo-description: Décrit les macros que vous pouvez ajouter à une URL de destination.
seo-title: Macros de destination définies
solution: Audience Manager
title: Macros de destination définies
uuid: 982 cab 05-8 a 3 f -4 f 96-b 4 d 0-291709712 ad 1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Destination Macros Defined {#destination-macros-defined}

Describes the macros you can add to a destination [!DNL URL].

<!-- destination-macros.xml -->

When creating a [!DNL URL] destination, you can insert the following macros into the [!DNL URL] string. Check with your data/destination partner about proper macro placement within the destination [!DNL URL].

>[!NOTE]
>
>Les macros sont facultatives sauf indication contraire. Le format *italique* indique un espace réservé variable.

<table id="table_2C532EFB9DAE41B08714753EBD7DFB05"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> %alias%</code> </p> </td> 
   <td colname="col2"> <p>Obligatoire. </p> <p>Définit l'emplacement de la valeur de segment mappée dans une URL de destination. Usually this is the <i>Segment ID</i>, but could also be the integration code. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>Inserts the user's <span class="keyword"> Audience Manager</span> ID into the destination URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>% dpid_<i>id source</i>%</code> </p> </td> 
   <td colname="col2"> <p>The <i>data source id</i> corresponds to the identifier for a data source passed in to the macro. </p> <p>Voyons comment cela fonctionne dans un exemple simple. In this case, we have an <span class="keyword"> Audience Manager</span> partner with the following IDs and conditions: </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">Data source ID: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">An internal customer ID: <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">Declared ID: The partner wants to pass in these values as the declared ID <code> 1:CustomerABC</code>. </li> 
    </ul> <p>To do this with the <code>%dpid_<i>data source id</i>%</code>, the <span class="keyword"> Audience Manager</span> partner would format the macro like this: </p> 
    <ul class="simplelist"> 
     <li> <code> % dpid_ 1%</code> </li> 
    </ul> <p>The macro will replace <code> 1</code> with <code> CustomerABC</code>. </p> <p> 
     <draft-comment>
       Basé sur AAM -22193 https://jira.corp.adobe.com/browse/AAM-22193 
     </draft-comment> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> % http_ proto %</code> </p> </td> 
   <td colname="col2"> <p>Détecte le protocole utilisé dans la webpage Web parente et l'insère dans l'URL de destination. For example: 
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">if the webpage is <b>https</b>://aam_client.com, this macro will be replaced with <b>https</b>://url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">if the webpage is <b>http</b>://aam_client.com, this macro will be replaced with <b>http</b>://url-destination.com </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> % mcid %</code> </p> </td> 
   <td colname="col2"> <p>Inserts the <span class="keyword"> Experience Cloud</span> ID into the destination URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> % region %</code> </p> </td> 
   <td colname="col2"> <p>Inserts the <span class="wintitle"> Data Collection Server (DCS)</span> region into the destination URL. In order to minimize latency, when the visitor makes an HTTP call to <span class="keyword"> Audience Manager</span>, they are being redirected to the closest <span class="wintitle"> DCS</span> datacenter. Ce processus est obtenu via DNS, capable de détecter l'emplacement du visiteur et de le diriger vers le centre de données approprié. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> % rnd %</code> </p> </td> 
   <td colname="col2"> <p>Exécute une fonction de mise en cache en insérant un nombre aléatoire dans l'URL de destination. Cela empêche les navigateurs de diffuser du contenu mis en cache. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>Insère un horodatage UNIX dans l'URL de destination pour empêcher les navigateurs de diffuser du contenu mis en cache. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cache Busting with Destination Macros {#destination-cache-busting}

The `%rnd%` and `%timestamp%` macros insert unique values into a [!DNL URL] string to prevent browser caching.

## Cache Busting with `%rnd%` and `%timestamp%` {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

Le cache des navigateurs (enregistrer) le contenu fréquemment demandé en mémoire. Lorsqu&#39;une page se charge, le contenu enregistré est diffusé à partir du cache plutôt qu&#39;à partir d&#39;un serveur distant. Ce processus permet de conserver des temps de téléchargement efficaces car les données sont diffusées localement plutôt qu&#39;à partir d&#39;un autre emplacement. Cependant, la mise en cache ne nécessitant pas d&#39;appel au serveur, elle peut fausser la création de rapports en diminuant artificiellement le nombre de requêtes uniques.

La mise en cache du cache empêche les navigateurs d&#39;enregistrer et de réutiliser du contenu. Cette technique utilise le code qui insère un horodatage ou un horodatage dans une chaîne URL, ce qui lui donne un aspect unique. As a result, each `HTTP` call is counted as a separate request to the server. Forcer un nouvel appel au serveur pour chaque requête permet de conserver la précision des rapports et de réduire les disparités. [!DNL Audience Manager] fournit deux macros pour la mise en cache :

* `%rnd%`: Insère un nombre aléatoire dans une URL.
* `%timestamp%`: Insère la date/heure Unix dans une URL.

## Comparing `%rnd%` and `%timestamp%` {#compare-rnd-timestamp}

Both macros prevent caching, but `%rnd%` may be more efficient. For example, with `%timestamp%`, if several users view a page simultaneously they&#39;ll get the same date/time value. As a result, the [!DNL URL] is not unique and multiple calls are counted only once. `%rnd%` Toutefois, génère une valeur numérique unique pour chaque appel (même lorsque les utilisateurs visualisent la même page simultanément). This means the [!DNL URL] string contains different values and is counted as unique.

>[!MORE_ LIKE_ THIS]
>
>* [Macros de destination définies](../../features/destinations/destination-macros.md#destination-macros-defined)