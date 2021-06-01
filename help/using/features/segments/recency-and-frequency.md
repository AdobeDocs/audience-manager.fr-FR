---
description: Dans le créateur de segments, la récence et la fréquence vous permettent de segmenter les visiteurs selon des actions qui se produisent ou se répètent au cours d’un intervalle quotidien défini.
seo-description: Dans le créateur de segments, la récence et la fréquence vous permettent de segmenter les visiteurs selon des actions qui se produisent ou se répètent au cours d’un intervalle quotidien défini.
seo-title: Récence et fréquence
solution: Audience Manager
title: Récence et fréquence
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: 'Segments '
exl-id: c00563f0-d270-4d4d-abeb-4b4b81aa68b8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 3%

---

# Récence et fréquence {#recency-and-frequency}

Dans [!UICONTROL Segment Builder], la récence et la fréquence vous permettent de segmenter les visiteurs en fonction d’actions qui se produisent ou se répètent au cours d’un intervalle quotidien défini.

L’Audience Manager définit [!DNL recency] et [!DNL frequency] comme suit :

* **[!UICONTROL Recency]:** récemment qu’un utilisateur a consulté ou qualifié pour une (ou plusieurs)  [!UICONTROL traits].
* **[!UICONTROL Frequency]:** Taux auquel un utilisateur a consulté ou qualifié pour une (ou plusieurs)  [!UICONTROL traits].

[!UICONTROL Recency] Les  [!UICONTROL Frequency] paramètres et vous aident à segmenter les visiteurs en fonction de leur niveau d’intérêt réel (ou perçu) pour un site, une section ou un élément créatif particulier. Par exemple, les utilisateurs qui remplissent les critères d’un segment avec des exigences de récence/fréquence élevée peuvent être plus intéressés par un site ou un produit que les utilisateurs qui visitent moins souvent ou moins fréquemment.

## Emplacement des paramètres [!UICONTROL Recency and Frequency] {#location}

Dans [!UICONTROL Segment Builder], les paramètres [!UICONTROL Recency] et [!UICONTROL Frequency] se trouvent dans la section [!UICONTROL Basic View] du panneau [!UICONTROL Traits]. Cliquez sur l’icône de l’horloge pour afficher ces commandes.

![](assets/recency_frequency.png)

## Limites et règles {#limitations-rules}

Examinez et comprenez ces limites et règles lorsque vous souhaitez appliquer la récence et la fréquence aux caractéristiques de vos segments.

### [!UICONTROL Recency] {#recency}

