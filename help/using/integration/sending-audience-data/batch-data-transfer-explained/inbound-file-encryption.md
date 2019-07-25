---
description: En tant qu'option, vous pouvez chiffrer les fichiers de données avec le chiffrement PGP lors de leur envoi à Audience Manager.
seo-description: En tant qu'option, vous pouvez chiffrer les fichiers de données avec le chiffrement PGP lors de leur envoi à Audience Manager.
seo-title: Chiffrement PGP du fichier pour les types de données entrants
solution: Audience Manager
title: Chiffrement PGP du fichier pour les types de données entrants
uuid: 89 caace 1-0259-48 fc -865 b-d 525 ec 7822 f 7
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# File PGP Encryption for Inbound Data Types{#file-pgp-encryption-for-inbound-data-types}

As an option, you can encrypt data files with [!DNL PGP] encryption when sending them to Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>Actuellement, nous ne prenons pas en charge le chiffrement et la compression dans le même fichier de données entrantes. You can select to either encrypt or [compress](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) your inbound files.

Suivez les étapes décrites ci-dessous pour chiffrer les fichiers de données entrantes.

1. Download the [Audience Manager public key](./assets/adobe_pgp.pub).
1. Importez la clé publique dans votre magasin de confiance.

   For example, if you use [!DNL GPG], the command could be similar to the following:

   `gpg --import adobe_pgp.pub`

1. Vérifiez que la clé a été correctement importée en exécutant la commande suivante :

   `gpg --list-keys`

   Un message similaire doit s'afficher :

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

1. Chiffrez les données entrantes à l'aide de la commande suivante :

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   All encrypted data must use `.pgp` or `.gpg` as the file extension (e.g. `ftp_dpm_100_123456789.sync.pgp` or `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager supports only the [!DNL Advanced Encryption Standard (AES)] data-encryption algorithm. Audience Manager prend en charge toute taille de clé.