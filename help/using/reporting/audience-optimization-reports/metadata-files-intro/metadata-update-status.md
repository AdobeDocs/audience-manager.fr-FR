---
description: Le répertoire d'état S 3 contient un fichier.info contenant des informations de succès et d'échec relatives aux fichiers téléchargés. Le fichier contient des données au format JSON avec des résultats d'état dans un tableau.
seo-description: Le répertoire d'état S 3 contient un fichier.info contenant des informations de succès et d'échec relatives aux fichiers téléchargés. Le fichier contient des données au format JSON avec des résultats d'état dans un tableau.
seo-title: Mises à jour de statut pour les fichiers de métadonnées
solution: Audience Manager
title: Mises à jour de statut pour les fichiers de métadonnées
uuid: 56 a 1 e 88 a -41 da -4 d 51-a 21 e -2 be 98 cca 7 fa 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Status Updates for Metadata Files{#status-updates-for-metadata-files}

The S3 status directory holds a `.info` file with success and failure information about your uploaded files. Le fichier contient des données au format JSON avec des résultats d&#39;état dans un tableau.

The contents of your `.info` file will look similar to this example.

```js
//sample file path
/log_ingestion/pid=1234/dpid=567/status/20150827.info

//sample contents
{
    "Files": [
        {
            "FileByteSize": 488900,
            "FileChecksumMD5": "94b821082daff242e452c0d8796b08f0",
            "FileName": "20141112_4_2",
            "MetadataType": "Creative",
            "Parent": "Site",
            "Status": "SUCCESS",
            "Description": ""
        },
        {
            "FileByteSize": 58812,
            "FileChecksumMD5": "db79f148e6a635629701c13a7bcc8db0",
            "FileName": "20141112_0_4",
            "MetadataType": "Site",
            "Parent": "None",
            "Status": "FAILURE",
            "Description": "Invalid format."
        }
    ],
    "Summary": {
        "Day": "2014-11-12",
        "ProcessingTimeRFC2822": "Wed, 10 Dec 2014 21:07:58 -0000",
        "ProcessingTimestampPOSIX": 1418263678,
        "TotalByteSize": 547712,
        "TotalNumberFiles": 2,
        "NumberSuccess": 1,
        "NumberFailure": 1,
        "GlobalStatus": "FAILURE"
    }
}
```

## Metadata Key-Value Pairs Defined {#key-value-pairs}

The following tables list and define the keys in the `Files` and `Summary` sections of a metadata status file.

**Clés du tableau Fichiers**

<table id="table_BF23C032FEFA446282E9364E85BE8C9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Clé </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Description</code> </p> </td> 
   <td colname="col2"> <p>Contient une brève description de l'échec du traitement. Ce champ est vide lorsque le traitement est réussi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filebytesize</code> </p> </td> 
   <td colname="col2"> <p>Taille du fichier en octets. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>The MD 5 checksum for the metadata file uploaded to your <code> meta</code> directory. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filename</code> </p> </td> 
   <td colname="col2"> <p>The name of the metadata file uploaded to your <code> meta</code> directory. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Metadatatype</code> </p> </td> 
   <td colname="col2"> <p>Nom lisible pour le type de données que contient votre fichier. Il est basé sur l'ID enfant de votre fichier - nom. </p> <p>See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Naming Conventions for Metadata Files</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Parent</code> </p> </td> 
   <td colname="col2"> <p>Nom lisible pour le type de données que contient votre fichier. Il est basé sur l'ID parent dans votre fichier - nom. </p> <p>See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Naming Conventions for Metadata Files</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> État</code> </p> </td> 
   <td colname="col2"> <p>Renvoie 2 valeurs textuelles décrivant l'état de traitement de votre fichier de métadonnées : </p> 
    <ul id="ul_3814EBB6B42B4EB294B1ABA5782190B6"> 
     <li id="li_92AAECE7E9A44B1193A1D93ABBCE46B0"> <code> SUCCESS</code> </li> 
     <li id="li_3109F4E254374117A89CB989F221CB18"> <code> ÉCHEC</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Clés de l&#39;objet Résumé**

<table id="table_C765A0CDBAA14A2FB5E0D38BDD1D292A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Clé </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Jour</code> </p> </td> 
   <td colname="col2"> <p>File processing date in <code><i>yyyy-mm-dd</i></code> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Globalstatus</code> </p> </td> 
   <td colname="col2"> <p>Renvoie 2 valeurs textuelles décrivant l'état de traitement de tous les fichiers pour une journée entière : </p> 
    <ul id="ul_3FC092CA043A486C9C79FECF71FAF8FB"> 
     <li id="li_754B32D8267D44BBBD6EC354C459C566"> <code> SUCCESS</code> </li> 
     <li id="li_8B64E39C80424AC2B95DF9B53D62864E"> <code> ÉCHEC</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Numberfailure</code> </p> </td> 
   <td colname="col2"> <p>Nombre de fichiers traités sans succès. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Numbersuccess</code> </p> </td> 
   <td colname="col2"> <p>Nombre de fichiers traités avec succès. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimeRFC2822</code> </p> </td> 
   <td colname="col2"> <p>Renvoie un horodatage lisible pour le traitement des heures de début. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Processingtimeposix</code> </p> </td> 
   <td colname="col2"> <p>Horodatage UNIX pour le traitement des heures de début. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Totalbytesize</code> </p> </td> 
   <td colname="col2"> <p>Nombre total d'octets pour tous les fichiers de métadonnées pour la journée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Totalnumberfiles</code> </p> </td> 
   <td colname="col2"> <p>Nombre total de fichiers traités pour la journée. </p> </td> 
  </tr> 
 </tbody> 
</table>
