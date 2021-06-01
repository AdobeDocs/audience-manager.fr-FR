---
description: Audience Manager définit une limite maximale sur le nombre de caractéristiques, de segments, de destinations et de modèles algorithmiques que vous pouvez créer pour un compte. Les limites s’appliquent à ces éléments, qu’ils soient créés dans l’interface utilisateur ou par programmation au moyen de méthodes API. Les limites d’utilisation permettent de protéger l’Audience Manager des processus automatisés qui peuvent tenter de compromettre nos API ou notre interface utilisateur.
seo-description: Audience Manager définit une limite maximale sur le nombre de caractéristiques, de segments, de destinations et de modèles algorithmiques que vous pouvez créer pour un compte. Les limites s’appliquent à ces éléments, qu’ils soient créés dans l’interface utilisateur ou par programmation au moyen de méthodes API. Les limites d’utilisation permettent de protéger l’Audience Manager des processus automatisés qui peuvent tenter de compromettre nos API ou notre interface utilisateur.
seo-title: Limites d’utilisation
solution: Audience Manager
title: Limites d’utilisation
keywords: Mappage des identifiants, mappages des identifiants, mappages de cookies
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Utilisation et facturation
exl-id: 8d29e231-d369-44ad-8e89-e6a4c83175f2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 6%

---

# Limites d’utilisation {#usage-limits}

Audience Manager définit une limite maximale sur le nombre de caractéristiques, de segments, de destinations et de modèles algorithmiques que vous pouvez créer pour un compte. Les limites s’appliquent à ces éléments, qu’ils soient créés dans l’interface utilisateur ou par programmation au moyen de méthodes [!DNL API]. Les limites d’utilisation permettent de protéger l’Audience Manager des processus automatisés qui peuvent tenter de compromettre nos [!DNL API]s ou notre interface utilisateur.

## Limites de mappage des identifiants {#id-mapping-limits}

Le tableau ci-dessous répertorie les limites [mappage des identifiants](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) pour les identifiants d’appareil. Une fois qu’un ID atteint l’une des limites ci-dessous, l’Audience Manager ajoute de nouveaux mappages d’ID en fonction d’une logique FIFO (premier entré, premier sorti), en supprimant le mappage d’ID stocké le plus ancien et en ajoutant le nouveau. Pour plus d’informations sur les ID pris en charge par l’Audience Manager, voir [Index des ID](../../reference/ids-in-aam.md) en Audience Manager.

| Mappage des identifiants | Limite maximale |
|-----------|-------------- |
| ID de publicité de l’appareil ([DAID](../../reference/ids-in-aam.md)) vers ID multi-appareils ([DPUUID](../../reference/ids-in-aam.md)) | 100 identifiants de publicité d’appareil ([DAID](../../reference/ids-in-aam.md)) à 1 identifiant multi-appareils ([DPUUID](../../reference/ids-in-aam.md)) |
| ID multi-appareils ([DPUUID](../../reference/ids-in-aam.md)) à ID de publicité de périphérique ([DAID](../../reference/ids-in-aam.md)) | 10 identifiants multi-appareils ([DPUUID](../../reference/ids-in-aam.md)) à 1 identifiant de publicité d’appareil ([DAID](../../reference/ids-in-aam.md)), pour chaque [DPID](../../reference/ids-in-aam.md) |
| ID de cookie/navigateur à l’ID de cookie/navigateur | 1 000 identifiants de cookie/navigateur à 1 identifiant de cookie/navigateur |

## Limites des éléments {#item-limits}

Les tableaux répertorient les limites actuelles par type d’élément. Vous ne pouvez pas créer de caractéristiques, de segments, de destinations ou [!UICONTROL Algorithmic Models] si vous atteignez une limite spécifique pour l’un de ces éléments. Si vous atteignez une limite, vous devez supprimer un élément plus ancien avant d’en créer un nouveau.

### Limites de caractéristiques

| Type de caractéristique | Limite maximale |
| -------------------------- | ------------------------------------- |
| Caractéristiques totales | 100 000 |
| Qualification totale des caractéristiques | 150 000. Pour plus d’informations sur la qualification des caractéristiques, voir Limite de qualification des caractéristiques dans [Référence de qualification des caractéristiques](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit). |
| Algorithmique | 50 |
| Basé sur des règles | 100 000 |
| Intégration | 100 000 |
| Caractéristiques du dossier | 2 000 |

### Limites de segment

| Type de segment | Limite maximale |
| -------------- | ------------- |
| Total des segments | 20 000 |

### Limites de destination

| Type de destination | Limite maximale |
| ------------------ | ------------- |
| Total des destinations | 1 000 |
| Cookie | 1 000 |
| URL | 1 000 |
| S2S | 100 |
| Adobe Analytics | 10 |

### Limites des modèles algorithmiques

| Élément | Limite maximale |
| -------- | ----- |
| Actif [!UICONTROL Look-Alike Models] | 20. L’Audience Manager ne comptabilise que les *modèles algorithmiques* principaux par rapport à la limite. |
| [!UICONTROL Look-Alike Models] taille maximale d&#39;audience | 25 000 000.  Notez que cette limite ne peut pas être augmentée. Vous pouvez réduire la taille des audiences en sélectionnant moins de sources de données pour le modèle ou en sélectionnant un intervalle de recherche en amont plus court. |
| Nombre maximal de caractéristiques exclues pour un [!UICONTROL Look-Alike Model] | 500. Voir [Exclusion des caractéristiques dans la modélisation algorithmique](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |
| Maximum [!UICONTROL Predictive Audiences Models] | 10 |
| Nombre maximal de personas de base pour [!UICONTROL Predictive Audiences Models] | 50 |

### Limites du dossier

| Élément | Limite maximale |
| ------------- | ------------------ |
| Dossiers de caractéristiques | 2 000.  La structure de dossiers peut comporter jusqu’à 5 niveaux de profondeur. |

### Limites des signaux dérivés

| Élément | Limite maximale |
| --------------- | ------------- |
| Signaux dérivés | 50 000. |

### Limite des comptes d’utilisateur de l’entreprise

| Élément | Limite maximale |
| ----------- | ------------- |
| Nombre maximum de comptes d’utilisateurs pour une entreprise | 1 000. |

## Utilisation du moniteur {#monitor-usage}

Vous pouvez afficher l’utilisation et les limites de votre compte en accédant à **[!UICONTROL Administration > Limits]**. L’accès nécessite des autorisations d’administrateur.

![image des limites d’utilisation](assets/usage-limits.png)

## Augmentation des limites d’éléments {#increase-item-limits}

Les limites par défaut répertoriées ici doivent fournir une capacité suffisante pour répondre aux besoins de votre entreprise. Si votre entreprise atteint systématiquement ces limites, contactez votre gestionnaire de compte pour discuter d’une augmentation.
