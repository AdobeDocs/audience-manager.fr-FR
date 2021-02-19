---
description: La gestion des utilisateurs de l'Audience Manager se déplace vers Adobe Admin Console. Cet article explique ce que vous devez faire pour préparer la migration des utilisateurs et ce qui va changer une fois la migration terminée.
keywords: rbac;RBAC;rôle-based;role-based;role-based contrôles d'accès
seo-description: La gestion des utilisateurs de l'Audience Manager se déplace vers Adobe Admin Console. Cet article explique ce que vous devez faire pour préparer la migration des utilisateurs et ce qui va changer une fois la migration terminée.
seo-title: Audience Manager de la migration des utilisateurs vers le Admin Console
solution: Audience Manager
title: Audience Manager de la migration des utilisateurs vers le Admin Console
feature: Administration
translation-type: tm+mt
source-git-commit: 2e01abab2616daccd7581cdaa18417650951d139
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 3%

---


# [!DNL Audience Manager] migration d’utilisateur vers  [!DNL Admin Console] {#user-migration}

## Présentation {#overview}

[!DNL Audience Manager] la gestion des comptes d’utilisateurs se rend à Adobe Admin Console [ ](https://helpx.adobe.com/fr/enterprise/using/admin-console.html), ce qui vous permet de bénéficier d’une expérience plus rationnelle dans l’ensemble de vos solutions d’Adobe.

L&#39;utilisation de [!DNL Admin Console] présente les avantages suivants :

| Avantage | Description |
|---|---|
| Authentification unique solutions | [!DNL Audience Manager] les utilisateurs peuvent se connecter à  [!DNL Experience Cloud] et à toutes les autres solutions à l’aide de leur  [!DNL Adobe ID] ou  [!DNL Enterprise ID]. Cette connexion permet d&#39;accéder à des solutions intégrées et à des services principaux sur [!DNL Experience Cloud]. Après la migration, les utilisateurs qui tentent de se connecter via des connexions héritées (`bank.demdex.com`) seront redirigés vers `experiencecloud.adobe.com`. |
| Gestion des utilisateurs et des groupes | Une fois la migration terminée, [!DNL Audience Manager] les administrateurs gèrent les utilisateurs et les groupes exclusivement dans [[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/). |
| Gérer les produits et services | À partir de [[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/), les administrateurs peuvent : <ul><li>Créer, mettre à jour et supprimer des utilisateurs</li><li>Accorder l’accès aux solutions et services</li></ul> |

Pour faciliter la migration des utilisateurs, nous demandons à tous les [!DNL Audience Manager] administrateurs de début de migrer leurs comptes d’utilisateurs vers [Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html) le plus tôt possible, en suivant les étapes décrites dans cet article.

## Ce que les utilisateurs doivent faire {#what-to-do-users}

En tant qu&#39;utilisateur d&#39;Audience Manager, il vous suffit de contacter votre administrateur [!DNL Audience Manager] et de lui demander de créer un nouveau compte d&#39;utilisateur pour vous dans [!DNL Admin Console].

## Ce que les administrateurs doivent faire {#what-to-do-admins}

Les administrateurs d’Audience Manager doivent suivre les étapes ci-dessous pour migrer les utilisateurs vers [!DNL Admin Console].

1. Accédez à [https://adminconsole.adobe.com](https://adminconsole.adobe.com) et connectez-vous en utilisant votre Adobe ID ou votre Enterprise ID. Si vous n’avez pas accès à [!DNL Admin Console], contactez le service à la clientèle ou votre consultant en Adobe.
2. Consultez le [!DNL Adobe Admin Console] [guide d&#39;aide](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html) pour obtenir des instructions détaillées sur la création et la gestion des comptes d&#39;utilisateurs.
3. Créez de nouveaux comptes d’utilisateurs pour tous vos utilisateurs d’Audience Manager existants.
4. Informer vos utilisateurs au sujet des comptes d’utilisateurs nouvellement créés. Une fois que les utilisateurs ont migré vers [!DNL Admin Console], ils doivent cesser d&#39;utiliser des connexions héritées.

## Considérations relatives à la migration des utilisateurs {#considerations}

Les utilisateurs et les administrateurs doivent tenir compte des points suivants pour la migration des utilisateurs d’Audience Manager :

* Une fois les nouveaux comptes d’utilisateurs créés dans le Admin Console, les autorisations existantes qu’ils possèdent à partir de leurs comptes d’utilisateurs hérités s’appliquent toujours.
* Les mises à jour des autorisations d&#39;utilisateur seront toujours gérées à partir de [!DNL Audience Manager]. Le [!DNL Admin Console] couvre uniquement la gestion des utilisateurs et des groupes.
* Les administrateurs n’ont pas besoin de désactiver les comptes d’utilisateurs hérités. Les anciens comptes d’utilisateurs seront automatiquement fusionnés dans les comptes migrés.
