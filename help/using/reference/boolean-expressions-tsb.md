---
description: Cet article explique comment les outils de caractéristiques d’Audience Manager et de segmentation utilisent les expressions booléennes ET, OU et NOT.
seo-description: Cet article explique comment les outils de caractéristiques d’Audience Manager et de segmentation utilisent les expressions booléennes ET, OU et NOT.
seo-title: Expressions booléennes dans le créateur de caractéristiques et de segments
solution: Audience Manager
title: Expressions booléennes dans le créateur de caractéristiques et de segments
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 0%

---


# Expressions booléennes dans le créateur de caractéristiques et de segments{#boolean-expressions-in-trait-and-segment-builder}

Cet article explique comment les outils de caractéristiques d’Audience Manager et de segmentation utilisent les expressions booléennes ET, OU et NOT.

<!-- 

c_tb_boolean.xml

 -->

**Expressions booléennes**

La logique booléenne est une branche d&#39;algèbre qui utilise quelques expressions (ou opérateurs) de base pour déterminer si une instruction est vraie ou fausse. Les opérateurs les plus courants sont [!UICONTROL AND], [!UICONTROL OR]et [!UICONTROL NOT]. Les combinaisons de ces expressions vous aident à définir des règles de qualification de caractéristiques ou de segment ciblées qui répondent parfaitement à vos besoins en données. L&#39;illustration suivante montre comment fonctionnent les expressions booléennes de base.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>L’ [!UICONTROL NOT] opérateur utilise une condition &quot;et&quot; implicite et est parfois écrit en [!UICONTROL AND NOT]tant que.

**Utilisation des Expressions booléennes dans le créateur de caractéristiques et de segments**

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
   <td colname="col1"> <p><b><span class="wintitle"> AND</span></b> </p> </td> 
   <td colname="col2"> <p>Exigences de qualification des audiences étroites et ciblées. </p> </td> 
   <td colname="col3"> <p>Les utilisateurs <i>doivent</i> appartenir à toutes les caractéristiques ou segments spécifiés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> OU</span></b> </p> </td> 
   <td colname="col2"> <p>Exigences de qualification des audiences générales et moins ciblées. </p> </td> 
   <td colname="col3"> <p>Les utilisateurs <i>peuvent</i> appartenir à des caractéristiques ou segments spécifiés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> SAUF</span></b> </p> </td> 
   <td colname="col2"> <p>Exigences de qualification des audiences étroites et ciblées. </p> <p>Utile lorsqu'il y a plusieurs conditions qui rendent difficile ou inefficace la définition des exigences de qualification des audiences. Il est parfois plus facile de valider les exigences qui excluent plutôt que d’inclure des exigences. </p> </td> 
   <td colname="col3"> <p>Les utilisateurs ne <i>doivent pas</i> appartenir à une caractéristique ou un segment exclu. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Exemple de cas d’utilisation **

L’ [!UICONTROL AND] opérateur est utile lorsque vous avez énuméré facilement les exigences d’appartenance à une caractéristique. Par exemple, supposons que vous deviez créer une audience de &quot;caméscopes coûteux&quot;. Avec un modèle de pixels, vous devez créer et placer des pixels pour les caméras et une valeur de prix numérique sur votre page. En revanche, avec les caractéristiques, vous pouvez appliquer des opérateurs booléens pour gérer les deux conditions (le [!UICONTROL AND] prix des caméras). La collecte de données est efficace avec moins d’appels HTTP, ce qui permet de préserver l’expérience des utilisateurs sur votre site.

**[!UICONTROL OR]Exemple de cas d’utilisation **

L&#39; [!UICONTROL OR] opérateur est utile lorsque vous souhaitez créer des signaux avec des exigences de qualification d&#39;audience générales. Si vous avez plusieurs exigences de qualification de caractéristiques ou de segments, l’ [!UICONTROL OR] opérateur évaluera la valeur true lorsque les visiteurs de votre site présentent *l’une* de ces caractéristiques. [!UICONTROL OR] peut s&#39;avérer particulièrement utile lorsque vous souhaitez créer rapidement une audience étendue de visiteurs de site qualifiés.

**[!UICONTROL AND NOT]Exemple de cas d’utilisation **

L’ [!UICONTROL AND NOT] opérateur est utile lorsqu’il est plus facile de définir une audience par *exclusion* que par *inclusion*. Supposons, par exemple, que vous vendiez et que vous souhaitiez segmenter les visiteurs en clients qui étudient uniquement les articles à prix plein. Plutôt que de créer une liste de signaux pour tous les articles admissibles à prix complet ou à prix de vente, il peut être plus facile de qualifier les visiteurs s&#39;ils *n&#39;ont pas* vu un article de prix de vente. Cette méthode est efficace sur le plan administratif, car vous avez généralement moins d&#39;articles à prix de vente que ceux offerts au prix complet. Avec une valeur booléenne [!UICONTROL NOT], les visiteurs *ne doivent pas* montrer le signal de vente pour être admissibles à une audience à prix plein. En revanche, [!UICONTROL AND NOT] c&#39;est le contraire du cas d&#39; [!UICONTROL AND] utilisation, qui montre comment l&#39;appartenance à l&#39;audience est déterminée par l&#39;inclusion (c.-à-d. que le visiteur est qualifié sur la base de 2 signaux explicitement indiqués).

>[!MORELIKETHIS]
>
>* [Utilisation d’opérateurs de comparaison dans TraitBuilder](../features/traits/trait-comparison-operators.md)
>* [Ordre des opérations dans les Expressions TraitBuilder](../features/traits/trait-operator-precedence.md)

