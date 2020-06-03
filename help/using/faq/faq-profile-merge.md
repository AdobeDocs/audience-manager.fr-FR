---
description: Réponses aux questions courantes sur la règle de fusion des Profils et le graphique des périphériques.
keywords: Organization ID
seo-description: Réponses aux questions courantes sur la règle de fusion des Profils et le graphique des périphériques.
seo-title: FAQ sur les règles de fusion de Profils et le graphique de périphériques
solution: Audience Manager
title: FAQ sur les règles de fusion de Profils et le graphique de périphériques
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
translation-type: tm+mt
source-git-commit: 56a9626b1fa77926bdc31ef72b058d2aa9b58f43
workflow-type: tm+mt
source-wordcount: '1545'
ht-degree: 2%

---


# FAQ sur les règles de fusion de Profils et le graphique de périphériques{#profile-merge-rules-and-device-graph-faq}

Réponses aux questions courantes sur la règle de fusion des Profils et le graphique des périphériques.

<!-- profile-merge-faq.xml -->

## Concepts de base des graphiques des périphériques {#device-graph-basics}

**Qu&#39;est-ce qu&#39;un graphique de périphérique ?**

Un graphique de périphérique est un ensemble de mappages d’ID qui définit des groupes de périphériques anonymes. Il associe ces dispositifs à une personne ou à un foyer en fonction d&#39;éléments communs dans les signaux recueillis à partir de chaque dispositif. Ces signaux permettent d&#39;identifier les appareils au niveau individuel ou familial.

 

**Qu&#39;est-ce qu&#39;un graphique de périphérique externe ?**

