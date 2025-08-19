---
description: Les options des règles de fusion de profil vous permettent d’étendre ou de renforcer le focus de l’audience sur des audiences spécifiques en fonction des besoins ou des objectifs commerciaux. Ces cas d’utilisation généraux expliquent comment utiliser les options disponibles et créer des règles de fusion pour le ciblage individuel, domestique et sur l’ensemble des appareils.
seo-description: Profile Merge Rules options let you expand or tighten audience focus on specific audiences based on business needs or goals. These general use cases explore how to use available options and create merge rules for individual, household, and cross-device targeting.
seo-title: General Use Cases for Profile Merge Rules
solution: Audience Manager
title: Cas d’utilisation généraux des règles de fusion de profils
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
feature: Profile Merge
exl-id: 66341736-4f61-4306-b9f4-1b37dc7ce0ff
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 1%

---

# Cas d’utilisation généraux des règles de fusion de profils {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] options vous permettent d’étendre ou de renforcer la cible d’audience selon des audiences spécifiques en fonction des besoins ou des objectifs de l’entreprise. Ces cas d’utilisation généraux expliquent comment utiliser les options disponibles et créer des règles de fusion pour le ciblage individuel, domestique et sur l’ensemble des appareils. [!UICONTROL Profile Merge Rules] fonctionne avec les destinations en temps réel et par lots.

>[!TIP]
>
>Pour obtenir la définition et la description de ces paramètres de [!UICONTROL Merge Rule], voir [Options de règle de fusion de profil définies](merge-rule-definitions.md).

## Ciblage d’appareil {#device-personalization}

Ce scénario s’applique aux marketeurs qui souhaitent évaluer un profil d’appareil unique pour un segment d’audience défini dans Audience Manager, afin de fournir une expérience cohérente à l’appareil à l’aide de plateformes de ciblage qui prennent en charge les identifiants d’appareil (DSP, plateformes de personnalisation sur site et autres plateformes de ciblage basées sur des appareils), sans prendre en compte l’authentification des utilisateurs.

Pour créer une règle qui cible uniquement les profils d’appareil, sélectionnez **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**.

![périphérique uniquement](assets/device-only.png)

Disons que John possède trois smartphones. Deux d’entre eux sont des iPhone 7 sur le plan de données A, et l’un d’eux est un Samsung sur le plan de données B. Sans tenir compte de son état d’authentification sur l’un des trois appareils, l’opérateur de téléphonie mobile de John souhaite lui offrir une mise à niveau du plan de données, mais uniquement pour les appareils iPhone 7 qui s’exécutent sur le plan de données A.

En utilisant la règle **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**, [!DNL Device 1] et [!DNL Device 3] sont tous deux qualifiés pour le segment, tandis que l’appareil 2 est ignoré.

![périphérique uniquement](assets/device-management.png)

## Ciblage des appareils partagés {#target-shared-devices}

Disons que John et sa femme, Jane, utilisent le même ordinateur portable pour visiter une boutique en ligne et commander divers articles.

John utilise son propre compte pour réserver des billets de voyage et des offres spéciales, tandis que Jane utilise son propre compte pour acheter de la musique et des films.

L’équipe marketing du magasin peut utiliser la règle **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** pour cibler John et Jane avec des offres spécifiques, en fonction uniquement de leur activité authentifiée.

![current-no-device](assets/current-no-device.png)

En utilisant cette règle, Audience Manager ignore complètement le profil d’appareil, qualifiant l’identifiant CRM de Jean pour le segment et ne qualifiant pas l’identifiant CRM de Jeanne.

![ciblage-d’appareil-partagé](assets/shared-device-targeting.png)

## Ciblage en ligne/hors ligne {#device-household-targeting}

Ce cas d’utilisation couvre la gestion des identités des ménages. Une entreprise peut fusionner un profil d’appareil unique avec le dernier profil qui s’est authentifié sur cet appareil, à l’aide de la règle **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]**.

![last-device-profile](assets/last-device-profile.png)

Prenons un segment composé de ménages dont le revenu est supérieur à 100 000 $/an et qui contient au moins un appareil [!DNL iPhone 7] sur le [!DNL Data Plan B]. Nous disposons de deux profils domestiques (profils sur plusieurs appareils), chacun connecté à deux profils d’appareils différents. Les caractéristiques requises pour être qualifiées pour le segment sont distribuées sur les profils d’appareil et inter-appareils.

