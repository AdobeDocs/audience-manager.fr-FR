---
description: Informations sur les configurations requises générales, authentification, paramètres de requête facultatifs, URL de requête et autres références.
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: Prise en main des API REST
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 622664170f2a76039bcf2333bde43ce9e60b6af2
workflow-type: tm+mt
source-wordcount: '2563'
ht-degree: 1%

---

# Prise en main de [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Informations sur les conditions requises générales, authentification, paramètres de requête facultatifs, [!DNL URLs] de requête et autres références.

## Exigences et recommandations relatives aux API {#api-requirements-recommendations}

Notez ce qui suit lorsque vous utilisez le code de l’API [Audience Manager &#x200B;](https://bank.demdex.com/portal/swagger/index.html#/) :

* **Paramètres de requête :** tous les paramètres de requête sont requis, sauf indication contraire.
* **En-têtes de requête** : lors de l’utilisation de jetons [Adobe Developer](https://www.adobe.io/), vous devez fournir l’en-tête de `x-api-key`. Vous pouvez obtenir votre clé [!DNL API] en suivant les instructions de la page [&#x200B; Intégration de compte de service &#x200B;](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
* **[!DNL JSON]le type de contenu :** spécifiez `content-type: application/json` *et* `accept: application/json` dans votre code.
* **Demandes et réponses :** envoyez les demandes sous la forme d’un objet [!DNL JSON] correctement formaté. [!DNL Audience Manager] répond avec des données formatées [!DNL JSON]. Les réponses du serveur peuvent contenir les données demandées, un code d’état, ou les deux.
* **Accès :** votre consultant [!DNL Audience Manager] vous fournira un identifiant client et une clé qui vous permettront d’effectuer des demandes de [!DNL API].
* **Documentation et exemples de code :** le texte en *italique* représente une variable que vous fournissez ou transmettez lors de l’exécution ou de la réception de données [!DNL API]. Remplacez le texte *en italique* par votre propre code, vos propres paramètres ou d’autres informations requises.

## Authentification {#authentication}

Les [!DNL Audience Manager] [!DNL REST APIs] prennent en charge trois méthodes d’authentification.

* [!BADGE Recommandé]{type=positive} [Authentification de serveur à serveur OAuth](#oauth-adobe-developer) à l’aide de la console de développement [Adobe](https://www.adobe.io/). [!DNL Adobe Developer] est l’écosystème et la communauté de développeurs d’Adobe. Elle comprend des [API pour tous les produits Adobe](https://developer.adobe.com/apis/). Il s’agit de la méthode recommandée pour configurer et utiliser [!DNL Adobe] [!DNL APIs]. Pour en savoir plus sur l’[authentification de serveur à serveur OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/), consultez la documentation destinée aux développeurs et développeuses d’Adobe.
* [!BADGE Obsolète]{type=negative} [Authentification JWT (compte de service)](#jwt) à l’aide de la [console de développement Adobe](https://www.adobe.io/). [!DNL Adobe Developer] est l’écosystème et la communauté de développeurs d’Adobe. Elle comprend des [API pour tous les produits Adobe](https://developer.adobe.com/apis/).
* [!BADGE Obsolète]{type=negative} [authentification OAuth héritée](#oauth-deprecated). Bien que cette méthode soit obsolète, les clients disposant d’intégrations [!DNL OAuth] existantes peuvent continuer à l’utiliser.

>[!IMPORTANT]
>
>Selon votre méthode d’authentification, vous devez ajuster votre [!DNL URLs] de requête en conséquence. Voir la section [Environnements](#environments) pour plus d’informations sur les noms d’hôtes à utiliser.

## Authentification de serveur à serveur OAuth à l’aide d’Adobe Developer {#oauth-adobe-developer}

Cette section explique comment rassembler les informations d’identification requises pour authentifier les appels API Audience Manager, comme indiqué dans le diagramme de flux ci-dessous. Vous pouvez rassembler la plupart des informations d’identification requises dans la configuration unique initiale. Toutefois, le jeton d’accès doit être actualisé toutes les 24 heures.

![Diagramme de flux d’authentification Audience Manager.](/help/using/api/rest-api-main/assets/aam-authentication-flow.png)

### Présentation d’Adobe Developer {#developer-overview}

[!DNL Adobe Developer] est l’écosystème et la communauté de développeurs d’Adobe. Elle comprend des [API pour tous les produits Adobe](https://developer.adobe.com/apis).

Il s’agit de la méthode recommandée pour configurer et utiliser [!DNL Adobe] [!DNL APIs].

### Conditions préalables {#prerequisites-server-to-server}

Avant de pouvoir configurer l’authentification [!DNL OAuth Server-to-Server], vérifiez que vous avez accès au [Adobe Developer Console](https://developer.adobe.com/console/home) dans [Adobe Developer](https://developer.adobe.com/). Contactez l’administrateur ou l’administratrice de votre organisation pour les demandes d’accès.

### Authentification {#oauth}

Pour configurer l’authentification [!DNL OAuth Server-to-Server] à l’aide de [!DNL Adobe Developer], procédez comme suit :

1. Connectez-vous à [Adobe Developer Console](https://developer.adobe.com/console/home).
1. Suivez les étapes du guide d’implémentation des informations d’identification de serveur à serveur [OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/).
   * Au cours de [Étape 2 : ajouter une API à votre projet à l’aide de l’authentification du compte de service](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), choisissez l’option [!DNL Audience Manager] [!DNL API] .
1. Testez la connexion en effectuant votre premier appel [!DNL API] en fonction des instructions de l’[étape 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Pour configurer et utiliser le [!DNL Audience Manager] [!DNL REST APIs] de manière automatisée, vous pouvez faire pivoter les secrets clients par programmation. Consultez [la documentation destinée aux développeurs](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#rotating-client-secrets-programmatically) pour obtenir des instructions détaillées.

### Ajouter l’API Audience Manager à un projet {#add-aam-api-to-project}

Accédez à [Adobe Developer Console](https://www.adobe.com/go/devs_console_ui) et connectez-vous avec votre Adobe ID. Suivez ensuite les étapes décrites dans le tutoriel sur la [création d’un projet vide](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty/) dans la documentation de Adobe Developer Console.

Une fois que vous avez créé un projet, sélectionnez **[!UICONTROL Add API]** dans l’écran **[!UICONTROL Project Overview]**.

>[!TIP]
>
>Si vous disposez des privilèges d’accès pour plusieurs organisations, utilisez le sélecteur d’organisation dans le coin supérieur droit de l’interface pour vous assurer que vous vous trouvez dans l’organisation dont vous avez besoin.

Écran Developer Console ![avec l’option Ajouter une API mise en surbrillance.](/help/using/api/rest-api-main/assets/add-api.png)

L’écran **[!UICONTROL Add an API]** s’affiche. Sélectionnez l’icône de produit de Adobe Experience Cloud, puis choisissez **[!UICONTROL Audience Manager API]** avant de sélectionner **[!UICONTROL Next]**.

![Sélectionner l’API Audience Manager.](/help/using/api/rest-api-main/assets/audience-manager-api.png)

>[!TIP]
>
>Sélectionnez l’option **[!UICONTROL View docs]** pour accéder à la [documentation de référence de l’API Audience Manager dans une fenêtre de navigateur distincte](https://bank.demdex.com/portal/swagger/index.html#).

### Sélectionner le type d’authentification OAuth serveur à serveur {#select-oauth-server-to-server}

Sélectionnez ensuite le type d’authentification pour générer les jetons d’accès et accéder à l’API Audience Manager.

>[!IMPORTANT]
>
>Sélectionnez la méthode **[!UICONTROL OAuth Server-to-Server]** , car il s’agira de la seule méthode prise en charge à l’avenir. La méthode **[!UICONTROL Service Account (JWT)]** est obsolète. Bien que les intégrations utilisant la méthode d’authentification JWT continueront à fonctionner jusqu’au 1er janvier 2025, Adobe vous recommande vivement de migrer les intégrations existantes vers la nouvelle méthode OAuth de serveur à serveur avant cette date.

![Sélectionnez la méthode d’authentification OAuth.](/help/using/api/rest-api-main/assets/select-oauth-authentication-method.png)

### Sélection des profils de produit pour votre intégration {#select-product-profiles}

Dans l’écran **[!UICONTROL Configure API]**, sélectionnez les profils de produit souhaités. Le compte de service de votre intégration aura accès aux fonctionnalités granulaires par le biais des profils de produit sélectionnés ici.

![Sélectionnez les profils de produit pour votre intégration.](/help/using/api/rest-api-main/assets/select-product-profiles.png)

Sélectionnez **[!UICONTROL Save configured API]** lorsque vous êtes prêt(e).

### Collecter les informations d’identification {#gather-credentials}

Une fois que l’API a été ajoutée au projet, la page **[!UICONTROL Audience Manager API]** du projet affiche les informations d’identification suivantes, requises dans tous les appels aux API Audience Manager :

![Informations d’intégration après l’ajout d’une API dans Developer Console.](/help/using/api/rest-api-main/assets/api-integration-information.png)

* `{API_KEY}` ([!UICONTROL Client ID])
* `{ORG_ID}` ([!UICONTROL Organization ID])

## Générer un jeton d’accès {#generate-access-token}

L’étape suivante consiste à générer des informations d’identification `{ACCESS_TOKEN}` à utiliser dans les appels API d’Audience Manager. Contrairement aux valeurs de `{API_KEY}` et `{ORG_ID}`, un nouveau jeton doit être généré toutes les 24 heures pour continuer à utiliser les API d’Audience Manager. Sélectionnez **[!UICONTROL Generate access token]**, comme illustré ci-dessous.

![Afficher comment générer un jeton d’accès](/help/using/api/rest-api-main/assets/generate-acces-token.gif)

## Tester un appel API {#test-api-call}

Après avoir obtenu votre jeton du porteur d’authentification, effectuez un appel API pour tester que vous pouvez désormais accéder aux API Audience Manager.

1. Accédez à la [documentation de référence de l’API](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_).
2. Sélectionnez **[!UICONTROL Authorize]** et collez le jeton d’accès obtenu à l’étape [Générer un jeton d’accès](#generate-access-token).

   ![Autoriser les appels API](/help/using/api/rest-api-main/assets/authorize-api-calls.gif)

3. Effectuez un appel GET au point d’entrée de l’API `/datasources` pour récupérer une liste de toutes les sources de données disponibles globalement, comme indiqué dans la documentation de référence de l’API [&#128279;](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_). Sélectionnez **[!UICONTROL Try it out]**, puis **[!UICONTROL Execute]**, comme illustré ci-dessous.

   ![Effectuer des appels API](/help/using/api/rest-api-main/assets/perform-api-calls.gif)


>[!BEGINSHADEBOX]

>[!BEGINTABS]

>[!TAB requête API]

```shell
curl -X 'GET' \
  'https://api.demdex.com/v1/datasources/' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer your-access-token'
```


>[!TAB Réponse de l’API en cas d’utilisation du jeton porteur correct]


Lors de l’utilisation d’un jeton d’accès fonctionnel, le point d’entrée de l’API renvoie une réponse 200, ainsi qu’un corps de réponse qui inclut toutes les sources de données globales auxquelles votre organisation a accès.

```json
[
  {
    "pid": 1794,
    "name": "testdatasource1",
    "description": "Test data source",
    "status": "ACTIVE",
    "integrationCode": "test_ds1",
    "dataExportRestrictions": [],
    "updateTime": 1595340792000,
    "crUID": 0,
    "upUID": 15910,
    "linkNamespace": false,
    "type": "GENERAL",
    "subIdType": "CROSS_DEVICE_PERSON",
    "inboundS2S": true,
    "outboundS2S": true,
    "useAudienceManagerVisitorID": false,
    "allowDataSharing": true,
    "masterDataSourceIdProvider": true,
    "uniqueTraitIntegrationCodes": false,
    "uniqueSegmentIntegrationCodes": false,
    "marketingCloudVisitorIdVersion": 0,
    "idType": "CROSS_DEVICE",
    "samplingEndTime": 1596550392825,
    "allowDeviceGraphSharing": false,
    "supportsAuthenticatedProfile": true,
    "deviceGraph": false,
    "authenticatedProfileName": "testdatasource1",
    "deviceGraphName": "",
    "customNamespaceId": 29769,
    "customNamespaceCode": "silviu_ds1",
    "customerProfileDataRetention": 62208000,
    "samplingStartTime": 1595340792825,
    "dataSourceId": 29769,
    "containerIds": [],
    "samplingEnabled": false
  },
  {
    "pid": 1794,
    "name": "AAM Test Company Audiences",
    "description": "Automatically generated trait data source",
    "status": "ACTIVE",
    "integrationCode": "adobe-provided",
    "dataExportRestrictions": [
      "PII"
    ],

    [...]
```

>[!ENDTABS]

>[!ENDSHADEBOX]

## [!BADGE Obsolète]{type=negative} Authentification [!DNL JWT] ([!DNL Service Account]) à l’aide d’Adobe Developer {#jwt}

+++ Affichez des informations sur la méthode [!DNL JWT] ([!DNL Service Account]) obsolète d’obtention de jetons d’authentification.

### Présentation d’Adobe Developer {#adobeio}

[!DNL Adobe Developer] est l’écosystème et la communauté de développeurs d’Adobe. Elle comprend des [API pour tous les produits Adobe](https://www.adobe.io/apis.html).

Il s’agit de la méthode recommandée pour configurer et utiliser [!DNL Adobe] [!DNL APIs].

### Conditions préalables {#prerequisites}

Avant de pouvoir configurer l’authentification [!DNL JWT], vérifiez que vous avez accès au [Adobe Developer Console](https://console.adobe.io/) dans [Adobe Developer](https://www.adobe.io/). Contactez l’administrateur ou l’administratrice de votre organisation pour les demandes d’accès.

### Authentification {#auth}

Pour configurer l’authentification [!DNL JWT (Service Account)] à l’aide de [!DNL Adobe Developer], procédez comme suit :

1. Connectez-vous à [Adobe Developer Console](https://console.adobe.io/).
1. Suivez les étapes de la section [Connexion au compte de service](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * Au cours de [Étape 2 : ajouter une API à votre projet à l’aide de l’authentification du compte de service](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), choisissez l’option [!DNL Audience Manager] [!DNL API] .
1. Testez la connexion en effectuant votre premier appel [!DNL API] en fonction des instructions de l’[étape 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Pour configurer et utiliser le [!DNL Audience Manager] [!DNL REST APIs] de manière automatisée, vous pouvez générer le [!DNL JWT] par programmation. Consultez la section [Authentification JWT (compte de service)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) pour obtenir des instructions détaillées.

### Autorisations RBAC de compte technique

Si votre compte Audience Manager utilise le [contrôle d’accès en fonction du rôle](../../features/administration/administration-overview.md), vous devez créer un compte d’utilisateur technique Audience Manager et l’ajouter au groupe RBAC Audience Manager qui effectuera les appels API.

Pour créer un compte d’utilisateur technique et l’ajouter à un groupe RBAC, procédez comme suit :

1. Appelez-`GET` `https://aam.adobe.io/v1/users/self`. L’appel crée un compte d’utilisateur technique que vous pouvez voir dans le [!UICONTROL Admin Console], dans la page [!UICONTROL Users] .

   ![compte technique &#x200B;](assets/technical-account.png)

1. Connectez-vous à votre compte Audience Manager et [ajoutez le compte d’utilisateur technique](../../features/administration/administration-overview.md#create-group) au groupe d’utilisateurs qui effectuera les appels API.

+++

## [!BADGE Obsolète]{type=negative} Authentification [!DNL OAuth] (Obsolète) {#oauth-deprecated}

+++ Affichez des informations sur l’ancienne méthode d’authentification [!DNL OAuth] obsolète permettant d’obtenir des jetons d’authentification.

>[!WARNING]
> L’authentification et le renouvellement [!DNL Audience Manager] jeton [!UICONTROL REST API] via [!DNL OAuth 2.0] sont désormais obsolètes.
>
> Utilisez plutôt l’authentification [JWT (compte de service)](#jwt-service-account-authentication-jwt).

La [!DNL Audience Manager] [!UICONTROL REST API] suit les normes [!DNL OAuth 2.0] pour l’authentification et le renouvellement des jetons. Les sections ci-dessous décrivent comment vous authentifier et commencer à utiliser les [!DNL API].

### Créer un utilisateur [!DNL API] générique {#requirements}

Nous vous recommandons de créer un compte utilisateur technique distinct pour travailler avec les [!DNL Audience Manager] [!DNL API]. Il s’agit d’un compte générique qui n’est pas lié à un utilisateur spécifique de votre organisation ni associé à celui-ci. Ce type de compte utilisateur [!DNL API] permet d’accomplir deux choses :

* Identifiez le service qui appelle le [!DNL API] (par exemple, les appels de vos applications qui utilisent nos [!DNL API] ou d’autres outils qui font des demandes [!DNL API]).
* Assurer un accès ininterrompu aux [!DNL API]. Un compte lié à une personne spécifique peut être supprimé lorsqu’elle quitte votre entreprise. Cela vous empêchera d’utiliser le code [!DNL API] disponible. Un compte générique qui n&#39;est pas lié à un employé particulier vous aide à éviter ce problème.

À titre d’exemple ou de cas d’utilisation pour ce type de compte, supposons que vous souhaitiez modifier de nombreux segments à la fois avec les [outils de gestion en bloc](../../reference/bulk-management-tools/bulk-management-intro.md). Pour ce faire, votre compte utilisateur doit disposer d’un accès [!DNL API]. Au lieu d’ajouter des autorisations à un utilisateur spécifique, créez un compte utilisateur [!DNL API] non spécifique disposant des informations d’identification, de la clé et du secret appropriés pour effectuer des appels [!DNL API]. Cela s’avère également utile si vous développez vos propres applications qui utilisent les [!DNL Audience Manager] [!DNL API].

Contactez votre consultant [!DNL Audience Manager] pour configurer un compte utilisateur générique en [!DNL API] seule.

### Workflow d’authentification de mot de passe {#password-authentication-workflow}

L&#39;authentification par mot de passe sécurise l&#39;accès à nos [!DNL REST API]. Les étapes ci-dessous décrivent le processus d’authentification par mot de passe à partir d’un client [!DNL JSON] dans votre navigateur.

>[!TIP]
>
>Chiffrez les jetons d’accès et d’actualisation si vous les stockez dans une base de données.

#### Étape 1 : Demander l&#39;accès [!DNL API]

Contactez votre responsable des solutions partenaires. Ils vous fourniront un identifiant client et un secret [!DNL API]. L’identifiant et le secret vous authentifient auprès de l’[!DNL API].

Remarque : si vous souhaitez recevoir un jeton d’actualisation, indiquez-le lorsque vous demandez un accès [!DNL API].

#### Étape 2 : demander le jeton

Transmettez une demande de jeton avec votre client [!DNL JSON] préféré. Lorsque vous créez la requête :

* Utilisez une méthode `POST` pour appeler `https://api.demdex.com/oauth/token`.
* Convertissez votre identifiant client et votre secret en une chaîne codée en base-64. Séparez l’ID et le secret par deux points pendant le processus de conversion. Par exemple, les informations d’identification `testId : testSecret` converties en `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Transmettez le [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` et `Content-Type: application/x-www-form-urlencoded` . Par exemple, votre en-tête pourrait ressembler à ceci : <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Configurez le corps de la requête comme suit :
  <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Étape 3 : recevoir le jeton

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

La clé `expires_in` représente le nombre de secondes avant l’expiration du jeton d’accès. De bonnes pratiques recommandent d’utiliser des délais d’expiration courts pour limiter l’exposition si le jeton est jamais exposé.

### Jeton d’actualisation {#refresh-token}

Les jetons d’actualisation renouvellent [!DNL API] accès après l’expiration du jeton d’origine. Si demandé, la réponse [!DNL JSON] dans le workflow de mot de passe comprend un jeton d’actualisation. Si vous ne recevez pas de jeton d’actualisation, créez-en un via le processus d’authentification par mot de passe.

Vous pouvez également utiliser un jeton d’actualisation pour générer un nouveau jeton avant l’expiration du jeton d’accès existant.

Si votre jeton d’accès a expiré, vous recevez un `401 Status Code` et l’en-tête suivant dans la réponse :

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

Les étapes suivantes décrivent le workflow d’utilisation d’un jeton d’actualisation pour créer un jeton d’accès à partir d’un client [!DNL JSON] dans votre navigateur.

#### Étape 1 : demander le nouveau jeton

Transmettez une demande de jeton d’actualisation au client [!DNL JSON] de votre choix. Lorsque vous créez la requête :

* Utilisez une méthode `POST` pour appeler `https://api.demdex.com/oauth/token`.
* Convertissez votre identifiant client et votre secret en une chaîne codée en base-64. Séparez l’ID et le secret par deux points pendant le processus de conversion. Par exemple, les informations d’identification `testId : testSecret` converties en `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Transmettez les en-têtes HTTP `Authorization:Basic <base-64 clientID:clientSecret>` et `Content-Type: application/x-www-form-urlencoded`. Par exemple, votre en-tête pourrait ressembler à ceci : <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* Dans le corps de la requête, spécifiez le `grant_type:refresh_token` et transmettez le jeton d’actualisation que vous avez reçu dans votre demande d’accès précédente. La requête doit se présenter comme suit : <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Étape 2 : recevoir le nouveau jeton

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

Le [!DNL Audience Manager] [!UICONTROL REST API] prend en charge le code d’autorisation et l’authentification implicite. Pour utiliser ces méthodes d’accès, vos utilisateurs doivent se connecter à `https://api.demdex.com/oauth/authorize` pour obtenir des jetons d’accès et d’actualisation.

+++

## Effectuer des demandes de [!DNL API] authentifiées {#authenticated-api-requests}

Conditions requises pour appeler des méthodes [!DNL API] après avoir reçu un jeton d’authentification.

Pour effectuer des appels par rapport aux méthodes [!DNL API] disponibles :

* Dans l’en-tête `HTTP`, définissez `Authorization: Bearer <token>`.
* Lors de l’utilisation de l’authentification [JWT (Compte de service)](#jwt), vous devez fournir l’en-tête `x-api-key`, qui sera le même que votre `client_id`. Vous pouvez obtenir votre `client_id` à partir de la page [Intégration d’Adobe Developer](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
* Appelez la méthode de [!DNL API] requise.

## Paramètres de requête [!DNL API] facultatifs {#optional-api-query-parameters}

Définissez les paramètres facultatifs disponibles pour les méthodes qui renvoient toutes les propriétés d’un objet .

Vous pouvez utiliser ces paramètres facultatifs avec des méthodes [!DNL API] qui renvoient des propriétés *all* pour un objet . Définissez ces options dans la chaîne de requête lors de la transmission de cette requête au [!DNL API].

| Paramètre | Description |
|--- |--- |
| `page` | Renvoie les résultats par numéro de page. La numérotation commence à 0. |
| `pageSize` | Définit le nombre de résultats de réponse renvoyés par la requête (10 est le nombre par défaut). |
| `sortBy` | Trie et renvoie les résultats en fonction de la propriété [!DNL JSON] spécifiée. |
| `descending` | Trie et renvoie les résultats dans l’ordre décroissant. `ascending` est la valeur par défaut. |
| `search` | Renvoie les résultats en fonction de la chaîne spécifiée que vous souhaitez utiliser comme paramètre de recherche. Supposons, par exemple, que vous souhaitiez trouver des résultats pour tous les modèles qui contiennent le mot « Test » dans l’un des champs de valeur de cet élément. Votre exemple de requête pourrait ressembler à ceci :   `GET https://aam.adobe.io/v1/models/?search=Test`.  Vous pouvez effectuer une recherche sur n’importe quelle valeur renvoyée par une méthode « [!DNL get all] ». |
| `folderId` | Renvoie tous les identifiants des [!UICONTROL traits] dans le dossier spécifié. Non disponible pour toutes les méthodes. |
| `permissions` | Renvoie une liste de segments en fonction de l’autorisation spécifiée. `READ` est la valeur par défaut. Les autorisations incluent :<ul><li>`READ` : renvoie et affiche des informations sur un segment.</li><li>`WRITE` : utilisez `PUT` pour mettre à jour un segment.</li><li>`CREATE` : utilisez `POST` pour créer un segment.</li><li>`DELETE` : permet de supprimer un segment. Nécessite l’accès aux caractéristiques sous-jacentes, le cas échéant. Par exemple, vous aurez besoin de droits pour supprimer les caractéristiques appartenant à un segment si vous souhaitez le supprimer.</li></ul><br>Spécifiez plusieurs autorisations avec des paires clé-valeur distinctes. Par exemple, pour renvoyer une liste de segments avec des autorisations `READ` et `WRITE` uniquement, transmettez `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) Définissez sur `true` pour renvoyer vos autorisations pour le segment. La valeur par défaut est `false`. |

{style="table-layout:auto"}

### Remarque Sur Les Options De Page

Lorsque les informations de page *ne sont pas* spécifiées, la requête renvoie des résultats [!DNL JSON] simples dans un tableau . Si les informations sur la page *est* sont spécifiées, la liste renvoyée est encapsulée dans un objet [!DNL JSON] qui contient des informations sur le résultat total et la page active. Votre exemple de requête à l’aide des options de page pourrait ressembler à ceci :

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] pour les demandes, les environnements d’évaluation et de production et les versions.

## [!DNL URLs] de la demande {#request-urls}

Le tableau suivant répertorie les [!DNL URLs] de requête utilisés pour transmettre des requêtes [!DNL API], par méthode.

Selon la méthode d’authentification que vous utilisez, vous devez ajuster le [!DNL URLs] de votre requête en fonction des tableaux ci-dessous.

### [!DNL URLs] de requête pour l’authentification [!BADGE &#x200B; OAuth &#x200B;]{type=positive}recommandée[!BADGE &#x200B; serveur à serveur et &#x200B;]{type=negative}obsolète[!DNL JWT] via Adobe Developer {#request-urls-jwt}

| Méthodes [!DNL API] | [!DNL URL] de la demande |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | Caractéristiques : `https://aam.adobe.io/v1/folders/traits /`<br>Segments : `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

{style="table-layout:auto"}

### [!DNL URLs] de demande pour l’authentification [!BADGE obsolète]{type=negative} héritée [!DNL OAuth] {#request-urls-oauth}

| Méthodes [!DNL API] | [!DNL URL] de la demande |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | Caractéristiques : `https://api.demdex.com/v1/folders/traits /`<br>Segments : `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

{style="table-layout:auto"}

## Environnements {#environments}

Les [!DNL Audience Manager] [!DNL API] permettent d’accéder à différents environnements de travail. Ces environnements vous permettent de tester le code sur des bases de données distinctes sans affecter les données de production actives. Le tableau suivant répertorie les environnements [!DNL API] disponibles et les noms d’hôtes de ressources correspondants.

Selon la méthode d’authentification que vous utilisez, vous devez ajuster les [!DNL URLs] de votre environnement conformément au tableau ci-dessous.

| Environnement | Nom d’hôte pour l’authentification [!DNL JWT] | Nom d’hôte pour l’authentification [!DNL OAuth] |
|---|---|---|
| **Production** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>L’environnement [!DNL Audience Manager] bêta est une version autonome à plus petite échelle de l’environnement de production. Toutes les données que vous souhaitez tester doivent être saisies et collectées dans cet environnement.

## Versions {#versions}

De nouvelles versions de ces [!DNL API] sont publiées régulièrement. Une nouvelle version incrémente le numéro de version [!DNL API]. Le numéro de version est référencé dans le [!DNL URL] de la requête, comme `v<version number>` dans l’exemple suivant :

`https://<host>/v1/...`

## Codes de réponse définis {#response-codes-defined}

`HTTP` les codes d’état et le texte de réponse renvoyés par le [!DNL Audience Manager] de [!UICONTROL REST API].

| ID du code de réponse | Texte de réponse | Définition |
|---|---|---|
| `200` | `OK` | La demande a été traitée. Renvoie le contenu ou les données attendus si nécessaire. |
| `201` | `Created` | La ressource a été créée. Renvoie pour les requêtes `PUT` et `POST`. |
| `204` | `No Content` | La ressource a été supprimée. Le corps de la réponse sera vide. |
| `400` | `Bad Request` | Le serveur n’a pas compris la demande. Généralement en raison d’une syntaxe incorrecte. Vérifiez votre requête et réessayez. |
| `403` | `Forbidden` | Vous n’avez pas accès à la ressource. |
| `404` | `Not Found` | La ressource est introuvable pour le chemin spécifié. |
| `409` | `Conflict` | La demande n’a pas pu aboutir en raison d’un conflit avec l’état de la ressource. |
| `500` | `Server Error` | Le serveur a rencontré une erreur inattendue qui l’a empêché de satisfaire la requête. |

>[!MORELIKETHIS]
>
>* [Authentification JWT (compte de service)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [&#x200B; Authentification OAuth &#x200B;](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [&#x200B; OAuth 2 simplifié &#x200B;](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)
