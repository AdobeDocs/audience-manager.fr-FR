---
description: Le répertoire d’état S3 contient un fichier .info contenant des informations de réussite et d’échec sur vos fichiers chargés. Le fichier contient des données au format JSON avec des résultats d’état dans un tableau.
seo-description: The S3 status directory holds a .info file with success and failure information about your uploaded files. The file contains JSON-formatted data with status results in an array.
seo-title: Status Updates for Metadata Files
solution: Audience Manager
title: Mises à jour d’état des fichiers de métadonnées
uuid: 56a1e88a-41da-4d51-a21e-2be98cca7fa2
feature: Log Files
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 1%

---


# Mises à jour d’état des fichiers de métadonnées{#status-updates-for-metadata-files}

Le répertoire d’état S3 contient un fichier `.info` contenant des informations de succès et d’échec sur vos fichiers chargés. Le fichier contient des données au format JSON avec des résultats d’état dans un tableau.

Le contenu de votre fichier `.info` ressemblera à cet exemple.

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

## Définition des paires clé-valeur de métadonnées {#key-value-pairs}

Les tableaux suivants répertorient et définissent les clés des sections `Files` et `Summary` d’un fichier d’état de métadonnées.

**Clés dans le tableau de fichiers**

<table id="table_BF23C032FEFA446282E9364E85BE8C9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Clé </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Description</code> </p> </td> 
   <td colname="col2"> <p>Contient une brève description des raisons de l’échec du traitement. Ce champ est vide en cas de réussite du traitement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>Taille de fichier en octets. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>La somme de contrôle MD 5 pour le fichier de métadonnées téléchargé dans votre répertoire <code> meta</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>Nom du fichier de métadonnées téléchargé dans votre répertoire <code> meta</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MetadataType</code> </p> </td> 
   <td colname="col2"> <p>Nom lisible par l’utilisateur pour le type de données que votre fichier contient. Il est basé sur l’ID enfant du nom de fichier. </p> <p>Voir <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Conventions de dénomination pour les fichiers de métadonnées</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Parent</code> </p> </td> 
   <td colname="col2"> <p>Nom lisible par l’utilisateur pour le type de données que votre fichier contient. Il est basé sur l’ID parent dans le nom de fichier. </p> <p>Voir <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Conventions de dénomination pour les fichiers de métadonnées</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Status</code> </p> </td> 
   <td colname="col2"> <p>Renvoie 2 valeurs textuelles qui décrivent l’état de traitement de votre fichier de métadonnées : </p> 
    <ul id="ul_3814EBB6B42B4EB294B1ABA5782190B6"> 
     <li id="li_92AAECE7E9A44B1193A1D93ABBCE46B0"> <code> SUCCESS</code> </li> 
     <li id="li_3109F4E254374117A89CB989F221CB18"> <code> FAILURE</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Clés dans l’objet de résumé**

<table id="table_C765A0CDBAA14A2FB5E0D38BDD1D292A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Clé </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>Date de traitement du fichier au format <code><i>yyyy-mm-dd</i></code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> GlobalStatus</code> </p> </td> 
   <td colname="col2"> <p>Renvoie 2 valeurs textuelles qui décrivent l’état du traitement de tous vos fichiers pour une journée entière : </p> 
    <ul id="ul_3FC092CA043A486C9C79FECF71FAF8FB"> 
     <li id="li_754B32D8267D44BBBD6EC354C459C566"> <code> SUCCESS</code> </li> 
     <li id="li_8B64E39C80424AC2B95DF9B53D62864E"> <code> FAILURE</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NumberFailure</code> </p> </td> 
   <td colname="col2"> <p>Le nombre de fichiers qui ont été traités sans succès. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NumberSuccess</code> </p> </td> 
   <td colname="col2"> <p>Le nombre de fichiers traités avec succès. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimeRFC2822</code> </p> </td> 
   <td colname="col2"> <p>Renvoie un horodatage lisible pour les heures de début du traitement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimePOSIX</code> </p> </td> 
   <td colname="col2"> <p>Horodatage UNIX pour les heures de début du traitement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>Nombre total d’octets pour tous vos fichiers de métadonnées pour la journée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>Nombre total de tous vos fichiers traités pour la journée. </p> </td> 
  </tr> 
 </tbody> 
</table>
