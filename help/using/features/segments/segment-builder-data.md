---
description: Ajoutez et supprimez des caractéristiques dans le créateur de segments afin d’afficher les populations réelles de caractéristiques ainsi que les données réelles et estimées sur la population de segments. Les données estimées sur la taille de la population vous aident à créer le segment approprié pour votre campagne.
seo-description: Ajoutez et supprimez des caractéristiques dans le créateur de segments afin d’afficher les populations réelles de caractéristiques ainsi que les données réelles et estimées sur la population de segments. Les données estimées sur la taille de la population vous aident à créer le segment approprié pour votre campagne.
seo-title: Données sur la population de segment et les caractéristiques dans le créateur de segments
solution: Audience Manager
title: Données sur la population de segment et les caractéristiques dans le créateur de segments
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
feature: 'Segments '
exl-id: f8953d10-8a31-4c07-8d96-169c30a21de0
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1251'
ht-degree: 2%

---

# [!UICONTROL Trait] et Données  [!UICONTROL Segment] de population dans  [!UICONTROL Segment Builder] {#trait-and-segment-population-data-in-segment-builder}

Ajoutez et supprimez [!UICONTROL traits] dans [!UICONTROL Segment Builder] pour afficher les populations [!UICONTROL trait] réelles ainsi que les données sur la population de segments réelles et estimées. Les données estimées sur la taille de la population vous aident à créer le segment approprié pour votre campagne.

## [!UICONTROL Trait] Données de population  {#trait-population-data}

[!UICONTROL Segment Builder] vous présente  [!UICONTROL Total Trait Population] le dernier jour où vous ajoutez une  [!UICONTROL trait] à un segment. Ces données apparaissent dans le champ bleu autour de la [!UICONTROL trait] sélectionnée dans la section [!UICONTROL Basic View].

![](assets/trait-size.png)

Le tableau suivant définit les mesures de population de caractéristiques :


| Mesure | Description |
|---------|----------|
| [!UICONTROL Total Trait Population] | Le nombre d’identifiants uniques dont le profil contient la caractéristique sélectionnée. |


## Calcul des populations de segments réel et estimé {#calculating-real-estimated-populations}

Lorsque vous créez un segment ou modifiez un segment existant, l’Audience Manager prend jusqu’à 24 heures pour afficher les résultats pour les populations réelles de segments en temps réel et totales.

Cependant, l’Audience Manager peut immédiatement estimer la taille de population totale et en temps réel de votre segment. Ces estimations sont basées sur des données historiques échantillonnées et renvoient les résultats à un intervalle de confiance de 95 %.

![](assets/confidence-interval.png)

Dans [!UICONTROL Segment Builder], une barre bleue sur les graphiques de population estimés indique les plages supérieures et inférieures possibles pour la taille du segment. Bien que les performances antérieures ne garantissent pas les résultats futurs, les données estimées peuvent vous aider à comprendre la taille potentielle d’un segment nouveau ou modifié.

## Présentation des données sur la population de segments {#segment-populations}

[!UICONTROL Segment Builder] vous montre les données de population de segments au fur et à mesure que vous créez et modifiez des segments.

* Pour les données de population estimée de segments (temps réel et total), [!UICONTROL Segment Builder] ne met pas automatiquement à jour les graphiques lorsque vous ajoutez ou supprimez des caractéristiques dans un segment. Cliquez sur **[!UICONTROL Calculate Estimates]** pour afficher (ou actualiser) les nombres estimés de population.

* Pour les données réelles (réelles) sur la population de segments (temps réel et total), [!UICONTROL Segment Builder] met automatiquement à jour le graphique de segments lorsque vous chargez un segment existant. Pour les nouveaux segments, ou lorsque vous ajoutez de nouvelles caractéristiques à un segment existant, les données réelles sur la population ne sont mises à jour que 24 heures après la création du segment.

![](assets/segment-data.png)

Pour plus d’informations sur les données estimées et réelles de la population de segments, reportez-vous aux définitions ci-dessous.

