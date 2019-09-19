---
description: Les options des règles de fusion de profils vous permettent d’étendre ou de renforcer le ciblage de l’audience sur des audiences spécifiques en fonction des besoins ou des objectifs de l’entreprise. Ces cas d’utilisation généraux explorent comment utiliser les options disponibles et créent des règles de fusion pour le ciblage individuel, domestique et inter-périphériques. Actuellement, les règles de fusion de profils fonctionnent uniquement avec les destinations en temps réel.
seo-description: Les options des règles de fusion de profils vous permettent d’étendre ou de renforcer le ciblage de l’audience sur des audiences spécifiques en fonction des besoins ou des objectifs de l’entreprise. Ces cas d’utilisation généraux explorent comment utiliser les options disponibles et créent des règles de fusion pour le ciblage individuel, domestique et inter-périphériques. Actuellement, les règles de fusion de profils fonctionnent uniquement avec les destinations en temps réel.
seo-title: Cas d’utilisation généraux des règles de fusion de profils
solution: Audience Manager
title: Cas d’utilisation généraux des règles de fusion de profils
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Cas d’utilisation généraux des règles de fusion de profils {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] vous permet d’étendre ou de renforcer le ciblage de l’audience sur des audiences spécifiques en fonction des besoins ou des objectifs de l’entreprise. Ces cas d’utilisation généraux explorent comment utiliser les options disponibles et créent des règles de fusion pour le ciblage individuel, domestique et inter-périphériques. Actuellement, [!UICONTROL Profile Merge Rules] utilisez uniquement des destinations en temps réel.

![](assets/merge-rules-options.png)

>[!TIP]
>
>Pour obtenir des définitions et des descriptions de ces [!UICONTROL Merge Rule] paramètres, voir Définition [des options des règles de fusion de](../../features/profile-merge-rules/merge-rule-definitions.md)profil.

## Ciblage ciblé {#focused-targeting}

L’authentification de l’utilisateur sur un site Web doit déclencher un appel d’ID déclaré à [!DNL Audience Manager]. Après cet événement, [!DNL Audience Manager] écrit les données de caractéristique dans (et lit à partir de) un profil authentifié. Le profil authentifié permet [!DNL Audience Manager]:

* Ecrivez des caractéristiques dans le profil authentifié spécifique à un utilisateur particulier.
* Identifier et différencier plusieurs utilisateurs de périphériques pour la segmentation.

### Atteindre les utilisateurs authentifiés

Les options de profil authentifiées créent des règles qui vous permettent de cibler les utilisateurs connectés à un site Web ou une application en fonction d’attributs hors ligne. Par exemple, une société de services financiers utiliserait cette option pour cibler les utilisateurs authentifiés avec des offres de mise à niveau de carte de crédit ciblées ou des offres de service spécialisées basées sur les revenus ou l’activité hors ligne. Un autre exemple serait une compagnie aérienne ciblant les vols fréquents authentifiés avec des transactions basées sur le kilométrage cumulé.

Pour créer une règle qui n’atteint que les utilisateurs authentifiés, sélectionnez **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL No Device Profile]**. Cette option évalue un segment en utilisant uniquement des données de profil authentifiées. Cette règle ignore les données du profil de périphérique anonyme.

Pour inclure également des données dans le profil de périphérique anonyme, utilisez la règle **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL Current Device Profile]** .

### Atteindre les utilisateurs en fonction de l’état d’authentification précédent

Ces options atteignent des utilisateurs spécifiques lorsqu’ils naviguent mais ne sont pas connectés. Pour ce faire, vous pouvez utiliser des options reposant sur un ciblage au niveau de l’utilisateur. Le ciblage implicite permet d’atteindre des personnes qui ne sont pas explicitement authentifiées sur votre site mais qui peuvent naviguer en ligne. Il fonctionne en lisant (mais pas en écrivant) les données du dernier profil authentifié. Et, pour préserver la propreté du profil authentifié, [!DNL Audience Manager] écrit de nouvelles qualifications de caractéristiques dans le profil du périphérique au lieu du profil authentifié. Supposons, par exemple, que vous soyez un spécialiste du marketing qui souhaite tester différentes offres auprès de clients existants qui ne sont pas connectés à votre site ou application. En tant que spécialiste du marketing, vous pouvez tester ces publicités avec des clients actuels non authentifiés afin de déterminer les offres qui obtiennent le plus de réponses.

Voici un exemple de règle qui parvient aux utilisateurs en fonction de l’authentification précédente :

* **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Current Device Profile]**

## Ciblage étendu {#expanded-targeting}

Outre les règles qui aident des clients spécifiques, les marketeurs ont également besoin de règles qui augmentent la taille des jeux de données disponibles pour le ciblage. [!UICONTROL Profile Merge Rules] vous permet de le faire avec l’option de profil de périphérique. Les options de périphérique permettent d’étendre l’ensemble de données éligible à la segmentation, car elles reposent sur des caractéristiques réalisées lorsqu’un utilisateur se trouvait dans un état anonyme sur un ou plusieurs périphériques. Cela peut s’avérer utile lorsque vous tentez d’atteindre un utilisateur sur tous ses appareils à l’aide d’un graphique de périphériques personnels ou de tous les appareils d’un ménage à l’aide d’un graphique de périphériques ménagers. Cette option peut être utilisée avec la publicité d’une offre de vacances en famille. Dans ce cas, vous souhaiterez atteindre chaque périphérique d’un foyer avec l’offre si un utilisateur de n’importe quel périphérique a manifesté son intérêt pour l’offre.

Pour créer une règle qui développe le jeu de données de ciblage, sélectionnez la règle **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Graph]** .

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

## Options de graphique de périphérique {#device-graph-options}

Le choix d’une [!UICONTROL device graph] option pour une [!UICONTROL Profile Merge] règle dépend de conditions propres à vos propriétés numériques et à vos objectifs commerciaux. Ces directives générales peuvent vous aider à comprendre quand utiliser un type de graphique par rapport à un autre. Notez que vous devez être membre du [!DNL Adobe Experience Cloud Device Co-op] ou avoir une relation contractuelle avec un graphique de périphérique externe pour utiliser ces options. Reportez-vous au tableau ci-dessous pour obtenir des instructions générales sur le moment de choisir une option de graphique de périphérique. Pour des cas d’utilisation spécifiques, voir Cas [d’utilisation de graphiques de périphériques de lien de](../../features/profile-merge-rules/profile-link-use-case.md) profil et Cas [d’utilisation de graphiques de périphériques](../../features/profile-merge-rules/external-graph-use-cases.md)externes.

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

>[!MORE_LIKE_This]
>
>* [Cas d’utilisation de graphiques de périphériques de lien de profil](../../features/profile-merge-rules/profile-link-use-case.md)
>* [Cas d’utilisation graphiques des périphériques externes](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [FAQ sur les règles de fusion de profils](../../faq/faq-profile-merge.md)

