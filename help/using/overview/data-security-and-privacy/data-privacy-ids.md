---
description: Ce document couvre les types d’identifiants Audience Manager que vous pouvez utiliser dans les demandes de confidentialité des données.
seo-description: Ce document couvre les types d’identifiants Audience Manager que vous pouvez utiliser dans les demandes de confidentialité des données.
seo-title: Identifiants (ID) Audience Manager
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, AAM ID
title: Identifiants (ID) Audience Manager
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Identifiants (ID) Audience Manager {#aam-ids}

Lorsque vous soumettez des [demandes de confidentialité des données](data-privacy-requests.md) à Adobe Audience Manager, vous devez inclure l’un des identifiants répertoriés ci-dessous. Vous pouvez trouver plus d’informations sur les formats d’identifiant dans notre [Index des identifiants dans Audience Manager](../../reference/ids-in-aam.md).

## Identifiant utilisateur unique Adobe Audience Manager

* **Identifiant utilisateur** : `aam_uuid`
* **Définition** : identifiant utilisateur unique Adobe Audience Manager
* **Identifiant de l’espace de noms** : 0

**Exemple d’objet JSON** :

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
>Vous pouvez également utiliser l’espace de noms [!DNL CORE].

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

## Identifiant Adobe Experience Cloud

* **Identifiant utilisateur** : `mid`
* **Définition** : [!DNL Adobe Experience Cloud ID], précédemment connu sous le nom de [!DNL Visitor ID] ou de [!DNL Marketing Cloud ID]
* **Identifiant de l’espace de noms** : 4

>[!NOTE]
>
>Vous pouvez également utiliser l’espace de noms [!DNL ECID]. Voir le deuxième exemple [!DNL JSON].

**Exemple d’objet JSON** :

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

## Identifiant client

**Identifiant utilisateur** : `cid`

**Définition** : identifiant client, comme un cookie que vous avez défini pour les visiteurs anonymes du site ou un identifiant [!DNL CRM] depuis un système hors ligne ou un nom d’utilisateur haché.

**Identifiant d’espace de noms** : spécifique au client. Recherchez-le dans votre instance Audience Manager.

**Exemple d’objet JSON** :

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

## Identifiant de publicité mobile

**Identifiant utilisateur** : `d_cid`

**Définition** : identifiants de publicité mobile.

**Identifiant d’espace de noms** :

* [!DNL IDFA:] 20915
* [!DNL GAID:] 20914

Consultez les [sources de données globales](../../features/global-data-sources.md) pour en savoir plus.

>[!IMPORTANT]
>
> Si vous utilisez le [!DNL SDK] mobile, alors vous devriez également envoyer l’identifiant Experience Cloud (`MID`) ainsi que les identifiants publicitaires mobiles pour terminer les réponses Access et Delete.

**Exemple d’objet JSON** :

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

**Identifiant utilisateur** : `d_cid_ic`

**Définition** : un code d’intégration pour la source de données. Vous pouvez l’utiliser à la place de l’identifiant de la source de données ou de l’espace de noms dans la demande [!DNL API] vers [!DNL Adobe Experience Cloud Privacy Core Service].

**Identifiant d’espace de noms** : ne s’applique pas

**Exemple d’objet JSON** :

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
