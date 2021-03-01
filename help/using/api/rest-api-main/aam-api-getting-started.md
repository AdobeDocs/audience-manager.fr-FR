---
description: Informations sur les configurations requises générales, authentification, paramètres de requête facultatifs, URL de requête et autres références.
seo-description: Informations sur les configurations requises générales, authentification, paramètres de requête facultatifs, URL de requête et autres références.
seo-title: Prise en main des API REST
solution: Audience Manager
title: Prise en main des API REST
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
translation-type: tm+mt
source-git-commit: ab8745a8ba24154793201893a39a039b5a098833
workflow-type: tm+mt
source-wordcount: '1861'
ht-degree: 4%

---


# Prise en main de [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Informations sur les exigences générales, l&#39;authentification, les paramètres de requête facultatifs, la demande [!DNL URLs] et d&#39;autres références.

<!-- c_rest_api_overview.xml -->

## Configuration requise et recommandations pour l’API {#api-requirements-recommendations}

Ce que vous devez et devez faire lorsque vous travaillez avec les [!DNL Audience Manager] [!DNL API]s.

<!-- aam-api-requirements.xml -->

Tenez compte des points suivants lorsque vous utilisez le code [Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/) :

* **Paramètres de requête :** tous les paramètres de requête sont obligatoires, sauf indication contraire.
* **En-têtes** de demande : lorsque vous utilisez  [Adobe I/](https://www.adobe.io/) Otokens, vous devez fournir l’ `x-api-key` en-tête. Vous pouvez obtenir votre clé [!DNL API] en suivant les instructions de la page [Intégration du compte de service](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
* **[!DNL JSON]type de contenu :** indiquez  `content-type: application/json`  **  `accept: application/json` et dans votre code.
* **Requêtes et réponses :** envoie des requêtes sous la forme d’un  [!DNL JSON] objet correctement formaté. [!DNL Audience Manager] répond par des données  [!DNL JSON] formatées. Les réponses du serveur peuvent contenir des données demandées, un code d’état ou les deux.
* **Accès :** Votre  [!DNL Audience Manager] consultant vous fournira un ID de client et une clé qui vous permettront d’effectuer des  [!DNL API] requêtes.
* **Documentation et exemples de code :** Le texte en  ** italiques représente une variable que vous fournissez ou transmettez lors de la création ou de la réception de  [!DNL API] données. Remplacez *italicised* texte par votre propre code, paramètres ou toute autre information requise.

## Authentification {#authentication}

[!DNL Audience Manager] [!DNL REST APIs] prend en charge deux méthodes d&#39;authentification.

* [Authentification JWT (Service Account) ](#jwt) à l’aide d’ [Adobe I/O](https://www.adobe.io/). [!DNL Adobe I/O] est l&#39;écosystème et la communauté du développement de l&#39;Adobe. Il comprend les [outils de développement d&#39;Adobes I/O et les API](https://www.adobe.io/apis/experienceplatform.html) et [API pour tous les produits d&#39;Adobe](https://www.adobe.io/apis.html). Il s’agit de la méthode recommandée pour configurer et utiliser [!DNL Adobe] [!DNL APIs].
* [Authentification OAuth (désapprouvée)](#oauth). Bien que cette méthode soit obsolète, les clients avec des intégrations [!DNL OAuth] existantes peuvent continuer à utiliser cette méthode.

>[!IMPORTANT]
>
>Selon votre méthode d&#39;authentification, vous devez ajuster votre requête [!DNL URLs] en conséquence. Consultez la section [Environnements](#environments) pour plus d’informations sur les noms d’hôte que vous devez utiliser.

## [!DNL JWT] ([!DNL Service Account]Authentification par Adobe I/O)  {#jwt}

### Aperçu de l&#39;Adobe I/O {#adobeio}

[!DNL Adobe I/O] est l&#39;écosystème et la communauté du développement de l&#39;Adobe. Il comprend les [outils de développement d&#39;Adobes I/O et les API](https://www.adobe.io/apis/experienceplatform.html) et [API pour tous les produits d&#39;Adobe](https://www.adobe.io/apis.html).

Il s’agit de la méthode recommandée pour configurer et utiliser [!DNL Adobe] [!DNL APIs].

### Conditions préalables {#prerequisites}

Avant de pouvoir configurer l&#39;authentification [!DNL JWT], assurez-vous d&#39;avoir accès à la [Console développeur d&#39;Adobes](https://console.adobe.io/) dans [Adobe I/O](https://www.adobe.io/). Contactez l’administrateur de votre organisation pour obtenir des demandes d’accès.

### Authentification {#auth}

Suivez les étapes ci-dessous pour configurer l&#39;authentification [!DNL JWT (Service Account)] à l&#39;aide de [!DNL Adobe I/O] :

1. Connectez-vous à [Adobe Developer Console](https://console.adobe.io/).
1. Suivez les étapes décrites dans [Service Account Connection](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * Au cours de l&#39;[étape 2: Ajoutez une API à votre projet à l’aide de l’authentification du compte de service ](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), sélectionnez l’option [!DNL Audience Manager] [!DNL API].
1. Essayez la connexion en effectuant votre premier appel [!DNL API] en fonction des instructions de l&#39;[étape 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Pour configurer et utiliser [!DNL Audience Manager] [!DNL REST APIs] de manière automatisée, vous pouvez générer le [!DNL JWT] par programmation. Voir [Authentification JWT (Service Account)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) pour obtenir des instructions détaillées.

## [!DNL OAuth] Authentification (obsolète)  {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] l’authentification et le renouvellement des jetons par le biais  [!DNL OAuth 2.0] est désormais obsolète.
>
> Utilisez à la place [l&#39;authentification JWT (Service Account)](#jwt-service-account-authentication-jwt).

[!DNL Audience Manager] [!UICONTROL REST API] suit les normes [!DNL OAuth 2.0] pour l’authentification et le renouvellement des jetons. Les sections ci-dessous décrivent comment vous authentifier et début en utilisant les [!DNL API]s.

### Créer un utilisateur générique [!DNL API] {#requirements}

Nous vous recommandons de créer un compte utilisateur technique distinct pour travailler avec les [!DNL Audience Manager] [!DNL API]s. Il s’agit d’un compte générique qui n’est pas lié ou associé à un utilisateur spécifique de votre organisation. Ce type de compte utilisateur [!DNL API] permet d’accomplir 2 tâches :

* Identifiez le service qui appelle [!DNL API] (par exemple, les appels de vos applications qui utilisent nos [!DNL API]s ou d&#39;autres outils qui effectuent des demandes [!DNL API]).
* Fournissez un accès ininterrompu aux [!DNL API]s. Un compte lié à une personne spécifique peut être supprimé lorsqu&#39;il quitte votre société. Cela vous empêchera de travailler avec le code [!DNL API] disponible. Un compte générique qui n’est pas lié à un employé particulier permet d’éviter ce problème.

À titre d&#39;exemple ou de cas d&#39;utilisation pour ce type de compte, supposons que vous souhaitiez modifier plusieurs segments à la fois avec les [outils de gestion en bloc](../../reference/bulk-management-tools/bulk-management-intro.md). Pour ce faire, votre compte utilisateur doit disposer d’un accès [!DNL API]. Plutôt que d&#39;ajouter des autorisations à un utilisateur spécifique, créez un compte utilisateur [!DNL API] non spécifique disposant des informations d&#39;identification, de la clé et du secret appropriés pour effectuer des appels [!DNL API]. Cela s&#39;avère également utile si vous développez vos propres applications qui utilisent les [!DNL Audience Manager] [!DNL API]s.

Contactez votre consultant [!DNL Audience Manager] pour configurer un compte utilisateur générique [!DNL API] uniquement.

### Workflow d&#39;authentification de mot de passe {#password-authentication-workflow}

L&#39;authentification par mot de passe sécurise l&#39;accès à [!DNL REST API]. Les étapes ci-dessous décrivent le processus d&#39;authentification par mot de passe d&#39;un client [!DNL JSON] dans votre navigateur.

>[!TIP]
>
>Chiffrez l’accès et actualisez les jetons si vous les stockez dans une base de données.

#### Étape 1 : Demande d&#39;accès [!DNL API]

Contactez votre responsable Solutions partenaires. Ils vous fourniront un [!DNL API] identifiant client et un secret. L&#39;ID et le secret vous authentifient dans [!DNL API].

Remarque : Si vous souhaitez recevoir un jeton actualisé, indiquez-le lorsque vous demandez l’accès [!DNL API].

#### Étape 2 : Demander le jeton

Transférez une demande de jeton avec votre client [!DNL JSON] préféré. Lorsque vous créez la requête :

* Utilisez une méthode `POST` pour appeler `https://api.demdex.com/oauth/token`.
* Convertissez votre ID client et votre secret en chaîne codée en base 64. Séparez l’ID et le secret à l’aide de deux points au cours du processus de conversion. Par exemple, les informations d’identification `testId : testSecret` sont converties en `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Transmettez [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` et `Content-Type: application/x-www-form-urlencoded` . Par exemple, votre en-tête peut ressembler à ceci : <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Configurez le corps de la demande comme suit :
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Étape 3 : Recevoir le jeton

La réponse [!DNL JSON] contient votre jeton d&#39;accès. La réponse doit se présenter comme suit :

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

La clé `expires_in` représente le nombre de secondes avant l&#39;expiration du jeton d&#39;accès. Il est recommandé d’utiliser de courts délais d’expiration pour limiter l’exposition si le jeton est un jour exposé.

### Actualiser le jeton {#refresh-token}

Actualisez les jetons pour renouveler [!DNL API] l’accès après l’expiration du jeton d’origine. Si nécessaire, la réponse [!DNL JSON] dans le flux de travail des mots de passe comprend un jeton actualisé. Si vous ne recevez pas de jeton actualisé, créez-en un nouveau par le biais du processus d’authentification par mot de passe.

Vous pouvez également utiliser un jeton actualisé pour générer un nouveau jeton avant l’expiration du jeton d&#39;accès existant.

Si votre jeton d&#39;accès a expiré, vous recevez un `401 Status Code` et l&#39;en-tête suivant dans la réponse :

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

Les étapes suivantes décrivent le processus d’utilisation d’un jeton actualisé pour créer un jeton d&#39;accès à partir d’un client [!DNL JSON] dans votre navigateur.

#### Étape 1 : Demander le nouveau jeton

Transférez une demande de jeton actualisé avec votre client [!DNL JSON] préféré. Lorsque vous créez la requête :

* Utilisez une méthode `POST` pour appeler `https://api.demdex.com/oauth/token`.
* Convertissez votre ID client et votre secret en chaîne codée en base 64. Séparez l’ID et le secret à l’aide de deux points au cours du processus de conversion. Par exemple, les informations d’identification `testId : testSecret` sont converties en `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Transmettez les en-têtes HTTP `Authorization:Basic <base-64 clientID:clientSecret>` et `Content-Type: application/x-www-form-urlencoded`. Par exemple, votre en-tête peut ressembler à ceci : <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* Dans le corps de la requête, spécifiez `grant_type:refresh_token` et transmettez le jeton actualisé que vous avez reçu dans votre précédente requête d’accès. La demande doit se présenter comme suit : <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Étape 2 : Recevoir le nouveau jeton

La réponse [!DNL JSON] contient votre nouveau jeton d&#39;accès. La réponse doit se présenter comme suit :

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

[!DNL Audience Manager] [!UICONTROL REST API] prend en charge le code d&#39;autorisation et l&#39;authentification implicite. Pour utiliser ces méthodes d’accès, vos utilisateurs doivent se connecter à `https://api.demdex.com/oauth/authorize` pour accéder à  et actualiser les jetons.

## Faire des demandes authentifiées [!DNL API] {#authenticated-api-requests}

Exigences relatives à l&#39;appel des méthodes [!DNL API] après réception d&#39;un jeton d&#39;authentification.

Pour lancer des appels à l&#39;aide des méthodes [!DNL API] disponibles :

* Dans l&#39;en-tête `HTTP`, définissez `Authorization: Bearer <token>`.
* Lorsque vous utilisez [JWT (Service Account) Authentication](#jwt), vous devez fournir l&#39;en-tête `x-api-key`, qui sera identique à votre `client_id`. Vous pouvez obtenir votre `client_id` à partir de la page [Adobe I/O integration](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
* Appelez la méthode [!DNL API] requise.

## Paramètres de Requête [!DNL API] facultatifs {#optional-api-query-parameters}

Définissez les paramètres facultatifs disponibles pour les méthodes qui renvoient toutes les propriétés d’un objet.

Vous pouvez utiliser ces paramètres facultatifs avec des méthodes [!DNL API] qui renvoient les propriétés *all* pour un objet. Définissez ces options dans la chaîne de requête lorsque vous transmettez cette requête à [!DNL API].

| Paramètre | Description |
|--- |--- |
| `page` | Renvoie les résultats par numéro de page. Débuts de numérotation à 0. |
| `pageSize` | Définit le nombre de résultats de réponse renvoyés par la requête (10 est la valeur par défaut). |
| `sortBy` | Trie et renvoie les résultats selon la propriété [!DNL JSON] spécifiée. |
| `descending` | Trie et renvoie les résultats dans l’ordre décroissant. `ascending` est définie par défaut. |
| `search` | Renvoie des résultats basés sur la chaîne spécifiée que vous souhaitez utiliser comme paramètre de recherche. Supposons, par exemple, que vous souhaitiez trouver des résultats pour tous les modèles qui contiennent le mot &quot;Test&quot; dans l’un des champs de valeur de cet élément. Votre exemple de demande peut se présenter comme suit :   `GET https://aam.adobe.io/v1/models/?search=Test`.  Vous pouvez effectuer une recherche sur toute valeur renvoyée par une méthode &quot;[!DNL get all]&quot;. |
| `folderId` | Renvoie tous les ID de [!UICONTROL traits] dans le dossier spécifié. Non disponible pour toutes les méthodes. |
| `permissions` | Renvoie une liste de segments basée sur l’autorisation spécifiée. `READ` est définie par défaut. Les autorisations comprennent :<ul><li>`READ` : Informations de retour et de vue sur un segment.</li><li>`WRITE` : Utilisez   `PUT`  pour mettre à jour un segment.</li><li>`CREATE` : Utilisez   `POST`  pour créer un segment.</li><li>`DELETE` : Suppression d’un segment. Nécessite l&#39;accès aux caractéristiques sous-jacentes, le cas échéant. Par exemple, vous aurez besoin de droits pour supprimer les caractéristiques qui appartiennent à un segment si vous souhaitez le supprimer.</li></ul><br>Spécifiez plusieurs autorisations avec des paires clé-valeur distinctes. Par exemple, pour renvoyer une liste de segments avec les autorisations `READ` et `WRITE` uniquement, transmettez `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) Définissez ce paramètre sur `true` pour renvoyer vos autorisations pour le segment. La valeur par défaut est `false`. |

### Remarque concernant les options de page

Lorsque les informations de page *ne sont pas* spécifiées, la requête renvoie plain [!DNL JSON] résulte en un tableau. Si les informations de page *sont* spécifiées, la liste renvoyée est encapsulée dans un objet [!DNL JSON] contenant des informations sur le résultat total et la page active. Votre exemple de requête utilisant les options de page peut ressembler à ceci :

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] pour les demandes, les environnements d’évaluation et de production et les versions.

## Demande [!DNL URLs] {#request-urls}

Le tableau suivant liste la requête [!DNL URLs] utilisée pour transmettre des requêtes [!DNL API], par méthode.

Selon la méthode d&#39;authentification que vous utilisez, vous devez ajuster votre requête [!DNL URLs] en fonction des tableaux ci-dessous.

### Demande [!DNL URLs] d&#39;authentification [!DNL JWT] {#request-urls-jwt}

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

### Demande [!DNL URLs] d&#39;authentification [!DNL OAuth] (obsolète) {#request-urls-oauth}

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

Les [!DNL Audience Manager] [!DNL API]s permettent d&#39;accéder à différents environnements de travail. Ces environnements vous aident à tester le code par rapport à des bases de données distinctes sans affecter les données de production en direct. Le tableau suivant liste les environnements [!DNL API] disponibles et les noms d&#39;hôte de ressources correspondants.

Selon la méthode d&#39;authentification que vous utilisez, vous devez ajuster votre environnement [!DNL URLs] en fonction du tableau ci-dessous.

| Environnement | Nom d&#39;hôte pour l&#39;authentification [!DNL JWT] | Nom d&#39;hôte pour l&#39;authentification [!DNL OAuth] |
|---|---|---|
| **Production** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Bêta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>L&#39;environnement [!DNL Audience Manager] bêta est une version autonome à plus petite échelle de l&#39;environnement de production. Toutes les données à tester doivent être entrées et collectées dans cet environnement.

## Versions {#versions}

De nouvelles versions de ces [!DNL API]s sont publiées régulièrement. Une nouvelle version incrémente le numéro de version [!DNL API]. Le numéro de version est référencé dans la requête [!DNL URL] sous la forme `v<version number>`, comme indiqué dans l’exemple suivant :

`https://<host>/v1/...`

## Codes de réponse définis {#response-codes-defined}

`HTTP` les codes d’état et le texte de réponse renvoyés par le  [!DNL Audience Manager] [!UICONTROL REST API].

| ID de code de réponse | Texte de la réponse | Définition |
|---|---|---|
| `200` | `OK` | La demande a été traitée avec succès. Renverra le contenu ou les données attendus si nécessaire. |
| `201` | `Created` | La ressource a été créée. Renvoie pour les requêtes `PUT` et `POST`. |
| `204` | `No Content` | La ressource a été supprimée. Le corps de la réponse sera vide. |
| `400` | `Bad Request` | Le serveur n&#39;a pas compris la demande. Généralement en raison d’une syntaxe incorrecte. Vérifiez votre demande et réessayez. |
| `403` | `Forbidden` | Vous n&#39;avez pas accès à la ressource. |
| `404` | `Not Found` | Impossible de trouver la ressource pour le chemin spécifié. |
| `409` | `Conflict` | Impossible de terminer la demande en raison d&#39;un conflit avec l&#39;état de la ressource. |
| `500` | `Server Error` | Le serveur a rencontré une erreur inattendue qui l&#39;a empêchée de répondre à la demande. |

>[!MORELIKETHIS]
>
>* [Authentification JWT (Service Account)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [Authentification OAuth](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 simplifié](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

