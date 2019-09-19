---
description: Ajoutez et supprimez des caractéristiques dans le créateur de segments afin d’afficher les populations de caractéristiques réelles ainsi que les données de population de segments réelles et estimées. Les données de taille de population estimée vous aident à créer le segment approprié pour votre campagne.
seo-description: Ajoutez et supprimez des caractéristiques dans le créateur de segments afin d’afficher les populations de caractéristiques réelles ainsi que les données de population de segments réelles et estimées. Les données de taille de population estimée vous aident à créer le segment approprié pour votre campagne.
seo-title: Données de population de caractéristiques et de segments dans le créateur de segments
solution: Audience Manager
title: Données de population de caractéristiques et de segments dans le créateur de segments
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Trait and Segment Population Data in Segment Builder {#trait-and-segment-population-data-in-segment-builder}

Ajoutez et supprimez des caractéristiques dans [!UICONTROL Segment Builder] pour afficher les populations de caractéristiques réelles ainsi que les données de population de segments réelles et estimées. Les données de taille de population estimée vous aident à créer le segment approprié pour votre campagne.

## Données de population de caractéristiques {#trait-population-data}

[!UICONTROL Segment Builder] vous montre le dernier jour [!UICONTROL Total Trait Population] où vous ajoutez une caractéristique à un segment. Ces données s’affichent dans le champ bleu entourant la caractéristique sélectionnée dans la [!UICONTROL Basic View] section.

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
   <td colname="col1"> <p> <span class="wintitle"> Population totale des caractéristiques</span> </p> </td>
   <td colname="col2"> <p>Nombre d’identifiants uniques dont le profil contient la caractéristique sélectionnée. </p> </td>
  </tr> 
 </tbody> 
</table>

## Calcul des populations de segments réelles et estimées {#calculating-real-estimated-populations}

Lorsque vous créez un segment ou modifiez un segment existant, Audience Manager prend jusqu’à 24 heures pour afficher les résultats pour les populations de segments réelles en temps réel et totales.

Toutefois, Audience Manager peut immédiatement estimer la taille de population totale et en temps réel de votre segment. Ces estimations sont basées sur des données historiques échantillonnées et renvoient les résultats à l’intervalle de confiance de 95 %.

![](assets/confidence-interval.png)

En [!UICONTROL Segment Builder]revanche, une barre bleue sur les graphiques de population estimés indique les plages supérieure et inférieure possibles pour la taille du segment. Bien que les performances passées ne garantissent pas les résultats futurs, les données estimées peuvent vous aider à comprendre la taille potentielle d’un segment nouveau ou modifié.

## Présentation des données de population de segments {#segment-populations}

[!UICONTROL Segment Builder] La illustre les données de population de segments au fur et à mesure que vous créez et modifiez des segments.

* Pour les données de population de segments estimées (en temps réel et total), [!UICONTROL Segment Builder] ne met pas automatiquement à jour les graphiques lorsque vous ajoutez ou supprimez des caractéristiques dans un segment. Cliquez sur **[!UICONTROL Calculate Estimates]** pour afficher (ou actualiser) l’estimation des chiffres de population.

* Pour les données de population de segments réelles (réelles) (en temps réel et total), [!UICONTROL Segment Builder] met à jour le graphique de segments automatiquement lorsque vous chargez un segment existant. Pour les nouveaux segments ou lorsque vous ajoutez de nouvelles caractéristiques à un segment existant, les données de population réelles ne sont mises à jour que 24 heures après la création du segment.

![](assets/segment-data.png)

Voir les définitions ci-dessous pour plus d’informations sur les données de population de segments estimées et réelles.

## Estimation des données de population de segments définies {#estimated-segment-population}

Le tableau suivant définit les mesures de population estimées.

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Estimation de la population en temps réel (potentielle) </span> </p> </td> 
   <td colname="col2"> <p>Nombre estimé de visiteurs uniques vus en temps réel pendant la période spécifiée et qualifiés pour le segment au moment où ils ont été vus par Audience Manager. </p> <p>Dans <span class="wintitle"> le créateur</span>de segments, les 30 derniers jours de populations pour les caractéristiques (<span class="wintitle"> Total des populations</span>de caractéristiques) peuvent être différents pour les caractéristiques et les segments évalués en temps réel. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">Pour les caractéristiques, la dernière mesure de 30 jours compte le nombre d’utilisateurs uniques qui se sont qualifiés pour cette caractéristique au cours des 30 derniers jours. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">Pour les segments évalués en temps réel, la mesure des 30 derniers jours comptabilise le nombre d’utilisateurs qui se sont qualifiés pour une caractéristique (dans ce segment) à un moment donné dans le passé et qui ont été de nouveau vus par Audience Manager au cours des 30 derniers jours. Par exemple, supposons qu’un utilisateur se soit qualifié pour une caractéristique il y a 60 jours et qu’il ait été de nouveau vu il y a 10 jours. Dans les données, cet utilisateur ne sera pas ajouté au nombre de caractéristiques car il s’est qualifié pour la caractéristique il y a plus de 30 jours. Toutefois, ils seront inclus dans le décompte des 30 derniers jours pour les segments évalués en temps réel. En effet, ils se sont qualifiés pour le segment dans l’intervalle de 30 jours. </li>
     </ul> </p> <p> <p>Remarque : La mesure <span class="wintitle"> Estimation de la population</span> en temps réel n’inclut pas les périphériques qui se sont qualifiés pour un segment en fonction des connexions fournies par une règle <span class="wintitle"> de fusion de</span> profil qui utilise une option <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> de graphique de</a>périphérique. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Estimation de la population totale (potentielle)</span> </p> </td> 
   <td colname="col2"> <p>Nombre estimé de visiteurs uniques susceptibles d’appartenir à votre segment nouveau ou modifié. Comme pour presque toute estimation, les performances passées ne garantissent pas les résultats futurs, mais vous pouvez utiliser le total estimé pour : </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">Déterminer le nombre de personnes qu’un segment nouveau ou révisé peut atteindre lorsque vous créez un segment. </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">Ajustez le segment en fonction de vos objectifs. Par exemple, les segments volumineux sont utiles pour les campagnes de sensibilisation à la marque et les segments plus petits sont utiles pour le ciblage ciblé ou le reciblage des campagnes. </li> 
     </ul> </p> <p> <p>Remarque : La mesure Population <span class="wintitle"> totale</span> estimée n’inclut pas les périphériques qui se sont qualifiés pour un segment en fonction des connexions fournies par une règle <span class="wintitle"> de fusion de</span> profil qui utilise une option <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> de graphique de</a>périphérique. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Définition des données de population de segments existantes (réelles) {#existing-segment-population}

[!UICONTROL Profile Merge Rules] influent sur le nombre réel en temps réel et total de la population. Ces totaux varient selon que le segment appartient ou non à [!UICONTROL Profile Merge Rule] une option de graphique de périphérique. Voir aussi Définition [des options des règles de fusion](../../features/profile-merge-rules/merge-rule-definitions.md)de profil.

### Segmenter les données de population pour les règles de fusion sans option graphique de périphérique

Le tableau suivant définit les mesures réelles de temps réel et de population totale lorsque vos segments sont utilisés par une [!UICONTROL Profile Merge Rule] création sans option de graphique de périphérique. Il s’agit des paramètres des options de l’appareil **[!UICONTROL No Device Options]** et **[!UICONTROL Current Device Proflie]**.

<table id="table_A18C973855DB46A0B39B81F32E0E7540"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Population en temps réel (existante)</span> </p> </td> 
   <td colname="col2"> <p>Nombre réel de visiteurs uniques affichés en temps réel pendant la période spécifiée et qui étaient qualifiés pour le segment au moment où ils étaient vus par Audience Manager. </p> <p>Dans <span class="wintitle"> le créateur</span>de segments, les 30 derniers jours de populations pour les caractéristiques (<span class="wintitle"> Total des populations</span>de caractéristiques) peuvent être différents pour les caractéristiques et les segments évalués en temps réel. </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">Pour les caractéristiques, la dernière mesure de 30 jours compte le nombre d’utilisateurs uniques qui se sont qualifiés pour cette caractéristique au cours des 30 derniers jours. </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">Pour les segments évalués en temps réel, la mesure des 30 derniers jours comptabilise le nombre d’utilisateurs qui se sont qualifiés pour une caractéristique (dans ce segment) à un moment donné dans le passé et qui ont été de nouveau vus par Audience Manager au cours des 30 derniers jours. Par exemple, supposons qu’un utilisateur se soit qualifié pour une caractéristique il y a 60 jours et qu’il ait été de nouveau vu il y a 10 jours. Dans les données, cet utilisateur ne sera pas ajouté au nombre de caractéristiques car il s’est qualifié pour la caractéristique il y a plus de 30 jours. Toutefois, ils seront inclus dans le décompte des 30 derniers jours pour les segments évalués en temps réel. En effet, ils se sont qualifiés pour le segment dans l’intervalle de 30 jours. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Population totale (existante)</span> </p> </td> 
   <td colname="col2"> <p>Nombre réel de visiteurs uniques qualifiés pour le segment à partir d’hier. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Segmenter les données de population pour les règles de fusion avec une option graphique de périphérique

Le tableau suivant définit les mesures réelles de temps réel et de population totale lorsque vos segments sont utilisés par une option de graphique de périphérique [!UICONTROL Profile Merge Rule] créée avec une option de graphique de périphérique. Il s’agit des paramètres d’options du périphérique pour le graphique [!UICONTROL Profile Link Device Graph], le graphique [!DNL Adobe] du périphérique et d’autres options de graphiques de périphérique tiers disponibles.

<table id="table_157EC6E5B5C44EB899854CA10B090F60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Population en temps réel (existante)</span> </p> </td> 
   <td colname="col2"> <p>Nombre réel de périphériques affichés en temps réel avec les profils actuels qui, lorsqu’ils sont fusionnés avec jusqu’à 3 autres profils de périphériques connectés par le graphique de périphériques, contiennent les caractéristiques permettant de qualifier le segment au moment où il a été vu par <span class="keyword"> Audience Manager</span>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Population totale (existante)</span> </p> </td> 
   <td colname="col2"> <p>Nombre total de périphériques avec des profils qui, lorsqu’ils étaient fusionnés avec 3 autres profils de périphériques connectés par le graphique de périphériques, étaient tous qualifiés pour le segment. </p> </td>
  </tr>
 </tbody>
</table>

### Restrictions liées aux expressions de récence et de fréquence lors de l’estimation des populations de segments

[!UICONTROL Segment Builder] prend en charge les estimations de la taille des segments pour les règles de segment qui contiennent jusqu’à 4 expressions de récence et de fréquence. Si vous choisissez plus de 4 expressions de récence et de fréquence lors de la création d’une règle de segmentation, l’estimateur de segments affiche une erreur lors de l’estimation de la population.

### Limites dues aux règles de fusion lors de l’estimation des populations de segments

Actuellement, il existe une limitation connue car notre estimateur de taille de segment ne tient pas compte des règles de fusion de profil. Par exemple, examinez les segments avec la règle **** Pas de profil authentifié + Profil[de périphérique actuel](../../features/profile-merge-rules/merge-rule-definitions.md)fusionnant. En raison de la façon dont nous calculons actuellement les chiffres d’estimation des segments, les populations estimées incluront des profils authentifiés. Toutefois, les populations de segments existantes ignoreront correctement les profils authentifiés.

>[!MORE_LIKE_This]
>
>* [FAQ sur les règles de fusion de profils et le graphique de périphériques](../../faq/faq-profile-merge.md)
>* [Profile Link](../../features/profile-merge-rules/merge-rules-overview.md)

