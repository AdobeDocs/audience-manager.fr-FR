---
description: Décrit les méthodes dans l’espace de noms DIL.modules. Ces modules permettent de collecter des données par programmation et d’utiliser des objets d’Audience Manager.
seo-description: Décrit les méthodes dans l’espace de noms DIL.modules. Ces modules permettent de collecter des données par programmation et d’utiliser des objets d’Audience Manager.
seo-title: Modules DIL
solution: Audience Manager
title: Modules DIL
uuid: d4c0d8dd-79f8-448e-b17c-c935415dd449
feature: Mise en oeuvre du DIL
exl-id: 4685bcbb-a63b-4613-bc94-54de9881966e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 4%

---

# Modules DIL{#dil-modules}

Décrit les méthodes dans l’espace de noms `DIL.modules`. Ces modules permettent de collecter des données par programmation et d’utiliser des objets d’Audience Manager.

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

Fonctionne avec [!UICONTROL DIL] pour envoyer des éléments de balise [!DNL Analytics] (variables, props, eVars, etc.) à l’Audience Manager. Renvoie les données d’une liste séparée par des virgules. Disponible dans la version 2.6.

**Signature de fonction :** `DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>Vous devez placer ce code sur la page *avant* la fonction `s.t();`.

<!-- 

r_dil_sc_init.xml

 -->

**Paramètres**

<table id="table_A8CF8D298D944A608E2F49719F2732A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> variables </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> names </code> </td> 
   <td colname="col2"> Chaîne </td> 
   <td colname="col3"> <p>Tableau de chaînes qui contient des variables Analytics <span class="keyword"> non énumérées comme </span> <code> pageName </code>, <code> channel </code>, <code> campaign </code>, <code> product </code>, etc. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> iteratedNames </code> </td> 
   <td colname="col2"> Objet </td> 
   <td colname="col3"> <p>Tableau d’objets qui contient des variables Analytics <span class="keyword"> énumérées </span> telles que props et evars (par ex. <code> prop1 </code>, <code> prop2 </code>, <code> evar3 </code>, <code> evar4 </code>). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> maxIndex </code> </td> 
   <td colname="col2"> Entier </td> 
   <td colname="col3"> <p>Indique le nombre de noms itérés à renvoyer. Par exemple, pour renvoyer deux props ou evars, définissez <code> maxIndex:2 </code>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> siteCatalystReportingSuite </code> </td> 
   <td colname="col2"> Objet </td> 
   <td colname="col3"> <p>Objet représentant l’objet <span class="keyword"> Analytics </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dilInstance </code> </td> 
   <td colname="col2"> Objet </td> 
   <td colname="col3"> <p>Objet représentant le DIL <span class="wintitle"> </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> options </code> </td> 
   <td colname="col2"> Objet </td> 
   <td colname="col3"> <p>Options supplémentaires : </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> replaceContextDataPeriodsWith </code> </p> <p>Si vous n’indiquez rien d’autre, les points sont remplacés par le trait de soulignement par défaut ( _ ). </p> <p>Par exemple, <code> s.contextData = {abc.def = '123'} </code>renvoie <code> c_contextData_abc_def=123 </code> dans la chaîne de requête de l’appel d’événement. </p> <p>Cette option est disponible uniquement dans <span class="wintitle"> DIL </span> version 5.0 ou ultérieure. </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> filterFromContextVariables </code> </p> <p>Par exemple, <code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code> entraîne le filtrage du tableau de chaînes à partir de la collecte de données de données contextuelles. Cette option exclut les informations d’identification personnelle (PII). </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Données capturées par siteCatalyst.init**

Cette fonction renvoie des détails sur les propriétés [!DNL Analytics] suivantes :

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `eVar` (1 à 250)
* `prop` (1 à 75)
* `pe`
* `pev1`
* `pev2`
* `pev3`

**Exemple de code**

Ce code crée une liste séparée par des virgules d’événements [!DNL Analytics] (props, eVars, etc.) si des valeurs existent pour elles.

```
// Get the Site Catalyst object instance: 
var s = s_gi(s_account); 
  
