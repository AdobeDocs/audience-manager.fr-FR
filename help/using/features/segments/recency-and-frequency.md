---
description: Dans le créateur de segments, la récence et la fréquence vous permettent de segmenter les visiteurs en fonction des actions qui se produisent ou se répètent au cours d’un intervalle quotidien défini.
seo-description: Dans le créateur de segments, la récence et la fréquence vous permettent de segmenter les visiteurs en fonction des actions qui se produisent ou se répètent au cours d’un intervalle quotidien défini.
seo-title: Récence et fréquence
solution: Audience Manager
title: Récence et fréquence
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 0%

---


# Recency and Frequency {#recency-and-frequency}

Dans [!UICONTROL Segment Builder], la récence et la fréquence vous permettent de segmenter les visiteurs en fonction des actions qui se produisent ou se répètent au cours d’un intervalle quotidien défini.

L&#39;Audience Manager définit [!DNL recency] et [!DNL frequency] comme suit :

* **[!UICONTROL Recency]:**Récemment où un utilisateur a consulté ou s’est qualifié pour une (ou plusieurs)[!UICONTROL traits].
* **[!UICONTROL Frequency]:**Taux auquel un utilisateur a consulté ou s’est qualifié pour une (ou plusieurs)[!UICONTROL traits].

[!UICONTROL Recency] et [!UICONTROL Frequency] les paramètres vous aident à segmenter les visiteurs en fonction de leur niveau d’intérêt réel (ou perçu) sur un site, une section ou un élément créatif particulier. Par exemple, les utilisateurs qui remplissent les critères d’un segment présentant des exigences de récence/fréquence élevée peuvent s’intéresser davantage à un site ou à un produit qu’aux utilisateurs qui visitent moins souvent ou moins fréquemment.

## Emplacement des [!UICONTROL Recency and Frequency] paramètres {#location}

