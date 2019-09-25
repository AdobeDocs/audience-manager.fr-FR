---
description: Audience Analytics vous permet d’envoyer des segments d’Audience Manager vers Analytics. Pour utiliser cette fonctionnalité, créez une destination Analytics à laquelle vous associez des segments dans Audience Manager.
seo-description: Audience Analytics vous permet d’envoyer des segments d’Audience Manager vers Analytics. Pour utiliser cette fonctionnalité, créez une destination Analytics à laquelle vous associez des segments dans Audience Manager.
seo-title: ' Configuration d’une destination Analytics'
solution: Audience Manager
title: ' Configuration d’une destination Analytics'
translation-type: tm+mt
source-git-commit: fa39d070be9ec9f07e9da31de3efd151dd2c6cf1

---


# Configure an Analytics Destination

## Conditions requises {#requirements}

Pour configurer une destination Analytics, l’utilisateur d’Audience Manager doit disposer des autorisations d’administrateur. Voir [Création d’utilisateurs](/help/using/features/administration/administration-overview.md#create-users) dans le Guide d’administration. Notez que l’autorisation `CREATE_DESTINATIONS` [](/help/using/features/administration/administration-overview.md#wild-card-permissions) de caractères génériques n’est pas suffisante pour créer des destinations Analytics.
Pour plus d’informations sur la configuration requise, voir Conditions préalables dans [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/).

## Votre destination Analytics par défaut et vos nouvelles destinations Analytics

| Type de destination Analytics | Description |
|---|---|
| Par défaut | Le nom de cette destination par défaut est "Adobe Analytics", que vous pouvez modifier. Les ID de suite de rapports mappés apparaissent dans le stockage de dossiers pour vos caractéristiques et segments Audience Manager. <br>  Audience Manager crée automatiquement une destination si votre compte comporte les éléments suivants : <br>  <ul><li>Satisfait aux exigences décrites dans la documentation [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/) .</li><li>Suite [de](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-reports-report-suites.html) rapports dans Analytics.</li><li>[Mapped a report suite to an organization](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).</li></ul> |
| Nouveau | Pour créer de nouvelles destinations Analytics, accédez à Données d’audience &gt; Destinations &gt; Créer une destination et suivez les étapes décrites ci-dessous. |

## Étape 1 : Fournir des informations de base

Cette section contient des champs et des options qui démarrent le processus de création de destination Analytics. Pour compléter cette section :

1. Cliquez sur Informations **** de base pour afficher les commandes.
2. Nommez la destination. Evitez les abréviations et les caractères spéciaux.
3. *(Facultatif)* Décrivez la destination. Une description concise est un moyen efficace de définir ou de fournir plus d’informations sur une destination.
4. *(Facultatif)* Dans la liste **Plate-forme** , laissez le paramètre par défaut sur **Tous**. Actuellement, ces options ne font rien. Elles sont conçues pour prendre en charge des fonctionnalités qui peuvent être ajoutées ultérieurement.
5. Dans la liste **Catégorie** , sélectionnez **Adobe Experience Cloud**.
6. Dans la liste **Type** , sélectionnez **Adobe Analytics**.
7. Cliquez sur **Enregistrer** pour accéder aux paramètres de configuration ou sur **Data Export Labels** pour appliquer des contrôles d’exportation à la destination.

>[!NOTE]
>
>Pour une destination Analytics, la case à cocher Mappage **de destination** automatique et l’option ID **de** segment sont sélectionnées par défaut. Vous ne pouvez pas modifier ces paramètres.

![information de base](assets/basicinformation.png)

## Étape 2 : Configuration des contrôles d’exportation de données

This section contains options that apply [Data Export Controls](/help/using/features/data-export-controls.md) to an Analytics destination. Skip this step if you do not use data export controls. To complete this section:

1. Click **Data Export Controls** to expose the controls.
1. Select a label that corresponds to the data export control applied to the destination (see Add Data Export Labels to a Destination ). [](/help/using/features/destinations/add-data-export-labels.md) For Analytics destinations, the PII check box is selected by default.
1. Cliquez sur **Enregistrer**.

![exportcontrols](assets/exportControls.png)

## Step 3: Map Report Suites

La section Configuration répertorie vos suites de rapports Analytics qui ont été activées pour le transfert côté serveur. If you have multiple Analytics destinations, the report suites assigned to these destinations will be mutually exclusive and enforced by Audience Manager. To complete this section:

1. Click Configuration to expose the controls.****
1. Select one (or more) report suites that you want to send segments to.
1. Cliquez sur **Enregistrer**.

![reportsuites](assets/reportSuites.png)

## Step 4: Segment Mappings

This section provides options that let you map segments automatically or manually.

| Option de mappage | Description |
|---|---|
| Mappez automatiquement tous les segments actuels et futurs. | Sélectionnée par défaut, cette fonctionnalité envoie tous les segments pour lesquels un visiteur est admissible, par accès, à Analytics. <br>  If a visitor belongs to more than 150 Audience Manager segments on a single hit, only the 150-most recently qualified segments are sent to Analytics, while the remaining list is truncated. Un indicateur supplémentaire est envoyé à Analytics pour indiquer que la liste de segments a été tronquée. Cette action s’affiche sous la forme "Limite d’audience atteinte" dans la dimension Nom des audiences et "1" dans la dimension ID d’audiences. Consultez la [FAQ](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/mc-audiences-faqs.html) pour plus de détails. <br>  Cette option affecte également la disponibilité de la destination dans le créateur de [segments](/help/using/features/segments/segment-builder.md). Par exemple, si un segment est automatiquement mappé sur une destination Analytics, cette destination n’est pas disponible pour la sélection dans la section Mappages [de](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) destination du créateur de segments. La destination Analytics apparaît grisée et affiche "Analytics" dans la colonne Type du navigateur de destination. |
| Mappage manuel des segments | Cette option expose les commandes de recherche et de navigation qui vous permettent de choisir les segments à envoyer à Analytics. <br>  Pour rechercher un segment : <br>  <ol><li>Tapez le nom ou l’identifiant du segment dans le champ de recherche.</li><li>Cliquez sur <b>Ajouter.</b></li><li>Continuez à rechercher et à ajouter des segments ou cliquez sur <b>Terminé</b>.</li></ol><br>  Pour rechercher un segment : <ol><li>Cliquez sur <b>Parcourir tous les segments</b>. Vous affichez ainsi une liste des segments disponibles.</li><li>Dans la liste, cochez la case du segment à utiliser, puis cliquez sur <b>Ajouter les segments</b>sélectionnés.</li><li>Cliquez sur <b>Enregistrer</b> dans la fenêtre Ajouter des mappages. Vous ne pouvez pas modifier les mises en correspondance, les dates de début ou de fin pendant la version bêta.</li><li>Continuez à parcourir et à ajouter des segments ou cliquez sur <b>Terminé</b>.</li></ol> ![mapsegments](assets/mapSegments.png) |

## Étapes suivantes

Après avoir créé et enregistré une destination, vous pouvez utiliser ces données dans Analytics. Toutefois, il peut s’écouler quelques heures avant que les données ne soient disponibles dans les suites de rapports sélectionnées. See [Use the Audience Data in Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/use-audience-data-analytics.html).
