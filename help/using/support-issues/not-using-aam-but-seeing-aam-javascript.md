---
description: Nous n’utilisons pas Audience Manager, mais nous voyons des appels JavaScript Audience Manager dans le débogueur de JavaScript. Pourquoi ?
seo-description: Nous n’utilisons pas, mais nous voyons des appels JavaScript Audience Manager dans le débogueur de JavaScript. Pourquoi ?
seo-title: Nous n’utilisons pas Audience Manager, mais nous voyons des appels JavaScript Audience Manager dans le débogueur de JavaScript. Pourquoi ?
solution: Audience Manager
title: Nous n’utilisons pas Audience Manager, mais nous voyons des appels JavaScript Audience Manager dans le débogueur de JavaScript. Pourquoi ?
feature: support
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Nous ne sommes pas client d’Audience Manager, mais nous pouvons voir des appels JavaScript d’Audience Manager sur notre site

## Question

Nous n’utilisons pas Adobe Audience Manager, mais nous voyons des appels JavaScript Audience Manager dans le débogueur de JavaScript.

Pourquoi cela se produit-il ?

## Réponse

Il est probable que vous exécutiez [Experience Cloud Identity Service](https://docs.adobe.com/content/help/fr-FR/id-service/using/home.html) sur votre propriété. Si tel est le cas, cette référence Audience Manager ne fait pas forcément référence à la propriété exécutant Audience Manager. Cela signifie plutôt qu’Audience Manager alimente ce service.

L’appel au serveur Audience Manager est généralement passé pour [synchroniser les identifiants du client](https://docs.adobe.com/content/help/fr-FR/id-service/using/id-service-api/methods/setcustomerids.html).
