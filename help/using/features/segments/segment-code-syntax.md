---
description: Le créateur de segments permet de créer des règles de caractéristiques pour un segment à l’aide d’un éditeur de code. Cliquez sur l’onglet Expressions de segment (Vue de code) du panneau Caractéristiques pour accéder à cette fonction.
seo-description: Le créateur de segments permet de créer des règles de caractéristiques pour un segment à l’aide d’un éditeur de code. Cliquez sur l’onglet Expressions de segment (Vue de code) du panneau Caractéristiques pour accéder à cette fonction.
seo-title: Syntaxe du code utilisée dans l’éditeur d’Expressions de segments
solution: Audience Manager
title: Syntaxe du code utilisée dans l’éditeur d’Expressions de segments
uuid: 7b4b06ca-7879-4501-8ba7-b2b6467b8a3b
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 1%

---


# Syntaxe du code utilisée dans l’éditeur d’Expressions de segments {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] vous permet de créer des règles de caractéristiques pour un segment à l’aide d’un éditeur de code. Cliquez sur l’ **[!UICONTROL Segment Expressions (Code View)]** onglet du [!UICONTROL Traits] panneau pour accéder à cette fonction.

## Syntaxe du code du créateur d’Expressions

Vous pouvez ajouter des règles de caractéristiques à un segment avec du code au lieu d’utiliser des fonctions de glisser-déposer. Lors du codage, remplacez les éléments en italique de l’exemple par une expression ou une valeur réelle. Le code de base utilise la syntaxe suivante :

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>Par défaut, [!DNL Boolean][!UICONTROL OR] les conditions s’appliquent à plusieurs caractéristiques *au sein* d’une expression.

### Joindre des segments avec des opérateurs booléens

Pour créer des groupes de segments, placez la fonction de fréquence entre parenthèses et définissez la relation *entre* chaque expression avec un [!DNL Boolean] opérateur ([!UICONTROL AND], [!UICONTROL OR]et [!UICONTROL NOT]).

### Paramètres

>[!NOTE]
>
>Tous les paramètres sont requis, sauf indication contraire.

| Nom ou variable | Description |
|---|---|
| `FREQUENCY` | Littéral devant précéder l’expression. |
| ` [`&lt;`traitID`>`T]` | Tableau d’identifiants de caractéristiques suivi de la lettre `T`. Séparez plusieurs caractéristiques par une virgule. Par exemple, `[123T, 456T]`. |
| ` <Recency Operator><Numeric Value>D` | *(Facultatif)* Définit les règles de récence sur les caractéristiques du segment. La lettre `D` indique la récence en jours. |
| ` <Frequency Operator><Numeric Value>` | Définit des règles de fréquence sur les caractéristiques du segment. |

### Opérateurs de récence et de fréquence autorisés

Définissez des intervalles de [récence et de fréquence](../../features/segments/recency-and-frequency.md) à l’aide d’un opérateur de comparaison et d’un entier. [!UICONTROL Segment Builder] utilise des expressions standard telles que &lt; (inférieur à), > (supérieur à), == (égal à), etc. Cependant, les types d’opérateurs autorisés varient lorsque vous définissez la récence ou la fréquence. Le tableau ci-dessous liste les opérateurs de récence/fréquence autorisés.

<table id="table_2F92617CB472442BA5639E24DB4E43D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opérateurs de récence </th> 
   <th colname="col2" class="entry"> Opérateurs de fréquence </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_66D11A34097648A997BA5C6CCC38503A"> 
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt;= (supérieur/égal à) </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt;= (inférieur/égal à) </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt;= (supérieur/égal à) </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt;= (inférieur/égal à) </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">== (égal à) </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Récence et fréquence](../../features/segments/recency-and-frequency.md)
>* [Expressions booléennes dans le créateur de caractéristiques et de segments](../../reference/boolean-expressions-tsb.md)
>* [Utilisation d’opérateurs de comparaison dans TraitBuilder](../../features/traits/trait-comparison-operators.md)
>* [Ordre des opérations dans les Expressions TraitBuilder](../../features/traits/trait-operator-precedence.md)

