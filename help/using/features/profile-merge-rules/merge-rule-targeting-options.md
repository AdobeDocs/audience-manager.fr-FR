---
description: Les options des règles de fusion de profils vous permettent d’étendre ou de renforcer le ciblage de l’audience sur des audiences spécifiques en fonction des besoins ou des objectifs de l’entreprise. Ces cas d’utilisation généraux explorent comment utiliser les options disponibles et créent des règles de fusion pour le ciblage individuel, domestique et inter-périphériques.
seo-description: Les options des règles de fusion de profils vous permettent d’étendre ou de renforcer le ciblage de l’audience sur des audiences spécifiques en fonction des besoins ou des objectifs de l’entreprise. Ces cas d’utilisation généraux explorent comment utiliser les options disponibles et créent des règles de fusion pour le ciblage individuel, domestique et inter-périphériques.
seo-title: Cas d’utilisation généraux des règles de fusion de profils
solution: Audience Manager
title: Cas d’utilisation généraux des règles de fusion de profils
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
translation-type: tm+mt
source-git-commit: 532c69981ebc082bd411a9232e9ef207b59dace5

---


# Cas d’utilisation généraux des règles de fusion de profils {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] vous permet d’étendre ou de renforcer le ciblage de l’audience sur des audiences spécifiques en fonction des besoins ou des objectifs de l’entreprise. Ces cas d’utilisation généraux explorent comment utiliser les options disponibles et créent des règles de fusion pour le ciblage individuel, domestique et inter-périphériques. [!UICONTROL Profile Merge Rules] fonctionnent avec des destinations en temps réel et par lot.

>[!TIP]
>
>Pour obtenir des définitions et des descriptions de ces [!UICONTROL Merge Rule] paramètres, voir Définition [des options des règles de fusion de](merge-rule-definitions.md)profil.

## Ciblage de périphériques {#device-personalization}

Ce scénario s’applique aux spécialistes du marketing qui souhaitent évaluer un profil de périphérique unique pour un segment d’audience défini dans Audience Manager, afin de fournir une expérience cohérente au périphérique à l’aide de plateformes de ciblage prenant en charge les ID de périphérique (DSP, plateformes de personnalisation sur site et autres plateformes de ciblage basées sur un périphérique), sans tenir compte de l’authentification des utilisateurs.

Pour créer une règle qui cible uniquement les profils de périphérique, sélectionnez **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**.

![périphérique uniquement](assets/device-only.png)

Disons que John possède trois smartphones. Deux d'entre eux sont des iPhone 7 sur le plan de données A, et l'un d'eux est un Samsung sur le plan de données B. Ne prenant pas en compte son état authentifié sur l'un des trois appareils, l'opérateur de téléphonie mobile de John veut lui offrir une mise à niveau du plan de données, mais seulement pour les appareils iPhone 7 qui s'exécutent sur le plan de données A.

En utilisant la règle **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]** , [!DNL Device 1] [!DNL Device 3] et les deux sont admissibles pour le segment, tandis que le périphérique 2 est ignoré.

![périphérique uniquement](assets/device-management.png)

## Ciblage de périphériques partagés {#target-shared-devices}

Disons que John et sa femme, Jane, utilisent le même ordinateur portable pour visiter une boutique en ligne et commander divers articles.

John utilise son propre compte pour réserver des billets de voyage et des offres spéciales, tandis que Jane utilise son propre compte pour acheter de la musique et des films.

L’équipe marketing du magasin peut utiliser la règle **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** pour cibler John et Jane avec des offres spécifiques, basées uniquement sur leur activité authentifiée.

![current-no-device](assets/current-no-device.png)

En utilisant cette règle, Audience Manager ignore complètement le profil du périphérique, qualifie l’ID CRM de John pour le segment et ne qualifie pas l’ID CRM de Jane.

![ciblage de périphériques partagés](assets/shared-device-targeting.png)

## Ciblage en ligne/hors ligne {#device-household-targeting}

Ce cas d'utilisation couvre la gestion de l'identité des ménages. Une entreprise peut fusionner un profil de périphérique unique avec le dernier profil authentifié sur ce périphérique, à l’aide de la règle **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]** .

![last-device-profile](assets/last-device-profile.png)

Prenons l'exemple d'un segment constitué de ménages dont le revenu est supérieur à 100 000 $ par année, qui comprend au moins un appareil qui est un appareil [!DNL iPhone 7] de transmission [!DNL Data Plan B]. Nous avons deux profils de famille (profils inter-périphériques), chacun étant connecté à deux profils de périphériques différents. Les caractéristiques requises pour être incluses dans le segment sont distribuées sur l’ensemble des profils de périphérique et de périphérique.

