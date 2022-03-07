---
description: Découvrez les composants d’un segment et les expressions utilisées pour définir les critères de qualification des audiences. Trouvez également des informations sur la manière dont les données sont transmises.
landing-page-description: Découvrez les composants d’un segment et les expressions utilisées pour définir les critères de qualification des audiences. Trouvez également des informations sur la manière dont les données sont transmises.
seo-title: Signals, Traits, and Segments
solution: Audience Manager
title: Signaux, caractéristiques et segments
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: Reference
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
source-git-commit: 865800eb076811db38aec8e98714ad9712804f77
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 2%

---

# [!UICONTROL Signals], [!UICONTROL Traits], et [!UICONTROL Segments] {#signals-traits-and-segments}

Décrit les composants d’une [!DNL Audience Manager] [!UICONTROL segment], les expressions utilisées pour définir les critères de qualification de l’audience et la manière dont les données sont transmises dans un appel d’événement.

## Composition et objectif

[!DNL Audience Manager] Les données se composent de [!UICONTROL signals], [!UICONTROL traits], [!UICONTROL segments]et les règles de qualification associées. The data elements and rules combine to create [!UICONTROL segments]. [!UICONTROL Segments] organize site visitors into related groups. Le tableau suivant définit les trois composants principaux d’une [!DNL Audience Manager] [!UICONTROL segment].

| Élément | Se compose de | Exemple |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] sont les plus petites unités de données dans [!DNL Audience Manager] et sont exprimés comme [paires clé-valeur](../reference/key-value-pairs-explained.md).<br><br><ul><li>La clé est une constante qui définit un jeu de données (par exemple, genre, couleur, prix).</li><li>La valeur est une variable liée à la constante (par exemple, mâle/femelle, vert, 100).</li></ul>Comparison operators join the key-value pair and set the relationship between them. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Combinaisons d’une ou de plusieurs [!UICONTROL signals].<br><br> [!DNL Boolean] les expressions et les opérateurs de comparaison permettent de créer [!UICONTROL trait] règles de qualification. <br><br>Créer des exigences de qualification précises avec des combinaisons [!UICONTROL traits] et [!UICONTROL trait] groupes. | Disponible [!UICONTROL signals], vous pouvez créer une `High End Camera Browser` règle exprimée en : `product=camera AND price>1000` |
| [!UICONTROL Segment] | Utilisateurs qui partagent un ensemble d’attributs communs et répondent aux critères des utilisateurs associés [!UICONTROL traits]. [!DNL Boolean] les expressions, ainsi que les exigences de récence/fréquence, vous permettent de créer [!UICONTROL segment] règles de qualification.<br><br> Créer des exigences de qualification précises avec des combinaisons [!UICONTROL trait] et [!UICONTROL segment] règles. | Disponible [!UICONTROL traits] et [!UICONTROL signals], vous pouvez créer une [!UICONTROL segment] règle exprimée en :`(product=camera AND type=digital SLR) OR (price>1000)` |

Utilisez le diagramme ci-dessous pour garder une note mentale de la relation entre [!UICONTROL signals], [!UICONTROL traits], et [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Build [!UICONTROL Traits] et [!UICONTROL Segment] Règles avec les outils visuels et les éditeurs de code**

Gestion des clients [!UICONTROL traits] et [!UICONTROL segments] avec les outils visuels et les éditeurs de code dans la variable [!DNL Audience Manager] de l’interface utilisateur. The visual tools let you create rules using search features, pop-up options, drop-down menus, and drag and drop functionality. Les éditeurs de code permettent aux utilisateurs avancés de développer par programmation des critères de segmentation d’audience.

**Appels d’événement Envoi de données à[!DNL Audience Manager]**

Un appel d’événement envoie des données de votre site web vers [!DNL Audience Manager]. L’appel contient [!UICONTROL signal], [!UICONTROL trait], et [!UICONTROL segment] données d’une [!DNL HTTP] requête. L’événement lui-même est tout ce qui suit le `/event` partie d’une [!DNL URL] chaîne. As shown in the example below, this process requires only a single event call to pass in multiple variables to [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segments : objectif, composition et règles](../features/segments/segments-purpose.md)

