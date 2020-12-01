---
description: La page de détails d’une caractéristique individuelle fournit un aperçu des informations telles que le nom de la caractéristique, l’ID, les mesures de performances, les expressions qui définissent la caractéristique, les segments auxquels elle appartient et le journal d’audit des caractéristiques. Pour afficher ces détails, accédez à Audience Data > Caractéristiques et cliquez sur le nom de la caractéristique que vous souhaitez utiliser.
seo-description: La page de détails d’une caractéristique individuelle fournit un aperçu des informations telles que le nom de la caractéristique, l’ID, les mesures de performances, les expressions qui définissent la caractéristique, les segments auxquels elle appartient et le journal d’audit des caractéristiques. Pour afficher ces détails, accédez à Audience Data > Caractéristiques et cliquez sur le nom de la caractéristique que vous souhaitez utiliser.
seo-title: Page Détails des caractéristiques
solution: Audience Manager
title: Page Détails des caractéristiques
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: identity type breakdown, identity breakdown, audience identity reporting, cross-device, cross-device ID, device ID
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 1%

---


# [!UICONTROL Trait] Page Détails  {#trait-details-page}

La page de détails d&#39;une [!UICONTROL trait] personne fournit un aperçu des détails [!UICONTROL trait], tels que le nom [!UICONTROL trait], l&#39;identifiant, les mesures de performances, les expressions qui définissent [!UICONTROL trait], les segments auxquels elle appartient et le journal d&#39;audit [!UICONTROL trait]. Pour vue ces détails, accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** et cliquez sur le nom de [!UICONTROL trait] que vous souhaitez utiliser.

## [!UICONTROL Trait] Outils de gestion  {#trait-management-tools}

Le haut de la page de détails [!UICONTROL trait] héberge les outils que vous pouvez utiliser pour gérer votre [!UICONTROL traits] :

1. **[!UICONTROL Add New]**: Utilisez cette option pour créer  [!UICONTROL rule-based],  [!UICONTROL algorithmic] ou  [!UICONTROL onboarded traits].
2. **[!UICONTROL Edit]**: Utilisez cette option pour modifier la configuration de la  [!UICONTROL trait]variable active.
3. **[!UICONTROL Delete]**: Utilisez cette option pour supprimer l’actif  [!UICONTROL trait] de votre compte d’Audience Manager.
4. **[!UICONTROL Marketplace Recommendations]**: Utilisez cette option pour trouver la même chose  [!UICONTROL traits] que celle que vous consultez, à partir des frais de  [!UICONTROL Audience Marketplace] données auxquels vous n’êtes pas abonné. Voir [Audience Marketplace pour les acheteurs de données](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) pour savoir comment naviguer dans [!UICONTROL Marketplace] et trouver des caractéristiques similaires.

![information de base sur les caractéristiques](assets/basic-trait-information.png)

## [!UICONTROL Trait] Informations {#basics}

La section [!UICONTROL Trait Information] affiche des détails sur les champs obligatoires et facultatifs que vous avez renseignés lors de la création de [!UICONTROL trait]. Cela inclut des éléments tels que le type [!UICONTROL trait], l&#39;ID [!UICONTROL trait], la description, [!UICONTROL data source] et d&#39;autres métadonnées. Ces détails varient selon le type [!UICONTROL trait] ([!UICONTROL folder], [!UICONTROL onboarded] ou [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

Le [!UICONTROL Trait Graph] fournit des mesures de performances en un coup d&#39;oeil pour le [!UICONTROL trait] sélectionné. Placez le curseur sur une ligne de tendance pour afficher des données supplémentaires pour le [!UICONTROL trait] sélectionné.

[!UICONTROL Unique Trait Realizations] représentent le nombre d’utilisateurs uniques qui ont ajouté ceci  [!UICONTROL trait] à leur profil au cours d’une période donnée. Le [!UICONTROL Total Trait Population] indique le nombre d&#39;utilisateurs uniques actuellement qualifiés pour ce [!UICONTROL trait].

