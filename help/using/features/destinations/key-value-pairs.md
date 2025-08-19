---
description: A [!DNL key-value pair] se compose de [!DNL related elements]. Une clé, qui est une constante qui définit l’ensemble de données (par exemple, genre, couleur, prix) et une valeur, qui est une variable appartenant à l’ensemble (par exemple, homme/femme, vert, 100). Destination Builder envoie des données formatées en paires clé-valeur.
solution: Audience Manager
title: Standard et série [!DNL Key-value pairs]
uuid: 43789419-5b3f-4e62-b2e0-2722340bdd41
feature: Destination Basics
exl-id: b37c829b-66be-4c31-8198-bc032371279e
source-git-commit: 0dfe96a4644c61fb5bc22e4791bfd09c574dcf34
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---

# Paires clé-valeur standard et série {#standard-and-serial-key-value-pairs}

Une paire clé-valeur se compose d’éléments associés : une clé, qui est une constante définissant l’ensemble de données (par exemple : genre, couleur, prix) et une valeur, qui est une variable appartenant à l’ensemble (par exemple : homme/femme, vert, 100). [!UICONTROL Destination Builder] envoie des données formatées en paires clé-valeur.

## Paires Clé-Valeur De Base {#basic-key-value-pairs}

Entièrement formé, un ensemble de base de paire clé-valeur pourrait ressembler à ceci :

* `gender = male`
* `color = green`
* `price > 100`

## Paires clé-valeur standard et série {#standard-serial-key-value-pairs}

Les destinations acceptent les données clé-valeur au format *`standard`* ou *`serialized`*.

* **Paires clé-valeur standard :** formate les données de destination en paires clé-valeur distinctes. Chaque clé est indiquée explicitement, même lorsqu’elle est utilisée à nouveau pour définir une valeur différente.
* **Paires clé-valeur sérialisées :** condense plusieurs valeurs en une seule paire clé-valeur. Dans une paire clé-valeur sérialisée, un indicateur spécial sépare les valeurs dans le jeu clé-valeur.

Les valeurs-clés standard et sérialisées peuvent contenir une ou plusieurs valeurs. Le tableau suivant fournit des exemples de formats de valeur de clé standard et série.

<table id="table_7895B1E800934117A19A96380F0CF91B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formatage </th>
   <th colname="col2" class="entry"> Paires Clé-Valeur Uniques </th>
   <th colname="col3" class="entry"> Paires Clé-Valeur Multiples </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Standard</b> </p> </td>
   <td colname="col2"> <p> <code> x = 1 &amp; x = 2 </code> </p> </td>
   <td colname="col3"> <p> <code> x = 1 &amp; x = 2 &amp; y = 3 &amp; y = 4 </code> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>Sérialisé</b> </p> </td> 
   <td colname="col2"> <p> <code> x = 1 ; 2 </code> </p> </td> 
   <td colname="col3"> <p> <code> x = 1 ; 2 &amp; y = 3 ; 4 </code> </p> </td>
  </tr>
 </tbody>
</table>

## Délimiteurs et séparateurs {#delimiters-separators}

Les caractères qui séparent les valeurs dans et entre les clés et les valeurs sont appelés *`delimiters`* et *`separators`*. Ils deviennent particulièrement importants lorsque vous envoyez des segments vers une destination dans un format série. La sérialisation vous permet de transmettre plusieurs valeurs avec une seule clé et de combiner des paires clé-valeur. Les délimiteurs et séparateurs sont définis comme suit :

* **Séparateur clé-valeur :** sépare une clé et une valeur dans une paire clé-valeur.
* **Délimiteur clé-valeur :** sépare des ensembles de paires clé-valeur.
* **Séparateur de série :** sépare plusieurs valeurs dans des ensembles de paires clé-valeur sérialisées.

## Exemples {#examples}

Avec [!UICONTROL Destination Builder], vous pouvez formater les données clé-valeur de plusieurs manières différentes. Jetons un œil à quelques exemples de chaque type.

