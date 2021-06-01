---
description: Les options des stratégies de fusion de profils vous permettent de développer ou de renforcer le ciblage de l’audience sur des audiences spécifiques en fonction des besoins ou des objectifs de l’entreprise. Ces cas d’utilisation généraux explorent la manière d’utiliser les options disponibles et de créer des règles de fusion pour le ciblage individuel, familial et multi-appareils.
seo-description: Les options des stratégies de fusion de profils vous permettent de développer ou de renforcer le ciblage de l’audience sur des audiences spécifiques en fonction des besoins ou des objectifs de l’entreprise. Ces cas d’utilisation généraux explorent la manière d’utiliser les options disponibles et de créer des règles de fusion pour le ciblage individuel, familial et multi-appareils.
seo-title: Cas d’utilisation généraux des stratégies de fusion de profils
solution: Audience Manager
title: Cas d’utilisation généraux des stratégies de fusion de profils
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
feature: Fusion des profils
exl-id: 66341736-4f61-4306-b9f4-1b37dc7ce0ff
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '999'
ht-degree: 4%

---

# Cas d’utilisation généraux des stratégies de fusion de profils {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] les options vous permettent de développer ou de renforcer le ciblage de l’audience sur des audiences spécifiques en fonction de besoins ou d’objectifs de l’entreprise. Ces cas d’utilisation généraux explorent la manière d’utiliser les options disponibles et de créer des règles de fusion pour le ciblage individuel, familial et multi-appareils. [!UICONTROL Profile Merge Rules] fonctionne avec les destinations en temps réel et par lots.

>[!TIP]
>
>Pour obtenir des définitions et des descriptions de ces [!UICONTROL Merge Rule] paramètres, voir [Options des règles de fusion de profils définies](merge-rule-definitions.md).

## Ciblage de périphérique {#device-personalization}

Ce scénario s’applique aux marketeurs qui souhaitent évaluer un profil d’appareil unique pour un segment d’audience défini dans l’Audience Manager, afin de fournir une expérience cohérente à l’appareil à l’aide des plateformes de ciblage qui prennent en charge les identifiants d’appareil (DSP, plateformes de personnalisation sur site et autres plateformes de ciblage basées sur l’appareil), sans tenir compte de l’authentification des utilisateurs.

Pour créer une règle qui cible uniquement les profils d’appareil, sélectionnez **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**.

![appareil uniquement](assets/device-only.png)

Disons que John possède trois smartphones. Deux d&#39;entre eux sont des iPhone 7s sur le plan de données A, et l&#39;un d&#39;eux est un Samsung sur le plan de données B. Ne prenant pas en compte son état authentifié sur l&#39;un des trois appareils, l&#39;opérateur de téléphonie mobile de John veut lui proposer une mise à niveau du plan de données, mais uniquement pour les appareils iPhone 7 qui fonctionnent sur le plan de données A.

En utilisant la règle **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]** , [!DNL Device 1] et [!DNL Device 3] répondent tous deux aux critères du segment, tandis que l’appareil 2 est ignoré.

![appareil uniquement](assets/device-management.png)

## Ciblage des appareils partagés {#target-shared-devices}

Disons que John et sa femme, Jane, utilisent le même ordinateur portable pour visiter un magasin en ligne et commander divers articles.

John utilise son propre compte pour réserver des billets de voyage et des offres spéciales, tandis que Jane utilise son propre compte pour faire ses achats de musique et de films.

L’équipe marketing du magasin peut utiliser la règle **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** pour cibler John et Jane avec des offres spécifiques, en fonction uniquement de leur activité authentifiée.

![current-no-device](assets/current-no-device.png)

En utilisant cette règle, l’Audience Manager ignore complètement le profil de l’appareil, qualifie l’identifiant CRM John pour le segment et ne qualifie pas l’identifiant CRM Jane.

![shared-device-targeting](assets/shared-device-targeting.png)

## Ciblage en ligne/hors ligne {#device-household-targeting}

Ce cas d’utilisation couvre la gestion des identités des ménages. Une société peut fusionner un seul profil d’appareil avec le dernier profil authentifié sur cet appareil, à l’aide de la règle **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]** .

![last-device-profile](assets/last-device-profile.png)

Prenons l’exemple d’un segment constitué de ménages dont le revenu annuel est supérieur à 100 000 $, contenant au moins un appareil qui est [!DNL iPhone 7] sur [!DNL Data Plan B]. Nous avons deux profils domestiques (profils multi-appareils), chacun connecté à deux profils d’appareils différents. Les caractéristiques requises pour être admissible pour le segment sont réparties entre les profils de l’appareil et entre appareils.

