---
description: Informations sur Amazon Simple Storage Service (Amazon S3).
seo-description: Informations sur Amazon Simple Storage Service (Amazon S3).
seo-title: Amazon S3 À Propos
solution: Audience Manager
title: Amazon S3 À Propos
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
translation-type: tm+mt
source-git-commit: 212ec8641068a9ed4c620987bb18586ee8c7d519

---


#  Amazon S3 : À propos de{#amazon-s-about}

Informations sur Amazon Simple Storage Service (Amazon S3).

En règle générale, il est recommandé d’utiliser Amazon S3 au lieu de FTP comme méthode d’obtention de fichiers et de distribution de fichiers aux partenaires. Amazon S3 fournit une interface de services Web simple qui peut être utilisée pour stocker et récupérer n’importe quelle quantité de données, à tout moment, de n’importe où sur le Web.

L’utilisation d’Amazon S3 présente les avantages suivants :

* **** Évolutivité : Amazon S3 offre une évolutivité presque illimitée.
* **** Fiabilité et disponibilité : Amazon S3 offre des services de stockage haute durabilité et haute disponibilité.
* **** Vitesse : Amazon S3 permet des transferts de données rapides.
* **** Facilité d'utilisation : Amazon S3 est très facile à utiliser et à implémenter. Votre mise en oeuvre peut être opérationnelle dans environ une heure. La mise en oeuvre d’un répertoire FTP prend beaucoup plus de temps.
* **** Téléchargements multipartie : Les fichiers volumineux peuvent être téléchargés rapidement et efficacement en tant que fichiers à plusieurs parties.
* **** Sécurité : Amazon S3 offre une sécurité renforcée.

   * Tous les répertoires sont accessibles uniquement au client ou au client approprié.
   * Prise en charge du protocole HTTPS pour les téléchargements et les téléchargements. Vous devez toujours utiliser HTTPS lors du transfert de fichiers dans [!DNL Audience Manager].
   * Amazon S3 fournit un chiffrement au repos pour chiffrer les fichiers [de données](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)sortants. Nous utilisons la méthode de chiffrement [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) , qui permet de générer et de gérer automatiquement les clés de chiffrement par Amazon S3.

* **** Prise en charge du débogage et de la sauvegarde : Amazon S3 permet [!DNL Audience Manager] de conserver des copies exactes des fichiers pour faciliter le débogage ou le retransfert.

Pour plus d’informations sur Amazon S3, voir les ressources suivantes :

[Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/) sur le site Web Amazon Web Services.

[Commencez avec le service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) de stockage Amazon Simple sur le site Web de documentation AWS.
