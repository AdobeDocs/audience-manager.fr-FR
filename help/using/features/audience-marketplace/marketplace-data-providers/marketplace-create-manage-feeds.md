---
description: Un flux de données requiert un nom, une description, une source de données et un type de plan. Les flux sont désactivés jusqu'à ce que vous enregistriez et activiez le flux. Configurez les flux de données publics ou privés dans Audience Marketplace > Mes données partagées. Disponible uniquement pour les vendeurs de données.
seo-description: Un flux de données requiert un nom, une description, une source de données et un type de plan. Les flux sont désactivés jusqu'à ce que vous enregistriez et activiez le flux. Configurez les flux de données publics ou privés dans Audience Marketplace > Mes données partagées. Disponible uniquement pour les vendeurs de données.
seo-title: Création, prix et gestion des flux de données
solution: Audience Manager
title: Création, prix et gestion des flux de données
topic: API DIL
uuid: e 28 c 20 b 3-33 fc -4485-8 ee 9-8530 d 126 f 741
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create, Price, and Manage Data Feeds {#create-price-and-manage-data-feeds}

Un flux de données requiert un nom, une description, une source de données et un type de plan. Les flux sont désactivés jusqu&#39;à ce que vous enregistriez et activiez le flux. Set up public or private data feeds in [!UICONTROL Audience Marketplace] &gt; [!UICONTROL My Shared Data]. Disponible uniquement pour les vendeurs de données.

## Create a Public or Private Data Feed {#create-public-private-data-feed}

Un flux de données requiert un nom, une description, une source de données et un type de plan. Les flux sont désactivés jusqu&#39;à ce que vous enregistriez et activiez le flux. Set up public or private data feeds in **[!UICONTROL Audience Marketplace > My Shared Data]**. Disponible uniquement pour les vendeurs de données.

<!-- t_data_feed.xml -->

Vous devez disposer des droits d&#39;administrateur pour créer un flux de données public ou privé.
Pour créer un flux de données :

1. Cliquez sur **[!UICONTROL New Data Feed]**.
1. Nommez le flux de données. Les acheteurs de données peuvent rechercher votre flux en fonction du nom.
1. Fournissez une brève description (255 caractères maximum).

   Une bonne description doit décrire votre flux avec précision. For example, you could include text for marketing categories, demographics, and geographic coverage (e.g., [!DNL US] or North America). La description du texte est possible et permet aux acheteurs de rechercher ou d&#39;évaluer votre flux. Une bonne description est un élément important d&#39;attirer les abonnés à votre flux de données.
1. Select a data source from the **[!UICONTROL Data Source]** options.

   >[!IMPORTANT]
   >
   >Toutes les caractéristiques actuelles et futures appartenant à cette source de données seront partagées avec vos acheteurs de données dans le cadre de ce flux.

1. In [!UICONTROL Plan Types], select the options you want to use and click **[!UICONTROL Add Plan]**.

   Les flux peuvent contenir plusieurs plans. Les plans peuvent contenir plusieurs cas d&#39;utilisation. For details, see [Plan Types for Data Feeds](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types).

1. Click **[!UICONTROL Save]** to save your data fee *without* activating it.
1. Pour enregistrer et activer un flux de données :
   1. Move the **[!UICONTROL Availability]** slider to **[!UICONTROL Active]**.
   1. Cliquez sur **[!UICONTROL Save]**.
   >[!NOTE]
   >
   >* Les flux de données enregistrés et activés ne peuvent pas être supprimés.
   >* Les acheteurs voient les flux actifs uniquement.


### Facultatif : Création d&#39;un flux de données privé

In the [!UICONTROL Settings] section, move the slider to:

* **[!UICONTROL Private]** et **[!UICONTROL Branded]**: [!UICONTROL Marketplace] La liste de l&#39;acheteur indique le nom du vendeur dans la colonne fournisseur et toutes les autres données sont masquées.

* **[!UICONTROL Private]** et **[!UICONTROL Unbranded]**: La [!UICONTROL Marketplace] liste de l&#39;acheteur affiche uniquement le nom et la description du flux de données. The data provider name appears as [!UICONTROL Private Seller].

To see what a private feed looks like to buyers, see the buyers section in [Private Data Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md).

>[!MORE_ LIKE_ THIS]
>
>* [Flux de données privés](../../../features/audience-marketplace/marketplace-private-feeds.md)


## Désactivation du flux de données d’un abonné {#deactivate-data-feed}

As an [!UICONTROL Audience Marketplace] data provider, you can revoke buyer access to a subscribed data feed. Vous pouvez supprimer un acheteur d&#39;un flux pour des raisons telles que le retard de paiement ou le non-paiement des frais ou s&#39;ils utilisent erronément des données de caractéristique.

<!-- marketplace-deactiva4te-subscribers.xml -->

Pour révoquer un abonné :

1. In [!UICONTROL My Shared Data], find the feed the subscriber is using.

   >[!NOTE]
   >
   >Les flux de données avec des comptes en retard sont marqués avec une icône Triangle/Exclamation.

1. In the [!UICONTROL Subscribers] column, click the blue number that counts subscribers for that feed. Cette page ouvre la page des détails d&#39;abonnement.
1. Move the **[!UICONTROL Subscription]** slider to **[!UICONTROL Off]**. Cette fenêtre ouvre une fenêtre de dialogue de confirmation.
1. In the [!UICONTROL Confirmation] pop, click **[!UICONTROL Yes]** to deactivate a subscription or **[!UICONTROL Cancel]** to quit without making subscription changes.

### Ce qui se produit après avoir désactivé un abonné

La révocation d&#39;un accès à un flux de données envoie un courrier électronique de notification à tous les utilisateurs administrateurs dans le compte de l&#39;acheteur de données. Le courrier électronique comprend une pièce jointe qui répertorie les caractéristiques révoquées. Cette liste permet aux abonnés de rechercher et de supprimer des caractéristiques désactivées de leurs segments et modèles.

### Facturation et désactivation de flux

Après avoir supprimé l&#39;accès à un flux de données, les abonnés sont chargés de payer les frais correspondant au mois précédent ou en cours, selon le moment où vous désactivez le flux.

## Plan Types for Data Feeds {#plan-types}

[!DNL Plan types] sont des composants essentiels d&#39;un flux [!UICONTROL Audience Marketplace] de données. En tant que fournisseur de données, ils vous permettent de créer plusieurs cas d&#39;utilisation et des options de prix pour vos flux. De plus, il peut être judicieux de créer quelques plans pour chaque flux de données. Les acheteurs peuvent ainsi choisir d&#39;où ils proviennent lorsqu&#39;ils recherchent des données à modéliser ou envoyer vers une destination.

[Créez un flux](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) de données à sélectionner [!UICONTROL Plan Types].

![](assets/plan_types.png)

## Plan Types and Use Case Options {#plan-types-use-cases}

<!-- c_feed_options.xml -->

The [!UICONTROL Use Case] settings let sellers control how buyers can use your data.

### Segments et chevauchement

A **[!UICONTROL Segments and Overlap]** use case creates a plan that lets buyers compare trait data in a [trait-to-trait overlap report](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report). Furthermore, buyers can add your data to segments and make comparisons with the [segment-to-trait](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) and [segment-to-segment](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) reports.

Each data feed must include at least one [!UICONTROL Segments and Overlap] use case. Buyers cannot subscribe to other plans in a data feed if the feed does not contain a [!UICONTROL Segments and Overlap] use case, either by itself or in combination with another use case.

Les comparaisons de chevauchement peuvent aider les acheteurs à :

* **Etend la portée de l&#39;audience :** Un chevauchement faible suggère que vos caractéristiques contiennent des utilisateurs que l&#39;acheteur n&#39;a pas consultés auparavant. Par conséquent, les acheteurs peuvent souhaiter que ces caractéristiques ajoutent de nouveaux utilisateurs à leurs segments d&#39;audience.
* **Améliorer les audiences existantes :** Un chevauchement élevé suggère que vos caractéristiques contiennent des utilisateurs similaires à ceux qu&#39;un acheteur connaît déjà. Par conséquent, les acheteurs peuvent souhaiter obtenir ces caractéristiques afin d&#39;apporter des améliorations incrémentielles ciblées aux audiences développées.

Ce cas d&#39;utilisation se présente comme suit :

* Unité de mesure : Frais forfaitaires
* Prix : Gratuit (0,00 €)

### Modélisation

A **[!UICONTROL Modeling]** use case creates a plan that lets buyers compare your traits to theirs with [algorithmic modeling](../../../features/algorithmic-models/understanding-models.md#understanding-models). Les acheteurs examinent les résultats du modèle pour rechercher de nouvelles audiences dans vos données qui partagent des attributs de conversion similaires. Ce cas d&#39;utilisation se présente comme suit :

* Unité de mesure : Frais forfaitaires
* Prix : Prix préférentiel ou prix de marché

### Activation

An **[!UICONTROL Activation]** use case lets buyers send data to a [destination](../../../features/destinations/destinations.md). Dans ce cas, les acheteurs ne peuvent pas comparer les données à un rapport de chevauchement ou à un modèle algorithmique. Ce cas d&#39;utilisation se présente comme suit :

* Unit of Measure: [!DNL CPM]
* Price: [!DNL CPM] market rate

## Billing and Price Options {#billing}

Les options de facturation et de prix contrôlent comment les acheteurs paient pour vos données.

<table id="table_CCEAAF24295942EA82F20753827D1A23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option </th> 
   <th colname="col2" class="entry"> Description </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Cycle de facturation</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> La valeur mensuelle dans les retards</span></b> est la seule option possible. Le cycle de facturation se termine le 10 e jour de chaque mois. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Unité de mesure</span></b> </td> 
   <td colname="col2">Facturez les acheteurs de données à un taux CPM ou à des frais fixes. 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> Avec le tarif CPM, les acheteurs de données sont tenus d'auto-rapporter l'utilisation. </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">Avec un tarif forfaitaire, les acheteurs de données ne génèrent pas de rapport, car un taux fixe leur est facturé. </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Prix</span></b> </td>
   <td colname="col2"> Montant payé par un vendeur au prix du CPM ou du prix forfaitaire, en dollars. </td>
  </tr> 
 </tbody> 
</table>

## Plan Notes {#plan-notes}

In the **[!UICONTROL Additional Notes]** field, take some time to describe each data plan in a feed. Une brève description permet aux acheteurs de comprendre le contenu ou l&#39;objectif de chaque plan dans un flux de données. Les acheteurs peuvent lire les flux de données et les descriptions lorsqu&#39;ils recherchent ou évaluent de nouvelles sources de données.

## Manage Private Data Feed Requests {#manage-private-requests}

Processus Provider pour la gestion des demandes de flux privés auprès des acheteurs.

To review, approve, or reject buyer requests, go to [!UICONTROL My Shared Data] and:

<!-- t_private_feed_workflows.xml -->

1. Cliquez sur le nom du flux de données privées.
2. Click **[!UICONTROL Access Requests]** to review all the buyers who want access to your data feed.
3. In the [!UICONTROL Allow Access] section of each request box, click the check mark to approve a request or the X to deny access.
4. Confirmez ou annulez l&#39;action sélectionnée dans la fenêtre contextuelle de confirmation.

>[!MORE_ LIKE_ THIS]
>
>* [Flux de données privés](../../../features/audience-marketplace/marketplace-private-feeds.md)


## Discounts for Data Providers {#discounts}

In [!UICONTROL Audience Marketplace], discounts let you reduce the published price of a data feed for individual subscribers. Vous pouvez proposer des remises aux abonnés qui ont soumis une demande d&#39;abonnement ou aux abonnés qui ont demandé des informations sur un flux de données. Discounts apply to [!DNL CPM] and flat rate feeds. Les remises peuvent s&#39;avérer utiles pour offrir des avantages d&#39;abonnement aux nouveaux clients ou pour récompenser la fidélité des clients.

## Apply Discounts to a Data Feed {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

Pour réduire un flux, ajoutez un montant de remise comme % au champ de remise et confirmez vos modifications. Data providers can discount a data feeds in [!UICONTROL Audience Marketplace] from either:

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

In these examples, the seller has added 10% discount to the [!UICONTROL Software Audience] data feed.

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Review Discounted Feeds {#review-discounted-feeds}

Data providers can see all of their subscribers and discounted feeds in **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)