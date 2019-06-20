---
description: Les options Règles de fusion de profils vous permettent de développer ou de renforcer la cible d'action sur des audiences spécifiques en fonction des besoins ou objectifs commerciaux. Ces cas d'utilisation généraux expliquent comment utiliser les options disponibles et créer des règles de fusion pour le ciblage individuel, domestique et inter-périphériques. Actuellement, les règles de fusion de profils fonctionnent avec les destinations en temps réel uniquement.
seo-description: Les options Règles de fusion de profils vous permettent de développer ou de renforcer la cible d'action sur des audiences spécifiques en fonction des besoins ou objectifs commerciaux. Ces cas d'utilisation généraux expliquent comment utiliser les options disponibles et créer des règles de fusion pour le ciblage individuel, domestique et inter-périphériques. Actuellement, les règles de fusion de profils fonctionnent avec les destinations en temps réel uniquement.
seo-title: Cas d'utilisation général pour les règles de fusion de profils
solution: Audience Manager
title: Cas d'utilisation général pour les règles de fusion de profils
uuid: c 9 eb 41 c 8-fe 19-45 f 8-9 ff 1-552 c 11 ef 08 da
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# General Use Cases for Profile Merge Rules {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] vous permettent de développer ou de renforcer la cible d&#39;action sur des audiences spécifiques en fonction des besoins ou objectifs commerciaux. Ces cas d&#39;utilisation généraux expliquent comment utiliser les options disponibles et créer des règles de fusion pour le ciblage individuel, domestique et inter-périphériques. [!UICONTROL Profile Merge Rules] Actuellement, travaillez avec des destinations en temps réel uniquement.

![](assets/merge-rules-options.png)

>[!TIP]
>
>For definitions and descriptions of these [!UICONTROL Merge Rule] settings, see [Profile Merge Rule Options Defined](../../features/profile-merge-rules/merge-rule-definitions.md).

## Focused targeting {#focused-targeting}

User authentication to a website should trigger a declared ID call to [!DNL Audience Manager]. After this event, [!DNL Audience Manager] writes trait data to (and reads from) an authenticated profile. The authenticated profile lets [!DNL Audience Manager]:

* Ecrivez des caractéristiques au profil authentifié propre à un utilisateur particulier.
* Identifiez et faites la distinction entre plusieurs utilisateurs de périphériques pour la segmentation.

### Portée des utilisateurs authentifiés

Les options de profil authentifiées créent des règles qui vous permettent de cibler les utilisateurs qui sont connectés à un site Web ou à une application en fonction d&#39;attributs hors ligne. Par exemple, une société de services financiers utilise cette option pour cibler les utilisateurs authentifiés avec des offres de mise à niveau de carte de crédit ciblées ou des offres de service spécialisées basées sur le revenu ou l&#39;activité hors ligne. Un autre exemple consisterait à cibler les frégates fréquemment authentifiées avec des offres basées sur le kilométrage cumulé.

To create a rule that reaches only authenticated users, select **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL No Device Profile]**. Cette option évaluera un segment en utilisant uniquement des données de profil authentifiées. Cette règle ignore les données du profil de périphérique anonyme.

To also include data in the anonymous device profile, use the **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL Current Device Profile]** rule.

### Atteindre les utilisateurs selon l&#39;état d&#39;authentification précédent

Ces options atteignent des utilisateurs spécifiques lorsqu&#39;ils naviguent sur le site mais qu&#39;ils ne sont pas connectés. Vous pouvez le faire avec des options basées sur le ciblage au niveau de l&#39;utilisateur supposé. Le ciblage supposé permet d&#39;atteindre les personnes qui ne sont pas authentifiées explicitement sur votre site mais qui peuvent être en ligne. Elle fonctionne en lisant (mais pas en écrivant) les données du dernier profil authentifié. And, to help keep the authenticated profile clean, [!DNL Audience Manager] writes new trait qualifications to the device profile instead of the authenticated profile. Supposons, par exemple, que vous soyez un spécialiste du marketing qui souhaite tester différentes offres avec des clients existants qui ne sont pas connectés à votre site ou à votre application. En tant que spécialiste du marketing, vous pouvez tester ces annonces auprès des clients actuels non authentifiés pour identifier les offres qui obtiennent le plus de réponse.

Voici un exemple de règle qui atteint les utilisateurs selon l&#39;authentification prédictionnelle :

* **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Current Device Profile]**

## Expanded targeting {#expanded-targeting}

