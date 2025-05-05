---
description: Audience Analytics vous permet d’envoyer des segments d’Audience Manager vers Analytics. Pour utiliser cette fonctionnalité, créez une destination Analytics à laquelle vous associez des segments dans Audience Manager.
seo-description: Audience Analytics lets you send Audience Manager segments to Analytics. To use this feature, you create an Analytics destination and map segments to it in Audience Manager.
seo-title: Configure an Analytics Destination
solution: Audience Manager
title: Configuration d’une destination Analytics
feature: Adobe Analytics Integration
exl-id: f3ead057-04d1-40cd-8e3d-d0934d85cdb4
source-git-commit: ef8cca16c8c9478f8558c26bf6f3ae95cd72e7ac
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 4%

---

# Configuration d’une destination Analytics

## Exigences {#requirements}

Pour configurer une destination Analytics, l’utilisateur de votre Audience Manager doit disposer des autorisations d’administrateur. Voir [Création d’utilisateurs](/help/using/features/administration/administration-overview.md#create-users) dans le Guide d’administration. Notez que disposer de l’autorisation `CREATE_DESTINATIONS` [caractère générique](/help/using/features/administration/administration-overview.md#wild-card-permissions) ne suffit pas pour créer des destinations Analytics.
Pour plus d’informations sur les exigences, voir Conditions préalables dans [Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html?lang=fr).

## Votre destination Analytics par défaut et les nouvelles destinations Analytics

| Type de destination Analytics | Description |
|---|---|
| Par défaut | Le nom de cette destination par défaut est &quot;Adobe Analytics&quot;, que vous pouvez modifier. Les identifiants de suite de rapports mappés apparaissent dans le stockage de dossiers pour vos segments et caractéristiques d’Audience Manager. <br>  L’Audience Manager crée automatiquement une destination si votre compte possède : <br>  <ul><li>Répondez aux exigences décrites dans la documentation [Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html?lang=fr).</li><li>Une [suite de rapports](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html?lang=fr) dans Analytics.</li></ul> |
| Nouveau | Pour créer de nouvelles destinations Analytics, accédez à Audience Data > Destinations > Créer une destination et suivez les étapes décrites ci-dessous pour chaque section. |

## Qualifications des segments d’Audience Manager dans Adobe Analytics {#segment-qualifications}

Lors de l’envoi d’informations sur les segments vers une destination Analytics, l’Audience Manager envoie uniquement les segments pour lesquels le visiteur a rempli les critères. Si un visiteur cesse de se qualifier pour un segment, ces informations sont _et non_ transférées à Adobe Analytics.

Par exemple, tenez compte des règles de segmentation ci-dessous :

* Segment A : caractéristique 1 ET caractéristique 2
* Segment B : caractéristique 1 ET NON caractéristique 2

Dans les rapports Analytics, un profil peut s’afficher comme qualifié pour les deux segments, même s’il n’a plus été qualifié pour le segment B.

## Étape 1 : fournir des informations de base

Cette section contient des champs et des options qui démarrent le processus de création de destination Analytics. Pour terminer cette section :

1. Cliquez sur **Informations de base** pour afficher les contrôles.
2. Nommez la destination. Évitez les abréviations et les caractères spéciaux.
3. *(Facultatif)* Décrivez la destination. Une description concise est un moyen efficace de définir ou de fournir plus d’informations sur une destination.
4. *(Facultatif)* Dans la liste **Plateforme**, laissez le paramètre par défaut défini sur **Toutes**. Actuellement, ces options ne font rien. Elles sont conçues pour prendre en charge des fonctionnalités qui peuvent être ajoutées ultérieurement.
5. Dans la liste **Category**, sélectionnez **Adobe Experience Cloud**.
6. Dans la liste **Type**, sélectionnez **Adobe Analytics**.
7. Cliquez sur **Enregistrer** pour accéder aux paramètres de configuration ou sur **Étiquettes d’exportation de données** pour appliquer des contrôles d’exportation à la destination.

>[!NOTE]
>
>Pour une destination Analytics, la case à cocher **Correspondance de destination avec remplissage automatique** et l’option **Identifiant de segment** sont sélectionnées par défaut. Vous ne pouvez pas modifier ces paramètres.

![basicinformation](assets/basicinformation.png)

## Étape 2 : configuration des contrôles des exportations de données

Cette section contient des options qui s’appliquent aux [contrôles des exportations de données](/help/using/features/data-export-controls.md) vers une destination Analytics. Ignorez cette étape si vous n’utilisez pas les contrôles d’exportation des données. Pour terminer cette section :

1. Cliquez sur **Contrôles des exportations de données** pour afficher les contrôles.
1. Sélectionnez un libellé correspondant au contrôle d’exportation des données appliqué à la destination (voir [Ajout de libellés d’exportation de données à une destination](/help/using/features/destinations/add-data-export-labels.md) ). Pour les destinations Analytics, la case à cocher PII est sélectionnée par défaut.
1. Cliquez sur **Enregistrer**.

![exportcontrol](assets/exportControls.png)

## Étape 3 : Mappage des suites de rapports

La section Configuration répertorie vos suites de rapports Analytics qui ont été activées pour le transfert côté serveur. Si vous disposez de plusieurs destinations Analytics, les suites de rapports affectées à ces destinations seront mutuellement exclusives et appliquées par Audience Manager. Pour terminer cette section :

1. Cliquez sur **Configuration** pour afficher les contrôles.
1. Sélectionnez une ou plusieurs suites de rapports auxquelles vous souhaitez envoyer des segments.
1. Cliquez sur **Enregistrer**.

![reportsuites](assets/reportSuites.png)

## Étape 4 : mappages de segments

Cette section fournit des options qui vous permettent de mapper les segments automatiquement ou manuellement.

| Option de mappage | Description |
|---|---|
| Mappage automatique de tous les segments actuels et futurs | Sélectionnée par défaut, cette fonctionnalité envoie à Analytics tous les segments pour lesquels un visiteur est admissible, par accès. <br>  Si un visiteur appartient à plus de 150 segments d’Audience Manager sur un seul accès, seuls les 150 segments les plus récemment qualifiés sont envoyés à Analytics, tandis que la liste des 150 segments restants est tronquée. Un indicateur supplémentaire est envoyé à Analytics pour indiquer que la liste de segments a été tronquée. Cette action s’affiche sous la forme &quot;Limite d’audience atteinte&quot; dans la dimension Nom d’audience et &quot;1&quot; dans la dimension ID d’audience. Pour plus d’informations, consultez la [FAQ](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html?lang=fr) . <br>  En outre, cette option affecte la disponibilité de la destination dans le [créateur de segments](/help/using/features/segments/segment-builder.md). Par exemple, si un segment est automatiquement mappé à une destination Analytics, cette destination ne peut pas être sélectionnée dans la section [mappages de destination](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) du créateur de segments. La destination Analytics apparaît en grisé et affiche &quot;Analytics&quot; dans la colonne Type du navigateur de destination. |
| Mappage manuel des segments | Cette option expose les commandes de recherche et de navigation qui vous permettent de choisir les segments que vous souhaitez envoyer à Analytics. <br>  Pour rechercher un segment : <br>  <ol><li>Saisissez le nom ou l’identifiant du segment dans le champ de recherche.</li><li>Cliquez sur <b>Ajouter.</b></li><li>Continuez à rechercher et à ajouter des segments ou cliquez sur <b>Terminé</b>.</li></ol><br>  Pour rechercher un segment : <ol><li>Cliquez sur <b>Parcourir tous les segments</b>. Cette opération expose une liste de segments disponibles.</li><li>Dans la liste, cochez la case du segment à utiliser et cliquez sur <b>Ajouter les segments sélectionnés</b>.</li><li>Cliquez sur <b>Enregistrer</b> dans la fenêtre Ajouter des mappages . Vous ne pouvez pas modifier les mappages, les dates de début ou de fin au cours de la version bêta.</li><li>Continuez à parcourir et à ajouter des segments ou cliquez sur <b>Terminé</b>.</li></ol> ![mapsegments](assets/mapSegments.png) |

## Étapes suivantes

Après avoir créé et enregistré une destination, vous pouvez utiliser ces données dans Analytics. Toutefois, il peut s’écouler quelques heures avant que les données ne soient disponibles dans les suites de rapports sélectionnées. Voir [Utilisation des données d’audience dans Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html?lang=fr).