Dans [!UICONTROL Segment Builder], [!UICONTROL Recency] et [!UICONTROL Frequency] les paramètres se trouvent dans la [!UICONTROL Basic View] section du [!UICONTROL Traits] panneau. Cliquez sur l&#39;icône de l&#39;horloge pour afficher ces commandes.

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
   <td colname="col2"> <p>Vous pouvez appliquer des contrôles de récence uniquement aux caractéristiques basées sur des règles et aux caractéristiques des dossiers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Caractéristiques des tiers</b> </p> </td> 
   <td colname="col2"> <p>Vous ne pouvez pas définir de règles de récence sur des caractéristiques tierces ou des groupes de caractéristiques qui contiennent des caractéristiques tierces. La récence et la fréquence ne s'appliquent qu'à vos propres caractéristiques. </p> </td> 
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
   <td colname="col1"> <p> <b>Caractéristiques des tiers</b> </p> </td> 
   <td colname="col2"> <p>Vous ne pouvez pas définir de règles de fréquence sur des caractéristiques tierces ou des groupes de caractéristiques qui contiennent des caractéristiques tierces. La récence et la fréquence ne s'appliquent qu'à vos propres caractéristiques. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Types de caractéristiques</b> </p> </td> 
   <td colname="col2"> <p>Vous pouvez appliquer des contrôles de fréquence uniquement aux caractéristiques basées sur des règles et aux caractéristiques des dossiers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Exigences de récence</b> </p> </td> 
   <td colname="col2"> <p>Vous pouvez configurer les exigences de fréquence <i>sans</i> configurer les exigences de récence. Il vous suffit de définir une valeur de fréquence et de laisser le champ récence vide. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Règles de fusion des Profils</b> </p> </td> 
   <td colname="col2"> <p>Voir <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Fréquence des caractéristiques, Graphiques de périphériques externes et Règles</a>de fusion des Profils. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemples de récence {#recency-examples}

Voici deux exemples de fonctionnement de la récence, selon votre sélection dans l’interface utilisateur :

### Utilisation d’un opérateur inférieur ou égal à (&lt;=)

![Inférieur à égal à](assets/less-than-equal-to.png)

Dans cet exemple, vous sélectionnez l’opérateur &lt;=, comme illustré dans la capture d’écran. Votre utilisateur est admissible pour le test [!UICONTROL segment] s’il est admissible pour l’un des trois [!UICONTROL traits] au moins trois fois au cours des cinq derniers jours. La chronologie ci-dessous montre la [!UICONTROL segment] qualification au moment de la création de la [!UICONTROL segment] qualification, le 1er octobre, et dix jours plus tard.

![Cinq derniers jours](assets/last-5-days.png)

### Utilisation d&#39;un opérateur supérieur ou égal à (=>)

![Supérieur à égal à](assets/greater-than-equal-to.png)

Dans cet exemple, vous sélectionnez l’opérateur =>, comme illustré dans la capture d’écran. Cela permet à votre utilisateur de bénéficier de l’un des trois critères [!UICONTROL segment] [!UICONTROL traits] de qualification au moins trois fois entre sa première qualification sur la plate-forme d’Audience Manager et la date limite fixée il y a cinq jours. La chronologie ci-dessous montre la [!UICONTROL segment] qualification au moment de la création de la [!UICONTROL segment] qualification, le 1er octobre, et dix jours plus tard.

![Qualification antérieure](assets/earlier-qualification.png)


## Exemples de plafonnement des fréquences {#frequency-capping}

Les expressions de plafonnement des fréquences incluent tous les utilisateurs dont le nombre de [!UICONTROL trait] réalisations est inférieur à une valeur souhaitée. Voici quelques exemples de Right and Wrong :

* Erreur - L’expression `frequency([1000T]) <= 5` inclut tous les utilisateurs qui ont réalisé que [!UICONTROL trait] l’ID &quot;1000&quot; est un maximum de cinq fois, mais inclut également les utilisateurs qui n’ont pas réalisé le [!UICONTROL trait]. Par conséquent, l’Audience Manager ne valide pas cette expression pour des raisons de performances, puisqu’elle permettrait d’élire un trop grand nombre d’utilisateurs pour la [!UICONTROL segment]variable.

* Droit - Si vous souhaitez inclure cinq fois tous les utilisateurs qui ont réalisé que l’ [!UICONTROL trait] ID &quot;1000&quot; ne comporte pas plus de cinq, ajoutez une autre condition à l’expression, afin de vous assurer que les utilisateurs se sont qualifiés au [!UICONTROL trait] moins une fois :  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Droit - Lorsque vous avez besoin que les exigences de récence/fréquence soient inférieures à un nombre spécifique de fois ou de jours, joignez-les [!UICONTROL trait] à un autre opérateur avec un `AND` opérateur. À l’aide de l’exemple figurant dans la première puce, cette expression devient valide lorsqu’elle est associée à une autre [!UICONTROL trait] comme indiqué ci-dessous : `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Droit - Pour les cas d’utilisation du plafonnement de la fréquence des publicités, vous pouvez créer une [!UICONTROL segment] règle similaire à celle-ci : `(frequency([1000T] <= 2D) >= 5)`. Cette expression inclut tous les utilisateurs qui ont réalisé au moins cinq fois la [!UICONTROL trait] lecture avec l’identifiant &quot;1000&quot; au cours des 2 derniers jours. Définissez le plafonnement de la fréquence en l’envoyant [!UICONTROL segment] au serveur d’annonces avec un `NOT` jeu sur le [!UICONTROL segment] serveur d’annonces. Cette approche permet d’obtenir de meilleures performances [!DNL Audience Manager] tout en poursuivant le même objectif pour le plafonnement des fréquences.

>[!MORELIKETHIS]
>
>* [Contrôles du créateur de segments : Section Traits](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Syntaxe du code utilisée dans l’éditeur d’Expressions de segments](../../features/segments/segment-code-syntax.md)

