---
description: Les mesures de lien de profil fournissent des données sur les personnes et les périphériques qui s’authentifient sur votre site. Les données et les graphiques du lien de profil se mettent à jour dynamiquement lorsque vous créez des règles de fusion ou lorsque vous cliquez sur une règle existante dans le tableau de bord Règles de fusion de profils . Ces mesures peuvent inclure une représentation graphique des appareils de Adobe Experience Cloud Device Co-op ou d’autres sources de représentation graphique des appareils tiers.
seo-description: Les mesures de lien de profil fournissent des données sur les personnes et les périphériques qui s’authentifient sur votre site. Les données et les graphiques du lien de profil se mettent à jour dynamiquement lorsque vous créez des règles de fusion ou lorsque vous cliquez sur une règle existante dans le tableau de bord Règles de fusion de profils . Ces mesures peuvent inclure une représentation graphique des appareils de Adobe Experience Cloud Device Co-op ou d’autres sources de représentation graphique des appareils tiers.
seo-title: Mesures des rapports des stratégies de fusion de profils
solution: Audience Manager
title: Mesures des rapports des stratégies de fusion de profils
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
feature: Fusion des profils
exl-id: 2af59c60-2448-44af-90d2-eccc52f7ff02
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 2%

---

# Mesures des rapports des stratégies de fusion de profils {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Merge Rule] les mesures fournissent des données sur les personnes et les appareils qui s’authentifient sur votre site. Les données et graphiques de [!UICONTROL Profile Merge Rule Reports] se mettent à jour dynamiquement lorsque vous créez une règle de fusion ou lorsque vous cliquez sur une règle existante dans le tableau de bord [!UICONTROL Profile Merge Rules]. Ces mesures peuvent inclure des graphiques d’appareil provenant de [!DNL Adobe Experience Cloud Device Co-op] ou d’autres sources de graphiques d’appareil tiers.

## Fusionner les mesures de règle {#merge-rule-metrics}

