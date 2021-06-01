---
description: Exemples de création d’expressions dans l’éditeur de code du Générateur d’expression.
seo-description: Exemples de création d’expressions dans l’éditeur de code du Générateur d’expression.
seo-title: Exemple d’expressions avec des opérateurs booléens et de comparaison
solution: Audience Manager
title: Exemple d’expressions avec des opérateurs booléens et de comparaison
uuid: ee74c376-2099-4816-8694-43f58845a0ac
feature: 'Caractéristiques '
exl-id: 68041d61-7942-4c2f-9e78-f2b2f803ef59
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 13%

---

# Exemple d’expressions avec des opérateurs booléens et de comparaison {#sample-expressions-with-boolean-and-comparison-operators}

Exemples auxquels vous pouvez vous référer pour la création d’expressions dans l’éditeur de code [!UICONTROL Expression Builder].

## Présentation des exemples de code {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

Créez vos propres règles de caractéristiques avec l’éditeur de code [!UICONTROL Expression Builder]. Les exemples suivants peuvent vous aider à démarrer. Certains des exemples précèdent la variable *`key`* avec `c_` pour l’identifier comme variable définie par l’utilisateur. Insérez le préfixe `c_` (ou toute autre convention d’affectation des noms) pour la variable *`key`* si vos appels d’événement envoient des données à [!DNL Audience Manager] en utilisant cette syntaxe.

## Expressions booléennes {#boolean-expressions}

### Exemple AND

La règle établit les exigences de qualification des caractéristiques à l’aide d’opérateurs booléens [!UICONTROL AND].

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exemple de code </th> 
   <th colname="col2" class="entry"> Pour être admissible, un visiteur doit : </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_make=="A") AND (c_model=="B") AND (c_search=="1")</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">Recherchez une marque et un modèle spécifiques. </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">Recherchez le produit à partir d’une page de résultats de recherche (recherche = "1" ou "true"). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Exemple OU

Cette règle établit les exigences de qualification des caractéristiques à l’aide des opérateurs [!DNL Boolean] [!UICONTROL OR] et [!UICONTROL AND] .

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exemple de code </th> 
   <th colname="col2" class="entry"> Pour être admissible, un visiteur doit : </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a== "1" OR b=="1") AND (c=="new")</code> </td> 
   <td colname="col2"> Respectez les conditions définies par les variables <code><i>a </i></code> ou <code><i>b </i></code> et <code><i>c </i></code>. </td> 
  </tr> 
 </tbody> 
</table>

## Exemple de plage avec Supérieur à, Inférieur À, Égal À

Cette règle établit les exigences de qualification de caractéristiques à l’aide d’une plage.

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exemple de code </th> 
   <th colname="col2" class="entry"> Pour être admissible, un visiteur doit : </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(price &gt;= 1.00 AND price &lt;= 100.00)</code> </td> 
   <td colname="col2"> Respectez toute condition de prix comprise entre 1,00 et 100,00. </td> 
  </tr> 
 </tbody> 
</table>
