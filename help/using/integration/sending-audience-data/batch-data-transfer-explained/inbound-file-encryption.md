---
description: Vous pouvez, au choix, chiffrer des fichiers de données avec chiffrement PGP lors de leur envoi à Audience Manager.
seo-description: Vous pouvez, au choix, chiffrer des fichiers de données avec chiffrement PGP lors de leur envoi à Audience Manager.
seo-title: Chiffrement PGP de fichier pour les types de données entrantes
solution: Audience Manager
title: Chiffrement PGP de fichier pour les types de données entrantes
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: Transferts des données entrantes
exl-id: 5f97a326-4840-4350-bbe8-bc8ce32b0a2e
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 12%

---

# Chiffrement PGP de fichier pour les types de données entrantes{#file-pgp-encryption-for-inbound-data-types}

Vous pouvez chiffrer les fichiers de données avec le chiffrement [!DNL PGP] lors de leur envoi à Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] le chiffrement inclut la compression de fichiers. Lors de l’envoi de [!DNL PGP] fichiers entrants chiffrés, assurez-vous de ne pas les [compresser](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) à l’aide de gzip (`.gz`).
>
>[!DNL PGP] les fichiers entrants cryptés qui sont également  [](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) compressés ne sont pas valides en Audience Manager.

Suivez les étapes décrites ci-dessous pour chiffrer les fichiers de données entrants.

1. Téléchargez la [clé publique d’Audience Manager](./assets/adobe_pgp.pub).
2. Importez la clé publique dans votre magasin de confiance.

   Par exemple, si vous utilisez [!DNL GPG], la commande peut être similaire à ce qui suit :

   `gpg --import adobe_pgp.pub`

3. Vérifiez que la clé a bien été importée en exécutant la commande suivante :

   `gpg --list-keys`

   Un message similaire à celui-ci devrait s’afficher :

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

4. Chiffrez les données entrantes à l&#39;aide de la commande suivante :

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   Toutes les données chiffrées doivent utiliser `.pgp` ou `.gpg` comme extension de fichier (par exemple : `ftp_dpm_100_123456789.sync.pgp` ou `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager ne prend en charge que l’algorithme de cryptage des données [!DNL Advanced Encryption Standard (AES)]. Audience Manager prend en charge n’importe quelle taille de clé.
