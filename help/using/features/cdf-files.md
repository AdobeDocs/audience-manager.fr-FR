---
description: Informations de base sur les fichiers de flux de données client (CDF) et instructions pour commencer. Commencez ici si vous souhaitez recevoir des fichiers CDF ou simplement plus d’informations.
keywords: données de deuxième niveau;deuxième niveau;données de deuxième niveau;deuxième niveau
seo-description: Informations de base sur les fichiers de flux de données client (CDF) et instructions pour commencer. Commencez ici si vous souhaitez recevoir des fichiers CDF ou simplement plus d’informations.
seo-title: Flux de données client
solution: Audience Manager
title: Flux de données client
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
feature: Flux de données client
exl-id: 118c4225-3b57-4a02-ae05-2fcbf3e5d743
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1930'
ht-degree: 3%

---

# [!UICONTROL Customer Data Feeds] {#customer-data-feeds}

Informations de base sur les fichiers [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) et instructions pour commencer. Commencez ici si vous souhaitez recevoir des [!UICONTROL CDF] fichiers ou simplement plus d’informations.

## Contenu et objectif du fichier {#file-contents-purpose}

Un fichier [!UICONTROL CDF] contient les mêmes données que celles envoyées à nos serveurs par un appel d’événement [!DNL Audience Manager] (`/event`). Cela inclut des données telles que les ID utilisateur, [!UICONTROL trait IDs], [!UICONTROL segment IDs], ainsi que tous les autres paramètres capturés par un appel d’événement. Les systèmes [!DNL Audience Manager] internes traitent les données d’événement dans un fichier [!UICONTROL CDF] dont le contenu est organisé en champs qui s’affichent dans un ordre défini. [!DNL Audience Manager] tente de générer  [!UICONTROL CDF] les fichiers toutes les heures et les stocke dans un compartiment sécurisé spécifique au client sur un  [!DNL Amazon S3] serveur. Nous fournissons ces fichiers afin que vous puissiez utiliser des données [!DNL Audience Manager] en dehors des limites imposées par notre interface utilisateur.

>[!IMPORTANT]
>
>Notez les restrictions suivantes lorsque vous utilisez des fichiers CDF :
>
>* Avant de configurer la diffusion de fichiers CDF, assurez-vous de disposer des autorisations appropriées de fournisseurs de données tiers pour l’exportation de caractéristiques tierces. Actuellement, l’Audience Manager ne prend pas en charge la fonctionnalité de l’interface utilisateur de demande d’autorisation d’exportation de fichiers CDF auprès de fournisseurs de données tiers. Contactez-les indépendamment.
>* Vous ne devez pas utiliser de fichiers [!UICONTROL CDF] comme proxy pour surveiller le trafic des pages, réconcilier les incohérences des rapports, ou pour la facturation, etc.


## Prise en main {#getting-started}

Il n’existe aucun processus en libre-service pour démarrer la diffusion de fichiers [!UICONTROL CDF]. Contactez votre [!DNL Audience Manager] consultant ou l’assistance clientèle pour commencer. Pendant la mise en oeuvre, votre représentant [!DNL Audience Manager] :

* Configurez votre compartiment de stockage [!DNL Amazon S3].
* Indiquez des informations d’authentification [!DNL S3] en lecture seule à votre compartiment de stockage de fichiers. Vous ne pourrez pas voir ni accéder aux répertoires et fichiers appartenant à d’autres clients.

