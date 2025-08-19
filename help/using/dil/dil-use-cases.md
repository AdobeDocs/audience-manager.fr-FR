---
description: Exemples de code et descriptions pour des cas d’utilisation DIL spécifiques.
seo-description: Code samples and descriptions for specific DIL use cases.
seo-title: DIL Use Cases and Code Samples
solution: Audience Manager
title: Cas d’utilisation et exemples de code DIL
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: DIL Implementation
exl-id: 001710be-b377-460a-9e29-7268d25a6305
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 1%

---

# Cas d’utilisation et exemples de code DIL{#dil-use-cases-and-code-samples}

>[!WARNING]
>
>Depuis juillet 2023, Adobe a interrompu le développement du [!DNL Data Integration Library (DIL)] et de l’extension [!DNL DIL].
>
>Les clients existants peuvent continuer à utiliser leur implémentation [!DNL DIL]. Cependant, Adobe ne développera pas d’[!DNL DIL] au-delà de ce point. Nous recommandons aux clients d’évaluer [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) pour leur stratégie de collecte de données à long terme.
>
>Les clients qui souhaitent implémenter de nouvelles intégrations de collecte de données après juillet 2023 doivent utiliser [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) à la place.

Exemples de code et descriptions pour des cas d’utilisation DIL spécifiques.

<!-- 

c_dil_use_case.xml

 -->

## Envoi d’éléments de données à Audience Manager avec DIL {#send-data-elements-dil}

Créez une variable objet qui envoie des informations sur les éléments de page à Audience Manager. Cela s’avère utile pour la collecte de données générale ou comme alternative à la collecte de données avec des variables Analytics.

<!-- 

c_dil_send_page_objects.xml

 -->

**Description**

Le code suivant montre comment collecter des données de page et les envoyer à Audience Manager avec [!UICONTROL DIL]. Ces exemples utilisent une variable pour contenir des éléments de données dans une liste plate ou un tableau. N’oubliez pas de transmettre des variables en tant que [paires clé-valeur](../reference/key-value-pairs-explained.md). Notez également le préfixe `c_` devant la clé dans la paire clé-valeur. Ce [préfixe obligatoire](../features/traits/trait-variable-prefixes.md) identifie les informations en tant que données définies par l’utilisateur. Dans le premier exemple, vous devez ajouter manuellement des `c_` à la clé. Dans le deuxième exemple, [!UICONTROL DIL] effectue automatiquement cette opération pour vous.

**Garder les propriétés de valeur cohérentes**

N’oubliez pas de conserver les propriétés de valeur identiques lors de la transmission des données. Par exemple, si vous disposez de deux clés identiques avec des valeurs différentes, la valeur de la dernière paire clé-valeur est prioritaire sur les objets valeur précédents. Par exemple, transmettre `color:blue` et `color:red` définit la valeur renvoyée sur rouge (remplace le bleu).

**Exemple 1 : envoyer des données sous forme de paires clé-valeur**

Cet exemple de base envoie des données de couleur et de prix à Audience Manager sous la forme de paires clé-valeur. Votre code peut ressembler à ce qui suit :

<pre class="java"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals(&lbrace; 
   c_color:"blue", 
   c_price:"900" 
&rbrace;); 
sample_dil.api.submit();
</code></pre>

**Exemple 2 : envoyer des données dans un objet**

Cet exemple avancé montre comment envoyer des données d’un objet à Audience Manager. Lorsque vous utilisez cette méthode, [!UICONTROL DIL] vous permet de transmettre un objet en tant que paramètre de fonction dans la méthode [!DNL signals()]. [!UICONTROL DIL] Votre code peut ressembler à ce qui suit :

<pre class="java"><code>
var my_object = &lbrace; 
   color : "blue", 
   price : "900" 
&rbrace;; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**Exemple 3 : envoi de données de page dans un tableau**

Dans ce cas, la variable `my_object` utilise un tableau pour contenir les données. Cet exemple s’appuie sur les informations transmises par la méthode recommandée ci-dessus, mais ajoute une couche supplémentaire pour s’adapter à un type de produit et à un modèle. Votre code peut ressembler à ce qui suit :

<pre class="java"><code>
var my_objects = &lbrack;&lbrace; 
   color : "blue", 
   price : "900" 
&rbrace;, &lbrace; 
   type : "acura", 
   model : "tl" 
&rbrace;&rbrack;; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
 
for (var i = 0; i < my_objects.length; i++) 
//Load the object and append "c_" to all the keys in the key-value pairs.  
&lbrace; 
    sample_dil.api.signals(my_objects[i], "c_"); 
&rbrace; 
sample_dil.api.submit();
</code></pre>

## Capturer l’URL de référence {#capture-referring-url}

Capturez et envoyez une URL de référence à Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Cette méthode ne fonctionne que lorsque les utilisateurs passent d’une page à l’autre avec des protocoles similaires (HTTP ou HTTPS). Par exemple, le navigateur conserve une URL de référence lorsque vous naviguez d’un site sécurisé à un autre site sécurisé. Les navigateurs ne conservent pas l’URL de référence lorsque vous passez d’un site sécurisé à un site non sécurisé. Ce comportement est une fonctionnalité normale du navigateur et ne peut pas être contourné par [!UICONTROL DIL].

**Exemple de code**

