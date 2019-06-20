---
description: Créateur de segments permet de créer des règles de caractéristique pour un segment à l'aide d'un éditeur de code. Cliquez sur l'onglet Expressions de segment (Affichage du code) du panneau Caractéristiques pour accéder à cette fonction.
seo-description: Créateur de segments permet de créer des règles de caractéristique pour un segment à l'aide d'un éditeur de code. Cliquez sur l'onglet Expressions de segment (Affichage du code) du panneau Caractéristiques pour accéder à cette fonction.
seo-title: Syntaxe du code utilisée dans l'éditeur d'expression de segment
solution: Audience Manager
title: Syntaxe du code utilisée dans l'éditeur d'expression de segment
uuid: 7 b 4 b 06 ca -7879-4501-8 ba 7-b 2 b 6467 b 8 a 3 b
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Code Syntax Used in the Segment Expression Editor {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] vous permet de créer des règles de caractéristique pour un segment à l&#39;aide d&#39;un éditeur de code. Click the **[!UICONTROL Segment Expressions (Code View)]** tab in the [!UICONTROL Traits] panel to access this feature.

## Syntaxe du code du créateur d&#39;expressions

Vous pouvez ajouter des règles de caractéristique à un segment avec du code plutôt que d&#39;utiliser des fonctions glisser-déposer. Lors du codage, remplacez les éléments en italique dans l&#39;exemple par une expression ou une valeur réelle. Le code de base utilise la syntaxe suivante :

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>By default, [!DNL Boolean] [!UICONTROL OR] conditions apply to multiple traits *within* an expression.

### Jonction de segments avec des opérateurs booléens

To build groups of segments, wrap the frequency function in parenthesis and set the relationship *between* each expression with a [!DNL Boolean] operator ([!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT]).

### Paramètres

>[!NOTE]
>
>Tous les paramètres sont obligatoires, sauf indication contraire.

| Nom ou variable | Description |
|---|---|
| `FREQUENCY` | Littéral devant précéder l&#39;expression. |
| ` [`&lt;`traitID`&gt;`T]` | An array of trait IDs followed by the letter `T`. Séparez plusieurs caractéristiques par une virgule. For example, `[123T, 456T]`. |
| ` <Recency Operator><Numeric Value>D` | *(Facultatif)* Définit les règles de récence sur les caractéristiques du segment. The letter `D` indicates recency in days. |
| ` <Frequency Operator><Numeric Value>` | Définit les règles de fréquence sur les caractéristiques du segment. |

### Opérateurs de récence et de fréquence autorisés

Set [recency and frequency](../../features/segments/recency-and-frequency.md) intervals with a comparison operator and an integer. [!UICONTROL Segment Builder] utilise des expressions standard telles que &lt; (moins que), &gt; (supérieur à), = = (égal), etc. Toutefois, les types d&#39;opérateurs autorisés varient lorsque vous définissez la récence ou la fréquence. Le tableau ci-dessous répertorie les opérateurs de récence/fréquence autorisés.

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
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt; = (supérieur/égal à) </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt; = (inférieur/égal à) </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt; = (supérieur/égal à) </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt; = (inférieur/égal à) </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">= = (égal à) </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Récence et fréquence](../../features/segments/recency-and-frequency.md)
>* [Expressions booléennes dans le créateur de caractéristiques et le créateur de segment](../../reference/boolean-expressions-tsb.md)
>* [Utilisation des opérateurs de comparaison dans traitbuilder](../../features/traits/trait-comparison-operators.md)
>* [Ordre des opérations dans les expressions traitbuilder](../../features/traits/trait-operator-precedence.md)

