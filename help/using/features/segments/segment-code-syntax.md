---
description: Le créateur de segments vous permet de créer des règles de caractéristiques pour un segment à l’aide d’un éditeur de code. Cliquez sur l’onglet Expressions du segment (Affichage du code) dans le panneau Caractéristiques pour accéder à cette fonctionnalité.
seo-description: Segment Builder lets you build trait rules for a segment using a code editor. Click the Segment Expressions (Code View) tab in the Traits panel to access this feature.
seo-title: Code Syntax Used in the Segment Expression Editor
solution: Audience Manager
title: Syntaxe du code utilisé dans l’éditeur d’expression de segment
uuid: 7b4b06ca-7879-4501-8ba7-b2b6467b8a3b
feature: Segments
exl-id: 64fa6f03-cef9-4187-866f-28c54f45f72e
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 4%

---

# Syntaxe du code utilisé dans l’éditeur d’expression de segment {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] permet de créer des règles de caractéristiques pour un segment à l’aide d’un éditeur de code. Cliquez sur l’onglet **[!UICONTROL Segment Expressions (Code View)]** dans le panneau [!UICONTROL Traits] pour accéder à cette fonctionnalité.

## Syntaxe Du Code Du Générateur D’Expression

Vous pouvez ajouter des règles de caractéristique à un segment avec du code au lieu d’utiliser des fonctionnalités de glisser-déposer. Lors du codage, remplacez les éléments en italique dans l’exemple par une expression ou une valeur réelle. Le code de base utilise la syntaxe suivante :

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>Par défaut, [!DNL Boolean] conditions de [!UICONTROL OR] s’appliquent à plusieurs caractéristiques *dans* une expression.

### Joindre des segments avec des opérateurs booléens

Pour créer des groupes de segments, placez la fonction de fréquence entre parenthèses et définissez la relation *entre* chaque expression avec un opérateur [!DNL Boolean] ([!UICONTROL AND], [!UICONTROL OR] et [!UICONTROL NOT]).

### Paramètres

>[!NOTE]
>
>Tous les paramètres sont requis, sauf indication contraire.

| Nom ou variable | Description |
|---|---|
| `FREQUENCY` | Un littéral qui doit précéder l’expression. |
| `[`&lt;`traitID`>`T]` | Tableau d’ID de caractéristique suivis de la lettre `T`. Séparez les caractéristiques multiples par une virgule. Par exemple, `[123T, 456T]`. |
| `<Recency Operator><Numeric Value>D` | *(Facultatif)* Définit des règles de récence sur les caractéristiques du segment. La lettre `D` indique la récence en jours. |
| `<Frequency Operator><Numeric Value>` | Définit des règles de fréquence sur les caractéristiques du segment. |

### Opérateurs Récence et Fréquence autorisés

Définissez des intervalles [récence et fréquence](../../features/segments/recency-and-frequency.md) avec un opérateur de comparaison et un entier. [!UICONTROL Segment Builder] utilise des expressions standard telles que &lt; (inférieur à), > (supérieur à), == (égal à), etc. Toutefois, les types d’opérateurs autorisés varient lorsque vous définissez la récence ou la fréquence. Le tableau ci-dessous répertorie les opérateurs de récence/fréquence autorisés.

<table id="table_2F92617CB472442BA5639E24DB4E43D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opérateurs Récents </th> 
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
>* [Utilisation des opérateurs de comparaison dans TraitBuilder](../../features/traits/trait-comparison-operators.md)
>* [&#x200B; Ordre des opérations dans les expressions TraitBuilder &#x200B;](../../features/traits/trait-operator-precedence.md)
