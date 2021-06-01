---
description: Décrit les étapes et fonctionnalités de configuration spécifiques au processus de création de caractéristiques intégré et basé sur des règles.
keywords: créer une caractéristique, créer des caractéristiques
seo-description: Décrit les étapes et fonctionnalités de configuration spécifiques au processus de création de caractéristiques intégré et basé sur des règles.
seo-title: Création de caractéristiques basées sur des règles ou intégrées
solution: Audience Manager
title: Création de caractéristiques basées sur des règles ou intégrées
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
feature: 'Caractéristiques '
exl-id: cad318ee-93b2-4afa-8a2f-a67b068eec0a
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 7%

---

# Créez[!UICONTROL Rules-Based] ou [!UICONTROL Onboarded Traits] {#create-rules-based-or-onboarded-traits}

Décrit les étapes et fonctionnalités de configuration spécifiques au processus de création de caractéristiques [!UICONTROL rules-based] et [!UICONTROL onboarded].

<!-- c_tb_rules_traits.xml -->

## Informations de base sur les caractéristiques {#basics}

Dans [!UICONTROL Trait Builder], les paramètres [!UICONTROL Basic Information] vous permettent de créer ou de modifier des [!UICONTROL traits] existants. Les paramètres [!UICONTROL Basic Information] sont les mêmes pour [!UICONTROL rules-based], [!UICONTROL onboarded] et [!UICONTROL algorithmic traits]. Pour créer un [!UICONTROL trait], indiquez un nom (évitez les caractères spéciaux), un [!UICONTROL data source], puis sélectionnez un [!UICONTROL storage folder]. Les autres champs [!UICONTROL Basic Information] sont facultatifs.

<!-- c_tb_basics.xml -->

![create-trait](assets/create-trait.png)

### Champs d’informations de base définis

<table id="table_42AEC7A5B22346C5BB996D2D36C56229"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elément de l’interface </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Nom</span></b> </td> 
   <td colname="col2"> <p>Nom de la caractéristique. Obligatoire. </p> <p>Longueur maximale : 255 caractères. </p> <p> <p>Remarque : Lorsque vous nommez des caractéristiques, évitez les caractères spéciaux suivants : 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Virgules </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Blocs </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Tons d’union </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Onglets </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Barre verticale ou symbole de barre verticale </li> 
      </ul> </p> </p> <p>Cela permet de réduire les erreurs de traitement lorsque vous configurez un <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> transfert de fichier de données entrant</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Description</span></b> </td> 
   <td colname="col2"> Quelques mots pour décrire l’objectif ou la fonction d’une caractéristique. Facultatif. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Source de données</span></b> </td> 
   <td colname="col2"> Associe la caractéristique à un fournisseur de données spécifique. Obligatoire. <p>Utilisez le premier menu déroulant pour filtrer entre les sources de données d’Audience Manager, les suites de rapports Adobe Analytics ou les deux. Utilisez ensuite le deuxième menu déroulant pour choisir votre source de données.</p><p> Si vous n’utilisez pas de suites de rapports Adobe Analytics, le sélecteur de type de source de données est désactivé et par défaut, les sources de données d’Audience Manager sont uniquement utilisées.</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Type d’événement</span></b> </td> 
   <td colname="col2"> Attribue la caractéristique à un type ou à une catégorie, généralement en fonction de sa fonction (par exemple, conversion, visiteur du site, partenaire, page vue, etc.). Facultatif. <p> Pour savoir comment créer des caractéristiques de conversion, reportez-vous à la <a href="https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">vidéo Création de caractéristiques de conversion dans Audience Manager</a>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Code d’intégration</span></b> </td> 
   <td colname="col2"> Champ pour un identifiant, un SKU ou toute autre valeur utilisé par vos processus d’entreprise internes. Facultatif. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Commentaires</span></b> </td> 
   <td colname="col2"> Remarques générales sur une caractéristique. Facultatif. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Stocker dans</span></b> </td> 
   <td colname="col2"> Détermine le dossier de stockage auquel la caractéristique appartient. Obligatoire. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Catégorie de données</span></b> </td> 
   <td colname="col2"> Classe les caractéristiques en fonction des catégories courantes. <p>Remarque :  Les caractéristiques appartiennent à une seule catégorie. Facultatif. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Définissez un [!UICONTROL Trait] Intervalle d’expiration {#set-expiration-interval}

Dans [!UICONTROL Trait Builder], [!UICONTROL Advanced Options] permet de définir un intervalle de temps de vie ([!DNL TTL]) pour un [!UICONTROL trait]. [!DNL TTL] définit le nombre de jours pendant lesquels un visiteur qualifié reste dans un  [!UICONTROL trait] (120 jours est la valeur par défaut). Lorsqu’elle est définie sur 0, l’appartenance [!UICONTROL trait] n’expire jamais.

<!-- t_tb_ttl.xml -->

### Définissez le délai d’activation pour un [!UICONTROL trait]

1. Développez la section [!UICONTROL Advanced Options] et saisissez un nombre pour définir une valeur [!DNL TTL] pour la balise [!UICONTROL trait].
1. Cliquez sur **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [Explication de la durée de vie des segments](../../features/traits/segment-ttl-explained.md)

