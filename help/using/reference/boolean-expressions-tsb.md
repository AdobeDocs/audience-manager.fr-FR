---
description: Cet article explique comment les outils de caractéristiques et de segments d’Audience Manager utilisent les expressions booléennes ET, OU et NON.
seo-description: This article explains how the Audience Manager trait and segment tools use the Boolean expressions AND, OR, and NOT.
seo-title: Boolean Expressions in Trait and Segment Builder
solution: Audience Manager
title: Expressions booléennes dans le créateur de caractéristiques et de segments
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: Reference
exl-id: 44bc0385-2cce-4173-9833-b9a30fb6edae
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 0%

---

# Expressions booléennes dans le créateur de caractéristiques et de segments{#boolean-expressions-in-trait-and-segment-builder}

Cet article explique comment les outils de caractéristiques et de segments d’Audience Manager utilisent les expressions booléennes ET, OU et NON.

<!-- 

c_tb_boolean.xml

 -->

**Expressions booléennes**

La logique booléenne est une branche de l’algèbre qui utilise quelques expressions de base (ou opérateurs) pour déterminer si une instruction est vraie ou fausse. Les opérateurs les plus courants sont [!UICONTROL AND], [!UICONTROL OR] et [!UICONTROL NOT]. Les combinaisons de ces expressions vous permettent de rendre les règles de qualification de caractéristique ou de segment ciblées particulièrement adaptées à vos besoins en données. L’illustration suivante montre le fonctionnement des expressions booléennes de base.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>L’opérateur [!UICONTROL NOT] utilise une condition « and » implicite et est parfois écrit comme [!UICONTROL AND NOT].

**Utilisation d’expressions booléennes dans le créateur de caractéristiques et de segments**

Vous créez des règles de qualification de caractéristique et de segment avec des expressions booléennes. Le tableau ci-dessous décrit les bonnes pratiques générales pour la création de critères de qualification avec [!UICONTROL AND], [!UICONTROL OR] et [!UICONTROL NOT].

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Expression </th> 
   <th colname="col2" class="entry"> Utiliser pour créer </th> 
   <th colname="col3" class="entry"> A qualifier </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> ET </span></b> </p> </td> 
   <td colname="col2"> <p>Exigences de qualification d’audience étroites et ciblées. </p> </td> 
   <td colname="col3"> <p>Les utilisateurs <i>doivent</i> appartiennent à toutes les caractéristiques ou à tous les segments spécifiés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> OU </span></b> </p> </td> 
   <td colname="col2"> <p>Exigences de qualification des audiences larges et moins ciblées. </p> </td> 
   <td colname="col3"> <p>Les utilisateurs <i>peuvent</i> appartenir à n’importe quelle caractéristique ou segment spécifié. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NON</span></b> </p> </td> 
   <td colname="col2"> <p>Exigences de qualification d’audience étroites et ciblées. </p> <p>Utile lorsqu’il existe plusieurs conditions qui rendent difficile ou inefficace la définition des exigences de qualification des audiences. Parfois, il est plus facile de valider par rapport à des exigences qui excluent plutôt qu’incluent. </p> </td> 
   <td colname="col3"> <p>Les utilisateurs <i>ne doivent pas</i> appartenir à une caractéristique ou à un segment exclu. </p> </td> 
  </tr> 
 </tbody> 
</table>

Exemple **[!UICONTROL AND]cas d’utilisation**

L’opérateur [!UICONTROL AND] est utile lorsque vous avez facilement énuméré les exigences d’appartenance aux caractéristiques. Supposons, par exemple, que vous ayez besoin de créer une audience composée de « clients qui achètent des appareils photo coûteux ». Avec un modèle en pixels, vous devez créer et placer des pixels pour les appareils photo et une valeur de prix numérique sur votre page. En revanche, avec les caractéristiques , vous pouvez appliquer des opérateurs booléens pour gérer les deux conditions (caméras [!UICONTROL AND] prix). Le résultat est une collecte de données efficace avec moins d’appels HTTP, ce qui permet de préserver l’expérience utilisateur sur votre site.

Exemple **[!UICONTROL OR]cas d’utilisation**

L’opérateur [!UICONTROL OR] est utile lorsque vous souhaitez créer des signaux avec des exigences de qualification d’audience larges. Si vous avez plusieurs exigences de qualification de caractéristique ou de segment, l’opérateur [!UICONTROL OR] évaluera sur true lorsque les visiteurs de votre site présentent *l’une* ces caractéristiques. [!UICONTROL OR] peut s’avérer le plus utile lorsque vous souhaitez créer rapidement une vaste audience de visiteurs qualifiés du site.

Exemple **[!UICONTROL AND NOT]cas d’utilisation**

L’opérateur [!UICONTROL AND NOT] est utile lorsqu’il est plus facile de définir une audience par *exclusion* plutôt que par *inclusion*. Supposons, par exemple, que vous ayez une vente et que vous souhaitiez segmenter les visiteurs en clients qui ne consultent que les articles au prix complet. Plutôt que de créer une liste de signaux pour tous les articles complets ou au prix de vente admissibles, il peut être plus facile de qualifier les visiteurs s’ils n’ont *vu* un article au prix de vente. Cette méthode est efficace sur le plan administratif, car vous disposez généralement de moins d&#39;articles à prix de vente que ceux offerts à prix plein. Avec une [!UICONTROL NOT] booléenne, les visiteurs *ne doivent pas* montrer le signal de vente pour être admissibles à l’adhésion à l’audience à prix plein. En revanche, [!UICONTROL AND NOT] est l’opposé du cas d’utilisation [!UICONTROL AND], qui a montré comment l’appartenance à l’audience est déterminée par l’inclusion (c’est-à-dire que le visiteur s’est qualifié en fonction de 2 signaux explicites).

>[!MORELIKETHIS]
>
>* [Utilisation des opérateurs de comparaison dans TraitBuilder](../features/traits/trait-comparison-operators.md)
>* [ Ordre des opérations dans les expressions TraitBuilder ](../features/traits/trait-operator-precedence.md)
