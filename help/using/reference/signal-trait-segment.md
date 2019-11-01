---
description: Décrit les composants d’un segment Audience Manager, les expressions utilisées pour définir les critères de qualification de l’audience et la manière dont les données sont transmises dans un appel d’événement.
seo-description: Décrit les composants d’un segment Audience Manager, les expressions utilisées pour définir les critères de qualification de l’audience et la manière dont les données sont transmises dans un appel d’événement.
seo-title: Signaux, caractéristiques et segments
solution: Audience Manager
title: Signaux, caractéristiques et segments
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Signaux, caractéristiques et segments{#signals-traits-and-segments}

Décrit les composants d’un segment Audience Manager, les expressions utilisées pour définir les critères de qualification de l’audience et la manière dont les données sont transmises dans un appel d’événement.

<!-- 

c_signal_trait_segment.xml

 -->

**Composition et objet**

[!DNL Audience Manager] les données sont constituées de signaux, de caractéristiques, de segments et de règles de qualification connexes. Les éléments de données et les règles se combinent pour créer des segments. Les segments organisent les visiteurs du site en groupes apparentés. Le tableau suivant définit les trois principaux composants d’un [!DNL Audience Manager] segment.

<table id="table_E8373A01C3414C42B4983A59BF0F0669"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Consiste en </th> 
   <th colname="col3" class="entry"> Exemple </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Signal</b> </td> 
   <td colname="col2"> <p>Les signaux sont les unités de données les plus petites d’ <span class="keyword"> Audience Manager</span> et sont exprimés en paires <a href="../reference/key-value-pairs-explained.md"></a>clé-valeur. </p> 
    <ul id="ul_728347E325284B9FA0B4E05DE8CF4570"> 
     <li id="li_89574A3B4A734726AD43405AE6D85FF5">La clé est une constante qui définit un jeu de données (par exemple, sexe, couleur, prix). </li> 
     <li id="li_D35601B33EE24EC5857F45D9577254D4">La valeur est une variable liée à la constante (ex. : mâle/femelle, vert, 100). </li> 
    </ul> <p>Les opérateurs de comparaison joignent la paire clé-valeur et définissent la relation entre eux. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A6D8D30A37C94437A7BF38736C6F8556"> 
     <li id="li_74C87C34FA254783AC0DEBBC69B35AC4"><code> product=camera</code> </li> 
     <li id="li_C1727B9136024E56B60374597A7DCA00"><code> price&gt;1000</code> </li> 
     <li id="li_B2E7798768EE444AB978F3F27B0BC0B5"><code> type=digital SLR</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Caractéristique</b> </td> 
   <td colname="col2"> <p>Combinaisons d’un ou de plusieurs signaux. </p> <p>Les expressions booléennes et les opérateurs de comparaison vous permettent de créer des règles de qualification des caractéristiques. </p> <p>Créer des exigences de qualification précises avec des combinaisons de caractéristiques et de groupes de caractéristiques. </p> </td> 
   <td colname="col3"> <p>A partir des signaux disponibles, vous pouvez créer une règle "Navigateur de caméras haut de gamme" exprimée comme suit : </p> <p><code> product=camera AND price&gt;1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Segment</b> </td> 
   <td colname="col2"> <p>Utilisateurs qui partagent un ensemble d’attributs communs et sont admissibles pour les caractéristiques connexes. </p> <p>Les expressions booléennes, ainsi que les exigences de récence/fréquence, vous permettent de créer des règles de qualification de segment. </p> <p>Créez des exigences de qualification précises avec des combinaisons de caractéristiques et de règles de segmentation. </p> </td> 
   <td colname="col3"> <p>A partir des caractéristiques et des signaux disponibles, vous pouvez créer une règle de segment exprimée comme suit : </p> <p><code> (product=camera AND type=digital SLR) OR (price&gt;1000)</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Utilisez le diagramme ci-dessous pour garder une note mentale de la relation entre les signaux, les caractéristiques et les segments.

![](assets/signals-traits-segments.png)

**Création de caractéristiques et de règles de segmentation avec des outils visuels et des éditeurs de code**

Les clients gèrent les caractéristiques et les segments à l’aide d’outils visuels et d’éditeurs de code dans l’interface [!DNL Audience Manager] utilisateur. Les outils visuels vous permettent de créer des règles à l’aide de fonctions de recherche, d’options contextuelles, de menus déroulants et de fonctionnalités de glisser-déposer. Les éditeurs de code permettent aux utilisateurs avancés de développer par programmation des critères de segmentation de l’audience.

**Appels d’événement Envoyer des données à Audience Manager**

Un appel d’événement envoie des données de votre site Web vers [!DNL Audience Manager]. L’appel contient des données de signal, de caractéristique et de segment dans une requête HTTP. L’événement lui-même est tout après la `/event` partie d’une chaîne URL. Comme le montre l'exemple ci-dessous, ce processus ne nécessite qu'un appel d'événement unique pour transmettre plusieurs variables à [!DNL Audience Manager].

```
https://<domain>/event?product=camera&price>100
```

>[!MORELIKETHIS]
>
>* [Segments : Objectif, composition et règles](../features/segments/segments-purpose.md)

