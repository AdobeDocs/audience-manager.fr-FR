---
description: Informations sur les exigences générales, l’authentification, les paramètres facultatifs de , les URL de requête et d’autres références.
seo-description: Informations sur les exigences générales, l’authentification, les paramètres facultatifs de , les URL de requête et d’autres références.
seo-title: Prise en main des API REST
solution: Audience Manager
title: Prise en main des API REST
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
translation-type: tm+mt
source-git-commit: af43becaf841909174fad097f4d4d5040c279b47

---


# Prise en main des API REST {#getting-started-with-rest-apis}

Informations sur les exigences générales, l’authentification, les paramètres facultatifs de , les URL de requête et d’autres références.

<!-- c_rest_api_overview.xml -->

## Configuration requise et recommandations pour l’API {#api-requirements-recommendations}

Les choses que vous devez faire et que vous devez faire lorsque vous travaillez avec les directeurs de   [!DNL API]s.

<!-- aam-api-requirements.xml -->

Tenez compte des points suivants lorsque vous travaillez avec [code API](https://bank.demdex.com/portal/swagger/index.html#/) Gestionnaire de  de :

* **Paramètres de requête :** Tous les paramètres de requête sont obligatoires, sauf indication contraire.
* **[!DNL JSON]type de contenu :**Spécifiez`content-type: application/json`et **`accept: application/json`dans votre code.

* **Demandes et réponses :** Envoyez des requêtes sous la forme d’un [!DNL JSON] objet correctement formaté. [!DNL Audience Manager] répond par des données [!DNL JSON] formatées. Les réponses du serveur peuvent contenir des données demandées, un code d’état ou les deux.

* **Accès :** Votre [!DNL Audience Manager] consultant vous fournira un ID de client et une clé qui vous permettront de faire [!DNL API] des demandes.

* **Documentation et exemples de code :** Le texte en *italique* représente une variable que vous fournissez ou transmettez lors de la création ou de la réception de [!DNL API] données. Remplacez *le texte en italique* par votre propre code, paramètres ou autres informations requises.

## Recommandations : Création d’un utilisateur API générique {#requirements}

Nous vous recommandons de créer un compte d’utilisateur technique distinct pour travailler avec les directeurs de  de [!DNL API]. Il s’agit d’un compte générique qui n’est pas associé à un utilisateur spécifique de votre entreprise ou qui n’est pas lui-même associé. Ce type de compte [!DNL API] utilisateur vous permet d’accomplir deux tâches :

* Identifiez le service qui appelle le [!DNL API] (par exemple, les appels de vos applications qui utilisent nos [!DNL API]applications ou d’autres outils qui effectuent [!DNL API] des requêtes).
* Fournir un accès ininterrompu aux [!DNL API]s. Un compte lié à une personne spécifique peut être supprimé lorsqu’il quitte votre. Cela vous empêchera de travailler avec le [!DNL API] code disponible. Un compte générique qui n’est pas lié à un employé en particulier permet d’éviter ce problème.

À titre d’exemple ou de cas d’utilisation pour ce type de compte, supposons que vous souhaitiez modifier un grand nombre de segments à la fois avec les outils [de gestion en](../../reference/bulk-management-tools/bulk-management-intro.md)masse. Eh bien, pour ce faire, votre compte utilisateur a besoin d&#39; [!DNL API] accès. Plutôt que d’ajouter des autorisations à un utilisateur spécifique, créez un compte utilisateur non spécifique [!DNL API] doté des informations d’identification, de la clé et du secret appropriés pour effectuer [!DNL API] des appels. Cela s’avère également utile si vous développez vos propres applications qui utilisent les   Manager [!DNL API]s.

Contactez votre consultant   Manager pour configurer un compte utilisateur générique [!DNL API]uniquement.

## OAuth Authentication {#oauth}

 Gestionnaire de  de applique les [!UICONTROL REST API] [!DNL OAuth 2.0] normes d’authentification et de renouvellement des jetons. Les sections ci-dessous décrivent comment vous authentifier et  utiliser les [!DNL API]s.

## Processus d’authentification par mot de passe {#password-authentication-workflow}

<!-- oath-authentication.xml -->

L&#39;authentification par mot de passe sécurise l&#39;accès à notre [!DNL REST API]site. Les étapes ci-dessous décrivent le processus d’authentification par mot de passe d’un [!DNL JSON] client dans votre navigateur.

>[!TIP]
>
>Chiffrez l’accès et actualisez les jetons si vous les stockez dans une base de données.

### Étape 1 : Demande d’accès à l’API

Contactez votre gestionnaire de solutions partenaires. Ils vous fourniront un ID [!DNL API] client et un secret. L&#39;ID et le secret vous authentifient auprès du [!DNL API].

Remarque : Si vous souhaitez recevoir un jeton d’actualisation, indiquez-le lorsque vous demandez l’ [!DNL API] accès.

### Étape 2 : Demander le jeton

Transmettez une demande de jeton à votre [!DNL JSON] client préféré. Lorsque vous créez la requête :

* Utilisez une `POST` méthode pour appeler `https://api.demdex.com/oauth/token`.
* Convertissez votre ID client et votre secret en chaîne codée en base 64. Séparez l’ID et le secret par deux-points pendant le processus de conversion. Par exemple, les informations d’identification `testId : testSecret` sont converties en `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Transmettez les [!DNL HTTP] en-têtes `Authorization:Basic <base-64 clientID:clientSecret>` et `Content-Type: application/x-www-form-urlencoded` . Par exemple, votre en-tête peut ressembler à ceci : <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Configurez l’organisme de requête comme suit :
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

### Étape 3 : Recevoir le jeton

La [!DNL JSON] réponse contient votre  de. La réponse doit se présenter comme suit :

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

La `expires_in` clé représente le nombre de secondes jusqu’à l’expiration du. Il est recommandé d’utiliser de courts délais d’expiration pour limiter l’exposition si le jeton est exposé.

## Actualiser le jeton {#refresh-token}

Les jetons d’actualisation renouvellent [!DNL API] l’accès après l’expiration du jeton d’origine. Si nécessaire, la réponse [!DNL JSON] dans le flux de travail des mots de passe inclut un jeton d’actualisation. Si vous ne recevez pas de jeton d’actualisation, créez-en un nouveau au moyen du processus d’authentification par mot de passe.

Vous pouvez également utiliser un jeton d’actualisation pour générer un nouveau jeton avant l’expiration du existant.

Si votre  a expiré, vous recevez un en-tête `401 Status Code` et l’en-tête suivants dans la réponse :

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

Les étapes suivantes décrivent le processus d’utilisation d’un jeton d’actualisation pour créer un nouveau à partir d’un [!DNL JSON] client dans votre navigateur.

### Étape 1 : Demande du nouveau jeton

Transmettez une demande de jeton actualisé à votre [!DNL JSON] client préféré. Lorsque vous créez la requête :

* Utilisez une `POST` méthode pour appeler `https://api.demdex.com/oauth/token`.
* Convertissez votre ID client et votre secret en chaîne codée en base 64. Séparez l’ID et le secret par deux-points pendant le processus de conversion. Par exemple, les informations d’identification `testId : testSecret` sont converties en `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Transmettez les en-têtes HTTP `Authorization:Basic <base-64 clientID:clientSecret>` et `Content-Type: application/x-www-form-urlencoded`. Par exemple, votre en-tête peut ressembler à ceci : <br/> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/> `Content-Type: application/x-www-form-urlencoded`
* Dans le corps de la requête, spécifiez le jeton `grant_type:refresh_token` d’actualisation que vous avez reçu dans votre demande d’accès précédente, puis transmettez-le. La requête doit se présenter comme suit : <br/> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

### Étape 2 : Recevez le nouveau jeton

La [!DNL JSON] réponse contient votre nouveau  de. La réponse doit se présenter comme suit :

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

## Code d’autorisation et authentification implicite {#authentication-code-implicit}

 Gestionnaire de  de [!UICONTROL REST API] prend en charge le code d’autorisation et l’authentification implicite. Pour utiliser ces méthodes d’accès, vos utilisateurs doivent se connecter pour accéder `https://api.demdex.com/oauth/authorize` aux jetons et les actualiser.

## Demandes d’API authentifiées {#authenticated-api-requests}

Conditions requises pour appeler [!DNL API] des méthodes après réception d’un jeton d’authentification.

<!-- c_oauth_call_methods.xml -->

Pour lancer des appels par rapport aux [!DNL API] méthodes disponibles :

* Dans l’ `HTTP` en-tête, définissez `Authorization: Bearer <token>`.
* Appelez la [!DNL API] méthode requise.

## Paramètres de  d&#39;API facultatifs {#optional-api-query-parameters}

Définissez les paramètres facultatifs disponibles pour les méthodes qui renvoient toutes les propriétés d’un objet.

<!-- c_rest_api_optional.xml -->

Vous pouvez utiliser ces paramètres facultatifs avec [!DNL API] des méthodes qui renvoient *toutes les* propriétés d’un objet. Définissez ces options dans la chaîne de requête lors de la transmission de ce à la [!DNL API].

| Paramètre | Description |
|--- |--- |
| page | Renvoie les résultats par numéro de page. de numérotation à 0. |
| pageSize | Définit le nombre de résultats de réponse renvoyés par la requête (10 est la valeur par défaut). |
| sortBy | Trie et renvoie les résultats selon la [!DNL JSON] propriété spécifiée. |
| décroissant | Trie et renvoie les résultats dans l’ordre décroissant.  est la valeur par défaut. |
| rechercher | Renvoie les résultats en fonction de la chaîne spécifiée que vous souhaitez utiliser comme paramètre de recherche. Supposons, par exemple, que vous souhaitiez rechercher des résultats pour tous les modèles qui contiennent le mot &quot;Test&quot; dans l’un des champs de valeur de cet élément. Votre exemple de requête peut ressembler à ceci :   `GET https://api.demdex.com/v1/models/?search=Test`.  Vous pouvez rechercher n’importe quelle valeur renvoyée par une méthode &quot;get all&quot;. |
| folderId | Renvoie tous les ID des caractéristiques du dossier spécifié. Non disponible pour toutes les méthodes. |
| permissions | Renvoie un  de segments en fonction de l’autorisation spécifiée.  READ est la valeur par défaut. Les autorisations comprennent :<ul><li>`READ` : Renvoie et  des informations sur un segment.</li><li>`WRITE` : Utilisez `PUT` pour mettre à jour un segment.</li><li>`CREATE` : Utilisez `POST` pour créer un segment.</li><li>`DELETE` : Suppression d’un segment. Nécessite l’accès aux caractéristiques sous-jacentes, le cas échéant. Par exemple, vous aurez besoin de droits pour supprimer les caractéristiques qui appartiennent à un segment si vous souhaitez le supprimer.</li></ul><br>Spécifiez plusieurs autorisations avec des paires clé-valeur distinctes. Par exemple, pour renvoyer un  de segments avec `READ` et `WRITE` des autorisations uniquement, transmettez `"permissions":"READ"`, `"permissions":"WRITE"` . |
| includePermissions | (Booléen) Définissez cette variable sur true pour renvoyer vos autorisations pour le segment. La valeur par défaut est false. |

### Remarque À Propos Des Options De Page

Lorsque les informations de page ne *sont pas* spécifiées, la requête renvoie des résultats simples [!DNL JSON] dans un tableau. Si des informations sur la page *sont* spécifiées, le renvoyé est encapsulé dans un [!DNL JSON] objet contenant des informations sur le résultat total et la page active. L’exemple de requête utilisant les options de page peut ressembler à ceci :

```
GET https://api.demdex.com/v1/models/?page=1&pageSize=2&search=Test
```

## URL des API {#api-urls}

[!DNL URLs] pour les demandes, l’évaluation et la production  les  et les versions.

<!-- r_rest_urls.xml -->

## URL de requête {#request-urls}

Le tableau suivant  les URL de requête utilisées pour transmettre [!DNL API] des requêtes, par méthode.

| [!DNL API] Méthodes | Demande [!DNL URL] |
|--- |--- |
| Modélisation algorithmique | `https://api.demdex.com/v1/models/` |
| Source de données | `https://api.demdex.com/v1/datasources/` |
| Signaux dérivés | `https://api.demdex.com/v1/signals/derived/` |
| Destinations  | `https://api.demdex.com/v1/destinations/` |
| Domaines | `https://api.demdex.com/v1/partner-sites/` |
| Dossiers | Caractéristiques :  `https://api.demdex.com/v1/folders/traits /`<br>Segments :  `https://api.demdex.com/v1/folders/segments /` |
| Schema | `https://api.demdex.com/v1/schemas/` |
| Segments | `https://api.demdex.com/v1/segments/` |
| Caractéristiques | `https://api.demdex.com/v1/traits/` |
| Types de caractéristiques | `https://api.demdex.com/v1/customer-trait-types` |
| Taxonomie | `https://api.demdex.com/v1/taxonomies/0/` |

##  {#environments}

Les [!DNL Audience Manager] s [!DNL API]permettent d’accéder à différents  de  de travail. Ces   vous aident à tester le code par rapport à des bases de données distinctes sans affecter les données de production en direct. Le tableau ci-dessous  le  de l’disponible [!DNL API] ainsi que les noms d’hôtes de ressource correspondants.

| Environnement | Nom d’hôte |
|---|---|
| **Production** | `https://api.demdex.com/...` |
| **Bêta** | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>Le de   Manager bêta  est une version autonome à plus petite échelle dude production. Toutes les données que vous souhaitez tester doivent être saisies et collectées dans ce  .

## Versions {#versions}

De nouvelles versions de ces [!DNL API]logiciels sont publiées régulièrement. Une nouvelle version incrémente le numéro de [!DNL API] version. Le numéro de version est référencé dans l’URL de demande, comme `v<version number>` illustré dans l’exemple suivant :

`https://<host>/v1/...`

## Codes de réponse définis {#response-codes-defined}

`HTTP` les codes d’état et le texte de réponse renvoyés par le  Gestionnaire de  de [!UICONTROL REST API].

<!-- r_api_http_response_codes.xml -->

| ID de code de réponse | Texte de réponse | Définition |
|---|---|---|
| 200 | OK | La requête a bien été traitée. Renvoie le contenu ou les données attendus, le cas échéant. |
| 201 | Créé | La ressource a été créée. Renvoie pour `PUT` et `POST` les requêtes. |
| 204 | Aucun contenu | La ressource a été supprimée. Le corps de la réponse sera vide. |
| 400 | Requête incorrecte | Le serveur n’a pas compris la requête. Généralement en raison d’une syntaxe incorrecte. Vérifiez votre demande et réessayez. |
| 403 | Interdit | Vous n’avez pas accès à la ressource. |
| 404 | introuvables | Impossible de trouver la ressource pour le chemin spécifié. |
| 409 | Conflit | Impossible de terminer la demande en raison d&#39;un conflit avec l&#39;état de la ressource. |
| 500 | Erreur du serveur | Le serveur a rencontré une erreur inattendue qui l’empêchait de répondre à la demande. |

>[!MORELIKETHIS]
>
>* [Authentification OAuth](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 simplifié](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

