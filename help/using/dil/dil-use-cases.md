---
description: Exemples de code et descriptions pour des cas d'utilisation DIL spécifiques.
seo-description: Exemples de code et descriptions pour des cas d'utilisation DIL spécifiques.
seo-title: Cas d'utilisation DIL et exemples de code
solution: Audience Manager
title: Cas d'utilisation DIL et exemples de code
uuid: 27995 c 2 d -6572-438 e-af 99-b 5477 f 090 ae 9
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DIL Use Cases and Code Samples{#dil-use-cases-and-code-samples}

Exemples de code et descriptions pour des cas d'utilisation DIL spécifiques.

<!-- 

c_dil_use_case.xml

 -->

## Send Data Elements to Audience Manager with DIL {#send-data-elements-dil}

Créez une variable d'objet qui envoie des informations sur les éléments de la page à Audience Manager. Ceci s'avère utile pour la collecte de données générales ou pour la collecte de données avec des variables Analytics.

<!-- 

c_dil_send_page_objects.xml

 -->

**Description**

The following code demonstrates how to collect page data and send it to Audience Manager with [!UICONTROL DIL]. Ces exemples utilisent une variable pour contenir des éléments de données dans une liste aplatie ou un tableau. Remember, pass in variables as [key-value pairs](../reference/key-value-pairs-explained.md). Also, note the `c_` prefix before the key in the key-value pair. This [required prefix](../features/traits/trait-variable-prefixes.md) identifies information as user-defined data. In the first example, you need to manually append `c_` to the key. In the second example, [!UICONTROL DIL] does this for you automatically.

**Conserver les propriétés de valeur cohérentes**

Pensez à conserver les propriétés de valeur de la même façon lors de la transmission des données. Par exemple, si vous disposez de deux clés identiques avec des valeurs différentes, la valeur de la dernière paire clé-valeur est prioritaire sur les objets de valeur précédents. For example, passing in `color:blue` and `color:red` sets the returned value to red (overwrites blue).

**Exemple 1 : Envoyer les données en tant que paires clé-valeur**

Cet exemple de base envoie les données de couleur et de prix à Audience Manager sous la forme de paires clé-valeur. Votre code peut ressembler à ce qui suit :

<pre class="&ldquo;java&rdquo;"><code>var sample_ dil = DIL. create ({partner : « <i>nom du partenaire</i> ») ; 
sample_ dil. api. signals ({ 
 c_ color : « bleu », 
 c_ price : « 900 »}) 
; 
sample_ dil. api. submit () ;</code>
</pre>

**Exemple 2 : Envoi de données dans un objet**

Cet exemple avancé montre comment envoyer des données dans un objet à Audience Manager. When working with this method, [!UICONTROL DIL] lets you pass an object as a function parameter into the [!DNL signals()] method. [!UICONTROL DIL] Votre code peut ressembler à ce qui suit :

<pre class="java"><code>var my_ object = { 
 color : « bleu », 
 prix : « 900 »} 
; 
 
var sample_ dil = DIL. create ({partner : « <i>nom du partenaire</i> ») ; 
//load l'objet et ajoutez « c_ » à toutes les clés des paires clé-valeur et envoyez les données à audiencemanager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**Exemple 3 : Envoi de données de page dans un tableau**

In this case, the variable `my_object` uses an array to hold data. Cet exemple repose sur les informations transmises par la méthode recommandée ci-dessus, mais ajoute un calque supplémentaire pour tenir compte d'un type et d'un modèle de produit. Votre code peut ressembler à ce qui suit :

<pre class="java"><code>var my_ objects = [{ 
 color : « bleu », 
 prix : « 900 »}, 
{ 
 type : « acura », 
 modèle : « tl »}] 
; 
 
var sample_ dil = DIL. create ({partner : « <i>nom du partenaire</i> ») ; 
 
for (var i = 0 ; i &lt; my_ objects. length ; i + +) 
//load l'objet et ajoute « c_ » à toutes les clés des paires clé-valeur. 
{ 
    sample_dil.api.signals(my_objects[i], "c_"); 
} 
sample_dil.api.submit();
</code></pre>

>[!MORE_ LIKE_ THIS]
>
>* [signaux](../dil/dil-instance-methods.md#signals)


## Capture Referring URL {#capture-referring-url}

Capturez et envoyez une URL de référence à Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Cette méthode fonctionne uniquement lorsque les utilisateurs passent d'une page à une autre avec des protocoles similaires (HTTP/HTTPS). Par exemple, le navigateur conserve une URL de référence lorsque vous accédez à un autre site sécurisé depuis un site sécurisé. Les navigateurs ne conservent pas l'URL de référence lorsque vous passez d'un site sécurisé à un site non sécurisé. This behavior is normal browser functionality and cannot be circumvented by [!UICONTROL DIL].

**Exemple de code**

Votre code peut ressembler à ce qui suit :

<pre class="java"><code>var adobe_ dil = DIL. create ({partner : « <i>nom du partenaire</i> ») ; 
adobe_ dil. api. signals ({d_ referer : document. referrer}). submit () ;</code>
</pre>

## Capture Search Engine Types and Keyword Search Terms {#capture-search-engine-types}

Envoyez des informations sur le type de moteur de recherche et les recherches de mots-clés dans Audience Manager.

<!-- 

c_dil_search_engine_valid.xml

 -->

**Moteurs de recherche pris en charge**

By default, `DIL.getSearchReferrer` recognizes searches from these search engines (including international variations):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Description**

Le code suivant montre comment obtenir le référent de recherche pour n'importe quel moteur de recherche pris en charge. In this case, let's assume a user searched on the term "homes" from [!DNL Google] Canada ( `www.google.ca`). Ce code vous aidera à capturer ces termes de recherche et à les envoyer à Audience Manager.

**Code de base**

Basic code for getting the search referrer (from `google.com`, for example) looks like this:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Exemple de code de moteur de recherche répertorié**

In this case, let's assume that a user searched for the term "homes" from [!DNL Google] Canada ( `www.google.ca`). Note how the code prefixes the required `c_` parameter to search engine ( `c_se`) and search term ( `c_st`). `c_` est [un préfixe](../features/traits/trait-variable-prefixes.md) obligatoire qui identifie ces variables comme des variables définies par le client à Audience Manager.

<pre class="java"><code>var adobe_ dil = DIL. create ({partner : « <i>nom du partenaire</i> ») ; 
var search_ referrer = DIL. tools. getsearchreferrer () ; 
 
if (search_ referrer &amp; &amp; search_ referrer. valid) { 
 adobe_ dil. api. signals ({ 
 c_ se : se. name, 
 c_ st : se. keywords 
 }). submit () ; 
}</code>
</pre>

**Exemple de code de moteur de recherche non répertorié**

In this case, let's assume that a user searched for the term "homes" from `dogpile.com`. Because [!DNL Dogpile] is not supported by default, you can configure DIL to recognize this search engine and return the search terms to Audience Manager. Votre code peut ressembler à ce qui suit :

<pre class="java"><code>var adobe_ dil = DIL. create ({partner : « <i>nom du partenaire</i> ») ; 
var search_ referrer = DIL. tools. getsearchreferrer (document. referrer, { 
 Hostpattern : /dogpile\./, 
    queryParam:"q" 
}); 
 
if (search_referrer &amp;&amp; search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

## Map Key Values to Other Keys {#map-key-values}

Associez la valeur d'une paire clé-valeur à une autre clé.

<!-- 

c_dil_map_keys.xml

 -->

**Description**

In a key-value pair, the `c_` prefix appended to the key identifies the signal as customer-defined data. Les données définies par le client servent à cibler le site spécifique qui transmet les données lors d'un appel d'événement. Cependant, vous souhaitez parfois que ces informations soient disponibles pour toutes les propriétés de votre compte Audience Manager. To do this, map the value in a `c_` key-value pair to a platform level key. A platform level key is prefixed with `d_` and makes the signal available for targeting across all properties in your account.

Par exemple, vous collectez les données du code postal à partir d'un site particulier, mais vous souhaitez le cibler sur toutes les propriétés d'Audience Manager. To make the ZIP code available at the platform level, you could map your customer-defined ZIP code key (e.g. `c_zip`) to a platform defined key as shown below.

**Exemple de code**

Votre code peut ressembler à ce qui suit :

```java
var adobe_dil = DIL.create({ 
    partner : "adobe", 
    mappings : { 
        c_zip : 'd_zip', 
        d_key2 : 'h_dil_key2' 
    } 
}); 
adobe_dil.api.signals({c_zip : '10010'}).submit(); 
// Request will look like /event?c_zip=10010&d_zip=10010
```

>[!MORE_ LIKE_ THIS]
>
>* [Exigences en matière de préfixe pour les variables clés](https://marketing.adobe.com/resources/help/en_US/aam/r_tb_variable_prefixes.html)


## Traffic DIL in Google Tag Manager (GTM) {#traffic-dil-gtm}

Configurez et diffusez le code DIL avec une balise GTM.

<!-- 

t_dil_google_tagmanager.xml

 -->

This procedure assumes you have a [!DNL Google Tag Manager] account, some working knowledge of that product, and your Audience Manager `dil.js` file.

To traffic the `dil.js` file in GTM:

1. Créez un conteneur ou ouvrez un conteneur existant.
1. Ajoutez une nouvelle balise au conteneur.
1. Ouvrez la balise pour la modifier et :

   * Attribuez un nom à la balise.
   * Select **[!UICONTROL Custom HTML Tag]** from the **[!UICONTROL Tag Type]** drop-down list.
   * In the HTML field, place the [!UICONTROL DIL] code (library + the custom code) within script tags `<script>DIL code</script>`.
   * Cliquez sur **[!UICONTROL Save]**.

1. Publiez le conteneur.
1. Générez le code de balise de conteneur et placez-le sur votre inventaire.

>[!MORE_ LIKE_ THIS]
>
>* [Centre d'aide de Google Tag Manager](https://support.google.com/tagmanager#topic=3441530)

