---
description: Audience Analytics vous permet d’envoyer des segments d’Audience Manager vers Analytics. Pour utiliser cette fonctionnalité, créez une destination Analytics à laquelle vous associez des segments dans Audience Manager.
seo-description: Audience Analytics vous permet d’envoyer des segments d’Audience Manager vers Analytics. Pour utiliser cette fonctionnalité, créez une destination Analytics à laquelle vous associez des segments dans Audience Manager.
seo-title: Configuration d'une destination Analytics
solution: Audience Manager
title: Configuration d'une destination Analytics
translation-type: tm+mt
source-git-commit: 3179b9007e102f7031cc4cc9e0da64f77cfa3eeb

---


# Configuration d&#39;une destination Analytics

## Conditions requises {#requirements}

See [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/).

## Votre destination Analytics par défaut et les nouvelles destinations Analytics

| Type de destination Analytics | Description |
|---|---|
| Par défaut | Le nom de cette destination par défaut est « Adobe Analytics », que vous pouvez modifier. Les ID de suite de rapports mappés s&#39;affichent dans le stockage des dossiers pour vos caractéristiques et segments Audience Manager. <br>Audience Manager crée automatiquement une destination si votre compte comporte : <br> <ul><li>Met the requirements described in the [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/) documentation.</li><li>A [report suite](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-reports-report-suites.html) in Analytics.</li><li>[Association d&#39;une suite de rapports à une organisation](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).</li></ul> |
| Nouveau | Pour créer de nouvelles destinations Analytics, accédez à Données d&#39;audience &gt; Destinations &gt; Créer une destination et suivez les étapes de chaque section décrit ci-dessous. |

## Étape 1 : Fournir des informations de base

Cette section contient des champs et des options qui démarrent le processus de création de destination d&#39;Analytics. Pour terminer cette section :

1. Click **Basic Information** to expose the controls.
2. Nommez la destination. Evitez les abréviations et les caractères spéciaux.
3. *(Facultatif)* Décrivez la destination. Une description concise permet de définir ou fournir plus d&#39;informations sur une destination.
4. *(Facultatif)* Dans la liste **Plate-forme** , laissez le jeu par défaut **sur Tous**. Actuellement, ces options ne font rien. Ils sont conçus pour prendre en charge les fonctionnalités qui peuvent être ajoutées ultérieurement.
5. In the **Category** list, select **Adobe Experience Cloud**.
6. In the **Type** list, select **Adobe Analytics**.
7. Click **Save** to go to the Configuration settings or click **Data Export Labels** to apply export controls to the destination.

>[!NOTE]
>
>For an Analytics destination, the **Auto-fill Destination Mappping** check box and **Segment ID** option are selected by default. Vous ne pouvez pas modifier ces paramètres.

![base de base](assets/basicinformation.png)

## Étape 2 : Configuration des contrôles d&#39;exportation des données

This section contains options that apply [Data Export Controls](/help/using/features/data-export-controls.md) to an Analytics destination. Ignorez cette étape si vous n&#39;utilisez pas les commandes d&#39;exportation de données. Pour terminer cette section :

1. Click **Data Export Controls** to expose the controls.
2. Select a label that corresponds to the data export control applied to the destination (see [Add Data Export Labels to a Destination](/help/using/features/destinations/manage-destinations.md#add-data-export-labels) ). Pour les destinations Analytics, la case à cocher Informations d&#39;identification personnelle est sélectionnée par défaut.
3. Cliquez sur **Enregistrer**.

![exportcontrols](assets/exportControls.png)

## Étape 3 : Mappage des suites de rapports

La section Configuration répertorie les suites de rapports Analytics qui ont été activées pour le transfert côté serveur. Si vous disposez de plusieurs destinations Analytics, les suites de rapports affectées à ces destinations sont mutuellement : exclusives et appliquées par Audience Manager. Pour terminer cette section :

1. Click **Configuration** to expose the controls.
2. Sélectionnez une ou plusieurs suites de rapports auxquelles vous voulez envoyer des segments.
3. Cliquez sur **Enregistrer**.

![reportsuites](assets/reportSuites.png)

## Étape 4 : Correspondances de segments

Cette section propose des options vous permettant de mapper automatiquement ou manuellement les segments.

| Option de mappage | Description |
|---|---|
| Mappage automatique de tous les segments actuels et futurs | Sélectionné par défaut, cette fonction envoie tous les segments qu&#39;un visiteur qualifie pour, par accès, Analytics. <br>Si un visiteur appartient à plus de 150 segments Audience Manager sur un seul accès, seuls les 150 segments qualifiés les plus récemment qualifiés sont envoyés à Analytics, tandis que la liste restante est tronquée. Un indicateur supplémentaire est envoyé à Analytics signifiant que la liste des segments a été tronquée. Cette action s&#39;affiche sous la forme « Limite d&#39;audience atteinte » dans la dimension Nom des audiences et « 1 » dans la dimension ID d&#39;audiences. See the [FAQ](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/mc-audiences-faqs.html) for details. <br>Cette option affecte également la disponibilité de destination dans [le créateur de segments](/help/using/features/segments/segment-builder.md). For example, if a segment is mapped automatically to an Analytics destination, that destination is not available for selection in the [destination mappings](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) section of Segment Builder. La destination Analytics apparaît grisée et affiche « Analytics » dans la colonne Type du navigateur de destination. |
| Mise en correspondance manuelle des segments | Cette option affiche les commandes de recherche et de navigation qui vous permettent de choisir les segments à envoyer à Analytics. <br>Pour rechercher un segment : <br> <ol><li>Tapez le nom ou l&#39;identifiant du segment dans le champ de recherche.</li><li>Cliquez sur <b>Ajouter.</b></li><li>Continue to search and add segments or click <b>Done</b>.</li></ol><br>Pour rechercher un segment : <ol><li>Click <b>Browse all segments</b>. Cette opération expose la liste des segments disponibles.</li><li>From the list, select the check box of the segment you want to use and click <b>Add selected segments</b>.</li><li>Click <b>Save</b> in the Add Mappings window. Vous ne pouvez pas modifier les dates de mappage, de début ou de fin pendant la version bêta.</li><li>Continue to browse and add segments or click <b>Done</b>.</li></ol> |

![mapsegments](assets/mapSegments.png)

## Étapes suivantes

Après avoir créé et enregistré une destination, vous pouvez utiliser ces données dans Analytics. Toutefois, cette opération peut prendre quelques heures avant que les données ne soient disponibles dans les suites de rapports sélectionnées. See [Use the Audience Data in Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/use-audience-data-analytics.html).