// Instantiate DIL code: 
var scDil = DIL.create({ 
        partner: 'adobe', 
        containerNSID: 5 
}); 
 
// Use the module: 
DIL.modules.siteCatalyst.init(s, scDil, { 
        //Specify the Site Catalyst variables you want to capture: 
        names: ['pageName', 'channel', 'campaign'], 
        //Use this to create iterated variable names: 
        iteratedNames: [{ 
               name: 'eVar', 
               maxIndex: 75 
        }, { 
               name: 'prop', 
               maxIndex: 75 
        }] 
});
```

Pour suivre tous les points de données [!DNL Analytics] surveillés sans la fonction supplémentaire affichée ci-dessus, appelez `siteCatalyst.init` seul comme suit :

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

La fonction `GA.submitUniversalAnalytics();` envoie à l’Audience Manager des données provenant de la [!DNL Universal Analytics] de Google. Cette fonction [!UICONTROL DIL] est conçue pour fonctionner avec `analytics.js`, qui est la dernière bibliothèque de code pour Google [!DNL Universal Analytics].

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] ne dispose d’aucun aperçu ou contrôle sur la bibliothèque de  `analytics.js` code Google. Vous devez vérifier que la collecte de données [!UICONTROL DIL] fonctionne toujours si ou lorsque Google publie de nouvelles versions de `analytics.js`.
   >
   >
* Vous ne pouvez pas utiliser `GA.submitUniversalAnalytics();` si vous utilisez toujours le code de suivi d’analyse hérité de Google (par exemple, `ga.js` ou `dc.js`). Voir [GA.init](../dil/dil-modules.md#ga-init) à la place.

>



**Signature de fonction :** `DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**Propriétés**

La fonction `GA.submitUniversalAnalytics();` accepte les propriétés suivantes.

<table id="table_8E0C1E4B17D541259E72B88F02BE4503"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Propriété </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> gaObject </code> </p> </td> 
   <td colname="col2"> <p>Variable globale pour votre instance de <span class="keyword"> Google Analytics </span>. Il s’agit généralement de <code> ga </code> par défaut, sauf si vous avez personnalisé votre code <span class="keyword"> Google Analytics </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance </code> </p> </td> 
   <td colname="col2"> <p>La variable qui représente votre instance du DIL <span class="wintitle"> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> internalPropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>(Facultatif)</i> Dans la  <code> analytics.js </code> bibliothèque, la propriété interne est la variable minimisée  <code> 'b' </code>. Cette variable contient les données <span class="keyword"> Google Analytics </span>. </p> <p>Cette propriété est facultative, car vous n’avez pas besoin de la définir, sauf si Google modifie le nom de sa variable interne. Par exemple, si cette variable minimisée est remplacée par <code> 'a' </code>, appelez <code> GA.submitUniversalAnalytics(); </code> comme suit : </p> <p> <code> DIL.modules.GAsubmitUniversalAnalytics(ga, DilInstance, 'a'); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemple**

N’oubliez pas de définir d’abord l’objet [!DNL Google Analytics] `ga` avant d’appeler [!UICONTROL DIL] et `GA.submitUniversalAnalytics();`. Votre code pourrait ressembler à ceci :

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

## GA.init {#ga-init}

La fonction `GA.init()` envoie à l’Audience Manager des données de la version héritée/obsolète de [!DNL Google Analytics].

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` fonctionne uniquement avec le code de suivi Analytics hérité de Google,  `ga.js` ou  `dc.js`. Vous ne pouvez pas appeler cette fonction [!UICONTROL DIL] si vous utilisez `analytics.js`, qui est la dernière bibliothèque de code pour Google [!DNL Universal Analytics]. [!DNL Audience Manager] Les clients qui utilisent  [!UICONTROL DIL] et  [!DNL Universal Analytics] doivent voir  [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics).

**Signature de fonction :** `DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**Paramètres**

