---
description: Exemples auxquels vous pouvez vous référer pour la création d’expressions dans l’éditeur de code du Générateur d’expression.
seo-description: Exemples auxquels vous pouvez vous référer pour la création d’expressions dans l’éditeur de code du Générateur d’expression.
seo-title: Exemples d’expressions avec opérateurs booléens et de comparaison
solution: Audience Manager
title: Exemples d’expressions avec opérateurs booléens et de comparaison
uuid: ee74c376-2099-4816-8694-43f58845a0ac
translation-type: tm+mt
source-git-commit: 92b75773d2bbe2f635d84bd5bffe625d2023b6cf

---


# Exemples d’expressions avec opérateurs booléens et de comparaison {#sample-expressions-with-boolean-and-comparison-operators}

Exemples auxquels vous pouvez vous référer pour la création d’expressions dans l’éditeur de [!UICONTROL Expression Builder] code.

## Présentation des exemples de code {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

Créez vos propres règles de caractéristiques avec l’éditeur de [!UICONTROL Expression Builder] code. Les exemples suivants peuvent vous aider à démarrer. Certains exemples préfigurent la *`key`* variable `c_` pour l’identifier comme variable définie par l’utilisateur. Incluez le `c_` préfixe (ou toute autre convention d’affectation de nom) de *`key`* variable si vos appels d’événement envoient des données à [!DNL Audience Manager] l’aide de cette syntaxe.

## Expressions booléennes {#boolean-expressions}

### Exemple ET

La règle établit les exigences de qualification des caractéristiques à l’aide d’opérateurs booléens [!UICONTROL AND] .

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exemple de code </th> 
   <th colname="col2" class="entry"> Pour être admissible, un visiteur doit </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_make=="A") AND (c_model="B") AND (c_search="1")</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">Recherchez une marque et un modèle spécifiques. </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">Recherchez le produit à partir d’une page de résultats de recherche (search = "1" ou "true"). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Exemple OU

Cette règle établit les exigences de qualification des caractéristiques à l’aide [!DNL Boolean] des opérateurs [!UICONTROL OR] et [!UICONTROL AND] .

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exemple de code </th> 
   <th colname="col2" class="entry"> Pour être admissible, un visiteur doit </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a== "1" OR b="1") ET (c="nouveau")</code> </td> 
   <td colname="col2"> Respectez les conditions définies par les variables <code><i>a </i></code> ou <code><i>b </i></code> et <code><i>c </i></code>. </td> 
  </tr> 
 </tbody> 
</table>

## Exemple de plage avec Supérieur à, Inférieur À, Égal À

Cette règle établit les exigences de qualification des caractéristiques à l’aide d’une plage.

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exemple de code </th> 
   <th colname="col2" class="entry"> Pour être admissible, un visiteur doit </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(prix &gt;= 1,00 ET prix &lt;= 100,00)</code> </td> 
   <td colname="col2"> Respectez toutes les conditions de prix comprises entre 1.00 et 100.00. </td> 
  </tr> 
 </tbody> 
</table>