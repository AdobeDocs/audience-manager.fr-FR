---
description: Présentation et flux de travail pour les acheteurs de données qui souhaitent acheter des données tierces depuis Audience Manager
seo-description: Présentation et flux de travail pour les acheteurs de données qui souhaitent acheter des données tierces depuis Audience Manager
seo-title: Audience Marketplace pour les acheteurs de données
solution: Audience Manager
title: Audience Marketplace pour les acheteurs de données
topic: API DIL
uuid: f 505 b 5 f 4-4231-4 e 84-993 a-cd 64128 b 540 f
translation-type: tm+mt
source-git-commit: 12cc02103902a77b8b5967c319f4ac18746a700e

---


# Audience Marketplace for Data Buyers {#audience-marketplace-for-data-buyers}

Overview and workflow for data buyers who want to purchase third-party data from within [!DNL Audience Manager].

>[!NOTE]
>[Les autorisations basées sur un rôle](../../../reporting/reports-dashboard.md) contrôlent l&#39;accès aux [!UICONTROL Audience Marketplace] fonctionnalités.
>
>* Les administrateurs peuvent créer des flux de données, gérer les abonnés et s&#39;abonner aux flux de données.
>* Les utilisateurs peuvent uniquement rechercher des flux et les afficher.


## The Marketplace: About {#about-marketplace}

<!-- c_marketplace_about.xml -->

The [!UICONTROL Marketplace] is an [!DNL Audience Manager] feature for data buyers that lists data feeds you can subscribe to. It lists flat rate, [!DNL CPM], or private data feeds. These feeds are provided by third-party vendors that use [!DNL Audience Manager] to sell data. In the [!UICONTROL Marketplace], reporting tools let you track feed usage and the overlap between your traits and those in a subscribed data feed. Finally, with [!UICONTROL Audience Marketplace], [!DNL Adobe] takes care of invoices and fee payments (though you do have to self-report usage when subscribed to a [!DNL CPM] feed). Ces fonctionnalités vous permettent de trouver des sources de données efficaces sans perdre de temps à rechercher un fournisseur de données.

>[!TIP]
> 
>Use the **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** to find high quality data feeds that you can subscribe to. Then, go back into the Audience Manager UI or use the [Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) to subscribe to the feeds you found.

![](assets/buyer_marketplace.png)

The [!UICONTROL Marketplace] list contains information that you can sort and search to find the data feed that&#39;s right for you. Items in the [!UICONTROL Marketplace] buyer&#39;s list include:

* **[!UICONTROL Search]:** Recherchez les flux de données par nom ou description texte.
* **[!UICONTROL Name]:** Nom du flux de données.
* **[!UICONTROL Description]:** Informations sur le contenu d&#39;un flux de données.
* **[!UICONTROL Provider]:** Nom du fournisseur de données.
* **[!UICONTROL Traits]:** Nombre de caractéristiques dans un flux de données.
* **[!UICONTROL 30 Day Provider Unique Users]:** Nombre d&#39;utilisateurs uniques vus au cours des 30 derniers jours.
* **[!UICONTROL 30 Day Overlapped Uniques]:** nombre d&#39;utilisateurs de votre compte qui se chevauchent avec les utilisateurs du compte du fournisseur.
* **[!UICONTROL Feed Overlap]:** La valeur unique chevauchée de 30 jours, affichée en pourcentages, est calculée comme suit : Acheteur de données 30 jours chevauché/acheteur de données 30 jours uniques) x 100.
* **[!UICONTROL Private Feeds]:** Voir [Flux de données privés](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]:** nombre d&#39;abonnements que vous disposez d&#39;un fournisseur de données.

## Flux de données privés {#private-data-feeds}

In the [!UICONTROL Marketplace] list, sometimes the provider&#39;s name and trait data are marked as private. This indicates a [private data feed](../../../features/audience-marketplace/marketplace-private-feeds.md). Un flux de données privé permet aux vendeurs de limiter l&#39;accès aux données à l&#39;acheteur. Les vendeurs peuvent rendre les flux privés lorsqu&#39;ils proposent des offres spéciales, des remises ou lorsque leur confidentialité et leur contrôle d&#39;accès sont importants pour eux. En tant qu&#39;acheteur, vous devez envoyer une demande d&#39;abonnement au vendeur si vous souhaitez accéder à un flux privé. See [Subscribe to a Private Data Feed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) for details.

>[!MORE_ LIKE_ THIS]
>
>* [Présentation de la page des détails de la formule d’Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details) (en anglais)
>* [Remises pour les acheteurs de données](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

