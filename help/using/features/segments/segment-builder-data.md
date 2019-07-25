---
description: Ajoutez et supprimez des caractéristiques dans le créateur de segments pour afficher les populations de caractéristiques réelles ainsi que les données réelles sur la population de segments. La taille estimée des données permet de créer le segment approprié pour votre campagne.
seo-description: Ajoutez et supprimez des caractéristiques dans le créateur de segments pour afficher les populations de caractéristiques réelles ainsi que les données réelles sur la population de segments. La taille estimée des données permet de créer le segment approprié pour votre campagne.
seo-title: Données sur la population de caractéristiques et de segments dans le créateur de segments
solution: Audience Manager
title: Données sur la population de caractéristiques et de segments dans le créateur de segments
uuid: e 1 e 59 c 0 a-b 4 c 7-4 cad -8485-3667 e 0 a 95 e 83
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Trait and Segment Population Data in Segment Builder {#trait-and-segment-population-data-in-segment-builder}

Add and remove traits in [!UICONTROL Segment Builder] to see actual trait populations along with actual and estimated segment population data. La taille estimée des données permet de créer le segment approprié pour votre campagne.

## Trait Population Data {#trait-population-data}

[!UICONTROL Segment Builder] vous indique [!UICONTROL Total Trait Population] le dernier jour lorsque vous ajoutez une caractéristique à un segment. This data appears in the blue field around your selected trait in the [!UICONTROL Basic View] section.

![](assets/trait-size.png)

Le tableau suivant définit les mesures de population de caractéristiques

<table id="table_9D837CF9ACA04D04BEE5925EC0B4A5D2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Description </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Population totale de caractéristiques</span> </p> </td>
   <td colname="col2"> <p>Nombre d'ID uniques ayant la caractéristique sélectionnée dans leur profil. </p> </td>
  </tr> 
 </tbody> 
</table>

## Calculating Real and Estimated Segment Populations {#calculating-real-estimated-populations}

Lorsque vous créez un segment ou modifiez un segment existant, Audience Manager prend jusqu'à 24 heures pour afficher les résultats pour les populations de segments réelles et en temps réel.

Cependant, Audience Manager peut immédiatement estimer la taille de population totale et totale de votre segment. Ces estimations reposent sur des données historiques échantillonnées et retournent des résultats à l'intervalle de confiance de 95 %.

![](assets/confidence-interval.png)

In [!UICONTROL Segment Builder], a blue bar on the estimated population graphs indicates the possible upper and lower ranges for segment size. Bien que les performances antérieures ne garantissent pas les résultats futurs, les données estimées peuvent vous aider à comprendre la taille potentielle d'un segment nouveau ou modifié.

## Segment Population Data Overview {#segment-populations}

[!UICONTROL Segment Builder] vous montre les données de population de segments lorsque vous créez et modifiez des segments.

* For estimated segment population data (real-time and total), [!UICONTROL Segment Builder] does not update the graphs automatically as you add or remove traits in a segment. Click **[!UICONTROL Calculate Estimates]** to see (or refresh) the estimated population numbers.

* For actual (real) segment population data (real-time and total), [!UICONTROL Segment Builder] updates the segment graph automatically when you load an existing segment. Pour les nouveaux segments ou lorsque vous ajoutez de nouvelles caractéristiques à un segment existant, les données de population réelles ne sont pas mises à jour avant 24 heures après la création du segment.

![](assets/segment-data.png)

Consultez les définitions ci-dessous pour plus d'informations sur les données de population de segments estimées et réelles.

## Estimated Segment Population Data Defined {#estimated-segment-population}

Le tableau suivant définit les mesures de population estimée.

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Estimation réelle - Population de temps (potentielle) </span> </p> </td> 
   <td colname="col2"> <p>Nombre estimé de visiteurs uniques vus en temps réel pour la période spécifiée et qui ont été qualifiés pour le segment au moment où ils ont été vus par Audience Manager. </p> <p>In <span class="wintitle"> Segment Builder</span>, the last 30-day populations for traits (<span class="wintitle"> Total Trait Populations</span>), can be different for traits and segments evaluated in real-times. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">Pour les caractéristiques, la mesure de 30 derniers jours compte le nombre d'utilisateurs uniques qui ont qualifié cette caractéristique au cours des 30 derniers jours. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">Pour les segments évalués en temps réel, la mesure de 30 derniers jours comptabilise le nombre d'utilisateurs qui ont qualifié une caractéristique (dans ce segment) à un moment donné et ont été remarqués de nouveau par Audience Manager au cours des 30 derniers jours. Supposons, par exemple, que vous ayez un utilisateur qui a qualifié une caractéristique il y a 60 jours et ait été vu de nouveau il y a 10 jours. Dans les données, cet utilisateur n'est pas ajouté au nombre de caractéristiques parce qu'il a préalablement qualifié la caractéristique il y a plus de 30 jours. Toutefois, elles seront incluses au dernier nombre de 30 jours pour les segments évalués en temps réel. Cela est dû au fait qu'ils ont qualifié le segment dans l'intervalle de 30 jours. </li>
     </ul> </p> <p> <p>Note: The <span class="wintitle"> Estimated Real-Time Population</span> metric does not include devices that have qualified for a segment based on connections provided by a <span class="wintitle"> Profile Merge Rule</span> that uses a <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> device graph option</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Population totale estimée (potentielle)</span> </p> </td> 
   <td colname="col2"> <p>Nombre estimé de visiteurs uniques qui peuvent se trouver dans votre segment nouveau ou modifié. Comme pour la quasi-totalité des estimations, les performances antérieures ne garantissent pas les résultats futurs, mais vous pouvez utiliser le total estimé pour : </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">Déterminez combien de personnes un segment nouveau ou révisé peut atteindre lorsque vous créez un segment. </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">Ajustez le segment en fonction de vos objectifs. Par exemple, les grands segments sont utiles pour les campagnes de sensibilisation de la marque et les segments plus petits sont utiles pour cibler ou cibler les campagnes. </li> 
     </ul> </p> <p> <p>Note: The <span class="wintitle"> Estimated Total Population</span> metric does not include devices that have qualified for a segment based on connections provided by a <span class="wintitle"> Profile Merge Rule</span> that uses a <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> device graph option</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Existing (Actual) Segment Population Data Defined {#existing-segment-population}

[!UICONTROL Profile Merge Rules] affectent le nombre réel réel de population et de chiffres réels. These totals vary depending on if the [!UICONTROL Profile Merge Rule] a segment belongs to uses a device graph option or not. See also, [Profile Merge Rule Options Defined](../../features/profile-merge-rules/merge-rule-definitions.md).

### Données de population de segments pour les règles de fusion sans option graphique de périphérique

The following table defines the actual real-time and total population metrics when your segments are used by a [!UICONTROL Profile Merge Rule] created without a device graph option. These are the device options settings **[!UICONTROL No Device Options]** and **[!UICONTROL Current Device Proflie]**.

<table id="table_A18C973855DB46A0B39B81F32E0E7540"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Réel - Population temporelle (existante)</span> </p> </td> 
   <td colname="col2"> <p>Nombre réel de visiteurs uniques vus en temps réel pour la période spécifiée et qui ont été qualifiés pour le segment au moment où ils ont été vus par Audience Manager. </p> <p>In <span class="wintitle"> Segment Builder</span>, the last 30-day populations for traits (<span class="wintitle"> Total Trait Populations</span>), can be different for traits and segments evaluated in real-time. </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">Pour les caractéristiques, la mesure de 30 derniers jours compte le nombre d'utilisateurs uniques qui ont qualifié cette caractéristique au cours des 30 derniers jours. </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">Pour les segments évalués en temps réel, la mesure de 30 derniers jours comptabilise le nombre d'utilisateurs qui ont qualifié une caractéristique (dans ce segment) à un moment donné et ont été remarqués de nouveau par Audience Manager au cours des 30 derniers jours. Supposons, par exemple, que vous ayez un utilisateur qui a qualifié une caractéristique il y a 60 jours et ait été vu de nouveau il y a 10 jours. Dans les données, cet utilisateur n'est pas ajouté au nombre de caractéristiques parce qu'il a préalablement qualifié la caractéristique il y a plus de 30 jours. Toutefois, elles seront incluses au dernier nombre de 30 jours pour les segments évalués en temps réel. Cela est dû au fait qu'ils ont qualifié le segment dans l'intervalle de 30 jours. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Population totale (existante)</span> </p> </td> 
   <td colname="col2"> <p>nombre réel de visiteurs uniques qui étaient qualifiés pour le segment depuis hier. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Données de population de segments pour la fusion des règles avec une option Graphique de périphérique

The following table defines the actual real-time and total population metrics when your segments are used by a [!UICONTROL Profile Merge Rule] created with a device graph option. These are the device options settings for the [!UICONTROL Profile Link Device Graph], the [!DNL Adobe] device graph, and other third-party device graph choices that are available to you.

<table id="table_157EC6E5B5C44EB899854CA10B090F60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Réel - Population temporelle (existante)</span> </p> </td> 
   <td colname="col2"> <p>The actual number of devices seen in real-time with current profiles that, when merged with up to 3-other device profiles connected by the device graph, contains the traits to qualify for the segment the moment it was seen by <span class="keyword"> Audience Manager</span>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Population totale (existante)</span> </p> </td> 
   <td colname="col2"> <p>Nombre total de périphériques avec des profils qui, lorsqu'ils sont fusionnés avec trois autres profils de périphérique connectés par le graphique de l'appareil, ont tous été qualifiés pour le segment. </p> </td>
  </tr>
 </tbody>
</table>

### Limites en raison de la récence et des expressions de fréquence lors de l'estimation des populations de segment

[!UICONTROL Segment Builder] prend en charge les estimations de taille de segment pour les règles de segmentation qui contiennent jusqu'à 4 expressions de récence et de fréquence. Si vous choisissez plus de 4 expressions de récence et de fréquence lors de la création d'une règle de segment, l'estimateur de segment affiche une erreur lors de l'estimation de la population.

### Limites dues à la fusion des règles lors de l'estimation des populations de segments

Actuellement, il existe une limite connue car notre estimateur de taille de segment ne tient pas compte des règles de fusion de profils. For example, look at segments with the **No Authenticated Profile + Current Device Profile** [merge rule](../../features/profile-merge-rules/merge-rule-definitions.md). Du fait de la façon dont nous calculons actuellement les chiffres d'estimation des segments, les populations estimées incluent les profils authentifiés. Toutefois, les populations de segments existantes ignorent correctement les profils authentifiés.

>[!MORE_ LIKE_ THIS]
>
>* [FAQ sur la fusion des profils et le graphique des périphériques](../../faq/faq-profile-merge.md)
>* [Profile Link](../../features/profile-merge-rules/merge-rules-overview.md)

