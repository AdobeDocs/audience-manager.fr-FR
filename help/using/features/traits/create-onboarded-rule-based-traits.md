---
description: Décrit les étapes et les fonctionnalités de configuration spécifiques au processus de création de caractéristiques basé sur des règles et intégré.
keywords: créer une caractéristique;créer des caractéristiques
seo-description: Décrit les étapes et les fonctionnalités de configuration spécifiques au processus de création de caractéristiques basé sur des règles et intégré.
seo-title: Création de caractéristiques basées sur des règles ou intégrées
solution: Audience Manager
title: Création de caractéristiques basées sur des règles ou intégrées
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
translation-type: tm+mt
source-git-commit: 76adee013246c68da7ad871cef57f6ef174a239c

---


# Création de caractéristiques basées sur des règles ou intégrées {#create-rules-based-or-onboarded-traits}

Décrit les étapes et les fonctionnalités de configuration spécifiques au processus de création [!UICONTROL rules-based] et [!UICONTROL onboarded] de caractéristiques.

<!-- c_tb_rules_traits.xml -->

## Informations de base sur les caractéristiques {#basics}

Dans [!UICONTROL Trait Builder], les [!UICONTROL Basic Information] paramètres vous permettent de créer ou de modifier des caractéristiques existantes. Les [!UICONTROL Basic Information] paramètres sont les mêmes pour les caractéristiques basées sur des règles, intégrées et algorithmiques. Pour créer une nouvelle caractéristique, attribuez un nom (évitez les caractères spéciaux), une source de données et sélectionnez un dossier de stockage. Les autres [!UICONTROL Basic Information] champs sont facultatifs.

<!-- c_tb_basics.xml -->

### Définition des champs d’informations de base

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
   <td colname="col2"> <p>Nom de la caractéristique. Obligatoire. </p> <p>Longueur maximale : 255 caractères. </p> <p> <p>Remarque : Lorsque vous attribuez un nom aux caractéristiques, évitez les caractères spéciaux suivants : 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Virgules </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Tirets </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Tirets </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Onglets </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Symbole de barre verticale ou de barre verticale </li> 
      </ul> </p> </p> <p>Cela permet de réduire les erreurs de traitement lorsque vous configurez un transfert <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"></a>de fichier de données entrantes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Description</span></b> </td> 
   <td colname="col2"> Quelques mots pour décrire l'objectif ou la fonction du trait. Facultatif. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Type d’événement</span></b> </td> 
   <td colname="col2"> Attribue la caractéristique à un type ou une catégorie, généralement en fonction de la fonction (par exemple, conversion, visiteur du site, partenaire, page vue, etc.). Facultatif. <p> Pour savoir comment créer des caractéristiques de conversion, reportez-vous à la vidéo <a href="https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">Création de caractéristiques de conversion dans Audience Manager</a>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Source de données</span></b> </td> 
   <td colname="col2"> Associe la caractéristique à un fournisseur de données spécifique. Obligatoire. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Code d’intégration</span></b> </td> 
   <td colname="col2"> Champ d’un ID, d’un SKU ou d’une autre valeur utilisés par vos processus internes. Facultatif. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Commentaires</span></b> </td> 
   <td colname="col2"> Remarques générales sur une caractéristique. Facultatif. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Stocké dans</span></b> </td> 
   <td colname="col2"> Détermine le dossier de stockage auquel appartient la caractéristique. Obligatoire. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Catégorie de données</span></b> </td> 
   <td colname="col2"> Classe les caractéristiques en fonction des catégories couramment comprises. <p>Remarque :  Les caractéristiques appartiennent à une seule catégorie. Facultatif. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Définir un intervalle d’expiration des caractéristiques {#set-expiration-interval}

Dans [!UICONTROL Trait Builder]le, [!UICONTROL Advanced Options] vous permet de définir un intervalle de temps de vie ([!DNL TTL]) pour une caractéristique. [!DNL TTL] définit le nombre de jours qu’un visiteur qualifié reste dans une caractéristique (120 jours par défaut). Lorsqu’elle est définie sur 0, l’appartenance à une caractéristique n’expire jamais.

<!-- t_tb_ttl.xml -->

### Définition de TTL pour une caractéristique

1. Développez la [!UICONTROL Advanced Options] section et entrez un nombre pour définir une [!DNL TTL] valeur pour la caractéristique.
2. Cliquez sur **[!UICONTROL Save]**.
   ![](assets/TTL.png)

>[!MORE_LIKE_This]
>
>* [Segment Durée de vie expliqué](../../features/traits/segment-ttl-explained.md)

