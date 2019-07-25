---
description: Les fichiers de contrôle de transfert (.info) fournissent des métadonnées sur les transferts de fichiers afin que les partenaires puissent vérifier que les transferts de fichiers gérés par Audience Manager sont correctement transférés.
seo-description: Les fichiers de contrôle de transfert (.info) fournissent des métadonnées sur les transferts de fichiers afin que les partenaires puissent vérifier que les transferts de fichiers gérés par Audience Manager sont correctement transférés.
seo-title: Transfert de fichiers de contrôle pour les transferts de fichiers journaux
solution: Audience Manager
title: Transfert de fichiers de contrôle pour les transferts de fichiers journaux
uuid: ef 58213 e -7 b 37-4 c 5 a -8556-0 de 695706793
translation-type: tm+mt
source-git-commit: c5f9845a48d9d4432f38e9a0aaa256d89f9c1c11

---


# Transfer-Control Files for Log File Transfers {#transfer-control-files-for-log-file-transfers}

Transfer-control ([!DNL .info]) files provide metadata information about file transfers so that partners can verify that Audience Manager handled file transfers correctly.

[!DNL Audience Manager] envoie un fichier de contrôle de transfert à un partenaire avec chaque transfert de fichier. Due to the multi-thread nature of the [!DNL FTP] publisher, the transfer-control file might be sent before the actual files are finished transferring.

The metadata in the [!DNL .info] file lets partners:

* Déterminer à quel moment un cycle de transfert complet est terminé (le nombre total de fichiers de la séquence a été diffusé) ;
* Déterminer si un fichier donné dans la séquence est complet/correct (en examinant la taille du fichier en octets et le nombre total de lignes) ;
* Validez le nombre de lignes dans les fichiers bruts et verrez le nombre de lignes après le chargement des fichiers dans la base de données de la fin de réception (taille du fichier dans les lignes).

## File Naming Conventions {#file-naming-conventions}

The transfer-control file has the same name as the root of the batch/sequence with a [!DNL .info] file extension.s

For example, if the first file in the sequence were named: [!DNL ftp_12345_67890_full_1500727351632-1.sync], the control file would be named [!DNL ftp_12345_67890_iter_1500727351632.info].

## Format du fichier {#file-format}

```
{
  Files: [
    {
      FileByteSize: 293029329,
      FileLineCount: 36893908,
      FileName: "ftp_12345_67890_full_1500727351632-1.sync.gz",
      FileSequenceNumber: 1,
      md5: "983g634be2ad5263c6a6c4958bf61d9f"
    },
    {
      FileByteSize: 293039238,
      FileLineCount: 36895184,
      FileName: "ftp_12345_67890_full_1500727351632-2.sync.gz",
      FileSequenceNumber: 2,
      md5: "6sn9907c8e78cfd78409622e7b55a984"
    },
    {
      FileByteSize: 293050833,
      FileLineCount: 36896787,
      FileName: "ftp_12345_67890_full_1500727351632-3.sync.gz",
      FileSequenceNumber: 3,
      md5: "7cdfb8e74cd6cec1jy6vel21ccb4a962"
    },
    {
      FileByteSize: 218425764,
      FileLineCount: 27498226,
      FileName: "ftp_12345_67890_full_1500727351632-4.sync.gz",
      FileSequenceNumber: 4,
      md5: "7hs53149f8a2444457g968f04cbbdee5"
    }
  ],
  Totals: {
    FileName: "ftp_12345_67890_full_1500727351632.sync",
    TotalByteSize: 1097545164,
    TotalNumberFiles: 4,
    TotalNumberLines: 138184105
    }
}
```

>[REMARQUE]
>
> The batch total numbers are exclusive of the [!DNL .info] file itself. That is, the totals do not include the [!DNL .info] file, its byte size, or its line count.
>
> Les tailles d'octets des fichiers et du nombre de lignes incluent les lignes/lignes d'en-tête et d'espacement (vides). Pour obtenir le décompte des lignes/lignes de données réelles, soustrayez les en-têtes.
>
> Les lignes totales par lot et la taille totale des octets sont incluses dans les en-têtes et les rangées d'espacement.