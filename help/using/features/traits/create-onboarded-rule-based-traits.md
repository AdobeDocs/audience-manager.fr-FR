---
description: Décrit les étapes de configuration et les fonctionnalités spécifiques au processus de création de caractéristiques basé sur des règles et intégrées.
keywords: créer une caractéristique ; créer des caractéristiques
seo-description: Décrit les étapes de configuration et les fonctionnalités spécifiques au processus de création de caractéristiques basé sur des règles et intégrées.
seo-title: Création de caractéristiques articulées autour de règles ou articulées autour de règles
solution: Audience Manager
title: Création de caractéristiques articulées autour de règles ou articulées autour de règles
uuid: 4243 e 09 f -1 f 96-443 a -864 a-d 6 e 6918079 fa
translation-type: tm+mt
source-git-commit: 76adee013246c68da7ad871cef57f6ef174a239c

---


# Création de caractéristiques articulées autour de règles ou articulées autour de règles {#create-rules-based-or-onboarded-traits}

Décrit les étapes et les fonctionnalités de configuration spécifiques au [!UICONTROL rules-based] processus de création de [!UICONTROL onboarded] caractéristiques.

<!-- c_tb_rules_traits.xml -->

## Informations de base pour les caractéristiques {#basics}

Dans [!UICONTROL Trait Builder], [!UICONTROL Basic Information] les paramètres vous permettent de créer ou de modifier des caractéristiques existantes. [!UICONTROL Basic Information] Les paramètres sont identiques pour les caractéristiques basées sur des règles, des valeurs intégrées et des algorithmes. Pour créer une nouvelle caractéristique, indiquez un nom (évitez les caractères spéciaux), une source de données et sélectionnez un dossier de stockage. D'autres [!UICONTROL Basic Information] champs sont facultatifs.

<!-- c_tb_basics.xml -->

### Champs d'informations de base définis

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
      </ul> </p> </p> <p>Cela permet de réduire les erreurs de traitement lorsque vous configurez un transfert de fichier de données <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> entrant</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Description</span></b> </td> 
   <td colname="col2"> Quelques mots pour décrire la finalité ou la fonction de la caractéristique. Facultatif. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Type d’événement</span></b> </td> 
   <td colname="col2"> Attribue la caractéristique à un type ou une catégorie, généralement selon la fonction (conversion, visiteur du site, partenaire, page vue, etc.). Facultatif. <p> Pour savoir comment créer des caractéristiques de conversion, reportez-vous à <a href="https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">la vidéo Création de caractéristiques de conversion dans Audience Manager</a>. </p></td> 
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

## Définition d'un intervalle d'expiration de caractéristique {#set-expiration-interval}

Dans [!UICONTROL Trait Builder], vous [!UICONTROL Advanced Options] pouvez définir un intervalle de temps à réel ([!DNL TTL]) pour une caractéristique. [!DNL TTL] définit le nombre de jours pendant lesquels un visiteur qualifié reste dans une caractéristique (120 jours sont par défaut). Lorsqu'elle est définie sur 0, l'appartenance à la caractéristique n'expire jamais.

<!-- t_tb_ttl.xml -->

### Définition de TTL pour une caractéristique

1. Développez [!UICONTROL Advanced Options] la section et saisissez un nombre pour définir [!DNL TTL] la valeur de la caractéristique.
2. Cliquez sur **[!UICONTROL Save]**.
   ![](assets/TTL.png)

>[!MORE_ LIKE_ THIS]
>
>* [Temps de segmentation pour l'explication de la durée](../../features/traits/segment-ttl-explained.md)

