---
description: Présentation et workflow pour les acheteurs de données qui souhaitent acheter des données tierces à partir d’Audience Manager
seo-description: Overview and workflow for data buyers who want to purchase third-party data from within Audience Manager
seo-title: Audience Marketplace for Data Buyers
solution: Audience Manager
title: Audience Marketplace pour les acheteurs de données
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
TQID: https://experienceleague.adobe.com/7rX24xDAh7PEcN29jLv-b1z0EhSp2Ku5-KlVoBVi4CA
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
  - id: d8f86c1e-15ad-457f-9d6f-5e756573fad4
subfeature_v2:
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
  - id: d921db59-bd4a-43dc-97e6-4ff4611f1ae8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: f2fdbb191013b0bcb9bdab0529e3b7f3c872fd54
workflow-type: tm+mt
source-wordcount: 729
ht-degree: 2%

---

# [!UICONTROL Audience Marketplace] pour les acheteurs de données {#audience-marketplace-for-data-buyers}

Présentation et workflow pour les acheteurs de données qui souhaitent acheter des données tierces depuis [!DNL Audience Manager].

>[!NOTE]
>[Autorisations basées sur les rôles](../../../reporting/reports-dashboard.md) contrôlez l’accès aux fonctionnalités [!UICONTROL Audience Marketplace].
>
>* Les administrateurs peuvent créer des flux de données, gérer les abonnés et s’abonner à des flux de données.
>* Les utilisateurs peuvent uniquement rechercher et afficher des flux.

## Le [!UICONTROL Marketplace] : À propos de {#about-marketplace}

La [!UICONTROL Marketplace] est une fonctionnalité [!DNL Audience Manager] pour les acheteurs de données qui répertorie les flux de données auxquels vous pouvez vous abonner. Il répertorie les flux de données fixes, [!DNL CPM] et privés. Ces flux sont fournis par des fournisseurs tiers qui utilisent [!DNL Audience Manager] pour vendre des données.

Dans le [!UICONTROL Marketplace], les outils de création de rapports vous permettent de suivre l’utilisation des flux et le chevauchement entre vos [!UICONTROL traits] et ceux d’un flux de données avec abonnement. Enfin, avec [!UICONTROL Audience Marketplace], [!DNL Adobe] s’occupe des factures et des paiements de frais (bien que vous deviez déclarer vous-même l’utilisation lorsque vous êtes abonné à un flux [!DNL CPM]). Ces fonctionnalités vous permettent de trouver des sources de données efficaces sans perdre de temps à rechercher un fournisseur de données.

>[!TIP]
>
>Utilisez l’outil de recherche d’audiences **[Adobe](https://www.adobe-audience-finder.com/)** pour trouver des flux de données de haute qualité auxquels vous pouvez vous abonner. Ensuite, revenez à l’interface utilisateur [!DNL Audience Manager] ou utilisez [l’API Audience Marketplace Buyer](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) pour vous abonner aux flux trouvés.

![présentation-marketplace-acheteur](assets/buyer-marketplace-overview.png)

La liste [!UICONTROL Marketplace] contient des informations que vous pouvez trier et rechercher pour trouver le flux de données qui vous convient. Les objets figurant sur la liste d&#39;achat [!UICONTROL Marketplace] sont les suivants :

* **[!UICONTROL Search]**: Find data feeds by name or text description.
* **[!UICONTROL Similar Traits]** : affiche le nombre de [!UICONTROL traits] similaires d’un flux de données. This column is shown after you enter a [!UICONTROL trait] or [!UICONTROL segment] to filter by in the **[!UICONTROL Similarity To]** section.
* **[!UICONTROL Name]** : nom du flux de données.
* **[!UICONTROL Description]** : informations sur le contenu d’un flux de données.
* **[!UICONTROL Provider]**: Name of the data provider.
* **[!UICONTROL Traits]**: The number of [!UICONTROL traits] in a data feed.
* **[!UICONTROL 30 Day Provider Unique Users]**: The number of unique users seen in the last 30 days.
* **[!UICONTROL 30 Day Overlapped Uniques]**: The number of users in your account that overlap with the users in the provider’s account.
* **[!UICONTROL Feed Overlap]**: The 30 day overlapped uniques value, displayed in percentages, calculated as: Data buyer 30 day overlapped uniques / Data buyer 30 day uniques) x 100.
* **[!UICONTROL Private Feeds]**: See [Private Data Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: The number of subscriptions you have with a data provider.

 

To easily find the best data feeds for your needs, use the following filters available on the left side of the [!UICONTROL Marketplace] page:

* **[!UICONTROL Similarity To]**: Filter data feeds based on their similarity to either a [!UICONTROL trait] or [!UICONTROL segment] of your choosing. When entering the [!UICONTROL trait] or segment to compare to, you can use the [!UICONTROL trait] or [!UICONTROL segment] ID, or their respective names.
* **[!UICONTROL Similarity Cutoff]**: Drag the slider to filter the data feeds based on how similar their [!UICONTROL traits] are to your selected [!UICONTROL trait] or [!UICONTROL segment].
* **[!UICONTROL Subscription Status]**: Filter the data feeds based on your subscription status.
* **[!UICONTROL Plan Use Case]**: Filter data feeds based on their supported use cases: **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]**, and **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Filter data feeds based on their pricing type.

## Finding Similar [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] gives you the option to find [!UICONTROL traits] from various data feeds, based on their similarity to your existing [!UICONTROL traits] or segments. Procédez comme suit :

1. Go to **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Use the **[!UICONTROL Similarity To]** selector to choose between filtering based on a [!UICONTROL trait] or [!UICONTROL segment]. You can filter based on [!UICONTROL trait]/[!UICONTROL segment] ID or name. The search box automatically shows you relevant suggestions based on your input.
3. Once you&#39;ve identified the trait or segment that you want to filter by, click it in the suggestions list.
4. To narrow down the results, use the **[!UICONTROL Similarity Cutoff]** slider to move from less similar [!UICONTROL traits], to more similar ones.

Once the filtering is complete, you&#39;ll see a new column in the results page: **[!UICONTROL Similar Traits]**. This column shows you the number of similar [!UICONTROL traits] to the one you filtered by, from each data feed that meets the filtering criteria.

Pour afficher la liste complète des caractéristiques similaires, cliquez sur le nombre dans la colonne **[!UICONTROL Similar Traits]** .

>[!NOTE]
>
> Audience Marketplace affiche les 500 premiers résultats de [!UICONTROL trait] similaires provenant des flux de données.

Regardez la vidéo ci-dessous pour un aperçu complet de la manière de trouver des [!UICONTROL traits] similaires.

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Flux de données privés {#private-data-feeds}

Dans la liste [!UICONTROL Marketplace], le nom et les données [!UICONTROL trait] du fournisseur sont parfois marqués comme privés. Indique un [flux de données privé](../../../features/audience-marketplace/marketplace-private-feeds.md). Un flux de données privé permet aux vendeurs de limiter l’accès des acheteurs à leurs données. Les vendeurs peuvent rendre les flux privés lorsqu&#39;ils offrent des offres spéciales, des remises ou lorsque la confidentialité et le contrôle d&#39;accès sont importants pour eux. En tant qu&#39;acheteur, vous devez envoyer une demande d&#39;abonnement au vendeur si vous souhaitez accéder à un flux privé. Voir [S’abonner à un flux de données privé](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) pour plus d’informations.

>[!MORELIKETHIS]
>
>* [Présentation de la page des détails de la formule d’Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details) (en anglais)
>* [Remises pour les acheteurs de données](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)
