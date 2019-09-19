---
description: Exemples de code et descriptions pour des cas d’utilisation DIL spécifiques.
seo-description: Exemples de code et descriptions pour des cas d’utilisation DIL spécifiques.
seo-title: Cas d’utilisation DIL et exemples de code
solution: Audience Manager
title: Cas d’utilisation DIL et exemples de code
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
translation-type: tm+mt
source-git-commit: 8763bff3960e2033951cf68e65f5ad44377b2917

---


# Cas d’utilisation DIL et exemples de code{#dil-use-cases-and-code-samples}

Exemples de code et descriptions pour des cas d’utilisation DIL spécifiques.

<!-- 

c_dil_use_case.xml

 -->

## Envoyer des éléments de données à Audience Manager avec DIL {#send-data-elements-dil}

Créez une variable d’objet qui envoie des informations sur les éléments de page à Audience Manager. Cela s’avère utile pour la collecte de données générales ou comme alternative à la collecte de données avec des variables Analytics.

<!-- 

c_dil_send_page_objects.xml

 -->

**Description**

Le code suivant montre comment collecter des données de page et les envoyer à Audience Manager avec [!UICONTROL DIL]. Ces exemples utilisent une variable pour contenir des éléments de données dans une liste plate ou un tableau. N’oubliez pas de transmettre les variables sous forme de paires [clé-valeur](../reference/key-value-pairs-explained.md). Notez également le `c_` préfixe avant la clé dans la paire clé-valeur. Ce préfixe [](../features/traits/trait-variable-prefixes.md) obligatoire identifie les informations comme données définies par l’utilisateur. Dans le premier exemple, vous devez ajouter manuellement `c_` à la clé. Dans le deuxième exemple, [!UICONTROL DIL] effectue cette opération automatiquement.

**Conserver la cohérence des propriétés de valeur**

N’oubliez pas de conserver les propriétés de valeur de la même manière lors de la transmission des données. Par exemple, si vous disposez de deux clés identiques avec des valeurs différentes, la valeur de la dernière paire clé-valeur est prioritaire sur les objets valeur précédents. Par exemple, la transmission `color:blue` et la `color:red` définition de la valeur renvoyée sur rouge (écrase le bleu).

**Exemple 1 : Envoyer des données sous forme de paires clé-valeur**

Cet exemple de base envoie les données de couleur et de prix à Audience Manager sous la forme de paires clé-valeur. Votre code peut ressembler à ce qui suit :

<pre class="&ldquo;java&rdquo;"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signaux({ c_color:"blue", c_price:"900" }); 
sample_dil.api.submit();
</code></pre>

**Exemple 2 : Envoyer des données dans un objet**

Cet exemple avancé montre comment envoyer des données dans un objet à Audience Manager. Lorsque vous utilisez cette méthode, [!UICONTROL DIL] vous permet de transmettre un objet en tant que paramètre de fonction dans la [!DNL signals()] méthode. [!UICONTROL DIL] Votre code peut ressembler à ce qui suit :

<pre class="java"><code>
var my_object = { color : "blue", prix : "900" }; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Chargez l’objet et ajoutez "c_" à toutes les clés des paires clé-valeur et envoyez les données à AudienceManager. 
sample_dil.api.signaux(my_object,"c_").submit();
</code></pre>

**Exemple 3 : Envoyer des données de page dans un tableau**

Dans ce cas, la variable `my_object` utilise un tableau pour contenir des données. Cet exemple s’appuie sur les informations transmises par la méthode recommandée ci-dessus, mais ajoute une couche supplémentaire pour prendre en compte un type de produit et un modèle. Votre code peut ressembler à ce qui suit :

<pre class="java"><code>
var my_object = [{ color : "blue", prix : "900" }, { type : "acura", modèle : "tl" }]; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
 
for (var i = 0; i &lt; my_object.length; i++) //Chargez l’objet et ajoutez "c_" à toutes les clés des paires clé-valeur.  
{ sample_dil.api.signaux(my_object[i], "c_"); 
} sample_dil.api.submit();
</code></pre>

>[!MORE_LIKE_This]
>
>* [signaux](../dil/dil-instance-methods.md#signals)


## Capturer l’URL de référence {#capture-referring-url}

Capturez et envoyez une URL de référence à Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Cette méthode fonctionne uniquement lorsque les utilisateurs passent d’une page à l’autre avec des protocoles similaires (HTTP ou HTTPS). Par exemple, le navigateur conserve une URL de référence lorsque vous naviguez d’un site sécurisé vers un autre site sécurisé. Les navigateurs ne conservent pas l’URL de référence lorsque vous passez d’un site sécurisé à un site non sécurisé. Ce comportement est une fonctionnalité normale du navigateur et ne peut pas être contourné par [!UICONTROL DIL].

**Exemple de code**

Votre code peut ressembler à ce qui suit :

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signaux({ d_referer) : document.referrer }).submit();
</code></pre>

## Capturer les types de moteurs de recherche et les termes de recherche de mots-clés {#capture-search-engine-types}

