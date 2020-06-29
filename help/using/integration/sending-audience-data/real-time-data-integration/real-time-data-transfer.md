---
description: Le processus d’assimilation des données entrantes en temps réel utilise une série de requêtes HTTP du navigateur d’un utilisateur pour transmettre les données à l’Audience Manager.
seo-description: Le processus d’assimilation des données entrantes en temps réel utilise une série de requêtes HTTP du navigateur d’un utilisateur pour transmettre les données à l’Audience Manager.
seo-title: Ingestion des données entrantes en temps réel
solution: Audience Manager
title: Ingestion des données entrantes en temps réel
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 1%

---


# Ingestion des données entrantes en temps réel {#real-time-inbound-data-ingestion}

Le processus d’assimilation des données entrantes en temps réel utilise une série de `HTTP` requêtes du navigateur d’un utilisateur pour transmettre des données à l’Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

Les données entrantes doivent être formatées en tant que paires clé-valeur appelées signaux. En règle générale, chaque signal est mappé à un segment créé ou géré par le biais de l’interface utilisateur ou [!DNL API]de.

## Paramètres de chaîne d’URL et syntaxe {#url-string-syntax}

Le transfert [!DNL URL] de données entrant doit contenir les variables décrites ci-dessous. Pensez à [créer des caractéristiques](../../../features/traits/create-onboarded-rule-based-traits.md) et une structure [de](../../../features/traits/trait-storage.md#create-trait-storage-folder) dossiers dans l’ [!DNL Audience Manager] interface utilisateur avant de configurer des transferts de données en temps réel.

>[!NOTE]
>
>Remplacez le contenu en italique par les valeurs de paramètre réelles.

| Paramètre | Description |
|---|---|
| `<KEY>` | Identificateur unique dans une paire clé-valeur (par exemple, sexe, couleur, prix). |
| `<VAL>` | Variable qui appartient au jeu de données défini par la clé (par exemple, gender=male, color=green, price=100) |

### Syntaxe de l’URL

Lors d’un processus d’assimilation de données entrantes en temps réel, une [!DNL URL] chaîne correctement formatée utilise la syntaxe suivante :

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
