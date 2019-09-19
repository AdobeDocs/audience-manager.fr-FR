---
description: Décrit les macros que vous pouvez ajouter à une URL de destination.
seo-description: Décrit les macros que vous pouvez ajouter à une URL de destination.
seo-title: Macros de destination définies
solution: Audience Manager
title: Macros de destination définies
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Macros de destination définies {#destination-macros-defined}

Décrit les macros que vous pouvez ajouter à une destination [!DNL URL].

<!-- destination-macros.xml -->

Lors de la création d’une [!DNL URL] destination, vous pouvez insérer les macros suivantes dans la [!DNL URL] chaîne. Vérifiez auprès de votre partenaire de données/destination le positionnement correct des macros dans la destination [!DNL URL].

>[!NOTE]
>
>Les macros sont facultatives, sauf indication contraire. Le format *italique* indique un espace réservé variable.

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
   <td colname="col2"> <p>Insère l’ID <span class="keyword"> Audience Manager</span> de l’utilisateur dans l’URL de destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_id<i>de source de</i>données%</code> </p> </td> 
   <td colname="col2"> <p>L’ID <i>de source de</i> données correspond à l’identifiant d’une source de données transmise à la macro. </p> <p>Examinons comment cela fonctionne dans un exemple simple. Dans ce cas, nous avons un partenaire <span class="keyword"> Audience Manager</span> avec les identifiants et conditions suivants : </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">ID de source de données : <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">ID client interne : <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">ID déclaré : Le partenaire souhaite transmettre ces valeurs en tant qu’ID déclaré <code> 1:CustomerABC</code>. </li> 
    </ul> <p>Pour ce faire, avec l’ID <code><i>de source de</i>%dpid_</code>données% <span class="keyword"> , le partenaire d’Audience Manager</span> formate la macro comme suit : </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>La macro remplacera <code> 1</code> par <code> CustomerABC</code>. </p> <p> 
     <draft-comment>
       Basé sur AAM-22193 https://jira.corp.adobe.com/browse/AAM-22193 
     </draft-comment> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>Détecte le protocole utilisé dans la page Web parente et l’insère dans l’URL de destination. For example: 
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">si la page Web est <b>https</b>://aam_client.com, cette macro sera remplacée par <b>https</b>://url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">si la page Web est <b>http</b>://aam_client.com, cette macro sera remplacée par <b>http</b>://url-destination.com </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>Insère l’ <span class="keyword"> ID Experience Cloud</span> dans l’URL de destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p>Insère la région <span class="wintitle"> Data Collection Server (DCS)</span> dans l’URL de destination. Afin de minimiser la latence, lorsque le visiteur effectue un appel HTTP à <span class="keyword"> Audience Manager</span>, il est redirigé vers le centre de données <span class="wintitle"> DCS</span> le plus proche. Pour ce faire, le service DNS permet de détecter l’emplacement du visiteur et de le diriger vers le centre de données approprié. </p> </td> 
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

## Mise en cache avec les macros de destination {#destination-cache-busting}

Les macros `%rnd%` et `%timestamp%` les macros insèrent des valeurs uniques dans une [!DNL URL] chaîne pour empêcher la mise en cache du navigateur.

## Mise en cache avec `%rnd%` et `%timestamp%`{#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

Les navigateurs mettent en cache (enregistrent) le contenu fréquemment demandé en mémoire. Lors du chargement d’une page, le contenu enregistré est diffusé à partir du cache plutôt qu’à partir d’un serveur distant. Ce processus permet de conserver des temps de téléchargement efficaces, car les données sont diffusées localement plutôt qu’à partir d’un autre emplacement. Cependant, comme la mise en cache ne nécessite pas d’appel serveur, elle peut fausser la création de rapports en diminuant artificiellement le nombre de requêtes uniques.

La suppression du cache empêche les navigateurs d’enregistrer et de réutiliser le contenu. Cette technique utilise du code qui insère un nombre aléatoire ou un horodatage dans une chaîne d’URL, ce qui le rend unique au navigateur. Par conséquent, chaque `HTTP` appel est compté comme une requête distincte au serveur. Le fait de forcer un nouvel appel au serveur pour chaque requête permet de maintenir la précision des rapports et de réduire les incohérences. [!DNL Audience Manager] fournit deux macros pour la déformation du cache :

* `%rnd%`: Insère un nombre aléatoire dans une URL.
* `%timestamp%`: Insère la date et l’heure Unix dans une URL.

## Comparaison `%rnd%` et `%timestamp%`{#compare-rnd-timestamp}

Les deux macros empêchent la mise en cache, mais `%rnd%` peuvent être plus efficaces. Par exemple, `%timestamp%`si plusieurs utilisateurs consultent simultanément une page, ils obtiennent la même valeur de date/heure. Par conséquent, le n’ [!DNL URL] est pas unique et plusieurs appels sont comptabilisés une seule fois. Cependant, `%rnd%` génère une valeur numérique unique pour chaque appel (même lorsque les utilisateurs voient simultanément la même page). Cela signifie que la [!DNL URL] chaîne contient des valeurs différentes et est comptée comme unique.

>[!MORE_LIKE_This]
>
>* [Macros de destination définies](../../features/destinations/destination-macros.md#destination-macros-defined)