Audience Manager fusionne chaque paire de profils périphérique + inter-périphériques pour déterminer si l’ensemble de caractéristiques fusionné est admissible pour le segment. Audience Manager évaluant chaque profil inclus dans la fusion, il est possible de segmenter un profil de périphérique et un profil domestique.

Le lien entre le périphérique et le profil du profil du client permet à Audience Manager de bénéficier [!DNL Household 2] du segment, mais pas [!DNL Household 1]. À partir de [!DNL Household 2], [!DNL Device 3] est uniquement admissible pour le segment. Cela [!UICONTROL Profile Merge Rule] a permis au spécialiste du marketing de diffuser un message marketing cohérent à un périphérique ([!DNL Device 3]) et à un foyer ([!DNL Household 2]) individuel.

![gestion des ménages](assets/household-management.png)

## Ciblage pour les destinations basées sur les personnes {#all-cross-device}

> [!IMPORTANT]
>
> Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans ce document n'est un conseil juridique. Veuillez consulter votre propre conseiller juridique pour obtenir des conseils juridiques.

Ce scénario de ciblage n’est disponible que pour les clients qui ont acheté le [!DNL People-Based Destinations] module complémentaire. Cette règle permet aux spécialistes du marketing d’atteindre les clients en fonction de leurs propres données authentifiées.

Supposons qu’un détaillant en ligne veuille atteindre les clients existants par le biais de plateformes sociales et leur montrer des offres personnalisées basées sur leurs commandes précédentes. Avec [!UICONTROL People-Based Destinations]cela, ils peuvent assimiler des adresses électroniques hachées de leur propre [!DNL CRM] dans Audience Manager, créer des segments à partir des données hors ligne et envoyer ces segments aux plateformes sociales sur lesquelles ils souhaitent faire de la publicité, à l’aide de cet identifiant de hachage, en optimisant leurs dépenses publicitaires.

Pour en savoir plus sur cette option, voir Destinations basées sur les [personnes](../destinations/people-based-destinations-overview.md).

![tout-périphérique](assets/all-cross-device.png)

## Options de graphique de périphérique {#device-graph-options}

Le choix d’une [!UICONTROL device graph] option pour une [!UICONTROL Profile Merge] règle dépend de conditions propres à vos propriétés numériques et à vos objectifs commerciaux. Ces directives générales peuvent vous aider à comprendre quand utiliser un type de graphique par rapport à un autre. Remarque : vous devez être membre d’ [Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) ou avoir une relation contractuelle avec un graphique de périphérique externe pour utiliser ces options. Reportez-vous au tableau ci-dessous pour obtenir des instructions générales sur le moment de choisir une option de graphique de périphérique. Pour des cas d’utilisation spécifiques, voir Cas [d’utilisation de graphiques de périphériques de lien de](profile-link-use-case.md) profil et Cas [d’utilisation de graphiques de périphériques](external-graph-use-cases.md)externes.

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de graphique de périphérique </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Graphique de périphérique de lien de profil</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Les règles de fusion</span> de profil créées avec l’option Lien <span class="wintitle"></span> de profil sont idéales pour : </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Propriétés numériques présentant un niveau élevé d’authentification du client. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Des campagnes ciblées et de faible portée. Le graphique du périphérique Lien <span class="wintitle"></span> de profil est basé sur des données déterministes uniquement. Ce pool de profils de périphériques sera toujours plus petit par rapport au pool d’utilisateurs et de périphériques non authentifiés. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Cas d’utilisation où les clients doivent être authentifiés pour pouvoir bénéficier de la segmentation. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Options graphiques de périphériques externes </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Les règles de fusion</span> de profil créées avec le <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Device Co-op</a> d’Experience Cloud ou tout graphique de périphérique externe intégré à Audience Manager <span class="keyword"></span> sont idéales pour : </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Propriétés numériques présentant un faible niveau d’authentification du client. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Campagnes de grande envergure sur les marques. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Cas d’utilisation où les clients n’ont pas besoin d’être authentifiés pour être admissibles à la segmentation. </li> 
     </ul> </p> <p> <p>Conseil : La <span class="keyword"> Device Co-op</span> est votre meilleure option si vous êtes un client <span class="keyword"> Experience Cloud</span> avec une faible authentification et aucune relation avec un fournisseur de graphiques de périphériques. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

Regardez la vidéo ci-dessous pour un aperçu des cas d'utilisation possibles pour [!UICONTROL Profile Merge Rules].

>[!VIDEO](https://video.tv.adobe.com/v/28975/?captions=fre_fr)

>[!MORE_LIKE_This]
>
>* [Cas d’utilisation de graphiques de périphériques de lien de profil](profile-link-use-case.md)
>* [Cas d’utilisation graphiques des périphériques externes](external-graph-use-cases.md)
>* [FAQ sur les règles de fusion de profils](../../faq/faq-profile-merge.md)

