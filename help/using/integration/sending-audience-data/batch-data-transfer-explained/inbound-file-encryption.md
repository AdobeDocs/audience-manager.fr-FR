---
description: En option, vous pouvez chiffrer des fichiers de données à l’aide d’un chiffrement PGP lors de leur envoi à l’Audience Manager.
seo-description: En option, vous pouvez chiffrer des fichiers de données à l’aide d’un chiffrement PGP lors de leur envoi à l’Audience Manager.
seo-title: Chiffrement PGP de fichier pour les types de données entrantes
solution: Audience Manager
title: Chiffrement PGP de fichier pour les types de données entrantes
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: Transferts des données entrantes
exl-id: 5f97a326-4840-4350-bbe8-bc8ce32b0a2e
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 12%

---

# Chiffrement PGP de fichier pour les types de données entrantes{#file-pgp-encryption-for-inbound-data-types}

Vous pouvez chiffrer des fichiers de données à l&#39;aide d&#39;un chiffrement [!DNL PGP] lors de leur envoi à l&#39;Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] le chiffrement inclut la compression de fichiers. Lors de l&#39;envoi de [!DNL PGP] fichiers entrants chiffrés, veillez à ne pas les [compresser](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) à l&#39;aide de gzip (`.gz`).
>
>[!DNL PGP] les fichiers entrants chiffrés qui sont également  [](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) compressés ne sont pas valides en Audience Manager.

Suivez les étapes décrites ci-dessous pour chiffrer les fichiers de données entrants.

1. Téléchargez la [clé publique d&#39;Audience Manager](./assets/adobe_pgp.pub).
2. Importez la clé publique dans votre magasin approuvé.

   Par exemple, si vous utilisez [!DNL GPG], la commande peut être semblable à la suivante :

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

   Toutes les données chiffrées doivent utiliser `.pgp` ou `.gpg` comme extension de fichier (ex. `ftp_dpm_100_123456789.sync.pgp` ou `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >L’Audience Manager ne prend en charge que l’algorithme de chiffrement des données [!DNL Advanced Encryption Standard (AES)]. L’Audience Manager prend en charge n’importe quelle taille de clé.
