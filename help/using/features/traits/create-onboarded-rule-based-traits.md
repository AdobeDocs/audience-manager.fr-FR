---
description: Décrit les étapes de configuration et les fonctionnalités spécifiques au processus de création de caractéristiques basé sur des règles et intégrées.
keywords: créer une caractéristique ; créer des caractéristiques
seo-description: Décrit les étapes de configuration et les fonctionnalités spécifiques au processus de création de caractéristiques basé sur des règles et intégrées.
seo-title: Création de caractéristiques articulées autour de règles ou articulées autour de règles
solution: Audience Manager
title: Création de caractéristiques articulées autour de règles ou articulées autour de règles
uuid: 4243 e 09 f -1 f 96-443 a -864 a-d 6 e 6918079 fa
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create Rules-Based or Onboarded Traits {#create-rules-based-or-onboarded-traits}

Describes set up steps and features specific to the [!UICONTROL rules-based] and [!UICONTROL onboarded] trait creation process.

<!-- c_tb_rules_traits.xml -->

## Basic Information for Traits {#basics}

In [!UICONTROL Trait Builder], the [!UICONTROL Basic Information] settings let you create new, or edit existing traits. [!UICONTROL Basic Information] Les paramètres sont identiques pour les caractéristiques basées sur des règles, des valeurs intégrées et des algorithmes. Pour créer une nouvelle caractéristique, indiquez un nom (évitez les caractères spéciaux), une source de données et sélectionnez un dossier de stockage. Other [!UICONTROL Basic Information] fields are optional.

<!-- c_tb_basics.xml -->

### Champs d&#39;informations de base définis

<table id="table_42AEC7A5B22346C5BB996D2D36C56229"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elément de l'interface </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Nom</span></b> </td> 
   <td colname="col2"> <p>Nom de la caractéristique. Obligatoire. </p> <p>Longueur maximale : 255 caractères. </p> <p> <p>Remarque : Lors du nommage des caractéristiques, évitez ces caractères spéciaux : 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Virgules </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Tirets </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Tirets </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Onglets </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Symbole barre verticale ou barre verticale </li> 
      </ul> </p> </p> <p>This helps reduce processing errors when you set up an <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> inbound data file transfer</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Description</span></b> </td> 
   <td colname="col2"> Quelques mots pour décrire la finalité ou la fonction de la caractéristique. Facultatif. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Type d’événement</span></b> </td> 
   <td colname="col2"> Attribue la caractéristique à un type ou une catégorie, généralement selon la fonction (conversion, visiteur du site, partenaire, page vue, etc.). Facultatif. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Source de données</span></b> </td> 
   <td colname="col2"> Associe la caractéristique à un fournisseur de données spécifique. Obligatoire. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Code d’intégration</span></b> </td> 
   <td colname="col2"> Champ d'un identifiant, d'un SKU ou d'une autre valeur utilisée par vos processus métier internes. Facultatif. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Commentaires</span></b> </td> 
   <td colname="col2"> Remarques générales sur une caractéristique. Facultatif. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Stocké dans</span></b> </td> 
   <td colname="col2"> Détermine le dossier de stockage auquel la caractéristique appartient. Obligatoire. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Catégorie de données</span></b> </td> 
   <td colname="col2"> Classe les caractéristiques selon des catégories communément connues. <p>Remarque : Les caractéristiques appartiennent à une seule catégorie uniquement. Facultatif. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Set a Trait Expiration Interval {#set-expiration-interval}

In [!UICONTROL Trait Builder], the [!UICONTROL Advanced Options] lets you set a time-to-live ([!DNL TTL]) interval for a trait. [!DNL TTL] définit le nombre de jours pendant lesquels un visiteur qualifié reste dans une caractéristique (120 jours sont par défaut). Lorsqu&#39;elle est définie sur 0, l&#39;appartenance à la caractéristique n&#39;expire jamais.

<!-- t_tb_ttl.xml -->

### Définition de TTL pour une caractéristique

1. Expand the [!UICONTROL Advanced Options] section and enter a number to set a [!DNL TTL] value for the trait.
1. Cliquez sur **[!UICONTROL Save]**.
   ![](assets/TTL.png)

>[!MORE_ LIKE_ THIS]
>
>* [Temps de segmentation pour l&#39;explication de la durée](../../features/traits/segment-ttl-explained.md)

