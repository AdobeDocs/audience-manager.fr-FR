---
description: Exemples et descriptions de code pour des cas d’utilisation de DIL spécifiques.
seo-description: Exemples et descriptions de code pour des cas d’utilisation de DIL spécifiques.
seo-title: Cas d’utilisation DIL et exemples de code
solution: Audience Manager
title: Cas d’utilisation DIL et exemples de code
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: Mise en oeuvre du DIL
exl-id: 001710be-b377-460a-9e29-7268d25a6305
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 3%

---

# Cas d’utilisation DIL et exemples de code{#dil-use-cases-and-code-samples}

Exemples et descriptions de code pour des cas d’utilisation de DIL spécifiques.

<!-- 

c_dil_use_case.xml

 -->

## Envoyer des éléments de données à l’Audience Manager avec DIL {#send-data-elements-dil}

Créez une variable d’objet qui envoie des informations sur les éléments de page à l’Audience Manager. Cela s’avère utile pour la collecte générale des données ou comme alternative à la collecte de données avec des variables Analytics.

<!-- 

c_dil_send_page_objects.xml

 -->

**Description**

Le code suivant montre comment collecter des données de page et les envoyer à l’Audience Manager avec [!UICONTROL DIL]. Ces exemples utilisent une variable pour contenir des éléments de données dans une liste plate ou un tableau. Pour rappel, transmettez les variables sous la forme de [paires clé-valeur](../reference/key-value-pairs-explained.md). Notez également le préfixe `c_` devant la clé dans la paire clé-valeur. Ce [préfixe requis](../features/traits/trait-variable-prefixes.md) identifie les informations en tant que données définies par l’utilisateur. Dans le premier exemple, vous devez ajouter manuellement `c_` à la clé. Dans le deuxième exemple, [!UICONTROL DIL] le fait automatiquement pour vous.

**Conserver les propriétés de valeur cohérentes**

N’oubliez pas de conserver les propriétés de valeur identiques lors de la transmission de données. Par exemple, si vous disposez de deux clés identiques avec des valeurs différentes, la valeur de la dernière paire clé-valeur est prioritaire sur les objets valeur précédents. Par exemple, transmettre `color:blue` et `color:red` définit la valeur renvoyée sur rouge (remplace bleu).

**Exemple 1 : Envoi de données en tant que paires clé-valeur**

Cet exemple de base envoie des données de couleur et de prix à l’Audience Manager sous la forme de paires clé-valeur. Votre code pourrait ressembler à ce qui suit :

<pre class="&ldquo;java&rdquo;"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
</code></pre>

**Exemple 2 : Envoi de données dans un objet**

Cet exemple avancé montre comment envoyer des données dans un objet à l’Audience Manager. Lorsque vous utilisez cette méthode, [!UICONTROL DIL] vous permet de transmettre un objet en tant que paramètre de fonction dans la méthode [!DNL signals()]. [!UICONTROL DIL] Votre code pourrait ressembler à ce qui suit :

<pre class="java"><code>
var my_object = { 
   color : "blue", 
   price : "900" 
}; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**Exemple 3 : Envoi de données de page dans un tableau**

Dans ce cas, la variable `my_object` utilise un tableau pour contenir des données. Cet exemple s’appuie sur les informations transmises par la méthode recommandée ci-dessus, mais ajoute une couche supplémentaire pour s’adapter à un type de produit et à un modèle. Votre code pourrait ressembler à ce qui suit :

<pre class="java"><code>
var my_objects = [{ 
   color : "blue", 
   price : "900" 
}, { 
   type : "acura", 
   model : "tl" 
}]; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
 
for (var i = 0; i < my_objects.length; i++) 
//Load the object and append "c_" to all the keys in the key-value pairs.  
{ 
    sample_dil.api.signals(my_objects[i], "c_"); 
} 
sample_dil.api.submit();
</code></pre>

## Capturer l’URL de référence {#capture-referring-url}

Capturez et envoyez une URL de référence à l’Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Cette méthode fonctionne uniquement lorsque les utilisateurs se déplacent entre des pages avec des protocoles similaires (HTTP ou HTTPS). Par exemple, le navigateur conserve une URL de référence lorsque vous naviguez d’un site sécurisé vers un autre site sécurisé. Les navigateurs ne conservent pas l’URL de référence lorsque vous vous déplacez entre des sites sécurisés et non sécurisés. Ce comportement est une fonctionnalité normale du navigateur et ne peut pas être contourné par [!UICONTROL DIL].

**Exemple de code**

Votre code pourrait ressembler à ce qui suit :

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## Capturer les types de moteur de recherche et les termes de recherche de mots-clés {#capture-search-engine-types}

Envoyez des informations sur le type de moteur de recherche et les recherches de mots-clés à Audience Manager.

