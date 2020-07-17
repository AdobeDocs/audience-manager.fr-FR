---
description: Réponses aux questions courantes concernant les stratégies de fusion de profils et la représentation graphique des appareils.
keywords: Organization ID
seo-description: Réponses aux questions courantes concernant les stratégies de fusion de profils et la représentation graphique des appareils.
seo-title: FAQ sur les stratégies de fusion de profils et la représentation graphique des appareils
solution: Audience Manager
title: FAQ sur les stratégies de fusion de profils et la représentation graphique des appareils
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1548'
ht-degree: 86%

---


# FAQ sur les stratégies de fusion de profils et la représentation graphique des appareils {#profile-merge-rules-and-device-graph-faq}

Réponses aux questions courantes concernant les stratégies de fusion de profils et la représentation graphique des appareils.

<!-- profile-merge-faq.xml -->

## Concepts de base de la représentation graphique des appareils {#device-graph-basics}

**Qu’est-ce que la représentation graphique des appareils ?**

La représentation graphique des appareils est un ensemble de mappages d’identifiants qui définit des groupes d’appareils anonymes. Il associe ces appareils à une personne ou à un foyer en fonction d’éléments communs présents dans les signaux recueillis à partir de chaque appareil. Ces signaux permettent d’identifier les appareils au niveau individuel ou familial.

 

**Qu’est-ce que la représentation graphique externe des appareils ?**

