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
source-wordcount: '0'
ht-degree: 0%

---

# [!UICONTROL Signals], [!UICONTROL Traits], et [!UICONTROL Segments] {#signals-traits-and-segments}

Décrit les composants d’une [!DNL Audience Manager] [!UICONTROL segment], les expressions utilisées pour définir les critères de qualification de l’audience et la manière dont les données sont transmises dans un appel d’événement.

## Composition et objectif

[!DNL Audience Manager] Les données se composent de [!UICONTROL signals], [!UICONTROL traits], [!UICONTROL segments]et les règles de qualification associées. Les éléments de données et les règles se combinent pour créer [!UICONTROL segments]. [!UICONTROL Segments] organiser les visiteurs du site en groupes connexes ; Le tableau suivant définit les trois composants principaux d’une [!DNL Audience Manager] [!UICONTROL segment].

| Élément | Se compose de | Exemple |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] sont les plus petites unités de données dans [!DNL Audience Manager] et sont exprimés comme [paires clé-valeur](../reference/key-value-pairs-explained.md).<br><br><ul><li>La clé est une constante qui définit un jeu de données (par exemple, genre, couleur, prix).</li><li>La valeur est une variable liée à la constante (par exemple, mâle/femelle, vert, 100).</li></ul>Les opérateurs de comparaison se joignent à la paire clé-valeur et définissent la relation entre eux. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Combinaisons d’une ou de plusieurs [!UICONTROL signals].<br><br> [!DNL Boolean] les expressions et les opérateurs de comparaison permettent de créer [!UICONTROL trait] règles de qualification. <br><br>Créer des exigences de qualification précises avec des combinaisons [!UICONTROL traits] et [!UICONTROL trait] groupes. | Disponible [!UICONTROL signals], vous pouvez créer une `High End Camera Browser` règle exprimée en : `product=camera AND price>1000` |
| [!UICONTROL Segment] | Utilisateurs qui partagent un ensemble d’attributs communs et répondent aux critères des utilisateurs associés [!UICONTROL traits]. [!DNL Boolean] les expressions, ainsi que les exigences de récence/fréquence, vous permettent de créer [!UICONTROL segment] règles de qualification.<br><br> Créer des exigences de qualification précises avec des combinaisons [!UICONTROL trait] et [!UICONTROL segment] règles. | Disponible [!UICONTROL traits] et [!UICONTROL signals], vous pouvez créer une [!UICONTROL segment] règle exprimée en :`(product=camera AND type=digital SLR) OR (price>1000)` |

Utilisez le diagramme ci-dessous pour garder une note mentale de la relation entre [!UICONTROL signals], [!UICONTROL traits], et [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Build [!UICONTROL Traits] et [!UICONTROL Segment] Règles avec les outils visuels et les éditeurs de code**

Gestion des clients [!UICONTROL traits] et [!UICONTROL segments] avec les outils visuels et les éditeurs de code dans la variable [!DNL Audience Manager] de l’interface utilisateur. Les outils visuels vous permettent de créer des règles à l’aide des fonctions de recherche, des options contextuelles, des menus déroulants et de la fonctionnalité de glisser-déposer. Les éditeurs de code permettent aux utilisateurs avancés de développer par programmation des critères de segmentation d’audience.

**Appels d’événement Envoi de données à[!DNL Audience Manager]**

Un appel d’événement envoie des données de votre site web vers [!DNL Audience Manager]. L’appel contient [!UICONTROL signal], [!UICONTROL trait], et [!UICONTROL segment] données d’une [!DNL HTTP] requête. L’événement lui-même est tout ce qui suit le `/event` partie d’une [!DNL URL] chaîne. Comme illustré dans l’exemple ci-dessous, ce processus ne nécessite qu’un seul appel d’événement pour transmettre plusieurs variables à [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segments : objectif, composition et règles](../features/segments/segments-purpose.md)

