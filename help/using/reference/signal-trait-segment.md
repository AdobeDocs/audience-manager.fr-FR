---
description: Décrit les composants d'un segment Audience Manager, les expressions utilisées pour définir les critères de qualification d'audience et la manière dont les données sont transmises dans un appel d'événement.
seo-description: Décrit les composants d'un segment Audience Manager, les expressions utilisées pour définir les critères de qualification d'audience et la manière dont les données sont transmises dans un appel d'événement.
seo-title: Signaux, caractéristiques et segments
solution: Audience Manager
title: Signaux, caractéristiques et segments
uuid: 485 fcc 5 c-b 289-463 b-a 610-0 d 727 df 90 f 3 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Signals, Traits, and Segments{#signals-traits-and-segments}

Décrit les composants d&#39;un segment Audience Manager, les expressions utilisées pour définir les critères de qualification d&#39;audience et la manière dont les données sont transmises dans un appel d&#39;événement.

<!-- 

c_signal_trait_segment.xml

 -->

**Composition et objectif**

[!DNL Audience Manager] Les données sont constituées de signaux, de caractéristiques, de segments et de règles de qualification associées. Les éléments et les règles de données se combinent pour créer des segments. Les segments organisent les visiteurs du site en groupes associés. The following table defines the three principal components in an [!DNL Audience Manager] segment.

<table id="table_E8373A01C3414C42B4983A59BF0F0669"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Se compose de </th> 
   <th colname="col3" class="entry"> Exemple </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Signal</b> </td> 
   <td colname="col2"> <p>Signals are the smallest data units in <span class="keyword"> Audience Manager</span> and are expressed as <a href="../reference/key-value-pairs-explained.md"> key-value pairs</a>. </p> 
    <ul id="ul_728347E325284B9FA0B4E05DE8CF4570"> 
     <li id="li_89574A3B4A734726AD43405AE6D85FF5">La clé est une constante qui définit un jeu de données (par exemple, sexe, couleur, prix). </li> 
     <li id="li_D35601B33EE24EC5857F45D9577254D4">La valeur est liée à la constante (par ex. homme/femme, vert, 100). </li> 
    </ul> <p>Les opérateurs de comparaison rejoignent la paire clé-valeur et définissent la relation entre eux. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A6D8D30A37C94437A7BF38736C6F8556"> 
     <li id="li_74C87C34FA254783AC0DEBBC69B35AC4"><code> product = camera</code> </li> 
     <li id="li_C1727B9136024E56B60374597A7DCA00"><code> prix &gt; 1000</code> </li> 
     <li id="li_B2E7798768EE444AB978F3F27B0BC0B5"><code> type = SLR numérique</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Caractéristique</b> </td> 
   <td colname="col2"> <p>Combinaisons d'un ou de plusieurs signaux. </p> <p>Les expressions booléennes et les opérateurs de comparaison vous permettent de créer des règles de qualification des caractéristiques. </p> <p>Créez des conditions de qualification précises avec des combinaisons de caractéristiques et de groupes de caractéristiques. </p> </td> 
   <td colname="col3"> <p>A partir des signaux disponibles, vous pouvez créer une règle « Navigateur de caméra haut de gamme » comme suit : </p> <p><code> product = camera AND prix &gt; 1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Segment</b> </td> 
   <td colname="col2"> <p>Utilisateurs partageant un jeu d'attributs communs et remplissant les caractéristiques associées. </p> <p>Les expressions booléennes, ainsi que les exigences de récence/fréquence, vous permettent de créer des règles de qualification des segments. </p> <p>Créez des conditions de qualification précises avec des combinaisons de caractéristiques et de règles de segmentation. </p> </td> 
   <td colname="col3"> <p>A partir des caractéristiques et des signaux disponibles, vous pouvez créer une règle de segmentation exprimée en tant que : </p> <p><code> (product = camera AND type = digital SLR) OR (prix &gt; 1000)</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Utilisez le diagramme ci-dessous pour garder une note mentale de la relation entre les signaux, les caractéristiques et les segments.

![](assets/signals-traits-segments.png)

**Création de caractéristiques et de règles de segmentation avec outils visuels et Editeurs de code**

Clients manage traits and segments with visual tools and code editors in the [!DNL Audience Manager] user interface. Les outils visuels vous permettent de créer des règles à l&#39;aide de fonctionnalités de recherche, d&#39;options contextuelles, de menus déroulants et de fonctionnalités de glisser-déposer. Les éditeurs de code offrent aux utilisateurs avancés un moyen de développer par programmation des critères de segmentation d&#39;audience.

**Appels d&#39;événement Envoyer des données à Audience Manager**

An event call sends data from your website to [!DNL Audience Manager]. L&#39;appel contient les données de signal, de caractéristique et de segment dans une requête HTTP. The event itself is everything after the `/event` part of a URL string. As shown in the example below, this process requires only a single event call to pass in multiple variables to [!DNL Audience Manager].

```
https://<domain>/event?product=camera&price>100
```

>[!MORE_ LIKE_ THIS]
>
>* [Segments : Objet, composition et règles](../features/segments/segments-purpose.md)

