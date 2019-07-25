---
description: Le processus d'ingestion des données entrantes en temps réel utilise une série de requêtes HTTP provenant du navigateur d'un utilisateur pour transmettre des données à Audience Manager.
seo-description: Le processus d'ingestion des données entrantes en temps réel utilise une série de requêtes HTTP provenant du navigateur d'un utilisateur pour transmettre des données à Audience Manager.
seo-title: Ingestion de données entrantes en temps réel
solution: Audience Manager
title: Ingestion de données entrantes en temps réel
uuid: 43 cb 0 ebc -6 c 36-4391-bbfb -6 b 203 d 63 c 69 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Real-Time Inbound Data Ingestion {#real-time-inbound-data-ingestion}

The real-time inbound data ingestion process uses a series of `HTTP` requests from a user's browser to pass in data to Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

Les données entrantes doivent être formatées sous forme de paires clé-valeur appelées signaux. Typically, each signal is mapped to a segment created or managed through the user interface or [!DNL API].

## URL String Parameters and Syntax {#url-string-syntax}

The [!DNL URL] for an inbound data transfer should contain the variables described below. Remember to [create traits](../../../features/traits/create-onboarded-rule-based-traits.md) and a [folder structure](../../../features/traits/trait-storage.md#create-trait-storage-folder) in the [!DNL Audience Manager] UI before setting up real-time data transfers.

>[!NOTE]
>
>Remplacez le contenu en italique par les valeurs de paramètre réelles.

| Paramètre | Description |
|---|---|
| `<KEY>` | Identifiant unique dans une paire clé-valeur (par exemple sexe, couleur, prix). |
| `<VAL>` | Une variable appartenant au jeu de données défini par la clé (par exemple sexe = homme, couleur = vert, prix = 100) |

### Syntaxe d'URL

During a real-time inbound data ingestion process, a properly formatted [!DNL URL] string uses the following syntax:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
