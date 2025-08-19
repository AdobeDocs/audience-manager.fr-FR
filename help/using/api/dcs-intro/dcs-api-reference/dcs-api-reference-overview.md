---
description: Informations conceptuelles, descriptions et définitions du code, des méthodes et des processus de l’API DCS.
seo-description: Conceptual information, descriptions, and definitions for DCS API code, methods, and processes in Adobe Audience Manager (AAM).
seo-title: DCS API Reference Overview in Adobe Audience Manager (AAM)
title: Présentation de la référence de l’API DCS
feature: DCS
exl-id: 84d20041-0b98-4ba5-ba97-29c35f088ad9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '276'
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
