---
description: En option, vous pouvez chiffrer des fichiers de données à l’aide d’un chiffrement PGP lors de leur envoi à l’Audience Manager.
seo-description: En option, vous pouvez chiffrer des fichiers de données à l’aide d’un chiffrement PGP lors de leur envoi à l’Audience Manager.
seo-title: Chiffrement PGP de fichier pour les types de données entrants
solution: Audience Manager
title: Chiffrement PGP de fichier pour les types de données entrants
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---


# Chiffrement PGP de fichier pour les types de données entrants{#file-pgp-encryption-for-inbound-data-types}

Vous pouvez chiffrer des fichiers de données à l’aide d’un [!DNL PGP] chiffrement lors de leur envoi à l’Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] le chiffrement inclut la compression de fichiers. Lorsque vous envoyez des fichiers [!DNL PGP] chiffrés entrants, veillez à ne pas les [compresser](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) à l’aide de gzip (`.gz`).
>
>[!DNL PGP] les fichiers entrants chiffrés qui sont également [compressés](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) ne sont pas valides en Audience Manager.

Suivez les étapes décrites ci-dessous pour chiffrer les fichiers de données entrants.

1. Téléchargez la clé [publique](./assets/adobe_pgp.pub)Audience Manager.
2. Importez la clé publique dans votre magasin approuvé.

   Par exemple, si vous utilisez [!DNL GPG], la commande peut être similaire à la commande suivante :

   `gpg --import adobe_pgp.pub`

3. Vérifiez que la clé a été correctement importée en exécutant la commande suivante :

   `gpg --list-keys`

   Vous devriez voir un message similaire à celui-ci :

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

4. Chiffrez les données entrantes à l’aide de la commande suivante :

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   Toutes les données chiffrées doivent utiliser `.pgp` ou `.gpg` comme extension de fichier (par ex. `ftp_dpm_100_123456789.sync.pgp` ou `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >L’Audience Manager ne prend en charge que l’algorithme [!DNL Advanced Encryption Standard (AES)] de chiffrement des données. L’Audience Manager prend en charge n’importe quelle taille de clé.
