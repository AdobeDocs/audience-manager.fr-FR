---
description: Informations de base sur les fichiers CDF (Customer Data Feed) et instructions de prise en main. Commencez ici si vous souhaitez recevoir des fichiers CDF ou simplement obtenir plus d’informations.
keywords: données secondaires;tiers;données secondaires;données secondaires
seo-description: Basic information about Customer Data Feed (CDF) files and instructions on how to get started. Start here if you're interested in receiving CDF files or just want more information.
seo-title: Customer Data Feeds
solution: Audience Manager
title: Flux de données client
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
feature: Customer Data Feeds
exl-id: 118c4225-3b57-4a02-ae05-2fcbf3e5d743
source-git-commit: 89137248aa47573f5b65e387a152f651419da827
workflow-type: tm+mt
source-wordcount: '1988'
ht-degree: 2%

---

# [!UICONTROL Customer Data Feeds] {#customer-data-feeds}

Informations de base sur les fichiers [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) et instructions pour démarrer. Commencez ici si vous souhaitez recevoir des fichiers [!UICONTROL CDF] ou simplement obtenir plus d&#39;informations.

## Contenu et objectif du fichier {#file-contents-purpose}

Un fichier [!UICONTROL CDF] contient les mêmes données qu’un appel d’événement [!DNL Audience Manager] (`/event`) envoie à nos serveurs. Cela inclut les données telles que les identifiants d’utilisateur, les [!UICONTROL trait IDs], les [!UICONTROL segment IDs] et tous les autres paramètres capturés par un appel d’événement. Les systèmes de [!DNL Audience Manager] internes traitent les données d’événement dans un fichier [!UICONTROL CDF] avec le contenu organisé en champs qui apparaissent dans un ordre défini. [!DNL Audience Manager] tente de générer des fichiers [!UICONTROL CDF] toutes les heures et les stocke dans un compartiment sécurisé et spécifique au client sur un serveur [!DNL Amazon S3]. Nous fournissons ces fichiers afin que vous puissiez travailler avec des données [!DNL Audience Manager] en dehors des limites imposées par notre interface utilisateur.

>[!IMPORTANT]
>
>Notez les restrictions suivantes lorsque vous utilisez des fichiers CDF :
>
>* Avant de configurer la diffusion des fichiers CDF, vérifiez que vous disposez des autorisations appropriées de fournisseurs de données tiers pour l’exportation de caractéristiques tierces. Audience Manager ne prend actuellement pas en charge la fonctionnalité dans l’interface utilisateur pour demander l’autorisation d’exportation de diffusion de fichiers CDF à des fournisseurs de données tiers. Veuillez donc les contacter indépendamment.
>* Vous ne devez pas utiliser les fichiers [!UICONTROL CDF] comme proxy pour surveiller le trafic de pages, réconcilier les incohérences de rapports, ou pour la facturation, etc.

## Prise en main {#getting-started}

Il n’existe aucun processus en libre-service pour démarrer [!UICONTROL CDF] diffusion de fichiers. Contactez votre consultant [!DNL Audience Manager] ou l’assistance clientèle pour commencer. Pendant la mise en œuvre, votre représentant [!DNL Audience Manager] :

* Configurez votre compartiment de stockage [!DNL Amazon S3].
* Fournissez des informations d’authentification [!DNL S3] en lecture seule à votre compartiment de stockage de fichiers. Vous ne pourrez pas voir ni accéder aux répertoires et fichiers appartenant à d&#39;autres clients.

