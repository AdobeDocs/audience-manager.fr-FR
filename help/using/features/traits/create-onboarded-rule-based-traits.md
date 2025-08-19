---
description: Décrit les étapes et les fonctionnalités de configuration spécifiques au processus de création de caractéristiques basé sur des règles et intégrées.
keywords: créer une caractéristique;créer des caractéristiques
seo-description: Describes set up steps and features specific to the rules-based and onboarded trait creation process.
seo-title: Create Rules-Based or Onboarded Traits
solution: Audience Manager
title: Création de caractéristiques basées sur des règles ou intégrées
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
feature: Traits
exl-id: cad318ee-93b2-4afa-8a2f-a67b068eec0a
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 2%

---

# Créer des [!UICONTROL Rules-Based] ou des [!UICONTROL Onboarded Traits] {#create-rules-based-or-onboarded-traits}

Décrit les étapes et les fonctionnalités de configuration spécifiques au processus de création de caractéristiques [!UICONTROL rules-based] et [!UICONTROL onboarded].

<!-- c_tb_rules_traits.xml -->

## Informations de base sur les caractéristiques {#basics}

En [!UICONTROL Trait Builder], les paramètres [!UICONTROL Basic Information] vous permettent de créer des [!UICONTROL traits] ou d’en modifier d’existants. Les paramètres [!UICONTROL Basic Information] sont les mêmes pour [!UICONTROL rules-based], [!UICONTROL onboarded] et [!UICONTROL algorithmic traits]. Pour créer un [!UICONTROL trait], donnez un nom (évitez les caractères spéciaux), un [!UICONTROL data source] et sélectionnez un [!UICONTROL storage folder]. Les autres champs [!UICONTROL Basic Information] sont facultatifs.

<!-- c_tb_basics.xml -->

![créer-caractéristique](assets/create-trait.png)

### Champs D’Informations De Base Définis

<table id="table_42AEC7A5B22346C5BB996D2D36C56229"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément d’interface </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Name </span></b> </td> 
   <td colname="col2"> <p>Nom de la caractéristique. Obligatoire. </p> <p>Longueur maximale : 255 caractères. </p> <p> <p>Remarque : lorsque vous nommez des caractéristiques, évitez les caractères spéciaux suivants : 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Virgules </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Tirets </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Tirets </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Onglets </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Symbole de barre verticale ou de barre verticale </li> 
      </ul> </p> </p> <p>Cela permet de réduire les erreurs de traitement lorsque vous configurez un <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> transfert de fichier de données entrant</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">Description</span></b> </td> 
   <td colname="col2"> Quelques mots pour décrire l’objectif ou la fonction de la caractéristique. Facultatif. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Data Source</span></b> </td> 
   <td colname="col2"> Associe la caractéristique à un fournisseur de données spécifique. Obligatoire. <p>Utilisez le premier menu déroulant pour filtrer entre les sources de données Audience Manager, les suites de rapports Adobe Analytics ou les deux. Utilisez ensuite le deuxième menu déroulant pour choisir votre source de données.</p><p> Si vous n’utilisez pas de suites de rapports Adobe Analytics, le sélecteur de type de source de données est désactivé et correspond par défaut aux sources de données Audience Manager uniquement.</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> type d’événement</span></b> </td> 
   <td colname="col2"> Attribue la caractéristique à un type ou à une catégorie, généralement en fonction de la fonction (par exemple, conversion, visiteur du site, partenaire, page vue, etc.). Facultatif. <p> Pour savoir comment créer des caractéristiques de conversion, consultez la <a href="https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">vidéo Création de caractéristiques de conversion dans Audience Manager</a>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Code d’intégration <b><span class="uicontrol"></span></b> </td> 
   <td colname="col2"> Champ pour un ID, un SKU ou une autre valeur utilisée par vos processus d’entreprise internes. Facultatif. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Commentaires</span></b> </td> 
   <td colname="col2"> Remarques générales sur une caractéristique. Facultatif. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Stocker Dans </span></b> </td> 
   <td colname="col2"> Détermine à quel dossier de stockage appartient la caractéristique. Obligatoire. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> catégorie de données</span></b> </td> 
   <td colname="col2"> Classe les caractéristiques selon des catégories communément comprises. <p>Remarque : les caractéristiques appartiennent à une seule catégorie uniquement. Facultatif. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Définir un intervalle d’expiration de [!UICONTROL Trait] {#set-expiration-interval}

Dans [!UICONTROL Trait Builder], le [!UICONTROL Advanced Options] vous permet de définir un intervalle de durée de vie ([!DNL TTL]) pour un [!UICONTROL trait]. [!DNL TTL] définit le nombre de jours pendant lesquels un visiteur qualifié reste dans un [!UICONTROL trait] (120 jours par défaut). Lorsqu’elle est définie sur 0, l’appartenance à [!UICONTROL trait] n’expire jamais.

<!-- t_tb_ttl.xml -->

### Définir la TTL d’une [!UICONTROL trait]

1. Développez la section [!UICONTROL Advanced Options] et saisissez un nombre pour définir une valeur [!DNL TTL] pour le [!UICONTROL trait].
1. Cliquez sur **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [Explication de la durée de vie du segment](../../features/traits/segment-ttl-explained.md)