Outre les règles qui permettent d&#39;atteindre des clients spécifiques, les marketeurs ont également besoin de règles qui augmentent la taille des ensembles de données disponibles pour le ciblage. [!UICONTROL Profile Merge Rules] vous permet de le faire avec l&#39;option de profil de périphérique. Les options de périphérique étendent l&#39;ensemble de données éligible à la segmentation, car elles tirent parti des caractéristiques réalisées lorsqu&#39;un utilisateur se trouvait dans un état anonyme sur un ou plusieurs périphériques. Cela peut s&#39;avérer utile lorsque vous tentez d&#39;atteindre un utilisateur sur l&#39;ensemble de son appareil à l&#39;aide d&#39;un graphique de périphérique individuel ou de tous les périphériques d&#39;un foyer à l&#39;aide d&#39;un graphique de périphérique ménager. Cette option peut inclure la publicité d&#39;une offre de vacances familiale. Dans ce cas, vous souhaitez atteindre chaque périphérique d&#39;un foyer avec l&#39;offre si un utilisateur sur n&#39;importe quel périphérique a manifesté un intérêt pour l&#39;offre.

To create a rule that expands the targeting data set, select the **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Graph]** rule.

<!-- 

<p>Rules that use the device graph option extend your data set even further. With the device graph option, <span class="keyword"> Audience Manager</span> relies on the device profiles aggregated from the last 3 devices that a visitor used for authentication to your site. The device graph rules include: </p> 
<p> 
 <ul id="ul_3008B6AF16EC408F98EC4088111281FB"> 
  <li id="li_FA2087F1ED454CD0B9E09656B79ED23B"> <b><span class="uicontrol"> Current Authenticated Profiles</span></b> + <b><span class="uicontrol"> Profile Merge Device Graph</span></b> or a Co-op device graph option </li> 
  <li id="li_001A8DB517CB4EE394DBD530F2080FD5"> <b><span class="uicontrol"> Last Authenticated Profiles</span></b> + <b><span class="uicontrol"> Profile Merge Device Graph</span></b> or a Co-op device graph option </li> 
 </ul> </p> 
<p> 
 <note type="tip">
  Create a simple rule with 
  <b><span class="uicontrol"> No Authenticated Profile</span></b> + 
  <b><span class="uicontrol"> Current Device Profile</span></b> when you're still developing a strategy and are unsure about which options to choose or if your site doesn't use authentication. 
 </note> </p>

 -->

## Device Graph Options {#device-graph-options}

Choosing a [!UICONTROL device graph] option for a [!UICONTROL Profile Merge] rule depends on conditions unique to your digital properties and business goals. Ces instructions générales peuvent vous aider à comprendre quand utiliser un type de graphique par rapport à un autre. Note, you must be a member of the [!DNL Adobe Experience Cloud Device Co-op] or have a contractual relationship with an external device graph to use these options. Reportez-vous au tableau ci-dessous pour obtenir des instructions générales sur le moment auquel choisir un graphique de périphérique. For specific use cases, see [Profile Link Device Graph Use Cases](../../features/profile-merge-rules/profile-link-use-case.md) and [External Device Graph Use Cases](../../features/profile-merge-rules/external-graph-use-cases.md).

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de graphique de périphérique </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Profile Link</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Les règles de fusion</span> de profils créées avec l' <span class="wintitle"> option Link Link</span> sont parfaites pour : </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Propriétés numériques qui présentent un haut niveau d'authentification des clients. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Campagnes ciblées et ciblées. The <span class="wintitle"> Profile Link</span> device graph is built on deterministic data only. Ce pool de profils de périphérique sera toujours plus petit par rapport au pool d'utilisateurs et de périphériques non authentifiés. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Cas où les clients doivent être dans un état authentifié pour bénéficier de la segmentation. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Options graphiques de périphérique externe </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Les règles de fusion</span> de profils créées avec <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> le Device Cloud Device Co-op</a> ou tout graphique de périphérique externe intégré <span class="keyword"> à Audience Manager</span> sont parfaites pour : </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Propriétés numériques ayant un faible niveau d'authentification des clients. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Des campagnes de marque large et large. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Cas où les clients n'ont pas besoin d'être dans un état authentifié pour bénéficier de la segmentation. </li> 
     </ul> </p> <p> <p>Tip: The <span class="keyword"> Device Co-op</span> is your best option if you're a <span class="keyword"> Experience Cloud</span> customer with low authentication and no relationship with any device graph provider. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Cas d&#39;utilisation du graphique de périphérique de lien de profil](../../features/profile-merge-rules/profile-link-use-case.md)
>* [Cas d’utilisation graphiques des périphériques externes](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [FAQ sur la fusion des profils](../../faq/faq-profile-merge.md)

