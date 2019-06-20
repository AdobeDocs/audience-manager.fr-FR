---
description: Informations sur les exigences générales, l'authentification, les paramètres de requête facultatifs, les URL de requête et d'autres références.
seo-description: Informations sur les exigences générales, l'authentification, les paramètres de requête facultatifs, les URL de requête et d'autres références.
seo-title: Prise en main des API REST
solution: Audience Manager
title: Prise en main des API REST
uuid: af 0 e 527 e -6 eec -449 c -9709-f 90 e 57 cd 188 d
translation-type: tm+mt
source-git-commit: 27800ce003a62733eece0d5de3b94737ed61133a

---


# Getting Started with REST APIs {#getting-started-with-rest-apis}

Informations sur les exigences générales, l&#39;authentification, les paramètres de requête facultatifs, les URL de requête et d&#39;autres références.

<!-- c_rest_api_overview.xml -->

## API Requirements and Recommendations {#api-requirements-recommendations}

Things you must and should do when working with the Audience Manager [!DNL API]s.

<!-- aam-api-requirements.xml -->

Note the following when working with [Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/) code:

* **Paramètres de requête :** Tous les paramètres de requête sont obligatoires sauf indication contraire.
* **[!DNL JSON]type de contenu :** Spécifiez `content-type: application/json`*et* `accept: application/json` dans votre code.

* **Demandes et réponses :** Envoyer des requêtes en tant [!DNL JSON] qu&#39;objet correctement formaté. [!DNL Audience Manager] répond aux [!DNL JSON] données formatées. Les réponses au serveur peuvent contenir les données demandées, un code d&#39;état ou les deux.

* **Accès :** Votre [!DNL Audience Manager] consultant vous fournira un identifiant client et une clé qui vous permettront de [!DNL API] créer des requêtes.

* **Documentation et exemples de code :** Le texte *en italique* représente une variable que vous fournissez ou que vous transmettez lors de la création ou de la réception [!DNL API] de données. Replace *italicised* text with your own code, parameters, or other required information.

## Recommendations: Create a Generic API User {#requirements}

We recommend you create a separate, technical user account for working with the Audience Manager [!DNL API]s. This is a generic account that is not tied to or associated with a specific user in your organization. This type of [!DNL API] user account helps you accomplish 2 things:

* Identify what service is calling the [!DNL API] (e.g., calls from your apps that use our [!DNL API]s or from other tools that make [!DNL API] requests).
* Provide uninterrupted access to the [!DNL API]s. An account tied to a specific person may be deleted when they leave your company. This will prevent you from working with the available [!DNL API] code. Un compte générique qui n&#39;est lié à aucun employé particulier permet d&#39;éviter ce problème.

As an example or use case for this type of account, let&#39;s say you want to change a lot of segments at once with the [Bulk Management Tools](../../reference/bulk-management-tools/bulk-management-intro.md). Well, to do this, your user account needs [!DNL API] access. Rather than add permissions to a specific user, create a non-specific, [!DNL API] user account that has the appropriate credentials, key, and secret to make [!DNL API] calls. This is also useful if you develop your own applications that use the Audience Manager [!DNL API]s.

Work with your Audience Manager consultant to set up a generic, [!DNL API]-only user account.

## OAuth Authentication {#oauth}

The Audience Manager [!UICONTROL REST API] follows [!DNL OAuth 2.0] standards for token authentication and renewal. The sections below describe how to authenticate and start working with the [!DNL API]s.

## Password Authentication Workflow {#password-authentication-workflow}

<!-- oath-authentication.xml -->

Password authentication secure access our [!DNL REST API]. The steps below outline the workflow for password authentication from a [!DNL JSON] client in your browser.

>[!TIP]
>
>Chiffrez l&#39;accès et actualisez les jetons si vous les stockez dans une base de données.

### Étape 1 : Accès à l&#39;API de requête

Contactez votre gestionnaire de solutions partenaires. They will provide you with an [!DNL API] client ID and secret. The ID and secret authenticate you to the [!DNL API].

Note: If you&#39;d like to receive a refresh token, specify that when you request [!DNL API] access.

### Étape 2 : Demander le jeton

Pass in a token request with your preferred [!DNL JSON] client. Lorsque vous créez la requête :

* Use a `POST` method to call `https://api.demdex.com/oauth/token`.
* Convertissez votre ID client et votre secret en chaînes codées base -64. Séparez l&#39;ID et le secret par deux points durant le processus de conversion. For example, the credentials `testId : testSecret` convert to `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pass in the [!DNL HTTP] headers `Authorization:Basic <base-64 clientID:clientSecret>` and `Content-Type: application/x-www-form-urlencoded` . For example, your header could look like this: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Configurez le corps de la requête comme suit :
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

