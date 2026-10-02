---
description: Le créateur de caractéristiques évalue les expressions selon l’ordre des opérations répertorié ci-dessous, de priorité haute à priorité basse. Les éléments de caractéristiques définis par des opérateurs de priorité élevée sont évalués en premier, avant les autres opérateurs de priorité. Cette section classe chaque opérateur en fonction de la priorité, du plus élevé au plus bas.
seo-description: Trait Builder evaluates expressions according to the order-of-operations listed below, from high to low precedence. Trait elements defined by high-precedence operators are evaluated first, before other precedence operators. This section ranks each operator according to precedence, from high to low.
seo-title: Order of Operations in Trait Builder
solution: Audience Manager
title: Ordre des opérations dans le créateur de caractéristiques
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
feature: Traits
exl-id: 90700479-4a8e-4a07-81ef-2e9d8a1d9f15
TQID: 'https://experienceleague.adobe.com/Jfmytv1c-4Uc8q2UGVU5Lgx-iOZ-yk2sSzc8iRviBAs'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: b89b323a-1e91-40b1-8d20-96b5b726d55a
    internal-label: Audience management
subfeature_v2:
  - id: b1ecf375-97f8-4f5a-a937-6129552209be
    internal-label: Traits
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 2%
---
# Ordre des opérations dans le créateur de caractéristiques {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] évalue les expressions selon l’ordre des opérations répertorié ci-dessous, de priorité haute à priorité basse. Les éléments de caractéristiques définis par des opérateurs de priorité élevée sont évalués en premier, avant les autres opérateurs de priorité. Cette section classe chaque opérateur en fonction de la priorité, du plus élevé au plus bas.

<!-- c_tb_operator_precedence.xml -->

<table id="table_F0FA45B652C7464B90D35526817110FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Priorité de l’opérateur </th> 
   <th colname="col2" class="entry"> Symbole </th> 
   <th colname="col3" class="entry"> Commentaires </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Parenthèse </td> 
   <td colname="col2"> ( ) </td> 
   <td colname="col3"> Les expressions entre parenthèses sont toujours évaluées en premier et suivent l’ordre de priorité. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Opérateurs de comparaison </td> 
   <td colname="col2"> &lt; &gt; &lt;= &gt;= </td> 
   <td colname="col3"> Inférieur à, supérieur à, inférieur/égal à, supérieur/égal à sont ensuite évalués. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Opérateurs d’égalité </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> Égal à, différent de sont évalués après les opérateurs précédents. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Booléen <span class="wintitle"> AND</span> </td> 
   <td colname="col2"><span class="wintitle"> ET </span> </td> 
   <td colname="col3" morerows="1"> n/d </td> 
  </tr> 
  <tr> 
   <td colname="col1">Booléen <span class="wintitle"> OR</span> </td> 
   <td colname="col2"><span class="wintitle"> OU </span> </td> 
   <td colname="col3" morerows="1"> n/d </td> 
  </tr> 
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Utilisation d’expressions booléennes (AND, OR, NOT) dans TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Utilisation des opérateurs de comparaison dans TraitBuilder](../../features/traits/trait-comparison-operators.md)
