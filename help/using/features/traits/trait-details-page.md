---
description: La page Détails d'une caractéristique individuelle donne une vue d'ensemble des informations telles que le nom de la caractéristique, l'ID, les mesures de performances, les expressions qui définissent la caractéristique, les segments auxquels il appartient et le journal d'audit de la caractéristique. Pour les afficher, accédez à Données d'audience > Caractéristiques, puis cliquez sur le nom de la caractéristique avec laquelle vous souhaitez travailler.
seo-description: La page Détails d'une caractéristique individuelle donne une vue d'ensemble des informations telles que le nom de la caractéristique, l'ID, les mesures de performances, les expressions qui définissent la caractéristique, les segments auxquels il appartient et le journal d'audit de la caractéristique. Pour les afficher, accédez à Données d'audience > Caractéristiques, puis cliquez sur le nom de la caractéristique avec laquelle vous souhaitez travailler.
seo-title: Page Détails de la caractéristique
solution: Audience Manager
title: Page Détails de la caractéristique
uuid: 23301376-c 1 cc -4778-b 8 c 4-9831 f 6739 db 9
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# Trait Details Page {#trait-details-page}

La page Détails d&#39;une caractéristique individuelle donne une vue d&#39;ensemble des informations telles que le nom de la caractéristique, l&#39;ID, les mesures de performances, les expressions qui définissent la caractéristique, les segments auxquels il appartient et le journal d&#39;audit de la caractéristique. To vew these details, go to [!UICONTROL Audience Data > Traits] and click the name of the trait you want to work with.

## Informations fondamentales {#basics}

The [!UICONTROL Basic Information] section shows details about required and optional fields you completed when building the trait. Cela inclut des éléments tels que le type de caractéristique, l&#39;ID de caractéristique, la description, la source de données et d&#39;autres métadonnées. Ces détails varient selon le type de caractéristique (dossier, emplacement intégré ou selon des règles).

![](assets/basicInfo.png)

## Trait Graph {#trait-graph}

The [!UICONTROL Trait Graph] provides at-a-glance performance metrics for your selected trait. Maintenez votre curseur sur une ligne de tendance pour afficher d&#39;autres données pour la caractéristique sélectionnée.

[!UICONTROL Unique Trait Realizations] représentent le nombre d&#39;utilisateurs uniques qui ont ajouté cette caractéristique à leur profil au cours de la période donnée. The [!UICONTROL Total Trait Population] indicates the number of unique users currently qualified for this trait.

* Pour les caractéristiques basées sur des règles, la qualification des caractéristiques se produit en temps réel, car les utilisateurs remplissent une caractéristique dans leur navigateur.
* For onboarded traits, trait qualification happens after an inbound file is processed, i.e. the inbound file is [fed into Audience Manager](../../faq/faq-inbound-data-ingestion.md) and that is when the trait qualification happens.
* **Realizations de caractéristiques uniques**: Nombre d&#39;utilisateurs uniques qui ont ajouté cette caractéristique à leur profil au cours de la période donnée.
* **Population totale de caractéristiques**: Nombre d&#39;utilisateurs uniques actuellement qualifiés pour cette caractéristique.

![](assets/traitGraph.png)

## Trait Expression {#trait-expression}

The [!UICONTROL Trait Expression] section shows you the criteria users must meet to qualify for the trait. These rules are set when you [create or edit a trait](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## Trait Segments {#trait-segments}

The [!UICONTROL Segments with this Trait] section lists all the segments the selected trait belongs to. Vous pouvez cliquer sur un nom de segment pour afficher des détails sur ce segment.

![](assets/traitSegments.png)

## Trait Audit/History Log {#trait-audit-history}

For rule-based and onboarded traits, the [!UICONTROL Trait Expression Change History] shows you the last 10 changes made to trait expression rules and who made them. If your trait has more than 10 changes, click **[!UICONTROL Export to CSV]** to download the entire audit log. Le journal d&#39;audit n&#39;est pas disponible pour les caractéristiques d&#39;un dossier ou d&#39;un algorithme.

>[!NOTE]
>
>[!UICONTROL Not Available] dans [!UICONTROL By User] la colonne signifie que le compte de cet utilisateur a été supprimé.

![](assets/traitHistory.png)