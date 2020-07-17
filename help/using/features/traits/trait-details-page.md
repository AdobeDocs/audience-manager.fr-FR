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


# [!UICONTROL Trait] Page Détails {#trait-details-page}

La page de détails d’une personne [!UICONTROL trait] fournit un aperçu des [!UICONTROL trait] détails, tels que le [!UICONTROL trait] nom, l’ID, les mesures de performances, les expressions qui définissent le [!UICONTROL trait]segment, les segments auxquels il appartient et le journal d’ [!UICONTROL trait] audit. Pour vue ces détails, cliquez sur **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** et cliquez sur le nom du [!UICONTROL trait] que vous souhaitez utiliser.

## [!UICONTROL Trait] Outils de gestion {#trait-management-tools}

La partie supérieure de la page [!UICONTROL trait] de détails héberge les outils que vous pouvez utiliser pour gérer vos [!UICONTROL traits]:

1. **[!UICONTROL Add New]**: Utilisez cette option pour créer [!UICONTROL rule-based], [!UICONTROL algorithmic]ou [!UICONTROL onboarded traits].
2. **[!UICONTROL Edit]**: Utilisez cette option pour modifier la configuration de la [!UICONTROL trait]variable active.
3. **[!UICONTROL Delete]**: Utilisez cette option pour supprimer l’actif [!UICONTROL trait] de votre compte d’Audience Manager.
4. **[!UICONTROL Marketplace Recommendations]**: Utilisez cette option pour trouver la même solution que [!UICONTROL traits] celle que vous consultez, à partir des frais [!UICONTROL Audience Marketplace] de données auxquels vous n’êtes pas abonné. Voir [Audience Marketplace pour les acheteurs](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) de données pour savoir comment naviguer dans le [!UICONTROL Marketplace] site et trouver des caractéristiques similaires.

![information de base sur les caractéristiques](assets/basic-trait-information.png)

## [!UICONTROL Trait] Informations {#basics}

La [!UICONTROL Trait Information] section affiche des détails sur les champs obligatoires et facultatifs que vous avez renseignés lors de la création de la [!UICONTROL trait]. Il s’agit notamment du [!UICONTROL trait] type, de l’ [!UICONTROL trait] ID, de la description [!UICONTROL data source]et d’autres métadonnées. Ces détails varient en fonction du [!UICONTROL trait] type ([!UICONTROL folder], [!UICONTROL onboarded]ou [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

Le [!UICONTROL Trait Graph] fournit des mesures de performances en un coup d’oeil pour votre sélection [!UICONTROL trait]. Placez le curseur sur une ligne de tendance pour afficher des données supplémentaires pour la ligne sélectionnée [!UICONTROL trait].

[!UICONTROL Unique Trait Realizations] représentent le nombre d’utilisateurs uniques qui ont ajouté ceci [!UICONTROL trait] à leur profil au cours d’une période donnée. Le [!UICONTROL Total Trait Population] indique le nombre d’utilisateurs uniques actuellement qualifiés pour cette [!UICONTROL trait]campagne.

En [!UICONTROL rule-based traits]effet, [!UICONTROL trait] la qualification se produit en temps réel, dans la mesure où les utilisateurs remplissent les conditions requises pour bénéficier d’une [!UICONTROL trait] qualification dans leur navigateur.

Par exemple, [!UICONTROL onboarded traits]la [!UICONTROL trait] qualification se produit après le traitement d&#39;un fichier entrant, c&#39;est-à-dire que le fichier entrant est [alimenté en Audience Manager](../../faq/faq-inbound-data-ingestion.md) et c&#39;est-à-dire lorsque la [!UICONTROL trait] qualification se produit.

Le [!UICONTROL Trait Graph] montre les informations suivantes :

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: sélectionnez cette option pour afficher les résultats pour [!UICONTROL traits] lesquels collectent des données pour les profils authentifiés. Lorsque vous sélectionnez cette option, seules les données du [!UICONTROL Cross-Device ID] rapport s’affichent et aucune donnée ne s’affiche sous le [!UICONTROL Device ID] rapport.
   * **[!UICONTROL Device ID]**: sélectionnez cette option pour afficher les résultats pour [!UICONTROL traits] lesquels collectent des données pour les profils de périphériques. Lorsque vous sélectionnez cette option, seules les données du [!UICONTROL Device ID] rapport s’affichent et aucune donnée ne s’affiche sous le [!UICONTROL Cross-Device ID] rapport.

      ![trait-graphique](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: Nombre d’utilisateurs uniques qui ont ajouté ceci [!UICONTROL trait] à leur profil au cours d’une période donnée.
* **[!UICONTROL Total Trait Population]**: Nombre d’utilisateurs uniques actuellement qualifiés pour ce type [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**: Les trois premières entrées montrent les trois premières [!UICONTROL cross-device data sources] avec le plus grand nombre de personnes ayant obtenu le [!UICONTROL trait]classement, dans l&#39;ordre décroissant. La quatrième entrée montre la somme de tous les autres [!DNL DPUUIDs] ([!DNL CRM IDs]) qui ont été qualifiés pour le [!UICONTROL trait], des [!UICONTROL cross-device data sources] qui ne sont pas dans les trois premiers. Ce rapport s&#39;affiche uniquement si vous sélectionnez [!UICONTROL Cross-device ID] dans le menu [!UICONTROL Show Results By] déroulant en haut à droite de la page. L’option de liste déroulante par défaut est [!UICONTROL Device ID]l’endroit où ce rapport n’est pas affiché.

   ![trait-graphique](assets/trait-identity.png)

   >[!NOTE]
   >
   >L&#39;Audience Manager affiche le [!UICONTROL Identity Type Breakdown] rapport uniquement si [!UICONTROL cross-device] les ID sont qualifiés pour le [!UICONTROL trait].

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] Expression {#trait-expression}

La [!UICONTROL Trait Expression] section présente les critères que les utilisateurs doivent respecter pour être admissibles au [!UICONTROL trait]programme. Ces règles sont définies lorsque vous [créez ou modifiez une caractéristique](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait]Segments {#trait-segments}

La [!UICONTROL Segments with this Trait] section liste tous les segments auxquels [!UICONTROL trait] appartient la sélection. Vous pouvez cliquer sur le nom d’un segment pour afficher les détails sur ce segment.

![](assets/traitSegments.png)

## [!UICONTROL Trait] Journal d’audit/d’historique {#trait-audit-history}

Pour [!UICONTROL rule-based] et [!UICONTROL onboarded traits], le [!UICONTROL Trait Expression Change History] montre les 10 dernières modifications apportées aux règles d&#39; [!UICONTROL trait] expression et qui les a apportées. Si votre [!UICONTROL trait] compte plus de 10 modifications, cliquez **[!UICONTROL Export to CSV]** pour télécharger l’intégralité du journal d’audit. Le journal d&#39;audit n&#39;est pas disponible pour [!UICONTROL folder] ou [!UICONTROL algorithmic traits].

>[!NOTE]
>
>[!UICONTROL Not Available] dans la [!UICONTROL By User] colonne signifie que le compte de cet utilisateur a été supprimé.

![](assets/traitHistory.png)