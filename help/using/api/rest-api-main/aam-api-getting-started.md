---
description: Informations sur les configurations requises générales, authentification, paramètres de requête facultatifs, URL de requête et autres références.
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: Prise en main des API REST
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 95182160b37bb15df4867bbacd06d8d75c971fa3
workflow-type: tm+mt
source-wordcount: '1942'
ht-degree: 3%

---

# Prise en main de [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Informations sur les exigences générales, authentification, paramètres de requête facultatifs, requête [!DNL URLs] et autres références.

<!-- c_rest_api_overview.xml -->

## Configuration requise et recommandations pour l’API {#api-requirements-recommendations}

Ce que vous devez faire et devez faire lorsque vous utilisez les [!DNL Audience Manager] [!DNL API]s.

<!-- aam-api-requirements.xml -->

Notez ce qui suit lorsque vous utilisez le code [API d’Audience Manager](https://bank.demdex.com/portal/swagger/index.html#/) :

* **Paramètres de requête :** tous les paramètres de requête sont requis, sauf indication contraire.
* **En-têtes de requête** : lorsque vous utilisez des jetons d’ [Adobe I/](https://www.adobe.io/) , vous devez fournir l’ `x-api-key` en-tête . Vous pouvez obtenir votre clé [!DNL API] en suivant les instructions de la page [Intégration de compte de service](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) .
* **[!DNL JSON]type de contenu :** indiquez  `content-type: application/json`  **  `accept: application/json` et dans votre code.
* **Requêtes et réponses :** envoyez des requêtes sous la forme d’un  [!DNL JSON] objet correctement formaté. [!DNL Audience Manager] répond avec des données  [!DNL JSON] formatées. Les réponses du serveur peuvent contenir les données demandées, un code d’état ou les deux.
* **Accès :** votre  [!DNL Audience Manager] consultant vous fournira un identifiant client et une clé qui vous permettront d’effectuer  [!DNL API] des requêtes.
* **Documentation et exemples de code :** le texte en  ** italique représente une variable que vous fournissez ou transmettez lors de la création ou de la réception de  [!DNL API] données. Remplacez *italicized* par votre propre code, paramètres ou d’autres informations requises.

## Authentification {#authentication}

[!DNL Audience Manager] [!DNL REST APIs] prend en charge deux méthodes d’authentification.

* [JWT (Service Account) ](#jwt) Authentification à l’aide d’ [Adobe I/O](https://www.adobe.io/). [!DNL Adobe I/O] est l’écosystème de développement et la communauté de l’Adobe. Il comprend les [outils de développement d’Adobe I/O et les API](https://www.adobe.io/apis/experienceplatform.html) et [API pour tous les produits d’Adobe](https://www.adobe.io/apis.html). Il s’agit de la méthode recommandée pour configurer et utiliser [!DNL Adobe] [!DNL APIs].
* [Authentification OAuth (obsolète)](#oauth). Bien que cette méthode soit obsolète, les clients avec des intégrations [!DNL OAuth] existantes peuvent continuer à utiliser cette méthode.

>[!IMPORTANT]
>
>Selon votre méthode d’authentification, vous devez ajuster votre requête [!DNL URLs] en conséquence. Voir la section [Environnements](#environments) pour plus d’informations sur les noms d’hôtes que vous devez utiliser.

## [!DNL JWT] ([!DNL Service Account]) Authentification par Adobe I/O {#jwt}

### Présentation des Adobes I/O {#adobeio}

[!DNL Adobe I/O] est l’écosystème de développement et la communauté de l’Adobe. Il comprend les [outils de développement d’Adobe I/O et les API](https://www.adobe.io/apis/experienceplatform.html) et [API pour tous les produits d’Adobe](https://www.adobe.io/apis.html).

Il s’agit de la méthode recommandée pour configurer et utiliser [!DNL Adobe] [!DNL APIs].

### Conditions préalables {#prerequisites}

Avant de pouvoir configurer l’authentification [!DNL JWT], vérifiez que vous avez accès à [Adobe Developer Console](https://console.adobe.io/) dans [Adobe I/O](https://www.adobe.io/). Contactez l’administrateur de votre entreprise pour les demandes d’accès.

### Authentification {#auth}

Suivez les étapes ci-dessous pour configurer l’authentification [!DNL JWT (Service Account)] à l’aide de [!DNL Adobe I/O] :

1. Connectez-vous à [Adobe Developer Console](https://console.adobe.io/).
1. Suivez les étapes de la section [Connexion au compte de service](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * Pendant [Étape 2 : Ajoutez une API à votre projet à l’aide de l’authentification du compte de service ](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), sélectionnez l’option [!DNL Audience Manager] [!DNL API].
1. Essayez la connexion en effectuant votre premier appel [!DNL API] en fonction des instructions de l’[étape 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Pour configurer et utiliser [!DNL Audience Manager] [!DNL REST APIs] de manière automatisée, vous pouvez générer le [!DNL JWT] par programmation. Voir [Authentification JWT (compte de service)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) pour obtenir des instructions détaillées.

### Autorisations RBAC du compte technique

Si votre compte d’Audience Manager utilise le [contrôle d’accès en fonction du rôle](../../features/administration/administration-overview.md), vous devez créer un compte d’utilisateur technique d’Audience Manager et l’ajouter au groupe RBAC d’Audience Manager qui effectuera les appels d’API.

Pour créer un compte d’utilisateur technique et l’ajouter à un groupe RBAC, procédez comme suit :

1. Effectuez un appel `GET` à `https://aam.adobe.io/v1/users/self`. L’appel crée un compte utilisateur technique que vous pouvez voir dans la [!UICONTROL Admin Console], sur la page [!UICONTROL Users].

   ![compte technique](assets/technical-account.png)

1. Connectez-vous à votre compte d’Audience Manager et [ajoutez le compte d’utilisateur technique](../../features/administration/administration-overview.md#create-group) au groupe d’utilisateurs qui effectuera les appels API.

## [!DNL OAuth] Authentification (obsolète) {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] l’authentification et le renouvellement des jetons via  [!DNL OAuth 2.0] sont désormais obsolètes.
>
> Utilisez plutôt [l’authentification JWT (compte de service)](#jwt-service-account-authentication-jwt).

[!DNL Audience Manager] [!UICONTROL REST API] suit les normes [!DNL OAuth 2.0] pour l’authentification et le renouvellement des jetons. Les sections ci-dessous décrivent comment vous authentifier et commencer à utiliser les [!DNL API]s.

### Créer un utilisateur générique [!DNL API] {#requirements}

Nous vous recommandons de créer un compte utilisateur technique distinct pour travailler avec les [!DNL Audience Manager] [!DNL API]s. Il s’agit d’un compte générique qui n’est pas lié ou associé à un utilisateur spécifique de votre entreprise. Ce type de compte utilisateur [!DNL API] vous permet d’accomplir 2 tâches :

* Identifiez le service qui appelle [!DNL API] (par exemple, les appels provenant de vos applications qui utilisent nos [!DNL API]s ou d’autres outils qui effectuent des demandes [!DNL API]).
* Accordez un accès ininterrompu aux [!DNL API]s. Un compte lié à une personne spécifique peut être supprimé lorsqu’il quitte votre société. Cela vous empêchera de travailler avec le code [!DNL API] disponible. Un compte générique qui n’est pas lié à un employé spécifique vous permet d’éviter ce problème.

Par exemple, pour ce type de compte, supposons que vous souhaitiez modifier de nombreux segments à la fois avec les [outils de gestion en bloc](../../reference/bulk-management-tools/bulk-management-intro.md). Pour ce faire, votre compte utilisateur doit disposer d’un accès [!DNL API]. Au lieu d’ajouter des autorisations à un utilisateur spécifique, créez un compte utilisateur [!DNL API] non spécifique qui dispose des informations d’identification, de la clé et du secret appropriés pour effectuer des appels [!DNL API]. Cela s’avère également utile si vous développez vos propres applications qui utilisent les [!DNL Audience Manager] [!DNL API]s.

Contactez votre consultant [!DNL Audience Manager] pour configurer un compte utilisateur générique [!DNL API] uniquement.

### Processus d’authentification par mot de passe {#password-authentication-workflow}

L&#39;authentification par mot de passe sécurise l&#39;accès à notre [!DNL REST API]. Les étapes ci-dessous décrivent le workflow d’authentification par mot de passe d’un client [!DNL JSON] dans votre navigateur.

>[!TIP]
>
>Chiffrez l’accès et actualisez les jetons si vous les stockez dans une base de données.

#### Étape 1 : Demande d’accès [!DNL API]

Contactez votre responsable Partenaires en solutions . Ils vous fourniront un ID client [!DNL API] et un secret. L’identifiant et le secret vous authentifient dans la balise [!DNL API].

Remarque : Si vous souhaitez recevoir un jeton d’actualisation, indiquez-le lorsque vous demandez l’accès [!DNL API].

#### Étape 2 : Demander le jeton

Transmettez une requête de jeton avec votre client [!DNL JSON] préféré. Lorsque vous créez la requête :

* Utilisez une méthode `POST` pour appeler `https://api.demdex.com/oauth/token`.
* Convertissez votre ID client et votre secret client en chaîne codée en base 64. Séparez l’ID et le secret par deux points au cours du processus de conversion. Par exemple, les informations d’identification `testId : testSecret` sont converties en `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Transmettez [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` et `Content-Type: application/x-www-form-urlencoded` . Par exemple, votre en-tête peut ressembler à ceci : <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Configurez le corps de la requête comme suit :
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Étape 3 : Réception du jeton

La réponse [!DNL JSON] contient votre jeton d’accès. La réponse doit se présenter comme suit :

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

La clé `expires_in` représente le nombre de secondes jusqu’à l’expiration du jeton d’accès. Pour respecter les bonnes pratiques, utilisez de courts délais d’expiration pour limiter l’exposition si le jeton est un jour exposé.

### Actualiser le jeton {#refresh-token}

Actualisez les jetons pour renouveler l’accès [!DNL API] après l’expiration du jeton d’origine. Si nécessaire, la réponse [!DNL JSON] du workflow de mot de passe inclut un jeton d’actualisation. Si vous ne recevez pas de jeton d’actualisation, créez-en un nouveau par le biais du processus d’authentification par mot de passe.

Vous pouvez également utiliser un jeton d’actualisation pour générer un nouveau jeton avant l’expiration du jeton d’accès existant.

Si votre jeton d’accès a expiré, vous recevez un `401 Status Code` et l’en-tête suivant dans la réponse :

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

Les étapes suivantes décrivent le processus d’utilisation d’un jeton d’actualisation pour créer un nouveau jeton d’accès à partir d’un client [!DNL JSON] dans votre navigateur.

#### Étape 1 : Demander le nouveau jeton

Transmettez une requête de jeton d’actualisation avec votre client [!DNL JSON] préféré. Lorsque vous créez la requête :

* Utilisez une méthode `POST` pour appeler `https://api.demdex.com/oauth/token`.
* Convertissez votre ID client et votre secret client en chaîne codée en base 64. Séparez l’ID et le secret par deux points au cours du processus de conversion. Par exemple, les informations d’identification `testId : testSecret` sont converties en `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Transmettez les en-têtes HTTP `Authorization:Basic <base-64 clientID:clientSecret>` et `Content-Type: application/x-www-form-urlencoded`. Par exemple, votre en-tête peut ressembler à ceci : <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* Dans le corps de la requête, spécifiez la balise `grant_type:refresh_token` et transmettez le jeton d’actualisation que vous avez reçu dans votre demande d’accès précédente. La requête doit se présenter comme suit : <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Étape 2 : Réception du nouveau jeton

La réponse [!DNL JSON] contient votre nouveau jeton d’accès. La réponse doit se présenter comme suit :

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

### Code d’autorisation et authentification implicite {#authentication-code-implicit}

[!DNL Audience Manager] [!UICONTROL REST API] prend en charge le code d’autorisation et l’authentification implicite. Pour utiliser ces méthodes d’accès, vos utilisateurs doivent se connecter à `https://api.demdex.com/oauth/authorize` pour accéder aux jetons et les actualiser.

## Lancer des requêtes [!DNL API] authentifiées {#authenticated-api-requests}

Conditions requises pour appeler les méthodes [!DNL API] après réception d’un jeton d’authentification.

Pour lancer des appels par rapport aux méthodes [!DNL API] disponibles :

* Dans l’en-tête `HTTP`, définissez `Authorization: Bearer <token>`.
* Lors de l’utilisation de l’authentification [JWT (compte de service)](#jwt), vous devez fournir l’en-tête `x-api-key`, qui sera identique à votre `client_id`. Vous pouvez obtenir votre `client_id` à partir de la page [Intégration des Adobes I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) .
* Appelez la méthode [!DNL API] requise.

## Paramètres de requête facultatifs [!DNL API] {#optional-api-query-parameters}

Définissez les paramètres facultatifs disponibles pour les méthodes qui renvoient toutes les propriétés d’un objet.

Vous pouvez utiliser ces paramètres facultatifs avec des méthodes [!DNL API] qui renvoient les propriétés *all* d’un objet. Définissez ces options dans la chaîne de requête lors de la transmission de cette requête à [!DNL API].

| Paramètre | Description |
|--- |--- |
| `page` | Renvoie les résultats par numéro de page. La numérotation commence à 0. |
| `pageSize` | Définit le nombre de résultats de réponse renvoyés par la requête (10 est la valeur par défaut). |
| `sortBy` | Trie et renvoie les résultats en fonction de la propriété [!DNL JSON] spécifiée. |
| `descending` | Trie et renvoie les résultats dans l’ordre décroissant. `ascending` est la valeur par défaut. |
| `search` | Renvoie des résultats en fonction de la chaîne spécifiée que vous souhaitez utiliser comme paramètre de recherche. Par exemple, supposons que vous souhaitiez trouver des résultats pour tous les modèles ayant le mot &quot;Test&quot; dans l’un des champs de valeur de cet élément. Votre exemple de requête peut ressembler à ceci :   `GET https://aam.adobe.io/v1/models/?search=Test`.  Vous pouvez effectuer une recherche sur n’importe quelle valeur renvoyée par une méthode &quot;[!DNL get all]&quot;. |
| `folderId` | Renvoie tous les identifiants de [!UICONTROL traits] dans le dossier spécifié. Non disponible pour toutes les méthodes. |
| `permissions` | Renvoie une liste de segments basée sur l’autorisation spécifiée. `READ` est la valeur par défaut. Les autorisations incluent :<ul><li>`READ` : Renvoi et affichage des informations sur un segment.</li><li>`WRITE` : Utilisez   `PUT`  pour mettre à jour un segment.</li><li>`CREATE` : Utilisez   `POST`  pour créer un segment.</li><li>`DELETE` : Suppression d’un segment. Nécessite l’accès aux caractéristiques sous-jacentes, le cas échéant. Par exemple, vous aurez besoin de droits pour supprimer les caractéristiques qui appartiennent à un segment si vous souhaitez le supprimer.</li></ul><br>Spécifiez plusieurs autorisations avec des paires clé-valeur distinctes. Par exemple, pour renvoyer une liste de segments avec les autorisations `READ` et `WRITE` uniquement, transmettez `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) Définissez cette variable sur `true` pour renvoyer vos autorisations pour le segment. La valeur par défaut est `false`. |

### Remarque À Propos Des Options De Page

Lorsque les informations sur la page *ne sont pas* spécifiées, la requête renvoie la valeur &quot;plain&quot; [!DNL JSON], ce qui génère un tableau. Si les informations sur la page *sont* spécifiées, la liste renvoyée est encapsulée dans un objet [!DNL JSON] contenant des informations sur le résultat total et la page active. Votre exemple de requête utilisant les options de page peut ressembler à ceci :

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] pour les demandes, les environnements d’évaluation et de production, ainsi que les versions.

## Demande [!DNL URLs] {#request-urls}

Le tableau suivant répertorie la requête [!DNL URLs] utilisée pour transmettre les requêtes [!DNL API], par méthode.

Selon la méthode d’authentification que vous utilisez, vous devez ajuster votre requête [!DNL URLs] en fonction des tableaux ci-dessous.

### Demande [!DNL URLs] d’authentification [!DNL JWT] {#request-urls-jwt}

| [!DNL API] Méthodes | Demande [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | Caractéristiques :  `https://aam.adobe.io/v1/folders/traits /`<br>Segments :  `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

### Demande [!DNL URLs] d’authentification [!DNL OAuth] (obsolète) {#request-urls-oauth}

| [!DNL API] Méthodes | Demande [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | Caractéristiques :  `https://api.demdex.com/v1/folders/traits /`<br>Segments :  `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

## Environnements {#environments}

Les [!DNL Audience Manager] [!DNL API]permettent d’accéder à différents environnements de travail. Ces environnements vous aident à tester le code par rapport à des bases de données distinctes sans affecter les données de production en direct. Le tableau suivant répertorie les environnements [!DNL API] disponibles et les noms d’hôtes de ressources correspondants.

Selon la méthode d’authentification que vous utilisez, vous devez ajuster votre environnement [!DNL URLs] en fonction du tableau ci-dessous.

| Environnement | Nom d’hôte pour l’authentification [!DNL JWT] | Nom d’hôte pour l’authentification [!DNL OAuth] |
|---|---|---|
| **Production** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>L’environnement bêta [!DNL Audience Manager] est une version autonome à plus petite échelle de l’environnement de production. Toutes les données que vous souhaitez tester doivent être entrées et collectées dans cet environnement.

## Versions {#versions}

De nouvelles versions de ces [!DNL API]s sont publiées régulièrement. Une nouvelle version incrémente le numéro de version [!DNL API] . Le numéro de version est référencé dans la requête [!DNL URL] sous la forme `v<version number>`, comme illustré dans l’exemple suivant :

`https://<host>/v1/...`

## Codes de réponse définis {#response-codes-defined}

`HTTP` codes d’état et texte de réponse renvoyés par  [!DNL Audience Manager] [!UICONTROL REST API].

| Identifiant de code de réponse | Texte de la réponse | Définition |
|---|---|---|
| `200` | `OK` | La requête a été traitée avec succès. Renvoie le contenu ou les données attendus, le cas échéant. |
| `201` | `Created` | La ressource a été créée. Renvoie pour les demandes `PUT` et `POST`. |
| `204` | `No Content` | La ressource a été supprimée. Le corps de la réponse sera vide. |
| `400` | `Bad Request` | Le serveur n’a pas compris la requête. Généralement en raison d’une syntaxe incorrecte. Vérifiez votre requête, puis réessayez. |
| `403` | `Forbidden` | Vous n’avez pas accès à la ressource. |
| `404` | `Not Found` | La ressource est introuvable pour le chemin spécifié. |
| `409` | `Conflict` | Impossible de terminer la requête en raison d’un conflit avec l’état de la ressource. |
| `500` | `Server Error` | Le serveur a rencontré une erreur inattendue qui l’a empêché de répondre à la demande. |

>[!MORELIKETHIS]
>
>* [Authentification JWT (compte de service)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [Authentification OAuth](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 simplifié](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

