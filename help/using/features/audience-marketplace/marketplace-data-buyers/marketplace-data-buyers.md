---
description: Présentation et workflow pour les acheteurs de données qui souhaitent acheter des données tierces à partir d’Audience Manager
seo-description: Overview and workflow for data buyers who want to purchase third-party data from within Audience Manager
seo-title: Audience Marketplace for Data Buyers
solution: Audience Manager
title: Audience Marketplace pour les acheteurs de données
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '724'
ht-degree: 1%

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

* **[!UICONTROL Search]** : rechercher des flux de données par nom ou description textuelle.
* **[!UICONTROL Similar Traits]** : affiche le nombre de [!UICONTROL traits] similaires d’un flux de données. Cette colonne s’affiche après avoir saisi un [!UICONTROL trait] ou un [!UICONTROL segment] à utiliser comme filtre dans la section **[!UICONTROL Similarity To]**.
* **[!UICONTROL Name]** : nom du flux de données.
* **[!UICONTROL Description]** : informations sur le contenu d’un flux de données.
* **[!UICONTROL Provider]** : nom du fournisseur de données.
* **[!UICONTROL Traits]** : nombre de [!UICONTROL traits] dans un flux de données.
* **[!UICONTROL 30 Day Provider Unique Users]** : nombre d’utilisateurs uniques vus au cours des 30 derniers jours.
* **[!UICONTROL 30 Day Overlapped Uniques]** : nombre d’utilisateurs de votre compte qui se chevauchent avec les utilisateurs du compte du fournisseur.
* **[!UICONTROL Feed Overlap]** : valeur uniques de 30 jours avec chevauchement, affichée en pourcentages, calculée comme suit : acheteur de données 30 jours avec chevauchement uniques / acheteur de données 30 jours uniques) x 100.
* **[!UICONTROL Private Feeds]** : Voir [Flux de données privés](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]** : nombre d’abonnements dont vous disposez auprès d’un fournisseur de données.

 

Pour trouver facilement les flux de données qui répondent le mieux à vos besoins, utilisez les filtres suivants disponibles sur le côté gauche de la page [!UICONTROL Marketplace] :

* **[!UICONTROL Similarity To]** : filtrez les flux de données en fonction de leur similarité avec un [!UICONTROL trait] ou un [!UICONTROL segment] de votre choix. Lors de la saisie du [!UICONTROL trait] ou du segment auquel effectuer la comparaison, vous pouvez utiliser l’ID de [!UICONTROL trait] ou de [!UICONTROL segment], ou leurs noms respectifs.
* **[!UICONTROL Similarity Cutoff]** : faites glisser le curseur pour filtrer les flux de données en fonction de la similitude de leurs [!UICONTROL traits] avec les [!UICONTROL trait] ou [!UICONTROL segment] sélectionnés. Pour en savoir plus sur [!UICONTROL trait] scores de similarité, voir [&#x200B; Score de similarité de caractéristique &#x200B;](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]** : filtrez les flux de données en fonction du statut de votre abonnement.
* **[!UICONTROL Plan Use Case]** : filtrez les flux de données en fonction de leurs cas d’utilisation pris en charge : **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]** et **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]** : filtrez les flux de données en fonction de leur type de tarification.

## Recherche de [!UICONTROL Traits] similaires {#finding-similar-traits}

[!UICONTROL Audience Marketplace] vous donne la possibilité de rechercher des [!UICONTROL traits] à partir de divers flux de données, en fonction de leur similitude avec vos [!UICONTROL traits] ou segments existants. Procédez comme suit :

1. Accédez à **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Utilisez le sélecteur de **[!UICONTROL Similarity To]** pour choisir entre le filtrage basé sur un [!UICONTROL trait] ou un [!UICONTROL segment]. Vous pouvez filtrer par identifiant ou nom de [!UICONTROL trait]/[!UICONTROL segment]. La zone de recherche affiche automatiquement les suggestions pertinentes en fonction de vos entrées.
3. Une fois que vous avez identifié la caractéristique ou le segment selon lequel vous souhaitez filtrer, cliquez dessus dans la liste de suggestions.
4. Pour réduire les résultats, utilisez le curseur **[!UICONTROL Similarity Cutoff]** pour passer de [!UICONTROL traits] moins similaires à des plus similaires.

Une fois le filtrage terminé, une nouvelle colonne s&#39;affiche dans la page de résultats : **[!UICONTROL Similar Traits]**. Cette colonne indique le nombre de [!UICONTROL traits] similaires à celui que vous avez filtré, pour chaque flux de données qui répond aux critères de filtrage.

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
