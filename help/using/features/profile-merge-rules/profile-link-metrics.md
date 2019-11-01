---
description: Les mesures Lien de profil fournissent des données sur les personnes et les périphériques qui s’authentifient sur votre site. Les données et graphiques du lien de profil se mettent à jour dynamiquement lorsque vous créez des règles de fusion ou lorsque vous cliquez sur une règle existante dans le tableau de bord Règles de fusion de profil. Ces mesures peuvent inclure un graphique de périphérique issu d’Adobe Experience Cloud Device Co-op ou d’autres sources de graphique de périphérique tiers.
seo-description: Les mesures Lien de profil fournissent des données sur les personnes et les périphériques qui s’authentifient sur votre site. Les données et graphiques du lien de profil se mettent à jour dynamiquement lorsque vous créez des règles de fusion ou lorsque vous cliquez sur une règle existante dans le tableau de bord Règles de fusion de profil. Ces mesures peuvent inclure un graphique de périphérique issu d’Adobe Experience Cloud Device Co-op ou d’autres sources de graphique de périphérique tiers.
seo-title: Mesures des rapports pour les règles de fusion de profils
solution: Audience Manager
title: Mesures des rapports pour les règles de fusion de profils
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Mesures des rapports pour les règles de fusion de profils {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Merge Rule] les mesures fournissent des données sur les personnes et les périphériques qui s’authentifient sur votre site. Les données et les graphiques sont [!UICONTROL Profile Merge Rule Reports] mis à jour dynamiquement lorsque vous créez une règle de fusion ou lorsque vous cliquez sur une règle existante dans le [!UICONTROL Profile Merge Rules] tableau de bord. Ces mesures peuvent inclure des graphiques de périphériques provenant de sources de graphiques de périphériques [!DNL Adobe Experience Cloud Device Co-op] ou d’autres sources tierces.

## Fusionner les mesures de règle {#merge-rule-metrics}

