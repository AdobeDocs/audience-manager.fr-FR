---
description: Détaille les composants d’un segment d’Audience Manager, les expressions utilisées pour définir les critères de qualification des audiences et la façon dont les données sont transmises lors d’un appel d’événement.
seo-description: Détaille les composants d’un segment d’Audience Manager, les expressions utilisées pour définir les critères de qualification des audiences et la façon dont les données sont transmises lors d’un appel d’événement.
seo-title: Signaux, caractéristiques et segments
solution: Audience Manager
title: Signaux, caractéristiques et segments
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: reference
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 17%

---


# [!UICONTROL Signals],  [!UICONTROL Traits]et  [!UICONTROL Segments] {#signals-traits-and-segments}

Décrit les composants d&#39;un [!DNL Audience Manager] [!UICONTROL segment], les expressions utilisées pour définir les critères de qualification des audiences et la façon dont les données sont transmises dans un appel de événement.

## Composition et objet

[!DNL Audience Manager] les données se composent de règles de qualification  [!UICONTROL signals],  [!UICONTROL traits],  [!UICONTROL segments]et associées. Les éléments de données et les règles se combinent pour créer [!UICONTROL segments]. [!UICONTROL Segments] organiser les visiteurs du site en groupes apparentés. Le tableau suivant définit les trois principaux composants d&#39;un [!DNL Audience Manager] [!UICONTROL segment].

| Élément | Se compose de | Exemple |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] sont les plus petites unités de données dans  [!DNL Audience Manager] et sont exprimées en paires [ ](../reference/key-value-pairs-explained.md)clé-valeur.<br><br><ul><li>La clé est une constante qui définit un jeu de données (par exemple, sexe, couleur, prix).</li><li>La valeur est une variable liée à la constante (ex. : mâle/femelle, vert, 100).</li></ul>Les opérateurs de comparaison se joignent à la paire clé-valeur et définissent la relation entre eux. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Combinaisons d&#39;un ou de plusieurs [!UICONTROL signals].<br><br> [!DNL Boolean] Les expressions et les opérateurs de comparaison vous permettent de créer des règles de  [!UICONTROL trait] qualification. <br><br>Créer des exigences de qualification précises avec des combinaisons de  [!UICONTROL traits] et de  [!UICONTROL trait] groupes. | A partir de [!UICONTROL signals] disponible, vous pouvez créer une règle `High End Camera Browser` exprimée comme suit : `product=camera AND price>1000` |
| [!UICONTROL Segment] | Utilisateurs qui partagent un ensemble d&#39;attributs communs et sont éligibles pour les [!UICONTROL traits] connexes. [!DNL Boolean] Les expressions, ainsi que les exigences de récence/fréquence, vous permettent de créer des règles de  [!UICONTROL segment] qualification.<br><br> Créer des exigences de qualification précises avec des combinaisons de  [!UICONTROL trait] et de  [!UICONTROL segment] règles. | A partir des [!UICONTROL traits] et [!UICONTROL signals] disponibles, vous pouvez créer une règle [!UICONTROL segment] exprimée comme suit :`(product=camera AND type=digital SLR) OR (price>1000)` |

Utilisez le diagramme ci-dessous pour conserver une note mentale de la relation entre [!UICONTROL signals], [!UICONTROL traits] et [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Création  [!UICONTROL Traits] et  [!UICONTROL Segment] règles avec des outils visuels et des éditeurs de code**

Les clients gèrent [!UICONTROL traits] et [!UICONTROL segments] avec des outils visuels et des éditeurs de code dans l&#39;interface utilisateur [!DNL Audience Manager]. Les outils visuels vous permettent de créer des règles à l’aide de fonctions de recherche, d’options contextuelles, de menus déroulants et de fonctionnalités de glisser-déposer. Les éditeurs de code offrent aux utilisateurs expérimentés la possibilité de développer par programmation des critères de segmentation des audiences.

**Appels de événement Envoyer des données à[!DNL Audience Manager]**

Un appel de événement envoie des données de votre site Web à [!DNL Audience Manager]. L&#39;appel contient des données [!UICONTROL signal], [!UICONTROL trait] et [!UICONTROL segment] dans une requête [!DNL HTTP]. Le événement lui-même est tout ce qui suit la partie `/event` d&#39;une chaîne [!DNL URL]. Comme indiqué dans l&#39;exemple ci-dessous, ce processus ne nécessite qu&#39;un seul appel de événement pour transmettre plusieurs variables à [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segments : objectif, composition et règles](../features/segments/segments-purpose.md)

