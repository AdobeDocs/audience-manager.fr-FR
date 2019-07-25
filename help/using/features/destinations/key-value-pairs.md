---
description: Une paire clé-valeur se compose d'éléments associés, une clé qui définit le jeu de données (par exemple, sexe, couleur, prix) et une valeur, qui est une variable qui appartient à la visionneuse (homme/femme, vert, 100, par exemple). Le créateur de destinations envoie les données au format clé-valeur.
seo-description: Une paire clé-valeur se compose d'éléments associés, une clé qui définit le jeu de données (par exemple, sexe, couleur, prix) et une valeur, qui est une variable qui appartient à la visionneuse (homme/femme, vert, 100, par exemple). Le créateur de destinations envoie les données au format clé-valeur.
seo-title: Paires standard/de série-valeur standard
solution: Audience Manager
title: Paires standard/de série-valeur standard
uuid: 43789419-5 b 3 f -4 e 62-b 2 e 0-2722340 bdd 41
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Standard and Serial Key-Value Pairs {#standard-and-serial-key-value-pairs}

Une paire clé-valeur se compose d'éléments associés : Clé qui définit le jeu de données (par exemple, sexe, couleur, prix) et une valeur, qui est une variable qui appartient à la visionneuse (homme/femme, vert, 100, par exemple). [!UICONTROL Destination Builder] envoie les données au format clé-valeur.

## Basic Key-Value Pairs {#basic-key-value-pairs}

Entièrement formé, un ensemble de base de paire clé-valeur pourrait ressembler à celui-ci :

* `gender = male`
* `color = green`
* `price > 100`

## Standard and Serial Key-Value Pairs {#standard-serial-key-value-pairs}

Destinations accept key-value data in *`standard`* or *`serialized`* format.

* **Paires clé-valeur standard :** Formate les données de destination en paires clé-valeur distinctes. Chaque clé est explicitement spécifiée, même lorsqu'elle est réutilisée pour définir une valeur différente.
* **Paires clé-valeur sérialisées :** Condense plusieurs valeurs en une paire clé-valeur unique. Dans une paire clé-valeur sérialisée, un indicateur spécial sépare les valeurs dans le jeu de valeurs clés.

Les valeurs de clé standard et sérialisées peuvent contenir des valeurs uniques ou multiples. Le tableau suivant présente des exemples de formats standard et de valeurs de clé de série.

<table id="table_7895B1E800934117A19A96380F0CF91B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formatage </th>
   <th colname="col2" class="entry"> Paires clé-valeur unique </th>
   <th colname="col3" class="entry"> Paires clé-valeur multiples </th>
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

## Delimiters and Separators {#delimiters-separators}

The characters that separate values within and between keys and values are known as *`delimiters`* and *`separators`*. Elles deviennent particulièrement importantes lorsque vous envoyez des segments à une destination dans un format de série. La sérialisation permet de transmettre plusieurs valeurs à l'aide d'une clé unique et de combiner des paires clé-valeur. Les délimiteurs et les séparateurs sont définis comme suit :

* **Séparateur de valeur clé :** Sépare une clé et une valeur dans une paire clé-valeur.
* **Délimiteur de valeur clé :** Sépare les ensembles de paires clé-valeur.
* **Séparateur de série :** Sépare plusieurs valeurs dans des ensembles de paires clé-valeur sérialisées.

## Exemples {#examples}

With [!UICONTROL Destination Builder] you can format key-value data in several different ways. Examinons quelques exemples de chaque type.

<table id="table_C2FBDC887C8C4CC88B1B2A7CF8E2795F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exemples de paires clé-valeur </th> 
   <th colname="col2" class="entry"> Exemple </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Clé unique standard</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 </code> </p> </td> 
   <td colname="col3"> <p>Jeu simple de paires clé-valeur. L'exemple contient les éléments suivants : </p> 
    <ul id="ul_28C0CB005B264373926CA5D7418EE845"> 
     <li id="li_B6D300DBA9064F0BA743BA9B04339511">Clé : X </li> 
     <li id="li_9A1C98D5C9124FF1B4F032668576C03A">Valeurs : 1, 2 </li> 
     <li id="li_1D2828328E554176846C94F6140C0CBF">Séparateur : = </li> 
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">Délimiteur de valeur clé : &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Plusieurs paires clé-valeur</b> (sans série) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 &amp; Y = 3 &amp; Y = 4 </code> </p> </td> 
   <td colname="col3"> <p>Ensemble de plusieurs paires clé-valeur qui transmettent des valeurs avec des ensembles de valeurs clés distincts. L'exemple contient les éléments suivants : </p> 
    <ul id="ul_7FB22A43B435463D9F209067FF2C3619"> 
     <li id="li_7487657F6C2F48F5A4C4C9F9E8FB3B4B">Clés : X, Y </li> 
     <li id="li_B828CF81DAB8443FBB2EDF6538A63B3C">Valeurs : 1, 2, 3, 4 </li> 
     <li id="li_EA4C95F6C93D435EB79237E38CE6F011">Séparateur : = </li> 
     <li id="li_45984AE2B581498299054BA5276D461D">Délimiteur de valeur clé : &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Clé unique en série</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 ; 3 </code> </p> </td> 
   <td colname="col3"> <p>Jeu de valeurs clés qui transmet plusieurs valeurs avec une clé unique. Cette clé comportant plusieurs valeurs, elle est connue sous le nom de paire clé-valeur sérialisée. L'exemple contient les éléments suivants : </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">Clé : X </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">Valeurs : 1, 2, 3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">Séparateur : = </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">Séparateur de série : point-virgule </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Plusieurs paires clé-valeur</b> (serial) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 &amp; Y = 3 ; 4 </code> </p> </td> 
   <td colname="col3"> <p>Ensemble de plusieurs paires clé-valeur qui transmettent plusieurs valeurs sur des clés distinctes. L'exemple contient les éléments suivants : </p> 
    <ul id="ul_CB50133B2E944818B9F2A0586EF69774"> 
     <li id="li_FD3D7ECC2BF046E99B1ED0B73EFE341F">Clés : X, Y </li> 
     <li id="li_2BADC98C4CE74BBBBA1DC446D24615AC">Valeurs : 1, 2, 3, 4 </li> 
     <li id="li_4125435175AD4A43A44B980B28F32364">Séparateur : = </li> 
     <li id="li_48CFC279B2514F4FB2935B05FC7F287A">Délimiteur: &amp; </li> 
     <li id="li_576C731F2FAF47FD92F55345CD6D36A0">Séparateur de série : point-virgule </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Destination Serialization {#destination-serialized}

Une destination sérialisée combine plusieurs caractéristiques dans une chaîne unique et envoie ces informations à une destination.

<!-- c_dest_serialized.xml -->

La transmission de données sérialisées contribue à améliorer l'efficacité, car plusieurs caractéristiques se déclenchent de manière séquentielle, plutôt qu'en parallèle. Cela fournit au serveur de destination suffisamment de temps pour recevoir, traiter et renvoyer des données avant de répondre à d'autres requêtes.

### Destinations prises en charge

In [!DNL Audience Manager], you can serialize and send data to just about any destination you want to work with. However, before using this feature, you will need to know the destination [!DNL URL] and where to place some required or optional macros. Obtenez les informations sur le placement de macro depuis votre partenaire de destination. See [Destination Macros Defined](../../features/destinations/destination-macros.md#destination-macros-defined) for more information.