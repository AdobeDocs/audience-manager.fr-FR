---
description: Exemples de code et descriptions pour des cas d'utilisation DIL spécifiques.
seo-description: Exemples de code et descriptions pour des cas d'utilisation DIL spécifiques.
seo-title: Cas d'utilisation DIL et exemples de code
solution: Audience Manager
title: Cas d'utilisation DIL et exemples de code
uuid: 27995 c 2 d -6572-438 e-af 99-b 5477 f 090 ae 9
translation-type: tm+mt
source-git-commit: 8763bff3960e2033951cf68e65f5ad44377b2917

---


# Cas d'utilisation DIL et exemples de code{#dil-use-cases-and-code-samples}

Exemples de code et descriptions pour des cas d'utilisation DIL spécifiques.

<!-- 

c_dil_use_case.xml

 -->

## Envoi d'éléments de données à Audience Manager avec DIL {#send-data-elements-dil}

Créez une variable d'objet qui envoie des informations sur les éléments de la page à Audience Manager. Ceci s'avère utile pour la collecte de données générales ou pour la collecte de données avec des variables Analytics.

<!-- 

c_dil_send_page_objects.xml

 -->

**Description**

Le code suivant montre comment collecter les données de la page et les envoyer à Audience Manager. [!UICONTROL DIL] Ces exemples utilisent une variable pour contenir des éléments de données dans une liste aplatie ou un tableau. Souvenez-vous de transmettre les variables sous forme [de paires clé-valeur](../reference/key-value-pairs-explained.md). Notez également le `c_` préfixe avant la clé dans la paire clé-valeur. Ce préfixe [obligatoire](../features/traits/trait-variable-prefixes.md) identifie les informations sous forme de données définies par l'utilisateur. Dans le premier exemple, vous devez ajouter manuellement `c_` à la clé. Dans le deuxième exemple, [!UICONTROL DIL] cela vous concerne automatiquement.

**Conserver les propriétés de valeur cohérentes**

Pensez à conserver les propriétés de valeur de la même façon lors de la transmission des données. Par exemple, si vous disposez de deux clés identiques avec des valeurs différentes, la valeur de la dernière paire clé-valeur est prioritaire sur les objets de valeur précédents. Par exemple, transmettre `color:blue` et `color:red` définir la valeur renvoyée sur rouge (écraser bleu).

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

Cet exemple avancé montre comment envoyer des données dans un objet à Audience Manager. Lorsque vous utilisez cette méthode, [!UICONTROL DIL] vous pouvez transmettre un objet comme paramètre de fonction dans la [!DNL signals()] méthode. [!UICONTROL DIL] Votre code peut ressembler à ce qui suit :

<pre class="java"><code>var my_ object = { 
 color : « bleu », 
 prix : « 900 »} 
; 
 