Envoyez des informations sur le type de moteur de recherche et les recherches de mots-clés à Audience Manager.

>[!IMPORTANT]
>
>Cette section décrit les fonctionnalités héritées, qui ne sont pas prises en charge dans les dernières versions de DIL.

**Moteurs de recherche pris en charge**

Par défaut, `DIL.getSearchReferrer` reconnaît les recherches issues de ces moteurs de recherche (y compris les variations internationales) :

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Description**

Le code suivant montre comment obtenir le référent de recherche pour l'un des moteurs de recherche pris en charge. Dans ce cas, supposons qu’un utilisateur ait effectué une recherche sur le terme "maisons" en provenance du [!DNL Google] Canada ( `www.google.ca`). Ce code vous aidera à capturer ces termes de recherche et à les envoyer à Audience Manager.

**Code de base**

Le code de base pour obtenir le référent de recherche (à partir `google.com`, par exemple,) ressemble à ceci :

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Exemple de code de moteur de recherche répertorié**

Dans ce cas, supposons qu’un utilisateur ait recherché le terme "maisons" à partir du [!DNL Google] Canada ( `www.google.ca`). Notez comment le code préfixe le `c_` paramètre requis au moteur de recherche ( `c_se`) et au terme de recherche ( `c_st`). `c_` est un préfixe [](../features/traits/trait-variable-prefixes.md) obligatoire qui identifie ces variables comme des variables définies par le client dans Audience Manager.

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(); 
 
if (search_referrer &amp;&amp; search_referrer.valid) { adobe_dil.api.signaux({ c_se : se.name, c_st : se.keywords }).submit(); 
}</code></pre>

**Exemple de code de moteur de recherche non répertorié**

Dans ce cas, supposons qu’un utilisateur ait recherché le terme "domiciles" `dogpile.com`. Comme [!DNL Dogpile] n’est pas pris en charge par défaut, vous pouvez configurer DIL pour reconnaître ce moteur de recherche et renvoyer les termes de recherche à Audience Manager. Votre code peut ressembler à ce qui suit :

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(document.referrer, { hostPattern:/dogpile\./, queryParam:"q" }); 
 
if (search_referrer &amp;&amp; search_referrer.valid) { adobe_dil.api.signaux({ c_se : se.name, c_st : se.keywords }).submit(); 
}</code></pre>

## Faire correspondre les valeurs clés aux autres clés {#map-key-values}

Associez la valeur d’une paire clé-valeur à une autre clé.

<!-- 

c_dil_map_keys.xml

 -->

**Description**

Dans une paire clé-valeur, le `c_` préfixe annexé à la clé identifie le signal comme des données définies par le client. Les données définies par le client sont utilisées pour le ciblage sur le site spécifique qui a transmis les données sur un appel d’événement. Cependant, vous souhaitez parfois que ces informations soient disponibles dans toutes les propriétés de votre compte Audience Manager. Pour ce faire, mappez la valeur d’une paire `c_` clé-valeur à une clé de niveau plate-forme. Une clé au niveau de la plate-forme est précédée d’un préfixe `d_` et rend le signal disponible pour le ciblage sur toutes les propriétés de votre compte.

Par exemple, vous collectez des données de code postal à partir d’un site particulier, mais souhaitez les cibler sur toutes vos propriétés Audience Manager. Pour rendre le code postal disponible au niveau de la plate-forme, vous pouvez mapper votre clé de code postal définie par le client (ex. `c_zip`) à une clé définie par une plateforme, comme illustré ci-dessous.

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

>[!MORE_LIKE_This]
>
>* [Préfixe requis pour les variables clés](https://marketing.adobe.com/resources/help/en_US/aam/r_tb_variable_prefixes.html)


## Trafic DIL dans Google Tag Manager (GTM) {#traffic-dil-gtm}

Configurez et diffusez DIL avec une balise GTM.

<!-- 

t_dil_google_tagmanager.xml

 -->

Cette procédure suppose que vous disposez d’un [!DNL Google Tag Manager] compte, d’une connaissance pratique de ce produit et de votre `dil.js` fichier Audience Manager.

Pour effectuer le trafic du `dil.js` fichier dans GTM :

1. Créez un conteneur ou ouvrez un conteneur existant.
1. Ajoutez une nouvelle balise au conteneur.
1. Ouvrez la balise pour la modifier et :

   * Nommez la balise .
   * Select **[!UICONTROL Custom HTML Tag]** from the **[!UICONTROL Tag Type]** drop-down list.
   * Dans le champ HTML, placez le [!UICONTROL DIL] code (bibliothèque + code personnalisé) dans les balises de script `<script>DIL code</script>`.
   * Cliquez sur **[!UICONTROL Save]**.

1. Publiez le conteneur.
1. Générez le code de balise de conteneur et importez-le dans votre inventaire.

>[!MORE_LIKE_This]
>
>* [Centre d’aide Google Tag Manager](https://support.google.com/tagmanager#topic=3441530)

