---
description: Décrit les méthodes dans l’espace de noms DIL.tools. Ces fonctions d’utilitaire vous aident à effectuer des tâches spécifiques.
seo-description: Décrit les méthodes dans l’espace de noms DIL.tools. Ces fonctions d’utilitaire vous aident à effectuer des tâches spécifiques.
seo-title: Outils DIL
solution: Audience Manager
title: Outils DIL
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: Mise en oeuvre du DIL
exl-id: 1f52eb95-8287-4dd0-b933-00de6926a797
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 5%

---

# Outils DIL

Décrit les méthodes dans l’espace de noms `DIL.tools`. Ces fonctions d’utilitaire vous aident à effectuer des tâches spécifiques.

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

Renvoie les termes de recherche utilisés pour atteindre la page active.

<!-- 

r_dil_get_search_referrer.xml

 -->

### Objectif de `getSearchReferrer`

Dans DIL, `getSearchReferrer` renvoie les résultats de la recherche (noms et mots-clés) utilisés pour atteindre votre site. Vous pouvez transmettre des termes de recherche spécifiques à cette fonction ou la laisser rechercher par défaut les moteurs de recherche pris en charge ( [!DNL AOL], [!DNL Ask], [!DNL Bing], [!DNL Google] et [!DNL Yahoo]) par rapport à `document.referrer`.

### Signature de fonction

Signature de fonction : `DIL.tools.getSearchReferrer(uri, initConfig)`

### Paramètres de fonction

`getSearchReferrer` accepte :

* *`{string}`*:  *(Facultatif)* Chaîne contenant l’URL de recherche (utilisée  `document.referrer` si non définie).
* *`{object}`*:  *(Facultatif)* Objet contenant la configuration pour  `hostPattern`,  `queryParam` ou  `queryPattern`.

Et renvoie :

* `{object}` Objet contenant des noms et des mots-clés valides.

### Exemples

<table id="table_D035276601EC428295E4D619F05BB8D0"> 
 <thead> 
  <tr> 
   <th> Type de recherche </th> 
   <th> Description </th> 
   <th> Exemple de code </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Recherche par défaut</td> 
   <td> Renvoie les termes de recherche par mot-clé utilisés par les moteurs de recherche AOL, Ask, Bing, Google et Yahoo. </td> 
   <td>
      <code>var&amp;nbsp;results&amp;nbsp;=&amp;nbsp;DIL.tools.getSearchReferrer();</code> 
  </td>
  </tr> 
  <tr> 
   <td>Transmission d’une URL personnalisée</td> 
   <td>Renvoie le référent de recherche en fonction d’une URL personnalisée.</td> 
   <td> 
  <code>
        var&nbsp;results&nbsp;= 
        DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>Faire correspondre le nom d’hôte de l’URL avec un Regex personnalisé</b></td> 
   <td> Transmettez une expression régulière personnalisée pour correspondre au nom d’hôte de l’URL de référence. </td> 
   <td> 
  <code>
      var results = 
        DIL.tools.getSearchReferrer("https://www.ehow.com/
      search.aspx?q=adobe+rules",{ 
      &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
      &nbsp;&nbsp;&nbsp;queryParam:"p" 
      }); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>Faire correspondre des modèles de recherche avec un regex personnalisé</b> </td> 
   <td> Transmettez une expression régulière personnalisée pour effectuer une recherche personnalisée. </td> 
   <td> 
    <code>
      var&nbsp;results&nbsp;= 
      DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
      {
        &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
        &nbsp;&nbsp;&nbsp;search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      });
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## décomposerURI

Dissocie un identifiant de ressource unique ( [!DNL URI]) en ses composants constitutifs : `hash`, `host`, `href`, `pathname`, `protocol`, `search` et `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

Signature de fonction : `DIL.tools.decomposeURI`

### Paramètres de fonction

`decomposeURI` accepte :

* *`uri {string}`*:  *(Facultatif)* Chaîne contenant l’URI. La valeur par défaut est `document.location.href` si elle n’est pas spécifiée.

Et renvoie :

* *`{object}`*: Objet contenant des noms et des mots-clés valides.

### Exemple de code


```javascript
var uriData = DIL.tools.decomposeURI('https://www.adobe.com/?arg1=123&arg2=456#am'); 
{ 
  hash : "#am", 
  host : "www.adobe.com", 
  hostname : "www.adobe.com", 
  href : "https://www.adobe.com/?arg1=123&arg2=456#am", 
  pathname : "", 
  protocol : "https:", 
  search : "?arg1=123&arg2=456", 
  uriParams : { 
    arg1 : "123", 
    arg2 : "456" 
  } 
}
```

## getMetaTags

Recherche du contenu spécifique défini dans les balises META d’une page web et renvoie ces données dans un objet.

<!-- 

r_dil_get_metatags.xml

 -->

### Signature de fonction

Signature de fonction : `DIL.tools.getMetaTags( 1 or more parameters)`

### Paramètres de fonction

`getMetaTags` accepte un ou plusieurs paramètres de nom (type chaîne) à rechercher. Elle renvoie un objet composé de paires clé-valeur.

### Exemple de code

<pre class="&ldquo;javascript&rdquo;"><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>', '<i>keywords</i>',  '<i>description</i>'), 'c_').submit();
</code></pre>

<pre><code>
var dataLib = DIL.create({ 
     partner: <i>`partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
