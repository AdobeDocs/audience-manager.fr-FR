---
description: Les options  Fusionner les règles vous permettent d’étendre ou de resserrer  de se concentrer sur desspécifiques en fonction des besoins ou des objectifs de l’entreprise. Ces cas d’utilisation généraux explorent comment utiliser les options disponibles et créent des règles de fusion pour le ciblage individuel, domestique et inter-périphériques.
seo-description: Les options  Fusionner les règles vous permettent d’étendre ou de resserrer  de se concentrer sur desspécifiques en fonction des besoins ou des objectifs de l’entreprise. Ces cas d’utilisation généraux explorent comment utiliser les options disponibles et créent des règles de fusion pour le ciblage individuel, domestique et inter-périphériques.
seo-title: 'Cas d’utilisation généraux pour les règles de fusion '
solution: Audience Manager
title: 'Cas d’utilisation généraux pour les règles de fusion '
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
translation-type: tm+mt
source-git-commit: 75fe1e0f7321107930a28e354ca2f4a256a477ac

---


# Cas d’utilisation généraux pour les règles de fusion {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] vous permet d’étendre ou de resserrer   vous concentrer sur des  spécifiques en fonction des besoins ou des objectifs de l’entreprise. Ces cas d’utilisation généraux explorent comment utiliser les options disponibles et créent des règles de fusion pour le ciblage individuel, domestique et inter-périphériques. [!UICONTROL Profile Merge Rules] fonctionnent avec des destinations en temps réel et par lot.

>[!TIP]
>
>Pour obtenir des définitions et des descriptions de ces [!UICONTROL Merge Rule] paramètres, reportez-vous à la section Définition [des options des règles de fusion des de](merge-rule-definitions.md).

## Ciblage de périphériques {#device-personalization}

Ce scénario s’applique aux spécialistes du marketing qui souhaitent évaluer un  de périphérique unique pour un segment  de défini dans le Gestionnaire de de, afin de fournir une expérience cohérente au périphérique à l’aide de plateformes de ciblage prenant en charge les identifiants de périphérique (DSP, plateformes de personnalisation sur site et autres plateformes de ciblage basées sur un périphérique), sans tenir compte de l’authentification des utilisateurs.

Pour créer une règle qui ne  que le de périphérique, sélectionnez **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**.

![périphérique uniquement](assets/device-only.png)

Disons que John possède trois smartphones. Deux d&#39;entre eux sont des iPhone 7 sur le plan de données A, et l&#39;un d&#39;eux est un Samsung sur le plan de données B. Ne prenant pas en compte son état authentifié sur l&#39;un des trois appareils, l&#39;opérateur de téléphonie mobile de John veut  lui  une mise à niveau du plan de données, mais seulement pour les appareils iPhone 7 qui s&#39;exécutent sur le plan de données A.

En utilisant la règle **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]** , [!DNL Device 1] [!DNL Device 3] et les deux sont admissibles pour le segment, tandis que le périphérique 2 est ignoré.

![périphérique uniquement](assets/device-management.png)

## Ciblage de périphériques partagés {#target-shared-devices}

Disons que John et sa femme, Jane, utilisent le même ordinateur portable pour visiter une boutique en ligne et commander divers articles.

John utilise son propre compte pour réserver des billets de voyage et des offres spéciales, tandis que Jane utilise son propre compte pour acheter de la musique et des films.

L’équipe marketing du magasin peut utiliser la règle **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** pour  John et Jane avec des transactions spécifiques, basées uniquement sur leurs  authentifiés.

![current-no-device](assets/current-no-device.png)

En utilisant cette règle,  Gestionnaire de  ignore complètement l’de périphérique, qualifie l’ID de gestion de la relation client John pour le segment et non l’ID de gestion de la relation client Jane.

![ciblage de périphériques partagés](assets/shared-device-targeting.png)

## Ciblage en ligne/hors ligne {#device-household-targeting}

Ce cas d&#39;utilisation couvre la gestion de l&#39;identité des ménages. Un peut fusionner un seul de périphérique  avec le dernier  de périphérique authentifié sur ce périphérique, à l’aide de la règle **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]** .

![last-device-](assets/last-device-profile.png)

Prenons l&#39;exemple d&#39;un segment constitué de ménages dont le revenu est supérieur à 100 000 $ par année, qui comprend au moins un appareil qui est un appareil [!DNL iPhone 7] de transmission [!DNL Data Plan B]. Nous avons deux  domestiques (inter-périphériques), chacune étant connectée à deuxdifférents dispositifs. Les caractéristiques requises pour être incluses dans le segment sont distribuées sur l’ensemble du périphérique et du sur plusieurs périphériques.

 Gestionnaire de  de fusionne chaque paire de périphérique + multipériphérique pour déterminer si le jeu de caractéristiques fusionné est admissible pour le segment.  Gestionnaire  de évalue chaque inclus dans la fusion. Il est donc possible de segmenter à la fois un de périphérique et un domestique.

