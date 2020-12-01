---
description: Décrit les étapes et fonctionnalités de configuration spécifiques au processus de création de caractéristiques intégré et basé sur des règles.
keywords: create trait;create traits
seo-description: Décrit les étapes et fonctionnalités de configuration spécifiques au processus de création de caractéristiques intégré et basé sur des règles.
seo-title: Création de caractéristiques basées sur des règles ou intégrées
solution: Audience Manager
title: Création de caractéristiques basées sur des règles ou intégrées
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 7%

---


# Créez[!UICONTROL Rules-Based] ou [!UICONTROL Onboarded Traits] {#create-rules-based-or-onboarded-traits}

Décrit les étapes et fonctionnalités configurées spécifiques au processus de création de caractéristiques [!UICONTROL rules-based] et [!UICONTROL onboarded].

<!-- c_tb_rules_traits.xml -->

## Informations de base sur les caractéristiques {#basics}

Dans [!UICONTROL Trait Builder], les paramètres [!UICONTROL Basic Information] vous permettent de créer ou de modifier [!UICONTROL traits] existant. Les paramètres [!UICONTROL Basic Information] sont identiques pour [!UICONTROL rules-based], [!UICONTROL onboarded] et [!UICONTROL algorithmic traits]. Pour créer un [!UICONTROL trait], indiquez un nom (évitez les caractères spéciaux), un [!UICONTROL data source], puis sélectionnez un [!UICONTROL storage folder]. Les autres champs [!UICONTROL Basic Information] sont facultatifs.

<!-- c_tb_basics.xml -->

![create-trait](assets/create-trait.png)

### Définition des champs d&#39;informations de base

<table id="table_42AEC7A5B22346C5BB996D2D36C56229"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elément Interface </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Nom</span></b> </td> 
   <td colname="col2"> <p>Nom de la caractéristique. Obligatoire. </p> <p>Longueur maximale : 255 caractères. </p> <p> <p>Remarque : Lorsque vous nommez des caractéristiques, évitez les caractères spéciaux suivants : 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Virgules </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Tirets </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Tirets </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Onglets </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Symbole de barre verticale ou de barre verticale </li> 
      </ul> </p> </p> <p>Cela permet de réduire les erreurs de traitement lorsque vous configurez un <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> transfert de fichier de données entrant</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Description</span></b> </td> 
   <td colname="col2"> Quelques mots pour décrire l'objectif ou la fonction du trait. Facultatif. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Source de données</span></b> </td> 
   <td colname="col2"> Associe la caractéristique à un fournisseur de données spécifique. Obligatoire. <p>Utilisez le premier menu déroulant pour filtrer entre les sources de données d’Audience Manager, les suites de rapports Adobe Analytics ou les deux. Ensuite, utilisez le deuxième menu déroulant pour choisir votre source de données.</p><p> Si vous n’utilisez pas les suites de rapports Adobe Analytics, le sélecteur de type de source de données est désactivé et les sources de données d’Audience Manager sont désactivées par défaut uniquement.</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Type d’événement</span></b> </td> 
   <td colname="col2"> Attribue la caractéristique à un type ou une catégorie, généralement en fonction de la fonction (par exemple, conversion, visiteur du site, partenaire, vue de page, etc.). Facultatif. <p> Pour savoir comment créer des caractéristiques de conversion, consultez la <a href="https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">vidéo Création de caractéristiques de conversion dans l'Audience Manager</a>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Code d’intégration</span></b> </td> 
   <td colname="col2"> Champ d’un identifiant, d’un SKU ou d’une autre valeur utilisé par vos processus métier internes. Facultatif. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Commentaires</span></b> </td> 
   <td colname="col2"> Remarques générales sur une caractéristique. Facultatif. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Stocker dans</span></b> </td> 
   <td colname="col2"> Détermine le dossier d’enregistrement auquel appartient la caractéristique. Obligatoire. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Catégorie de données</span></b> </td> 
   <td colname="col2"> Classe les caractéristiques en fonction de catégories courantes. <p>Remarque :  Les traits appartiennent à une seule catégorie. Facultatif. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Définir un intervalle d&#39;expiration [!UICONTROL Trait] {#set-expiration-interval}

Dans [!UICONTROL Trait Builder], [!UICONTROL Advanced Options] vous permet de définir un intervalle de temps de vie ([!DNL TTL]) pour un [!UICONTROL trait]. [!DNL TTL] définit le nombre de jours pendant lesquels un visiteur qualifié reste dans un  [!UICONTROL trait] (120 jours est par défaut). Lorsqu&#39;elle est définie sur 0, l&#39;abonnement [!UICONTROL trait] n&#39;expire jamais.

<!-- t_tb_ttl.xml -->

### Définissez TTL pour un [!UICONTROL trait]

1. Développez la section [!UICONTROL Advanced Options] et entrez un nombre pour définir une valeur [!DNL TTL] pour [!UICONTROL trait].
1. Cliquez sur **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [Explication de la durée de vie du segment](../../features/traits/segment-ttl-explained.md)