## Données de population de segment estimées définies {#estimated-segment-population}

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
   <td colname="col1"> <p> <span class="wintitle"> Population estimée en temps réel (potentielle)  </span> </p> </td> 
   <td colname="col2"> <p>Nombre estimé de visiteurs uniques affichés en temps réel pendant la période spécifiée et qui étaient qualifiés pour le segment au moment où ils ont été vus par l’Audience Manager. </p> <p>Dans <span class="wintitle"> Créateur de segments</span>, les populations des 30 derniers jours pour les caractéristiques (<span class="wintitle"> Population totale de caractéristiques</span>) peuvent être différentes pour les caractéristiques et les segments évalués en temps réel. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">Pour les caractéristiques, la mesure des 30 derniers jours comptabilise le nombre d’utilisateurs uniques qualifiés pour cette caractéristique au cours des 30 derniers jours. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">Pour les segments évalués en temps réel, la mesure des 30 derniers jours comptabilise le nombre d’utilisateurs qualifiés pour une caractéristique (dans ce segment) à un moment donné dans le passé et qui ont été de nouveau affichés par l’Audience Manager au cours des 30 derniers jours. Supposons, par exemple, que vous ayez un utilisateur qui s’est qualifié pour une caractéristique il y a 60 jours et qui a été consulté à nouveau il y a 10 jours. Dans les données, cet utilisateur ne sera pas ajouté au nombre de caractéristiques, car il s’est qualifié pour la première fois pour la caractéristique il y a plus de 30 jours. Cependant, elles seront incluses dans le décompte des 30 derniers jours pour les segments évalués en temps réel. Cela est dû au fait qu’ils se sont qualifiés pour le segment dans l’intervalle de 30 jours. </li>
     </ul> </p> <p> <p>Remarque : La mesure <span class="wintitle"> Population estimée en temps réel</span> n’inclut pas les appareils qualifiés pour un segment en fonction des connexions fournies par une <span class="wintitle"> règle de fusion de profils</span> qui utilise une option de graphique d’appareil <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"></a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Population totale estimée (potentielle)</span> </p> </td> 
   <td colname="col2"> <p>Nombre estimé de visiteurs uniques pouvant se trouver dans votre segment nouveau ou modifié. Comme pour la plupart des estimations, les performances antérieures ne garantissent pas les résultats futurs, mais vous pouvez utiliser le total estimé pour : </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">déterminer le nombre de personnes qu’un segment nouveau ou révisé peut atteindre lors de la création d’un segment ; </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">Réglez le segment en fonction de vos objectifs. Par exemple, les segments volumineux sont utiles pour les campagnes de sensibilisation à la marque et les segments plus petits sont utiles pour le ciblage ou le reciblage ciblé. </li> 
     </ul> </p> <p> <p>Remarque : La mesure <span class="wintitle"> Population totale estimée</span> n’inclut pas les appareils qualifiés pour un segment en fonction des connexions fournies par une <span class="wintitle"> règle de fusion de profils</span> qui utilise une option de graphique d’appareil <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"></a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Données de population de segment existantes (réelles) définies {#existing-segment-population}

[!UICONTROL Profile Merge Rules] affectent les chiffres réels en temps réel et la population totale. Ces totaux varient selon que le [!UICONTROL Profile Merge Rule] segment appartient ou non à l’utilisation d’une représentation graphique des appareils. Voir aussi [Options de stratégie de fusion de profils définies](../../features/profile-merge-rules/merge-rule-definitions.md).

### Données de population de segment pour [!UICONTROL Merge Rules] sans [!UICONTROL Device Graph Option]

