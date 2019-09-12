---
description: Audience Manager définit une limite maximale quant au nombre de caractéristiques, de segments, de destinations et de modèles algorithmiques que vous pouvez créer pour un compte. Les limites s'appliquent à ces éléments, qu'ils soient créés dans l'interface utilisateur ou par programmation via des méthodes API. Les limites d'utilisation permettent de protéger Audience Manager à partir des processus automatisés susceptibles de tenter de compromettre nos API ou l'interface utilisateur.
seo-description: Audience Manager définit une limite maximale quant au nombre de caractéristiques, de segments, de destinations et de modèles algorithmiques que vous pouvez créer pour un compte. Les limites s'appliquent à ces éléments, qu'ils soient créés dans l'interface utilisateur ou par programmation via des méthodes API. Les limites d'utilisation permettent de protéger Audience Manager à partir des processus automatisés susceptibles de tenter de compromettre nos API ou l'interface utilisateur.
seo-title: Limites d'utilisation
solution: Audience Manager
title: Limites d'utilisation
keywords: Mappage d'ID, mappages d'ID, mappages des cookies
uuid: 50 ca 4647-0 b 5 c -409 c -89 fa -4 fa 1799 b 3222
translation-type: tm+mt
source-git-commit: d893998e9e59dbce64195a167e267c6f7ed16f90

---


# Limites d'utilisation {#usage-limits}

Audience Manager définit une limite maximale quant au nombre de caractéristiques, de segments, de destinations et de modèles algorithmiques que vous pouvez créer pour un compte. Les limites s'appliquent à ces éléments, qu'ils soient créés dans l'interface utilisateur ou par programmation par le biais [!DNL API] de méthodes. Les limites d'utilisation permettent de protéger Audience Manager à partir des processus automatisés susceptibles de tenter de compromettre l'interface [!DNL API]utilisateur ou l'interface utilisateur.

## Limites de mappage des identifiants {#id-mapping-limits}

Le tableau ci-dessous répertorie les limites [de mappage](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) des identifiants pour les ID de périphérique. Lorsqu'un ID atteint l'une des limites ci-dessous, Audience Manager ajoute de nouveaux mappages d'ID basés sur une logique [!DNL FIFO] (première dans, premier affichage) en supprimant le mappage d'ID stocké le plus ancien et en ajoutant la nouvelle. Pour plus d'informations sur les ID pris en charge par Audience Manager, reportez-vous [à l'index des ID](../../reference/ids-in-aam.md) dans Audience Manager.

| Mappage d'ID | Limite maximale |
|-----------|-------------- |
| ID de publication de périphérique (DAID) avec ID de périphérique (identifiant de CRM) | 100 Identifiants de publicité de périphérique (DSI) à 1 ID de périphérique (identifiant CRM) |
| ID de la CRM (Cross-Device ID) vers DAID (Device Advertizing ID) | 10 Identifiants multiterminaux (ID de gestion de la relation client) sur 1 ID de publicité de périphérique (DAID) |
| ID de cookie/navigateur avec cookie/ID de navigateur | 1 000 identifiants de cookie/navigateur à 1 cookie/ID de navigateur |

## Limites d'éléments {#item-limits}

Les tableaux répertorient les limites actuelles par type d'élément. Vous ne pouvez pas créer de caractéristiques, de segments, de destinations ou [!UICONTROL Algorithmic Models] si vous atteignez une limite spécifique pour l'un de ces éléments. Si vous atteignez une limite, vous devez supprimer un ancien élément avant de pouvoir en créer un nouveau.

### Limites de caractéristiques

| Type de caractéristique | Limite maximale |
| -------------------------- | ------------------------------------- |
| Total caractéristiques | 100,000 |
| Qualification totale des caractéristiques | 150,000. Pour plus d'informations sur la qualification des caractéristiques, reportez-vous à la section Limite de qualification des caractéristiques dans [Référence des caractéristiques Caractéristiques](/help/using/features/traits/trait-qualification-reference.md#trait-qualification-limit). |
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
| Nombre maximum de caractéristiques exclues pour un modèle | 500. Voir [Exclusion de caractéristiques dans la modélisation algorithmique](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |

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

## Surveiller l'utilisation {#monitor-usage}

Vous pouvez afficher l'utilisation et les limites de votre compte en **[!UICONTROL Administration > Limits]** accédant à. L'accès requiert des autorisations d'administrateur.

![image limite d'utilisation](assets/usage-limits.png)

## Augmenter les limites d'éléments {#increase-item-limits}

Les limites par défaut indiquées ici devraient fournir une capacité suffisante pour répondre aux besoins de votre entreprise. Si votre organisation atteint régulièrement ces limites, contactez le représentant du compte pour discuter d'une augmentation.