---
description: Cet article explique comment les outils de caractéristique et de segment d'Audience Manager utilisent les expressions booléennes ET, OU et NOT.
seo-description: Cet article explique comment les outils de caractéristique et de segment d'Audience Manager utilisent les expressions booléennes ET, OU et NOT.
seo-title: Expressions booléennes dans le créateur de caractéristiques et le créateur de segment
solution: Audience Manager
title: Expressions booléennes dans le créateur de caractéristiques et le créateur de segment
uuid: 14 f 02 d 3 f -4 c 84-41 fe-bc 91-b 34 f 0 d 49574 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Boolean Expressions in Trait and Segment Builder{#boolean-expressions-in-trait-and-segment-builder}

Cet article explique comment les outils de caractéristique et de segment d'Audience Manager utilisent les expressions booléennes ET, OU et NOT.

<!-- 

c_tb_boolean.xml

 -->

**Expressions booléennes**

La logique booléenne est une branche d'algebra qui utilise quelques expressions de base (ou opérateurs) pour déterminer si une instruction est vraie ou fausse. The most common operators are [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT]. Les combinaisons de ces expressions vous aident à adapter les règles de qualification des segments ou des segments à vos exigences de données. L'illustration suivante illustre le fonctionnement des expressions booléennes de base.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>[!UICONTROL NOT] L'opérateur utilise une condition « et » implicite et est parfois écrit sous [!UICONTROL AND NOT]la forme.

**Utilisation des expressions booléennes dans le créateur de caractéristiques et le créateur de segment**

Vous créez des règles de qualification de caractéristique et de segment avec des expressions booléennes. The table below describes general best practices for creating qualification criteria with [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT].

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Expression </th> 
   <th colname="col2" class="entry"> Utilisez-la pour créer </th> 
   <th colname="col3" class="entry"> Pour qualifier </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> ET</span></b> </p> </td> 
   <td colname="col2"> <p>Exigences de qualification d'audience étroites et ciblées. </p> </td> 
   <td colname="col3"> <p>Users <i>must</i> belong to all specified traits or segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> OU</span></b> </p> </td> 
   <td colname="col2"> <p>Exigences de qualification d'audience larges et moins ciblées. </p> </td> 
   <td colname="col3"> <p>Users <i>can</i> belong to any specified traits or segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> SAUF</span></b> </p> </td> 
   <td colname="col2"> <p>Exigences de qualification d'audience étroites et ciblées. </p> <p>Utile lorsqu'il existe plusieurs conditions qui rendent difficile ou inefficace la définition des conditions de qualification de l'audience. Il arrive qu'il soit plus facile de valider les exigences qui excluent plutôt que d'inclure. </p> </td> 
   <td colname="col3"> <p>Users <i>must not</i> belong to an excluded trait or segment. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Exemple de cas d'utilisation**

[!UICONTROL AND] L'opérateur est utile lorsque vous avez facilement des exigences d'adhésion aux caractéristiques. Par exemple, imaginons que vous deviez créer un public de « acheteurs de caméra coûteux ».  » » Avec un modèle de pixels, vous devez créer et placer des pixels pour les appareils photo et une valeur numérique de prix sur votre page. By contrast, with traits you can apply Boolean operators to handle both conditions (cameras [!UICONTROL AND] price). Le résultat est une collecte de données efficace avec moins d'appels HTTP, ce qui contribue à préserver l'expérience de l'utilisateur sur votre site.

**[!UICONTROL OR]Exemple de cas d'utilisation**

[!UICONTROL OR] L'opérateur est utile lorsque vous souhaitez créer des signaux avec des exigences étendues de qualification d'audience. If you have several trait or segment qualification requirements, the [!UICONTROL OR] operator will evaluate to true when your site visitors exhibit *any* of those characteristics. [!UICONTROL OR] peut être plus utile lorsque vous souhaitez créer rapidement un large public de visiteurs qualifiés du site.

**[!UICONTROL AND NOT]Exemple de cas d'utilisation**

[!UICONTROL AND NOT] L'opérateur est utile lorsqu'il est plus facile de définir une audience par *exclusion* plutôt *que par inclusion*. Supposons, par exemple, que vous disposiez d'une vente et que vous souhaitiez segmenter les visiteurs en clients qui examinent uniquement les articles à prix complet. Rather than create a list of signals for all qualifying full or sale-price items, it may be easier to qualify visitors if they have *not* seen a sale price item. Ceci est efficace administrativement car vous disposez généralement d'un moins grand nombre d'articles de prix de vente que ceux proposés à prix complet. With a Boolean [!UICONTROL NOT], visitors *must not* exhibit the sale signal to qualify for full-price audience membership. By contrast, [!UICONTROL AND NOT] is the opposite of the [!UICONTROL AND] use case, which showed how audience membership is determined by inclusion (i.e., the visitor qualified based on 2 explicitly stated signals).

>[!MORE_ LIKE_ THIS]
>
>* [Utilisation des opérateurs de comparaison dans traitbuilder](../features/traits/trait-comparison-operators.md)
>* [Ordre des opérations dans les expressions traitbuilder](../features/traits/trait-operator-precedence.md)

