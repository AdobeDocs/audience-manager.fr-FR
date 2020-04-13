---
description: Nous n'utilisons pas  Gestionnaire de  de, mais nous voyons des appels Javascript Gestionnaire de de  de Javascript dans le débogueur Javascript - Pourquoi ?
seo-description: Nous n'utilisons pas, mais nous voyons  appels Javascript Gestionnaire de  dans le débogueur Javascript - Pourquoi ?
seo-title: Nous n'utilisons pas  Gestionnaire de  de, mais nous voyons des appels Javascript Gestionnaire de de  de Javascript dans le débogueur Javascript - Pourquoi ?
solution: Audience Manager
title: Nous n'utilisons pas  Gestionnaire de  de, mais nous voyons des appels Javascript Gestionnaire de de  de Javascript dans le débogueur Javascript - Pourquoi ?
translation-type: tm+mt
source-git-commit: 1f5c1a91f0b5df5291d3143d297e25128b5bb716

---


# Nous ne sommes pas un client   Manager, mais nous vous invitons à consulter les appels Javascript du Gestionnaire de de la  sur notre site.

## Question

Nous n’utilisons pas Adobe  Gestionnaire de, mais nous voyons des appels Javascript Gestionnaire de dans le débogueur Javascript.

Pourquoi cela se produit-il ?

## Réponse

Il est probable que vous exécutiez le service [d’identité](https://docs.adobe.com/content/help/en/id-service/using/home.html) Experience Cloud sur votre propriété. Si vous l’êtes, la référence à ce  Gestionnaire de  de ne fait pas nécessairement référence à la propriété qui exécute le Gestionnaire de de . Cela signifie que  Gestionnaire de  est en train de mettre ce service sous tension.

L’appel du serveur   Manager est généralement effectué pour [synchroniser les ID](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html)du client.
