---
description: Décrit les macros que vous pouvez ajouter à une URL de destination.
seo-description: Décrit les macros que vous pouvez ajouter à une URL de destination.
seo-title: Macros de destination définies
solution: Audience Manager
title: Macros de destination définies
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
translation-type: tm+mt
source-git-commit: da0eb0244fc3ae158fa151727f4253625dcff2c4
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 1%

---


# Macros de destination définies {#destination-macros-defined}

Décrit les macros que vous pouvez ajouter à une destination [!DNL URL].

<!-- destination-macros.xml -->

Lors de la création d’une [!DNL URL] destination, vous pouvez insérer les macros suivantes dans la [!DNL URL] chaîne. Vérifiez auprès de votre partenaire de données/de destination le positionnement correct des macros dans la destination [!DNL URL].

>[!NOTE]
>
>Sauf indication contraire, les macros sont facultatives. Le format *italique* indique un espace réservé variable.

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
   <td colname="col2"> <p>Obligatoire. </p> <p>Définit l’emplacement de la valeur de segment mappée dans une URL de destination. Il s’agit généralement de l’ID <i>de</i>segment, mais il peut également s’agir du code d’intégration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>Insère l’ID du gestionnaire <span class="keyword"> d’</span> Audiences de l’utilisateur dans l’URL de destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p>L’ID <i>de source de</i> données correspond à l’identifiant d’une source de données transmise à la macro. </p> <p>Examinons comment cela fonctionne dans un exemple simple. Dans ce cas, nous avons un partenaire <span class="keyword"> Audience Manager</span> avec les ID et conditions suivants : </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">ID de source de données : <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">Un ID de client interne : <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">ID déclaré : Le partenaire souhaite transmettre ces valeurs en tant qu’identifiant déclaré <code> 1:CustomerABC</code>. </li> 
    </ul> <p>Pour ce faire, le <code>%dpid_<i>data source id</i>%</code>partenaire <span class="keyword"> Audience Manager</span> formate la macro comme suit : </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>La macro va remplacer <code> 1</code> par <code> CustomerABC</code>. </p> <p> 
     <draft-comment>
       Basé sur AAM-22193 https://jira.corp.adobe.com/browse/AAM-22193 
     </draft-comment> </p> </td> 
  </tr> 
  <tr>
    <td><p><code>${GDPR}</code></p></td>
    <td><p>Indique si les règlements du RGMD s'appliquent au visiteur ou non. Utilisez cette macro pour inclure le consentement dans les segments envoyés aux destinations URL intégrées à IAB. Voir Module externe <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager pour le TCF</a> IAB pour en savoir plus.</p></td>
  </tr>
   <tr>
    <td><code>${GDPR_CONSENT_XXXX}</code></p></td>
    <td><p>Chaîne de consentement (y compris l’ID du fournisseur IAB) collectée lorsque des visiteurs fournissent ou refusent le consentement sur votre site. Utilisez cette macro pour inclure la chaîne de consentement dans les segments envoyés aux destinations URL intégrées à IAB. Remplacez cette valeur par <code>XXXX</code> l’identifiant du partenaire de destination. Voir Module externe <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager pour le TCF</a> IAB pour en savoir plus. </p></td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>Détecte le protocole utilisé dans la page Web parente et l’insère dans l’URL de destination. Par exemple:
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">si la page web est <b>https</b>://aam_client.com, cette macro sera remplacée par <b>https</b>://url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">si la page Web est <b>http</b>://aam_client.com, cette macro sera remplacée par <b>http</b>://url-destination.com </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>Insère l’ID <span class="keyword"> Experience Cloud</span> dans l’URL de destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p>Insère la région <span class="wintitle"> Data Collection Server (DCS)</span> dans l’URL de destination. Afin de minimiser la latence, lorsque le visiteur effectue un appel HTTP au gestionnaire <span class="keyword"></span>d’Audiences, il est redirigé vers le centre de données <span class="wintitle"> DCS</span> le plus proche. Pour ce faire, le service DNS est capable de détecter l’emplacement du visiteur et de le diriger vers le centre de données approprié. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd%</code> </p> </td> 
   <td colname="col2"> <p>Exécute une fonction de masquage du cache en insérant un nombre aléatoire dans l’URL de destination. Cela empêche les navigateurs de diffuser du contenu mis en cache. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>Insère un horodatage UNIX dans l’URL de destination afin d’empêcher les navigateurs de diffuser du contenu mis en cache. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Mise en cache avec des macros de destination {#destination-cache-busting}

Les `%rnd%` macros et `%timestamp%` macros insèrent des valeurs uniques dans une [!DNL URL] chaîne pour empêcher la mise en cache du navigateur.

## Mise en cache avec `%rnd%` et `%timestamp%` {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

Les navigateurs mettent en cache (enregistrent) le contenu fréquemment demandé en mémoire. Lors du chargement d’une page, le contenu enregistré est diffusé à partir du cache plutôt qu’à partir d’un serveur distant. Ce processus permet de conserver des temps de téléchargement efficaces, car les données sont utilisées localement plutôt qu’à partir d’un autre emplacement. Cependant, comme la mise en cache ne nécessite pas d’appel au serveur, elle peut fausser le rapports en diminuant artificiellement le nombre de requêtes uniques.

La suppression du cache empêche les navigateurs d’enregistrer et de réutiliser du contenu. Cette technique utilise un code qui insère un nombre aléatoire ou un horodatage dans une chaîne URL, ce qui la rend unique au navigateur. Par conséquent, chaque `HTTP` appel est comptabilisé comme une requête distincte au serveur. Le fait de forcer un nouvel appel de serveur pour chaque requête permet de conserver la précision du rapports et de réduire les incohérences. [!DNL Audience Manager] fournit deux macros pour la déformation du cache :

* `%rnd%`: Insère un nombre aléatoire dans une URL.
* `%timestamp%`: Insère la date et l’heure Unix dans une URL.

## Comparaison `%rnd%` et `%timestamp%` {#compare-rnd-timestamp}

Les deux macros empêchent la mise en cache, mais `%rnd%` peuvent être plus efficaces. Par exemple, `%timestamp%`si plusieurs utilisateurs vue une page simultanément, ils obtiennent la même valeur de date/heure. Par conséquent, le n’ [!DNL URL] est pas unique et plusieurs appels ne sont comptabilisés qu’une seule fois. Cependant, `%rnd%` génère une valeur numérique unique pour chaque appel (même si les utilisateurs voient simultanément la même page). Cela signifie que la [!DNL URL] chaîne contient des valeurs différentes et est comptée comme unique.

>[!MORELIKETHIS]
>
>* [Macros de destination définies](../../features/destinations/destination-macros.md#destination-macros-defined)