>[!IMPORTANT]
>
>Cette section décrit les fonctionnalités héritées, qui ne sont pas prises en charge dans les dernières versions de DIL.

**Moteurs de recherche pris en charge**

Par défaut, `DIL.getSearchReferrer` reconnaît les recherches issues de ces moteurs de recherche (y compris les variantes internationales) :

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Description**

Le code suivant indique comment obtenir le référent de recherche pour l’un des moteurs de recherche pris en charge. Dans ce cas, supposons qu’un utilisateur ait effectué une recherche sur le terme &quot;domiciles&quot; à partir de [!DNL Google] Canada ( `www.google.ca`). Ce code vous aidera à capturer ces termes de recherche et à les envoyer à l’Audience Manager.

**Code de base**

Le code de base pour obtenir le référent de recherche (à partir de `google.com`, par exemple) ressemble à ceci :

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Exemple de code de moteur de recherche répertorié**

Dans ce cas, supposons qu’un utilisateur ait recherché le terme &quot;domiciles&quot; à partir de [!DNL Google] Canada ( `www.google.ca`). Notez comment le code préfixe le paramètre `c_` requis au moteur de recherche ( `c_se`) et au terme de recherche ( `c_st`). `c_` est un préfixe  [obligatoire ](../features/traits/trait-variable-prefixes.md) qui identifie ces variables en tant que variables définies par le client à Audience Manager.

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(); 
 
if (search_referrer && search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

**Exemple de code de moteur de recherche non répertorié**

Dans ce cas, supposons qu’un utilisateur ait recherché le terme &quot;domiciles&quot; à partir de `dogpile.com`. Comme [!DNL Dogpile] n’est pas pris en charge par défaut, vous pouvez configurer DIL pour qu’il reconnaisse ce moteur de recherche et renvoie les termes de recherche à l’Audience Manager. Votre code pourrait ressembler à ce qui suit :

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(document.referrer, {  
    hostPattern:/dogpile\./, 
    queryParam:"q" 
}); 
 
if (search_referrer && search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

## Mise en correspondance des valeurs de clés avec d’autres clés {#map-key-values}

Associez la valeur d’une paire clé-valeur à une autre clé.

<!-- 

c_dil_map_keys.xml

 -->

**Description**

Dans une paire clé-valeur, le préfixe `c_` ajouté à la clé identifie le signal comme données définies par le client. Les données définies par le client sont utilisées pour le ciblage sur le site spécifique qui a transmis les données lors d’un appel d’événement. Cependant, il arrive que vous souhaitiez que ces informations soient disponibles dans toutes les propriétés de votre compte d’Audience Manager. Pour ce faire, mappez la valeur d’une paire `c_` clé-valeur à une clé de niveau plate-forme. Une clé au niveau de la plateforme est précédée du préfixe `d_` et rend le signal disponible pour le ciblage sur toutes les propriétés de votre compte.

Par exemple, vous collectez des données de code postal d’un site particulier, mais souhaitez les cibler sur toutes les propriétés de votre Audience Manager. Pour rendre le code postal disponible au niveau de la plateforme, vous pouvez mapper votre clé de code postal définie par le client (par exemple, `c_zip`) vers une clé définie par la plateforme comme illustré ci-dessous.

**Exemple de code**

Votre code pourrait ressembler à ce qui suit :

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

## DIL de trafic dans Google Tag Manager (GTM) {#traffic-dil-gtm}

Configurez et servez le DIL avec une balise GTM.

<!-- 

t_dil_google_tagmanager.xml

 -->

Cette procédure suppose que vous disposez d’un compte [!DNL Google Tag Manager], d’une connaissance pratique de ce produit et de votre fichier `dil.js` d’Audience Manager.

Pour traiter le fichier `dil.js` dans GTM, procédez comme suit :

1. Créez un conteneur ou ouvrez un conteneur existant.
1. Ajoutez une nouvelle balise au conteneur.
1. Ouvrez la balise pour la modifier et :

   * Attribuez un nom à la balise.
   * Sélectionnez **[!UICONTROL Custom HTML Tag]** dans la liste déroulante **[!UICONTROL Tag Type]**.
   * Dans le champ HTML, placez le code [!UICONTROL DIL] (bibliothèque + code personnalisé) dans les balises de script `<script>DIL code</script>`.
   * Cliquez sur **[!UICONTROL Save]**.

1. Publiez le conteneur.
1. Générez le code de balise conteneur et placez-le dans votre inventaire.

>[!MORELIKETHIS]
>
>* [Centre d’aide de Google Tag Manager](https://support.google.com/tagmanager#topic=3441530)
>* [Signaux](../dil/dil-instance-methods.md#signals)
* [Exigences de préfixe pour les variables clés](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/traits/trait-variable-prefixes.html#prefix-requirements-for-key-variables)