### Étape 3 : Recevoir le jeton

[!DNL JSON] La réponse contient votre jeton d&#39;accès. La réponse doit se présenter comme suit :

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

The `expires_in` key represents the number of seconds until the access token expires. En règle générale, utilisez des délais d&#39;expiration courts pour limiter l&#39;exposition si le jeton est exposé.

## Refresh Token {#refresh-token}

Refresh tokens renew [!DNL API] access after the original token expires. If requested, the response [!DNL JSON] in the password workflow includes a refresh token. Si vous ne recevez pas de jeton d&#39;actualisation, créez-en un nouveau via le processus d&#39;authentification du mot de passe.

Vous pouvez également utiliser un jeton Actualiser pour générer un nouveau jeton avant l&#39;expiration du jeton d&#39;accès existant.

If your access token has expired, you receive a `401 Status Code` and the following header in the response:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

The following steps outline the workflow for using a refresh token to create a new access token from a [!DNL JSON] client in your browser.

### Étape 1 : Demander le nouveau jeton

Pass in a refresh token request with your preferred [!DNL JSON] client. Lorsque vous créez la requête :

* Use a `POST` method to call `https://api.demdex.com/oauth/token`.
* Convertissez votre ID client et votre secret en chaînes codées base -64. Séparez l&#39;ID et le secret par deux points durant le processus de conversion. For example, the credentials `testId : testSecret` convert to `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pass in the HTTP headers `Authorization:Basic <base-64 clientID:clientSecret>` and `Content-Type: application/x-www-form-urlencoded`. For example, your header could look like this: <br/> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/> `Content-Type: application/x-www-form-urlencoded`
* In the request body, specify the `grant_type:refresh_token` and pass in the refresh token you received in your previous access request. The request should look like this: <br/> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

### Étape 2 : Recevoir le nouveau jeton

[!DNL JSON] La réponse contient votre nouveau jeton d&#39;accès. La réponse doit se présenter comme suit :

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

## Authorization Code and Implicit Authentication {#authentication-code-implicit}

The Audience Manager [!UICONTROL REST API] supports authorization code and implicit authentication. To use these access methods, your users need to log in to `https://api.demdex.com/oauth/authorize` to get access and refresh tokens.

