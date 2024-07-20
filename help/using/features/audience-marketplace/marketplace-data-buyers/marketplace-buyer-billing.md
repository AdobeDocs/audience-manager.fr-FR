---
description: Les acheteurs de données d’Audience Marketplace s’engagent à signaler toutes les impressions publicitaires diffusées à l’aide des caractéristiques contenues dans le flux de données dont le prix est calculé sur la base du coût par millier d’impressions publicitaires (CPM). L’utilisation du CPM est prévue le 5e jour de chaque mois calendaire et inclut des données pour le mois précédent. Les abonnés à des frais plats n’ont pas besoin de signaler l’utilisation.
seo-description: Audience Marketplace data buyers agree to report all ad impressions served using traits contained in the data feed priced on a cost per thousand ad impressions (CPM) basis. CPM usage is due on the 5th day of each calendar month and includes data for previous month. Flat fee subscribers do not need to report usage.
seo-title: Billing for Data Feed Buyers
solution: Audience Manager
title: Facturation pour les acheteurs de flux de données
keywords: Création de rapports au niveau du segment, au niveau du segment, au niveau du segment
uuid: d7236667-282b-4160-9909-579721af4016
feature: Audience Marketplace
exl-id: 401cf3be-fa84-4654-936e-e2871fef0be9
source-git-commit: 88ed0b28fdf5dc03c8a878529d65b4bc844ea6c9
workflow-type: tm+mt
source-wordcount: '2029'
ht-degree: 0%

---

# Facturation pour les acheteurs de flux de données {#billing-for-data-feed-buyers}

Les acheteurs de données d’Audience Marketplace acceptent de signaler toutes les impressions publicitaires diffusées à l’aide des caractéristiques contenues dans le flux de données dont le prix est calculé sur la base du coût par millier d’impressions publicitaires ([!DNL CPM]). L’utilisation de [!DNL CPM] doit avoir lieu le 5e jour de chaque mois calendaire et inclut des données pour le mois précédent. Les abonnés à des frais plats n’ont pas besoin de signaler l’utilisation.

<br> 

## Comment signaler l’utilisation du CPM {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] acheteurs de données acceptent de signaler toutes les impressions publicitaires diffusées à l’aide des caractéristiques contenues dans le prix du flux de données sur une base de coût par millier d’impressions publicitaires ([!DNL CPM]). L’utilisation de [!DNL CPM] doit avoir lieu le 5 jour de chaque mois calendaire et inclut des données pour le mois précédent. Les abonnés à des frais plats n’ont pas besoin de signaler l’utilisation.

[!UICONTROL Audience Marketplace] offre deux manières de signaler l&#39;utilisation de [!DNL CPM] :