Les rapports renvoient des données dans des graphiques à barres côte-à-côte lorsque vos règles de fusion utilisent des données provenant d’ [Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/) ou d’autres graphiques de périphériques tiers auxquels vous avez accès [!DNL Audience Manager]. Vous pouvez ainsi comparer vos données propriétaires authentifiées avec les données inter-périphériques fournies par le graphique de périphériques tiers [!UICONTROL Experience Cloud Device Co-op] ou un autre graphique de périphériques tiers. Pour plus d’informations sur les données renvoyées par [!UICONTROL Device Co-op]l’application, voir [Le graphique de périphériques : Processus internes et sortie](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html). Ces données sont mises à jour quotidiennement.

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
   <td colname="col2"> <p>Montre : </p> 
    <ul id="ul_7F7373919A4A49028EF4BF7B28D9F8E9"> 
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> Personnes</span>actives : Nombre de personnes qui se sont authentifiées sur votre site au cours des 60 derniers jours. </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> Périphérique</span>croisé : Nombre total d’identifiants <a href="merge-rules-start.md#create-data-source"> de</a> plusieurs périphériques stockés dans la <a href="https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html"> source</a> de données du profil <a href="merge-rule-definitions.md"></a> authentifié sélectionné pour la durée de vie de la source de données. </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> % de personnes</span>actives : Affiche les personnes <span class="wintitle"></span> actives sous forme de %. </li> 
    </ul> <p> <span class="wintitle"> Activité</span> authentifiée vous permet de comparer les sources de données par activité, volume et pourcentage. Il peut vous aider à trouver une source de données qui compte beaucoup de personnes et un pourcentage élevé d’utilisateurs actifs. Vous pouvez également trouver intéressant de comparer les sources de données à une proportion élevée d’utilisateurs actifs par rapport à la taille totale de l’audience. Par exemple, il arrive qu’une source de données avec un faible nombre total de durée de vie et une forte activité soit plus précieuse que celles avec des résultats de durée de vie élevés et un faible nombre d’activités. </p> <p> <p>Remarque : Les mesures Activité <span class="wintitle"></span> authentifiée contiennent uniquement des données de lien <span class="wintitle"></span> de profil. Ce rapport n’inclut pas les données de graphique <span class="wintitle"></span> de périphérique. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Périphériques moyens par personne</span></b> </p> </td> 
   <td colname="col2"> <p> Indique le nombre moyen de périphériques utilisés par les visiteurs qui se sont authentifiés sur votre site pour la source de données sélectionnée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Nombre total de périphériques</span></b> </p> </td> 
   <td colname="col2"> <p>Indique le nombre total de périphériques que les visiteurs ont utilisés pour s’authentifier sur votre site pour la source de données sélectionnée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Nombre total de personnes</span></b> </p> </td> 
   <td colname="col2"> <p>Affiche le nombre total de personnes identifiées de manière déterministe pour la source de données sélectionnée. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Mesures de graphique de périphérique {#device-graph-metrics}

Les [!UICONTROL Merge Rules] rapports affichent également des données sur le nombre total de personnes et de périphériques qui ont consulté votre site pour la source de données et le graphique de périphériques sélectionnés. Ces mesures renvoient des données basées sur des intervalles de temps prédéfinis (période de recherche en arrière) qui varient selon l’option de périphérique sélectionnée lors de la création d’une règle. Le tableau suivant répertorie ces intervalles de rapport pour chaque option de graphique de périphérique.

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option graphique de périphérique </th> 
   <th colname="col2" class="entry"> Intervalle de recherche de rapport </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Profile Link</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_B2FF2341573840549FFB96579F537082"> 
      <li id="li_B37323C2F2434F41B407500AC5C15447">Nombre total de personnes : 60 jours </li> 
      <li id="li_08D911224A60418BBB3CFB4E70CE73D4">Nombre total de périphériques : 120 jours </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Graphique du périphérique de co-op</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_64AD1DD89DF64703B70B973A463BA020"> 
      <li id="li_D7D3A3871F434CBFA71BE8929EB41648">Nombre total de personnes : 180 jours </li> 
      <li id="li_125D387986B2463EB310203CE5857EDA">Nombre total de périphériques : 180 jours </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LiveRamp</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_2772F3AD7E1440789B635794ECDE8DFB"> 
      <li id="li_1432363829D64615B1D349A3722D6268">Nombre total de personnes : 180 jours </li> 
      <li id="li_D5C0E3CE92524B54BBD36C73A326292B">Nombre total de périphériques : 180 jours </li> 
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

### Rapport de lien de profil standard

Un [!UICONTROL Profile Link] rapport standard ressemble à l’exemple suivant. Les règles de fusion qui utilisent plusieurs sources de données (jusqu’à 3 au maximum) affichent des graphiques dans des onglets distincts pour chaque source de données. Cette règle de fusion n’inclut pas [!UICONTROL Device Co-op] les données.

![](assets/profile-link-metrics.png)

### Rapport Lien De Profil Avec Données Graphiques De Périphérique

Un [!UICONTROL Profile Link Device Graph] rapport qui inclut des données de graphique de périphérique issues du graphique de périphérique [!UICONTROL Adobe Experience Cloud Device Co-op] ou d’un graphique de périphérique tiers affiche [!UICONTROL Profile Link] et les données de graphique de périphérique avec des graphiques à barres côte à côte. Le fait de placer ces graphiques côte à côte vous permet d’évaluer les avantages de l’utilisation de la [!UICONTROL Experience Cloud Device Co-op] variable par rapport à [!UICONTROL Profile Link] elle-même. Les règles de fusion qui utilisent plusieurs sources de données (jusqu’à 3 au maximum) affichent des graphiques dans des onglets distincts pour chaque source de données. En guise de rappel, le [!UICONTROL Authenticated Activity] graphique et les mesures ne renvoient aucune donnée du graphique de [!DNL Adobe] périphérique ou d’autres graphiques de périphérique tiers auxquels vous avez accès dans [!DNL Audience Manager].

![](assets/profile-link-graph.png)

## Graphiques de tendances des liens de profil {#profile-link-trend}

Outre les autres visualisations de données, [!UICONTROL Profile Link] les rapports incluent un graphique linéaire. Le graphique linéaire est conçu pour vous montrer les tendances au fil du temps pour vos règles de profil. Les graphiques de tendances (et les autres rapports) sont disponibles lorsque vous cliquez sur une règle dans la page d’ [!UICONTROL Profile Merge Rules] entrée ( **[!UICONTROL Audience Data > Profile Merge Rules]**). Ces graphiques incluent des données de graphique de périphérique si vous êtes membre du [!UICONTROL Device Co-op] ou d’autres graphiques de périphérique tiers auxquels vous avez accès dans [!DNL Audience Manager]. Cliquez sur une ligne de tendance pour afficher les données sous-jacentes.

>[!MORELIKETHIS]
>
>* [FAQ sur les règles de fusion de profils](../../faq/faq-profile-merge.md)

