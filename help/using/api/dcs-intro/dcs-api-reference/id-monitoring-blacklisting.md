---
description: Le serveur de collecte de données contrôle les ID qu'il reçoit et répertorie les adresses qui sont envoyées à un taux anormalement élevé pendant une courte période.
keywords: id ; surveillance ; liste noire ; dcs
seo-description: Le serveur de collecte de données contrôle les ID qu'il reçoit et répertorie les adresses qui sont envoyées à un taux anormalement élevé pendant une courte période.
seo-title: Surveillance des identifiants et liste noire
solution: Audience Manager
title: Surveillance des identifiants et liste noire
uuid: 498 e 0316-cf 1 b -43 e 9-88 ba -338 ee 0 daf 225
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# Surveillance des identifiants et liste noire

[!UICONTROL DCS] Les moniteurs reçoivent les ID qu'ils reçoivent et répertorient ceux qui sont envoyés à un taux anormalement élevé sur une courte période.

## Aperçu

To protect the Audience Manager infrastructure against malicious activity, the [!UICONTROL DCS] uses an advanced algorithm to monitor the IDs it receives. These can be [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s), or [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). See [Index of IDs in Audience Manager](../../../reference/ids-in-aam.md) for detailed explanations of the IDs supported by Audience Manager.

The [!UICONTROL DCS] monitors the frequency at which it receives these IDs to detect potential malicious activity. When the [!UICONTROL DCS] detects an unusually large amount of [!UICONTROL DCS] requests for any given ID in a short amount of time, that ID is blacklisted.

## Codes d’erreur

You can identify blacklisted IDs by the error codes received from the [!UICONTROL DCS]. Les codes d'erreur que vous pouvez recevoir sont les suivants :

* 303 : ID de client bloqué ;
* 306 : ID de périphérique déclaré bloqué ;
* 307 : Opération de profil bloquée pour l'ID.

See [DCS Error Codes, Messages, and Examples](dcs-error-codes.md) for details on the error codes that you may receive.

## Liste noire

Les identifiants placés sur liste noire ne doivent pas être utilisés dans les futures requêtes, car ils génèrent des rapports de données incorrects. The [!UICONTROL DCS] does not support un-blacklisting of IDs.

## Impact sur la synchronisation des identifiants

[!UICONTROL DCS] Les appels peuvent inclure un ou plusieurs types d'ID. Les appels contenant un ID unique sont totalement ignorés si cet identifiant est placé sur liste noire et qu'aucune synchronisation des identifiants ne se produit dans ce cas.

When a multiple ID call also includes a blacklisted ID, the [!UICONTROL DCS] disregards the blacklisted ID and only uses the remaining, non-blacklisted IDs for synchronization.

## Causes et correctifs des listes noires d'ID

La cause la plus fréquente des ID placés sur liste noire est l'intégration incorrecte entre l'infrastructure client et Audience Manager. Lorsque vous identifiez un identifiant sur liste noire, vérifiez soigneusement les intégrations d'Audience Manager. See **Implementation and Integration Guides** for detailed explanations of how you should configure Audience Manager to work with other Experience Cloud solutions or external systems.

Another frequent cause of blacklisted IDs are indexing bots (web crawlers), which generally cause increases in traffic, leading to the same IDs being sent to the [!UICONTROL DCS] multiple times. Si vous identifiez l'indexation des robots comme motif de liste noire d'ID, vous devez limiter l'accès aux robots à votre site Web.

Si vous avez un temps dur pour identifier les problèmes d'intégration, n'hésitez pas à contacter le service clientèle. Prior to opening a support request, make sure to keep the `.har` `HTTP` archive of your browser ready. Cette archive aide l'équipe d'assistance à identifier les raisons pour lesquelles l'association de l'ID a eu lieu.