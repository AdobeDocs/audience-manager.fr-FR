---
description: Informations conceptuelles, descriptions et définitions du code, des méthodes et des processus de l’API DCS.
seo-description: Conceptual information, descriptions, and definitions for DCS API code, methods, and processes in Adobe Audience Manager (AAM).
seo-title: DCS API Reference Overview in Adobe Audience Manager (AAM)
title: Présentation de la référence de l’API DCS
feature: DCS
exl-id: 84d20041-0b98-4ba5-ba97-29c35f088ad9
TQID: https://experienceleague.adobe.com/e7W6fcETh4YArPa0k2hn11GMYgFjSU4AxALe92a7DhE
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2:
  - id: d8f681b8-67cc-42dc-85c5-a0977528a942
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 276
ht-degree: 0%

---

# Présentation de la référence de l’API DCS

Informations conceptuelles, descriptions et définitions relatives au code, aux méthodes et aux processus [!DNL DCS API].

* [Méthodes de l’API DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

  Envoyez des données au [!DNL DCS API] à l’aide de méthodes GET ou POST.

* [Codes d’erreur DCS, messages et exemples](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

  Codes d’erreur et messages générés par les serveurs de collecte de données (DCS) répertoriés dans l’ordre numérique par identifiant de code.

* [Surveillance et Liste bloquée des identifiants](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

  Le serveur de collecte de données surveille les identifiants qu’il reçoit et ajoute à une liste bloquée ceux qui sont envoyés à un débit anormalement élevé sur une courte période.

* [Identifiants de zone géographique, emplacements et noms d’hôte du serveur de collecte de données](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

  Le nom d’hôte du serveur DCS régional est requis pour effectuer des appels vers le serveur DCS. En effet, le serveur de collecte de données stocke les informations dans des centres de données géographiquement proches des visiteurs du site. Vos requêtes fonctionneront si vous les envoyez au mauvais serveur de collecte de données, mais ces appels sont inefficaces et peuvent retarder la réponse. Pour effectuer une requête DCS, faites correspondre l’ID de région à son nom d’hôte régional correspondant et formez votre requête avec le nom d’hôte approprié.

* [Formatage des paires clé-valeur dans les appels DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

  Lors d’un appel, le serveur de collecte de données accepte les données clé-valeur au format standard ou sérialisé. Consultez cette section pour plus d’informations sur le format des données clé-valeur standard et sérialisées.

* [Conditions de concurrence et gestion des erreurs](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

  Décrit comment empêcher les conditions de concurrence et la gestion des erreurs DCS.

* [Attributs pris en charge pour les appels API DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

  Répertorie et décrit la syntaxe et les attributs pris en charge (ou les paires clé-valeur) que vous pouvez transmettre aux serveurs de collecte de données (DCS). Ces informations peuvent vous aider à formater vos requêtes DCS et à comprendre les paramètres renvoyés par ce système.
