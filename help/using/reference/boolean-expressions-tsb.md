---
description: Cet article explique comment les outils de caractéristiques et de segments d’Audience Manager utilisent les expressions booléennes AND, OR et NOT.
seo-description: Cet article explique comment les outils de caractéristiques et de segments d’Audience Manager utilisent les expressions booléennes AND, OR et NOT.
seo-title: Expressions booléennes dans le créateur de caractéristiques et de segments
solution: Audience Manager
title: Expressions booléennes dans le créateur de caractéristiques et de segments
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Expressions booléennes dans le créateur de caractéristiques et de segments{#boolean-expressions-in-trait-and-segment-builder}

Cet article explique comment les outils de caractéristiques et de segments d’Audience Manager utilisent les expressions booléennes AND, OR et NOT.

<!-- 

c_tb_boolean.xml

 -->

**Expressions booléennes**

La logique booléenne est une branche d’algèbre qui utilise quelques expressions de base (ou opérateurs) pour déterminer si une instruction est vraie ou fausse. Les opérateurs les plus courants sont [!UICONTROL AND], [!UICONTROL OR]et [!UICONTROL NOT]. Les combinaisons de ces expressions vous aident à définir des règles de qualification de caractéristiques ou de segments ciblées qui répondent parfaitement à vos besoins en données. L’illustration suivante illustre le fonctionnement des expressions booléennes de base.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>L’ [!UICONTROL NOT] opérateur utilise une condition "et" implicite et est parfois écrit en tant que [!UICONTROL AND NOT].

**Utilisation des expressions booléennes dans le créateur de caractéristiques et de segments**

Vous créez des règles de qualification de caractéristiques et de segments avec des expressions booléennes. Le tableau ci-dessous décrit les meilleures pratiques générales pour la création de critères de qualification avec [!UICONTROL AND], [!UICONTROL OR]et [!UICONTROL NOT].

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Expression </th> 
   <th colname="col2" class="entry"> Utilisez-la pour créer </th> 
   <th colname="col3" class="entry"> Pour être admissible </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> ET</span></b> </p> </td> 
   <td colname="col2"> <p>Exigences de qualification du public étroites et ciblées. </p> </td> 
   <td colname="col3"> <p>Les utilisateurs <i>doivent</i> appartenir à tous les segments ou caractéristiques spécifiés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> OU</span></b> </p> </td> 
   <td colname="col2"> <p>Exigences de qualification d’audience générales et moins ciblées. </p> </td> 
   <td colname="col3"> <p>Les utilisateurs <i>peuvent</i> appartenir à des caractéristiques ou à des segments spécifiés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> SAUF</span></b> </p> </td> 
   <td colname="col2"> <p>Exigences de qualification du public étroites et ciblées. </p> <p>Utile lorsqu’il existe plusieurs conditions qui rendent difficile ou inefficace la définition des exigences de qualification de l’audience. Il est parfois plus facile de valider les critères par rapport aux exigences qui excluent plutôt que d’inclure. </p> </td> 
   <td colname="col3"> <p>Les utilisateurs ne <i>doivent pas</i> appartenir à une caractéristique ou à un segment exclu. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Exemple de cas d’utilisation**

L’ [!UICONTROL AND] opérateur est utile lorsque vous avez facilement énuméré les conditions d’adhésion aux caractéristiques. Supposons, par exemple, que vous deviez créer un public de "acheteurs de caméras onéreux". Avec un modèle de pixels, vous devez créer et placer des pixels pour les caméras et une valeur de prix numérique sur votre page. En revanche, avec les caractéristiques, vous pouvez appliquer des opérateurs booléens pour gérer les deux conditions (prix [!UICONTROL AND] des caméras). La collecte de données est donc efficace avec moins d’appels HTTP, ce qui permet de préserver l’expérience des utilisateurs sur votre site.

**[!UICONTROL OR]Exemple de cas d’utilisation**

L’ [!UICONTROL OR] opérateur est utile lorsque vous souhaitez créer des signaux avec des exigences de qualification d’audience générales. Si vous avez plusieurs critères de qualification de caractéristiques ou de segments, l’ [!UICONTROL OR] opérateur évaluera la valeur true lorsque les visiteurs de votre site présentent *l’une* de ces caractéristiques. [!UICONTROL OR] peut s’avérer particulièrement utile lorsque vous souhaitez créer rapidement un large public de visiteurs qualifiés sur le site.

**[!UICONTROL AND NOT]Exemple de cas d’utilisation**

L’ [!UICONTROL AND NOT] opérateur est utile lorsqu’il est plus facile de définir une audience par *exclusion* que par *inclusion*. Supposons, par exemple, que vous vendiez et que vous souhaitiez segmenter les visiteurs en clients qui examinent uniquement les articles à prix plein. Plutôt que de créer une liste de signaux pour tous les articles à prix complet ou à prix de vente admissibles, il peut être plus facile de qualifier les visiteurs s’ils *n’ont pas* vu un article de prix de vente. C'est efficace sur le plan administratif, car vous avez habituellement moins d'articles de prix de vente que ceux offerts à plein prix. Avec une valeur booléenne [!UICONTROL NOT], les visiteurs ne *doivent pas* afficher le signal de vente pour bénéficier d’un abonnement à prix plein. En revanche, [!UICONTROL AND NOT] c’est le contraire du [!UICONTROL AND] cas d’utilisation qui montre comment l’appartenance à l’audience est déterminée par l’inclusion (c.-à-d. que le visiteur est qualifié sur la base de 2 signaux explicitement indiqués).

>[!MORE_LIKE_This]
>
>* [Utilisation des opérateurs de comparaison dans TraitBuilder](../features/traits/trait-comparison-operators.md)
>* [Ordre des opérations dans les expressions TraitBuilder](../features/traits/trait-operator-precedence.md)

