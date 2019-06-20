---
description: Informations conceptuelles, descriptions et définitions du code, des méthodes et des processus de l'API DCS.
seo-description: Informations conceptuelles, descriptions et définitions du code, des méthodes et des processus d'API DCS dans Adobe Audience Manager (AAM).
seo-title: Présentation de l'API de DCS dans Adobe Audience Manager (AAM)
title: Présentation de référence de l'API DCS
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# Présentation de référence de l&#39;API DCS

Informations conceptuelles, descriptions et définitions du code, des méthodes et des processus de l&#39;API DCS.

* [Méthodes de l&#39;API DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   Envoyez des données à l&#39;API DCS à l&#39;aide des méthodes GET ou POST.

* [Codes, messages et exemples d’erreur des serveurs de collecte de données](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   Codes d&#39;erreur et messages générés par les serveurs de collecte de données (DCS) classés par l&#39;ordre numérique par ID de code.

* [Surveillance des identifiants et liste noire](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-blacklisting.md)

   Le serveur de collecte de données contrôle les ID qu&#39;il reçoit et répertorie les adresses qui sont envoyées à un taux anormalement élevé pendant une courte période.

* [Identifiants de région de DCS, emplacements et noms d&#39;hôtes](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   Le nom d&#39;hôte du serveur DCS régional est requis pour effectuer des appels au serveur de collecte de données. Cela est dû au fait que le serveur de collecte de données stocke les informations dans les centres de données proches des visiteurs du site. Vos requêtes fonctionnent si vous les envoyez au serveur DCS incorrect, mais ces appels sont inefficaces et peuvent retarder la réponse. Pour effectuer une requête DCS, faites correspondre l&#39;identifiant de région à son nom d&#39;hôte régional correspondant et formulez votre requête avec le nom d&#39;hôte approprié.

* [Mise en forme des paires clé-valeur dans les appels DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   Lors d&#39;un appel, le serveur de collecte de données accepte les données clé-valeur au format standard ou sérialisé. Consultez cette section pour plus d&#39;informations sur la mise en forme des données standard et sérialisées de valeurs de clé.

* [Conditions de concurrence et gestion des erreurs](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   Décrit la procédure à suivre pour éviter les conditions de concurrence et la gestion des erreurs DCS.

* [Attributs pris en charge pour les appels d&#39;API DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   Répertorie et décrit la syntaxe et les attributs pris en charge (ou paires clé-valeur) que vous pouvez transmettre aux serveurs de collecte de données (DCS). Ces informations peuvent vous aider à formater vos requêtes DCS et à comprendre les paramètres renvoyés par ce système.
