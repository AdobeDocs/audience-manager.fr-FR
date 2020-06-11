---
description: Informations sur les exigences générales, l’authentification, les paramètres de requête facultatifs, les URL de demande et d’autres références.
seo-description: Informations sur les exigences générales, l’authentification, les paramètres de requête facultatifs, les URL de demande et d’autres références.
seo-title: Prise en main des API REST
solution: Audience Manager
title: Prise en main des API REST
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
translation-type: tm+mt
source-git-commit: e51a4302808958093342170d513701ac1547c275
workflow-type: tm+mt
source-wordcount: '1890'
ht-degree: 3%

---


# Prise en main des API REST {#getting-started-with-rest-apis}

Informations sur les exigences générales, l’authentification, les paramètres de requête facultatifs, les URL de demande et d’autres références.

<!-- c_rest_api_overview.xml -->

## Configuration requise et recommandations pour l’API {#api-requirements-recommendations}

Ce que vous devez et devez faire lorsque vous travaillez avec les gestionnaires d’Audiences [!DNL API]s.

<!-- aam-api-requirements.xml -->

Tenez compte des points suivants lorsque vous utilisez le code API [](https://bank.demdex.com/portal/swagger/index.html#/) Audience Manager :

* **Paramètres de requête :** Tous les paramètres de requête sont requis, sauf indication contraire.
* **En-têtes** de demande : lorsque vous utilisez des jetons d&#39;E/S [](https://www.adobe.io/) Adobe, vous devez fournir l&#39; `x-api-key` en-tête. Vous pouvez obtenir votre clé d’API en suivant les instructions de la page d’intégration [du compte de](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) service.
* **[!DNL JSON]type de contenu :**Spécifiez`content-type: application/json`et **`accept: application/json`dans votre code.

* **Demandes et réponses :** Envoie les requêtes sous la forme d’un [!DNL JSON] objet correctement formaté. [!DNL Audience Manager] répond par des données [!DNL JSON] formatées. Les réponses du serveur peuvent contenir des données demandées, un code d’état ou les deux.

* **Accès :** Votre [!DNL Audience Manager] consultant vous fournira un ID de client et une clé qui vous permettront de faire [!DNL API] des demandes.

* **Documentation et exemples de code :** Le texte en *italique* représente une variable que vous fournissez ou transmettez lors de la création ou de la réception de [!DNL API] données. Remplacez le texte *en italique* par votre propre code, paramètres ou autres informations requises.

## Authentification {#authentication}

Les API REST d’Audience Manager prennent en charge deux méthodes d’authentification.

* [Authentification](#jwt)JWT (Service Account). Il s’agit de la méthode d’authentification recommandée.
* [Authentification OAuth (désapprouvée)](#oauth). Bien que cette méthode soit obsolète, les clients avec des intégrations OAuth existantes peuvent continuer à utiliser cette méthode.

>[!IMPORTANT]
>
>En fonction de votre méthode d’authentification, vous devez ajuster les URL de requête en conséquence. Consultez la section [Environnements](#environments) pour plus d’informations sur les noms d’hôtes à utiliser.

## Authentification JWT (Service Account) {#jwt}

### Conditions préalables {#prerequisites}

Avant de pouvoir configurer l’authentification JWT, assurez-vous d’avoir accès à la Console [développeur](https://console.adobe.io/)Adobe. Contactez l’administrateur de votre organisation pour obtenir des demandes d’accès.

### Authentification

Suivez les étapes ci-dessous pour configurer l’authentification JWT (Service Account) :

1. Connectez-vous à la Console [développeur](https://console.adobe.io/)Adobe.
1. Suivez les étapes décrites dans Connexion [au compte](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)de service.
   * Au cours de l’ [étape 2 : Ajoutez une API à votre projet à l’aide de l’authentification](https://www.adobe.io/authentication/auth-methods.html#step-2-add-an-api-to-your-project-using-service-account-authentication)du compte de service, sélectionnez l’option API Audience Manager.
1. Essayez la connexion en effectuant votre premier appel d&#39;API en fonction des instructions de l&#39; [étape 3](https://www.adobe.io/authentication/auth-methods.html#step-3-try-it.).

>[!NOTE]
>
>Pour configurer et utiliser les API REST d’Audience Manager de manière automatisée, vous pouvez générer le fichier JWT par programmation. Voir Authentification [](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) JWT (Service Account) pour obtenir des instructions détaillées.

## Authentification OAuth (obsolète) {#oauth}

>[!WARNING]
> L’authentification et le renouvellement des [!UICONTROL REST API] jetons du Gestionnaire d’Audiences [!DNL OAuth 2.0] sont désormais obsolètes.
>
> Utilisez plutôt l&#39;authentification [](#jwt-service-account-authentication-jwt) JWT (Service Account).

Le gestionnaire des Audiences [!UICONTROL REST API] respecte [!DNL OAuth 2.0] les normes d’authentification et de renouvellement des jetons. Les sections ci-dessous décrivent comment vous authentifier et début en utilisant les [!DNL API]s.

### Création d’un utilisateur API générique {#requirements}

Nous vous recommandons de créer un compte d’utilisateur technique distinct pour travailler avec les gestionnaires d’Audiences [!DNL API]s. Il s’agit d’un compte générique qui n’est pas lié ou associé à un utilisateur spécifique de votre organisation. Ce type de compte [!DNL API] utilisateur vous permet d’accomplir deux tâches :

* Identifiez le service qui appelle le [!DNL API] (par exemple, les appels de vos applications qui utilisent nos [!DNL API]applications ou d&#39;autres outils qui effectuent des [!DNL API] demandes).
* Fournir un accès ininterrompu aux [!DNL API]s. Un compte lié à une personne spécifique peut être supprimé lorsqu&#39;il quitte votre société. Cela vous empêchera de travailler avec le [!DNL API] code disponible. Un compte générique qui n’est pas lié à un employé particulier permet d’éviter ce problème.

À titre d&#39;exemple ou de cas d&#39;utilisation pour ce type de compte, supposons que vous souhaitiez modifier un grand nombre de segments à la fois avec les outils [de gestion](../../reference/bulk-management-tools/bulk-management-intro.md)en bloc. Eh bien, pour ce faire, votre compte d&#39;utilisateur a besoin d&#39; [!DNL API] accès. Plutôt que d’ajouter des autorisations à un utilisateur spécifique, créez un compte d’ [!DNL API] utilisateur non spécifique doté des informations d’identification, de la clé et du secret appropriés pour effectuer [!DNL API] des appels. Cela s’avère également utile si vous développez vos propres applications qui utilisent les Audiences Manager [!DNL API]s.

Contactez votre consultant Audience Manager pour configurer un compte d’utilisateur générique [!DNL API]uniquement.

### Workflow d’authentification de mot de passe {#password-authentication-workflow}

<!-- oath-authentication.xml -->

L&#39;authentification par mot de passe sécurise l&#39;accès à notre [!DNL REST API]site. Les étapes ci-dessous décrivent le processus d’authentification par mot de passe d’un [!DNL JSON] client de votre navigateur.

>[!TIP]
>
>Chiffrez l’accès et actualisez les jetons si vous les stockez dans une base de données.

#### Étape 1 : Demande d’accès à l’API

Contactez votre responsable Solutions partenaires. Ils vous fourniront un ID [!DNL API] client et un secret. L’ID et le secret vous authentifient auprès du [!DNL API].

Remarque : Si vous souhaitez recevoir un jeton actualisé, indiquez-le lorsque vous demandez l’ [!DNL API] accès.

#### Étape 2 : Demander le jeton

Transmettez une demande de jeton à votre [!DNL JSON] client préféré. Lorsque vous créez la requête :

* Utilisez une `POST` méthode pour appeler `https://api.demdex.com/oauth/token`.
* Convertissez votre ID client et votre secret en chaîne codée en base 64. Séparez l’ID et le secret à l’aide de deux points au cours du processus de conversion. Par exemple, les informations d’identification `testId : testSecret` sont converties en `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Transmettez les [!DNL HTTP] en-têtes `Authorization:Basic <base-64 clientID:clientSecret>` et `Content-Type: application/x-www-form-urlencoded` . Par exemple, votre en-tête peut ressembler à ceci : <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Configurez le corps de la demande comme suit :
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Étape 3 : Recevoir le jeton

La [!DNL JSON] réponse contient votre jeton d&#39;accès. La réponse doit se présenter comme suit :

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

La `expires_in` clé représente le nombre de secondes avant l’expiration du jeton d&#39;accès. Il est recommandé d’utiliser de courts délais d’expiration pour limiter l’exposition si le jeton est un jour exposé.

### Actualiser le jeton {#refresh-token}

Actualisez les jetons pour renouveler [!DNL API] l’accès après l’expiration du jeton d’origine. Si cela est demandé, la réponse [!DNL JSON] du flux de travail des mots de passe inclut un jeton actualisé. Si vous ne recevez pas de jeton actualisé, créez-en un nouveau par le biais du processus d’authentification par mot de passe.

Vous pouvez également utiliser un jeton actualisé pour générer un nouveau jeton avant l’expiration du jeton d&#39;accès existant.

Si votre jeton d&#39;accès a expiré, vous recevez un en-tête `401 Status Code` et l’en-tête suivants dans la réponse :

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

Les étapes suivantes décrivent le processus d’utilisation d’un jeton d’actualisation pour créer un jeton d&#39;accès à partir d’un [!DNL JSON] client dans votre navigateur.

#### Étape 1 : Demander le nouveau jeton

Transférez une demande de jeton actualisé avec votre [!DNL JSON] client préféré. Lorsque vous créez la requête :

* Utilisez une `POST` méthode pour appeler `https://api.demdex.com/oauth/token`.
* Convertissez votre ID client et votre secret en chaîne codée en base 64. Séparez l’ID et le secret à l’aide de deux points au cours du processus de conversion. Par exemple, les informations d’identification `testId : testSecret` sont converties en `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Transmettez les en-têtes HTTP `Authorization:Basic <base-64 clientID:clientSecret>` et `Content-Type: application/x-www-form-urlencoded`. Par exemple, votre en-tête peut ressembler à ceci : <br/> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/> `Content-Type: application/x-www-form-urlencoded`
* Dans le corps de la requête, spécifiez le jeton `grant_type:refresh_token` actualisé que vous avez reçu dans votre précédente requête d’accès et transmettez-le. La demande doit se présenter comme suit : <br/> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Étape 2 : Recevoir le nouveau jeton

La [!DNL JSON] réponse contient votre nouveau jeton d&#39;accès. La réponse doit se présenter comme suit :

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

Le Gestionnaire d’Audiences [!UICONTROL REST API] prend en charge le code d’autorisation et l’authentification implicite. Pour utiliser ces méthodes d’accès, les utilisateurs doivent se connecter pour accéder `https://api.demdex.com/oauth/authorize` et actualiser les jetons.

## Faire des demandes d’API authentifiées {#authenticated-api-requests}

Conditions requises pour appeler [!DNL API] les méthodes après réception d’un jeton d’authentification.

<!-- c_oauth_call_methods.xml -->

Pour lancer des appels par rapport aux [!DNL API] méthodes disponibles :

* Dans l’ `HTTP` en-tête, définissez `Authorization: Bearer <token>`.
* Lors de l’utilisation de l’authentification [](#jwt)JWT (Service Account), vous devez fournir l’ `x-api-key` en-tête, qui sera identique à celui de votre `client_id`compte. Vous pouvez accéder à votre `client_id` demande à partir de la page d&#39;intégration [des E/S](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) Adobe.
* Appelez la [!DNL API] méthode requise.

## Paramètres facultatifs de la Requête API {#optional-api-query-parameters}

Définissez les paramètres facultatifs disponibles pour les méthodes qui renvoient toutes les propriétés d’un objet.

<!-- c_rest_api_optional.xml -->

Vous pouvez utiliser ces paramètres facultatifs avec [!DNL API] des méthodes qui renvoient *toutes les* propriétés d’un objet. Définissez ces options dans la chaîne de requête lors de la transmission de cette requête à la [!DNL API].

| Paramètre | Description |
|--- |--- |
| page | Renvoie les résultats par numéro de page. débuts de numérotation à 0. |
| pageSize | Définit le nombre de résultats de réponse renvoyés par la requête (10 est la valeur par défaut). |
| sortBy | Trie et renvoie les résultats selon la [!DNL JSON] propriété spécifiée. |
| décroissant | Trie et renvoie les résultats dans l’ordre décroissant. Ascendant est défini par défaut. |
| rechercher | Renvoie des résultats basés sur la chaîne spécifiée que vous souhaitez utiliser comme paramètre de recherche. Supposons, par exemple, que vous souhaitiez trouver des résultats pour tous les modèles qui contiennent le mot &quot;Test&quot; dans l’un des champs de valeur de cet élément. Votre exemple de demande peut se présenter comme suit :   `GET https://aam.adobe.io/v1/models/?search=Test`.  Vous pouvez rechercher n’importe quelle valeur renvoyée par une méthode &quot;get all&quot;. |
| folderId | Renvoie tous les ID des caractéristiques du dossier spécifié. Non disponible pour toutes les méthodes. |
| permissions | Renvoie une liste de segments basée sur l’autorisation spécifiée.  READ est par défaut. Les autorisations comprennent :<ul><li>`READ` : Informations de retour et de vue sur un segment.</li><li>`WRITE` : Permet `PUT` de mettre à jour un segment.</li><li>`CREATE` : Utilisez `POST` pour créer un segment.</li><li>`DELETE` : Suppression d’un segment. Nécessite l&#39;accès aux caractéristiques sous-jacentes, le cas échéant. Par exemple, vous aurez besoin de droits pour supprimer les caractéristiques qui appartiennent à un segment si vous souhaitez le supprimer.</li></ul><br>Spécifiez plusieurs autorisations avec des paires clé-valeur distinctes. Par exemple, pour renvoyer une liste de segments avec `READ` et `WRITE` des autorisations uniquement, transmettez `"permissions":"READ"`, `"permissions":"WRITE"` . |
| includePermissions | (Booléen) Définissez cette variable sur true pour renvoyer vos autorisations pour le segment. La valeur par défaut est false. |

### Remarque concernant les options de page

Lorsque les informations de page ne *sont pas* spécifiées, la requête renvoie des résultats simples [!DNL JSON] dans un tableau. Si des informations sur la page *sont* spécifiées, la liste renvoyée est encapsulée dans un [!DNL JSON] objet contenant des informations sur le résultat total et la page active. Votre exemple de requête utilisant les options de page peut ressembler à ceci :

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## URL des API {#api-urls}

[!DNL URLs] pour les demandes, les environnements d’évaluation et de production et les versions.

<!-- r_rest_urls.xml -->

## URL de demande {#request-urls}

Le tableau suivant liste les URL de requête utilisées pour transmettre des [!DNL API] requêtes, par méthode.

En fonction de la méthode d’authentification que vous utilisez, vous devez ajuster les URL de requête en fonction des tableaux ci-dessous.

### Demander des URL pour l’authentification JWT {#request-urls-jwt}

| [!DNL API] Méthodes | Demande [!DNL URL] |
|--- |--- |
| Modélisation algorithmique | `https://aam.adobe.io/v1/models/` |
| Source de données | `https://aam.adobe.io/v1/datasources/` |
| Signaux dérivés | `https://aam.adobe.io/v1/signals/derived/` |
| Destinations  | `https://aam.adobe.io/v1/destinations/` |
| Domaines | `https://aam.adobe.io/v1/partner-sites/` |
| Dossiers | Caractéristiques :  `https://aam.adobe.io/v1/folders/traits /`<br>Segments :  `https://aam.adobe.io/v1/folders/segments /` |
| Schéma | `https://aam.adobe.io/v1/schemas/` |
| Segments | `https://aam.adobe.io/v1/segments/` |
| Caractéristiques | `https://aam.adobe.io/v1/traits/` |
| Types de caractéristiques | `https://aam.adobe.io/v1/customer-trait-types` |
| Taxonomie | `https://aam.adobe.io/v1/taxonomies/0/` |

### URL de demande pour l’authentification OAuth (obsolète) {#request-urls-oauth}

| [!DNL API] Méthodes | Demande [!DNL URL] |
|--- |--- |
| Modélisation algorithmique | `https://api.demdex.com/v1/models/` |
| Source de données | `https://api.demdex.com/v1/datasources/` |
| Signaux dérivés | `https://api.demdex.com/v1/signals/derived/` |
| Destinations  | `https://api.demdex.com/v1/destinations/` |
| Domaines | `https://api.demdex.com/v1/partner-sites/` |
| Dossiers | Caractéristiques :  `https://api.demdex.com/v1/folders/traits /`<br>Segments :  `https://api.demdex.com/v1/folders/segments /` |
| Schéma | `https://api.demdex.com/v1/schemas/` |
| Segments | `https://api.demdex.com/v1/segments/` |
| Caractéristiques | `https://api.demdex.com/v1/traits/` |
| Types de caractéristiques | `https://api.demdex.com/v1/customer-trait-types` |
| Taxonomie | `https://api.demdex.com/v1/taxonomies/0/` |

## Environnements {#environments}

Les [!DNL Audience Manager] s [!DNL API]permettent d&#39;accéder à différents environnements de travail. Ces environnements vous aident à tester le code par rapport à des bases de données distinctes sans affecter les données de production en direct. Le tableau suivant liste les [!DNL API] environnements disponibles et les noms d’hôte de ressources correspondants.

Selon la méthode d’authentification que vous utilisez, vous devez ajuster les URL de votre environnement en fonction du tableau ci-dessous.

| Environnement | Nom d’hôte pour l’authentification JWT | Nom d’hôte pour l’authentification OAuth |
|---|---|---|
| **Production** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Bêta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |


>[!NOTE]
>
>L’environnement bêta d’Audience Manager est une version autonome à plus petite échelle de l’environnement de production. Toutes les données à tester doivent être entrées et collectées dans cet environnement.

## Versions {#versions}

De nouvelles versions de ces [!DNL API]logiciels sont publiées régulièrement. Une nouvelle version incrémente le numéro de [!DNL API] version. Le numéro de version est référencé dans l’URL de demande, comme `v<version number>` indiqué dans l’exemple suivant :

`https://<host>/v1/...`

## Définition des codes de réponse {#response-codes-defined}

`HTTP` les codes d’état et le texte de réponse renvoyés par le Gestionnaire d’Audiences [!UICONTROL REST API].

<!-- r_api_http_response_codes.xml -->

| ID de code de réponse | Texte de la réponse | Définition |
|---|---|---|
| 200 | OK | La demande a été traitée avec succès. Renverra le contenu ou les données attendus si nécessaire. |
| 201 | Créé | La ressource a été créée. Renvoie pour `PUT` et `POST` les requêtes. |
| 204 | Aucun contenu | La ressource a été supprimée. Le corps de la réponse sera vide. |
| 400 | Requête incorrecte | Le serveur n&#39;a pas compris la demande. Généralement en raison d’une syntaxe incorrecte. Vérifiez votre demande et réessayez. |
| 403 | Interdit | Vous n&#39;avez pas accès à la ressource. |
| 404 | introuvables | Impossible de trouver la ressource pour le chemin spécifié. |
| 409 | Conflit | Impossible de terminer la demande en raison d&#39;un conflit avec l&#39;état de la ressource. |
| 500 | Erreur serveur | Le serveur a rencontré une erreur inattendue qui l&#39;a empêchée de répondre à la demande. |

>[!MORELIKETHIS]
>
>* [Authentification JWT (Service Account)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [Authentification OAuth](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 simplifié](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