Votre code peut ressembler à ce qui suit :

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## Capture des types de moteurs de recherche et des termes de recherche par mot-clé {#capture-search-engine-types}

Envoyez à Audience Manager des informations sur les recherches par type de moteur de recherche et par mot-clé.

>[!IMPORTANT]
>
>Cette section décrit les fonctionnalités héritées, qui ne sont pas prises en charge dans les dernières versions de DIL.

**Moteurs de recherche pris en charge**

Par défaut, `DIL.getSearchReferrer` reconnaît les recherches effectuées à partir de ces moteurs de recherche (y compris les variations internationales) :

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Description**

Le code suivant montre comment obtenir le référent de recherche pour l’un des moteurs de recherche pris en charge. Dans ce cas, supposons qu&#39;un utilisateur ait effectué une recherche sur le terme « maisons » de [!DNL Google] Canada ( `www.google.ca`). Ce code vous aidera à capturer ces termes de recherche et à les envoyer à Audience Manager.

**Code de base**

Le code de base pour obtenir le référent de recherche (à partir de `google.com`, par exemple) ressemble à ceci :

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Exemple de code de moteur de recherche répertorié**

Dans ce cas, supposons qu&#39;un utilisateur ait recherché le terme « maisons » de [!DNL Google] Canada ( `www.google.ca`). Notez comment le code préfixe le paramètre `c_` requis au moteur de recherche ( `c_se`) et au terme de recherche ( `c_st`). `c_` est un [préfixe obligatoire](../features/traits/trait-variable-prefixes.md) qui identifie ces variables comme des variables définies par le client ou la cliente pour Audience Manager.

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(); 
 
if (search_referrer && search_referrer.valid) &lbrace; 
  adobe_dil.api.signals(&lbrace; 
    c_se : se.name, 
    c_st : se.keywords 
  &rbrace;).submit(); 
&rbrace;
</code></pre>

**Exemple de code de moteur de recherche non répertorié**

Dans ce cas, supposons qu’un utilisateur ait recherché le terme « maisons » dans `dogpile.com`. Étant donné que [!DNL Dogpile] n’est pas pris en charge par défaut, vous pouvez configurer DIL pour reconnaître ce moteur de recherche et renvoyer les termes de recherche à Audience Manager. Votre code peut ressembler à ce qui suit :

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(document.referrer, &lbrace;  
    hostPattern:/dogpile\./, 
    queryParam:"q" 
&rbrace;); 
 
if (search_referrer && search_referrer.valid) &lbrace; 
  adobe_dil.api.signals(&lbrace; 
    c_se : se.name, 
    c_st : se.keywords 
  &rbrace;).submit(); 
&rbrace;
</code></pre>

## Mapper des valeurs de clé à d’autres clés {#map-key-values}

Associez la valeur d’une paire clé-valeur à une autre clé.

<!-- 

c_dil_map_keys.xml

 -->

**Description**

Dans une paire clé-valeur, le préfixe `c_` ajouté à la clé identifie le signal en tant que données définies par le client. Les données définies par le client ou la cliente sont utilisées pour le ciblage sur le site spécifique qui a transmis des données lors d’un appel d’événement. Cependant, vous souhaitez parfois que ces informations soient disponibles dans toutes les propriétés de votre compte Audience Manager. Pour ce faire, mappez la valeur d’une paire clé-valeur `c_` à une clé au niveau de la plateforme. Une clé au niveau de la plateforme est précédée de `d_` et rend le signal disponible pour le ciblage sur toutes les propriétés de votre compte.

Par exemple, vous collectez des données de code postal d’un site particulier, mais souhaitez les cibler sur toutes vos propriétés Audience Manager. Pour rendre le code postal disponible au niveau de la plateforme, vous pouvez mapper votre clé de code postal définie par le client (par exemple, `c_zip`) à une clé définie par la plateforme, comme illustré ci-dessous.

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

## DIL de trafic dans Google Tag Manager (GTM) {#traffic-dil-gtm}

Configurez et servez DIL avec une balise GTM.

<!-- 

t_dil_google_tagmanager.xml

 -->

Cette procédure suppose que vous disposez d’un compte [!DNL Google Tag Manager], d’une certaine connaissance pratique de ce produit et de votre fichier `dil.js` Audience Manager.

Pour transférer le fichier `dil.js` dans GTM, procédez comme suit :

1. Créez un nouveau conteneur ou ouvrez un conteneur existant.
1. Ajoutez une nouvelle balise au conteneur .
1. Ouvrez la balise pour la modifier et :

   * Nommez la balise .
   * Sélectionnez **[!UICONTROL Custom HTML Tag]** dans la liste déroulante **[!UICONTROL Tag Type]** .
   * Dans le champ HTML , placez le code [!UICONTROL DIL] (bibliothèque + le code personnalisé) dans les balises de script `<script>DIL code</script>`.
   * Cliquez sur **[!UICONTROL Save]**.

1. Publiez le conteneur .
1. Générez un code de balise conteneur et placez-le sur votre inventaire.

>[!MORELIKETHIS]
>
>* [Centre D’Aide Du Gestionnaire De Balises Google](https://support.google.com/tagmanager#topic=3441530)
>* [Signaux ](../dil/dil-instance-methods.md#signals)
>* [Exigences de préfixe pour les variables clés](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/traits/trait-variable-prefixes.html#prefix-requirements-for-key-variables)
