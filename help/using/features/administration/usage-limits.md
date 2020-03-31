---
description: ' Gestionnaire de  de définit une limite maximale sur le nombre de caractéristiques, de segments, de destinations et de modèles algorithmiques que vous pouvez créer pour un compte. Les limites s’appliquent à ces éléments, qu’ils soient créés dans l’interface utilisateur ou par programmation au moyen de méthodes API. Les limites d’utilisation permettent de protéger  Gestionnaire  de des processus automatisés qui peuvent tenter de compromettre nos API ou notre interface utilisateur.'
seo-description: ' Gestionnaire de  de définit une limite maximale sur le nombre de caractéristiques, de segments, de destinations et de modèles algorithmiques que vous pouvez créer pour un compte. Les limites s’appliquent à ces éléments, qu’ils soient créés dans l’interface utilisateur ou par programmation au moyen de méthodes API. Les limites d’utilisation permettent de protéger  Gestionnaire  de des processus automatisés qui peuvent tenter de compromettre nos API ou notre interface utilisateur.'
seo-title: Limites d’utilisation
solution: Audience Manager
title: Limites d’utilisation
keywords: ID mapping, ID mappings, cookie mappings
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
translation-type: tm+mt
source-git-commit: f9f201824accdde18efafa0a8c389af48423534d

---


# Limites d’utilisation {#usage-limits}

 Gestionnaire de  de définit une limite maximale sur le nombre de caractéristiques, de segments, de destinations et de modèles algorithmiques que vous pouvez créer pour un compte. Les limites s’appliquent à ces éléments, qu’ils soient créés dans l’interface utilisateur ou par programmation au moyen de [!DNL API] méthodes. Les limites d’utilisation permettent de protéger   Manager des processus automatisés qui peuvent tenter de compromettre nos [!DNL API]applications ou notre interface utilisateur.

## Limites de mappage des identifiants {#id-mapping-limits}

Le tableau ci-dessous  les limites de mappage [des](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) ID pour les ID de périphérique. Une fois qu’un ID atteint l’une des limites ci-dessous,  Gestionnaire de  de ajoute de nouveaux mappages d’ID en fonction d’une logique [!DNL FIFO] (premier entré, premier sorti), en supprimant le plus ancien mappage d’ID stocké et en ajoutant le nouveau. Reportez-vous à [Index des ID](../../reference/ids-in-aam.md) dans  Gestionnaire de  de pour plus d’informations sur les ID pris en charge par le Gestionnaire de de .

| Mappage d’ID | Limite maximale |
|-----------|-------------- |
| ID de publicité de périphérique ([DAID](../../reference/ids-in-aam.md)) vers ID de périphérique croisé ([DPUUID](../../reference/ids-in-aam.md)) | 100 identifiants de publicité de périphérique ([DAID](../../reference/ids-in-aam.md)) à 1 ID de publicités inter-périphériques ([DPUUID](../../reference/ids-in-aam.md)) |
| ID inter-périphériques ([DPUUID](../../reference/ids-in-aam.md)) à ID de publicité de périphérique ([DAID](../../reference/ids-in-aam.md)) | 10 identifiants inter-périphériques ([DPUUID](../../reference/ids-in-aam.md)) à 1 identifiant publicitaire de périphérique ([DAID](../../reference/ids-in-aam.md)), par [DPID](../../reference/ids-in-aam.md) |
| Cookie/ID de navigateur vers cookie/ID de navigateur | 1 000 identifiants de cookie/navigateur à 1 cookie/ID de navigateur |

## Limites d’éléments {#item-limits}

Les tableaux  les limites actuelles par type d’élément. Vous ne pouvez pas créer de nouvelles caractéristiques, de nouveaux segments, de nouvelles destinations ou [!UICONTROL Algorithmic Models] si vous atteignez une limite spécifique pour l’un de ces éléments. Si vous atteignez une limite, vous devez supprimer un élément plus ancien avant de pouvoir en créer un nouveau.

### Limites de caractéristiques

| Type de caractéristiques | Limite maximale |
| -------------------------- | ------------------------------------- |
| Caractéristiques totales | 100,000 |
| Qualifications totales des caractéristiques | 150,000. Pour plus d&#39;informations sur la qualification des caractéristiques, voir Limite de qualification des caractéristiques dans le Guide de référence [sur les qualités des](/help/using/features/traits/trait-qualification-reference.md#trait-qualification-limit)caractéristiques. |
| Algorithmique | 50 |
| Basé sur les règles | 100,000 |
| En mode intégré | 100,000 |
| Caractéristiques des dossiers | 2,000 |

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
| Modèles algorithmiques taille maximale  taille  du | 25,000,000.  Notez que cette limite ne peut pas être augmentée. Vous pouvez réduire  tailles  de en sélectionnant moins de sources de données pour le modèle ou en sélectionnant une fenêtre de retour en arrière plus courte. |
| Nombre maximal de caractéristiques exclues pour un modèle | 500. Voir Exclusion de [caractéristiques dans la modélisation](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md)algorithmique. |

### Limites des dossiers

| Élément | Limite maximale |
| ------------- | ------------------ |
| Dossiers de caractéristiques | 2,000.  Votre structure de dossiers peut être profonde de 5 niveaux maximum. |

### Limites des signaux dérivés

| Élément | Limite maximale |
| --------------- | ------------- |
| Signaux dérivés | 50 000. |

### Limite des comptes d’utilisateurs 

| Élément | Limite maximale |
| ----------- | ------------- |
| Nombre maximal de comptes d’utilisateurs pour une  de | 1 000. |

## Utilisation du moniteur {#monitor-usage}

Vous pouvez voir l’utilisation et les limites de votre compte en accédant à **[!UICONTROL Administration > Limits]**. L’accès requiert des autorisations d’administrateur.

![image limite l&#39;utilisation](assets/usage-limits.png)

## Augmenter les limites d&#39;articles {#increase-item-limits}

Les limites par défaut répertoriées ici doivent fournir une capacité suffisante pour répondre aux besoins de votre entreprise. Si votre entreprise atteint systématiquement ces limites, contactez votre gestionnaire de compte pour discuter d’une augmentation.