---
description: Ce document décrit les types d’ID Audience Manager que vous pouvez utiliser dans les demandes de confidentialité de données.
seo-description: Ce document décrit les types d’ID Audience Manager que vous pouvez utiliser dans les demandes de confidentialité de données.
seo-title: Identifiants (ID) Audience Manager
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, AAM ID
title: Identifiants (ID) Audience Manager
translation-type: tm+mt
source-git-commit: 30352749e926d5730e9cc8beef3936c9ed6d2986

---


# Identifiants (ID) Audience Manager {#aam-ids}

Lorsque vous envoyez des demandes [de confidentialité de](data-privacy-requests.md) données à Adobe Audience Manager, vous devez inclure l’un des identifiants (ID) répertoriés ci-dessous. Vous trouverez plus d’informations sur les formats d’ID dans notre [Index des identifiants](../../reference/ids-in-aam.md)Audience Manager.

## ID utilisateur unique Adobe Audience Manager

* **Identifiant utilisateur**: `aam_uuid`
* **Définition**:ID utilisateur unique Adobe Audience Manager
* **ID** d’espace de noms : 0

**Exemple d’objet JSON**:

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

>[!NOTE]
>
>Vous pouvez également utiliser l’ [!DNL CORE] espace de noms.

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

## Adobe Experience Cloud ID

* **Identifiant utilisateur**: `mid`
* **Définition**: [!DNL Adobe Experience Cloud ID], anciennement appelé [!DNL Visitor ID] ou [!DNL Marketing Cloud ID]
* **ID** d’espace de noms : 4

>[!NOTE]
>
>Vous pouvez également utiliser l’ [!DNL ECID] espace de noms. Voir le deuxième [!DNL JSON] exemple.

**Exemple d’objet JSON**:

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

## Customer ID

**Identifiant utilisateur**: `cid`

**Définition**: ID de client, tel qu’un cookie que vous avez défini pour les visiteurs anonymes du site ou un [!DNL CRM] ID provenant d’un système hors ligne ou d’un nom d’utilisateur haché.

**ID** d’espace de noms : Spécifique au client. Recherchez-le dans votre instance Audience Manager.

**Exemple d’objet JSON**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"1234567",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-1234567"
      },
      {
        "namespace": "1234567",
        "type": "namespaceId",
        "value": "another-unique-user-id-for-datasource-1234567"
      },
      {
        "namespace":"54321",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-54321"
      }
    ]
  }
```

## ID de publicité mobile

**Identifiant utilisateur**: `d_cid`

**Définition**: Identifiants de publicité mobile.

**ID d’espace de noms**:

* [!DNL IDFA:] 20915
* [!DNL GAID:] 20914

Voir Sources [de données](../../features/global-data-sources.md) globales pour en savoir plus.

>[!IMPORTANT]
>
> Si vous utilisez Mobile [!DNL SDK], vous devez également envoyer l’ID Experience Cloud (`MID`) avec les ID de publicité mobile pour obtenir des réponses d’accès et de suppression complètes.

**Exemple d’objet JSON**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"20914",
        "type": "namespaceId",
        "value": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2"
      },
      {
        "namespace":"20915",
        "type": "namespaceId",
        "value": "AEBE52E7-03EE-455A-B3C4-E57283966239"
      }
    ]
  }
]
```

## Code d’intégration

**Identifiant utilisateur**: `d_cid_ic`

**Définition**: Code d’intégration de la source de données. Vous pouvez l’utiliser à la place de l’ID de source de données/de l’ID d’espace de noms dans la [!DNL API] requête [!DNL Adobe Experience Cloud Privacy Core Service].

**ID** d’espace de noms : Sans objet

**Exemple d’objet JSON**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "loyaltyCard",
        "type": "integrationCode",
        "value": "272023537812"
      },
      {
        "namespace":"offlineCampaign",
        "type": "integrationCode",
        "value": "9546673332"
      }
    ]
  }
]
```
