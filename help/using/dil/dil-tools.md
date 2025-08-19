---
description: Décrit les méthodes de l’espace de noms DIL.tools. Ces fonctions d’utilitaire vous aident à effectuer des tâches spécifiques.
seo-description: Describes methods in the DIL.tools namespace. These utility functions help you perform specific tasks.
seo-title: DIL Tools
solution: Audience Manager
title: Outils DIL
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: DIL Implementation
exl-id: 1f52eb95-8287-4dd0-b933-00de6926a797
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 2%

---

# Outils DIL

>[!WARNING]
>
>Depuis juillet 2023, Adobe a interrompu le développement du [!DNL Data Integration Library (DIL)] et de l’extension [!DNL DIL].
>
>Les clients existants peuvent continuer à utiliser leur implémentation [!DNL DIL]. Cependant, Adobe ne développera pas d’[!DNL DIL] au-delà de ce point. Nous recommandons aux clients d’évaluer [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=fr) pour leur stratégie de collecte de données à long terme.
>
>Les clients qui souhaitent implémenter de nouvelles intégrations de collecte de données après juillet 2023 doivent utiliser [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=fr) à la place.

Décrit les méthodes de l’espace de noms `DIL.tools`. Ces fonctions d’utilitaire vous aident à effectuer des tâches spécifiques.

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

Renvoie les termes de recherche utilisés pour atteindre la page active.

<!-- 

r_dil_get_search_referrer.xml

 -->

### But de la `getSearchReferrer`

Dans DIL, `getSearchReferrer` renvoie les résultats de recherche (noms et mots-clés) utilisés pour accéder à votre site. Vous pouvez transmettre des termes de recherche spécifiques à cette fonction ou la laisser rechercher les moteurs de recherche pris en charge ( [!DNL AOL], [!DNL Ask], [!DNL Bing], [!DNL Google] et [!DNL Yahoo]) par `document.referrer` par défaut.

### Signature de fonction

Signature de fonction : `DIL.tools.getSearchReferrer(uri, initConfig)`

### Paramètres de la fonction

`getSearchReferrer` accepte :

* *`{string}`* : *(facultatif)* chaîne contenant l’URL de recherche (utilise `document.referrer` si elle n’est pas définie).
* *`{object}`* : *(facultatif)* objet contenant la configuration de l’`hostPattern`, du `queryParam` ou de l’`queryPattern`.

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
      <code>var&nbsp;results&nbsp;=&nbsp;DIL.tools.getSearchReferrer();</code> 
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
   <td> <b>Faire correspondre le nom d’hôte de l’URL avec une expression régulière personnalisée</b></td> 
   <td> Transmettez une expression régulière personnalisée pour correspondre au nom d’hôte de l’URL de référence. </td> 
   <td> 
  <code>
      var results = 
        DIL.tools.getSearchReferrer("https://www.ehow.com/
      search.aspx?q=adobe+rules",&lbrace; 
      &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
      &nbsp;&nbsp;&nbsp;queryParam:"p" 
      &rbrace;); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>Faire correspondre des modèles de recherche avec une expression régulière personnalisée</b> </td> 
   <td> Transmettez une expression régulière personnalisée pour effectuer une recherche personnalisée. </td> 
   <td> 
    <code>
      var&nbsp;results&nbsp;= 
      DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
      &lbrace;
        &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
        &nbsp;&nbsp;&nbsp;search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      &rbrace;);
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## décomposerURI

Désassemble un identifiant de ressource uniforme ([!DNL URI]) en ses composants constitutifs : `hash`, `host`, `href`, `pathname`, `protocol`, `search` et `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

Signature de fonction : `DIL.tools.decomposeURI`

### Paramètres de la fonction

`decomposeURI` accepte :

* *`uri {string}`* : *(facultatif)* chaîne contenant l’URI. La valeur par défaut est `document.location.href` si elle n’est pas spécifiée.

Et renvoie :

* *`{object}`* : objet contenant des noms et des mots-clés valides.

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

Recherche du contenu spécifique défini dans les balises de métadonnées sur une page web et renvoie ces données dans un objet .

<!-- 

r_dil_get_metatags.xml

 -->

### Signature de fonction

Signature de fonction : `DIL.tools.getMetaTags( 1 or more parameters)`

### Paramètres de la fonction

`getMetaTags` accepte un ou plusieurs paramètres de nom (type chaîne) à rechercher. Elle renvoie un objet composé de paires clé-valeur.

### Exemple de code

<pre class="javascript"><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>', '<i>keywords</i>',  '<i>description</i>'), 'c_').submit();
</code></pre>

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: <i>&grave;partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