>[!MORE_ LIKE_ THIS]
>
>* [Oauth 2.0](https://oauth.net/2/)
>* [Oauth 2 simplifié](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)


## Make Authenticated API Requests {#authenticated-api-requests}

Requirements for calling [!DNL API] methods after you receive an authentication token.

<!-- c_oauth_call_methods.xml -->

To make calls against the available [!DNL API] methods:

* In the `HTTP` header, set `Authorization: Bearer <token>`.
* Call the required [!DNL API] method.

>[!MORE_ LIKE_ THIS]
>
>* [Authentification oauth](../../api/rest-api-main/aam-api-getting-started.md#oauth)


## Optional API Query Parameters {#optional-api-query-parameters}

Définissez les paramètres facultatifs disponibles pour les méthodes qui renvoient toutes les propriétés d&#39;un objet.

<!-- c_rest_api_optional.xml -->

You can use these optional parameters with [!DNL API] methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API].

| Paramètre | Description |
|--- |--- |
| page | Renvoie les résultats par numéro de page. La numérotation commence à 0. |
| Pagesize | Définit le nombre de résultats de réponse renvoyés par la requête (10 est par défaut). |
| Sortby | Sorts and returns results according to the specified [!DNL JSON] property. |
| décroissant | Trie et renvoie les résultats par ordre décroissant. L&#39;ordre croissant est par défaut. |
| recherche | Renvoie les résultats en fonction de la chaîne spécifiée que vous souhaitez utiliser comme paramètre de recherche. Par exemple, supposons que vous souhaitiez obtenir des résultats pour tous les modèles qui contiennent le mot « Test » dans l&#39;un des champs de valeur de cet élément. Your sample request could look like this:   `GET https://api.demdex.com/v1/models/?search=Test`.  Vous pouvez rechercher une valeur renvoyée par une méthode « get all ». |
| Folderid | Renvoie tous les ID des caractéristiques dans le dossier spécifié. Pas disponible pour toutes les méthodes. |
| autorisations | Renvoie une liste de segments en fonction de l&#39;autorisation spécifiée. READ est par défaut. Les autorisations incluent :<ul><li>`READ` : Renseignez et affichez les informations sur un segment.</li><li>`WRITE` : Permet `PUT` de mettre à jour un segment.</li><li>`CREATE` : Permet `POST` de créer un segment.</li><li>`DELETE` : Suppression d’un segment. Nécessite l&#39;accès aux caractéristiques sous-jacentes, le cas échéant. Par exemple, vous aurez besoin des droits pour supprimer les caractéristiques qui appartiennent à un segment si vous souhaitez le supprimer.</li></ul><br>Spécifiez plusieurs autorisations avec des paires clé-valeur distinctes. For example, to return a list of segments with  `READ`  and  `WRITE`  permissions only, pass in  `"permissions":"READ"`, `"permissions":"WRITE"` . |
| Includepermissions | (Booléen) Définissez cette valeur sur true pour renvoyer vos autorisations pour le segment. La valeur par défaut est false. |

### Remarque concernant les options de page

When page information *is not* specified, the request returns plain [!DNL JSON] results in an array. If page information *is* specified, then the returned list is wrapped in a [!DNL JSON] object that contains information about the total result and current page. Votre exemple de requête utilisant les options de page peut ressembler à celui-ci :

```
GET https://api.demdex.com/v1/models/?page=1&pageSize=2&search=Test
```

## URL des API {#api-urls}

[!DNL URLs] pour les demandes, les environnements d&#39;évaluation et de production et les versions.

<!-- r_rest_urls.xml -->

## Request URLs {#request-urls}

The following table lists the request URLs used to pass in [!DNL API] requests, by method.

| [!DNL API] Méthodes | Demande [!DNL URL] |
|--- |--- |
| Modélisation algorithmique | `https://api.demdex.com/v1/models/` |
| Source de données | `https://api.demdex.com/v1/datasources/` |
| Signaux dérivés | `https://api.demdex.com/v1/signals/derived/` |
| Destinations | `https://api.demdex.com/v1/destinations/` |
| Domaines | `https://api.demdex.com/v1/partner-sites/` |
| Dossiers | Traits:  `https://api.demdex.com/v1/folders/traits /`<br>Segments:  `https://api.demdex.com/v1/folders/segments /` |
| Schéma | `https://api.demdex.com/v1/schemas/` |
| Segments | `https://api.demdex.com/v1/segments/` |
| Caractéristiques | `https://api.demdex.com/v1/traits/` |
| Types de caractéristiques | `https://api.demdex.com/v1/customer-trait-types` |
| Taxonomie | `https://api.demdex.com/v1/taxonomies/0/` |

## Environments {#environments}

The [!DNL Audience Manager] [!DNL API]s provide access to different working environments. Ces environnements vous aident à tester le code par rapport à des bases de données distinctes sans affecter les données de production en direct. The following table lists the available [!DNL API] environments and corresponding resource hostnames.

| Environnement | Nom d’hôte |
|---|---|
| **Production** | `https://api.demdex.com/...` |
| **Bêta** | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>L&#39;environnement bêta d&#39;Audience Manager est une version autonome à plus petite échelle de l&#39;environnement de production. Toutes les données à tester doivent être entrées et collectées dans cet environnement.

## Versions {#versions}

New versions of these [!DNL API]s are released on a regular schedule. A new release increments the [!DNL API] version number. The version number is referenced in the request URL as `v<version number>` as shown in the following example:

`https://<host>/v1/...`

## Response Codes Defined {#response-codes-defined}

`HTTP` code d&#39;état et texte de réponse renvoyé par Audience Manager [!UICONTROL REST API].

<!-- r_api_http_response_codes.xml -->

| ID du code de réponse | Texte de réponse | Définition |
|---|---|---|
| 200 | OK | La requête a bien été traitée. Renvoie le contenu ou les données attendus si nécessaire. |
| 201 | Créé | La ressource a été créée. Returns for `PUT` and `POST` requests. |
| 204 | Aucun contenu | La ressource a été supprimée. Le corps de la réponse est vide. |
| 400 | Requête incorrecte | Le serveur n&#39;a pas compris la requête. En raison d&#39;une syntaxe incorrecte. Vérifiez votre requête et réessayez. |
| 403 | Interdit | Vous n&#39;avez pas accès à la ressource. |
| 404 | introuvables | Impossible de trouver la ressource pour le chemin spécifié. |
| 409 | Conflit | La requête n&#39;a pas pu être effectuée en raison d&#39;un conflit avec l&#39;état de la ressource. |
| 500 | Erreur de serveur | Le serveur a rencontré une erreur inattendue qui empêchait l&#39;exécution de la requête. |