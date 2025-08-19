---
description: Dans le créateur de segments, la récence et la fréquence vous permettent de segmenter les visiteurs en fonction d’actions qui se produisent ou se répètent sur un intervalle quotidien défini.
seo-description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-title: Recency and Frequency
solution: Audience Manager
title: Récence et fréquence
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: Segments
exl-id: c00563f0-d270-4d4d-abeb-4b4b81aa68b8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 1%

---

# Récence et fréquence {#recency-and-frequency}

Dans [!UICONTROL Segment Builder], la récence et la fréquence vous permettent de segmenter les visiteurs et visiteuses en fonction d’actions qui se produisent ou se répètent sur un intervalle quotidien défini.

Audience Manager définit [!DNL recency] et [!DNL frequency] comme suit :

* **[!UICONTROL Recency]:** date à laquelle un utilisateur a consulté un (ou plusieurs) [!UICONTROL traits] ou s’est qualifié pour celui-ci.
* **[!UICONTROL Frequency]:** taux auquel un utilisateur a consulté ou s’est qualifié pour une (ou plusieurs) [!UICONTROL traits].

Les paramètres [!UICONTROL Recency] et [!UICONTROL Frequency] vous permettent de segmenter les visiteurs et visiteuses en fonction de leur niveau d’intérêt réel (ou perçu) pour un site, une section ou une création particulière. Par exemple, les utilisateurs et utilisatrices qui remplissent les critères d’un segment avec des exigences de récence/fréquence élevées peuvent être plus intéressés par un site ou un produit que les utilisateurs et utilisatrices qui visitent moins souvent ou moins fréquemment.

## Emplacement des paramètres [!UICONTROL Recency and Frequency] {#location}

En [!UICONTROL Segment Builder], les paramètres [!UICONTROL Recency] et [!UICONTROL Frequency] se trouvent dans la section [!UICONTROL Basic View] du panneau [!UICONTROL Traits]. Cliquez sur l’icône d’horloge pour afficher ces commandes.

![](assets/recency_frequency.png)

## Restrictions et règles {#limitations-rules}

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
   <td colname="col2"> <p>Vous pouvez appliquer des contrôles de récence aux caractéristiques de dossiers et basées sur des règles uniquement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Caractéristiques tierces</b> </p> </td> 
   <td colname="col2"> <p>Vous ne pouvez pas définir de règles de récence sur des caractéristiques tierces individuelles ou des groupes de caractéristiques contenant des caractéristiques tierces. La récence et la fréquence s’appliquent uniquement à vos propres caractéristiques. </p> </td> 
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
   <td colname="col2"> <p>Vous ne pouvez pas définir de règles de fréquence sur des caractéristiques tierces individuelles ou des groupes de caractéristiques contenant des caractéristiques tierces. La récence et la fréquence s’appliquent uniquement à vos propres caractéristiques. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Types de caractéristiques</b> </p> </td> 
   <td colname="col2"> <p>Vous pouvez appliquer des contrôles de fréquence aux caractéristiques basées sur des règles et des dossiers uniquement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Exigences de récence</b> </p> </td> 
   <td colname="col2"> <p>Vous pouvez configurer les exigences de fréquence <i>sans</i> configurer les exigences de récence. Définissez simplement une valeur de fréquence et laissez le champ Récence vide. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Stratégies de fusion de profils</b> </p> </td> 
   <td colname="col2"> <p>Voir Fréquence des caractéristiques <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules">, Graphiques d’appareil externe et Règles de fusion de profil</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemples de récence {#recency-examples}

Voici deux exemples de fonctionnement de la récence, en fonction de votre sélection dans l’interface utilisateur :

### Utilisation d’un opérateur inférieur ou égal à (&lt;=)

![Inférieur ou égal à](assets/less-than-equal-to.png)

Dans cet exemple, vous sélectionnez l’opérateur &lt;= , comme illustré dans la capture d’écran. Cela qualifie votre utilisateur pour le [!UICONTROL segment] s’il est éligible à l’un des trois [!UICONTROL traits] au moins trois fois au cours des cinq derniers jours. La chronologie ci-dessous montre la qualification du [!UICONTROL segment] au moment de la création du [!UICONTROL segment], le 1er octobre et dix jours plus tard.

![Cinq derniers jours](assets/last-5-days.png)

### Utilisation d’un opérateur supérieur ou égal à (=>)

![Supérieur ou égal à](assets/greater-than-equal-to.png)

Dans cet exemple, vous sélectionnez l’opérateur =>, comme illustré dans la capture d’écran. Cela qualifie votre utilisateur pour la [!UICONTROL segment] s’il est éligible à l’une des trois [!UICONTROL traits] au moins trois fois à tout moment entre sa première qualification sur la plateforme Audience Manager et la date limite fixée il y a cinq jours. La chronologie ci-dessous montre la qualification du [!UICONTROL segment] au moment de la création du [!UICONTROL segment], le 1er octobre et dix jours plus tard.

![Qualification antérieure](assets/earlier-qualification.png)


## Exemples de limitation de la fréquence {#frequency-capping}

Les expressions de limitation de la fréquence incluent tous les utilisateurs dont le nombre de réalisations [!UICONTROL trait] est inférieur à une valeur souhaitée. Voici quelques exemples réels et erronés :

* Erreur - L’expression `frequency([1000T]) <= 5` inclut tous les utilisateurs qui ont réalisé l’[!UICONTROL trait] avec l’ID « 1 000 » un maximum de cinq fois, mais inclut également les utilisateurs qui n’ont pas réalisé l’[!UICONTROL trait]. Par conséquent, Audience Manager ne valide pas cette expression pour des raisons de performances, car elle qualifierait trop d’utilisateurs pour la [!UICONTROL segment].

* Droite : si vous souhaitez inclure tous les utilisateurs qui ont réalisé l’[!UICONTROL trait] avec l’ID « 1 000 » cinq fois au maximum, ajoutez une autre condition à l’expression, pour vous assurer que les utilisateurs se sont qualifiés pour l’[!UICONTROL trait] au moins une fois : `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* À droite : lorsque vous avez besoin que les exigences en matière de récence/fréquence soient inférieures à un nombre spécifique de fois ou de jours, joignez ce [!UICONTROL trait] à un autre avec un opérateur `AND`. En reprenant l’exemple du premier point, cette expression devient valide lorsqu’elle est jointe à une autre [!UICONTROL trait], comme illustré ici : `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Droite : pour les cas d’utilisation de limitation de la fréquence de la publicité, vous pouvez créer une règle de [!UICONTROL segment] similaire à celle-ci : `(frequency([1000T] <= 2D) >= 5)`. Cette expression inclut tous les utilisateurs qui ont réalisé le [!UICONTROL trait] avec l’ID « 1 000 » au cours des 2 derniers jours au moins cinq fois. Définissez le capping de la fréquence en envoyant ce [!UICONTROL segment] au serveur d’annonces avec un `NOT` défini sur le [!UICONTROL segment] du serveur d’annonces. Cette approche permet d&#39;obtenir de meilleures performances en [!DNL Audience Manager] tout en poursuivant le même objectif de limitation de fréquence.

>[!MORELIKETHIS]
>
>* [Contrôles du créateur de segments : section Caractéristiques](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Syntaxe du code utilisé dans l’éditeur d’expressions de segments](../../features/segments/segment-code-syntax.md)
