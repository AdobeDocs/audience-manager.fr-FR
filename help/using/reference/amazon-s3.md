---
description: Informations sur Amazon Simple Storage Service (Amazon S 3).
seo-description: Informations sur Amazon Simple Storage Service (Amazon S 3).
seo-title: Amazon S 3 A propos de
solution: Audience Manager
title: Amazon S 3 A propos de
uuid: 8197 ecdf-df 8 f -488 d-bbc 0-d 8 d 4205 b 42 b 4
translation-type: tm+mt
source-git-commit: 212ec8641068a9ed4c620987bb18586ee8c7d519

---


# Amazon S3: About{#amazon-s-about}

Informations sur Amazon Simple Storage Service (Amazon S 3).

En règle générale, il est recommandé d'utiliser Amazon S 3 plutôt que FTP comme méthode d'obtention de fichiers et de fourniture de fichiers aux partenaires. Amazon S 3 fournit une interface de services Web simple qui permet de stocker et de récupérer n'importe quelle quantité de données à tout moment, depuis n'importe quel emplacement sur le Web.

L'utilisation d'Amazon S 3 présente les avantages suivants :

* **Évolutivité :** Amazon S 3 offre une évolutivité presque illimitée.
* **Fiabilité et disponibilité :** Amazon S 3 offre des services de stockage haut de gamme et de haute disponibilité.
* **Vitesse :** Amazon S 3 permet des transferts de données rapides.
* **Facilité - de - utilisez :** Amazon S 3 est très facile à utiliser et à implémenter. Votre implémentation peut être opérationnelle dans environ une heure. La mise en œuvre d'un répertoire FTP prend beaucoup plus de temps.
* **Chargements multiparties :** Les fichiers volumineux peuvent être téléchargés rapidement et efficacement en tant que téléchargements de fichiers à parties multiples.
* **Sécurité :** Amazon S 3 offre une sécurité renforcée.

   * Tous les répertoires sont accessibles uniquement au client ou client approprié.
   * Prise en charge du protocole HTTPS pour les téléchargements et les téléchargements. You should always use HTTPS when transferring files in [!DNL Audience Manager].
   * Amazon S3 provides encryption-at-rest for encrypting [outbound data files](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). We use the [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) encryption method, which allows encryption keys to be automatically generated and managed by Amazon S3.

* **Prise en charge de débogage et de sauvegarde :** Amazon S 3 [!DNL Audience Manager] permet de conserver des copies exactes des fichiers pour faciliter le débogage ou le retransfert.

Pour plus d'informations sur Amazon S 3, consultez les ressources suivantes :

[Amazon Simple Storage Service (Amazon S 3)](https://aws.amazon.com/s3/) sur le site web Amazon Web Services.

[Commencez avec Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) sur le site Web de documentation AWS.