Un graphique de périphérique externe est un graphique de périphérique dans [!DNL Audience Manager] lequel n’a pas été créé exclusivement à partir de vos propres sources de données inter-périphériques. Par exemple, lorsque vous créez une règle [de fusion de](../features/profile-merge-rules/merge-rules-start.md) Profil et que vous choisissez les options de graphique de périphérique [!UICONTROL Co-op Device Graph] ou tiers, vous travaillez avec un graphique de périphérique externe. Voir Options [](../features/profile-merge-rules/merge-rule-definitions.md#device-options)de périphérique.

 

**Quels sont les cas d&#39;utilisation courants d&#39;un graphique de périphérique externe dans un[!UICONTROL Profile Merge Rule]site ?**

L&#39;objectif principal de l&#39;utilisation d&#39;un graphique d&#39;appareil dans un [!UICONTROL Profile Merge Rule] est d&#39;évaluer et de qualifier plusieurs appareils appartenant à une seule personne ou à un même foyer pour un segment spécifique. Le segment lui-même peut avoir plusieurs utilisations, par exemple, le ciblage d’une audience de prospects avec une publicité diffusée par un fournisseur de services Internet ou la personnalisation de l’expérience sur site d’un client via une plateforme de personnalisation sur site. See [External Device Graph Use Cases](../features/profile-merge-rules/external-graph-use-cases.md).

 

**Audience Manager fournit-il une prise en charge globale des graphiques de périphériques externes ?**

Non. Les graphiques des dispositifs externes sont disponibles uniquement aux États-Unis et au Canada.

 

**À quelle fréquence les données graphiques des périphériques externes sont-elles mises[!DNL Audience Manager]à jour ?**

Une fois par semaine.

 

## Graphiques de périphériques et règles de fusion de Profils {#device-graph-profile-merge-rules}

**Comment utiliser[!DNL Audience Manager]un graphique de périphérique ?**

Dans [!DNL Audience Manager], les graphiques de périphérique apparaissent comme des options de configuration lorsque vous [créez une règle](../features/profile-merge-rules/merge-rules-start.md)de fusion de Profil. Grâce à vos [!UICONTROL Profile Merge Rules]graphiques de périphériques, vous pouvez [!DNL Audience Manager]:

* Fusionnez plusieurs profils de périphérique ensemble. Cela crée un ensemble unique de caractéristiques.
* Evaluez le paramètre de caractéristiques pour la qualification de segment (plutôt que d’évaluer chaque profil de périphérique individuellement).
* Ajoutez des périphériques qualifiés aux segments disponibles.

 

**Combien[!UICONTROL Profile Merge Rules]puis-je créer ?**

Actuellement, vous pouvez créer un maximum de 4 [!UICONTROL Profile Merge Rules]. La quatrième règle de fusion du Profil ([!UICONTROL All Cross-Device Profiles]) n’est disponible que pour les clients qui achètent le [!UICONTROL People-Based Destinations] module complémentaire.

 

**Combien de profils de périphérique fusionnent-ils et lisent-ils[!DNL Audience Manager]lors de l&#39;utilisation d&#39;un graphique de périphérique dans un[!UICONTROL Profile Merge Rule]?**

Lors de la qualification d’un périphérique pour un segment à l’aide d’un [!UICONTROL Profile Merge Rule]gestionnaire d’Audiences fusionne et lit le profil de périphérique actuel et un maximum de 99 autres profils de périphérique supplémentaires liés par l’option de graphique de périphérique sélectionnée.

 

**Quels périphériques sont admissibles pour un segment lors de l’utilisation d’un graphique de périphérique dans un[!UICONTROL Profile Merge Rule]?**

Les périphériques [!DNL Audience Manager] fusionnés et lus sont les mêmes que ceux qui sont qualifiés pour un segment.

 

**Où peut-[!DNL Audience Manager]on envoyer des segments qui ont été qualifiés par un[!UICONTROL Profile Merge Rule]graphique de périphérique ?**

[!DNL Audience Manager] peut envoyer des segments à une destination dans des fichiers de commandes ou en temps réel.

 

## Segments, graphiques de périphériques et règles de fusion de Profils {#segments-device-graphs-rules}

**Comment dissocier un périphérique lorsqu’il n’est plus qualifié pour un segment avec un[!DNL Audience Manager][!UICONTROL Profile Merge Rule]graphique de périphérique ?**

Audience Manager fusionne jusqu’à 100 périphériques lors de l’évaluation de segments avec un graphique [!UICONTROL Profile Merge Rule] utilisant un périphérique. Si le signal de non-segmentation est émis, le périphérique actuel et jusqu&#39;à 99 périphériques supplémentaires seront supprimés du segment dans la destination. Pour plus d’informations sur la désegmentation, voir Règles de fusion des [Profils et Processus](../features/profile-merge-rules/merge-rule-unsegment.md)de désegmentation des périphériques.

 

**Si une destination peut désegmenter des périphériques, est-ce que les périphériques seront supprimés des segments par[!UICONTROL Profile Merge Rules]le biais d’un graphique de périphérique ?**

Oui. Voir l&#39;explication ci-dessus.

 

**Si je crée un segment avec un graphique[!UICONTROL Profile Merge Rule]de périphérique et que le segment utilise à la fois des données en temps réel et des données intégrées, mon segment sera-t-il mis à jour au fur et à mesure que les données intégrées changent ?**

Oui.

 

**Les estimations de la taille des segments incluent-elles les périphériques qui remplissent les critères d’un segment en fonction des connexions fournies par une[!UICONTROL Profile Merge Rule]option de graphique de périphérique ?**

Non. Reportez-vous aux définitions des sections [!UICONTROL Estimated Real-Time Population] et [!UICONTROL Estimated Total Population] dans Données de population de [caractéristiques et de segments dans le créateur](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/segments/segment-builder-data.html)de segments.

 

**Inclut-[!UICONTROL Addressable Audiences]t-il les périphériques qui remplissent les critères d’un segment en fonction des connexions fournies par une[!UICONTROL Profile Merge Rule]option de graphique de périphérique ?**

Oui.

 

**Si un segment utilise un[!UICONTROL Profile Merge Rule]avec[!UICONTROL No Cross-Device Profile]et que les caractéristiques qui qualifient les périphériques pour le segment sont stockées uniquement sur le profil inter-périphériques, la population totale du segment sera-t-elle de 0 ?**

Oui. Audience Manager ne comptabilisera pas les caractéristiques stockées sur le profil inter-périphériques dans l’évaluation des segments lorsque la règle de fusion des Profils est définie sur [!UICONTROL No Cross-Device Profile].

 

## Fréquence des caractéristiques, graphiques de périphériques et règles de fusion de Profils {#trait-freq-device-rules}

**Comment calcule-t-[!DNL Audience Manager]on la fréquence des caractéristiques avec un[!UICONTROL Profile Merge Rule]graphique de périphérique ?**

La fréquence des caractéristiques est définie par la somme du nombre de qualifications pour une caractéristique spécifique sur plusieurs périphériques. Pour vous aider à comprendre ce problème, examinez le cas d’utilisation suivant.

<table id="table_DE7A308705C84B93B3089CAD2228569E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cas d’utilisation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_52EA0F142E3F488CAAC7CF541E7F3472"> 
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">Le périphérique A et le périphérique B sont liés par un graphique de périphérique. </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">Vous disposez d’une règle <span class="wintitle"> de fusion</span> de Profil qui utilise une option de graphique de périphérique. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">Un segment unique (segment 1) composé d'un trait unique (caractéristique 1), où le trait 1 a une fréquence de 8. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Actions</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> lit et fusionne les profils des périphériques A et B. À partir de cela, nous voyons les éléments suivants : </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">Le périphérique A a été qualifié pour la caractéristique 1 trois fois. Il a une fréquence de 3 pour le trait 1. </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">Le périphérique B a été qualifié pour la caractéristique 1 cinq fois. Il a une fréquence de 5 pour le trait 1. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Résultats</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> additionne la fréquence de la caractéristique 1 et utilise 8 (3 + 5 = 8) pour décider de la qualification du segment. Le périphérique A et le périphérique B sont inclus dans le segment 1, car leur fréquence est de 8. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

## Rapports, graphiques de périphériques et règles de fusion de Profils {#reports-device-graphs-rules}

**Puis-je voir le nombre de périphériques accessibles par un graphique[!UICONTROL Profile Merge Rule]utilisant un périphérique ?**

Oui. Les rapports renvoient des données au [!UICONTROL Profile Merge Rule] niveau. Les données du rapport sont mises à jour quotidiennement. Les données sont basées sur les périphériques affichés dans votre compte, et non sur ceux liés par un graphique de périphérique. Voir Mesures des [rapports pour les règles](../features/profile-merge-rules/profile-link-metrics.md)de fusion de Profils.

 

**Puis-je voir en temps *réel*le nombre de périphériques qualifiés pour un segment spécifique avec[!UICONTROL Profile Merge Rules]un graphique de périphérique ?**

Oui. La mesure de population en temps réel capture les qualifications des segments pour le périphérique actuel (périphérique affiché en temps réel) en utilisant les profils de tous les périphériques liés par un graphique de périphérique.

<table id="table_D37A51E99B314C04A96A084491A5FEC7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément du cas d’utilisation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2"> <p>Supposons que nous ayons : </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">Le segment 1 repose sur les caractéristiques et la logique de qualification suivantes : Segment 1 = Caractéristique A et Caractéristique B et Caractéristique C. </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3 profils de périphériques : Périphérique 1 (périphérique actuel), Périphérique 2 (graphique de périphérique), Périphérique 3 (graphique de périphérique). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Actions</b> </p> </td> 
   <td colname="col2"> <p>Chaque caractéristique disponible est associée à un périphérique : </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">Périphérique 1 : Caractéristique A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">Périphérique 2 : Caractéristique B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">Périphérique 3 : Caractéristique C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Résultats</b> </p> </td> 
   <td colname="col2"> <p>Compte tenu des éléments précédents, la population totale du segment 1 est de un. </p> <p>Dans ce cas, la règle <span class="wintitle"> de fusion des</span> Profils utilise tous les périphériques et leurs caractéristiques pour décider de la qualification des segments. Cela signifie que les périphériques 1, 2 et 3 sont inclus dans le segment 1, mais, comme indiqué ci-dessus, seul le périphérique 1 est inclus dans la population de segments en temps réel. En effet : </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">Périphérique 1 est le périphérique en cours qui interagit en temps réel avec les serveurs <span class="wintitle"> de collecte de données d’Audience Manager</span> (<span class="wintitle"> DCS</span>). </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">Les périphériques 2 et 3 sont associés au périphérique 1 par un graphique de périphérique, mais ils n’interagissent pas avec le serveur de collecte de données en même temps que le périphérique 1. </li> 
     </ul> </p> <p>Par conséquent, les périphériques 2 et 3 ne sont pas inclus dans la mesure de population de segments en temps réel. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**Puis-je voir le nombre total de périphériques qualifiés pour un segment spécifique avec un graphique[!UICONTROL Profile Merge Rule]de périphérique ?**

Oui. La mesure de population totale de segments inclut les périphériques supplémentaires qui se sont qualifiés pour un segment en fonction des connexions à partir d’un graphique de périphériques.

<table id="table_932E61B1D4374DD58F673C3B35C365EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément du cas d’utilisation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2"> <p>Supposons que nous ayons : </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">Le segment 1 repose sur les caractéristiques et la logique de qualification suivantes : Segment 1 = Caractéristique A et Caractéristique B et Caractéristique C. </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3 profils de périphériques : Périphérique 1 (périphérique actuel), Périphérique 2 (graphique de périphérique), Périphérique 3 (graphique de périphérique). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Associations</b> </p> </td> 
   <td colname="col2"> <p>Chaque caractéristique disponible est associée à un périphérique : </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">Périphérique 1 : Caractéristique A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">Périphérique 2 : Caractéristique B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">Périphérique 3 : Caractéristique C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Résultats</b> </p> </td> 
   <td colname="col2"> <p>Compte tenu des éléments précédents, la population totale du segment 1 est de trois (3). </p> <p>Dans ce cas, la règle <span class="wintitle"> de fusion des</span> Profils utilise tous les périphériques et leurs caractéristiques pour décider de la qualification des segments. Cela signifie que les périphériques 1, 2 et 3 sont admissibles au segment 1 et que les trois sont inclus dans la population totale. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**Les périphériques qui remplissent les critères d’un segment avec un graphique[!UICONTROL Profile Merge Rule]utilisant un périphérique sont-ils inclus dans les[!UICONTROL Interactive]rapports,[!UICONTROL Overlap]rapports et[!UICONTROL Audience Optimization]rapports ?**

Non.

**Pourquoi mes exportations de segments vers Adobe Campaign s’affichent-elles comme 0 après le 16 mars 2020 ?**

À la fin de 2019, nous avons publié une série d’améliorations des règles de fusion de Profil afin d’améliorer la précision des fichiers de commandes générés à l’aide d’ID d’ensemble de périphériques. Ces améliorations seront strictement respectées dans votre instance Gestionnaire d’Audiences à partir du lundi 16 mars 2020. Par conséquent, les segments mappés à une destination à l’aide d’un ID inter-périphériques cesseront de produire des exportations dans certaines configurations de règles de fusion de Profil.

Pour garantir l’intégration correcte entre votre instance Audience Manager et vos destinations à l’aide d’identifiants sur plusieurs périphériques, tels que Adobe Campaign, assurez-vous de respecter les exigences suivantes :

1. Examinez la règle de fusion de Profils utilisée par les segments mappés à votre destination d’identifiant déclaré Adobe Campaign. La règle de fusion des Profils doit utiliser l’ [!UICONTROL Last Authenticated Profile] option, de sorte que tous les profils authentifiés puissent être inclus dans les exportations. Si votre règle de fusion de Profil utilise une autre option, basculez-la sur [!UICONTROL Last Authenticated Profile].
2. Sélectionnez la source de données d’ID déclarés Adobe Campaign dans les paramètres de la règle de fusion de Profils.

>[!NOTE]
>
> Nous avons augmenté la limite de la règle de fusion de Profil de 1 pour les clients confrontés à cette situation, de sorte que vous puissiez créer une règle de fusion de Profil dédiée pour les segments mappés à la destination de l’identifiant déclaré Adobe Campaign, sans modifier les règles de fusion de Profils pour les autres cas d’utilisation.

>[!MORELIKETHIS]
>
>* [Profile Link](../features/profile-merge-rules/profile-link-use-case.md)

