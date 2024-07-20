---
description: Informations sur Amazon Simple Storage Service (Amazon S3).
seo-description: Information about Amazon Simple Storage Service (Amazon S3).
seo-title: Amazon S3  About
solution: Audience Manager
title: Amazon S3 - À propos
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: Reference
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# Amazon S3 : À propos{#amazon-s-about}

Informations sur Amazon Simple Storage Service (Amazon S3).

Il est recommandé d’utiliser Amazon S3 plutôt que le protocole FTP comme méthode d’obtention de fichiers et de distribution de fichiers aux partenaires. Amazon S3 fournit une interface de services web simple qui peut être utilisée pour stocker et récupérer n’importe quelle quantité de données, à tout moment, de n’importe où sur le web.

Les avantages de l’utilisation d’Amazon S3 sont les suivants :

* **Évolutivité :** Amazon S3 offre une évolutivité presque illimitée.
* **Fiabilité et disponibilité :** Amazon S3 offre des services de stockage haute durabilité et haute disponibilité.
* **Vitesse :** Amazon S3 permet des transferts de données rapides.
* **Facilité d’utilisation :** Amazon S3 est très facile à utiliser et à mettre en oeuvre. Votre mise en oeuvre peut être opérationnelle en une heure environ. La mise en oeuvre d’un répertoire FTP prend beaucoup plus de temps.
* **Téléchargements en plusieurs parties :** Les fichiers volumineux peuvent être téléchargés rapidement et efficacement en tant que chargements de fichiers en plusieurs parties.
* **Sécurité :** Amazon S3 fournit une sécurité renforcée.

   * Tous les répertoires sont accessibles uniquement au client ou au client approprié.
   * Prise en charge du protocole HTTPS pour les téléchargements et les téléchargements. Vous devez toujours utiliser HTTPS lors du transfert de fichiers dans [!DNL Audience Manager].
   * Amazon S3 fournit un chiffrement au repos pour chiffrer les [fichiers de données sortants](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). Nous utilisons la méthode de cryptage [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) qui permet de générer et gérer automatiquement les clés de cryptage par Amazon S3.

* **Prise en charge du débogage et de la sauvegarde :** Amazon S3 permet à [!DNL Audience Manager] de conserver des copies exactes des fichiers pour faciliter le débogage ou le retransfert.

Pour plus d’informations sur Amazon S3, voir les ressources suivantes :

[Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/) sur le site web de Amazon Web Services.

[Prise en main d’Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) sur le site Web de documentation AWS.