Le lien entre le périphérique et le  de domestique permet à  Gestionnaire de  de bénéficier [!DNL Household 2] du segment, mais pas [!DNL Household 1]. À partir de [!DNL Household 2], [!DNL Device 3] est uniquement admissible pour le segment. Cela [!UICONTROL Profile Merge Rule] a permis au spécialiste du marketing de diffuser un message marketing cohérent à un périphérique ([!DNL Device 3]) et à un foyer ([!DNL Household 2]) individuel.

![gestion des ménages](assets/household-management.png)

## Ciblage pour les destinations basées sur les personnes {#all-cross-device}

>[!IMPORTANT]
>
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans ce document n&#39;est un conseil juridique. Veuillez consulter votre propre conseiller juridique pour obtenir des conseils juridiques.

Ce scénario de ciblage n’est disponible que pour les clients qui ont acheté le [!DNL People-Based Destinations] module complémentaire. Cette règle permet aux spécialistes du marketing d’atteindre les clients en fonction de leurs propres données authentifiées.

Supposons qu’un détaillant en ligne veuille contacter des clients existants par le biais de plateformes sociales et leur montrer des  personnalisés en fonction de leurs commandes précédentes. Avec [!UICONTROL People-Based Destinations]cela, ils peuvent assimiler des adresses électroniques hachées de leur propre [!DNL CRM] dans  Gestionnaire de , créer des segments à partir des données hors ligne et envoyer ces segments aux plateformes sociales sur lesquelles ils veulent faire de la publicité, en utilisant cet identifiant haché, ce qui optimise leurs dépenses publicitaires.

Pour en savoir plus sur cette option, voir Destinations basées sur les [personnes](../destinations/people-based-destinations-overview.md).

![tout-périphérique](assets/all-cross-device.png)

## Options de graphique de périphérique {#device-graph-options}

Le choix d’une [!UICONTROL device graph] option pour une [!UICONTROL Profile Merge] règle dépend de conditions propres à vos propriétés numériques et à vos objectifs commerciaux. Ces directives générales peuvent vous aider à comprendre quand utiliser un type de graphique par rapport à un autre. Remarque : vous devez être membre d’ [Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) ou avoir une relation contractuelle avec un graphique de périphérique externe pour utiliser ces options. Reportez-vous au tableau ci-dessous pour obtenir des instructions générales sur le moment de choisir une option de graphique de périphérique. Pour des cas d’utilisation spécifiques, voir Cas [d’utilisation des graphiques de périphériques de liaison  Cas](profile-link-use-case.md) d’utilisation des graphiques de périphériques [externes et Cas](external-graph-use-cases.md)d’utilisation des graphiques de périphériquesexternes.

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de graphique de périphérique </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Graphique du périphérique de lien de</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Les règles de fusion</span>  créées avec l’option de lien <span class="wintitle"></span>  sont idéales pour : </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Propriétés numériques présentant un niveau élevé d’authentification du client. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Des campagnes ciblées et de faible portée. Le graphique du périphérique Lien <span class="wintitle"></span> de est construit uniquement sur des données déterministes. Ce pool de de périphériques sera toujours plus petit par rapport au pool d’utilisateurs et de périphériques non authentifiés. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Cas d’utilisation où les clients doivent être authentifiés pour pouvoir bénéficier de la segmentation. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Options graphiques de périphériques externes </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Les règles de fusion</span> des  créées avec <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Experience Cloud Device Co-op</a> ou tout graphique de périphérique externe intégré à <span class="keyword">  Manager</span> sont idéales pour : </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Propriétés numériques présentant un faible niveau d’authentification du client. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Campagnes de grande envergure sur les marques. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Cas d’utilisation où les clients n’ont pas besoin d’être authentifiés pour être admissibles à la segmentation. </li> 
     </ul> </p> <p> <p>Conseil : La <span class="keyword"> Device Co-op</span> est votre meilleure option si vous êtes un client <span class="keyword"> Experience Cloud</span> avec une faible authentification et aucune relation avec un fournisseur de graphiques de périphériques. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

Regardez la vidéo ci-dessous pour un aperçu des cas d&#39;utilisation possibles pour [!UICONTROL Profile Merge Rules].

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [Cas d&#39;utilisation de graphiques de périphériques de lien](profile-link-use-case.md)
>* [Cas d’utilisation graphiques des périphériques externes](external-graph-use-cases.md)
>* [FAQ sur les règles de fusion](../../faq/faq-profile-merge.md)

