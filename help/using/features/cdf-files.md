---
description: Informations de base sur les fichiers CDF (Customer Data Feed) et instructions pour la prise en main. Commencez ici si vous souhaitez recevoir des fichiers CDF ou souhaitez simplement plus d'informations.
keywords: données tierces ; tiers ; Données tierces ; tiers
seo-description: Informations de base sur les fichiers CDF (Customer Data Feed) et instructions pour la prise en main. Commencez ici si vous souhaitez recevoir des fichiers CDF ou souhaitez simplement plus d'informations.
seo-title: Flux de données client
solution: Audience Manager
title: Flux de données client
uuid: a 5 de 1630-2 c 7 a -4862-9 ba 0-f 8343 cdd 2782
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Customer Data Feeds {#customer-data-feeds}

Basic information about [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) files and instructions on how to get started. Start here if you're interested in receiving [!UICONTROL CDF] files or just want more information.

## File Contents and Purpose {#file-contents-purpose}

<!-- cdf-intro.xml -->

A [!UICONTROL CDF] file contains the same data that an [!DNL Audience Manager] event call ( `/event`) sends to our servers. Cela inclut les données telles que l'utilisateur - id, ID de caractéristique, ID de segment et tous les autres paramètres capturés par un appel d'événement. Internal [!DNL Audience Manager] systems processes event data into a [!UICONTROL CDF] file with content organized into fields that appear in a set order. [!DNL Audience Manager] tente de générer [!UICONTROL CDF] des fichiers par heure et de les stocker dans un compartiment sécurisé spécifique aux clients sur un [!DNL Amazon S3] serveur. We provide these files so you can work with [!DNL Audience Manager] data outside of the limits imposed by our user interface.

>[!NOTE]
>
>You should not use [!UICONTROL CDF] files as a proxy to monitor page traffic, reconcile report discrepancies, or for billing, etc.

## Prise en main {#getting-started}

There is no self-service process to start [!UICONTROL CDF] file delivery. Contact your [!DNL Audience Manager] consultant or Customer Care to get started. During implementation, your [!DNL Audience Manager] representative will:

* Set up your [!DNL Amazon S3] storage bucket.
* Provide read-only [!DNL S3] authentication credentials to your file storage bucket. Vous ne pourrez pas afficher ni accéder aux répertoires et aux fichiers qui appartiennent à d'autres clients.

File notifications and [!UICONTROL CDF] files will appear in your [!DNL S3] bucket when they're ready for download. You're responsible for monitoring and downloading files from your assigned [!DNL S3] directory. See [Customer Data Feed File Processing Notifications](#cdf-file-processing-notifications).

## Étapes suivantes {#next-steps}

The sections below and the [Customer Data Feed FAQ](../faq/faq-cdf.md) can help you become more familiar with this service.

## Customer Data Feed Contents Defined {#cdf-defined}

Lists and defines the data elements and arrays in a [!UICONTROL CDF] file, by order of appearance. Definitions include data types, but this information is not part of a [!UICONTROL CDF] file.

## Définitions {#definitions}

<!-- cdf-contents-defined.xml -->

A [!UICONTROL CDF] file includes some or all of the fields defined below. For information about internal file organization, see [Customer Data Feed File Structure](#cdf-file-structure).

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
   <td colname="col1"> <p><code> Heure de l'événement</code> </p> </td> 
   <td colname="col2"> <p>Horodatage </p> </td> 
   <td colname="col3"> <p>The time a CDF file was processed by the <span class="wintitle"> Data Collection Servers</span> (DCS). The timestamp uses the <i>yyyy-mm-dd hh:mm:ss</i> format and is set in the UTC time zone. </p> <p> <p>Note: The Event Time <i>is not</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">Heure de l'événement de page ou appel d'événement lui-même, bien qu'il soit peut-être proche de ces heures. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Associé à l'heure du serveur de collecte de données dans le fichier - nom. See also, <a href="#different-processing-times"> Customer Data Feed File Name Times and File Content Times...</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>Device </code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>This is the <span class="wintitle"> Unique User ID</span> (UUID), which is a 38-digit device ID for your site visitor. Voir également <a href="../reference/ids-in-aam.md">Index des ID dans Audience Manager</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> ID de conteneur</code> </p> </td> 
   <td colname="col2"> <p>Numérique </p> </td> 
   <td colname="col3"> <p>ID du conteneur qui déclenche les synchronisations d'ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Caractéristiques réalisées</code> </p> </td> 
   <td colname="col2"> <p>Tableau numérique </p> </td> 
   <td colname="col3"> <p>Tableau des ID de caractéristique qui contient toutes les caractéristiques qu'un visiteur a générées (qualifiées pour) dans l'appel d'événement. </p> <p>Notez que le tableau peut contenir des caractéristiques pour lesquelles le visiteur a déjà été qualifié et pour lesquelles elles sont requalifiées par l'intermédiaire de cet appel d'événement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Segments réalisés</code> </p> </td> 
   <td colname="col2"> <p>Tableau numérique </p> </td> 
   <td colname="col3"> <p>Tableau des ID de segment qui contient tous les segments qu'un visiteur a atteints (qualifiés pour) dans l'appel d'événement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Paramètres de requête</code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Chaîne qui capture tous les paramètres (variables, ID, paires clé-valeur, etc.) transmis lors de l'appel d'événement. </p> <p>Exemple abrégé : </p> <p> <code> d_ rtbd : json, c_ contextdata. a. carriername : mobile, c_ contextdata. a. adid : 92 D 56353-49 C 5-431 E-B 474-FC 528 D 585810, c_ contextdata. a, runmode : Application, c_ contextdata. a. dayssincelastupgrade : 61, d_ cid_ ic : xid % 01 EACB 6 E 40-AC 65-4012-9 FE 9-ABD 59965 E 9 C 4% 011, c_ contextdata. a. prevsessionlength : 583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Type de données référent</code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>URL non codée de la page de référence (le cas échéant). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Type de données IP</code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Adresse IP du visiteur capturé dans l'appel d'événement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Mcdevice </code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>The <span class="keyword"> Experience Cloud</span> ID (MID) assigned to the site visitor. See also, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and theExperience Cloud ID service</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Tous les segments</code> </p> </td> 
   <td colname="col2"> <p>Tableau numérique </p> </td> 
   <td colname="col3"> <p>Tableau d'ID de segment qui contient des segments précédemment traduits et de nouveaux segments pour lesquels le visiteur est qualifié. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Toutes les caractéristiques</code> </p> </td> 
   <td colname="col2"> <p>Tableau numérique </p> </td> 
   <td colname="col3"> <p>Tableau des identifiants de caractéristiques propriétaires et tiers qui contiennent des caractéristiques précédemment traduites et de nouvelles caractéristiques que le visiteur a qualifiées depuis le dernier flux de données généré. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Structure {#cdf-file-structure}

Lists and defines the data structure of a [!UICONTROL CDF] file. Cela inclut la séquence de données, les délimiteurs de champs et les séparateurs, une carte de fichiers de données et un exemple de fichier.

## Data Field Identifiers and Sequence {#identifiers-and-sequence}

<!-- cdf-file-structure.xml -->

[!UICONTROL CDF] ne contient pas de colonnes étiquetées ni d'en-têtes de champ. Instead, a [!UICONTROL CDF] file defines fields and arrays with non-printing [!DNL ASCII] characters. Also, the [!UICONTROL CDF] file lists each field and array in a specific order. La compréhension des identifiants de champ et de l'ordre vous aidera à analyser correctement le fichier.

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elément Fichier CDF </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Séparateurs de champs et délimiteurs </p> </td> 
   <td colname="col2"> <p>Ces caractères non imprimables définissent les éléments et la structure de votre fichier CDF : </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a (ASCII <code> 001</code> or <code> ^A</code>) separates data in individual fields with a non-printing space indicator. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b (ASCII <code> 002</code> or <code> ^B</code>) separates data an array and request parameters. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c (ASCII <code> 003</code> or <code> ^C</code>) defines key-value pairs. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Séquence de champs </p> </td> 
   <td colname="col2"> <p> <p>Important: <span class="keyword"> Audience Manager</span> reserves the right to add new fields to the end of the CDF file in future releases. Cela signifie que la conception technique de votre système d'analyse de fichiers ne doit pas supposer un nombre fixe de colonnes (bien qu'elle puisse supposer un ordre fixe pour les colonnes existantes). </p> </p> <p>Les données contenues dans votre fichier CDF s'affichent dans l'ordre indiqué ci-dessous. </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">Heure de l'événement </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Device  </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">ID de conteneur </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">Caractéristiques réalisées </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">Segments réalisés </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Paramètres de requête </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">Adresse IP </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Identifiant de périphérique d'Experience Cloud (ou MID). See also, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID Service</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">Tous les segments </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">Toutes les caractéristiques </li> 
     </ol> </p> <p>For field descriptions, see <a href="#cdf-defined"> Customer Data Feed Contents Defined</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## CDF File Map {#cdf-file-map}

[!UICONTROL CDF] les données de fichier apparaissent dans l'ordre indiqué ci-dessous.

![](assets/sequence-map.png)

## Identification des tableaux

Arrays in a [!UICONTROL CDF] file start and end with the `Ctrl + a` field separator. Le premier élément d'un tableau s'affiche ainsi comme un champ de données autonome. For example, the realized traits array starts with `^A1234`. The array delimiter and ID `^B5678` follows this entry. As a result, you might be tempted to think that the first element in the realized traits array is ID 5678 (because it starts with `^B`). Ce n'est pas le cas, c'est pourquoi vous devez connaître la séquence et la structure d'un fichier de données. Even though the first element in the realized trait array (or any of the other arrays in a [!UICONTROL CDF] file) starts with `^A`, the order of appearance or position in the file defines the start of an array. And, the first element in an array is always separated from the preceding entry by `^A`.

## Sample CDF File {#sample-file}

A sample [!UICONTROL CDF] file could look similar to the following. Dans cet exemple, nous avons inséré des sauts de ligne pour l'adapter à la page.

![](assets/CDF-sample.png)

## Customer Data Feed File Naming Conventions {#cdf-naming-conventions}

The sections below list and define the elements in your [!UICONTROL CDF] file name.

## CDF File Name: Syntax and Example {#cdf-file-name}

<!-- cdf-file-name.xml -->

A typical [!UICONTROL CDF] file name contains the elements listed below. Note, *italics* indicates a variable placeholder:

* **Syntaxe**

<pre><code>s 3 : //aam-cdf/your<i>s 3 bucket name</i>/day =<i>yyyy-mm-jj</i>/hour =<i>hh</i>/<i>AAM_ CDF_ partner ID_ AAM</i>_0.gz</code>
</pre>

* **Exemple**

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

In your [!DNL S3] storage bucket, files are sorted in ascending order by Partner ID ([!UICONTROL PID]), day, and hour.

## CDF File Name Elements Defined {#cdf-file-name-elements}

The following table lists and defines the elements in a [!UICONTROL CDF] file name.

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fichier - nom de l'élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> s 3 : //aam-cdf/</code> </p> </td> 
   <td colname="col2"> <p>Il s'agit du compartiment de stockage racine par défaut pour votre fichier CDF sur un serveur Amazon S 3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>votre nom de compartiment S 3</i></code> </p> </td> 
   <td colname="col2"> <p>nom de l'intervalle en lecture seule, S 3 qui contient vos fichiers CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day =<i>yyyy-mm-jj</i></code> </p> </td> 
   <td colname="col2"> <p>date de traitement de votre fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour =<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>Valeur temporelle exprimée en notation 24 heures et définie dans le fuseau horaire UTC. See also, <a href="#different-processing-times"> Customer Data Feed File Name Times and File Content Times...</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>ID de partenaire</i></code> </p> </td> 
   <td colname="col2"> <p>Votre ID de partenaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>ID de processus AAM</i>_ 0</code> </p> </td> 
   <td colname="col2"> <p>An internal, <span class="keyword"> Audience Manager</span> process ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>Extension de fichier gzip. Les fichiers CDF sont compressés. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Processing Notifications {#cdf-file-processing-notifications}

[!DNL Audience Manager] écrit `.info` un fichier dans [!DNL S3] votre répertoire pour vous informer lorsque votre [!UICONTROL Customer Data File] ([!UICONTROL CDF]) est prêt à être téléchargé. The `.info` file also includes [!DNL JSON] formatted metadata about the contents of your [!UICONTROL CDF] files. Consultez cette section pour plus d'informations sur la syntaxe et les champs utilisés par ce fichier de notification.

## Sample Info File {#sample-info-file}

<!-- cdf-notifications.xml -->

Each `.info` file contains a `Files` and `Totals` section. The `Files` section contains an array that holds specific metrics for each hourly file. The `Totals` section contains metrics aggregated across all your [!UICONTROL CDF] files for a particular day. The contents of your `.info` file could look similar to the following example.

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

## Info File Fields Defined {#info-file-fields-defined}

The following tables list and define the elements in a [!UICONTROL CDF] `.info` file.

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
   <td colname="col1"> <p> <code> Fichiers</code> </p> </td> 
   <td colname="col2"> <p>Commence le tableau contenant les métadonnées relatives à vos fichiers CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filebytesize</code> </p> </td> 
   <td colname="col2"> <p>Taille du fichier en octets. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Amazon S 3 etag. Le nombre qui suit le trait d'union indique le nombre de parties utilisées pour générer le fichier pendant le chargement en plusieurs parties. <code> Etag</code> n'est pas identique à la somme de contrôle MD 5 du fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filename</code> </p> </td> 
   <td colname="col2"> <p>Fichier - nom. See <a href="#cdf-naming-conventions"> Customer Data Feed File Naming Conventions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filesequencenumber</code> </p> </td> 
   <td colname="col2"> <p>Numéro d'index pour chaque fichier. </p> </td> 
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
   <td colname="col1"> <p> <code> Totaux</code> </p> </td> 
   <td colname="col2"> <p>Démarre l'objet contenant des données agrégées sur tous vos fichiers CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Jour</code> </p> </td> 
   <td colname="col2"> <p>jour de disponibilité des données. Uses <i>yyyy-mm-dd</i> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Heure</code> </p> </td> 
   <td colname="col2"> <p>Heure pendant laquelle les données sont disponibles. Utilise le format de 24 heures défini dans le fuseau horaire UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Totalbytesize</code> </p> </td> 
   <td colname="col2"> <p>Taille totale de tous les fichiers CDF pour cette date en octets. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Totalnumberfiles</code> </p> </td> 
   <td colname="col2"> <p>Nombre total de fichiers téléchargés dans votre répertoire S 3. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Name Times and File Content Times are Different {#different-processing-times}

Your [!UICONTROL CDF] file contains timestamps in the file name and file contents. These timestamps record different event processes for the same [!UICONTROL CDF] file. Il n'est pas rare de voir des horodatages différents dans le nom et le contenu du même fichier. Comprendre chaque horodatage peut vous aider à éviter les erreurs courantes lorsque vous travaillez avec ces données ou tentez de le trier par heure.

## Locating CDF File Timestamps {#locating-timestamps}

<!-- cdf-time-differences.xml -->

[!UICONTROL CDF] les fichiers enregistrent le temps différemment à deux emplacements distincts.

![](assets/cdf-timestamp.png)

## Understanding the Difference Between Timestamps {#understanding-timestamps}

The following table provides additional details about your [!UICONTROL CDF] file timestamps along with information about how to use them properly.

| Emplacement d'horodatage | Description |
|--- |--- |
| Nom de fichier | The timestamp in your CDF file name marks the time when [!DNL Audience Manager] started preparing your file for delivery. Cet horodatage est défini dans le fuseau horaire UTC. It uses the `hour=` parameter, with time formatted as a 2-digit hour in 24-hour notation. Cette durée peut être différente de l'heure d'événement enregistrée dans le contenu du fichier. Breakwhen Travailler avec des fichiers CDF, vous remarquerez parfois que votre compartiment S 3 est vide pendant une heure donnée. Un compartiment vide signifie peut-être l'un des éléments suivants :<ul><li>Il n'y a aucune donnée pour cette heure particulière. </li><li> Nos serveurs sont très chargés et ne peuvent traiter les fichiers qu'une heure particulière. Lorsque le serveur est rattrapé, il place les fichiers qui auraient dû se placer dans un intervalle antérieur dans un compartiment avec une valeur plus tard. For example, you'll see this when a file that should have been in the hour 17 bucket appear in the hour 18 bucket (with `hour=18` in the file name). Dans ce cas, le serveur a probablement commencé à traiter votre fichier en dehors de 17 heures, mais il n'a pas pu le terminer dans cet intervalle. Au lieu de cela, le fichier est déplacé vers la prochaine corbeille horaire.</li></ul><br>**Important**: N'utilisez pas le fichier : le nom de l'horodatage pour regrouper les événements par moment. If you need to group by time, use the `EventTime` timestamp in the file contents. |
| Contenu du fichier | L'horodatage dans le contenu du fichier CDF indique l'heure à laquelle les serveurs de collecte de données ont commencé à traiter le fichier. Cet horodatage est défini dans le fuseau horaire UTC. It uses the `EventTime` field, with time formatted as *`yyyy-mm-dd hh:mm:ss`*. This time is close to the actual time of the event on the page, but it can be different than the hour indicator in the file name. <br> **Conseil**: Contrairement à `hour=` l'horodatage du fichier, vous pouvez utiliser `EventTime` pour regrouper les données par heure. |

>[!MORE_ LIKE_ THIS]
>
>* [FAQ sur le flux de données client](../faq/faq-cdf.md)

