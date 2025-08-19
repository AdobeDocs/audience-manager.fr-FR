---
description: Ajoutez et supprimez des caractéristiques dans le créateur de segments pour afficher les populations de caractéristiques réelles ainsi que les données de population de segments réelles et estimées. Les données relatives à la taille de la population estimée vous permettent de créer le segment approprié pour votre campagne.
seo-description: Add and remove traits in Segment Builder to see actual trait populations along with actual and estimated segment population data. The estimated population size data helps you build the right segment for your campaign.
seo-title: Trait and Segment Population Data in Segment Builder
solution: Audience Manager
title: Données de population de caractéristiques et de segments dans le créateur de segments
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
feature: Segments
exl-id: f8953d10-8a31-4c07-8d96-169c30a21de0
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1213'
ht-degree: 1%

---

# [!UICONTROL Trait] et [!UICONTROL Segment] des données sur la population en [!UICONTROL Segment Builder] {#trait-and-segment-population-data-in-segment-builder}

Ajoutez et supprimez des [!UICONTROL traits] dans [!UICONTROL Segment Builder] pour afficher les populations de [!UICONTROL trait] réelles ainsi que les données de population de segments réelles et estimées. Les données relatives à la taille de la population estimée vous permettent de créer le segment approprié pour votre campagne.

## Données sur la population [!UICONTROL Trait] {#trait-population-data}

[!UICONTROL Segment Builder] vous indique le [!UICONTROL Total Trait Population] du dernier jour lorsque vous ajoutez un [!UICONTROL trait] à un segment. Ces données apparaissent dans le champ bleu autour du [!UICONTROL trait] sélectionné dans la section [!UICONTROL Basic View].

![](assets/trait-size.png)

Le tableau suivant définit les mesures de population de caractéristiques :


| Mesure | Description |
|---------|----------|
| [!UICONTROL Total Trait Population] | Le nombre d’identifiants uniques qui ont la caractéristique sélectionnée dans leur profil. |


## Calcul des populations de segments réelles et estimées {#calculating-real-estimated-populations}

Lorsque vous créez un segment ou modifiez un segment existant, Audience Manager met jusqu’à 24 heures pour afficher les résultats en temps réel pour les populations de segments réelles et totales.

Cependant, Audience Manager peut estimer immédiatement la taille de la population totale et en temps réel de votre segment. Ces estimations sont basées sur des données historiques échantillonnées et renvoient des résultats à l’intervalle de confiance de 95 %.

![](assets/confidence-interval.png)

En [!UICONTROL Segment Builder], une barre bleue sur les graphiques de population estimée indique les plages supérieure et inférieure possibles pour la taille du segment. Bien que les performances passées ne garantissent pas les résultats futurs, les données estimées peuvent vous aider à comprendre la taille potentielle d’un segment nouveau ou modifié.

## Présentation Des Données De Population De Segments {#segment-populations}

[!UICONTROL Segment Builder] vous montre les données de population de segments lorsque vous créez et modifiez des segments.

* Pour les données estimées de la population de segments (temps réel et total), [!UICONTROL Segment Builder] ne met pas automatiquement à jour les graphiques à mesure que vous ajoutez ou supprimez des caractéristiques dans un segment. Cliquez sur **[!UICONTROL Calculate Estimates]** pour afficher (ou actualiser) les estimations de population.

* Pour les données réelles (réelles) de la population de segments (temps réel et total), [!UICONTROL Segment Builder] met automatiquement à jour le graphique de segments lorsque vous chargez un segment existant. Pour les nouveaux segments ou lorsque vous ajoutez de nouvelles caractéristiques à un segment existant, les données de population réelles ne sont pas mises à jour tant que 24 heures ne se sont pas écoulées depuis la création du segment.

![](assets/segment-data.png)

Pour plus d’informations sur les données de population de segments estimées et réelles, consultez les définitions ci-dessous.

