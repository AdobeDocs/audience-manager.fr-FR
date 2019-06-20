---
description: Exemples de création d'expressions dans l'éditeur de code du Générateur d'expression.
seo-description: Exemples de création d'expressions dans l'éditeur de code du Générateur d'expression.
seo-title: Exemples d'expressions avec opérateurs booléens et de comparaison
solution: Audience Manager
title: Exemples d'expressions avec opérateurs booléens et de comparaison
uuid: ee 74 c 376-2099-4816-8694-43 f 58845 a 0 ac
translation-type: tm+mt
source-git-commit: 92b75773d2bbe2f635d84bd5bffe625d2023b6cf

---


# Sample Expressions With Boolean and Comparison Operators {#sample-expressions-with-boolean-and-comparison-operators}

Examples you can refer to for creating expressions in the [!UICONTROL Expression Builder] code editor.

## Code Samples Overview {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

Create your own trait rules with the [!UICONTROL Expression Builder] code editor. Les exemples suivants peuvent vous aider à démarrer. Some of the examples preface the *`key`* variable with `c_` to identify it as a user-defined variable. Include the `c_` prefix (or any other naming convention) for *`key`* variable if your event calls send data to [!DNL Audience Manager] using that syntax.

## Boolean Expressions {#boolean-expressions}

### Exemple ET

The rule establishes trait qualification requirements using Boolean [!UICONTROL AND] operators.

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exemple de code </th> 
   <th colname="col2" class="entry"> Pour être éligible, un visiteur doit </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_ make = = « A ») AND (c_ model = = « B ») AND (c_ search = = « 1 »)</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">Recherchez un formulaire et un modèle spécifiques. </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">Recherchez le produit à partir d'une page de résultats de recherche (recherche = « 1 » ou « vrai »). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Exemple OU

This rule establishes trait qualification requirements using [!DNL Boolean] [!UICONTROL OR] and [!UICONTROL AND] operators.

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exemple de code </th> 
   <th colname="col2" class="entry"> Pour être éligible, un visiteur doit </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a = = « 1 » OR b = = « 1 ») ET (c = = « new »)</code> </td> 
   <td colname="col2"> Meet the conditions set by variables <code><i>a </i></code> or <code><i>b </i></code> and <code><i>c </i></code>. </td> 
  </tr> 
 </tbody> 
</table>

## Exemple de plage avec plus grand que, inférieur à, égal à

Cette règle définit les exigences de qualification des caractéristiques à l&#39;aide d&#39;une plage.

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exemple de code </th> 
   <th colname="col2" class="entry"> Pour être éligible, un visiteur doit </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(prix &gt; = 1.00 AND prix &lt; = 100,00)</code> </td> 
   <td colname="col2"> Renseignez les conditions de prix comprises entre 1.00 et 100.00. </td> 
  </tr> 
 </tbody> 
</table>