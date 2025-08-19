---
description: Découvrez les composants d’un segment et les expressions utilisées pour définir les critères de qualification des audiences. Trouvez également des informations sur la manière dont les données sont transmises.
landing-page-description: Découvrez les composants d’un segment et les expressions utilisées pour définir les critères de qualification des audiences. Trouvez également des informations sur la manière dont les données sont transmises.
short-description: Découvrez les composants d’un segment et les expressions utilisées pour définir les critères de qualification des audiences. Trouvez également des informations sur la manière dont les données sont transmises.
seo-title: Signals, Traits, and Segments
solution: Audience Manager
title: Signaux, caractéristiques et segments
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: Reference
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 21%

---

# [!UICONTROL Signals], [!UICONTROL Traits] et [!UICONTROL Segments] {#signals-traits-and-segments}

Décrit les composants d’un [!DNL Audience Manager] [!UICONTROL segment], les expressions utilisées pour définir les critères de qualification des audiences et la manière dont les données sont transmises dans un appel d’événement.

## Composition et objet

[!DNL Audience Manager] données se composent de [!UICONTROL signals], de [!UICONTROL traits], de [!UICONTROL segments] et des règles de qualification associées. Les éléments de données et les règles se combinent pour créer des [!UICONTROL segments]. [!UICONTROL Segments] organiser les visiteurs et visiteuses du site en groupes associés. Le tableau suivant définit les trois composants principaux d’un [!DNL Audience Manager] [!UICONTROL segment].

| Élément | Se compose de | Exemple |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] sont les plus petites unités de données en [!DNL Audience Manager] et sont exprimées en [paires clé-valeur](../reference/key-value-pairs-explained.md).<br><br><ul><li>La clé est une constante qui définit un jeu de données (par exemple, genre, couleur, prix).</li><li>La valeur est une variable liée à la constante (par exemple, mâle/femelle, vert, 100).</li></ul>Les opérateurs de comparaison rejoignent la paire clé-valeur et définissent la relation entre eux. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Combinaisons d’un ou de plusieurs [!UICONTROL signals].<br><br> [!DNL Boolean] expressions et les opérateurs de comparaison vous permettent de créer des règles de qualification [!UICONTROL trait]. <br><br>Créer des exigences de qualification précises avec des combinaisons de groupes [!UICONTROL traits] et [!UICONTROL trait]. | Dans les [!UICONTROL signals] disponibles, vous pouvez créer une règle de `High End Camera Browser` exprimée sous la forme : `product=camera AND price>1000` |
| [!UICONTROL Segment] | Utilisateurs qui partagent un ensemble d’attributs communs et remplissent les critères pour les [!UICONTROL traits] associés. [!DNL Boolean] expressions, ainsi que les exigences de récence/fréquence, vous permettent de créer des règles de qualification [!UICONTROL segment].<br><br> Créer des exigences de qualification précises avec des combinaisons de règles de [!UICONTROL trait] et de [!UICONTROL segment]. | À partir des [!UICONTROL traits] et des [!UICONTROL signals] disponibles, vous pouvez créer une règle de [!UICONTROL segment] exprimée sous la forme : `(product=camera AND type=digital SLR) OR (price>1000)` |

Utilisez le diagramme ci-dessous pour conserver une note mentale sur la relation entre [!UICONTROL signals], [!UICONTROL traits] et [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Créer des règles de [!UICONTROL Traits] et de [!UICONTROL Segment] à l’aide d’outils visuels et d’éditeurs de code**

Les clients gèrent les [!UICONTROL traits] et les [!UICONTROL segments] à l’aide d’outils visuels et d’éditeurs de code dans l’interface utilisateur [!DNL Audience Manager]. Les outils visuels vous permettent de créer des règles à l’aide des fonctions de recherche, des options pop-up, des menus déroulants et des fonctionnalités de glisser-déposer. Les éditeurs de code permettent aux utilisateurs expérimentés de développer des critères de segmentation d’audience par programmation.

**Les appels d’événement envoient des données à[!DNL Audience Manager]**

Un appel d’événement envoie des données de votre site web à [!DNL Audience Manager]. L’appel contient des données [!UICONTROL signal], [!UICONTROL trait] et [!UICONTROL segment] dans une requête [!DNL HTTP]. L’événement lui-même est tout ce qui suit la partie `/event` d’une chaîne de [!DNL URL]. Comme illustré dans l’exemple ci-dessous, ce processus ne nécessite qu’un seul appel d’événement pour transmettre plusieurs variables à [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segments : objectif, composition et règles](../features/segments/segments-purpose.md)
