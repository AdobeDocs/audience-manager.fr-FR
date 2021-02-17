---
description: L’Audience Manager définit une limite maximale sur le nombre de caractéristiques, de segments, de destinations et de modèles algorithmiques que vous pouvez créer pour un compte. Les limites s’appliquent à ces éléments, qu’ils soient créés dans l’interface utilisateur ou par programmation au moyen de méthodes API. Les limites d’utilisation permettent de protéger l’Audience Manager des processus automatisés qui peuvent tenter de compromettre nos API ou notre interface utilisateur.
seo-description: L’Audience Manager définit une limite maximale sur le nombre de caractéristiques, de segments, de destinations et de modèles algorithmiques que vous pouvez créer pour un compte. Les limites s’appliquent à ces éléments, qu’ils soient créés dans l’interface utilisateur ou par programmation au moyen de méthodes API. Les limites d’utilisation permettent de protéger l’Audience Manager des processus automatisés qui peuvent tenter de compromettre nos API ou notre interface utilisateur.
seo-title: Limites d’utilisation
solution: Audience Manager
title: Limites d’utilisation
keywords: Mappage des identifiants, mappages des identifiants, mappages des cookies
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Usage and Billing
translation-type: tm+mt
source-git-commit: fc13643681eebec17a95607482f2864e81b95820
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 6%

---


# Limites d’utilisation {#usage-limits}

L’Audience Manager définit une limite maximale sur le nombre de caractéristiques, de segments, de destinations et de modèles algorithmiques que vous pouvez créer pour un compte. Les limites s’appliquent à ces éléments, qu’ils soient créés dans l’interface utilisateur ou par programmation au moyen de méthodes [!DNL API]. Les limites d&#39;utilisation permettent de protéger l&#39;Audience Manager des processus automatisés qui peuvent tenter de compromettre nos [!DNL API]s ou notre interface utilisateur.

## Limites de mappage des identifiants {#id-mapping-limits}

Le tableau ci-dessous liste les limites de [mappage des identifiants](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) pour les ID de périphérique. Une fois qu’un ID atteint l’une des limites ci-dessous, l’Audience Manager ajoute de nouveaux mappages d’ID basés sur une logique FIFO (premier entré, premier sorti), en supprimant le plus ancien mappage d’ID stocké et en ajoutant le nouveau. Consultez [Index des identifiants](../../reference/ids-in-aam.md) en Audience Manager pour plus d&#39;informations sur les identifiants pris en charge par l&#39;Audience Manager.

| Mappage des identifiants | Limite maximale |
|-----------|-------------- |
| ID de publicité de périphérique ([DAID](../../reference/ids-in-aam.md)) à l’ID de périphérique croisé ([DPUUID](../../reference/ids-in-aam.md)) | 100 identifiants de publicité de périphérique ([DAID](../../reference/ids-in-aam.md)) à 1 identifiant de périphérique croisé ([DPUUID](../../reference/ids-in-aam.md)) |
| ID de plusieurs périphériques ([DPUUID](../../reference/ids-in-aam.md)) à ID de publicité de périphérique ([DAID](../../reference/ids-in-aam.md)) | 10 ID multipériphériques ([DPUUID](../../reference/ids-in-aam.md)) à 1 ID de publicité de périphérique ([DAID](../../reference/ids-in-aam.md)), par [DPID](../../reference/ids-in-aam.md) |
| Cookie/ID de navigateur pour le cookie/ID de navigateur | 1 000 identifiants de cookie/navigateur à 1 cookie/ID de navigateur |

## Limites d&#39;articles {#item-limits}

Les tableaux liste les limites actuelles par type d&#39;élément. Vous ne pouvez pas créer de nouvelles caractéristiques, de nouveaux segments, de nouvelles destinations ou [!UICONTROL Algorithmic Models] si vous atteignez une limite spécifique pour l’un de ces éléments. Si vous atteignez une limite, vous devez supprimer un élément plus ancien avant de pouvoir en créer un nouveau.

### Limites de caractéristiques

| Type de caractéristique | Limite maximale |
| -------------------------- | ------------------------------------- |
| Traits totaux | 100 000 |
| Qualifications totales des caractéristiques | 150 000. Pour plus d&#39;informations sur la qualification des caractéristiques, voir Limite de qualification des caractéristiques dans [Référence sur les qualifications des caractéristiques](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit). |
| Algorithmique | 50 |
| Basé sur des règles | 100 000 |
| En bord | 100 000 |
| Caractéristiques des dossiers | 2 000 |

### Limites de segments

| Type de segment | Limite maximale |
| -------------- | ------------- |
| Total de segments | 20 000 |

### Limites de destination

| Type de destination | Limite maximale |
| ------------------ | ------------- |
| Total des destinations | 1 000 |
| Cookie | 1 000 |
| URL | 1 000 |
| S2S | 100 |
| Adobe Analytics | 10 |

### Limites du modèle algorithmique

| Élément | Limite maximale |
| -------- | ----- |
| Actif [!UICONTROL Look-Alike Models] | 20. L&#39;Audience Manager ne compte que les *modèles algorithmiques principaux* par rapport à la limite. |
| [!UICONTROL Look-Alike Models] taille maximale d’audience | 25 000 000.  Notez que cette limite ne peut pas être augmentée. Vous pouvez réduire la taille des audiences en sélectionnant moins de sources de données pour le modèle ou en sélectionnant une fenêtre de recherche plus courte. |
| Nombre maximal de caractéristiques exclues pour un [!UICONTROL Look-Alike Model] | 500. Voir [Exclusion des caractéristiques dans la modélisation algorithmique](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |
| Naximum [!UICONTROL Predictive Audiences Models] | 10 |
| Nombre maximal de personnages de base pour [!UICONTROL Predictive Audiences Models] | 50 |

### Limites des dossiers

| Élément | Limite maximale |
| ------------- | ------------------ |
| Dossiers de caractéristiques | 2 000.  Votre structure de dossiers peut comporter jusqu&#39;à 5 niveaux de profondeur. |

### Limites des signaux dérivés

| Élément | Limite maximale |
| --------------- | ------------- |
| Signaux dérivés | 50 000. |

### Limite des comptes utilisateur de société

| Élément | Limite maximale |
| ----------- | ------------- |
| Nombre maximal de comptes utilisateur pour une société | 1 000. |

## Utilisation du moniteur {#monitor-usage}

Vous pouvez afficher l&#39;utilisation et les limites de votre compte en accédant à **[!UICONTROL Administration > Limits]**. Access nécessite des autorisations d&#39;administrateur.

![image des limites d&#39;utilisation](assets/usage-limits.png)

## Augmenter les limites d&#39;articles {#increase-item-limits}

Les limites par défaut répertoriées ici doivent fournir une capacité suffisante pour répondre aux besoins de votre entreprise. Si votre entreprise atteint systématiquement ces limites, contactez votre gestionnaire de compte pour discuter d’une augmentation.