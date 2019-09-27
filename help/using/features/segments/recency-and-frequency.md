---
description: Dans le créateur de segments, la récence et la fréquence vous permettent de segmenter les visiteurs en fonction des actions survenant ou se répétant au cours d’un intervalle quotidien défini.
seo-description: Dans le créateur de segments, la récence et la fréquence vous permettent de segmenter les visiteurs en fonction des actions survenant ou se répétant au cours d’un intervalle quotidien défini.
seo-title: Récence et fréquence
solution: Audience Manager
title: Récence et fréquence
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
translation-type: tm+mt
source-git-commit: 1cbff10b9e978755e139e7d5b996249de5ebb5bd

---


# Recency and Frequency {#recency-and-frequency}

Dans [!UICONTROL Segment Builder]ce cas, la récence et la fréquence vous permettent de segmenter les visiteurs en fonction des actions survenant ou se répétant au cours d’un intervalle quotidien défini.

Audience Manager définit [!DNL recency] et [!DNL frequency] comme suit :

* **[!UICONTROL Recency]** : Récemment où un utilisateur a consulté ou s’est qualifié pour une (ou plusieurs) caractéristiques.
* **[!UICONTROL Frequency]** : Taux auquel un utilisateur a consulté ou s’est qualifié pour une (ou plusieurs) caractéristiques.

[!UICONTROL Recency] et [!UICONTROL Frequency] les paramètres vous aident à segmenter les visiteurs en fonction de leur niveau d’intérêt réel (ou perçu) pour un site, une section ou un élément créatif particulier. For example, users who qualify for a segment with high recency/frequency requirements may be more interested in a site or product than users who visit less often or less frequently.

## Location of Recency and Frequency Settings {#location}

In ,  and  settings are located in the  section of the  panel. [!UICONTROL Segment Builder][!UICONTROL Recency][!UICONTROL Frequency][!UICONTROL Basic View][!UICONTROL Traits] Click the clock icon to expose these controls.

![](assets/recency_frequency.png)

## Limitations and Rules {#limitations-rules}

Review and understand these limits and rules when you want to apply recency and frequency to traits in your segments.

### Récence

<table id="table_026064124C694D75B7A960457D50170B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limit or Rule </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Valeur minimale</b> </p> </td> 
   <td colname="col2"> <p>Recency must be greater than 0. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>Trait Types</b> </p> </td> 
   <td colname="col2"> <p>You can apply recency controls to rule-based and folder traits only. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Third-Party Traits</b> </p> </td> 
   <td colname="col2"> <p>You cannot set recency rules on individual third-party traits or trait groups that contain third-party traits. Recency and frequency applies to your own traits only. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Fréquence

<table id="table_EBD621D26C8B4D03933E8C0753C892A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limit or Rule </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Caractéristiques tierces</b> </p> </td> 
   <td colname="col2"> <p>Vous ne pouvez pas définir de règles de fréquence sur des caractéristiques tierces ou des groupes de caractéristiques qui contiennent des caractéristiques tierces. La récence et la fréquence s'appliquent à vos propres caractéristiques uniquement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Types de caractéristiques</b> </p> </td> 
   <td colname="col2"> <p>Vous pouvez appliquer des contrôles de fréquence uniquement aux caractéristiques basées sur des règles et des dossiers. </p> </td> 
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

## Exemples de récence {#recency-examples}

Voici deux exemples de fonctionnement de la récence, selon votre sélection dans l’interface utilisateur :

### Utilisation d’un opérateur inférieur ou égal à (&lt;=)

![Inférieur à égal à](assets/less-than-equal-to.png)

Dans cet exemple, vous sélectionnez l’opérateur &lt;=, comme illustré dans la capture d’écran. Votre utilisateur est admissible pour le segment s’il est admissible à l’une des trois caractéristiques au moins trois fois au cours des cinq derniers jours. La chronologie ci-dessous montre la qualification du segment au moment de la création du segment, le 1er octobre et dix jours plus tard.

![Cinq derniers jours](assets/last-5-days.png)

### Utilisation d’un opérateur supérieur ou égal à (=&gt;)

![Supérieur à égal à](assets/greater-than-equal-to.png)

Dans cet exemple, vous sélectionnez l’opérateur =&gt;, comme illustré dans la capture d’écran. Cela permet à votre utilisateur d’accéder au segment s’il est admissible à l’une des trois caractéristiques au moins trois fois à chaque fois entre sa première qualification sur la plate-forme Audience Manager et le délai d’expiration il y a cinq jours. The timeline below shows the segment qualification at the time the segment is created, on October 1st, and ten days later.

![Qualification antérieure](assets/earlier-qualification.png)


## Exemples de plafonnement des fréquences {#frequency-capping}

Les expressions de plafonnement des fréquences incluent tous les utilisateurs dont le nombre de réalisations de caractéristiques est inférieur à une valeur souhaitée. Voici quelques exemples de droite et de mauvaise qualité :

* Erreur : l’expression `frequency([1000T]) <= 5` inclut tous les utilisateurs qui ont réalisé que la caractéristique avec l’ID "1000" était au maximum cinq fois, mais inclut également les utilisateurs qui n’ont pas réalisé la caractéristique. Par conséquent, Audience Manager ne valide pas cette expression pour des raisons de performances, car il qualifierait trop d’utilisateurs pour le segment.

* Droit - Si vous souhaitez inclure tous les utilisateurs qui ont réalisé que la caractéristique avec l’ID "1000" était au maximum cinq fois, ajoutez une autre condition à l’expression, afin de vous assurer que les utilisateurs sont qualifiés pour la caractéristique au moins une fois :  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Droit - Lorsque vous avez besoin que les exigences de récence/fréquence soient inférieures à un nombre spécifique de fois ou de jours, joignez cette caractéristique à une autre avec un `AND` opérateur. Using the example in the first bullet point, this expression becomes valid when joined with another trait as shown here: .`frequency([1000T]) <= 5 AND isSiteVisitorTrait`

* Right - For advertising frequency-capping use cases, you could create a segment rule similar to this: . `(frequency([1000T] <= 2D) >= 5)` This expression includes all users that have realized the trait with the ID "1000" in the past 2 days at least five times. Set frequency capping by sending this segment to the ad server with a  set on the segment in the ad server. `NOT` This approach achieves greater performance in  while still serving the same purpose for frequency capping.[!DNL Audience Manager]

>[!MORE_LIKE_THIS]
>
>* [Segment Builder Controls: Traits Section](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Code Syntax Used in the Segment Expression Editor](../../features/segments/segment-code-syntax.md)

