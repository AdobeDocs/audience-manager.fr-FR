---
description: Détaille les composants d’un segment d’Audience Manager, les expressions utilisées pour définir les critères de qualification des audiences et la façon dont les données sont transmises lors d’un appel d’événement.
landing-page-description: Décrit les composants d’un segment, les expressions utilisées pour définir les critères de qualification des audiences et la manière dont les données sont transmises.
seo-title: Signaux, caractéristiques et segments
solution: Audience Manager
title: Signaux, caractéristiques et segments
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: 'Référence '
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 15%

---

# [!UICONTROL Signals],  [!UICONTROL Traits]et  [!UICONTROL Segments] {#signals-traits-and-segments}

Décrit les composants d’un [!DNL Audience Manager] [!UICONTROL segment], les expressions utilisées pour définir les critères de qualification des audiences et la manière dont les données sont transmises dans un appel d’événement.

## Composition et objectif

[!DNL Audience Manager] Les données se composent de  [!UICONTROL signals],  [!UICONTROL traits],  [!UICONTROL segments] et des règles de qualification associées. Les éléments de données et les règles se combinent pour créer [!UICONTROL segments]. [!UICONTROL Segments] organiser les visiteurs du site en groupes connexes ; Le tableau suivant définit les trois composants principaux dans une balise [!DNL Audience Manager] [!UICONTROL segment].

| Élément | Se compose de | Exemple |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] sont les plus petites unités de données de  [!DNL Audience Manager] et sont exprimées en paires  [clé-valeur](../reference/key-value-pairs-explained.md).<br><br><ul><li>La clé est une constante qui définit un jeu de données (par exemple, genre, couleur, prix).</li><li>La valeur est une variable liée à la constante (par exemple, mâle/femelle, vert, 100).</li></ul>Les opérateurs de comparaison se joignent à la paire clé-valeur et définissent la relation entre eux. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Combinaisons d’une ou de plusieurs [!UICONTROL signals].<br><br> [!DNL Boolean] les expressions et les opérateurs de comparaison permettent de créer des règles  [!UICONTROL trait] de qualification. <br><br>Créez des exigences de qualification précises avec des combinaisons de  [!UICONTROL traits] et de  [!UICONTROL trait] groupes. | À partir de la [!UICONTROL signals] disponible, vous pouvez créer une règle `High End Camera Browser` exprimée comme suit : `product=camera AND price>1000` |
| [!UICONTROL Segment] | Utilisateurs qui partagent un ensemble d’attributs communs et répondent aux critères [!UICONTROL traits] associés. [!DNL Boolean] les expressions, ainsi que les exigences de récence/fréquence, vous permettent de créer des règles  [!UICONTROL segment] de qualification.<br><br> Créez des exigences de qualification précises avec des combinaisons de  [!UICONTROL trait] et de  [!UICONTROL segment] règles. | À partir des [!UICONTROL traits] et [!UICONTROL signals] disponibles, vous pouvez créer une règle [!UICONTROL segment] exprimée comme suit :`(product=camera AND type=digital SLR) OR (price>1000)` |

Utilisez le diagramme ci-dessous pour garder une note mentale de la relation entre [!UICONTROL signals], [!UICONTROL traits] et [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Création  [!UICONTROL Traits] et  [!UICONTROL Segment] règles à l’aide des outils visuels et des éditeurs de code**

Les clients gèrent [!UICONTROL traits] et [!UICONTROL segments] avec des outils visuels et des éditeurs de code dans l’interface utilisateur [!DNL Audience Manager]. Les outils visuels vous permettent de créer des règles à l’aide des fonctions de recherche, des options contextuelles, des menus déroulants et de la fonctionnalité de glisser-déposer. Les éditeurs de code permettent aux utilisateurs avancés de développer par programmation des critères de segmentation d’audience.

**Appels d’événement Envoi de données à[!DNL Audience Manager]**

Un appel d’événement envoie des données de votre site web à [!DNL Audience Manager]. L’appel contient les données [!UICONTROL signal], [!UICONTROL trait] et [!UICONTROL segment] d’une requête [!DNL HTTP]. L’événement lui-même est tout ce qui suit la partie `/event` d’une chaîne [!DNL URL]. Comme illustré dans l’exemple ci-dessous, ce processus ne nécessite qu’un seul appel d’événement pour transmettre plusieurs variables à [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segments : objectif, composition et règles](../features/segments/segments-purpose.md)

