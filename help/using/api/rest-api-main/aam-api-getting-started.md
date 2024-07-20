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
source-wordcount: '2558'
ht-degree: 1%

---

# Prise en main de [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Informations sur les exigences générales, authentification, paramètres de requête facultatifs, requête [!DNL URLs] et autres références.

## Configuration requise pour l’API et Recommendations {#api-requirements-recommendations}

Notez ce qui suit lorsque vous utilisez le code [API d&#39;Audience Manager](https://bank.demdex.com/portal/swagger/index.html#/) :

* **Paramètres de requête :** tous les paramètres de requête sont requis, sauf indication contraire.
* **En-têtes de demande** : lorsque vous utilisez des jetons [Adobe Developer](https://www.adobe.io/), vous devez fournir l’en-tête `x-api-key`. Vous pouvez obtenir votre clé [!DNL API] en suivant les instructions de la page [Intégration de compte de service](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) .
* **[!DNL JSON]type de contenu :** Spécifiez `content-type: application/json` *et* `accept: application/json` dans votre code.
* **Requêtes et réponses :** envoyez des requêtes sous la forme d’un objet [!DNL JSON] correctement formaté. [!DNL Audience Manager] répond avec [!DNL JSON] données formatées. Les réponses du serveur peuvent contenir les données demandées, un code d’état ou les deux.
* **Accès :** Votre consultant [!DNL Audience Manager] vous fournira un identifiant client et une clé qui vous permettront d’effectuer des requêtes [!DNL API].
* **Documentation et exemples de code :** Le texte en *italics* représente une variable que vous fournissez ou transmettez lors de la création ou de la réception de données [!DNL API]. Remplacez le texte *italicized* par votre propre code, paramètres ou d’autres informations requises.

## Authentification {#authentication}

[!DNL Audience Manager] [!DNL REST APIs] prend en charge trois méthodes d’authentification.

* [!BADGE Recommandé]{type=positive}[Authentification OAuth serveur à serveur](#oauth-adobe-developer) à l’aide de [Adobe console de développement](https://www.adobe.io/). [!DNL Adobe Developer] est l’écosystème et la communauté des développeurs de l’Adobe. Il comprend des [API pour tous les produits Adobe](https://developer.adobe.com/apis/). Il s’agit de la méthode recommandée pour configurer et utiliser [!DNL Adobe] [!DNL APIs]. Pour en savoir plus sur l’ [authentification OAuth serveur à serveur](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/) dans la documentation destinée aux développeurs d’Adobe.
* [!BADGE Obsolète]{type=negative}[Authentification JWT (compte de service)](#jwt) à l’aide de [la console de développement d’Adobe](https://www.adobe.io/). [!DNL Adobe Developer] est l’écosystème et la communauté des développeurs de l’Adobe. Il comprend des [API pour tous les produits Adobe](https://developer.adobe.com/apis/).
* [!BADGE Obsolète]{type=negative}[Authentification OAuth héritée](#oauth-deprecated). Bien que cette méthode soit obsolète, les clients avec des intégrations [!DNL OAuth] existantes peuvent continuer à utiliser cette méthode.

>[!IMPORTANT]
>
>Selon votre méthode d’authentification, vous devez ajuster votre requête [!DNL URLs] en conséquence. Voir la section [Environnements](#environments) pour plus d’informations sur les noms d’hôtes que vous devez utiliser.

## Authentification OAuth serveur à serveur à l’aide d’Adobe Developer {#oauth-adobe-developer}

Cette section explique comment rassembler les informations d’identification requises pour authentifier les appels API d’Audience Manager, comme indiqué dans l’organigramme ci-dessous. Vous pouvez rassembler la plupart des informations d’identification requises dans la configuration initiale unique. Le jeton d’accès doit toutefois être actualisé toutes les 24 heures.

![ Diagramme de flux d&#39;authentification des Audiences Manager.](/help/using/api/rest-api-main/assets/aam-authentication-flow.png)

### Présentation d’Adobe Developer {#developer-overview}

[!DNL Adobe Developer] est l’écosystème et la communauté des développeurs de l’Adobe. Il comprend des [API pour tous les produits Adobe](https://developer.adobe.com/apis).

Il s’agit de la méthode recommandée pour configurer et utiliser [!DNL Adobe] [!DNL APIs].

### Conditions préalables {#prerequisites-server-to-server}

Avant de pouvoir configurer l’authentification [!DNL OAuth Server-to-Server], assurez-vous d’avoir accès au [Adobe Developer Console](https://developer.adobe.com/console/home) dans [Adobe Developer](https://developer.adobe.com/). Contactez l’administrateur de votre entreprise pour les demandes d’accès.

### Authentification {#oauth}

Suivez les étapes ci-dessous pour configurer l’authentification [!DNL OAuth Server-to-Server] à l’aide de [!DNL Adobe Developer] :

1. Connectez-vous à [Adobe Developer Console](https://developer.adobe.com/console/home).
1. Suivez les étapes du [guide de mise en oeuvre des informations d’identification OAuth Server-to-Server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/).
   * Pendant [l’étape 2 : ajoutez une API à votre projet à l’aide de l’authentification du compte de service ](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), sélectionnez l’option [!DNL Audience Manager] [!DNL API] .
1. Essayez la connexion en effectuant votre premier appel [!DNL API] en fonction des instructions de l’ [étape 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Pour configurer et utiliser automatiquement [!DNL Audience Manager] [!DNL REST APIs], vous pouvez faire pivoter les secrets du client par programmation. Pour obtenir des instructions détaillées, reportez-vous à la [documentation destinée aux développeurs](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#rotating-client-secrets-programmatically).

### Ajout de l’API d’Audience Manager à un projet {#add-aam-api-to-project}

Accédez à [Adobe Developer Console](https://www.adobe.com/go/devs_console_ui) et connectez-vous avec votre Adobe ID. Suivez ensuite les étapes décrites dans le tutoriel sur la [création d’un projet vide](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty/) de la documentation Adobe Developer Console.

Une fois que vous avez créé un projet, sélectionnez **[!UICONTROL Add API]** sur l’écran **[!UICONTROL Project Overview]**.

>[!TIP]
>
>Si vous êtes configuré pour plusieurs organisations, utilisez le sélecteur d’organisations dans le coin supérieur droit de l’interface pour vous assurer que vous êtes dans l’organisation dont vous avez besoin.

![Écran Developer Console avec l&#39;option Ajouter une API mise en surbrillance.](/help/using/api/rest-api-main/assets/add-api.png)

L’écran **[!UICONTROL Add an API]** s’affiche. Sélectionnez l’icône de produit pour Adobe Experience Cloud, puis choisissez **[!UICONTROL Audience Manager API]** avant de sélectionner **[!UICONTROL Next]**.

![Sélectionnez l’API d’Audience Manager.](/help/using/api/rest-api-main/assets/audience-manager-api.png)

>[!TIP]
>
>Sélectionnez l’option **[!UICONTROL View docs]** pour accéder, dans une fenêtre de navigateur distincte, à la [documentation de référence de l’API d’Audience Manager](https://bank.demdex.com/portal/swagger/index.html#) complète.

### Sélectionnez le type d’authentification OAuth Server-to-Server {#select-oauth-server-to-server}

Sélectionnez ensuite le type d&#39;authentification pour générer les jetons d&#39;accès et accéder à l&#39;API d&#39;Audience Manager.

>[!IMPORTANT]
>
>Sélectionnez la méthode **[!UICONTROL OAuth Server-to-Server]** car il s’agira de la seule méthode prise en charge à l’avenir. La méthode **[!UICONTROL Service Account (JWT)]** est obsolète. Bien que les intégrations utilisant la méthode d’authentification JWT continueront à fonctionner jusqu’au 1er janvier 2025, Adobe recommande vivement de migrer les intégrations existantes vers la nouvelle méthode OAuth Server-to-Server avant cette date.

![Sélectionnez la méthode d&#39;authentification OAuth.](/help/using/api/rest-api-main/assets/select-oauth-authentication-method.png)

### Sélection des profils de produit pour votre intégration {#select-product-profiles}

Dans l’écran **[!UICONTROL Configure API]**, sélectionnez les profils de produit souhaités. Le compte de service de votre intégration aura accès à des fonctionnalités granulaires par le biais des profils de produits sélectionnés ici.

![Sélectionnez les profils de produit pour votre intégration.](/help/using/api/rest-api-main/assets/select-product-profiles.png)

Sélectionnez **[!UICONTROL Save configured API]** lorsque vous êtes prêt.

### Collecte des informations d’identification {#gather-credentials}

Une fois l’API ajoutée au projet, la page **[!UICONTROL Audience Manager API]** du projet affiche les informations d’identification suivantes, requises dans tous les appels aux API d’Audience Manager :

![ Informations d’intégration après l’ajout d’une API dans Developer Console.](/help/using/api/rest-api-main/assets/api-integration-information.png)

* `{API_KEY}` ([!UICONTROL Client ID])
* `{ORG_ID}` ([!UICONTROL Organization ID])

## Générer un jeton d’accès {#generate-access-token}

L’étape suivante consiste à générer des informations d’identification `{ACCESS_TOKEN}` à utiliser dans les appels API d’Audience Manager. Contrairement aux valeurs de `{API_KEY}` et `{ORG_ID}`, un nouveau jeton doit être généré toutes les 24 heures pour continuer à utiliser les API Audience Manager. Sélectionnez **[!UICONTROL Generate access token]**, comme illustré ci-dessous.

![Afficher comment générer un jeton d’accès](/help/using/api/rest-api-main/assets/generate-acces-token.gif)

## Test d’un appel API {#test-api-call}

Après avoir obtenu votre jeton porteur d’authentification, effectuez un appel API pour tester si vous pouvez désormais accéder aux API d’Audience Manager.

1. Accédez à la [documentation de référence sur les API](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_).
2. Sélectionnez **[!UICONTROL Authorize]** et collez le jeton d’accès que vous avez obtenu à l’étape [générer un jeton d’accès](#generate-access-token) .

   ![Autoriser les appels API](/help/using/api/rest-api-main/assets/authorize-api-calls.gif)

3. Effectuez un appel GET au point d’entrée de l’API `/datasources` pour récupérer une liste de toutes les sources de données disponibles globalement, comme indiqué dans la [documentation de référence de l’API](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_). Sélectionnez **[!UICONTROL Try it out]**, suivi de **[!UICONTROL Execute]**, comme illustré ci-dessous.

   ![ Effectuer des appels API](/help/using/api/rest-api-main/assets/perform-api-calls.gif)


>[!BEGINSHADEBOX]

>[!BEGINTABS]

>[!TAB Requête API]

```shell
curl -X 'GET' \
  'https://api.demdex.com/v1/datasources/' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer your-access-token'
```


>[!TAB Réponse de l’API en cas d’utilisation du jeton porteur correct]


Lors de l’utilisation d’un jeton d’accès fonctionnel, le point de terminaison de l’API renvoie une réponse 200, ainsi qu’un corps de réponse qui inclut toutes les sources de données globales auxquelles votre organisation a accès.

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

## [!BADGE Obsolète]{type=negative}[!DNL JWT] ([!DNL Service Account]) Authentification à l’aide d’Adobe Developer {#jwt}

+++ Affichez des informations sur la méthode obsolète [!DNL JWT] ([!DNL Service Account]) pour obtenir des jetons d’authentification.

### Présentation d’Adobe Developer {#adobeio}

[!DNL Adobe Developer] est l’écosystème et la communauté des développeurs de l’Adobe. Il comprend des [API pour tous les produits Adobe](https://www.adobe.io/apis.html).

Il s’agit de la méthode recommandée pour configurer et utiliser [!DNL Adobe] [!DNL APIs].

### Conditions préalables {#prerequisites}

Avant de pouvoir configurer l’authentification [!DNL JWT], assurez-vous d’avoir accès au [Adobe Developer Console](https://console.adobe.io/) dans [Adobe Developer](https://www.adobe.io/). Contactez l’administrateur de votre entreprise pour les demandes d’accès.

### Authentification {#auth}

Suivez les étapes ci-dessous pour configurer l’authentification [!DNL JWT (Service Account)] à l’aide de [!DNL Adobe Developer] :

1. Connectez-vous à [Adobe Developer Console](https://console.adobe.io/).
1. Suivez les étapes de la section [Connexion au compte de service](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * Pendant [l’étape 2 : ajoutez une API à votre projet à l’aide de l’authentification du compte de service ](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), sélectionnez l’option [!DNL Audience Manager] [!DNL API] .
1. Essayez la connexion en effectuant votre premier appel [!DNL API] en fonction des instructions de l’ [étape 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Pour configurer et utiliser automatiquement [!DNL Audience Manager] [!DNL REST APIs], vous pouvez générer le [!DNL JWT] par programmation. Voir [Authentification JWT (compte de service)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) pour obtenir des instructions détaillées.

### Autorisations RBAC du compte technique

Si votre compte d’Audience Manager utilise le [contrôle d’accès en fonction du rôle](../../features/administration/administration-overview.md), vous devez créer un compte d’utilisateur technique d’Audience Manager et l’ajouter au groupe RBAC d’Audience Manager qui effectuera les appels d’API.

Pour créer un compte d’utilisateur technique et l’ajouter à un groupe RBAC, procédez comme suit :

1. Effectuez un appel `GET` à `https://aam.adobe.io/v1/users/self`. L’appel crée un compte utilisateur technique que vous pouvez voir dans la page [!UICONTROL Admin Console], dans la page [!UICONTROL Users].

   ![compte technique](assets/technical-account.png)

1. Connectez-vous à votre compte d’Audience Manager et [ ajoutez le compte d’utilisateur technique ](../../features/administration/administration-overview.md#create-group) au groupe d’utilisateurs qui effectuera les appels API.

+++

## [!BADGE Obsolète]{type=negative}[!DNL OAuth] Authentification (obsolète) {#oauth-deprecated}

+++ Affichez des informations sur la méthode d’authentification [!DNL OAuth] héritée obsolète pour obtenir des jetons d’authentification.

>[!WARNING]
> L’authentification et le renouvellement des jetons [!DNL Audience Manager] [!UICONTROL REST API] via [!DNL OAuth 2.0] sont désormais obsolètes.
>
> Utilisez plutôt l’ [authentification JWT (compte de service)](#jwt-service-account-authentication-jwt) .

[!DNL Audience Manager] [!UICONTROL REST API] suit les [!DNL OAuth 2.0] standards pour l’authentification et le renouvellement des jetons. Les sections ci-dessous décrivent comment vous authentifier et commencer à utiliser les [!DNL API].

### Création d’un utilisateur générique [!DNL API] {#requirements}

Nous vous recommandons de créer un compte utilisateur technique distinct pour travailler avec les [!DNL Audience Manager] [!DNL API]. Il s’agit d’un compte générique qui n’est pas lié ou associé à un utilisateur spécifique de votre entreprise. Ce type de compte utilisateur [!DNL API] vous permet d’accomplir 2 tâches :

* Identifiez le service qui appelle le [!DNL API] (par exemple, les appels de vos applications qui utilisent nos [!DNL API] ou d&#39;autres outils qui effectuent des requêtes [!DNL API]).
* Accordez un accès ininterrompu aux [!DNL API]. Un compte lié à une personne spécifique peut être supprimé lorsqu’il quitte votre société. Cela vous empêchera de travailler avec le code [!DNL API] disponible. Un compte générique qui n’est pas lié à un employé spécifique vous permet d’éviter ce problème.

Par exemple, pour ce type de compte, supposons que vous souhaitiez modifier de nombreux segments à la fois avec les [outils de gestion en bloc](../../reference/bulk-management-tools/bulk-management-intro.md). Pour ce faire, votre compte utilisateur doit disposer d’un accès [!DNL API]. Au lieu d’ajouter des autorisations à un utilisateur spécifique, créez un compte utilisateur [!DNL API] non spécifique disposant des informations d’identification, de la clé et du secret appropriés pour effectuer des appels [!DNL API]. Ceci est également utile si vous développez vos propres applications qui utilisent les [!DNL Audience Manager] [!DNL API].

Contactez votre consultant [!DNL Audience Manager] pour configurer un compte utilisateur générique [!DNL API] uniquement.

### Processus d’authentification par mot de passe {#password-authentication-workflow}

L&#39;authentification par mot de passe sécurise l&#39;accès à notre [!DNL REST API]. Les étapes ci-dessous décrivent le processus d’authentification par mot de passe d’un client [!DNL JSON] dans votre navigateur.

>[!TIP]
>
>Chiffrez l’accès et actualisez les jetons si vous les stockez dans une base de données.

#### Étape 1 : Demander l’accès à [!DNL API]

Contactez votre responsable Partenaires en solutions . Ils vous fourniront un ID client [!DNL API] et un secret. L’identifiant et le secret vous authentifient dans le [!DNL API].

Remarque : Si vous souhaitez recevoir un jeton d’actualisation, indiquez-le lorsque vous demandez l’accès à [!DNL API].

#### Étape 2 : demander le jeton

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

Les jetons d’actualisation renouvellent l’accès à [!DNL API] après l’expiration du jeton d’origine. Si nécessaire, la réponse [!DNL JSON] du workflow de mot de passe inclut un jeton d’actualisation. Si vous ne recevez pas de jeton d’actualisation, créez-en un nouveau par le biais du processus d’authentification par mot de passe.

Vous pouvez également utiliser un jeton d’actualisation pour générer un nouveau jeton avant l’expiration du jeton d’accès existant.

Si votre jeton d’accès a expiré, vous recevez un `401 Status Code` et l’en-tête suivant dans la réponse :

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

Les étapes suivantes décrivent le processus d’utilisation d’un jeton d’actualisation pour créer un jeton d’accès à partir d’un client [!DNL JSON] dans votre navigateur.

#### Étape 1 : demander le nouveau jeton

Transmettez une requête de jeton d’actualisation avec votre client [!DNL JSON] préféré. Lorsque vous créez la requête :

* Utilisez une méthode `POST` pour appeler `https://api.demdex.com/oauth/token`.
* Convertissez votre ID client et votre secret client en chaîne codée en base 64. Séparez l’ID et le secret par deux points au cours du processus de conversion. Par exemple, les informations d’identification `testId : testSecret` sont converties en `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Transmettez les en-têtes HTTP `Authorization:Basic <base-64 clientID:clientSecret>` et `Content-Type: application/x-www-form-urlencoded`. Par exemple, votre en-tête peut ressembler à ceci : <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* Dans le corps de la requête, spécifiez le `grant_type:refresh_token` et transmettez le jeton d’actualisation que vous avez reçu dans votre demande d’accès précédente. La requête doit ressembler à ceci : <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Étape 2 : réception du nouveau jeton

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

+++

## Lancer des requêtes [!DNL API] authentifiées {#authenticated-api-requests}

Conditions requises pour appeler les méthodes [!DNL API] après réception d’un jeton d’authentification.

Pour effectuer des appels par rapport aux méthodes [!DNL API] disponibles :

* Dans l&#39;en-tête `HTTP`, définissez `Authorization: Bearer <token>`.
* Lors de l&#39;utilisation de l&#39;authentification [JWT (Service Account) Authentication](#jwt), vous devez fournir l&#39;en-tête `x-api-key`, qui sera identique à votre `client_id`. Vous pouvez obtenir votre `client_id` à partir de la page [intégration Adobe Developer](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
* Appelez la méthode [!DNL API] requise.

## Paramètres de requête facultatifs [!DNL API] {#optional-api-query-parameters}

Définissez les paramètres facultatifs disponibles pour les méthodes qui renvoient toutes les propriétés d’un objet.

Vous pouvez utiliser ces paramètres facultatifs avec des méthodes [!DNL API] qui renvoient *toutes* propriétés pour un objet. Définissez ces options dans la chaîne de requête lors de la transmission de cette requête à [!DNL API].

| Paramètre | Description |
|--- |--- |
| `page` | Renvoie les résultats par numéro de page. La numérotation commence à 0. |
| `pageSize` | Définit le nombre de résultats de réponse renvoyés par la requête (10 est la valeur par défaut). |
| `sortBy` | Trie et renvoie les résultats en fonction de la propriété [!DNL JSON] spécifiée. |
| `descending` | Trie et renvoie les résultats dans l’ordre décroissant. `ascending` est la valeur par défaut. |
| `search` | Renvoie des résultats en fonction de la chaîne spécifiée que vous souhaitez utiliser comme paramètre de recherche. Par exemple, supposons que vous souhaitiez trouver des résultats pour tous les modèles ayant le mot &quot;Test&quot; dans l’un des champs de valeur de cet élément. Votre exemple de requête peut ressembler à ceci :   `GET https://aam.adobe.io/v1/models/?search=Test`.  Vous pouvez effectuer une recherche sur n’importe quelle valeur renvoyée par une méthode &quot;[!DNL get all]&quot;. |
| `folderId` | Renvoie tous les identifiants de [!UICONTROL traits] dans le dossier spécifié. Non disponible pour toutes les méthodes. |
| `permissions` | Renvoie une liste de segments basée sur l’autorisation spécifiée. `READ` est la valeur par défaut. Les autorisations incluent :<ul><li>`READ` : renvoie et affiche des informations sur un segment.</li><li>`WRITE` : utilisez `PUT` pour mettre à jour un segment.</li><li>`CREATE` : utilisez `POST` pour créer un segment.</li><li>`DELETE` : supprimez un segment. Nécessite l’accès aux caractéristiques sous-jacentes, le cas échéant. Par exemple, vous aurez besoin de droits pour supprimer les caractéristiques qui appartiennent à un segment si vous souhaitez le supprimer.</li></ul><br> Spécifiez plusieurs autorisations avec des paires clé-valeur distinctes. Par exemple, pour renvoyer une liste de segments avec les autorisations `READ` et `WRITE` uniquement, transmettez `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) Définissez cette variable sur `true` pour renvoyer vos autorisations pour le segment. La valeur par défaut est `false`. |

{style="table-layout:auto"}

### Remarque À Propos Des Options De Page

Lorsque les informations sur la page *ne sont pas* spécifiées, la requête renvoie la chaîne plain [!DNL JSON] donne un tableau. Si les informations sur la page *sont* spécifiées, alors la liste renvoyée est encapsulée dans un objet [!DNL JSON] qui contient des informations sur le résultat total et la page active. Votre exemple de requête utilisant les options de page peut ressembler à ceci :

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] pour les demandes, les environnements d’évaluation et de production, ainsi que les versions.

## Requête [!DNL URLs] {#request-urls}

Le tableau suivant répertorie la requête [!DNL URLs] utilisée pour transmettre des requêtes [!DNL API], par méthode.

Selon la méthode d’authentification que vous utilisez, vous devez ajuster votre requête [!DNL URLs] en fonction des tableaux ci-dessous.

### Demande [!DNL URLs] pour le [!BADGE recommandé]{type=positive}[!BADGE Obsolète]{type=negative}[!DNL JWT] Authentification via Adobe Developer {#request-urls-jwt}

| [!DNL API] Méthodes | Requête [!DNL URL] |
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

### Demande [!DNL URLs] pour le [!BADGE obsolète]{type=negative}[!DNL OAuth] Authentication {#request-urls-oauth}

| [!DNL API] Méthodes | Requête [!DNL URL] |
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

Les [!DNL Audience Manager] [!DNL API] permettent d&#39;accéder à différents environnements de travail. Ces environnements vous aident à tester le code par rapport à des bases de données distinctes sans affecter les données de production en direct. Le tableau suivant répertorie les environnements [!DNL API] disponibles et les noms d’hôtes de ressources correspondants.

Selon la méthode d’authentification que vous utilisez, vous devez ajuster votre environnement [!DNL URLs] en fonction du tableau ci-dessous.

| Environnement | Nom d’hôte pour l’authentification [!DNL JWT] | Nom d’hôte pour l’authentification [!DNL OAuth] |
|---|---|---|
| **Production** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>L’environnement bêta [!DNL Audience Manager] est une version autonome à plus petite échelle de l’environnement de production. Toutes les données que vous souhaitez tester doivent être entrées et collectées dans cet environnement.

## Versions {#versions}

De nouvelles versions de ces [!DNL API] sont publiées régulièrement. Une nouvelle version incrémente le numéro de version [!DNL API]. Le numéro de version est référencé dans la requête [!DNL URL] sous la forme `v<version number>`, comme illustré dans l’exemple suivant :

`https://<host>/v1/...`

## Codes de réponse définis {#response-codes-defined}

`HTTP` codes d’état et texte de réponse renvoyés par [!DNL Audience Manager] [!UICONTROL REST API].

| Identifiant de code de réponse | Texte de la réponse | Définition |
|---|---|---|
| `200` | `OK` | La requête a été traitée avec succès. Renvoie le contenu ou les données attendus, le cas échéant. |
| `201` | `Created` | La ressource a été créée. Renvoie pour les requêtes `PUT` et `POST`. |
| `204` | `No Content` | La ressource a été supprimée. Le corps de la réponse sera vide. |
| `400` | `Bad Request` | Le serveur n’a pas compris la requête. En raison d’une syntaxe incorrecte. Vérifiez votre requête, puis réessayez. |
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
