---
description: Audience Manager définit une limite maximale sur le nombre de caractéristiques, de segments, de destinations et de modèles algorithmiques que vous pouvez créer pour un compte. Les limites s’appliquent à ces éléments, qu’ils soient créés dans l’interface utilisateur ou par programmation au moyen de méthodes API. Les limites d’utilisation permettent de protéger Audience Manager des processus automatisés qui peuvent tenter de compromettre nos API ou notre interface utilisateur.
seo-description: Audience Manager définit une limite maximale sur le nombre de caractéristiques, de segments, de destinations et de modèles algorithmiques que vous pouvez créer pour un compte. Les limites s’appliquent à ces éléments, qu’ils soient créés dans l’interface utilisateur ou par programmation au moyen de méthodes API. Les limites d’utilisation permettent de protéger Audience Manager des processus automatisés qui peuvent tenter de compromettre nos API ou notre interface utilisateur.
seo-title: ' Limites d’utilisation'
solution: Audience Manager
title: ' Limites d’utilisation'
keywords: Mappage d’ID, mappage d’ID, mappage de cookies
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
translation-type: tm+mt
source-git-commit: d893998e9e59dbce64195a167e267c6f7ed16f90

---


#  Limites d’utilisation {#usage-limits}

Audience Manager définit une limite maximale sur le nombre de caractéristiques, de segments, de destinations et de modèles algorithmiques que vous pouvez créer pour un compte. Les limites s’appliquent à ces éléments, qu’ils soient créés dans l’interface utilisateur ou par programmation au moyen de [!DNL API] méthodes. Les limites d’utilisation permettent de protéger Audience Manager des processus automatisés qui peuvent tenter de compromettre nos [!DNL API]applications ou notre interface utilisateur.

## Limites de mappage des identifiants {#id-mapping-limits}

Le tableau ci-dessous répertorie les limites de mappage [des](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) ID pour les ID de périphérique. Une fois qu’un ID atteint l’une des limites ci-dessous, Audience Manager ajoute de nouveaux mappages d’ID en fonction d’une logique [!DNL FIFO] (premier entré, premier sorti), en supprimant le plus ancien mappage d’ID stocké et en ajoutant le nouveau. Pour plus d’informations sur les ID pris en charge par Audience Manager, voir [Index des ID](../../reference/ids-in-aam.md) dans Audience Manager.

| Mappage d’ID | Limite maximale |
|-----------|-------------- |
| ID de publicité de périphérique (DAID) vers ID de périphérique croisé (ID CRM) | 100 ID de publicité de périphérique (DAID) à 1 ID de publication sur plusieurs périphériques (ID CRM) |
| ID de cross-device (CRM ID) à ID de publicité de périphérique (DAID) | 10 ID de plusieurs périphériques (ID CRM) à 1 ID de publicité de périphérique (DAID) |
| Cookie/ID de navigateur vers cookie/ID de navigateur | 1 000 identifiants de cookie/navigateur à 1 cookie/ID de navigateur |

## Limites d’éléments {#item-limits}

Les tableaux répertorient les limites actuelles par type d’élément. Vous ne pouvez pas créer de nouvelles caractéristiques, de nouveaux segments, de nouvelles destinations ou [!UICONTROL Algorithmic Models] si vous atteignez une limite spécifique pour l’un de ces éléments. Si vous atteignez une limite, vous devez supprimer un élément plus ancien avant de pouvoir en créer un nouveau.

### Limites de caractéristiques

| Type de caractéristiques | Limite maximale |
| -------------------------- | ------------------------------------- |
| Caractéristiques totales | 100,000 |
| Qualifications totales des caractéristiques | 150,000. Pour plus d'informations sur la qualification des caractéristiques, voir Limite de qualification des caractéristiques dans le Guide de référence [sur les qualités des](/help/using/features/traits/trait-qualification-reference.md#trait-qualification-limit)caractéristiques. |
| Algorithmique | 50 |
| Basé sur les règles | 100,000 |
| En ligne | 100,000 |
|  Caractéristiques des dossiers | 2,000 |

### Limites de segments

| Type de segment | Limite maximale |
| -------------- | ------------- |
| Total des segments | 20,000 |

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
| Modèles algorithmiques taille maximale de l’audience | 25,000,000.  Notez que cette limite ne peut pas être augmentée. Vous pouvez réduire la taille de l’audience en sélectionnant moins de sources de données pour le modèle ou en sélectionnant une fenêtre de retour en arrière plus courte. |
| Nombre maximal de caractéristiques exclues pour un modèle | 500. Voir Exclusion de [caractéristiques dans la modélisation](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md)algorithmique. |

### Limites des dossiers

| Élément | Limite maximale |
| ------------- | ------------------ |
| Dossiers de caractéristiques | 2,000.  Votre structure de dossiers peut être profonde de 5 niveaux maximum. |

### Limites des signaux dérivés

| Élément | Limite maximale |
| --------------- | ------------- |
|  Signaux dérivés | 50 000. |

### Limite des comptes utilisateur de l’entreprise

| Élément | Limite maximale |
| ----------- | ------------- |
| Nombre maximal de comptes utilisateur pour une société | 1 000. |

## Utilisation du moniteur {#monitor-usage}

Vous pouvez voir l’utilisation et les limites de votre compte en accédant à **[!UICONTROL Administration > Limits]**. L’accès requiert des autorisations d’administrateur.

![image limite l'utilisation](assets/usage-limits.png)

## Augmenter les limites d'articles {#increase-item-limits}

Les limites par défaut répertoriées ici doivent fournir une capacité suffisante pour répondre aux besoins de votre entreprise. Si votre entreprise atteint systématiquement ces limites, contactez votre gestionnaire de compte pour discuter d’une augmentation.