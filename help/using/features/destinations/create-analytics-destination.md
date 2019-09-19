---
description: Audience Analytics vous permet d’envoyer des segments d’Audience Manager vers Analytics. Pour utiliser cette fonctionnalité, créez une destination Analytics à laquelle vous associez des segments dans Audience Manager.
seo-description: Audience Analytics vous permet d’envoyer des segments d’Audience Manager vers Analytics. Pour utiliser cette fonctionnalité, créez une destination Analytics à laquelle vous associez des segments dans Audience Manager.
seo-title: ' Configuration d’une destination Analytics'
solution: Audience Manager
title: ' Configuration d’une destination Analytics'
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


#  Configuration d’une destination Analytics

## Conditions requises {#requirements}

Voir Analyses [d’audience](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/).

## Votre destination Analytics par défaut et vos nouvelles destinations Analytics

| Type de destination Analytics | Description |
|---|---|
| Par défaut | Le nom de cette destination par défaut est "Adobe Analytics", que vous pouvez modifier. Les ID de suite de rapports mappés apparaissent dans le stockage de dossiers pour vos caractéristiques et segments Audience Manager. <br>  Audience Manager crée automatiquement une destination si votre compte comporte les éléments suivants : <br>  <ul><li>Satisfait aux exigences décrites dans la documentation [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/) .</li><li>Suite [de](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-reports-report-suites.html) rapports dans Analytics.</li><li>[Association d’une suite de rapports à une organisation](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).</li></ul> |
| Nouveau | Pour créer de nouvelles destinations Analytics, accédez à Données d’audience &gt; Destinations &gt; Créer une destination et suivez les étapes décrites ci-dessous. |

## Étape 1 : Fournir des informations de base

Cette section contient des champs et des options qui démarrent le processus de création de destination Analytics. Pour compléter cette section :

1. Cliquez sur Informations **** de base pour afficher les commandes.
1. Nommez la destination. Evitez les abréviations et les caractères spéciaux.
1. *(Facultatif)* Décrivez la destination. Une description concise est un moyen efficace de définir ou de fournir plus d’informations sur une destination.
1. *(Facultatif)* Dans la liste **Plate-forme** , laissez le paramètre par défaut sur **Tous**. Actuellement, ces options ne font rien. Elles sont conçues pour prendre en charge des fonctionnalités qui peuvent être ajoutées ultérieurement.
1. Dans la liste **Catégorie** , sélectionnez **Adobe Experience Cloud**.
1. Dans la liste **Type** , sélectionnez **Adobe Analytics**.
1. Cliquez sur **Enregistrer** pour accéder aux paramètres de configuration ou sur **Data Export Labels** pour appliquer des contrôles d’exportation à la destination.

>[!NOTE]
>
>Pour une destination Analytics, la case à cocher Mappage **de destination** automatique et l’option ID **de** segment sont sélectionnées par défaut. Vous ne pouvez pas modifier ces paramètres.

![information de base](assets/basicinformation.png)

## Étape 2 : Configuration des contrôles d’exportation de données

Cette section contient des options qui appliquent des contrôles [d’exportation de](/help/using/features/data-export-controls.md) données à une destination Analytics. Ignorez cette étape si vous n’utilisez pas les contrôles d’exportation de données. Pour compléter cette section :

1. Cliquez sur **Data Export Controls** pour exposer les commandes.
1. Sélectionnez une étiquette correspondant au contrôle d'exportation des données appliqué à la destination (voir [Ajouter des étiquettes d'exportation de données à une destination](/help/using/features/destinations/add-data-export-labels.md) ). Pour les destinations Analytics, la case à cocher Informations d’identification personnelle est activée par défaut.
1. Cliquez sur **Enregistrer**.

![contrôles des exportations](assets/exportControls.png)

## Étape 3 : Mettre en correspondance les suites de rapports

La section Configuration répertorie vos suites de rapports Analytics qui ont été activées pour le transfert côté serveur. Si vous avez plusieurs destinations Analytics, les suites de rapports affectées à ces destinations seront mutuellement exclusives et mises en oeuvre par Audience Manager. Pour compléter cette section :

1. Cliquez sur **Configuration** pour afficher les commandes.
1. Sélectionnez une ou plusieurs suites de rapports auxquelles vous souhaitez envoyer des segments.
1. Cliquez sur **Enregistrer**.

![suites de rapports](assets/reportSuites.png)

## Étape 4 : Mappages de segments

Cette section propose des options qui vous permettent de mapper les segments automatiquement ou manuellement.

| Option de mappage | Description |
|---|---|
| Mappez automatiquement tous les segments actuels et futurs. | Sélectionnée par défaut, cette fonctionnalité envoie tous les segments pour lesquels un visiteur est admissible, par accès, à Analytics. <br>  Si un visiteur appartient à plus de 150 segments d’Audience Manager sur un seul accès, seuls les 150 segments qualifiés les plus récents sont envoyés à Analytics, tandis que la liste restante est tronquée. Un indicateur supplémentaire est envoyé à Analytics pour indiquer que la liste de segments a été tronquée. Cette action s’affiche sous la forme "Limite d’audience atteinte" dans la dimension Nom des audiences et "1" dans la dimension ID d’audiences. Consultez la [FAQ](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/mc-audiences-faqs.html) pour plus de détails. <br>  Cette option affecte également la disponibilité de la destination dans le créateur de [segments](/help/using/features/segments/segment-builder.md). Par exemple, si un segment est automatiquement mappé sur une destination Analytics, cette destination n’est pas disponible pour la sélection dans la section Mappages [de](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) destination du créateur de segments. La destination Analytics apparaît grisée et affiche "Analytics" dans la colonne Type du navigateur de destination. |
| Mappage manuel des segments | Cette option expose les commandes de recherche et de navigation qui vous permettent de choisir les segments à envoyer à Analytics. <br>  Pour rechercher un segment : <br>  <ol><li>Tapez le nom ou l’identifiant du segment dans le champ de recherche.</li><li>Cliquez sur <b>Ajouter.</b></li><li>Continuez à rechercher et à ajouter des segments ou cliquez sur <b>Terminé</b>.</li></ol><br>  Pour rechercher un segment : <ol><li>Cliquez sur <b>Parcourir tous les segments</b>. Vous affichez ainsi une liste des segments disponibles.</li><li>Dans la liste, cochez la case du segment à utiliser, puis cliquez sur <b>Ajouter les segments</b>sélectionnés.</li><li>Cliquez sur <b>Enregistrer</b> dans la fenêtre Ajouter des mappages. Vous ne pouvez pas modifier les mises en correspondance, les dates de début ou de fin pendant la version bêta.</li><li>Continuez à parcourir et à ajouter des segments ou cliquez sur <b>Terminé</b>.</li></ol> ![mapsegments](assets/mapSegments.png) |

## Étapes suivantes

Après avoir créé et enregistré une destination, vous pouvez utiliser ces données dans Analytics. Toutefois, il peut s’écouler quelques heures avant que les données ne soient disponibles dans les suites de rapports sélectionnées. See [Use the Audience Data in Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/use-audience-data-analytics.html).