Les notifications de fichiers et les fichiers [!UICONTROL CDF] apparaîtront dans votre compartiment [!DNL S3] lorsqu’ils seront prêts à être téléchargés. Vous êtes responsable de la surveillance et du téléchargement des fichiers à partir du répertoire [!DNL S3] qui vous a été attribué. Voir [Notifications de traitement des fichiers de flux de données client](#cdf-file-processing-notifications).

## Étapes suivantes {#next-steps}

Les sections ci-dessous et la [FAQ sur les flux de données client](../faq/faq-cdf.md) peuvent vous aider à vous familiariser avec ce service.

## Contenu [!UICONTROL Customer Data Feed] défini {#cdf-defined}

Répertorie et définit les éléments de données et les tableaux d’un fichier [!UICONTROL CDF], par ordre d’apparition. Les définitions incluent les types de données, mais ces informations ne font pas partie d’un fichier [!UICONTROL CDF].

>[!IMPORTANT]
>
>Les pixels d’événement sont exclus par défaut dans les configurations CDF. Veillez à spécifier dans votre demande à l’assistance clientèle si vous souhaitez que les pixels d’événement soient inclus dans vos fichiers CDF. Chaque pixel d’événement est renseigné sous la forme d’une ligne unique dans vos fichiers CDF.

## Définitions {#definitions}

Un fichier [!UICONTROL CDF] comprend certains ou tous les champs définis ci-dessous. Pour plus d’informations sur l’organisation interne des fichiers, voir [ Structure de fichier du flux de données client ](#cdf-file-structure).

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
   <td colname="col2"> <p>Date et heure </p> </td> 
   <td colname="col3"> <p>Heure à laquelle un fichier CDF a été traité par les serveurs de collecte de données <span class="wintitle"> (DCS</span>. La date et l’heure utilisent le format <i>aaaa-mm-jj hh:mm:ss</i> et sont définies dans le fuseau horaire UTC. </p> <p> <p>Remarque : l’heure de l’événement <i> n’est pas </i> : <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">Heure de l’événement de page ou de l’appel d’événement lui-même, bien qu’elle puisse être proche de ces heures. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Associé à l’heure du serveur de collecte de données dans le nom du fichier. Voir aussi <a href="#different-processing-times"> les heures du nom de fichier du flux de données client et les heures du contenu du fichier</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Il s’agit de l’identifiant utilisateur unique <span class="wintitle"> (UUID)</span> qui est un identifiant d’appareil de 38 chiffres pour le visiteur de votre site. Voir aussi Index <a href="../reference/ids-in-aam.md"> des identifiants dans Audience Manager</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>Numérique </p> </td> 
   <td colname="col3"> <p>L’identifiant du conteneur qui déclenche les synchronisations d’identifiant. Ce champ n’est renseigné que si vous définissez l’ID de conteneur dans le champ <i>d_nsid</i> au sein de votre implémentation de site. Sinon, la valeur par défaut de 0 ne sera pas incluse dans les fichiers CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>Tableau numérique </p> </td> 
   <td colname="col3"> <p>Tableau d’identifiants de caractéristiques qui contient toutes les caractéristiques qu’un visiteur a réalisées (pour lesquelles il a rempli les critères) dans l’appel d’événement. </p> <p>Notez que le tableau peut contenir des caractéristiques pour lesquelles le visiteur s’est qualifié auparavant et pour lesquelles il se qualifie à nouveau par le biais de cet appel d’événement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>Tableau numérique </p> </td> 
   <td colname="col3"> <p>Tableau d’identifiants de segment qui contient tous les segments qu’un visiteur a réalisés (pour lesquels il a rempli les critères) dans l’appel d’événement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Chaîne qui capture tous les paramètres (variables, identifiants, paires clé-valeur, identifiants publicitaires d’appareil, etc.) transmis lors de l’appel d’événement. </p> <p>Exemple raccourci : </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer Data Type</code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>URL non codée de la page de référence (le cas échéant). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP Data Type</code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>L’adresse IP du visiteur capturée dans l’appel d’événement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Identifiant <span class="keyword"> Experience Cloud</span> (MID) attribué au visiteur du site. Voir aussi Cookies <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> et Adobe Experience Platform Identity Service</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>Tableau numérique </p> </td> 
   <td colname="col3"> <p>Tableau d’identifiants de segment qui contient les segments précédemment réalisés et les nouveaux segments pour lesquels le visiteur est qualifié. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>Tableau numérique </p> </td> 
   <td colname="col3"> <p>Tableau d’ID de caractéristiques propriétaires et tiers qui contient les caractéristiques précédemment créées et les nouvelles caractéristiques pour lesquelles le visiteur s’est qualifié depuis le dernier flux de données généré. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Structure de fichier [!UICONTROL Customer Data Feed] {#cdf-file-structure}

Répertorie et définit la structure des données d’un fichier [!UICONTROL CDF]. Cela inclut la séquence de données, les délimiteurs et séparateurs de champ, un mappage de fichier de données et un exemple de fichier.

## Identifiants et séquence des champs de données {#identifiers-and-sequence}

Les fichiers [!UICONTROL CDF] ne contiennent pas de colonnes ou d’en-têtes de champ libellés. À la place, un fichier [!UICONTROL CDF] définit des champs et des tableaux avec des caractères [!DNL ASCII] non imprimables. En outre, le fichier [!UICONTROL CDF] répertorie chaque champ et tableau dans un ordre spécifique. Comprendre l’ordre et les identifiants des champs vous aidera à analyser correctement le fichier.

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément de fichier CDF </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Séparateurs et délimiteurs de champ </p> </td> 
   <td colname="col2"> <p>Ces caractères non imprimables définissent les éléments et la structure de votre fichier CDF : </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a (<code> 001</code> ASCII ou <code> ^A</code>) sépare les données de champs individuels avec un indicateur d’espace non imprimable. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b (<code> 002</code> ASCII ou <code> ^B</code>) sépare les données d’un tableau et les paramètres de requête. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c (<code> 003</code> ASCII ou <code> ^C</code>) définit les paires clé-valeur. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Séquence de champs </p> </td> 
   <td colname="col2"> <p> <p>Important : <span class="keyword"> Audience Manager</span> se réserve le droit d’ajouter de nouveaux champs à la fin du fichier CDF dans les prochaines versions. Cela signifie que la conception technique de votre système d'analyse de fichiers ne doit pas supposer un nombre fixe de colonnes (bien qu'elle puisse supposer un ordre fixe pour les colonnes existantes).</p> </p> <p>Les données de votre fichier CDF s’affichent dans l’ordre indiqué ci-dessous. /N peut apparaître à la place de l’un de ces champs, indiquant une valeur nulle.</p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">Heure de l’événement </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Device  </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">ID de conteneur </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">Caractéristiques réalisées </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">Segments Réalisés </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Paramètres de requête </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Référent </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">Adresse IP </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Identifiant de l’appareil Experience Cloud (ou MID). Voir aussi Cookies <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> et service d’identités Adobe Experience Platform</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">Tous les segments </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">Toutes les caractéristiques </li> 
     </ol> </p> <p>Pour obtenir la description des champs, voir <a href="#cdf-defined"> du contenu du flux de données client défini</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Mappage de fichier [!UICONTROL CDF] {#cdf-file-map}

[!UICONTROL CDF] données du fichier s’affichent dans l’ordre indiqué ci-dessous.

![](assets/sequence-map.png)

## Identification de tableaux

Les tableaux d’un fichier [!UICONTROL CDF] commencent et se terminent par le séparateur de champs `Ctrl + a`. Ainsi, le premier élément d’un tableau ressemble à un champ de données autonome. Par exemple, le tableau de [!UICONTROL traits] réalisé commence par `^A1234`. Le délimiteur de tableau et l’ID `^B5678` suivent cette entrée. Par conséquent, vous pouvez être tenté de penser que le premier élément du tableau de [!UICONTROL traits] réalisé est l’ID 5678 (car il commence par `^B`). Ce n’est pas le cas, c’est pourquoi vous devez connaître la séquence et la structure d’un fichier de données. Même si le premier élément du tableau de [!UICONTROL trait] réalisé (ou de tout autre tableau d’un fichier [!UICONTROL CDF]) commence par `^A`, l’ordre d’aspect ou de position dans le fichier définit le début d’un tableau. De plus, le premier élément d’un tableau est toujours séparé de l’entrée précédente par des `^A`.

## Exemple de fichier [!UICONTROL CDF] {#sample-file}

Un exemple de fichier [!UICONTROL CDF] pourrait ressembler à ce qui suit. Nous avons inséré des sauts de ligne dans cet exemple pour l’adapter à la page.

![](assets/CDF-sample.png)

## Conventions de dénomination des fichiers [!UICONTROL Customer Data Feed] {#cdf-naming-conventions}

Les sections ci-dessous répertorient et définissent les éléments dans votre nom de fichier [!UICONTROL CDF].

## Nom de fichier [!UICONTROL CDF] : syntaxe et exemple {#cdf-file-name}

Un nom de fichier [!UICONTROL CDF] type contient les éléments répertoriés ci-dessous. Remarque : *l’italique* indique un espace réservé de variable :

### Syntaxe

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF_PARTNER-ID_FILE-SEQUENCE_0.gz
```

### Exemple

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_0_0_0.gz
```

Dans votre compartiment de stockage [!DNL S3], les fichiers sont triés par ordre croissant par identifiant de partenaire ([!UICONTROL PID]), jour et heure.

## Éléments De Nom De Fichier [!UICONTROL CDF] Définis {#cdf-file-name-elements}

Le tableau suivant répertorie et définit les éléments d’un nom de fichier [!UICONTROL CDF].

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément de nom de fichier </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> s3://aam-cdf/</code> </p> </td> 
   <td colname="col2"> <p>Il s’agit du compartiment de stockage racine par défaut pour votre fichier CDF sur un serveur Amazon S3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>your S3 bucket name</i> </code> </p> </td> 
   <td colname="col2"> <p>Nom du compartiment S3 en lecture seule qui contient vos fichiers CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Date de traitement de votre fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>Valeur horaire exprimée dans la notation sur 24 heures et définie dans le fuseau horaire UTC. Voir aussi <a href="#different-processing-times"> les heures du nom de fichier du flux de données client et les heures du contenu du fichier</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Identifiant de votre partenaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>File Sequence</i>_0</code> </p> </td> 
   <td colname="col2"> <p>Valeurs qui identifient la séquence de fichiers. La séquence s’incrémente comme suit : 0_0_0 , 0_1_0, 0_2_0....1_0_0</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>Extension de fichier gzip. Les fichiers CDF sont compressés au format GZIP. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Notifications de traitement de fichier [!UICONTROL Customer Data Feed] {#cdf-file-processing-notifications}

[!DNL Audience Manager] écrit un fichier `.info` dans votre répertoire [!DNL S3] pour vous informer lorsque votre [!UICONTROL Customer Data File] ([!UICONTROL CDF]) est prêt à être téléchargé. Le fichier `.info` comprend également [!DNL JSON] métadonnées formatées sur le contenu de vos fichiers [!UICONTROL CDF]. Consultez cette section pour plus d’informations sur la syntaxe et les champs utilisés par ce fichier de notification.

## Exemple de fichier d’informations {#sample-info-file}

Chaque fichier `.info` contient une section `Files` et `Totals`. La section `Files` contient un tableau qui contient des mesures spécifiques pour chaque fichier horaire. La section `Totals` contient des mesures agrégées dans tous vos fichiers [!UICONTROL CDF] pour un jour spécifique. Le contenu de votre fichier `.info` peut ressembler à l’exemple suivant.

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

## Champs de fichier d’informations définis {#info-file-fields-defined}

Les tableaux suivants répertorient et définissent les éléments d’un fichier [!UICONTROL CDF] `.info`.

### File, objet

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
   <td colname="col2"> <p>Démarre le tableau qui contient les métadonnées de vos fichiers CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>Taille du fichier en octets. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>ETag Amazon S3. Le nombre qui suit le trait d’union indique le nombre de parties utilisées pour créer le fichier lors du chargement en plusieurs parties. Le <code> ETag</code> n’est pas identique à la somme de contrôle MD5 du fichier . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>Nom du fichier. Voir <a href="#cdf-naming-conventions"> des conventions de dénomination des fichiers de flux de données client</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileSequenceNumber</code> </p> </td> 
   <td colname="col2"> <p>Numéro d’index pour chaque fichier. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Totaux, objet

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
   <td colname="col2"> <p>Démarre l’objet qui contient des données agrégées sur tous vos fichiers CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>Jour de disponibilité des données. Utilise le format <i>aaaa-mm-jj</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>Heure à laquelle les données sont disponibles. Utilise le format 24 heures défini dans le fuseau horaire UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>Taille totale de tous vos fichiers CDF pour cette date en octets. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>Nombre total de fichiers chargés dans votre répertoire S3. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Les heures de nom de fichier [!UICONTROL Customer Data Feed] et de contenu de fichier sont différentes {#different-processing-times}

Votre fichier [!UICONTROL CDF] contient des horodatages dans le nom et le contenu du fichier. Ces horodatages enregistrent différents processus d’événement pour le même fichier [!UICONTROL CDF]. Il n’est pas rare de voir des horodatages différents dans le nom et le contenu d’un même fichier. Comprendre chaque horodatage peut vous aider à éviter les erreurs courantes lors de l’utilisation de ces données ou d’essayer de les trier par heure.

## Localisation des horodatages de fichier [!UICONTROL CDF] {#locating-timestamps}

[!UICONTROL CDF] fichiers enregistrent le temps différemment dans 2 emplacements distincts.

![](assets/cdf-timestamp.png)

## Comprendre la différence entre les horodatages {#understanding-timestamps}

Le tableau suivant fournit des détails supplémentaires sur les horodatages de vos fichiers [!UICONTROL CDF] ainsi que des informations sur leur utilisation correcte.

| Emplacement de l’horodatage | Description |
|--- |--- |
| Nom de fichier | La date et l’heure indiquées dans le nom de fichier de votre [!DNL CDF] correspondent à l’heure à laquelle [!DNL Audience Manager] avez commencé à préparer votre fichier pour la diffusion. Cet horodatage est défini dans le fuseau horaire [!DNL UTC]. Elle utilise le paramètre `hour=` , avec une heure formatée en tant qu’heure à 2 chiffres dans la notation de 24 heures. Cette heure peut être différente de l’heure de l’événement enregistrée dans le contenu du fichier. Lorsque vous travaillez avec des fichiers [!DNL CDF], vous remarquerez parfois que votre compartiment [!DNL S3] est vide pendant une heure particulière. Un compartiment vide signifie que peut signifier l’un des éléments suivants :<ul><li>Il n&#39;y a pas de données pour cette heure-là. </li><li> Nos serveurs sont soumis à de lourdes charges et ne peuvent traiter les fichiers pendant une heure particulière. Lorsque le serveur effectue un rattrapage, il place les fichiers qui auraient dû se trouver dans un fichier de regroupement temporel antérieur dans un regroupement avec une valeur temporelle ultérieure. Par exemple, vous verrez ceci lorsqu’un fichier qui aurait dû se trouver dans le compartiment de l’heure 17 apparaît dans le compartiment de l’heure 18 (avec `hour=18` dans le nom du fichier). Dans ce cas, le serveur a probablement commencé à traiter votre fichier au cours de l’heure 17, mais n’a pas pu le terminer dans cet intervalle de temps. Au lieu de cela, le fichier est envoyé à l’intervalle horaire suivant.</li></ul><br>**Important** : n’utilisez pas la date et l’heure du nom du fichier pour regrouper les événements par heure. Si vous devez effectuer un regroupement par heure, utilisez la date et l’heure `EventTime` dans le contenu du fichier. |
| Contenu du fichier | L’horodatage dans le contenu de votre fichier [!DNL CDF] indique l’heure à laquelle le [!DNL Data Collection Servers] a commencé à traiter le fichier. Cet horodatage est défini dans le fuseau horaire [!DNL UTC]. Il utilise le champ `EventTime`, avec l’heure au format *`yyyy-mm-dd hh:mm:ss`*. Cette heure est proche de l’heure réelle de l’événement sur la page, mais elle peut être différente de l’indicateur d’heure dans le nom de fichier. <br> **Conseil** : contrairement à l’horodatage `hour=` dans le nom de fichier, vous pouvez utiliser `EventTime` pour regrouper les données par heure. |

>[!MORELIKETHIS]
>
>* [FAQ sur le flux de données client](../faq/faq-cdf.md)