| Nom | Type | Description |
|---|---|---|
| `_gaq` | Tableau | Tableau contenant des commandes GA. |
| `dilInstance` | Objet | Objet contenant l’instance de DIL. |
| `trackVars` | Objet | *(Facultatif)* Objet constitué de la  `names` propriété. Cette propriété est un tableau de noms de commande GA dont vous souhaitez effectuer le suivi. |

**Appels de fonction GA pris en charge**

Par défaut, `GA.init` capture les données à partir des fonctions suivantes :

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL crée des clés pour les données GA**

L’Audience Manager accepte les données sous la forme de paires clé-valeur, tandis que la disponibilité générale fonctionne avec les éléments d’un tableau. Pour utiliser les données GA, [!UICONTROL DIL] crée automatiquement une paire clé-valeur et forme une clé comme celle-ci : `c_ <key name>`. En outre, les éléments des tableaux GA apparaissent dans un ordre spécifique. Par conséquent, vous devez fournir tous les paramètres dans cet ordre, même s’ils ne contiennent aucune donnée. [!UICONTROL DIL] mappe les clés pour les méthodes GA suivantes :

```js
// Tracking Social Interactions 
_gaq.push(['_trackSocial', 
    'facebook',                        // c_socialNetwork 
    'like',                            // c_socialAction 
    'https://www.adobe.com/cool.php',   // c_socialTarget 
    '/cool.php'                        // c_socialPagePath 
]);  
 
// Tracking a Transaction 
_gaq.push(['_addTrans', 
   '1234',           // c_transOrderId 
   'Womens Apparel', // c_transAfflication 
   '28.28',          // c_transTotal 
   '1.29',           // c_tranTax 
   '15.00',          // c_transShipping 
   'San Jose',       // c_transCity 
   'California',     // c_transState 
   'USA'             // c_transCountry 
]); 
 
// Tracking an item 
_gaq.push(['_addItem', 
   '1234',           // c_itemOrderId=1234 
   'DD44',           // c_itemSku 
   'T-Shirt',        // c_itemName 
   'Olive Medium',   // c_itemCategory 
   '11.99',          // c_itemPrice 
   '1'               // c_itenQuantity 
]);
```

**Exemple de code**

```js
// DIL JavaScript library needs to be loaded and executed here 
var dilInstance = DIL.create({ 
    partner : "adobe" 
}); 
 
// Assume ga.js has not loaded 
var _gaq = _gaq || []; 
_gaq.push( 
  ['_setAccount', 'UA-XXXXX-X'], 
  ['_setDomainName', 'example.com'], 
  ['_setCustomVar', 1, 'Section', 'Life & Style', 3], 
  ['_trackPageview'] 
); 
_gaq.push([ 
  '_addItem', 
  '1234',         // order ID - necessary to associate item with transaction 
  'DD44',         // SKU/code - required 
  'T-Shirt',      // product name - necessary to associate revenue with product 
  'Olive Medium', // category or variation 
  '11.99',        // unit price - required 
  '1'             // quantity - required 
]); 
```

Pour effectuer le suivi de toutes les mesures de disponibilité générale surveillées sans la fonction supplémentaire affichée ci-dessus, appelez `GA.init` seul comme suit :

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**Exemple d’appel d’événement**

L’appel d’événement d’URL à l’Audience Manager peut ressembler à ceci :

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORELIKETHIS]
>
>* [Code de suivi des Google Analytics](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [Terminer la mise à niveau Web : ga.js/dc.js à analytics.js](https://developers.google.com/analytics/devguides/collection/upgrade)
>* [Ajout d’analytics.js à votre site](https://developers.google.com/analytics/devguides/collection/analyticsjs/)
>* [Référence des méthodes d’objet ga](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)

