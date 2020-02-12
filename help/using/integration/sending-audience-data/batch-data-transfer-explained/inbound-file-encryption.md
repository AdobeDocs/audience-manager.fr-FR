---
description: En option, vous pouvez chiffrer des fichiers de données à l’aide du chiffrement PGP lors de leur envoi à Audience Manager.
seo-description: En option, vous pouvez chiffrer des fichiers de données à l’aide du chiffrement PGP lors de leur envoi à Audience Manager.
seo-title: Chiffrement PGP de fichier pour les types de données entrants
solution: Audience Manager
title: Chiffrement PGP de fichier pour les types de données entrants
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
translation-type: tm+mt
source-git-commit: 8d2d841f8e94fd67c2165eb280b85ab18001d77e

---


# Chiffrement PGP de fichier pour les types de données entrants{#file-pgp-encryption-for-inbound-data-types}

Vous pouvez, en option, chiffrer des fichiers de données avec [!DNL PGP] chiffrement lors de leur envoi à Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>Actuellement, nous ne prenons pas en charge le chiffrement et la compression sur le même fichier de données entrant. Vous pouvez choisir de chiffrer ou de [compresser](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) vos fichiers entrants.
>
> Toutefois, gardez à l’esprit que le chiffrement PGP inclut une compression intégrée.

Suivez les étapes décrites ci-dessous pour chiffrer les fichiers de données entrants.

1. Téléchargez la clé [publique d’](./assets/adobe_pgp.pub)Audience Manager.
1. Importez la clé publique dans votre magasin de confiance.

   Par exemple, si vous utilisez [!DNL GPG], la commande peut être semblable à ce qui suit :

   `gpg --import adobe_pgp.pub`

1. Vérifiez que la clé a été correctement importée en exécutant la commande suivante :

   `gpg --list-keys`

   Un message similaire à celui-ci doit s’afficher :

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

1. Chiffrez les données entrantes à l’aide de la commande suivante :

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   Toutes les données chiffrées doivent utiliser `.pgp` ou `.gpg` comme extension de fichier ( `ftp_dpm_100_123456789.sync.pgp` ou `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager ne prend en charge que l’algorithme [!DNL Advanced Encryption Standard (AES)] de chiffrement des données. Audience Manager prend en charge n’importe quelle taille de clé.
