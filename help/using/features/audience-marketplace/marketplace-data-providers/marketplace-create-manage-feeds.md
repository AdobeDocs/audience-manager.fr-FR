---
description: Un flux de données nécessite un nom, une description, une source de données et un type de plan. Les flux sont désactivés jusqu’à ce que vous les enregistriez et les activiez. Configurez des flux de données publics ou privés dans Audience Marketplace > Mes données partagées. Disponible uniquement pour les vendeurs de données.
seo-description: A data feed requires a name, description, data source, and a plan type. Feeds are disabled until you save and activate the feed. Set up public or private data feeds in Audience Marketplace > My Shared Data. Available to data sellers only.
seo-title: Create, Price, and Manage Data Feeds
solution: Audience Manager
title: Création, tarification et gestion des flux de données
uuid: e28c20b3-33fc-4485-8ee9-8530d126f741
feature: Audience Marketplace
exl-id: e8605e94-e62a-430c-9aef-875f995fb436
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1260'
ht-degree: 1%

---

# Création, tarification et gestion des flux de données {#create-price-and-manage-data-feeds}

## Créer un flux de données public ou privé {#create-public-private-data-feed}

Un flux de données nécessite un nom, une description, une source de données et un type de plan. Les flux sont désactivés jusqu’à ce que vous les enregistriez et les activiez. Configurez les flux de données publics ou privés dans **[!UICONTROL Audience Marketplace > My Shared Data]**. Disponible uniquement pour les vendeurs de données.

<!-- t_data_feed.xml -->

Vous devez disposer de droits d’administrateur pour créer un flux de données public ou privé.
Pour créer un flux de données :

1. Cliquez sur **[!UICONTROL New Data Feed]**.
1. Nommez le flux de données. Les acheteurs de données peuvent rechercher votre flux en fonction de son nom.
1. Fournissez une brève description (255 caractères maximum).

   Une bonne description doit décrire votre flux avec précision. Par exemple, vous pouvez inclure du texte pour les catégories marketing, les données démographiques et la couverture géographique (par exemple, [!DNL US] ou Amérique du Nord). Le texte descriptif est consultable et aide les acheteurs à trouver ou à évaluer votre flux. Une bonne description est importante pour attirer les abonnés à votre flux de données.
1. Sélectionnez une source de données parmi les options de **[!UICONTROL Data Source]**. Les flux de données sont limités à une seule source de données. Vous ne pouvez pas affecter plusieurs sources de données au même flux de données.

   >[!IMPORTANT]
   >
   >Toutes les caractéristiques actuelles et futures appartenant à cette source de données seront partagées avec vos acheteurs de données, dans le cadre de ce flux.

1. Dans [!UICONTROL Plan Types], sélectionnez les options que vous souhaitez utiliser, puis cliquez sur **[!UICONTROL Add Plan]**.

   Les flux peuvent contenir plusieurs plans. Les plans peuvent contenir plusieurs cas d’utilisation. Pour plus d’informations, consultez [Types de plan pour les flux de données](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types).

1. Cliquez sur **[!UICONTROL Save]** pour enregistrer votre flux de données *sans* l’activer.
1. Pour enregistrer et activer un flux de données :
   1. Déplacez le curseur **[!UICONTROL Availability]** vers **[!UICONTROL Active]**.
   1. Cliquez sur **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >* Les flux de données enregistrés et activés ne peuvent pas être supprimés.
   >* Les acheteurs ne voient que les flux actifs.

### Facultatif : Créer un flux de données privé

Dans la section [!UICONTROL Settings], déplacez le curseur sur :

* **[!UICONTROL Private]** et **[!UICONTROL Branded]** : la liste des [!UICONTROL Marketplace] de l&#39;acheteur affiche le nom du vendeur dans la colonne fournisseur et toutes les autres données sont masquées.

* **[!UICONTROL Private]** et **[!UICONTROL Unbranded]** : la liste des [!UICONTROL Marketplace] de l&#39;acheteur affiche uniquement le nom et la description du flux de données. Le nom du fournisseur de données s’affiche sous la forme [!UICONTROL Private Seller].

Pour voir à quoi ressemble un flux privé pour les acheteurs, consultez la section acheteurs dans [Flux de données privées](../../../features/audience-marketplace/marketplace-private-feeds.md).

## Désactivation du flux de données d’un abonné {#deactivate-data-feed}

