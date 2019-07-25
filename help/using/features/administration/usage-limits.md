---
description: Audience Manager définit une limite maximale quant au nombre de caractéristiques, de segments, de destinations et de modèles algorithmiques que vous pouvez créer pour un compte. Les limites s'appliquent à ces éléments, qu'ils soient créés dans l'interface utilisateur ou par programmation via des méthodes API. Les limites d'utilisation permettent de protéger Audience Manager à partir des processus automatisés susceptibles de tenter de compromettre nos API ou l'interface utilisateur.
seo-description: Audience Manager définit une limite maximale quant au nombre de caractéristiques, de segments, de destinations et de modèles algorithmiques que vous pouvez créer pour un compte. Les limites s'appliquent à ces éléments, qu'ils soient créés dans l'interface utilisateur ou par programmation via des méthodes API. Les limites d'utilisation permettent de protéger Audience Manager à partir des processus automatisés susceptibles de tenter de compromettre nos API ou l'interface utilisateur.
seo-title: Limites d'utilisation
solution: Audience Manager
title: Limites d'utilisation
topic: API DIL
uuid: 50 ca 4647-0 b 5 c -409 c -89 fa -4 fa 1799 b 3222
translation-type: tm+mt
source-git-commit: a9550d71bbc6adf939539df05cd38a9d22ef261b

---


# Usage Limits {#usage-limits}

Audience Manager définit une limite maximale quant au nombre de caractéristiques, de segments, de destinations et de modèles algorithmiques que vous pouvez créer pour un compte. Limits apply to these items whether created in the user interface or programmatically through [!DNL API] methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our [!DNL API]s or user interface.

## Limites de mappage des identifiants {#id-mapping-limits}

The table below lists the [ID mapping](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) limits for device IDs. Once an ID reaches any of the limits below, Audience Manager adds new ID mappings based on a [!DNL FIFO] (first in, first out) logic, by removing the oldest stored ID mapping, and adds the new one. Refer to [Index of IDs](../../reference/ids-in-aam.md) in Audience Manager for details on the IDs supported by Audience Manager.

| Mappage d'ID | Limite maximale |
|-----------|-------------- |
| ID de publication de périphérique (DAID) avec ID de périphérique (identifiant de CRM) | 100 Identifiants de publicité de périphérique (DSI) à 1 ID de périphérique (identifiant CRM) |
| ID de la CRM (Cross-Device ID) vers DAID (Device Advertizing ID) | 10 Identifiants multiterminaux (ID de gestion de la relation client) sur 1 ID de publicité de périphérique (DAID) |
| ID de cookie/navigateur avec cookie/ID de navigateur | 1 000 identifiants de cookie/navigateur à 1 cookie/ID de navigateur |

## Item Limits {#item-limits}

Les tableaux répertorient les limites actuelles par type d'élément. You cannot create new traits, segments, destinations, or [!UICONTROL Algorithmic Models] if you reach a specific limit for one of these items. Si vous atteignez une limite, vous devez supprimer un ancien élément avant de pouvoir en créer un nouveau.

### Limites de caractéristiques

| Type de caractéristique | Limite maximale |
| -------------------------- | ------------------------------------- |
| Total caractéristiques | 100,000 |
| Qualification totale des caractéristiques | 150,000. For more information on trait qualification, see Trait Qualification Limit in [Trait Qualifications Reference](/help/using/features/traits/trait-qualification-reference.md#trait-qualification-limit). |
| Algorithmique | 50 |
| Basé sur les règles | 100,000 |
| Intégré | 100,000 |
| Caractéristiques du dossier | 2,000 |

### Limites de segment

| Type de segment | Limite maximale |
| -------------- | ------------- |
| Nombre total de segments | 20,000 |

### Limites de destination

| Type de destination | Limite maximale |
| ------------------ | ------------- |
| Destinations totales | 1 000 |
| Cookie | 1 000 |
| URL | 1 000 |
| S2S | 100 |
| Adobe Analytics | 10 |

### Limites du modèle algorithmique

| Élément | Limite maximale |
| -------- | ----- |
| Modèles algorithmiques actifs | 20. Audience Manager only counts *active* algorithmic models against the limit. |
| Taille maximale de l'audience des modèles algorithmiques | 25,000,000.  Notez que cette limite ne peut pas être augmentée. Vous pouvez réduire les tailles d'audience en sélectionnant moins de sources de données pour le modèle ou en sélectionnant une fenêtre de recherche plus courte. |
| Nombre maximum de caractéristiques exclues pour un modèle | 500. See [Trait Exclusion in Algorithmic Modeling](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |

### Limites de dossier

| Élément | Limite maximale |
| ------------- | ------------------ |
| Dossiers de caractéristiques | 2,000.  La structure de dossiers peut être au maximum de 5 niveaux. |

### Limites des signaux dérivés

| Élément | Limite maximale |
| --------------- | ------------- |
| Signaux dérivés | 50 000. |

### Limite des comptes d'utilisateurs de la société

| Élément | Limite maximale |
| ----------- | ------------- |
| Nombre maximum de comptes d'utilisateurs pour une entreprise | 1 000. |

## Monitor Usage {#monitor-usage}

You can see usage and limits for your account by going to **[!UICONTROL Administration > Limits]**. L'accès requiert des autorisations d'administrateur.

![image limite d'utilisation](assets/usage-limits.png)

## Increase Item Limits {#increase-item-limits}

Les limites par défaut indiquées ici devraient fournir une capacité suffisante pour répondre aux besoins de votre entreprise. Si votre organisation atteint régulièrement ces limites, contactez le représentant du compte pour discuter d'une augmentation.