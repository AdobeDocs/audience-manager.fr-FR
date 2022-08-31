---
description: Les options des stratégies de fusion de profils vous permettent de développer ou de renforcer le ciblage de l’audience sur des audiences spécifiques en fonction des besoins ou des objectifs de l’entreprise. Ces cas d’utilisation généraux explorent la manière d’utiliser les options disponibles et de créer des règles de fusion pour le ciblage individuel, familial et multi-appareils.
seo-description: Profile Merge Rules options let you expand or tighten audience focus on specific audiences based on business needs or goals. These general use cases explore how to use available options and create merge rules for individual, household, and cross-device targeting.
seo-title: General Use Cases for Profile Merge Rules
solution: Audience Manager
title: Cas d’utilisation généraux des stratégies de fusion de profils
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
feature: Profile Merge
exl-id: 66341736-4f61-4306-b9f4-1b37dc7ce0ff
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 2%

---

# Cas d’utilisation généraux des stratégies de fusion de profils {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] les options vous permettent de développer ou de renforcer le ciblage de l’audience sur des audiences spécifiques en fonction de besoins ou d’objectifs de l’entreprise. Ces cas d’utilisation généraux explorent la manière d’utiliser les options disponibles et de créer des règles de fusion pour le ciblage individuel, familial et multi-appareils. [!UICONTROL Profile Merge Rules] fonctionne avec les destinations en temps réel et par lots.

>[!TIP]
>
>Pour connaître les définitions et les descriptions de ces éléments [!UICONTROL Merge Rule] paramètres, voir [Définition des options des règles de fusion de profils](merge-rule-definitions.md).

## Ciblage des périphériques {#device-personalization}

Ce scénario s’applique aux marketeurs qui souhaitent évaluer un profil d’appareil unique pour un segment d’audience défini dans l’Audience Manager, afin de fournir une expérience cohérente à l’appareil à l’aide des plateformes de ciblage qui prennent en charge les identifiants d’appareil (DSP, plateformes de personnalisation sur site et autres plateformes de ciblage basées sur l’appareil), sans tenir compte de l’authentification des utilisateurs.

Pour créer une règle qui cible uniquement les profils d’appareil, sélectionnez **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**.

![appareil uniquement](assets/device-only.png)

Disons que John possède trois smartphones. Deux d’entre eux sont iPhone 7s sur le plan de données A, et l’un d’eux est un Samsung sur le plan de données B. Ne prenant pas en compte son état authentifié sur l’un des trois appareils, l’opérateur de téléphonie mobile de John souhaite lui proposer une mise à niveau du plan de données, mais uniquement pour les appareils iPhone 7 qui s’exécutent sur le plan de données A.

En utilisant la variable **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]** règle, [!DNL Device 1] et [!DNL Device 3] tous deux correspondent au segment, tandis que l’appareil 2 est ignoré.

![appareil uniquement](assets/device-management.png)

## Ciblage des périphériques partagés {#target-shared-devices}

Disons que John et sa femme, Jane, utilisent le même ordinateur portable pour visiter un magasin en ligne et commander divers articles.

John utilise son propre compte pour réserver des billets de voyage et des offres spéciales, tandis que Jane utilise son propre compte pour faire ses achats de musique et de films.

L’équipe marketing du magasin peut utiliser la variable **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** règle pour cibler John et Jane avec des offres spécifiques, basées uniquement sur leur activité authentifiée.

![current-no-device](assets/current-no-device.png)

En utilisant cette règle, l’Audience Manager ignore complètement le profil de l’appareil, qualifie l’identifiant CRM John pour le segment et ne qualifie pas l’identifiant CRM Jane.

![shared-device-targeting](assets/shared-device-targeting.png)

## Ciblage en ligne/hors ligne {#device-household-targeting}

Ce cas d’utilisation couvre la gestion des identités des ménages. Une entreprise peut fusionner un profil de périphérique unique avec le dernier profil authentifié sur ce périphérique, à l’aide de la variable **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]** règle.

![last-device-profile](assets/last-device-profile.png)

Prenons l’exemple d’un segment constitué de ménages dont le revenu est supérieur à 100 000 $ par an, contenant au moins un appareil qui est une [!DNL iPhone 7] on [!DNL Data Plan B]. Nous avons deux profils domestiques (profils multi-appareils), chacun connecté à deux profils d’appareils différents. Les caractéristiques requises pour être admissible pour le segment sont réparties entre les profils de l’appareil et entre appareils.