En tant que fournisseur de données [!UICONTROL Audience Marketplace], vous pouvez révoquer l’accès des acheteurs à un flux de données auquel ils sont abonnés. Vous pouvez supprimer un acheteur d&#39;un aliment pour des raisons telles que le paiement tardif ou le non-paiement des frais ou s&#39;il utilise les données sur les caractéristiques de façon incorrecte.

<!-- marketplace-deactiva4te-subscribers.xml -->

Pour révoquer un abonné :

1. Dans [!UICONTROL My Shared Data], recherchez le flux que l’abonné utilise.

   >[!NOTE]
   >
   >Les flux de données avec comptes en retard sont marqués d’une icône en forme de triangle ou de point d’exclamation.

1. Dans la colonne [!UICONTROL Subscribers] , cliquez sur le nombre bleu qui comptabilise les abonnés à ce flux. La page Détails de l’abonnement s’ouvre alors.
1. Déplacez le curseur **[!UICONTROL Subscription]** vers **[!UICONTROL Off]**. Une boîte de dialogue de confirmation s’ouvre alors.
1. Dans la fenêtre contextuelle de [!UICONTROL Confirmation], cliquez sur **[!UICONTROL Yes]** pour désactiver un abonnement ou **[!UICONTROL Cancel]** pour quitter sans modifier l’abonnement.

### Conséquences de la désactivation d’un abonné

La révocation de l’accès à un flux de données envoie un e-mail de notification à tous les utilisateurs administrateurs du compte de l’acheteur de données. L’e-mail comprend une pièce jointe qui répertorie les caractéristiques révoquées. Cette liste permet aux abonnés de rechercher et de supprimer des caractéristiques désactivées de leurs segments et modèles.

### Désactivation de la facturation et du flux

Après avoir supprimé l’accès à un flux de données, les abonnés et abonnées sont responsables des frais pour le mois précédent ou le mois en cours, selon le moment où vous avez désactivé le flux.

## Types de plan pour les flux de données {#plan-types}

[!DNL Plan types] sont des composants essentiels dans un flux de données [!UICONTROL Audience Marketplace]. En tant que fournisseur de données, ils vous permettent de créer plusieurs cas d’utilisation et options de prix pour vos flux. En outre, il peut être judicieux de créer quelques plans pour chaque flux de données. Cela donne aux acheteurs différentes options parmi lesquelles choisir lorsqu’ils recherchent des données à modéliser ou à envoyer à une destination.

[Créez un flux de données](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) pour sélectionner des [!UICONTROL Plan Types].

![](assets/plan_types.png)

## Types de plan et options de cas d’utilisation {#plan-types-use-cases}

<!-- c_feed_options.xml -->

Les paramètres [!UICONTROL Use Case] permettent aux vendeurs de contrôler la manière dont les acheteurs peuvent utiliser vos données.

### Segments et chevauchement

Un cas d’utilisation **[!UICONTROL Segments and Overlap]** crée un plan qui permet aux acheteurs de comparer les données des caractéristiques dans un [ rapport de chevauchement des caractéristiques](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report). De plus, les acheteurs peuvent ajouter vos données aux segments et effectuer des comparaisons avec les rapports [segment à caractéristique](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) et [segment à segment](../../../reporting/dynamic-reports/segment-segment-overlap-report.md).

Chaque flux de données doit inclure au moins un cas d’utilisation [!UICONTROL Segments and Overlap]. Les acheteurs ne peuvent pas s’abonner à d’autres plans dans un flux de données si le flux ne contient pas de cas d’utilisation [!UICONTROL Segments and Overlap], seul ou en combinaison avec un autre cas d’utilisation.

Les comparaisons de chevauchements peuvent aider les acheteurs à :

* **Étendre la portée de l’audience :** un chevauchement faible suggère que vos caractéristiques contiennent des utilisateurs que l’acheteur n’a pas encore vus. Par conséquent, les acheteurs peuvent souhaiter que ces caractéristiques ajoutent de nouveaux utilisateurs à leurs segments d’audience.
* **Améliorer les audiences existantes :** un chevauchement élevé suggère que vos caractéristiques contiennent des utilisateurs similaires à ceux qu’un acheteur connaît déjà. Par conséquent, les acheteurs peuvent souhaiter que ces caractéristiques aident à apporter des améliorations ciblées et progressives aux audiences développées.

Tarifiez ce cas d’utilisation comme suit :

* Unité de mesure : Frais forfaitaires
* Prix : Gratuit (0,00 $)

### Modélisation