## Données De Population De Segments Estimées Définies {#estimated-segment-population}

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
   <td colname="col1"> <p> <span class="wintitle"> Estimation De La Population En Temps Réel (Potentiel) </span> </p> </td> 
   <td colname="col2"> <p>Estimation du nombre de visiteurs et visiteuses uniques vus en temps réel pour la période spécifiée et qui étaient qualifiés pour le segment au moment où ils ont été vus par Audience Manager. </p> <p>Dans <span class="wintitle"> créateur de segments</span> les dernières populations de 30 jours pour les caractéristiques (<span class="wintitle"> populations totales de caractéristiques</span>) peuvent être différentes pour les caractéristiques et les segments évalués en temps réel. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">Pour les caractéristiques, la mesure des 30 derniers jours comptabilise le nombre d’utilisateurs uniques qui se sont qualifiés pour cette caractéristique au cours des 30 derniers jours. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">Pour les segments évalués en temps réel, la mesure des 30 derniers jours comptabilise le nombre d’utilisateurs qui se sont qualifiés pour une caractéristique (dans ce segment) à un moment donné dans le passé et qui ont été vus de nouveau par Audience Manager au cours des 30 derniers jours. Supposons, par exemple, que vous ayez un utilisateur qualifié pour une caractéristique il y a 60 jours et qu’il ait été revu il y a 10 jours. Dans les données, cet utilisateur ne sera pas ajouté au nombre de caractéristiques, car il s’est qualifié pour la première fois pour la caractéristique il y a plus de 30 jours. Toutefois, ils seront inclus dans le dernier comptage sur 30 jours pour les segments évalués en temps réel. Cela est dû au fait qu’ils se sont qualifiés pour le segment au cours de l’intervalle de 30 jours. </li>
     </ul> </p> <p> <p>Remarque : la mesure Population en temps réel estimée <span class="wintitle"> n’inclut pas </span> appareils qualifiés pour un segment en fonction des connexions fournies par une règle de fusion de profil <span class="wintitle"></span> qui utilise une option de graphique d’appareil <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"></a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Estimation De La Population Totale (Potentielle)</span> </p> </td> 
   <td colname="col2"> <p>Estimation du nombre de visiteurs et visiteuses uniques susceptibles de se trouver dans votre segment nouveau ou modifié. Comme pour presque toutes les estimations, les performances passées ne garantissent pas les résultats futurs, mais vous pouvez utiliser le total estimé pour : </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">Découvrez le nombre de personnes qu’un segment nouveau ou révisé peut atteindre à mesure que vous créez un segment. </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">Réglez le segment en fonction de vos objectifs. Par exemple, les segments volumineux sont utiles pour les campagnes de sensibilisation à la marque et les segments plus petits sont utiles pour les campagnes de ciblage ciblé ou de reciblage. </li> 
     </ul> </p> <p> <p>Remarque : la mesure Population totale estimée <span class="wintitle"> n</span>inclut pas les appareils qualifiés pour un segment en fonction des connexions fournies par une règle de fusion de profil <span class="wintitle"></span> qui utilise une option de graphique d’appareil <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"></a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Données De Population De Segments Existantes (Réelles) Définies {#existing-segment-population}

[!UICONTROL Profile Merge Rules] affectent les nombres réels de population en temps réel et totaux. Ces totaux varient selon que le [!UICONTROL Profile Merge Rule] auquel appartient un segment utilise ou non une option de graphique d’appareil. Voir aussi [Définition des options de règle de fusion de profil](../../features/profile-merge-rules/merge-rule-definitions.md).

### Données de population de segments pour les [!UICONTROL Merge Rules] sans [!UICONTROL Device Graph Option]

Le tableau suivant définit les mesures de population totale et en temps réel lorsque vos segments sont utilisés par une [!UICONTROL Profile Merge Rule] créée sans option de [!UICONTROL device graph]. Il s’agit des paramètres des options de l’appareil **[!UICONTROL No Device Options]** et **[!UICONTROL Current Device Proflie]**.