<table id="table_C2FBDC887C8C4CC88B1B2A7CF8E2795F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exemples De Paires Clé-Valeur </th> 
   <th colname="col2" class="entry"> Exemple </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Clé unique standard</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 </code> </p> </td> 
   <td colname="col3"> <p>Ensemble simple de paires clé-valeur. L’exemple contient les éléments suivants : </p> 
    <ul id="ul_28C0CB005B264373926CA5D7418EE845"> 
     <li id="li_B6D300DBA9064F0BA743BA9B04339511">Clé : X </li> 
     <li id="li_9A1C98D5C9124FF1B4F032668576C03A">Valeurs : 1, 2 </li> 
     <li id="li_1D2828328E554176846C94F6140C0CBF">Séparateur : = </li> 
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">Délimiteur clé-valeur : &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Paires clé-valeur multiples</b> (non série) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 &amp; Y = 3 &amp; Y = 4 </code> </p> </td> 
   <td colname="col3"> <p>Ensemble de plusieurs paires clé-valeur qui transmettent des valeurs avec des jeux clé-valeur distincts. L’exemple contient les éléments suivants : </p> 
    <ul id="ul_7FB22A43B435463D9F209067FF2C3619"> 
     <li id="li_7487657F6C2F48F5A4C4C9F9E8FB3B4B">Touches : X, Y </li> 
     <li id="li_B828CF81DAB8443FBB2EDF6538A63B3C">Valeurs : 1, 2, 3, 4 </li> 
     <li id="li_EA4C95F6C93D435EB79237E38CE6F011">Séparateur : = </li> 
     <li id="li_45984AE2B581498299054BA5276D461D">Délimiteur clé-valeur : &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Clé unique série</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 ; 3 </code> </p> </td> 
   <td colname="col3"> <p>Un ensemble clé-valeur qui transmet plusieurs valeurs avec une seule clé. Cette clé ayant plusieurs valeurs, elle est connue sous le nom de paire clé-valeur sérialisée. L’exemple contient les éléments suivants : </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">Clé : X </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">Valeurs : 1, 2, 3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">Séparateur : = </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">Séparateur de série : point-virgule </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Paires clé-valeur multiples</b> (série) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 &amp; Y = 3 ; 4 </code> </p> </td> 
   <td colname="col3"> <p>Ensemble de plusieurs paires clé-valeur qui transmettent plusieurs valeurs sur des clés distinctes. L’exemple contient les éléments suivants : </p> 
    <ul id="ul_CB50133B2E944818B9F2A0586EF69774"> 
     <li id="li_FD3D7ECC2BF046E99B1ED0B73EFE341F">Touches : X, Y </li> 
     <li id="li_2BADC98C4CE74BBBBA1DC446D24615AC">Valeurs : 1, 2, 3, 4 </li> 
     <li id="li_4125435175AD4A43A44B980B28F32364">Séparateur : = </li> 
     <li id="li_48CFC279B2514F4FB2935B05FC7F287A">Délimiteur : &amp; </li> 
     <li id="li_576C731F2FAF47FD92F55345CD6D36A0">Séparateur de série : point-virgule </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Sérialisation de destination {#destination-serialized}

Une destination sérialisée combine plusieurs caractéristiques en une seule chaîne et envoie ces informations à une destination.

<!-- c_dest_serialized.xml -->

La transmission sérialisée des données contribue à améliorer l’efficacité, car plusieurs caractéristiques se déclenchent de manière séquentielle, plutôt qu’en parallèle. Le serveur de destination dispose ainsi de suffisamment de temps pour recevoir, traiter et renvoyer des données avant de répondre à d’autres requêtes.

### Destinations prises en charge

Dans [!DNL Audience Manager], vous pouvez sérialiser et envoyer des données vers n’importe quelle destination avec laquelle vous souhaitez travailler. Cependant, avant d’utiliser cette fonctionnalité, vous devez connaître le [!DNL URL] de destination et savoir où placer certaines macros obligatoires ou facultatives. Obtenez les informations sur l’emplacement de la macro auprès de votre partenaire de destination. Voir [Macros de destination définies](../../features/destinations/destination-macros.md#destination-macros-defined) pour plus d’informations.
