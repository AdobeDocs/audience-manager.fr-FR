---
description: Cet article explique comment les outils de caractéristique et de segment de l’Audience Manager utilisent les expressions booléennes AND, OR, and NOT.
seo-description: Cet article explique comment les outils de caractéristique et de segment de l’Audience Manager utilisent les expressions booléennes AND, OR, and NOT.
seo-title: Expressions booléennes dans le créateur de caractéristiques et de segments
solution: Audience Manager
title: Expressions booléennes dans le créateur de caractéristiques et de segments
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: 'Référence '
exl-id: 44bc0385-2cce-4173-9833-b9a30fb6edae
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 4%

---

# Expressions booléennes dans le créateur de caractéristiques et de segments{#boolean-expressions-in-trait-and-segment-builder}

Cet article explique comment les outils de caractéristique et de segment de l’Audience Manager utilisent les expressions booléennes AND, OR, and NOT.

<!-- 

c_tb_boolean.xml

 -->

**Expressions booléennes**

La logique booléenne est une branche d’algèbre qui utilise quelques expressions de base (ou opérateurs) pour déterminer si une instruction est vraie ou fausse. Les opérateurs les plus courants sont [!UICONTROL AND], [!UICONTROL OR] et [!UICONTROL NOT]. Les combinaisons de ces expressions vous aident à définir des règles de qualification de segment ou de caractéristique ciblées parfaitement adaptées à vos besoins en données. L’illustration suivante montre le fonctionnement des expressions booléennes de base.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>L’opérateur [!UICONTROL NOT] utilise une condition &quot;et&quot; implicite et est parfois écrit en tant que [!UICONTROL AND NOT].

**Utilisation d’expressions booléennes dans le créateur de caractéristiques et de segments**

Vous créez des règles de qualification de caractéristiques et de segment avec des expressions booléennes. Le tableau ci-dessous décrit les bonnes pratiques générales pour la création de critères de qualification avec [!UICONTROL AND], [!UICONTROL OR] et [!UICONTROL NOT].

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Expression </th> 
   <th colname="col2" class="entry"> Utilisez-le pour créer des </th> 
   <th colname="col3" class="entry"> A qualifier </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> ET</span></b> </p> </td> 
   <td colname="col2"> <p>Exigences de qualification des audiences étroites et ciblées. </p> </td> 
   <td colname="col3"> <p>Les utilisateurs <i>doivent</i> appartenir à tous les segments ou caractéristiques spécifiés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> OU</span></b> </p> </td> 
   <td colname="col2"> <p>Exigences de qualification des audiences générales et moins ciblées. </p> </td> 
   <td colname="col3"> <p>Les utilisateurs <i>peuvent</i> appartenir à des caractéristiques ou des segments spécifiés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> SAUF</span></b> </p> </td> 
   <td colname="col2"> <p>Exigences de qualification des audiences étroites et ciblées. </p> <p>Utile lorsque plusieurs conditions rendent difficile ou inefficace la définition des exigences de qualification des audiences. Il est parfois plus facile de valider les exigences qui excluent plutôt que d’inclure. </p> </td> 
   <td colname="col3"> <p>Les utilisateurs <i>ne doivent pas</i> appartenir à une caractéristique ou à un segment exclu. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Exemple de cas d’utilisation**

L’opérateur [!UICONTROL AND] est utile lorsque vous avez facilement énuméré les exigences d’adhésion aux caractéristiques. Par exemple, supposons que vous deviez créer une audience de &quot;acheteurs de caméras onéreux&quot;. Avec un modèle de pixel, vous devez créer et placer des pixels pour les caméras et une valeur de prix numérique sur votre page. En revanche, avec les caractéristiques, vous pouvez appliquer des opérateurs booléens pour gérer les deux conditions (prix des caméras [!UICONTROL AND]). La collecte de données est ainsi efficace avec moins d’appels HTTP, ce qui permet de préserver l’expérience de l’utilisateur sur votre site.

**[!UICONTROL OR]Exemple de cas d’utilisation**

L’opérateur [!UICONTROL OR] est utile lorsque vous souhaitez créer des signaux avec des exigences de qualification d’audience générales. Si vous avez plusieurs exigences de qualification de caractéristique ou de segment, l’opérateur [!UICONTROL OR] renvoie la valeur true lorsque les visiteurs de votre site présentent *n’importe quelle* de ces caractéristiques. [!UICONTROL OR] s’avère particulièrement utile lorsque vous souhaitez créer rapidement une large audience de visiteurs qualifiés sur le site.

**[!UICONTROL AND NOT]Exemple de cas d’utilisation**

L’opérateur [!UICONTROL AND NOT] est utile lorsqu’il est plus facile de définir une audience par *exclusion* plutôt que par *inclusion*. Supposons, par exemple, que vous ayez une vente et que vous souhaitiez segmenter les visiteurs en clients qui consultent uniquement les articles à prix plein. Plutôt que de créer une liste de signaux pour tous les articles admissibles à prix complet ou à prix de vente, il peut être plus facile de qualifier les visiteurs s’ils ont *pas* vu un article à prix de vente. Cette méthode est efficace sur le plan administratif car vous avez généralement moins d’articles de prix de vente que ceux proposés au prix complet. Avec une valeur booléenne [!UICONTROL NOT], les visiteurs *ne doivent pas* présenter le signal de vente pour être éligibles au prix total de l’audience. En revanche, [!UICONTROL AND NOT] est l’opposé du cas d’utilisation [!UICONTROL AND], qui montre comment l’appartenance à l’audience est déterminée par l’inclusion (c’est-à-dire le visiteur qualifié sur la base de 2 signaux explicitement indiqués).

>[!MORELIKETHIS]
>
>* [Utilisation d’opérateurs de comparaison dans TraitBuilder](../features/traits/trait-comparison-operators.md)
* [Ordre des opérations dans les expressions TraitBuilder](../features/traits/trait-operator-precedence.md)

