---
description: Vous pouvez, de manière optionnelle, chiffrer les fichiers de données avec le chiffrement PGP lors de leur envoi à Audience Manager.
seo-description: As an option, you can encrypt data files with PGP encryption when sending them to Audience Manager.
seo-title: File PGP Encryption for Inbound Data Types
solution: Audience Manager
title: Chiffrement PGP de fichier pour les types de données entrants
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: Inbound Data Transfers
exl-id: 5f97a326-4840-4350-bbe8-bc8ce32b0a2e
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---

# Chiffrement PGP de fichier pour les types de données entrants{#file-pgp-encryption-for-inbound-data-types}

Vous pouvez chiffrer les fichiers de données avec un chiffrement [!DNL PGP] lors de leur envoi à Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>Le chiffrement [!DNL PGP] inclut la compression de fichiers. Lorsque vous envoyez [!DNL PGP] fichiers entrants chiffrés, veillez à ne pas les [compresser](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) à l’aide de gzip (`.gz`).
>
>[!DNL PGP] fichiers entrants chiffrés qui sont également [ compressés ](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) ne sont pas valides dans Audience Manager.

Pour chiffrer les fichiers de données entrants, procédez comme suit.

1. Téléchargez la clé publique [Audience Manager](./assets/adobe_pgp.pub).
2. Importez la clé publique dans votre magasin approuvé.

   Par exemple, si vous utilisez [!DNL GPG], la commande peut être similaire à la suivante :

   `gpg --import adobe_pgp.pub`

3. Vérifiez que la clé a été correctement importée en exécutant la commande suivante :

   `gpg --list-keys`

   Un message similaire au suivant devrait s’afficher :

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

4. Chiffrez les données entrantes à l&#39;aide de la commande suivante :

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   Toutes les données chiffrées doivent utiliser `.pgp` ou `.gpg` comme extension de fichier (par exemple `ftp_dpm_100_123456789.sync.pgp` ou `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager prend uniquement en charge l’algorithme de chiffrement des données [!DNL Advanced Encryption Standard (AES)]. Audience Manager prend en charge n’importe quelle taille de clé.