Les rapports renvoient des données dans des graphiques à barres côte à côte lorsque vos règles de fusion utilisent des données provenant de [Adobe Experience Cloud Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/about/overview.html) ou d’autres graphiques d’appareils tiers auxquels vous avez accès dans [!DNL Audience Manager]. Cela vous permet de comparer vos données propriétaires authentifiées avec les données multi-appareils fournies par la [!UICONTROL Experience Cloud Device Co-op] ou une autre représentation graphique tierce des appareils. Pour plus d’informations sur les données renvoyées par [!UICONTROL Device Co-op], voir [Device Graph : Processus internes et sortie](https://experienceleague.adobe.com/docs/device-co-op/using/device-graph/device-graph-overview.html). Ces données sont mises à jour quotidiennement.

<table id="table_A7FB2F9804F84AC8A6DD05C0E6EE7555"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Activité authentifiée</span></b> </p> </td> 
   <td colname="col2"> <p>Affiche : </p> 
    <ul id="ul_7F7373919A4A49028EF4BF7B28D9F8E9"> 
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> Principales personnes</span> : Nombre de personnes qui se sont authentifiées sur votre site au cours des 60 derniers jours. </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> Périphérique</span> croisé : Nombre total d’ <a href="merge-rules-start.md#create-data-source"> identifiants </a> inter-appareils stockés dans la source de  <a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html"> données </a> du  <a href="merge-rule-definitions.md"> profil </a> authentifié sélectionné pour la durée de vie de la source de données. </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> % de Principaux</span> : Affiche les personnes  <span class="wintitle"> Principales </span> en %. </li> 
    </ul> <p> <span class="wintitle"> L’</span> activité authentifiée permet de comparer les sources de données par activité, volume et pourcentage. Il peut vous aider à trouver une source de données qui compte un grand nombre de personnes et un pourcentage élevé d’utilisateurs principaux. Vous pouvez également comparer des sources de données présentant une forte proportion d’utilisateurs principaux par rapport à la taille totale de l’audience. Par exemple, il arrive qu’une source de données avec un faible nombre total de durée de vie et une activité élevée ait plus de valeur que celles avec des résultats de durée de vie élevés et un faible nombre d’activités. </p> <p> <p>Remarque : Les mesures <span class="wintitle"> Activité authentifiée</span> contiennent uniquement des données <span class="wintitle"> Lien de profil</span>. Ce rapport n’inclut pas les données <span class="wintitle"> Device Graph</span>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Périphériques moyens par personne</span></b> </p> </td> 
   <td colname="col2"> <p> Indique le nombre moyen d’appareils utilisés par les visiteurs qui se sont authentifiés sur votre site pour la source de données sélectionnée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Nombre total de périphériques</span></b> </p> </td> 
   <td colname="col2"> <p>Indique le nombre total d’appareils utilisés par les visiteurs pour s’authentifier sur votre site pour la source de données sélectionnée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Total personnes</span></b> </p> </td> 
   <td colname="col2"> <p>Affiche le nombre total de personnes qui ont été identifiées de manière déterministe pour la source de données sélectionnée. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Mesures de Device Graph {#device-graph-metrics}

Les rapports [!UICONTROL Merge Rules] affichent également des données sur le nombre total de personnes et d’appareils qui ont visité votre site pour la source de données et la représentation graphique des appareils sélectionnés. Ces mesures renvoient des données en fonction d’intervalles de temps prédéfinis (période de recherche en amont) qui varient selon l’option de périphérique sélectionnée lors de la création d’une règle. Le tableau suivant répertorie ces intervalles de rapport pour chacune des options de représentation graphique des appareils.

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option Device Graph </th> 
   <th colname="col2" class="entry"> Intervalle de recherche en amont des rapports </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Profile Link</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_B2FF2341573840549FFB96579F537082"> 
      <li id="li_B37323C2F2434F41B407500AC5C15447">Nombre total de personnes : 60 jours </li> 
      <li id="li_08D911224A60418BBB3CFB4E70CE73D4">Total des appareils : 120 jours </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Graphique d’appareil Co-op</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_64AD1DD89DF64703B70B973A463BA020"> 
      <li id="li_D7D3A3871F434CBFA71BE8929EB41648">Nombre total de personnes : 180 jours </li> 
      <li id="li_125D387986B2463EB310203CE5857EDA">Total des appareils : 180 jours </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LiveRamp</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_2772F3AD7E1440789B635794ECDE8DFB"> 
      <li id="li_1432363829D64615B1D349A3722D6268">Nombre total de personnes : 180 jours </li> 
      <li id="li_D5C0E3CE92524B54BBD36C73A326292B">Total des appareils : 180 jours </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Tapad</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_274529DB58E6442E95C6AD89BECB1362"> 
      <li id="li_67102211A72A4E47AACFE5E369793C17">Nombre total de personnes : 60 jours </li> 
      <li id="li_3E8F3DA6A7B5487895A626674DA363A5">Nombre total de périphériques 60 jours </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemples de rapports {#sample-reports}

### Rapport Lien de profil standard

Un rapport [!UICONTROL Profile Link] standard ressemble à l’exemple suivant. Les règles de fusion qui utilisent plusieurs sources de données (jusqu’à 3, au maximum) affichent des graphiques dans des onglets distincts pour chaque source de données. Cette règle de fusion n’inclut pas les données [!UICONTROL Device Co-op].

![](assets/profile-link-metrics.png)

### Rapport Lien De Profil Avec Données Graphiques De Périphérique

Un rapport [!UICONTROL Profile Link Device Graph] qui comprend des données de représentation graphique des appareils issues de la [!UICONTROL Adobe Experience Cloud Device Co-op] ou une représentation graphique des appareils tiers affiche les [!UICONTROL Profile Link] données de représentation graphique des appareils avec des graphiques à barres côte à côte. Le placement de ces graphiques les uns à côté des autres vous permet d’évaluer les avantages de l’utilisation de [!UICONTROL Experience Cloud Device Co-op] par rapport à [!UICONTROL Profile Link] en soi. Les règles de fusion qui utilisent plusieurs sources de données (jusqu’à 3, au maximum) affichent des graphiques dans des onglets distincts pour chaque source de données. Pour rappel, le graphique et les mesures [!UICONTROL Authenticated Activity] ne renvoient pas de données provenant de la [!DNL Adobe] représentation graphique des appareils ou d’autres représentations graphiques tierces auxquelles vous avez accès dans [!DNL Audience Manager].

![](assets/profile-link-graph.png)

## Graphiques des tendances des liens de profil {#profile-link-trend}

Outre les autres visualisations de données, les rapports [!UICONTROL Profile Link] incluent un graphique linéaire. Le graphique linéaire est conçu pour vous montrer les tendances au fil du temps de vos règles de profil. Les graphiques de tendances (et les autres rapports) sont disponibles lorsque vous cliquez sur une règle dans la [!UICONTROL Profile Merge Rules] page d’entrée ( **[!UICONTROL Audience Data > Profile Merge Rules]**). Ces graphiques incluent des données de représentation graphique des appareils si vous êtes membre de [!UICONTROL Device Co-op] ou d’autres graphiques d’appareils tiers auxquels vous avez accès dans [!DNL Audience Manager]. Cliquez sur une ligne de tendance pour afficher les données sous-jacentes.

>[!MORELIKETHIS]
>
>* [FAQ sur les règles de fusion de profils](../../faq/faq-profile-merge.md)