L’Audience Manager fusionne chaque paire de profils d’appareils + multi-appareils pour voir si le jeu fusionné de caractéristiques est admissible pour le segment. Comme Audience Manager évalue chaque profil inclus dans la fusion, un profil de périphérique et un profil du foyer peuvent être segmentés.

Le lien entre l’appareil et le profil du foyer permet à l’Audience Manager de qualifier [!DNL Household 2] pour le segment, mais pas [!DNL Household 1]. À partir de [!DNL Household 2], seule [!DNL Device 3] est admissible pour le segment. Ce [!UICONTROL Profile Merge Rule] a permis au marketeur de diffuser un message marketing cohérent à un appareil ([!DNL Device 3]) et au foyer en général ([!DNL Household 2]).

![gestion des ménages](assets/household-management.png)

## Ciblage des destinations basées sur les personnes {#all-cross-device}

>[!IMPORTANT]
>
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans le présent article n&#39;est un avis juridique. Veuillez consulter votre propre service juridique pour obtenir des conseils juridiques.

Ce scénario de ciblage n’est disponible que pour les clients qui ont acheté le module complémentaire [!DNL People-Based Destinations]. Cette règle permet aux marketeurs d’atteindre des clients en fonction de leurs propres données authentifiées.

Supposons qu’un détaillant en ligne souhaite atteindre des clients existants par le biais de plateformes sociales et leur présenter des offres personnalisées basées sur ses commandes précédentes. Avec [!UICONTROL People-Based Destinations], ils peuvent ingérer des adresses électroniques hachées de leur propre [!DNL CRM] dans l’Audience Manager, créer des segments à partir des données hors ligne et envoyer ces segments aux plateformes sociales sur lesquelles ils souhaitent faire de la publicité, à l’aide de cet identifiant haché, optimisant ainsi leurs dépenses publicitaires.

Pour en savoir plus sur cette option, voir [Destinations basées sur les personnes](../destinations/people-based-destinations-overview.md).

![sur plusieurs appareils](assets/all-cross-device.png)

## Options de Device Graph {#device-graph-options}

Le choix d’une option [!UICONTROL device graph] pour une règle [!UICONTROL Profile Merge] dépend de conditions propres à vos propriétés numériques et à vos objectifs commerciaux. Ces instructions générales peuvent vous aider à savoir quand utiliser un type de graphique ou un autre. Notez que vous devez être membre de [Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/fr-FR/device-co-op/using/home.html) ou avoir une relation contractuelle avec un graphique d’appareil externe pour utiliser ces options. Reportez-vous au tableau ci-dessous pour obtenir des instructions générales sur le choix d’une option de représentation graphique des appareils. Pour des cas d’utilisation spécifiques, voir [Cas d’utilisation des représentations graphiques des appareils Profile Link](profile-link-use-case.md) et [Cas d’utilisation des représentations graphiques externes des appareils](external-graph-use-cases.md).

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
   <td colname="col2"> <p><span class="wintitle"> Les </span> règles de fusion de profils créées avec l’option de  <span class="wintitle"> liaison de </span> profils sont idéales pour : </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Propriétés numériques présentant un niveau élevé d’authentification du client. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Des campagnes ciblées et de faible portée. Le graphique d’appareil <span class="wintitle"> Profile Link</span> repose uniquement sur des données déterministes. Ce groupe de profils d’appareils sera toujours plus petit par rapport au groupe d’utilisateurs et de périphériques non authentifiés. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Cas d’utilisation où les clients doivent se trouver dans un état authentifié pour être admissibles à la segmentation. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Options de représentation graphique des appareils externes </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Les </span> règles de profil créées avec  <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud Device Co-</a>  ou toute représentation graphique externe des appareils intégrée à  <span class="keyword"> Audience </span> Manager sont idéales pour : </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Propriétés numériques présentant un faible niveau d’authentification du client. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Campagnes de marque de grande envergure. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Cas d’utilisation où les clients n’ont pas besoin d’être authentifiés pour être admissibles à la segmentation. </li> 
     </ul> </p> <p> <p>Conseil : <span class="keyword"> Device Co-op</span> est votre meilleure option si vous êtes un client <span class="keyword"> Experience Cloud</span> avec une authentification faible et aucune relation avec un fournisseur de graphiques d’appareil. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

Regardez la vidéo ci-dessous pour un aperçu des cas d’utilisation possibles pour [!UICONTROL Profile Merge Rules].

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [Cas d’utilisation des représentations graphiques des appareils Profile Link](profile-link-use-case.md)
* [Cas d’utilisation des représentations graphiques externes des appareils](external-graph-use-cases.md)
* [FAQ sur les règles de fusion de profils](../../faq/faq-profile-merge.md)

