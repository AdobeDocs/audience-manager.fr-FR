---
description: Les fichiers de contrôle de transfert (.info) fournissent des informations de métadonnées sur les transferts de fichiers afin que les partenaires puissent vérifier que l’Audience Manager a géré correctement les transferts de fichiers.
seo-description: Les fichiers de contrôle de transfert (.info) fournissent des informations de métadonnées sur les transferts de fichiers afin que les partenaires puissent vérifier que l’Audience Manager a géré correctement les transferts de fichiers.
seo-title: Fichiers de contrôle de transfert pour les transferts de fichiers journaux
solution: Audience Manager
title: Fichiers de contrôle de transfert pour les transferts de fichiers journaux
uuid: ef58213e-7b37-4c5a-8556-0de695706793
feature: Transferts de données sortantes
exl-id: 4fd1aab1-2dc2-4de9-97be-58e79825db40
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 6%

---

# Fichiers de contrôle de transfert pour les transferts de fichiers journaux {#transfer-control-files-for-log-file-transfers}

Les fichiers de contrôle de transfert ([!DNL .info]) fournissent des informations de métadonnées sur les transferts de fichiers afin que les partenaires puissent vérifier que l’Audience Manager a géré correctement les transferts de fichiers.

[!DNL Audience Manager] envoie un fichier de contrôle de transfert à un partenaire avec chaque transfert de fichier. En raison de la nature multi-thread de l’éditeur [!DNL FTP], le fichier de contrôle de transfert peut être envoyé avant que les fichiers réels ne soient transférés.

Les métadonnées du fichier [!DNL .info] permettent aux partenaires :

* Déterminer à quel moment le cycle de transfert complet est terminé (le nombre total de fichiers dans la séquence a été livré) ;
* Déterminer si un fichier donné de la séquence est complet/correct (en examinant la taille du fichier en octets et le nombre total de lignes) ;
* Validez le nombre de lignes dans les fichiers bruts par rapport au nombre de lignes après le chargement des fichiers dans la base de données du côté de réception (taille du fichier en lignes).

## Conventions de dénomination des fichiers {#file-naming-conventions}

Le fichier de contrôle de transfert porte le même nom que la racine du lot/de la séquence avec une extension de fichier [!DNL .info].s

Par exemple, si le premier fichier de la séquence a été nommé : [!DNL ftp_12345_67890_full_1500727351632-1.sync], le fichier de contrôle serait nommé [!DNL ftp_12345_67890_iter_1500727351632.info].

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

>[!NOTE]
>
> Les nombres totaux des lots sont exclusifs au fichier [!DNL .info] lui-même. En d’autres termes, les totaux n’incluent pas le fichier [!DNL .info], sa taille en octets ou son nombre de lignes.
>
> Les tailles d’octet des fichiers et le nombre de lignes incluent tous les en-têtes et espaces (vierges) lignes/lignes. Pour obtenir le nombre de lignes/lignes de données réelles, soustrayez les en-têtes.
>
> Les lignes totales du lot et la taille totale des octets incluent tous les rangées d’en-tête et d’espace.
