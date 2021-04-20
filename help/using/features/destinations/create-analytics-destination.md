---
description: Audience Analytics vous permet d’envoyer des segments d’Audience Manager vers Analytics. Pour utiliser cette fonctionnalité, créez une destination Analytics à laquelle vous associez des segments dans Audience Manager.
seo-description: Audience Analytics vous permet d’envoyer des segments d’Audience Manager vers Analytics. Pour utiliser cette fonctionnalité, créez une destination Analytics à laquelle vous associez des segments dans Audience Manager.
seo-title: Configuration d’une destination Analytics
solution: Audience Manager
title: Configuration d’une destination Analytics
feature: Adobe Analytics Integration
exl-id: f3ead057-04d1-40cd-8e3d-d0934d85cdb4
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 9%

---

# Configuration d’une destination Analytics

## Exigences {#requirements}

Pour configurer une destination Analytics, l’utilisateur de votre Audience Manager doit disposer des autorisations d’administrateur. Voir [Créer des utilisateurs](/help/using/features/administration/administration-overview.md#create-users) dans le Guide d&#39;administration. Notez que l’autorisation de caractère générique `CREATE_DESTINATIONS` [](/help/using/features/administration/administration-overview.md#wild-card-permissions) n’est pas suffisante pour créer des destinations Analytics.
Pour plus d&#39;informations sur les conditions requises, voir Conditions préalables dans [Audience Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html).

## Votre destination Analytics par défaut et les nouvelles destinations Analytics

| Type de destination Analytics | Description |
|---|---|
| Par défaut | Le nom de cette destination par défaut est &quot;Adobe Analytics&quot;, que vous pouvez modifier. Les identifiants de suite de rapports mappés s’affichent dans l’enregistrement de dossiers pour vos caractéristiques et segments d’Audience Manager. <br>  L’Audience Manager crée automatiquement une destination si votre compte dispose des éléments suivants :  <br>  <ul><li>Satisfaites aux exigences décrites dans la documentation [Audience Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html).</li><li>[suite de rapports](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html) dans Analytics.</li><li>[Association d’une suite de rapports à une organisation](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html).</li></ul> |
| Nouveau | Pour créer de nouvelles destinations Analytics, accédez à Audience Data > Destinations > Create New Destination et suivez les étapes décrites ci-dessous pour chaque section. |

## Étape 1 : Fournir des informations de base

Cette section contient des champs et des options qui début le processus de création de destination Analytics. Pour compléter cette section :

1. Cliquez sur **Informations de base** pour afficher les commandes.
2. Nommez la destination. Evitez les abréviations et les caractères spéciaux.
3. *(Facultatif)* Décrivez la destination. Une description concise est un moyen efficace de définir ou de fournir plus d&#39;informations sur une destination.
4. *(Facultatif)* Dans la  **** liste Plateforme, laissez le paramètre par défaut sur  **Tous**. Actuellement, ces options ne font rien. Ils sont conçus pour prendre en charge des fonctionnalités qui peuvent être ajoutées ultérieurement.
5. Dans la liste **Catégorie**, sélectionnez **Adobe Experience Cloud**.
6. Dans la liste **Type**, sélectionnez **Adobe Analytics**.
7. Cliquez sur **Enregistrer** pour accéder aux paramètres de configuration ou sur **Data Export Labels** pour appliquer des contrôles d&#39;exportation à la destination.

>[!NOTE]
>
>Pour une destination Analytics, les cases à cocher **Correspondance de destination de remplissage automatique** et **ID de segment** sont sélectionnées par défaut. Vous ne pouvez pas modifier ces paramètres.

![informations de base](assets/basicinformation.png)

## Étape 2 : Configuration des contrôles d’exportation de données

Cette section contient des options qui appliquent [Contrôles d’exportation de données](/help/using/features/data-export-controls.md) à une destination Analytics. Ignorez cette étape si vous n’utilisez pas les contrôles d’exportation de données. Pour compléter cette section :

1. Cliquez sur **Contrôles d’exportation de données** pour afficher les contrôles.
1. Sélectionnez une étiquette correspondant au contrôle d&#39;exportation des données appliqué à la destination (voir [Ajouter les étiquettes d&#39;exportation des données à une destination](/help/using/features/destinations/add-data-export-labels.md) ). Pour les destinations Analytics, la case à cocher Informations d’identification personnelle est sélectionnée par défaut.
1. Cliquez sur **Enregistrer**.

![contrôles des exportations](assets/exportControls.png)

## Étape 3 : Mettre en correspondance les suites de rapports

La section Configuration liste vos suites de rapports Analytics qui ont été activées pour le transfert côté serveur. Si vous avez plusieurs destinations Analytics, les suites de rapports attribuées à ces destinations s’excluent mutuellement et sont appliquées par Audience Manager. Pour compléter cette section :

1. Cliquez sur **Configuration** pour afficher les commandes.
1. Sélectionnez une (ou plusieurs) suite de rapports à laquelle vous souhaitez envoyer des segments.
1. Cliquez sur **Enregistrer**.

![reportsuites](assets/reportSuites.png)

## Étape 4 : Mappages de segments

Cette section propose des options qui vous permettent de mapper des segments automatiquement ou manuellement.

| Option de mappage | Description |
|---|---|
| Mapper automatiquement tous les segments actuels et futurs | Sélectionnée par défaut, cette fonction envoie à Analytics tous les segments pour lesquels un visiteur est admissible, par accès. <br>  Si un visiteur appartient à plus de 150 segments d’Audience Manager sur un seul accès, seuls les 150 segments les plus récemment qualifiés sont envoyés à Analytics, tandis que la liste restante est tronquée. Un indicateur supplémentaire est envoyé à Analytics pour indiquer que la liste de segments a été tronquée. Cette action s’affiche sous la forme &quot;limite d’Audience atteinte&quot; dans la dimension Nom des Audiences et &quot;1&quot; dans la dimension ID des Audiences. Voir la [FAQ](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html) pour plus de détails. <br>  Cette option affecte également la disponibilité de la destination dans le créateur [ de ](/help/using/features/segments/segment-builder.md)segments. Par exemple, si un segment est automatiquement mappé à une destination Analytics, cette destination n’est pas disponible pour la sélection dans la section [mappages de destination](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) du créateur de segments. La destination Analytics apparaît grisée et affiche &quot;Analytics&quot; dans la colonne Type du navigateur de destination. |
| Mappage manuel des segments | Cette option expose les commandes de recherche et de navigation qui vous permettent de choisir les segments à envoyer à Analytics. <br>  Pour rechercher un segment :  <br>  <ol><li>Tapez le nom ou l’identifiant du segment dans le champ de recherche.</li><li>Cliquez sur <b>Ajouter.</b></li><li>Continuez à rechercher et à ajouter des segments ou cliquez sur <b>Terminé</b>.</li></ol><br>  Pour rechercher un segment : <ol><li>Cliquez sur <b>Parcourir tous les segments</b>. Cela expose une liste de segments disponibles.</li><li>Dans la liste, cochez la case du segment à utiliser et cliquez sur <b>Ajouter les segments sélectionnés</b>.</li><li>Cliquez sur <b>Enregistrer</b> dans la fenêtre Correspondances d’Ajoutes. Vous ne pouvez pas modifier les mappages, les dates de début ou les dates de fin au cours de la version bêta.</li><li>Continuez à parcourir et à ajouter des segments ou cliquez sur <b>Terminé</b>.</li></ol> ![mapsegments](assets/mapSegments.png) |

## Étapes suivantes

Après avoir créé et enregistré une destination, vous pouvez utiliser ces données dans Analytics. Toutefois, il peut s’écouler quelques heures avant que les données ne soient disponibles dans les suites de rapports sélectionnées. Voir [Utilisation des données d’Audience dans Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html).
