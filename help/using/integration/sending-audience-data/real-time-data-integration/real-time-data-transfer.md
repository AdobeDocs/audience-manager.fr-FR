---
description: Le processus d’ingestion de données entrantes en temps réel utilise une série de requêtes HTTP du navigateur d’un utilisateur pour transmettre des données à Audience Manager.
seo-description: The real-time inbound data ingestion process uses a series of HTTP requests from a user's browser to pass in data to Audience Manager.
seo-title: Real-Time Inbound Data Ingestion
solution: Audience Manager
title: Ingestion De Données Entrantes En Temps Réel
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
exl-id: d243c74c-3a29-4dbf-a4c7-43ea526a9d7b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 1%

---

# Ingestion De Données Entrantes En Temps Réel {#real-time-inbound-data-ingestion}

Le processus d’ingestion de données entrantes en temps réel utilise une série de requêtes `HTTP` du navigateur d’un utilisateur pour transmettre des données à Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

Les données entrantes doivent être formatées sous la forme de paires clé-valeur appelées signaux. En règle générale, chaque signal est mappé à un segment créé ou géré via l’interface utilisateur ou l’[!DNL API].

## Paramètres de chaîne d’URL et syntaxe {#url-string-syntax}

Le [!DNL URL] d’un transfert de données entrant doit contenir les variables décrites ci-dessous. N’oubliez pas de [créer des caractéristiques](../../../features/traits/create-onboarded-rule-based-traits.md) et une [structure de dossiers](../../../features/traits/trait-storage.md#create-trait-storage-folder) dans l’interface utilisateur de [!DNL Audience Manager] avant de configurer les transferts de données en temps réel.

>[!NOTE]
>
>Remplacez le contenu en italique par les valeurs des paramètres réels.

| Paramètre | Description |
|---|---|
| `<KEY>` | Identifiant unique dans une paire clé-valeur (par exemple, genre, couleur, prix). |
| `<VAL>` | Une variable qui appartient au jeu de données défini par la clé (par exemple, genre=masculin, couleur=vert, prix=100) |

### Syntaxe de l&#39;URL

Lors d&#39;un processus d&#39;ingestion de données entrantes en temps réel, une chaîne de [!DNL URL] correctement formatée utilise la syntaxe suivante :

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