<table id="table_A18C973855DB46A0B39B81F32E0E7540"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> De La Population En Temps Réel (Existante)</span> </p> </td> 
   <td colname="col2"> <p>Nombre réel de visiteurs et visiteuses uniques vus en temps réel pour la période spécifiée et qui étaient qualifiés pour le segment au moment où ils ont été vus par Audience Manager. </p> <p>Dans <span class="wintitle"> créateur de segments</span> les dernières populations de 30 jours pour les caractéristiques (<span class="wintitle"> populations totales de caractéristiques</span>) peuvent être différentes pour les caractéristiques et les segments évalués en temps réel. </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">Pour les caractéristiques, la mesure des 30 derniers jours comptabilise le nombre d’utilisateurs uniques qui se sont qualifiés pour cette caractéristique au cours des 30 derniers jours. </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">Pour les segments évalués en temps réel, la mesure des 30 derniers jours comptabilise le nombre d’utilisateurs qui se sont qualifiés pour une caractéristique (dans ce segment) à un moment donné dans le passé et qui ont été vus de nouveau par Audience Manager au cours des 30 derniers jours. Supposons, par exemple, que vous ayez un utilisateur qualifié pour une caractéristique il y a 60 jours et qu’il ait été revu il y a 10 jours. Dans les données, cet utilisateur ne sera pas ajouté au nombre de caractéristiques, car il s’est qualifié pour la première fois pour la caractéristique il y a plus de 30 jours. Toutefois, ils seront inclus dans le dernier comptage sur 30 jours pour les segments évalués en temps réel. Cela est dû au fait qu’ils se sont qualifiés pour le segment au cours de l’intervalle de 30 jours. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Population Totale (Existante)</span> </p> </td> 
   <td colname="col2"> <p>Nombre réel de visiteurs et visiteuses uniques qualifiés pour le segment à compter d’hier. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Segmenter les données de population pour les [!UICONTROL Merge Rules] avec une option de [!UICONTROL Device Graph]

Le tableau suivant définit les mesures de la population totale et en temps réel lorsque vos segments sont utilisés par une [!UICONTROL Profile Merge Rule] créée avec une option de [!DNL device graph]. Il s’agit des paramètres des options de l’appareil pour le [!UICONTROL Profile Link Device Graph], le [!DNL Adobe] de [!DNL device graph] et d’autres choix de [!DNL device graph] tiers qui sont disponibles pour vous.


| Colonne A | Colonne B |
|---------|----------|
| [!UICONTROL Real-Time Population (Existing)] | Nombre réel d’appareils vus en temps réel avec les profils actuels qui, lorsqu’ils sont fusionnés avec jusqu’à 100 autres profils d’appareils connectés par le graphique d’appareil, contiennent les caractéristiques pour le segment au moment où il a été vu par Audience Manager. |
| [!UICONTROL Total Population (Existing)] | Nombre total d’appareils avec des profils qui, lorsqu’ils ont été fusionnés avec jusqu’à 100 autres profils d’appareils connectés par le graphique d’appareil, étaient tous qualifiés pour le segment. |

### Limitations dues aux expressions de récence et de fréquence lors de l’estimation des populations de segments

[!UICONTROL Segment Builder] prend en charge les estimations de taille de segment pour les règles de segment qui contiennent jusqu’à 4 expressions de récence et de fréquence. Le fait de choisir plus de 4 expressions de récence et de fréquence lors de la création d’une règle de segment entraîne l’affichage d’une erreur par l’estimateur de segment lors de l’estimation de la population.

### Limitations dues à l’[!UICONTROL Merge Rules] lors de l’estimation des populations de segments

Actuellement, il existe une limitation connue, car notre estimateur de taille de segment ne prend pas en compte les [!UICONTROL profile merge rules]. Prenons l’exemple des segments avec la **[!UICONTROL No Authenticated Profile + Current Device Profile]** [règle de fusion](../../features/profile-merge-rules/merge-rule-definitions.md). En raison de la manière dont nous calculons actuellement les nombres d’estimation de segment, les populations estimées incluront les profils authentifiés. Toutefois, les populations de segments existantes ignoreront correctement les profils authentifiés.

>[!MORELIKETHIS]
>
>* [FAQ sur les stratégies de fusion de profils et la représentation graphique des appareils](../../faq/faq-profile-merge.md)
>* [Profile Link](../profile-merge-rules/merge-rules-overview.md)
