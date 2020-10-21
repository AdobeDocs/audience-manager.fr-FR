---
description: Le répertoire d’état S3 contient un fichier .info contenant des informations de réussite et d’échec sur vos fichiers téléchargés. Le fichier contient des données au format JSON avec des résultats d’état dans un tableau.
seo-description: Le répertoire d’état S3 contient un fichier .info contenant des informations de réussite et d’échec sur vos fichiers téléchargés. Le fichier contient des données au format JSON avec des résultats d’état dans un tableau.
seo-title: Mises à jour d’état des fichiers de métadonnées
solution: Audience Manager
title: Mises à jour d’état des fichiers de métadonnées
uuid: 56a1e88a-41da-4d51-a21e-2be98cca7fa2
feature: log files
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 1%

---


# Mises à jour d’état des fichiers de métadonnées{#status-updates-for-metadata-files}

Le répertoire d’état S3 contient un `.info` fichier contenant des informations de réussite et d’échec sur vos fichiers téléchargés. Le fichier contient des données au format JSON avec des résultats d’état dans un tableau.

Le contenu de votre `.info` fichier ressemblera à cet exemple.

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

## Définition des paires clé-valeur des métadonnées {#key-value-pairs}

Les tableaux suivants liste et définissent les clés des sections `Files` et `Summary` des sections d’un fichier d’état de métadonnées.

**Raccourcis clavier dans le tableau Fichiers**

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
   <td colname="col2"> <p>Contient une brève description des raisons pour lesquelles le traitement a échoué. Ce champ est vide en cas de succès du traitement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>Taille du fichier en octets. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Somme de contrôle MD 5 pour le fichier de métadonnées téléchargé dans votre <code> meta</code> répertoire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>nom du fichier de métadonnées téléchargé dans votre <code> meta</code> répertoire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MetadataType</code> </p> </td> 
   <td colname="col2"> <p>Nom lisible par l’utilisateur pour le type de données que votre fichier contient. Il est basé sur l’ID enfant figurant dans le nom de fichier. </p> <p>See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Naming Conventions for Metadata Files</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Parent</code> </p> </td> 
   <td colname="col2"> <p>Nom lisible par l’utilisateur pour le type de données que votre fichier contient. Il est basé sur l’identifiant parent figurant dans le nom de fichier. </p> <p>See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Naming Conventions for Metadata Files</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Status</code> </p> </td> 
   <td colname="col2"> <p>Renvoie 2 valeurs de texte qui décrivent l’état de traitement de votre fichier de métadonnées : </p> 
    <ul id="ul_3814EBB6B42B4EB294B1ABA5782190B6"> 
     <li id="li_92AAECE7E9A44B1193A1D93ABBCE46B0"> <code> SUCCESS</code> </li> 
     <li id="li_3109F4E254374117A89CB989F221CB18"> <code> FAILURE</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Raccourcis dans l’objet Résumé**

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
   <td colname="col2"> <p>Date de traitement du fichier au <code><i>yyyy-mm-dd</i></code> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> GlobalStatus</code> </p> </td> 
   <td colname="col2"> <p>Renvoie 2 valeurs textuelles qui décrivent l’état de traitement de tous vos fichiers pour une journée entière : </p> 
    <ul id="ul_3FC092CA043A486C9C79FECF71FAF8FB"> 
     <li id="li_754B32D8267D44BBBD6EC354C459C566"> <code> SUCCESS</code> </li> 
     <li id="li_8B64E39C80424AC2B95DF9B53D62864E"> <code> FAILURE</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NumberFailure</code> </p> </td> 
   <td colname="col2"> <p>Nombre de fichiers traités sans succès. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NumberSuccess</code> </p> </td> 
   <td colname="col2"> <p>Nombre de fichiers traités avec succès. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimeRFC2822</code> </p> </td> 
   <td colname="col2"> <p>Renvoie un horodatage lisible pour les débuts de traitement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimePOSIX</code> </p> </td> 
   <td colname="col2"> <p>Horodatage UNIX pour le traitement des débuts. </p> </td> 
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