L’Audience Manager fusionne chaque paire de profils d’appareils + multi-appareils pour voir si le jeu fusionné de caractéristiques est admissible pour le segment. Comme Audience Manager évalue chaque profil inclus dans la fusion, un profil de périphérique et un profil du foyer peuvent être segmentés.

Le lien entre l’appareil et le profil du foyer permet à l’Audience Manager de remplir les conditions requises. [!DNL Household 2] pour le segment, mais pas [!DNL Household 1]. De [!DNL Household 2], uniquement [!DNL Device 3] est admissible pour le segment. Ceci [!UICONTROL Profile Merge Rule] a permis au marketeur de diffuser un message marketing cohérent à un appareil individuel ([!DNL Device 3]) et le ménage au sens large ([!DNL Household 2]).

![gestion des ménages](assets/household-management.png)

## Ciblage des destinations basées sur les personnes {#all-cross-device}

>[!IMPORTANT]
>
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans le présent article n&#39;est un avis juridique. Veuillez consulter votre propre service juridique pour obtenir des conseils juridiques.

Ce scénario de ciblage n’est disponible que pour les clients qui ont acheté la variable [!DNL People-Based Destinations] module complémentaire . Cette règle permet aux marketeurs d’atteindre des clients en fonction de leurs propres données authentifiées.

Supposons qu’un détaillant en ligne souhaite atteindre des clients existants par le biais de plateformes sociales et leur présenter des offres personnalisées basées sur ses commandes précédentes. Avec [!UICONTROL People-Based Destinations], ils peuvent ingérer des adresses électroniques hachées depuis leur propre [!DNL CRM] dans Audience Manager, créez des segments à partir des données hors ligne et envoyez ces segments aux plateformes sociales sur lesquelles ils souhaitent faire de la publicité, à l’aide de cet identifiant haché, en optimisant leurs dépenses publicitaires.

Pour en savoir plus sur cette option, voir [Destinations basées sur les personnes](../destinations/people-based-destinations-overview.md).

![sur plusieurs appareils](assets/all-cross-device.png)

## Options de Device Graph {#device-graph-options}

Choix d’une [!UICONTROL device graph] pour une [!UICONTROL Profile Merge] dépend de conditions propres à vos propriétés numériques et à vos objectifs métier. Ces instructions générales peuvent vous aider à savoir quand utiliser un type de graphique ou un autre. Notez que vous devez avoir une relation contractuelle avec une représentation graphique externe des appareils pour utiliser ces options. Reportez-vous au tableau ci-dessous pour obtenir des instructions générales sur le choix d’une option de représentation graphique des appareils. Pour consulter des cas d’utilisation spécifiques, voir [Cas d’utilisation des représentations graphiques des appareils Profile Link](profile-link-use-case.md) et [Cas d’utilisation graphiques des appareils externes](external-graph-use-cases.md).

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de graphique de périphérique </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Graphique du périphérique du lien de profil</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Fusion des profils</span> règles créées à l’aide de <span class="wintitle"> Lien de profil</span> sont idéales pour : </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Propriétés numériques présentant un niveau élevé d’authentification du client. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Des campagnes ciblées et de faible portée. Le <span class="wintitle"> Lien de profil</span> La représentation graphique des appareils repose uniquement sur des données déterministes. Ce groupe de profils d’appareils sera toujours plus petit par rapport au groupe d’utilisateurs et de périphériques non authentifiés. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Cas d’utilisation où les clients doivent se trouver dans un état authentifié pour être admissibles à la segmentation. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Options de représentation graphique des appareils externes </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Fusion des profils</span> règles créées avec n’importe quel graphique d’appareil externe intégré à <span class="keyword"> Audience Manager</span> sont idéales pour : </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Propriétés numériques présentant un faible niveau d’authentification du client. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Campagnes de marque de grande envergure. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Cas d’utilisation où les clients n’ont pas besoin d’être authentifiés pour être admissibles à la segmentation. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Regardez la vidéo ci-dessous pour un aperçu des cas d’utilisation possibles pour [!UICONTROL Profile Merge Rules].

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [Cas d’utilisation des représentations graphiques des appareils Profile Link](profile-link-use-case.md)
>* [Cas d’utilisation des représentations graphiques externes des appareils](external-graph-use-cases.md)
>* [FAQ sur les règles de fusion de profils](../../faq/faq-profile-merge.md)

