---
description: Dans le créateur de segments, la récence et la fréquence permettent de segmenter les visiteurs en fonction des actions qui surviennent ou se répètent sur un intervalle quotidien défini.
seo-description: Dans le créateur de segments, la récence et la fréquence permettent de segmenter les visiteurs en fonction des actions qui surviennent ou se répètent sur un intervalle quotidien défini.
seo-title: Récence et fréquence
solution: Audience Manager
title: Récence et fréquence
uuid: faadd 18 a-bf 27-4 b 73-995 e -9809 f 52 f 5350
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Recency and Frequency {#recency-and-frequency}

In [!UICONTROL Segment Builder], recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.

Audience Manager defines [!DNL recency] and [!DNL frequency] as follows:

* **[!UICONTROL Recency]:** Nombre de jours pendant lesquels un utilisateur a affiché ou qualifié une ou plusieurs caractéristiques.
* **[!UICONTROL Frequency]:** Taux d&#39;affichage ou de qualification d&#39;un utilisateur pour une ou plusieurs caractéristiques.

[!UICONTROL Recency] et [!UICONTROL Frequency] les paramètres vous aident à segmenter les visiteurs en fonction de leur niveau réel (ou perçu) d&#39;intérêt dans un site, une section ou un élément créatif particulier. Par exemple, les utilisateurs qui remplissent les critères d&#39;un segment avec des exigences de récence/fréquence élevées peuvent être plus intéressés par un site ou un produit que les utilisateurs qui visitent moins souvent ou moins souvent.

## Location of Recency and Frequency Settings {#location}

In [!UICONTROL Segment Builder], [!UICONTROL Recency] and [!UICONTROL Frequency] settings are located in the [!UICONTROL Basic View] section of the [!UICONTROL Traits] panel. Cliquez sur l&#39;icône représentant une horloge pour exposer ces commandes.

![](assets/recency_frequency.png)

## Limitations and Rules {#limitations-rules}

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
   <td colname="col2"> <p>Vous ne pouvez pas définir de règles de récence sur des caractéristiques tierces ou des groupes de caractéristiques qui contiennent des caractéristiques tierces. La récence et la fréquence s'appliquent uniquement à vos propres caractéristiques. </p> </td> 
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
   <td colname="col2"> <p>Vous ne pouvez pas définir de règles de fréquence sur des caractéristiques tierces ou des groupes de caractéristiques qui contiennent des caractéristiques tierces. La récence et la fréquence s'appliquent uniquement à vos propres caractéristiques. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions de récence</b> </p> </td> 
   <td colname="col2"> <p>You can configure frequency requirements <i>without</i> configuring recency requirements. Il suffit de définir une valeur de fréquence et de laisser le champ de récence vide. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Règles de fusion de profils</b> </p> </td> 
   <td colname="col2"> <p>See <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Trait Frequency, External Device Graphs, and Profile Merge Rules</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Frequency Capping Examples {#frequency-capping}

Les expressions de plafonnement de fréquence incluent tous les utilisateurs dont le nombre de realizations de caractéristiques est inférieur à la valeur souhaitée. Voici quelques exemples :

* The expression `frequency([1000T]) <= 5` includes all users that have realized the trait with the ID &quot;1000&quot; a maximum of five times, including users who have not realized the trait.
* When you need recency/frequency requirements to be less than a specific number of times or days, join that trait to another with an `AND` operator. Using the example above, this expression becomes valid when joined with another trait as shown here: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* For advertising frequency-capping use cases, you could create a segment rule similar to this: `(frequency([1000T] <= 2D) >= 5)`. Cette expression inclut tous les utilisateurs qui ont réalisé la caractéristique avec l&#39;identifiant « 1000 » au moins cinq fois au moins cinq fois. Set frequency capping by sending this segment to the ad server with a `NOT` set on the segment in the ad server. This approach achieves greater performance in [!DNL Audience Manager] while still serving the same purpose for frequency capping.

>[!MORE_ LIKE_ THIS]
>
>* [Commandes du créateur de segments : Section Caractéristiques](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Syntaxe du code utilisée dans l&#39;éditeur d&#39;expression de segment](../../features/segments/segment-code-syntax.md)