Un cas d’utilisation **[!UICONTROL Modeling]** crée un plan qui permet aux acheteurs de comparer vos caractéristiques aux leurs avec la [modélisation algorithmique](../../../features/algorithmic-models/understanding-models.md#understanding-models). Les acheteurs examinent les résultats du modèle pour trouver de nouvelles audiences dans vos données qui partagent des attributs de conversion similaires aux leurs. Tarifiez ce cas d’utilisation comme suit :

* Unité de mesure : Frais forfaitaires
* Prix : Prix réduit ou au taux du marché

### Activation

Un cas d’utilisation **[!UICONTROL Activation]** permet aux acheteurs d’envoyer des données vers une [destination](../../../features/destinations/destinations.md). Avec ce cas d’utilisation, les acheteurs ne peuvent pas comparer les données avec un rapport de chevauchement ou dans un modèle algorithmique. Tarifiez ce cas d’utilisation comme suit :

* Unité de mesure : [!DNL CPM]
* Prix : [!DNL CPM] taux du marché

## Options de facturation et de prix {#billing}

Les options de facturation et de prix contrôlent la façon dont les acheteurs paient pour vos données.

<table id="table_CCEAAF24295942EA82F20753827D1A23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option </th> 
   <th colname="col2" class="entry"> Description </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> cycle de facturation</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Mensuel en Arriérés</span></b> est la seule option. Le cycle de facturation se termine le 10 de chaque mois. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> unité de mesure</span></b> </td> 
   <td colname="col2">Facturer les acheteurs de données à un taux CPM ou à un tarif forfaitaire. 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> Avec la tarification CPM, les acheteurs de données sont tenus de générer des rapports d’utilisation. </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">Avec la tarification forfaitaire, les acheteurs de données ne signalent pas l'utilisation parce qu'ils sont facturés à un taux fixe. </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Price </span></b> </td>
   <td colname="col2"> Montant facturé par le vendeur à l'acheteur sous la forme d'un taux CPM ou d'un prix forfaitaire, en dollars. </td>
  </tr> 
 </tbody> 
</table>

## Remarques sur le plan {#plan-notes}

Dans le champ **[!UICONTROL Additional Notes]** , prenez le temps de décrire chaque plan de données dans un flux. Une bonne description brève aide les acheteurs à comprendre le contenu ou l’objectif de chaque plan dans un flux de données. Les acheteurs peuvent lire les descriptions des flux de données et des plans lorsqu’ils recherchent ou évaluent de nouvelles sources de données.

## Gérer les demandes de flux de données privées {#manage-private-requests}

Workflows de fournisseur pour la gestion des demandes de flux privées des acheteurs.

Pour examiner, approuver ou rejeter les demandes des acheteurs, accédez à [!UICONTROL My Shared Data] et à :

<!-- t_private_feed_workflows.xml -->

1. Cliquez sur le nom du flux de données privé.
2. Cliquez sur **[!UICONTROL Access Requests]** pour consulter tous les acheteurs qui souhaitent accéder à votre flux de données.
3. Dans la section [!UICONTROL Allow Access] de chaque demande, cochez la case pour approuver une demande ou le X pour refuser l’accès.
4. Confirmez ou annulez l’action sélectionnée dans la fenêtre contextuelle de confirmation.

## Remises pour les fournisseurs de données {#discounts}

En [!UICONTROL Audience Marketplace], les remises vous permettent de réduire le prix publié d’un flux de données pour les abonnés individuels. Vous pouvez offrir des remises aux abonnés qui ont soumis une demande d’abonnement ou aux abonnés qui ont demandé des détails sur un flux de données. Des remises s’appliquent aux flux [!DNL CPM] et à tarif fixe. Les remises peuvent s’avérer utiles si vous souhaitez proposer des incentives pour les abonnements à de nouveaux clients ou pour récompenser la fidélité des clients.

## Appliquer des remises à un flux de données {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

Pour réduire un flux, ajoutez un montant de réduction en % au champ de réduction et confirmez vos modifications. Les fournisseurs de données peuvent réduire un flux de données dans [!UICONTROL Audience Marketplace] de :

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

Dans ces exemples, le vendeur a ajouté une remise de 10 % au flux de données [!UICONTROL Software Audience].

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Consulter les flux à prix réduit {#review-discounted-feeds}

Les fournisseurs de données peuvent voir tous leurs abonnés et les flux à prix réduit en **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)

>[!MORELIKETHIS]
>
>* [Flux de données privés](../../../features/audience-marketplace/marketplace-private-feeds.md)
