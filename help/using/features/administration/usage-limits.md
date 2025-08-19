---
description: Audience Manager limite le nombre de caractéristiques, de segments, de destinations et de modèles algorithmiques que vous pouvez créer pour un compte. Des limites s’appliquent à ces éléments, qu’ils soient créés dans l’interface utilisateur ou par programmation via des méthodes API. Les limites d’utilisation protègent Audience Manager contre les processus automatisés qui peuvent tenter de compromettre nos API ou notre interface utilisateur.
seo-description: Audience Manager sets a maximum limit on the number of traits, segments, destinations, and algorithmic models that you can create for an account. Limits apply to these items whether created in the user interface or programmatically through API methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our APIs or user interface.
seo-title: Usage Limits
solution: Audience Manager
title: Limites d’utilisation
keywords: Mappage d’ID, mappages d’ID, mappages de cookies
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Usage and Billing
exl-id: 8d29e231-d369-44ad-8e89-e6a4c83175f2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 4%

---

# Limites d’utilisation {#usage-limits}

Audience Manager limite le nombre de caractéristiques, de segments, de destinations et de modèles algorithmiques que vous pouvez créer pour un compte. Des limites s’appliquent à ces éléments, qu’ils soient créés dans l’interface utilisateur ou par programmation via des méthodes [!DNL API]. Les limites d’utilisation protègent Audience Manager contre les processus automatisés qui peuvent tenter de compromettre nos [!DNL API] ou notre interface utilisateur.

## Limites de mappage des identifiants {#id-mapping-limits}

Le tableau ci-dessous répertorie les limites [mappage des identifiants](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) pour les identifiants d’appareil. Une fois qu’un ID atteint l’une des limites ci-dessous, Audience Manager ajoute de nouveaux mappages d’ID en fonction d’une logique FIFO (premier entré, premier sorti), en supprimant le mappage d’ID stocké le plus ancien et en ajoutant le nouveau. Pour plus d’informations sur les identifiants pris en charge par Audience Manager[ voir la section ](../../reference/ids-in-aam.md)Index des identifiants dans Audience Manager .

| Mappage d’ID | Limite Maximale |
|-----------|-------------- |
| Identifiant Advertising de l’appareil ([DAID](../../reference/ids-in-aam.md)) en identifiant sur plusieurs appareils ([DPUUID](../../reference/ids-in-aam.md)) | 100 identifiants Advertising d’appareil ([DAID](../../reference/ids-in-aam.md)) à 1 identifiant sur plusieurs appareils ([DPUUID](../../reference/ids-in-aam.md)) |
| Identifiant sur plusieurs appareils ([DPUUID](../../reference/ids-in-aam.md)) vers l’identifiant Advertising de l’appareil ([DAID](../../reference/ids-in-aam.md)) | 10 identifiants entre appareils ([DPUUID](../../reference/ids-in-aam.md)) à 1 identifiant Advertising d’appareil ([DAID](../../reference/ids-in-aam.md)), par [DPID](../../reference/ids-in-aam.md) |
| Cookie/ID de navigateur en cookie/ID de navigateur | 1 000 ID de cookie/navigateur pour 1 ID de cookie/navigateur |

## Limites d’élément {#item-limits}

Les tableaux répertorient les limites actuelles par type d’élément. Vous ne pouvez pas créer de caractéristiques, de segments, de destinations ou de [!UICONTROL Algorithmic Models] si vous atteignez une limite spécifique pour l’un de ces éléments. Si vous atteignez une limite, vous devez supprimer un élément plus ancien avant de pouvoir en créer un nouveau.

### Limites des caractéristiques

| Type de caractéristique | Limite Maximale |
| -------------------------- | ------------------------------------- |
| Total des caractéristiques | 100 000 |
| Total des qualifications de caractéristiques | 150 000. Pour plus d’informations sur la qualification des caractéristiques, voir Limite de qualification des caractéristiques dans [Référence des qualifications des caractéristiques](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit). |
| Algorithmique | 50 |
| Basé sur des règles | 100 000 |
| Intégré | 100 000 |
| Caractéristiques du dossier | 2 000 |

### Limites de segment

| Type de segment | Limite Maximale |
| -------------- | ------------- |
| Nombre total de segments | 20 000 |

### Limites de destination

| Type de destination | Limite Maximale |
| ------------------ | ------------- |
| Total des destinations | 1 000 |
| Cookie | 1 000 |
| URL | 1 000 |
| S2S | 100 |
| Adobe Analytics | 10 |

### Limites du modèle algorithmique

| Élément | Limite Maximale |
| -------- | ----- |
| [!UICONTROL Look-Alike Models] actifs | &#x200B;20. Audience Manager compte uniquement les modèles algorithmiques *actifs* par rapport à la limite. |
| [!UICONTROL Look-Alike Models] taille maximale d’audience | 25 000 000.  Notez que cette limite ne peut pas être augmentée. Vous pouvez réduire la taille de l’audience en sélectionnant moins de sources de données pour le modèle ou en sélectionnant un intervalle de recherche en amont plus court. |
| Nombre maximal de caractéristiques exclues pour un [!UICONTROL Look-Alike Model] | &#x200B;500. Voir [Exclusion de caractéristiques dans la modélisation algorithmique](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |
| [!UICONTROL Predictive Audiences Models] maximum | 10 |
| Nombre maximal de personnages de base pour [!UICONTROL Predictive Audiences Models] | 50 |

### Limites de dossiers

| Élément | Limite Maximale |
| ------------- | ------------------ |
| Dossiers de caractéristiques | &#x200B;2000.  La structure de vos dossiers peut comporter au maximum 5 niveaux. |

### Limites des signaux dérivés

| Élément | Limite Maximale |
| --------------- | ------------- |
| Signaux Dérivés | 50 000. |

### Limite des comptes d’utilisateurs de l’entreprise

| Élément | Limite Maximale |
| ----------- | ------------- |
| Nombre maximal de comptes utilisateur pour une entreprise | 1000. |

## Surveillance de l’utilisation {#monitor-usage}

Pour afficher l’utilisation et les limites de votre compte, accédez à **[!UICONTROL Administration > Limits]**. L’accès nécessite des autorisations d’administrateur.

![image des limites d’utilisation](assets/usage-limits.png)

## Augmenter les limites d&#39;article {#increase-item-limits}

Les limites par défaut répertoriées ici doivent fournir une capacité suffisante pour répondre aux besoins de votre entreprise. Si votre organisation atteint systématiquement ces limites, contactez votre représentant de compte pour discuter d’une augmentation.