* **Création de rapports au niveau du segment** : il s’agit de la méthode de création de rapports d’utilisation recommandée [!DNL CPM]. Lorsque vous signalez l’utilisation de [!DNL CPM] au niveau du segment, la section de création de rapports au niveau du flux de données est automatiquement remplie avec les montants d’utilisation correspondants, en fonction des algorithmes décrits dans la section [Attribution des coûts pour les flux de données CPM](#cost-attribution).
* **Création de rapports au niveau du flux de données** : cette méthode nécessite que vous signaliez individuellement l’utilisation de [!DNL CPM] pour chaque flux de données, en fonction des algorithmes décrits dans la section [Attribution des coûts pour les flux de données CPM](#cost-attribution). Toutefois, cette méthode est plus fastidieuse et susceptible aux erreurs que les rapports au niveau du segment.

<br> 

## Rapport sur l’utilisation du CPM au niveau du segment {#segment-level-report}

L’onglet [!UICONTROL Segment Usage] vous permet de créer des rapports sur l’utilisation au niveau du segment, tout en affichant les segments regroupés par destinations auxquelles ils sont mappés.

Après l’utilisation de [!DNL CPM] au niveau du segment, [!UICONTROL Audience Marketplace] affecte automatiquement l’utilisation correcte des flux de données correspondants, en fonction de l’ [ attribution de coûts pour les flux de données CPM](#cost-attribution).

Pour signaler l’utilisation de [!DNL CPM] au niveau du segment :

1. Accédez à **[!UICONTROL Audience Marketplace > Payables]**.
1. Sélectionnez l’onglet **[!UICONTROL Segment Usage]** .
1. Renseignez l’utilisation de vos segments. Vous pouvez utiliser la zone [!UICONTROL Search] pour filtrer les segments si vous n’avez besoin de créer des rapports d’utilisation que pour certains d’entre eux.
1. Cliquez sur **[!UICONTROL Edit Segments Usage]**.
1. Saisissez le montant d&#39;utilisation [!DNL CPM] dans la colonne [!UICONTROL Usage].
1. Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé et passez en revue la boîte de dialogue de confirmation.

   ![confirm-segment-usage](assets/confirm-segment-usage.png)

1. Cliquez sur **[!UICONTROL Confirm]**.

Visionnez également notre démonstration vidéo montrant comment vous pouvez créer des rapports sur l’utilisation au niveau du segment :

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## Rapport sur l’utilisation du CPM au niveau du flux de données {#feed-level-report}

La création de rapports au niveau du flux de données est un processus plus fastidieux et susceptible aux erreurs, puisque vous devez calculer individuellement l’utilisation de [!DNL CPM] pour chaque flux de données. Nous vous recommandons plutôt de [Signaler l’utilisation du CPM au niveau du segment](#segment-level-report).

Pour signaler l’utilisation de [!DNL CPM] au niveau du segment :

1. Accédez à **[!UICONTROL Audience Marketplace > Payables]**.
2. Sélectionnez l’onglet **[!UICONTROL Feed Usage]** .
3. Utilisez la zone [!UICONTROL Search] pour filtrer les flux de données et identifier ceux pour lesquels vous devez générer des rapports d’utilisation.
4. Cliquez sur **[!UICONTROL Edit Feeds Usage]**.
5. Calculez l’utilisation de [!DNL CPM] pour chaque flux de données en fonction de l’ [attribution de coûts pour les flux de données CPM](#cost-attribution) et saisissez-le dans la colonne [!UICONTROL Usage].
6. Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé et passez en revue la boîte de dialogue de confirmation.

   ![confirm-feed-usage](assets/confirm-feed-usage.png)

7. Cliquez sur **[!UICONTROL Confirm]**.

<br> 

## Création de rapports en bloc

Pour réduire les erreurs et la surcharge lors de l&#39;utilisation de [!DNL CPM] dans les rapports, vous pouvez utiliser l&#39;option de création de rapports en bloc pour télécharger un fichier [!DNL CSV] contenant les flux de données et les segments, remplir l&#39;utilisation et la télécharger à nouveau vers [!DNL Audience Manager]. Vous pouvez utiliser les rapports en bloc pour signaler l’utilisation des flux et des segments.

Pour mettre à jour l&#39;utilisation de [!DNL CPM] en masse :

1. Accédez à **[!UICONTROL Audience Marketplace > Payables]**.
1. Sélectionnez l’onglet **[!UICONTROL Feed Usage]** ou **[!UICONTROL Segment Usage]** en fonction du type de rapport à mettre à jour.
1. Cliquez sur **[!UICONTROL Edit Feeds Usage]** ou **[!UICONTROL Edit Segments Usage]**.
1. Cliquez sur **[!UICONTROL download the current usage]** pour vous assurer d’utiliser un fichier CSV valide.
1. Ouvrez le fichier sur votre ordinateur et renseignez le rapport d’utilisation.
1. Cliquez sur **[!UICONTROL Choose a CSV file]** pour télécharger le rapport d’utilisation mis à jour.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] valide le fichier dès que vous l’avez téléchargé et vous invite à le vérifier s’il détecte des erreurs dans le fichier.

<br> 

### Erreurs de validation des rapports en bloc

| Message d’erreur | Description | Correction de l’affichage inapproprié comme titre de la valeur |
| ------------- | -------------| -----|
| Entrée non valide | [!DNL Audience Manager] a détecté une modification dans le schéma de fichier [!DNL CSV], telle que des colonnes manquantes ou des modifications du titre des colonnes. | Évitez de modifier la structure du tableau. |
| introuvables | Pour [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] n&#39;a pas pu identifier la combinaison [!UICONTROL Segment ID] et [!UICONTROL Destination ID]. Pour [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] n&#39;a pas pu identifier la combinaison [!UICONTROL Data Provider Name], [!UICONTROL Feed Name] et [!UICONTROL Use Case]. | Pour [!UICONTROL Segment Level Reporting], vérifiez la validité de la combinaison [!UICONTROL Segment ID] et [!UICONTROL Destination ID]. Pour [!UICONTROL Feed Level Reporting], vérifiez la validité de la combinaison [!UICONTROL Data Provider Name], [!UICONTROL Feed Name] et [!UICONTROL Use Case]. |
| Duplication d’enregistrements trouvés | [!DNL Audience Manager] a détecté des enregistrements en double avec des valeurs d’impression différentes. | Consultez le rapport et assurez-vous de ne pas signaler des valeurs d’utilisation différentes pour le même flux de données ou segment. |
| Valeurs non prises en charge | [!DNL Audience Manager] a détecté des valeurs non numériques dans la colonne [!DNL Audience Manager]. | Consultez le rapport et veillez à n’entrer que des valeurs numériques dans la colonne [!DNL Audience Manager]. |
| En-têtes des champs obligatoires manquants | [!DNL Audience Manager] a détecté des en-têtes de table manquants pour les champs obligatoires. Pour [!UICONTROL Segment Level Reporting], les champs obligatoires sont : [!UICONTROL Segment ID], [!UICONTROL Destination ID]. Pour [!UICONTROL Feed Level Reporting], les champs obligatoires sont : [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name], [!UICONTROL Use Case] | Consultez le rapport et assurez-vous que les en-têtes de tableau n’ont pas été modifiés. |

>[!NOTE]
>La suppression des lignes du rapport d’utilisation [!DNL CSV] n’a aucun effet sur le rapport d’utilisation existant. [!DNL Audience Manager] traite uniquement les champs inclus dans le rapport.

<br> 

## [!DNL CPM] Bonnes pratiques de création de rapports

<table id="table_E68FA2130D1C495FAB8982DFB6A31FD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recommandations </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Toujours signaler le nombre total d'impressions</b> </p> </td> 
   <td colname="col2"> <p>Pour les totaux d’impression CPM : </p>
   <p> Signalez le nombre total d’impressions, sans utiliser de décimales. L’Audience Manager calcule automatiquement le CPM en fonction du nombre total que vous signalez.</p><p>Si vous devez signaler 1 234 567 impressions, signalez-le exactement comme cela. Il n’est pas nécessaire de diviser le nombre total d’impressions par 1 000 pour calculer le CPM.</p><p>Les caractéristiques utilisées pour optimiser le contenu web ou d’application (optimisation du contenu) à l’aide d’outils tels qu’Adobe Target ou une destination Analytics ne contribuent pas aux totaux d’utilisation pour les plans CPM. Les fournisseurs de données sont généralement rémunérés pour l’optimisation de contenu au moyen de forfaits.</p><p>Voir <a href="#cost-attribution">Attribution des coûts pour les flux de données CPM</a> pour plus d’informations. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>S’accrocher à l’intervalle de rapports mensuel</b> </p> </td> 
   <td colname="col2"> <p>Le système de rapports se ferme après le 5 de chaque mois. Si vous ne signalez pas l’utilisation du CPM d’ici là, vous devez ajouter ce montant au rapport pour le mois suivant. Supposons, par exemple, que vous utilisiez 1 000 impressions en octobre, que vous manquiez la date limite de création des rapports d’octobre et que vous utilisiez 1 000 impressions en novembre. Dans ce cas, vous signalez le total d’octobre et de novembre (2000) en décembre, entre le 1er et le 5.</p><p><b>Conseil</b> : vous devez toujours essayer de signaler l’utilisation du CPM pour le mois précédent entre le 1er et le 5e jour du mois suivant.</p><p>Vous pouvez signaler l’utilisation du CPM jusqu’au 5 du nouveau mois calendaire, mais cela n’est pas recommandé. L’utilisation du CPM dans les rapports avant le 5 de chaque mois donne à l’Audience Manager le temps de vérifier et de traiter les données.</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## Attribution des coûts pour les flux de données CPM {#cost-attribution}

Dans [!UICONTROL Audience Marketplace], vous devez générer un rapport automatique des montants d’impression chaque mois, pour chacun de vos segments. Nous recommandons l’utilisation de la fonction de création de rapports [!DNL CPM] au niveau du segment, de sorte que l’attribution des coûts soit faite automatiquement.

<!-- marketplace_cpm_billing.xml -->

### Résumé de la facturation {#billing-summary}

Vous devez envoyer les [!DNL CPM] montants d’impression des flux de données entre le 1er et le 5e jour de chaque mois calendaire. Pour ce faire correctement, nous vous recommandons de [signaler l’utilisation du CPM au niveau du segment](#segment-level-report).

>[!TIP]
>Lorsque vous signalez l’utilisation de [!DNL CPM] au niveau du segment, la section de rapport au niveau du flux de données est automatiquement renseignée avec les quantités d’utilisation correspondantes.

Si vous devez [!UICONTROL Report CPM Usage at Data Feed Level], vous devez compiler individuellement toutes les impressions diffusées pour chaque flux du mois civil précédent et les reporter en fonction de l’allocation de facturation décrite dans cet article.

Une fois que vous aurez reporté le numéro [!DNL CPM] du mois civil précédent, [!DNL Adobe] effectuera les opérations suivantes :

* Créez une facture et facturez-vous selon le taux [!DNL CPM] de chaque flux de données abonné.
* Paiement des frais dus aux fournisseurs de données (vendeurs) en fonction de votre utilisation de [!DNL CPM] signalée.

>[!IMPORTANT]
>
>En tant qu’acheteur, tous les totaux d’impression signalés doivent être vrais et précis. Si vous ne signalez pas les totaux d’impression avant le 5e jour de chaque mois, vous devez inclure les totaux du mois non signalé dans le mois suivant.

<br> 

## Attribution d’impressions au niveau du flux en fonction des règles de qualification des caractéristiques {#assign-impressions}

Le cas d’utilisation [!UICONTROL Activation] vous permet d’utiliser des caractéristiques dans le flux de données correspondant pour créer des segments dans le [créateur de segments](../../../features/segments/segment-builder.md) et mapper ces segments à une destination. Les opérateurs booléens [!UICONTROL AND], [!UICONTROL OR] et [!UICONTROL NOT] vous permettent de définir les conditions de qualification des caractéristiques et des segments.

Lorsque vous [signalez l’utilisation du CPM au niveau du flux de données](#feed-level-report), vous devez affecter les impressions proportionnellement à chaque flux de données, en fonction des opérateurs [!DNL Boolean] utilisés dans les règles de qualification des caractéristiques. Le tableau suivant répertorie comment affecter correctement les impressions par règle booléenne ou type de caractéristique.

>[!TIP]
>[Signaler l’utilisation du CPM au niveau du segment](#segment-level-report) pour que les rapports au niveau du flux de données soient automatiquement effectués par Audience Manager.

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Logique ou type de qualification de règle </th> 
   <th colname="col2" class="entry"> Distribution de facturation </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ET</span> </p> </td> 
   <td colname="col2"> <p>Appliquez 100 % des totaux d’impression délivrés à toutes les caractéristiques du fournisseur dans un segment basé sur des règles qui utilise une condition booléenne <span class="wintitle"> ET</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> OU</span> </p> </td> 
   <td colname="col2"> <p>Appliquez une attribution pondérée des totaux des impressions délivrées à toutes les caractéristiques du fournisseur dans un segment basé sur des règles qui utilise une condition OU booléenne. L'allocation pondérée est calculée à l'aide de la formule suivante :</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>Appliquez 100 % des totaux d’impression délivrés à toutes les caractéristiques du fournisseur dans un segment basé sur des règles qui utilise une condition booléenne <span class="wintitle"> NOT</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segments algorithmiques </p> </td> 
   <td colname="col2"> <p>Appliquez 100 % des totaux d’impression délivrés à tous les flux du fournisseur dans un segment contenant des caractéristiques algorithmiques. </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## Exemples de facturation {#billing-examples}

Les exemples ci-dessous ont pour but d’illustrer la manière dont l’affectation de l’utilisation de [!DNL CPM] est effectuée au niveau du flux de données.

>[!IMPORTANT]
>Nous vous recommandons plutôt de [Signaler l’utilisation du CPM au niveau du segment](#segment-level-report) pour que ce processus soit effectué automatiquement.

Examinons le scénario suivant :

![billing-examples](assets/billing-examples.png)

<br> 

### Cas 1 : segments contenant des règles de qualification ET

Ce segment contient 3 caractéristiques provenant de fournisseurs de données distincts. La qualification du segment étant basée sur une condition [!UICONTROL AND], les visiteurs doivent réaliser les caractéristiques des trois flux pour être admissibles au segment.

![](assets/billing-segment-and.png)

Avec une condition [!UICONTROL AND], vous devez affecter 100 % des impressions reçues au cours du mois aux trois fournisseurs de données. Dans la section [!UICONTROL Audience Marketplace > Payables], vous attribuez à chaque fournisseur 1 000 000 impressions.

Cet exemple s’applique aux segments qui utilisent des opérateurs [!DNL Boolean] [!UICONTROL NOT] ou aux segments qui contiennent des caractéristiques algorithmiques.

<br> 

### Cas 2 : Segments Avec Des Règles De Qualification OU

Ce segment contient 3 caractéristiques provenant de fournisseurs de données distincts. La qualification du segment étant basée sur une condition [!UICONTROL OR], les visiteurs doivent réaliser au moins l’une des trois caractéristiques pour être admissibles au segment.

Nous ne pouvons pas déterminer quelle caractéristique est responsable d’une impression, car la qualification est basée sur une condition [!UICONTROL OR]. Par conséquent, dans la section [!UICONTROL Audience Marketplace > Payables], vous attribuez à chaque fournisseur une allocation pondérée du total des impressions, en fonction de la population de caractéristiques.

![billing-segment-or](assets/billing-segment-or.png)

<br> 

### Cas 3 : segments avec des cas d’utilisation de modélisation et d’activation

Cet exemple décrit l’attribution en fonction de deux cas d’utilisation de flux de données : Modélisation et Activation. Dans cet exemple, nous examinons deux fournisseurs de données, avec les informations suivantes :

![data-feed](assets/feed-use-cases.png)

Dans le tableau ci-dessous, le segment X contient deux caractéristiques, T1 et T2, avec la règle de segment T1 OU T2, où :

* T1 est une caractéristique du flux de données A ;
* T2 est une caractéristique algorithmique modélisée selon des caractéristiques tierces du flux de données A et du flux de données B.

Le segment est mappé à une destination et 1 000 000 impressions sont entrées pour ce segment en un mois, à l’aide de la création de [rapports au niveau du segment](#segment-level-report).

Parmi ces 1 000 000 impressions :

* T1 représente 40 % de la population du segment, ce qui se traduit par 400 000 impressions pour le flux A.
* T2 représente 60 % de la population du segment, ce qui se traduit par 600 000 impressions pour le flux A et le flux B.

Au niveau du flux de données, la façon dont les impressions sont attribuées est la suivante :

* Le flux de données A reçoit 600 000 impressions de la caractéristique T2 (qui est modelée sur les caractéristiques du flux de données A et du flux de données B, qui reçoivent donc toutes deux les impressions) et 400 000 impressions de la caractéristique T1 (qui est une caractéristique du flux de données A), totalisant 1 000 00 impressions.
* Le flux de données B reçoit 600 000 impressions de la caractéristique T2 (voir l’explication ci-dessus) et 0 impressions de la caractéristique T1.

La ventilation en un coup d’oeil par flux de données et cas d’utilisation est la suivante :

![feed-ventilation](assets/feed-breakdown-alt.png)

>[!NOTE]
>
>Pour le cas d’utilisation de la modélisation, vous devez uniquement signaler l’utilisation du CPM lors de l’activation. Si vous exécutez uniquement un modèle, mais ne l’activez pas, aucun rapport d’utilisation n’est requis.

<br> 

## Affectation de facturation et d’impressions pour les flux de données de flux plats {#billing-flat-fee}

Un flux de données à frais fixes vous facture un montant fixe chaque mois, quel que soit le moment où l’abonnement commence ou le nombre d’impressions que vous utilisez. Les frais ne sont pas répartis au niveau de l’utilisation ou des intervalles mensuels partiels. Comme pour la facturation CPM, Adobe génère une facture et vous facture au tarif mensuel forfaitaire pour vos flux de données abonnés.

Par exemple, supposons que vous ayez décidé d’activer certaines caractéristiques dans un flux au milieu du mois. Vous serez toujours facturé au tarif mensuel complet, quelle que soit la date de démarrage de l’abonnement ou l’activation de caractéristiques spécifiques.