La représentation graphique externe des appareils constitue toute représentation graphique d’appareil dans [!DNL Audience Manager] qui n’a pas été créée exclusivement à partir de vos propres sources de données multi-appareils. Par exemple, lorsque vous créez une [stratégie de fusion de profils](../features/profile-merge-rules/merge-rules-start.md) et que vous sélectionnez les options de représentation graphique des appareils [!UICONTROL Co-op Device Graph] ou tiers, vous travaillez avec une représentation graphique externe des appareils. Voir [Options d’appareil](../features/profile-merge-rules/merge-rule-definitions.md#device-options).

 

**Quels sont les cas d’utilisation courants d’une représentation graphique externe des appareils dans une [!UICONTROL Profile Merge Rule] ?**

L’objectif principal de l’utilisation d’une représentation graphique des appareils dans une [!UICONTROL Profile Merge Rule] est d’évaluer et de qualifier plusieurs appareils appartenant à une même personne ou à un même foyer pour un segment spécifique. Le segment lui-même peut avoir plusieurs utilisations : par exemple, le ciblage d’une audience de prospects avec une publicité diffusée par un DSP ou la personnalisation de l’expérience sur site d’un client au moyen d’une plateforme de personnalisation sur site. Voir [Cas d’utilisation des représentations graphiques externes des appareils](../features/profile-merge-rules/external-graph-use-cases.md).

 

**Audience Manager prend-il en charge les représentations graphiques externes des appareils dans le monde entier ?**

Non. Les représentations graphiques externes des appareils sont disponibles uniquement aux États-Unis et au Canada.

 

**À quelle fréquence [!DNL Audience Manager] met-il à jour les données des représentations graphiques externes des appareils ?**

Une fois par semaine.

 

## Représentations graphiques des appareils et stratégies de fusion de profils {#device-graph-profile-merge-rules}

**Comment [!DNL Audience Manager] utilise-t-il une représentation graphique des appareils ?**

Dans [!DNL Audience Manager], les représentations graphiques des appareils apparaissent en tant qu’options de configuration lorsque vous [créez une stratégie de fusion de profils](../features/profile-merge-rules/merge-rules-start.md). Grâce à vos [!UICONTROL Profile Merge Rules], ces représentations graphiques des appareils permettent à [!DNL Audience Manager] :

* de fusionner plusieurs profils d’appareils. Cela crée un sur-ensemble unique de caractéristiques ;
* d’évaluer le sur-ensemble de caractéristiques pour la qualification de segment (plutôt que d’évaluer chaque profil d’appareil de manière individuelle) ;
* d’ajouter des appareils qualifiés aux segments disponibles.

 

**Combien de [!UICONTROL Profile Merge Rules] puis-je créer ?**

Actuellement, vous pouvez créer un maximum de 4 [!UICONTROL Profile Merge Rules]. La quatrième stratégie de fusion de profils ([!UICONTROL All Cross-Device Profiles]) est réservée aux clients qui ont acheté le module complémentaire [!UICONTROL People-Based Destinations].

 

**Combien de profils d’appareils [!DNL Audience Manager] fusionne et lit-il lorsqu’il utilise une représentation graphique des appareils dans une [!UICONTROL Profile Merge Rule] ?**

Lors de la qualification d’un appareil pour un segment au moyen d’une [!UICONTROL Profile Merge Rule], Audience Manager fusionne et lit le profil d’appareil actuel ainsi qu’un maximum de 99 autres profils d’appareils supplémentaires liés par l’option de représentation graphique des appareils que vous avez sélectionnée.

 

**Quels appareils sont qualifiés pour un segment lors de l’utilisation d’une représentation graphique des appareils dans une [!UICONTROL Profile Merge Rule] ?**

Les appareils fusionnés et lus par [!DNL Audience Manager] sont les mêmes que ceux qualifiés pour un segment.

 

**Où [!DNL Audience Manager] peut-il envoyer des segments qualifiés par une [!UICONTROL Profile Merge Rule] qui utilise une représentation graphique des appareils ?**

[!DNL Audience Manager] peut envoyer des segments vers une destination dans des fichiers de lots ou en temps réel.

 

## Segments, représentations graphiques des appareils et stratégies de fusion de profils {#segments-device-graphs-rules}

**Comment [!DNL Audience Manager] supprime-t-il la segmentation d’un appareil lorsqu’il n’est plus qualifié pour un segment avec une [!UICONTROL Profile Merge Rule] qui utilise une représentation graphique des appareils ?**

Audience Manager fusionne jusqu’à 100 appareils lors de l’évaluation de segments avec une [!UICONTROL Profile Merge Rule] qui utilise une représentation graphique des appareils. Si le signal de suppression de la segmentation est émis, l’appareil actuel et jusqu’à 99 appareils supplémentaires seront retirés du segment dans la destination. Pour plus d’informations sur la suppression de la segmentation, voir [Stratégies de fusion de profils et processus de suppression de la segmentation des appareils](../features/profile-merge-rules/merge-rule-unsegment.md).

 

**Si une destination peut supprimer la segmentation des appareils, les appareils seront-ils retirés des segments par les [!UICONTROL Profile Merge Rules] qui utilisent une représentation graphique des appareils ?**

Oui. Reportez-vous à l’explication ci-dessus.

 

**Si je crée un segment avec une [!UICONTROL Profile Merge Rule] qui utilise une représentation graphique des appareils et que le segment utilise à la fois des données en temps réel et des données intégrées, mon segment sera-t-il mis à jour au fur et à mesure que les données intégrées changent ?**

Oui.

 

**Les estimations de la taille des segments incluent-elles les appareils qualifiés pour un segment en fonction des connexions fournies par une [!UICONTROL Profile Merge Rule] qui utilise une représentation graphique des appareils ?**

Non. Voir les définitions pour [!UICONTROL Estimated Real-Time Population] et [!UICONTROL Estimated Total Population] dans [Données sur les caractéristiques et la population de segments dans le créateur de segments](https://docs.adobe.com/content/help/fr-FR/audience-manager/user-guide/features/segments/segment-builder-data.html).

 

**[!UICONTROL Addressable Audiences] inclut-il les appareils qualifiés pour un segment en fonction des connexions fournies par une [!UICONTROL Profile Merge Rule] qui utilise une représentation graphique des appareils ?**

Oui.

 

**Si un segment utilise une [!UICONTROL Profile Merge Rule] avec [!UICONTROL No Cross-Device Profile] et que les caractéristiques qualifiant les appareils pour le segment sont stockées uniquement sur le profil multi-appareils, la population totale du segment sera-t-elle de 0 ?**

Oui. Audience Manager ne comptabilisera pas les caractéristiques stockées sur le profil multi-appareils dans la notation des segments lorsque la stratégie de fusion de profils est définie sur [!UICONTROL No Cross-Device Profile].

 

## Fréquence des caractéristiques, représentations graphiques des appareils et stratégies de fusion de profils {#trait-freq-device-rules}

**Comment [!DNL Audience Manager] calcule-t-il la fréquence des caractéristiques avec une [!UICONTROL Profile Merge Rule] qui utilise une représentation graphique des appareils ?**

La fréquence des caractéristiques est définie par la somme du nombre de qualifications pour une caractéristique spécifique sur plusieurs appareils. Le cas d’utilisation suivant vous aidera à comprendre ce calcul :

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
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">L’appareil A et l’appareil B sont liés par une représentation graphique des appareils. </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">Vous disposez d’une <span class="wintitle">stratégie de fusion de profils</span> qui utilise une option de représentation graphique des appareils. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">Un seul segment (segment 1) composé d’une seule caractéristique (caractéristique 1), où la caractéristique 1 a une fréquence de 8. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Actions</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> lit et fusionne les profils des appareils A et B. Voici ce qui se produit alors : </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">L’appareil A a été qualifié pour la caractéristique 1 trois fois. Il a une fréquence de 3 pour la caractéristique 1. </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">L’appareil B a été qualifié pour la caractéristique 1 cinq fois. Il a une fréquence de 5 pour la caractéristique 1. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Résultats</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> additionne la fréquence de la caractéristique 1 et utilise 8 (3 + 5 = 8) pour décider de la qualification du segment. L’appareil A et l’appareil B sont tous deux qualifiés pour le segment 1, car leur fréquence est de 8. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

## Rapports, représentations graphiques des appareils et stratégies de fusion de profils {#reports-device-graphs-rules}

**Puis-je consulter le nombre d’appareils accessibles par une [!UICONTROL Profile Merge Rule] qui utilise une représentation graphique des appareils ?**

Oui. Les rapports renvoient des données au niveau de la [!UICONTROL Profile Merge Rule]. Les données du rapport sont mises à jour quotidiennement. Les données sont basées sur les appareils affichés dans votre compte, et non ceux liés par une représentation graphique des appareils. Voir [Mesures des rapports pour les stratégies de fusion de profils](../features/profile-merge-rules/profile-link-metrics.md).

 

**Puis-je consulter *en temps réel* le nombre d’appareils qualifiés pour un segment spécifique avec une [!UICONTROL Profile Merge Rules] qui utilise une représentation graphique des appareils ?**

Oui. La mesure de population en temps réel capture les qualifications de segments pour l’appareil actuel (l’appareil détecté en temps réel) en utilisant les profils de tous les appareils liés par une représentation graphique des appareils.

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
   <td colname="col2"> <p>Supposons que nous ayons : </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">le segment 1 élaboré sur les caractéristiques et la logique de qualification suivantes : segment 1 = caractéristique A et caractéristique B et caractéristique C ; </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3 profils d’appareils : appareil 1 (appareil actuel), appareil 2 (représentation graphique des appareils), appareil 3 (représentation graphique des appareils). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Actions</b> </p> </td> 
   <td colname="col2"> <p>Chaque caractéristique disponible est associée à un appareil : </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">Appareil 1 : caractéristique A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">Appareil 2 : caractéristique B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">Appareil 3 : caractéristique C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Résultats</b> </p> </td> 
   <td colname="col2"> <p>Compte tenu des éléments précédents, la population totale du segment 1 est de un. </p> <p>Dans ce cas, la <span class="wintitle"> stratégie de fusion de profils</span> utilise tous les appareils ainsi que leurs caractéristiques pour décider de la qualification pour un segment. Cela signifie que les appareils 1, 2 et 3 sont qualifiés pour le segment 1, mais que, comme indiqué ci-dessus, seul l’appareil 1 est inclus dans la population de segment en temps réel. En effet : </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">L’appareil 1 est l’appareil actuel qui interagit en temps réel avec les <span class="wintitle"> serveurs de collecte de données</span> (<span class="wintitle"> DCS</span>) d’Audience Manager. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">Les appareils 2 et 3 sont associés à l’appareil 1 par une représentation graphique des appareils, mais ils n’interagissent pas avec le serveur de collecte de données en même temps que l’appareil 1. </li> 
     </ul> </p> <p>Par conséquent, les appareils 2 et 3 ne sont pas inclus dans la mesure de population de segments en temps réel. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**Puis-je consulter le nombre total d’appareils qualifiés pour un segment spécifique avec une [!UICONTROL Profile Merge Rule] qui utilise une représentation graphique des appareils ?**

Oui. La mesure de population totale de segments inclut les appareils supplémentaires qualifiés pour un segment en fonction des connexions à partir d’une représentation graphique des appareils.

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
   <td colname="col2"> <p>Supposons que nous ayons : </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">le segment 1 élaboré sur les caractéristiques et la logique de qualification suivantes : segment 1 = caractéristique A et caractéristique B et caractéristique C ; </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3 profils d’appareils : appareil 1 (appareil actuel), appareil 2 (représentation graphique des appareils), appareil 3 (représentation graphique des appareils). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Associations</b> </p> </td> 
   <td colname="col2"> <p>Chaque caractéristique disponible est associée à un appareil : </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">Appareil 1 : caractéristique A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">Appareil 2 : caractéristique B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">Appareil 3 : caractéristique C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Résultats</b> </p> </td> 
   <td colname="col2"> <p>Compte tenu des éléments précédents, la population totale du segment 1 est de trois (3). </p> <p>Dans ce cas, la <span class="wintitle"> stratégie de fusion de profils</span> utilise tous les appareils ainsi que leurs caractéristiques pour décider de la qualification pour un segment. Cela signifie que les appareils 1, 2 et 3 sont qualifiés pour le segment 1 et qu’ils sont tous les trois inclus dans la population totale. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**Les appareils qualifiés pour un segment avec une [!UICONTROL Profile Merge Rule] qui utilise une représentation graphique des appareils sont-ils inclus dans les rapports [!UICONTROL Interactive], [!UICONTROL Overlap] et [!UICONTROL Audience Optimization] ?**

Non.

**Pourquoi est-ce que je vois une population de segments nulle pour les exportations de segments vers l’Adobe Campaign après le 16 mars 2020 ?**

À la fin de 2019, nous avons publié une série d’améliorations des règles de fusion de Profil afin d’améliorer la précision des fichiers de commandes générés à l’aide d’ID d’ensemble de périphériques. Ces améliorations seront strictement respectées dans votre instance d’Audience Manager à partir du lundi 16 mars 2020. Par conséquent, les segments mappés à une destination à l’aide d’un ID inter-périphériques cesseront de produire des exportations dans certaines configurations de règles de fusion de Profil.

Pour garantir l’intégration correcte entre votre instance d’Audience Manager et vos destinations à l’aide d’identifiants inter-périphériques, tels que l’Adobe Campaign, assurez-vous de respecter les exigences suivantes :

1. Examinez la règle de fusion de Profils utilisée par les segments mappés à votre destination d’identifiant déclaré Adobe Campaign. La règle de fusion des Profils doit utiliser l’ [!UICONTROL Last Authenticated Profile] option, de sorte que tous les profils authentifiés puissent être inclus dans les exportations. Si votre règle de fusion de Profil utilise une autre option, basculez-la sur [!UICONTROL Last Authenticated Profile].
2. Sélectionnez la source de données d’identifiant déclaré de l’Adobe Campaign dans les paramètres de la règle de fusion de Profils.

>[!NOTE]
>
> Nous avons augmenté la limite de la règle de fusion de Profil de 1 pour les clients confrontés à cette situation, de sorte que vous puissiez créer une règle de fusion de Profil dédiée pour les segments mappés à la destination de l’identifiant déclaré de l’Adobe Campaign, sans modifier les règles de fusion de Profil pour les autres cas d’utilisation.

>[!MORELIKETHIS]
>
>* [Profile Link](../features/profile-merge-rules/profile-link-use-case.md)

