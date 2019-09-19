---
description: Dans le créateur de segments, la récence et la fréquence vous permettent de segmenter les visiteurs en fonction des actions survenant ou se répétant au cours d’un intervalle quotidien défini.
seo-description: Dans le créateur de segments, la récence et la fréquence vous permettent de segmenter les visiteurs en fonction des actions survenant ou se répétant au cours d’un intervalle quotidien défini.
seo-title: Récence et fréquence
solution: Audience Manager
title: Récence et fréquence
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Recency and Frequency {#recency-and-frequency}

Dans [!UICONTROL Segment Builder]ce cas, la récence et la fréquence vous permettent de segmenter les visiteurs en fonction des actions survenant ou se répétant au cours d’un intervalle quotidien défini.

Audience Manager définit [!DNL recency] et [!DNL frequency] comme suit :

* **[!UICONTROL Recency]** : Nombre de jours pendant lesquels un utilisateur a consulté ou s’est qualifié pour une (ou plusieurs) caractéristiques.
* **[!UICONTROL Frequency]** : Taux auquel un utilisateur a consulté ou s’est qualifié pour une (ou plusieurs) caractéristiques.

[!UICONTROL Recency] et [!UICONTROL Frequency] les paramètres vous aident à segmenter les visiteurs en fonction de leur niveau d’intérêt réel (ou perçu) pour un site, une section ou un élément créatif particulier. Par exemple, les utilisateurs qui remplissent les conditions requises pour un segment avec des exigences de récence/fréquence élevée peuvent être plus intéressés par un site ou un produit que les utilisateurs qui visitent moins souvent ou moins fréquemment.

## Emplacement des paramètres de récence et de fréquence {#location}

Dans [!UICONTROL Segment Builder], [!UICONTROL Recency] et [!UICONTROL Frequency] les paramètres se trouvent dans la [!UICONTROL Basic View] section du [!UICONTROL Traits] panneau. Cliquez sur l’icône de l’horloge pour afficher ces commandes.

![](assets/recency_frequency.png)

## Limites et règles {#limitations-rules}

Examinez et comprenez ces limites et règles lorsque vous souhaitez appliquer la récence et la fréquence aux caractéristiques de vos segments.

### Récence

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
   <td colname="col1"> <p> <b>Caractéristiques tierces</b> </p> </td> 
   <td colname="col2"> <p>Vous ne pouvez pas définir de règles de récence sur des caractéristiques tierces ou des groupes de caractéristiques qui contiennent des caractéristiques tierces. La récence et la fréquence s'appliquent à vos propres caractéristiques uniquement. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Fréquence

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
   <td colname="col2"> <p>Vous ne pouvez pas définir de règles de fréquence sur des caractéristiques tierces ou des groupes de caractéristiques qui contiennent des caractéristiques tierces. La récence et la fréquence s'appliquent à vos propres caractéristiques uniquement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions de récence</b> </p> </td> 
   <td colname="col2"> <p>Vous pouvez configurer les exigences de fréquence <i>sans</i> configurer les exigences de récence. Il vous suffit de définir une valeur de fréquence et de laisser le champ récence vide. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Règles de fusion de profils</b> </p> </td> 
   <td colname="col2"> <p>Voir <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Fréquence des caractéristiques, Graphiques de périphériques externes et Règles</a>de fusion de profils. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemples de plafonnement des fréquences {#frequency-capping}

Les expressions de plafonnement des fréquences incluent tous les utilisateurs dont le nombre de réalisations de caractéristiques est inférieur à une valeur souhaitée. Voici quelques exemples :

* L’expression `frequency([1000T]) <= 5` inclut tous les utilisateurs qui ont réalisé la caractéristique avec l’ID "1 000" au maximum cinq fois, y compris les utilisateurs qui n’ont pas réalisé la caractéristique.
* Lorsque vous avez besoin que les exigences de récence/fréquence soient inférieures à un nombre spécifique de fois ou de jours, joignez cette caractéristique à une autre avec un `AND` opérateur. À l’aide de l’exemple ci-dessus, cette expression devient valide lorsqu’elle est associée à une autre caractéristique, comme illustré ici : `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Pour les cas d’utilisation du plafonnement de la fréquence des publicités, vous pouvez créer une règle de segmentation semblable à celle-ci : `(frequency([1000T] <= 2D) >= 5)`. Cette expression inclut tous les utilisateurs qui ont réalisé au moins cinq fois la caractéristique avec l’ID "1000" au cours des deux derniers jours. Définissez le plafonnement des fréquences en envoyant ce segment au serveur d’annonces avec une `NOT` visionneuse sur le segment dans le serveur d’annonces. Cette approche améliore les performances [!DNL Audience Manager] tout en poursuivant le même objectif pour le plafonnement des fréquences.

>[!MORE_LIKE_This]
>
>* [Contrôles du créateur de segments : Section Caractéristiques](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Syntaxe du code utilisée dans l’éditeur d’expression de segment](../../features/segments/segment-code-syntax.md)