Pour [!UICONTROL rule-based traits], la qualification [!UICONTROL trait] se produit en temps réel, car les utilisateurs remplissent les conditions requises pour accéder à [!UICONTROL trait] dans leur navigateur.

Pour [!UICONTROL onboarded traits], la qualification [!UICONTROL trait] se produit après le traitement d&#39;un fichier entrant, c&#39;est-à-dire que le fichier entrant est [ajouté à l&#39;Audience Manager](../../faq/faq-inbound-data-ingestion.md) et que la qualification [!UICONTROL trait] se produit.

Le [!UICONTROL Trait Graph] contient les informations suivantes :

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: sélectionnez cette option pour afficher les résultats pour  [!UICONTROL traits] lesquels collectent des données pour des profils authentifiés. Lorsque vous sélectionnez cette option, seules les données du rapport [!UICONTROL Cross-Device ID] s’affichent et aucune donnée ne sera présente sous le rapport [!UICONTROL Device ID].
   * **[!UICONTROL Device ID]**: sélectionnez cette option pour afficher les résultats pour  [!UICONTROL traits] lesquels collectent des données pour les profils de périphériques. Lorsque vous sélectionnez cette option, seules les données du rapport [!UICONTROL Device ID] s’affichent et aucune donnée ne sera présente sous le rapport [!UICONTROL Cross-Device ID].

      ![trait-graphique](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: Nombre d’utilisateurs uniques qui ont ajouté ceci  [!UICONTROL trait] à leur profil au cours d’une période donnée.
* **[!UICONTROL Total Trait Population]**: Nombre d’utilisateurs uniques actuellement qualifiés pour ce type  [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**: Les trois premières entrées montrent les trois premières  [!UICONTROL cross-device data sources] avec le plus grand nombre de personnes ayant obtenu le  [!UICONTROL trait]classement, dans l&#39;ordre décroissant. La quatrième entrée indique la somme de tous les autres [!DNL DPUUIDs] ([!DNL CRM IDs]) qui se sont qualifiés pour [!UICONTROL trait], à partir de [!UICONTROL cross-device data sources] qui ne figurent pas dans les trois premiers. Ce rapport s’affiche uniquement si vous sélectionnez [!UICONTROL Cross-device ID] dans le menu déroulant [!UICONTROL Show Results By] en haut à droite de la page. L’option de liste déroulante par défaut est [!UICONTROL Device ID], où ce rapport n’est pas affiché.

   ![trait-graphique](assets/trait-identity.png)

   >[!NOTE]
   >
   >L&#39;Audience Manager n&#39;affiche le rapport [!UICONTROL Identity Type Breakdown] que si [!UICONTROL cross-device] ID sont qualifiés pour [!UICONTROL trait].

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] Expression {#trait-expression}

La section [!UICONTROL Trait Expression] présente les critères que les utilisateurs doivent respecter pour être admissibles au [!UICONTROL trait]. Ces règles sont définies lorsque vous [créez ou modifiez une caractéristique](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait]Segments {#trait-segments}

La section [!UICONTROL Segments with this Trait] liste tous les segments auxquels [!UICONTROL trait] sélectionné appartient. Vous pouvez cliquer sur le nom d’un segment pour afficher les détails sur ce segment.

![](assets/traitSegments.png)

## [!UICONTROL Trait] Journal d’audit/d’historique  {#trait-audit-history}

Pour [!UICONTROL rule-based] et [!UICONTROL onboarded traits], [!UICONTROL Trait Expression Change History] présente les 10 dernières modifications apportées aux règles d&#39;expression [!UICONTROL trait] et les personnes qui les ont apportées. Si votre [!UICONTROL trait] comporte plus de 10 modifications, cliquez sur **[!UICONTROL Export to CSV]** pour télécharger l&#39;intégralité du journal d&#39;audit. Le journal d&#39;audit n&#39;est pas disponible pour [!UICONTROL folder] ou [!UICONTROL algorithmic traits].

>[!NOTE]
>
>[!UICONTROL Not Available] dans la  [!UICONTROL By User] colonne signifie que le compte de cet utilisateur a été supprimé.

![](assets/traitHistory.png)