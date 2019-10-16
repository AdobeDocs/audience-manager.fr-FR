---
description: Les règles de fusion de profils vous permettent de contrôler les jeux de données utilisés pour la segmentation et de cibler une personne avec précision sur plusieurs périphériques.
seo-description: Les règles de fusion de profils vous permettent de contrôler les jeux de données utilisés pour la segmentation et de cibler une personne avec précision sur plusieurs périphériques.
seo-title: Présentation des règles de fusion de profils
solution: Audience Manager
title: Présentation des règles de fusion de profils
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# Présentation des règles de fusion de profils {#profile-merge-rules-overview}

Vous [!UICONTROL Profile Merge Rules] pouvez ainsi contrôler quels jeux de données sont utilisés pour la segmentation et cibler précisément les utilisateurs sur plusieurs périphériques.

>[!VIDEO](https://video.tv.adobe.com/v/28974?captions=fre_fr)

## Collecte et ciblage de données avec des profils anonymes et authentifiés {#data-collection-targeting}

En règle générale, la segmentation et le ciblage de l’audience reposent sur les données collectées auprès de tous les utilisateurs sur un périphérique. La collecte et le ciblage des données en fonction des données au niveau du périphérique présentent certains inconvénients. Par exemple, vous ne pouvez pas faire la distinction entre plusieurs utilisateurs qui partagent un périphérique ou ciblent précisément des utilisateurs sur plusieurs périphériques. La collecte de données centrée sur le périphérique ne suffit plus pour les campagnes de marketing numérique ou le ciblage inter-périphériques.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] modifie fondamentalement la manière dont [!DNL Audience Manager] les données sont collectées et segmente les utilisateurs pour le ciblage. Il vous permet de travailler avec deux types de profils distincts, un profil de périphérique et un profil [](../../reference/visitor-authentication-states.md)authentifié.

<table id="table_CE98C0E32A964B27804736A896233869"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de profil </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Device  profil </td> 
   <td colname="col2"> <p>Un profil de périphérique est lié à un ID pour un périphérique donné, tel qu’un ID de cookie ou un ID de périphérique mobile. Il inclut : </p> <p>
     <ul id="ul_0420875DE65E44FFAC76E0DD205CFEC4"> 
      <li id="li_044AD85C644A41FB8EF48164BAC0CE34">Caractéristiques basées sur des règles, réalisées lorsqu’un utilisateur n’est pas authentifié. </li> 
      <li id="li_984D9790A6984139AFCFC2DFE4DF1BFC">Caractéristiques intégrées liées à un ID de périphérique tel que les données tierces basées sur des cookies. </li>
     </ul> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> Profil authentifié </td> 
   <td colname="col2"> <p>Le profil authentifié est lié à un ID utilisateur transmis lorsqu’une personne se connecte à votre site. Elle inclut </p>
    <ul id="ul_18319CAA875148DBAE095134D42637B3"> 
     <li id="li_E24BD33E049849E5A594B0750F530475">Caractéristiques basées sur des règles collectées sur plusieurs périphériques lorsqu’un utilisateur est authentifié. </li>
     <li id="li_531AC9E0EC9D45108457FEC8E8D4E66C">Caractéristiques intégrées dans un fichier hors ligne lié au même ID utilisateur. </li>
    </ul> </td>
  </tr>
 </tbody>
</table>

Ces différents profils contrôlent les données que vous pouvez utiliser pour la segmentation. Par exemple, avec un profil [](../../reference/visitor-authentication-states.md)authentifié, vous pouvez créer des segments précis à partir de données provenant de plusieurs périphériques pour un utilisateur unique. Cela signifie que vous pouvez offrir une expérience cohérente de la marque aux clients sur plusieurs périphériques. Audience Manager effectue cette opération en stockant le mappage des différents périphériques qu’une personne utilise pour ses activités en ligne sur son profil [](../../reference/visitor-authentication-states.md)authentifié. Ces mappages sont appelés le [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Avantages {#advantages}

Avec [!UICONTROL Profile Merge Rules] vous pouvez :

* Ciblez les utilisateurs en fonction du profil [](../../reference/visitor-authentication-states.md)authentifié, des profils anonymes ou des combinaisons des deux.
* Ciblez un client spécifique sur l’ensemble de ses périphériques.
* Créez un graphique de périphérique basé sur des données déterministes.
* Affinez les données de vos segments en fonction de différents profils.
* Obtenez des informations supplémentaires sur votre public.