Les notifications de fichier et les fichiers [!UICONTROL CDF] s’affichent dans votre compartiment [!DNL S3] lorsqu’ils sont prêts à être téléchargés. Vous êtes responsable de la surveillance et du téléchargement des fichiers à partir du répertoire [!DNL S3] qui vous est assigné. Voir [Notifications de traitement des fichiers de flux de données client](#cdf-file-processing-notifications).

## Étapes suivantes {#next-steps}

Les sections ci-dessous et la [FAQ sur le flux de données client](../faq/faq-cdf.md) peuvent vous aider à vous familiariser avec ce service.

## [!UICONTROL Customer Data Feed] Contenu défini {#cdf-defined}

Répertorie et définit les éléments de données et les tableaux dans un fichier [!UICONTROL CDF], par ordre d’apparition. Les définitions incluent les types de données, mais ces informations ne font pas partie d’un fichier [!UICONTROL CDF].

## Définitions {#definitions}

Un fichier [!UICONTROL CDF] contient certains ou tous les champs définis ci-dessous. Pour plus d’informations sur l’organisation interne des fichiers, voir [Structure de fichier de flux de données client](#cdf-file-structure).

<table id="table_46BC897A30C2469AB5911F5B85A3FAA7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Type de données </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> Event Time</code> </p> </td> 
   <td colname="col2"> <p>Horodatage </p> </td> 
   <td colname="col3"> <p>Heure à laquelle un fichier CDF a été traité par les <span class="wintitle"> serveurs de collecte de données</span> (DCS). L’horodatage utilise le format <i>aaaa-mm-jj hh:mm:ss</i> et est défini dans le fuseau horaire UTC. </p> <p> <p>Remarque : L’ heure de l’événement <i>n’est pas</i> : <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">Heure de l’événement de page ou de l’appel d’événement lui-même, bien qu’elle puisse être proche de cette heure. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Lié à l’heure DCS dans le nom de fichier. Voir aussi <a href="#different-processing-times"> Customer Data Feed File Name Times et File Content Times..</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Il s’agit de l’<span class="wintitle"> identifiant utilisateur unique</span> (UUID), qui est un identifiant d’appareil à 38 chiffres pour le visiteur de votre site. Voir également <a href="../reference/ids-in-aam.md">Index des ID dans Audience Manager</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>Numérique </p> </td> 
   <td colname="col3"> <p>L’identifiant du conteneur qui déclenche les synchronisations des identifiants. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>Tableau numérique </p> </td> 
   <td colname="col3"> <p>Tableau d’identifiants de caractéristiques qui contient toutes les caractéristiques qu’un visiteur a réalisées (pour lesquelles il est qualifié) dans l’appel d’événement. </p> <p>Notez que le tableau peut contenir des caractéristiques pour lesquelles le visiteur s’était qualifié avant et pour lesquelles il se qualifie à nouveau via cet appel d’événement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>Tableau numérique </p> </td> 
   <td colname="col3"> <p>Tableau d’identifiants de segment qui contient tous les segments qu’un visiteur a réalisés (pour lesquels il est qualifié) dans l’appel d’événement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Chaîne qui capture tous les paramètres (variables, identifiants, paires clé-valeur, identifiants publicitaires d’appareils, etc.) transmis lors de l’appel d’événement. </p> <p>Exemple raccourci : </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer Data Type</code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>URL non codée de la page de référence (le cas échéant). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP Data Type</code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Adresse IP du visiteur capturé dans l’appel d’événement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>ID <span class="keyword"> Experience Cloud</span> (MID) attribué au visiteur du site. Voir aussi <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies et service Adobe Experience Platform Identity</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>Tableau numérique </p> </td> 
   <td colname="col3"> <p>Tableau d’identifiants de segment contenant les segments précédemment réalisés et les nouveaux segments pour lesquels le visiteur est qualifié. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>Tableau numérique </p> </td> 
   <td colname="col3"> <p>Tableau d’identifiants de caractéristiques propriétaires et tiers contenant les caractéristiques précédemment réalisées et les nouvelles caractéristiques pour lesquelles le visiteur s’est qualifié depuis le dernier flux de données généré. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Structure de fichier {#cdf-file-structure}

Répertorie et définit la structure de données d’un fichier [!UICONTROL CDF]. Cela inclut la séquence de données, les délimiteurs et les séparateurs de champ, un mappage de fichier de données et un fichier d’exemple.

## Identifiants de champ de données et séquence {#identifiers-and-sequence}

[!UICONTROL CDF] Les fichiers ne contiennent pas de colonnes ou d’en-têtes de champ étiquetés. À la place, un fichier [!UICONTROL CDF] définit des champs et des tableaux avec des caractères [!DNL ASCII] non imprimables. En outre, le fichier [!UICONTROL CDF] répertorie chaque champ et tableau dans un ordre spécifique. La compréhension des identifiants de champ et de l’ordre vous aidera à analyser correctement le fichier.

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elément de fichier CDF </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Séparateurs de champs et délimiteurs </p> </td> 
   <td colname="col2"> <p>Ces caractères non imprimables définissent les éléments et la structure de votre fichier CDF : </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a (ASCII <code> 001</code> ou <code> ^A</code>) sépare les données de champs individuels par un indicateur d’espace non imprimable. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b (ASCII <code> 002</code> ou <code> ^B</code>) sépare les données d’un tableau et les paramètres de requête. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c (ASCII <code> 003</code> ou <code> ^C</code>) définit les paires clé-valeur. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Séquence de champ </p> </td> 
   <td colname="col2"> <p> <p>Important : <span class="keyword"> Audience Manager</span> se réserve le droit d’ajouter de nouveaux champs à la fin du fichier CDF dans les prochaines versions. Cela signifie que la conception technique de votre système d’analyse de fichiers ne doit pas supposer un nombre fixe de colonnes (bien qu’elle puisse supposer un ordre fixe pour les colonnes existantes). </p> </p> <p>Les données de votre fichier CDF apparaissent dans l’ordre indiqué ci-dessous. </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">Heure de l’événement </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Device  </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">ID de conteneur </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">Caractéristiques réalisées </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">Segments réalisés </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Paramètres de requête </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">Adresse IP </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">ID de périphérique Experience Cloud (ou MID). Voir aussi <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies et service Adobe Experience Platform Identity</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">Tous les segments </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">Toutes les caractéristiques </li> 
     </ol> </p> <p>Pour consulter la description des champs, voir <a href="#cdf-defined"> Contenu du flux de données client défini</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL CDF] Mappage de fichiers {#cdf-file-map}

[!UICONTROL CDF] Les données de fichier s’affichent dans l’ordre indiqué ci-dessous.

![](assets/sequence-map.png)

## Identification des tableaux

Les tableaux d’un fichier [!UICONTROL CDF] commencent et se terminent par le séparateur de champ `Ctrl + a` . Cela fait apparaître le premier élément d’un tableau comme un champ de données autonome. Par exemple, le tableau [!UICONTROL traits] réalisé commence par `^A1234`. Le délimiteur de tableau et l’identifiant `^B5678` suivent cette entrée. Par conséquent, vous pouvez être tenté de penser que le premier élément du tableau [!UICONTROL traits] réalisé est ID 5678 (car il commence par `^B`). Ce n’est pas le cas, c’est pourquoi vous devez connaître la séquence et la structure d’un fichier de données. Même si le premier élément du tableau [!UICONTROL trait] réalisé (ou de l’un des autres tableaux d’un fichier [!UICONTROL CDF]) commence par `^A`, l’ordre d’apparition ou de position dans le fichier définit le début d’un tableau. De plus, le premier élément d’un tableau est toujours séparé de l’entrée précédente par `^A`.

## Exemple de fichier [!UICONTROL CDF] {#sample-file}

Un exemple de fichier [!UICONTROL CDF] peut ressembler à ce qui suit. Nous avons inséré des sauts de ligne dans cet exemple pour l’aider à s’adapter à la page.

![](assets/CDF-sample.png)

## [!UICONTROL Customer Data Feed] Conventions de dénomination des fichiers {#cdf-naming-conventions}

Les sections ci-dessous répertorient et définissent les éléments de votre nom de fichier [!UICONTROL CDF].

## [!UICONTROL CDF] Nom du fichier : Syntaxe et exemple {#cdf-file-name}

Un nom de fichier [!UICONTROL CDF] type contient les éléments répertoriés ci-dessous. Remarque : *italics* indique un espace réservé variable :

### Syntaxe

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF-PARTNER-ID-AAM PROCESS-ID_0.gz
```

### Exemple

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

Dans votre compartiment de stockage [!DNL S3], les fichiers sont triés par ordre croissant par identifiant de partenaire ([!UICONTROL PID]), jour et heure.

## [!UICONTROL CDF] Définition des éléments du nom de fichier {#cdf-file-name-elements}

Le tableau suivant répertorie et définit les éléments d’un nom de fichier [!UICONTROL CDF].

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elément Nom du fichier </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> s3://aam-cdf/</code> </p> </td> 
   <td colname="col2"> <p>Il s’agit du compartiment de stockage racine par défaut de votre fichier CDF sur un serveur Amazon S3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>your S3 bucket name</i> </code> </p> </td> 
   <td colname="col2"> <p>Nom du compartiment S3 en lecture seule qui contient vos fichiers CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Date à laquelle votre fichier a été traité. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>Valeur horaire exprimée en notation de 24 heures et définie dans le fuseau horaire UTC. Voir aussi <a href="#different-processing-times"> Customer Data Feed File Name Times et File Content Times..</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Votre identifiant de partenaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AAM process ID</i>_0</code> </p> </td> 
   <td colname="col2"> <p>Identifiant de processus <span class="keyword"> Audience Manager interne</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>Extension de fichier gzip. Les fichiers CDF sont compressés par gzip. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Notifications de traitement de fichier {#cdf-file-processing-notifications}

[!DNL Audience Manager] écrit un  `.info` fichier dans votre  [!DNL S3] répertoire pour vous informer du moment où votre  [!UICONTROL Customer Data File] ([!UICONTROL CDF]) est prêt pour le téléchargement. Le fichier `.info` comprend également des métadonnées formatées [!DNL JSON] sur le contenu de vos fichiers [!UICONTROL CDF]. Consultez cette section pour plus d’informations sur la syntaxe et les champs utilisés par ce fichier de notification.

## Exemple de fichier d’informations {#sample-info-file}

Chaque fichier `.info` contient une section `Files` et `Totals`. La section `Files` contient un tableau contenant des mesures spécifiques pour chaque fichier horaire. La section `Totals` contient des mesures agrégées dans tous vos fichiers [!UICONTROL CDF] pour un jour particulier. Le contenu de votre fichier `.info` peut ressembler à l’exemple suivant.

```js
{
    "Files": [
        {
            "FileByteSize": 2709730,
            "FileChecksumMD5": "a9ea418e79511642cff11c2a898037dc-1",
            "FileName": "AAM_CDF_1109_000000_0.gz",
            "FileSequenceNumber": 1
        },
        {
            "FileByteSize": 2783351,
            "FileChecksumMD5": "7b469485d60274b6991acd0817855840-3",
            "FileName": "AAM_CDF_1109_000001_0.gz",
            "FileSequenceNumber": 2
        }
    ],
    "Totals": {
        "Day": "2017-09-26",
        "Hour": "18",
        "TotalByteSize": 150092997,
        "TotalNumberFiles": 2
    }
}
```

## Champs du fichier d’informations définis {#info-file-fields-defined}

Les tableaux suivants répertorient et définissent les éléments dans un fichier [!UICONTROL CDF] `.info`.

### Objet Fichiers

<table id="table_582101B414864DA991CE813A7937ECC6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Files</code> </p> </td> 
   <td colname="col2"> <p>Commence le tableau contenant des métadonnées sur vos fichiers CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>Taille de fichier en octets. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>L’ETag Amazon S3. Le nombre suivant le trait d’union indique le nombre de parties utilisées pour créer le fichier lors du chargement en plusieurs parties. <code> ETag</code> n’est pas identique à la somme de contrôle MD5 du fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>Nom du fichier. Voir <a href="#cdf-naming-conventions"> Conventions de dénomination des fichiers de flux de données client</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileSequenceNumber</code> </p> </td> 
   <td colname="col2"> <p>Un numéro d’index pour chaque fichier. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Objet Totaux

<table id="table_44F0B2D229E84A5DB3041760B1A50858"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Totals</code> </p> </td> 
   <td colname="col2"> <p>Commence l’objet qui contient des données agrégées sur tous vos fichiers CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>Jour pour lequel les données sont disponibles. Utilise le format <i>aaaa-mm-jj</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>Heure pour laquelle les données sont disponibles. Utilise le format 24 heures défini dans le fuseau horaire UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>Taille totale de tous les fichiers CDF pour cette date, en octets. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>Nombre total de fichiers chargés dans votre répertoire S3. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Les heures des noms de fichier et les heures du contenu du fichier diffèrent {#different-processing-times}

Votre fichier [!UICONTROL CDF] contient des horodatages dans le nom de fichier et le contenu du fichier. Ces horodatages enregistrent différents processus d’événement pour le même fichier [!UICONTROL CDF]. Il n’est pas rare de voir des horodatages différents dans le nom et le contenu d’un même fichier. La compréhension de chaque horodatage peut vous aider à éviter les erreurs courantes lorsque vous utilisez ces données ou essayez de les trier par heure.

## Localisation des [!UICONTROL CDF] horodatages du fichier {#locating-timestamps}

[!UICONTROL CDF] Les fichiers enregistrent le temps différemment dans 2 emplacements distincts.

![](assets/cdf-timestamp.png)

## Présentation de la différence entre les horodatages {#understanding-timestamps}

Le tableau suivant fournit des détails supplémentaires sur les horodatages de vos fichiers [!UICONTROL CDF], ainsi que des informations sur la manière de les utiliser correctement.

| Emplacement de l’horodatage | Description |
|--- |--- |
| Nom de fichier | L’horodatage de votre nom de fichier [!DNL CDF] indique l’heure à laquelle [!DNL Audience Manager] a commencé à préparer votre fichier pour la diffusion. Cet horodatage est défini dans le fuseau horaire [!DNL UTC]. Il utilise le paramètre `hour=`, avec une heure formatée en tant qu’heure à 2 chiffres en notation à 24 heures. Cette heure peut être différente de l’heure de l’événement enregistrée dans le contenu du fichier. Lorsque vous travaillez avec des fichiers [!DNL CDF], vous remarquerez parfois que votre compartiment [!DNL S3] est vide pendant une heure donnée. Un compartiment vide signifie l’une des significations suivantes :<ul><li>Il n&#39;y a pas de données pour cette heure particulière. </li><li> Nos serveurs sont soumis à de lourdes charges et ne peuvent pas traiter les fichiers pendant une heure donnée. Lorsque le serveur récupère, il place les fichiers qui auraient dû être placés dans un intervalle de temps antérieur dans un compartiment avec une valeur d’heure ultérieure. Par exemple, vous verrez ceci lorsqu’un fichier qui aurait dû se trouver dans le compartiment 17 de l’heure apparaîtra dans le compartiment 18 de l’heure (avec `hour=18` dans le nom de fichier). Dans ce cas, le serveur a probablement commencé à traiter votre fichier dans l’heure 17, mais il n’a pas pu le terminer dans cet intervalle. Au lieu de cela, le fichier est envoyé vers l’intervalle horaire suivant.</li></ul><br>**Important** : N’utilisez pas l’horodatage du nom de fichier pour regrouper les événements par heure. Si vous devez effectuer un groupement par heure, utilisez l’horodatage `EventTime` dans le contenu du fichier. |
| Contenu du fichier | L’horodatage du contenu de votre fichier [!DNL CDF] marque l’heure à laquelle [!DNL Data Collection Servers] a commencé à traiter le fichier. Cet horodatage est défini dans le fuseau horaire [!DNL UTC]. Il utilise le champ `EventTime`, avec l’heure au format *`yyyy-mm-dd hh:mm:ss`*. Cette heure est proche de l’heure réelle de l’événement sur la page, mais elle peut être différente de l’indicateur d’heure dans le nom du fichier. <br> **Conseil** : Contrairement à l’ `hour=` horodatage du nom de fichier, vous pouvez utiliser  `EventTime` pour regrouper les données par heure. |

>[!MORELIKETHIS]
>
>* [FAQ sur le flux de données client](../faq/faq-cdf.md)

