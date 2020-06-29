---
description: Le créateur de caractéristiques évalue les expressions selon l’ordre des opérations indiqué ci-dessous, de la priorité élevée à la priorité faible. Les éléments de caractéristiques définis par les opérateurs de priorité élevée sont évalués en premier, avant les autres opérateurs de priorité. Cette section classe chaque opérateur en fonction de la priorité, de haut en bas.
seo-description: Le créateur de caractéristiques évalue les expressions selon l’ordre des opérations indiqué ci-dessous, de la priorité élevée à la priorité faible. Les éléments de caractéristiques définis par les opérateurs de priorité élevée sont évalués en premier, avant les autres opérateurs de priorité. Cette section classe chaque opérateur en fonction de la priorité, de haut en bas.
seo-title: Ordre des opérations dans le créateur de caractéristiques
solution: Audience Manager
title: Ordre des opérations dans le créateur de caractéristiques
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 3%

---


# Ordre des opérations dans le créateur de caractéristiques {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] évalue les expressions selon l’ordre des opérations indiqué ci-dessous, de la priorité élevée à la priorité faible. Les éléments de caractéristiques définis par les opérateurs de priorité élevée sont évalués en premier, avant les autres opérateurs de priorité. Cette section classe chaque opérateur en fonction de la priorité, de haut en bas.

<!-- c_tb_operator_precedence.xml -->

<table id="table_F0FA45B652C7464B90D35526817110FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Priorité de l'opérateur </th> 
   <th colname="col2" class="entry"> Symbole </th> 
   <th colname="col3" class="entry"> Commentaires </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Parenthèse </td> 
   <td colname="col2"> ( ) </td> 
   <td colname="col3"> Les Expressions entre parenthèses sont toujours évaluées en premier et suivent l’ordre de priorité. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Opérateurs de comparaison </td> 
   <td colname="col2"> &lt; &gt; &lt;= &gt;= </td> 
   <td colname="col3"> Inférieur à, supérieur à, inférieur à/égal à, supérieur à/égal à sont évalués ensuite. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Opérateurs d'égalité </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> Est égal à, n’est pas égal à sont évalués après les opérateurs précédents. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolean <span class="wintitle"> AND</span> </td> 
   <td colname="col2"><span class="wintitle"> AND</span> </td> 
   <td colname="col3" morerows="1"> n/d </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolean <span class="wintitle"> OR</span> </td> 
   <td colname="col2"><span class="wintitle"> OU</span> </td> 
   <td colname="col3" morerows="1"> n/d </td> 
  </tr> 
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Utilisation d’Expressions booléennes (AND, OR, NOT) dans TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Utilisation d’opérateurs de comparaison dans TraitBuilder](../../features/traits/trait-comparison-operators.md)