Audience Manager fusionne chaque paire de profils appareil + inter-appareil pour voir si l’ensemble fusionné de caractéristiques est admissible pour le segment. Comme Audience Manager évalue chaque profil qui a été inclus dans la fusion, il est possible de segmenter à la fois un profil d’appareil et un profil domestique.

Le lien entre l’appareil et le profil domestique permet à Audience Manager de se qualifier [!DNL Household 2] pour le segment, mais pas [!DNL Household 1]. À partir de [!DNL Household 2], seul [!DNL Device 3] est qualifié pour le segment. Cette [!UICONTROL Profile Merge Rule] a permis au professionnel du marketing de diffuser un message marketing cohérent à un appareil individuel ([!DNL Device 3]) et à l’ensemble de la maison ([!DNL Household 2]).

![gestion des ménages](assets/household-management.png)

## Ciblage des destinations basées sur les personnes {#all-cross-device}

>[!IMPORTANT]
>
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans le présent document n&#39;est un avis juridique. Veuillez consulter votre propre service juridique pour obtenir des conseils juridiques.

Ce scénario de ciblage n’est disponible que pour les clients qui ont acheté le module complémentaire [!DNL People-Based Destinations]. Cette règle permet aux spécialistes marketing d’atteindre les clients en fonction de leurs propres données authentifiées.

Supposons qu’un retailer en ligne souhaite atteindre des clients existants par le biais de plateformes sociales et leur présenter des offres personnalisées en fonction de leurs commandes précédentes. Avec [!UICONTROL People-Based Destinations], ils peuvent ingérer des adresses e-mail hachées de leur propre [!DNL CRM] dans Audience Manager, créer des segments à partir des données hors ligne et envoyer ces segments aux plateformes sociales sur lesquelles ils souhaitent faire de la publicité, à l’aide de cet identifiant haché, ce qui optimise leurs dépenses publicitaires.

Pour en savoir plus sur cette option, voir [Destinations basées sur les personnes](../destinations/people-based-destinations-overview.md).

![tous les appareils](assets/all-cross-device.png)

## Options du graphique de l’appareil {#device-graph-options}

Le choix d’une option [!UICONTROL device graph] pour une règle de [!UICONTROL Profile Merge] dépend des conditions propres à vos propriétés numériques et à vos objectifs commerciaux. Ces instructions générales peuvent vous aider à comprendre quand utiliser un type de graphique par rapport à un autre. Notez que vous devez avoir une relation contractuelle avec un graphique d’appareil externe pour utiliser ces options. Reportez-vous au tableau ci-dessous pour obtenir des instructions générales sur le choix d’une option de graphique d’appareil. Pour des cas d’utilisation spécifiques, consultez [Cas d’utilisation du graphique d’appareil Profile Link](profile-link-use-case.md) et [Cas d’utilisation du graphique d’appareil externe](external-graph-use-cases.md).

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de graphique de l’appareil </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> graphique d’appareil Profile Link</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> la fusion de profils </span> les règles créées avec l’option <span class="wintitle"> le lien de profil </span> conviennent parfaitement aux situations suivantes : </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Propriétés numériques qui présentent un haut niveau d’authentification du client. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Campagnes ciblées et de faible portée. Le graphique d’appareil <span class="wintitle"> Profile Link</span> est basé uniquement sur des données déterministes. Ce groupe de profils d’appareils sera toujours plus petit par rapport au groupe d’utilisateurs et d’appareils non authentifiés. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Cas d’utilisation où les clients doivent être dans un état authentifié pour être qualifiés pour la segmentation. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Options de graphique d’appareil externe </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> la fusion de profils </span> les règles créées avec n’importe quel graphique d’appareil externe intégré à <span class="keyword"> Audience Manager</span> conviennent parfaitement aux situations suivantes : </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Propriétés numériques ayant un faible niveau d’authentification du client. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Campagnes de marque larges et de grande portée. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Cas d’utilisation où les clients n’ont pas besoin d’être dans un état authentifié pour être qualifiés pour la segmentation. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Regardez la vidéo ci-dessous pour un aperçu des cas d’utilisation possibles de [!UICONTROL Profile Merge Rules].

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [Cas d’utilisation des représentations graphiques des appareils Profile Link](profile-link-use-case.md)
>* [Cas d’utilisation des représentations graphiques externes des appareils](external-graph-use-cases.md)
>* [FAQ sur les règles de fusion de profil](../../faq/faq-profile-merge.md)