<table id="table_026064124C694D75B7A960457D50170B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limite ou règle </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Valeur minimale</b> </p> </td> 
   <td colname="col2"> <p>La récence doit être supérieure à 0. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>Types de caractéristiques</b> </p> </td> 
   <td colname="col2"> <p>Vous pouvez appliquer des contrôles de récence uniquement aux caractéristiques basées sur des règles et des dossiers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Caractéristiques tierces</b> </p> </td> 
   <td colname="col2"> <p>Vous ne pouvez pas définir de règles de récence sur des caractéristiques tierces individuelles ou des groupes de caractéristiques qui contiennent des caractéristiques tierces. La récence et la fréquence s’appliquent uniquement à vos propres caractéristiques. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Frequency] {#frequency}

<table id="table_EBD621D26C8B4D03933E8C0753C892A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limite ou règle </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Caractéristiques tierces</b> </p> </td> 
   <td colname="col2"> <p>Vous ne pouvez pas définir de règles de fréquence sur des caractéristiques tierces individuelles ou des groupes de caractéristiques qui contiennent des caractéristiques tierces. La récence et la fréquence s’appliquent uniquement à vos propres caractéristiques. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Types de caractéristiques</b> </p> </td> 
   <td colname="col2"> <p>Vous pouvez appliquer des contrôles de fréquence uniquement aux caractéristiques basées sur des règles et des dossiers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions de récence</b> </p> </td> 
   <td colname="col2"> <p>Vous pouvez configurer les exigences de fréquence <i>sans </i> configurer les exigences de récence. Définissez simplement une valeur de fréquence et laissez le champ de récence vide. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Stratégies de fusion de profils</b> </p> </td> 
   <td colname="col2"> <p>Voir <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Fréquence des caractéristiques, représentations graphiques externes des appareils et stratégies de fusion de profils</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemples de récence {#recency-examples}

Voici deux exemples de fonctionnement de la récence, selon votre sélection dans l’interface utilisateur :

### Utilisation d’un opérateur inférieur ou égal à (&lt;=)

![Inférieur à égal à](assets/less-than-equal-to.png)

Dans cet exemple, vous sélectionnez l&#39;opérateur &lt;=, comme dans la capture d&#39;écran. Cela qualifie votre utilisateur pour la valeur [!UICONTROL segment] s’il est admissible pour l’une des trois [!UICONTROL traits] au moins trois fois au cours des cinq derniers jours. La chronologie ci-dessous présente la qualification [!UICONTROL segment] au moment de la création de [!UICONTROL segment], le 1er octobre et dix jours plus tard.

![Les cinq derniers jours](assets/last-5-days.png)

### Utilisation d’un opérateur supérieur ou égal à (=>)

![Supérieur à égal à](assets/greater-than-equal-to.png)

Dans cet exemple, vous sélectionnez l&#39;opérateur =>, comme illustré dans la capture d&#39;écran. Cela qualifie votre utilisateur pour le [!UICONTROL segment] s’il est admissible pour l’un des trois [!UICONTROL traits] au moins trois fois à tout moment entre sa première qualification sur la plateforme de l’Audience Manager et l’heure d’interruption il y a cinq jours. La chronologie ci-dessous présente la qualification [!UICONTROL segment] au moment de la création de [!UICONTROL segment], le 1er octobre et dix jours plus tard.

![Qualification antérieure](assets/earlier-qualification.png)


## Exemples de limitation de fréquence {#frequency-capping}

Les expressions de limitation de fréquence incluent tous les utilisateurs dont le nombre de réalisations [!UICONTROL trait] est inférieur à la valeur souhaitée. Voici quelques exemples de droite et de mauvaise qualité :

* Erreur : l’expression `frequency([1000T]) <= 5` inclut tous les utilisateurs qui ont réalisé [!UICONTROL trait] avec l’ID &quot;1000&quot; au maximum cinq fois, mais inclut également les utilisateurs qui n’ont pas réalisé le [!UICONTROL trait]. Par conséquent, l’Audience Manager ne valide pas cette expression pour des raisons de performances, car elle qualifierait trop d’utilisateurs pour la balise [!UICONTROL segment].

* Droite : si vous souhaitez inclure cinq fois au maximum tous les utilisateurs qui ont réalisé le [!UICONTROL trait] avec l’ID &quot;1000&quot;, ajoutez une autre condition à l’expression, afin de vous assurer que les utilisateurs sont qualifiés pour le [!UICONTROL trait] au moins une fois :  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Droite : lorsque vous avez besoin que les exigences de récence/fréquence soient inférieures à un nombre spécifique de fois ou de jours, joignez cette balise [!UICONTROL trait] à une autre avec un opérateur `AND`. En reprenant l’exemple du premier point de puce, cette expression devient valide lorsqu’elle est associée à une autre balise [!UICONTROL trait] comme illustré ici : `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Droite - Pour les cas d’utilisation de la limitation de la fréquence des publicités, vous pouvez créer une règle [!UICONTROL segment] similaire à celle-ci : `(frequency([1000T] <= 2D) >= 5)`. Cette expression inclut tous les utilisateurs qui ont réalisé [!UICONTROL trait] avec l’ID &quot;1000&quot; au cours des deux derniers jours au moins cinq fois. Définissez la limitation de la fréquence en envoyant cette valeur [!UICONTROL segment] au serveur d’annonces avec une valeur `NOT` définie sur la valeur [!UICONTROL segment] dans le serveur d’annonces. Cette approche permet d’obtenir de meilleures performances dans [!DNL Audience Manager] tout en poursuivant le même objectif pour la limitation de la fréquence.

>[!MORELIKETHIS]
>
>* [Contrôles du créateur de segments : Section Caractéristiques](../../features/segments/segment-builder.md#segment-builder-controls-traits)
* [Syntaxe du code utilisé dans l’éditeur d’expressions de segments](../../features/segments/segment-code-syntax.md)