Le tableau suivant définit les mesures en temps réel et de population totale lorsque vos segments sont utilisés par une balise [!UICONTROL Profile Merge Rule] créée sans option [!UICONTROL device graph]. Il s’agit des paramètres des options de l’appareil **[!UICONTROL No Device Options]** et **[!UICONTROL Current Device Proflie]**.

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
   <td colname="col2"> <p>Nombre réel de visiteurs uniques affichés en temps réel pendant la période spécifiée et qui étaient qualifiés pour le segment au moment où ils ont été vus par l’Audience Manager. </p> <p>Dans <span class="wintitle"> Créateur de segments</span>, les populations des 30 derniers jours pour les caractéristiques (<span class="wintitle"> Population totale de caractéristiques</span>) peuvent être différentes pour les caractéristiques et les segments évalués en temps réel. </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">Pour les caractéristiques, la mesure des 30 derniers jours comptabilise le nombre d’utilisateurs uniques qualifiés pour cette caractéristique au cours des 30 derniers jours. </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">Pour les segments évalués en temps réel, la mesure des 30 derniers jours comptabilise le nombre d’utilisateurs qualifiés pour une caractéristique (dans ce segment) à un moment donné dans le passé et qui ont été de nouveau affichés par l’Audience Manager au cours des 30 derniers jours. Supposons, par exemple, que vous ayez un utilisateur qui s’est qualifié pour une caractéristique il y a 60 jours et qui a été consulté à nouveau il y a 10 jours. Dans les données, cet utilisateur ne sera pas ajouté au nombre de caractéristiques, car il s’est qualifié pour la première fois pour la caractéristique il y a plus de 30 jours. Cependant, elles seront incluses dans le décompte des 30 derniers jours pour les segments évalués en temps réel. Cela est dû au fait qu’ils se sont qualifiés pour le segment dans l’intervalle de 30 jours. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Population totale (existante)</span> </p> </td> 
   <td colname="col2"> <p>Le nombre réel de visiteurs uniques qui ont été qualifiés pour le segment depuis hier. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Données de population de segment pour [!UICONTROL Merge Rules] avec une option [!UICONTROL Device Graph]

Le tableau suivant définit les mesures en temps réel et de population totale lorsque vos segments sont utilisés par une [!UICONTROL Profile Merge Rule] créée avec une option [!DNL device graph]. Il s’agit des paramètres des options de l’appareil pour [!UICONTROL Profile Link Device Graph], [!DNL Adobe] [!DNL device graph] et d’autres options [!DNL device graph] tierces disponibles.


| Colonne A | Colonne B |
|---------|----------|
| [!UICONTROL Real-Time Population (Existing) ] | Nombre réel d’appareils vus en temps réel avec des profils actuels qui, lorsqu’ils sont fusionnés avec jusqu’à 100 autres profils d’appareils connectés par le graphique d’appareil, contiennent les caractéristiques à remplir pour le segment au moment où il a été vu par l’Audience Manager. |
| [!UICONTROL Total Population (Existing)] | Nombre total d’appareils avec des profils qui, lorsqu’ils étaient fusionnés avec jusqu’à 100 autres profils d’appareils connectés par la représentation graphique des appareils, étaient tous qualifiés pour le segment. |

### Limites dues à la récence et aux expressions de fréquence lors de l’estimation de la population de segments

[!UICONTROL Segment Builder] prend en charge les estimations de taille de segment pour les règles de segment qui contiennent jusqu’à 4 expressions de récence et de fréquence. Si vous choisissez plus de 4 expressions de récence et de fréquence lors de la création d’une règle de segment, l’estimateur de segment affiche une erreur lors de l’estimation de la population.

### Limites dues à [!UICONTROL Merge Rules] lors de l’estimation des populations de segments

Actuellement, il existe une limitation connue car notre estimateur de taille de segment ne prend pas en compte [!UICONTROL profile merge rules]. Par exemple, observez les segments avec la **[!UICONTROL No Authenticated Profile + Current Device Profile]** [règle de fusion](../../features/profile-merge-rules/merge-rule-definitions.md). En raison de la manière dont nous calculons actuellement les chiffres d’estimation des segments, les populations estimées incluront les profils authentifiés. Toutefois, les populations de segments existantes ignoreront correctement les profils authentifiés.

>[!MORELIKETHIS]
>
>* [FAQ sur les stratégies de fusion de profils et la représentation graphique des appareils](../../faq/faq-profile-merge.md)
* [Profile Link](../profile-merge-rules/merge-rules-overview.md)

