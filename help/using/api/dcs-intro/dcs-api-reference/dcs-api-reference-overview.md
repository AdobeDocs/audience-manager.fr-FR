---
description: Informations conceptuelles, descriptions et définitions pour le code, les méthodes et les processus de l’API DCS.
seo-description: Informations conceptuelles, descriptions et définitions pour le code, les méthodes et les processus de l’API DCS dans Adobe Audience Manager (AAM).
seo-title: Présentation de la référence de l’API DCS dans l’Adobe Audience Manager (AAM)
title: Présentation des références d’API DCS
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 13%

---


# Présentation des références d’API DCS

Informations conceptuelles, descriptions et définitions du [!DNL DCS API] code, des méthodes et des processus.

* [Méthodes d’API DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   Envoyez des données à l’ [!DNL DCS API] aide des méthodes GET ou POST.

* [Codes, messages et exemples d’erreur des serveurs de collecte de données](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   Codes d’erreur et messages générés par les serveurs de collecte de données (DCS) répertoriés par ID de code dans l’ordre numérique.

* [Surveillance et Liste bloquée des identifiants](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

   Le serveur de collecte de données contrôle les identifiants qu’il reçoit et ajoute ceux qui sont envoyés à un taux inhabituellement élevé sur une courte période à une liste bloquée.

* [Identifiants de zone géographique, emplacements et noms d’hôte du serveur de collecte de données](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   Le nom d’hôte du serveur DCS régional est requis pour effectuer des appels au serveur DCS. En effet, le serveur de collecte de données stocke des informations dans des centres de données situés à proximité géographique des visiteurs du site. Vos requêtes fonctionneront si vous les envoyez au mauvais serveur de collecte de données, mais ces appels sont inefficaces et peuvent retarder la réponse. Pour effectuer une demande de serveur de collecte de données, faites correspondre l’identifiant de région à son nom d’hôte régional correspondant et indiquez le nom d’hôte approprié dans votre requête.

* [Formatage des paires clé-valeur dans les appels DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   Lors d’un appel, le serveur de collecte de données accepte les données de valeur de clé dans un format standard ou sérialisé. Consultez cette section pour savoir comment formater les données de valeur de clé standard et sérialisées.

* [Conditions de race et gestion des erreurs](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   Décrit comment empêcher les conditions de concurrence et la gestion des erreurs DCS.

* [Attributs pris en charge pour les appels de l’API DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   Listes et décrit la syntaxe et les attributs pris en charge (ou paires clé-valeur) que vous pouvez transmettre aux serveurs de collecte de données (DCS). Ces informations peuvent vous aider à formater vos requêtes DCS et à comprendre les paramètres renvoyés par ce système.
