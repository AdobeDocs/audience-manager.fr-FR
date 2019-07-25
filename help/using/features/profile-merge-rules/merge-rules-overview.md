---
description: Avec les règles de fusion de profils, vous contrôlez les ensembles de données utilisés pour la segmentation et pouvez cibler une personne avec précision sur plusieurs périphériques.
seo-description: Avec les règles de fusion de profils, vous contrôlez les ensembles de données utilisés pour la segmentation et pouvez cibler une personne avec précision sur plusieurs périphériques.
seo-title: Présentation des règles de fusion des profils
solution: Audience Manager
title: Présentation des règles de fusion des profils
uuid: 9 e 7988 cc -9145-432 b -840 a -54 fbd 8657 b 3 b
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# Profile Merge Rules Overview {#profile-merge-rules-overview}

With [!UICONTROL Profile Merge Rules] you get control over the data sets used for segmentation and can target a person accurately across multiple devices.

## Data collection and targeting with anonymous and authenticated profiles {#data-collection-targeting}

En règle générale, la segmentation et le ciblage de l'audience reposent sur les données collectées auprès de tous les utilisateurs d'un périphérique. La collecte et le ciblage de données basés sur les données au niveau du périphérique ont certains inconvénients. Par exemple, vous ne pouvez pas faire la distinction entre plusieurs utilisateurs qui partagent un périphérique ou ciblent précisément les utilisateurs sur plusieurs périphériques. La collecte de données centrées sur le périphérique ne suffit plus pour les campagnes de marketing numérique ou le ciblage inter-périphériques.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] change fondamentalement la manière [!DNL Audience Manager] dont collecte les données et segmente les utilisateurs pour le ciblage. Il vous permet de travailler avec 2 types de profils distincts, un profil de périphérique et un profil authentifié.

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
   <td colname="col2"> <p>Un profil de périphérique est lié à un ID pour un périphérique donné, tel qu'un ID de cookie ou un ID de périphérique mobile. Il inclut : </p> <p>
     <ul id="ul_0420875DE65E44FFAC76E0DD205CFEC4"> 
      <li id="li_044AD85C644A41FB8EF48164BAC0CE34">Caractéristiques basées sur des règles réalisées lorsqu'un utilisateur n'est pas authentifié. </li> 
      <li id="li_984D9790A6984139AFCFC2DFE4DF1BFC">Caractéristiques intégrées liées à un ID de périphérique, telles que des données de cookie tierces. </li>
     </ul> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> Profil authentifié </td> 
   <td colname="col2"> <p>Le profil authentifié est lié à un utilisateur - id transmis lorsqu'une personne se connecte à votre site. Elle inclut </p>
    <ul id="ul_18319CAA875148DBAE095134D42637B3"> 
     <li id="li_E24BD33E049849E5A594B0750F530475">Caractéristiques basées sur des règles collectées sur l'ensemble des périphériques lorsqu'un utilisateur est authentifié. </li>
     <li id="li_531AC9E0EC9D45108457FEC8E8D4E66C">Caractéristiques intégrées dans un fichier hors ligne lié au même utilisateur - id. </li>
    </ul> </td>
  </tr>
 </tbody>
</table>

Ces différents profils contrôlent les données que vous pouvez utiliser pour la segmentation. Par exemple, avec un profil authentifié, vous pouvez créer des segments précis basés sur des données issues de divers périphériques pour une seule personne. Cela signifie que vous pouvez offrir une expérience de marque cohérente aux clients sur plusieurs périphériques. Additionally, cross-device authentication allows [!DNL Audience Manager] to map the different platforms a person uses for their online activities. This is called the [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Avantages {#advantages}

With [!UICONTROL Profile Merge Rules] you can:

* Utilisateurs ciblés sur la base de profils authentifiés, de profils anonymes ou de combinaisons de deux.
* Ciblez un client spécifique sur son appareil.
* Créez un graphique de périphérique basé sur des données déterministes.
* Affiner : ajustez les données de vos segments en fonction de différents profils.
* Obtenez des informations supplémentaires sur votre public.

## Prise en main {#getting-started}

See the following sections and the [FAQ](../../faq/faq-profile-merge.md) for more information about [!UICONTROL Profile Merge Rules].

* [Prise en main des règles de fusion de profils](/help/using/features/profile-merge-rules/merge-rules-start.md)
* [Tableau de bord des règles de fusion de profils](/help/using/features/profile-merge-rules/merge-rules-dashboard.md)
* [Options de règle de fusion de profils définies](/help/using/features/profile-merge-rules/merge-rule-definitions.md)
* [Cas d'utilisation général pour les règles de fusion de profils](/help/using/features/profile-merge-rules/merge-rule-targeting-options.md)
* [Cas d'utilisation du graphique de périphérique de lien de profil](/help/using/features/profile-merge-rules/profile-link-use-case.md)
* [Cas d’utilisation graphiques des périphériques externes](/help/using/features/profile-merge-rules/external-graph-use-cases.md)
* [Mesures des rapports pour les règles de fusion de profils](/help/using/features/profile-merge-rules/profile-link-metrics.md)
* [Processus de fusion des profils et processus de déssegmentation des périphériques](/help/using/features/profile-merge-rules/merge-rule-unsegment.md)
* [Suppression instantanée inter-périphérique](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md)
* [Remarques importantes concernant les règles de fusion de profils avec des graphiques de périphérique](/help/using/features/profile-merge-rules/considerations-pmr-device-graph.md)
