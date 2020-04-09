---
description: Nous n'utilisons pas  Gestionnaire de  de, mais nous voyons des appels Javascript Gestionnaire de de  de Javascript dans le débogueur Javascript - Pourquoi ?
seo-description: Nous n'utilisons pas, mais nous voyons  appels Javascript Gestionnaire de  dans le débogueur Javascript - Pourquoi ?
seo-title: Nous n'utilisons pas  Gestionnaire de  de, mais nous voyons des appels Javascript Gestionnaire de de  de Javascript dans le débogueur Javascript - Pourquoi ?
solution: Audience Manager
title: Nous n'utilisons pas  Gestionnaire de  de, mais nous voyons des appels Javascript Gestionnaire de de  de Javascript dans le débogueur Javascript - Pourquoi ?
translation-type: tm+mt
source-git-commit: 7206b43562eded19bfb30f8aea3bcad946a3f834

---


# Nous ne sommes pas un client   Manager, mais nous vous invitons à consulter les appels Javascript du Gestionnaire de de la  sur notre site.

## Question

Nous n’utilisons pas Adobe  Gestionnaire de, mais nous voyons des appels Javascript Gestionnaire de dans le débogueur Javascript.  Pourquoi cela se produirait-il ?

## Réponse

Il est probable que vous exécutez le service d’ID de sur votre propriété. Si vous l’êtes, la référence AAM ne fait pas nécessairement référence à la propriété exécutant  Gestionnaire de, mais cela signifie que  Gestionnaire de est en fait en train de mettre ce service sous tension.

Notez que l’appel AAM est généralement effectué pour synchroniser les ID de client Set.
