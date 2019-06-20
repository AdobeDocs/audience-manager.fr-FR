---
description: Le créateur de caractéristiques évalue les expressions selon l'ordre des opérations répertoriées ci-dessous, de haut en faible priorité. Les éléments de caractéristique définis par les opérateurs de priorité élevée sont évalués en premier, avant les autres opérateurs de priorité. Cette section classe chaque opérateur selon la priorité, de haut en bas.
seo-description: Le créateur de caractéristiques évalue les expressions selon l'ordre des opérations répertoriées ci-dessous, de haut en faible priorité. Les éléments de caractéristique définis par les opérateurs de priorité élevée sont évalués en premier, avant les autres opérateurs de priorité. Cette section classe chaque opérateur selon la priorité, de haut en bas.
seo-title: Ordre des opérations dans le créateur de caractéristiques
solution: Audience Manager
title: Ordre des opérations dans le créateur de caractéristiques
uuid: df 325047-af 62-45 ad -9 ca 1-046 bfcbe 5341
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Order of Operations in Trait Builder {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] évalue les expressions selon l&#39;ordre des opérations répertoriées ci-dessous, de haut en faible priorité. Les éléments de caractéristique définis par les opérateurs de priorité élevée sont évalués en premier, avant les autres opérateurs de priorité. Cette section classe chaque opérateur selon la priorité, de haut en bas.

<!-- c_tb_operator_precedence.xml -->

<table id="table_F0FA45B652C7464B90D35526817110FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Priorité des opérateurs </th> 
   <th colname="col2" class="entry"> Symbole </th> 
   <th colname="col3" class="entry"> Commentaires </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Parenthèses </td> 
   <td colname="col2"> ( ) </td> 
   <td colname="col3"> Les expressions entre parenthèses sont toujours évaluées en premier et suivent l'ordre de priorité. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Opérateurs de comparaison </td> 
   <td colname="col2"> &lt; &gt; &lt;= &gt;= </td> 
   <td colname="col3"> Plus petit que, plus petit que/égal à, supérieur à/égal à sont évalués suivant. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Opérateurs d'égalité </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> Égal à, non égal à être évalué après les opérateurs précédents. </td> 
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

>[!MORE_ LIKE_ THIS]
>
>* [Utilisation d&#39;expressions booléennes (ET, OU, NOT) dans traitbuilder](../../reference/boolean-expressions-tsb.md)
>* [Utilisation des opérateurs de comparaison dans traitbuilder](../../features/traits/trait-comparison-operators.md)