var sample_ dil = DIL. create ({partner : « <i>nom du partenaire</i> ») ; 
//load l'objet et ajoutez « c_ » à toutes les clés des paires clé-valeur et envoyez les données à audiencemanager. 
sample_ dil. api. signals (my_ object, « c_ »). submit () ;</code>
</pre>

**Exemple 3 : Envoi de données de page dans un tableau**

Dans ce cas, la variable `my_object` utilise un tableau pour contenir des données. Cet exemple repose sur les informations transmises par la méthode recommandée ci-dessus, mais ajoute un calque supplémentaire pour tenir compte d'un type et d'un modèle de produit. Votre code peut ressembler à ce qui suit :

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
 sample_ dil. api. signals (my_ objects [i], « c_ ») ; 
} 
sample_ dil. api. submit () ;</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [signaux](../dil/dil-instance-methods.md#signals)


## Capturer l'URL de référence {#capture-referring-url}

Capturez et envoyez une URL de référence à Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Cette méthode fonctionne uniquement lorsque les utilisateurs passent d'une page à une autre avec des protocoles similaires (HTTP/HTTPS). Par exemple, le navigateur conserve une URL de référence lorsque vous accédez à un autre site sécurisé depuis un site sécurisé. Les navigateurs ne conservent pas l'URL de référence lorsque vous passez d'un site sécurisé à un site non sécurisé. Ce comportement est une fonctionnalité normale du navigateur et ne peut pas être contourné [!UICONTROL DIL]par.

**Exemple de code**

Votre code peut ressembler à ce qui suit :

<pre class="java"><code>var adobe_ dil = DIL. create ({partner : « <i>nom du partenaire</i> ») ; 
adobe_ dil. api. signals ({d_ referer : document. referrer}). submit () ;</code>
</pre>

## Capturer les types de moteur de recherche et les termes de recherche de mots-clés {#capture-search-engine-types}

Envoyez des informations sur le type de moteur de recherche et les recherches de mots-clés dans Audience Manager.

>[!IMPORTANT]
>
>Cette section décrit les fonctionnalités héritées qui ne sont pas prises en charge par les dernières versions de DIL.

**Moteurs de recherche pris en charge**

Par défaut `DIL.getSearchReferrer` , reconnaît les recherches issues de ces moteurs de recherche (y compris les variations internationales) :

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Description**

Le code suivant montre comment obtenir le référent de recherche pour n'importe quel moteur de recherche pris en charge. Dans ce cas, supposons qu'un utilisateur ait recherché le terme « homes » du [!DNL Google] Canada ( `www.google.ca`). Ce code vous aidera à capturer ces termes de recherche et à les envoyer à Audience Manager.

**Code de base**

Le code de base pour obtenir le référent de recherche (par `google.com`exemple) ressemble à ceci :

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Exemple de code de moteur de recherche répertorié**

Dans ce cas, supposons qu'un utilisateur ait recherché le terme « homes » du [!DNL Google] Canada ( `www.google.ca`). Notez comment le code préfixe le paramètre requis `c_` au moteur de recherche ( `c_se`) et au terme de recherche ( `c_st`). `c_` est [un préfixe](../features/traits/trait-variable-prefixes.md) obligatoire qui identifie ces variables comme des variables définies par le client à Audience Manager.

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

Dans `dogpile.com`ce cas, supposons qu'un utilisateur a recherché le terme « homes ». Comme [!DNL Dogpile] la valeur par défaut n'est pas prise en charge, vous pouvez configurer DIL pour reconnaître ce moteur de recherche et renvoyer les termes de recherche à Audience Manager. Votre code peut ressembler à ce qui suit :

<pre class="java"><code>var adobe_ dil = DIL. create ({partner : « <i>nom du partenaire</i> ») ; 
var search_ referrer = DIL. tools. getsearchreferrer (document. referrer, { 
 Hostpattern : /dogpile\./, 
 Queryparam : « q »}) 
; 
 
if (search_ referrer &amp; &amp; search_ referrer. valid) { 
 adobe_ dil. api. signals ({ 
 c_ se : se. name, 
 c_ st : se. keywords 
 }). submit () ; 
}</code>
</pre>

## Mapper les valeurs clés à d'autres clés {#map-key-values}

Associez la valeur d'une paire clé-valeur à une autre clé.

<!-- 

c_dil_map_keys.xml

 -->

**Description**

Dans une paire clé-valeur, le `c_` préfixe ajouté à la clé identifie le signal comme données définies par le client. Les données définies par le client servent à cibler le site spécifique qui transmet les données lors d'un appel d'événement. Cependant, vous souhaitez parfois que ces informations soient disponibles pour toutes les propriétés de votre compte Audience Manager. Pour ce faire, mappez la valeur d'une `c_` paire clé-valeur à une clé de niveau plate-forme. Un préfixe de niveau plate-forme est ajouté `d_` et rend le signal disponible pour le ciblage sur toutes les propriétés de votre compte.

Par exemple, vous collectez les données du code postal à partir d'un site particulier, mais vous souhaitez le cibler sur toutes les propriétés d'Audience Manager. Pour rendre le code postal disponible au niveau de la plateforme, vous pouvez mapper la clé de code postal définie par le client (par exemple `c_zip`) à une clé définie de plate-forme comme illustré ci-dessous.

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


## Trafic DIL dans Google Tag Manager (GTM) {#traffic-dil-gtm}

Configurez et diffusez le code DIL avec une balise GTM.

<!-- 

t_dil_google_tagmanager.xml

 -->

Cette procédure suppose que vous disposez d' [!DNL Google Tag Manager] un compte, d'une connaissance approfondie de ce produit et de votre `dil.js` fichier Audience Manager.

Pour acheminer le `dil.js` fichier dans GTM :

1. Créez un conteneur ou ouvrez un conteneur existant.
1. Ajoutez une nouvelle balise au conteneur.
1. Ouvrez la balise pour la modifier et :

   * Attribuez un nom à la balise.
   * Select **[!UICONTROL Custom HTML Tag]** from the **[!UICONTROL Tag Type]** drop-down list.
   * Dans le champ HTML, placez le [!UICONTROL DIL] code (bibliothèque + le code personnalisé) dans les balises `<script>DIL code</script>`de script.
   * Cliquez sur **[!UICONTROL Save]**.

1. Publiez le conteneur.
1. Générez le code de balise de conteneur et placez-le sur votre inventaire.

>[!MORE_ LIKE_ THIS]
>
>* [Centre d'aide de Google Tag Manager](https://support.google.com/tagmanager#topic=3441530)

