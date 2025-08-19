---
description: Les acheteurs de données Audience Marketplace acceptent de signaler toutes les impressions d’annonce publicitaire diffusées à l’aide des caractéristiques contenues dans le flux de données tarifé au coût par millier d’impressions d’annonce (CPM). L’utilisation de CPM est due le 5e jour de chaque mois calendaire et inclut les données du mois précédent. Les abonnés au forfait n'ont pas besoin de signaler l'utilisation.
seo-description: Audience Marketplace data buyers agree to report all ad impressions served using traits contained in the data feed priced on a cost per thousand ad impressions (CPM) basis. CPM usage is due on the 5th day of each calendar month and includes data for previous month. Flat fee subscribers do not need to report usage.
seo-title: Billing for Data Feed Buyers
solution: Audience Manager
title: Facturation pour les acheteurs de flux de données
keywords: Rapports au niveau du segment, niveau du segment, niveau du segment
uuid: d7236667-282b-4160-9909-579721af4016
feature: Audience Marketplace
exl-id: 401cf3be-fa84-4654-936e-e2871fef0be9
source-git-commit: 88ed0b28fdf5dc03c8a878529d65b4bc844ea6c9
workflow-type: tm+mt
source-wordcount: '2029'
ht-degree: 0%

---

# Facturation pour les acheteurs de flux de données {#billing-for-data-feed-buyers}

Les acheteurs de données Audience Marketplace acceptent de signaler toutes les impressions d’annonce publicitaire diffusées à l’aide des caractéristiques contenues dans le flux de données tarifé sur la base du coût par millier d’impressions d’annonce ([!DNL CPM]). L’utilisation du [!DNL CPM] est due le 5e jour de chaque mois calendaire et inclut les données du mois précédent. Les abonnés au forfait n&#39;ont pas besoin de signaler l&#39;utilisation.

<br> 

## Comment générer des rapports sur l’utilisation de CPM {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] acheteurs de données acceptent de signaler toutes les impressions d’annonce publicitaire diffusées à l’aide des caractéristiques contenues dans le flux de données tarifé sur la base du coût par millier d’impressions d’annonce ([!DNL CPM]). L’utilisation du [!DNL CPM] est due le 5 jour de chaque mois calendaire et inclut les données du mois précédent. Les abonnés au forfait n&#39;ont pas besoin de signaler l&#39;utilisation.

[!UICONTROL Audience Marketplace] offre deux façons de générer des rapports sur l’utilisation des [!DNL CPM] :

* **Rapports au niveau du segment** : il s’agit de la méthode de rapport recommandée sur l’utilisation des [!DNL CPM]. Lorsque vous signalez l’utilisation des [!DNL CPM] au niveau du segment, la section de rapport au niveau des flux de données est automatiquement complétée avec les quantités d’utilisation correspondantes, en fonction des algorithmes décrits dans la section [Attribution des coûts pour les flux de données CPM](#cost-attribution).
* **Compte rendu des performances au niveau des flux de données** : cette méthode nécessite que vous rapportiez individuellement l’utilisation des [!DNL CPM] pour chaque flux de données, en fonction des algorithmes décrits dans [Attribution des coûts pour les flux de données CPM](#cost-attribution). Cependant, cette méthode est plus fastidieuse et sujette aux erreurs que le compte rendu des performances au niveau du segment.

<br> 

## Utilisation de Report CPM au niveau du segment {#segment-level-report}

L’onglet [!UICONTROL Segment Usage] vous permet de générer un rapport sur l’utilisation au niveau du segment, tout en affichant les segments regroupés par les destinations auxquelles ils sont mappés.

Après avoir signalé l’utilisation des [!DNL CPM] au niveau du segment, [!UICONTROL Audience Marketplace] attribue automatiquement les flux de données correspondants à l’utilisation correcte, en fonction de l’[Attribution des coûts pour les flux de données CPM](#cost-attribution).

Pour générer des rapports sur l’utilisation des [!DNL CPM] au niveau du segment :

1. Accédez à **[!UICONTROL Audience Marketplace > Payables]**.
1. Sélectionnez l’onglet **[!UICONTROL Segment Usage]** .
1. Renseignez l’utilisation de vos segments. Vous pouvez utiliser la zone de [!UICONTROL Search] pour filtrer les segments si vous n’avez besoin de créer des rapports que pour certains d’entre eux.
1. Cliquez sur **[!UICONTROL Edit Segments Usage]**.
1. Saisissez le montant d’utilisation du [!DNL CPM] dans la colonne [!UICONTROL Usage] .
1. Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé et passez en revue la boîte de dialogue de confirmation.

   ![confirmation-utilisation-segment](assets/confirm-segment-usage.png)

1. Cliquez sur **[!UICONTROL Confirm]**.

Regardez également notre vidéo de démonstration expliquant comment générer des rapports sur l’utilisation au niveau du segment :

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## Utilisation de Report CPM au niveau des flux de données {#feed-level-report}

Le compte rendu des performances au niveau des flux de données est un processus plus fastidieux et susceptible d’entraîner des erreurs, car vous devez calculer individuellement l’utilisation des [!DNL CPM] pour chaque flux de données. Nous vous recommandons de [Signaler l’utilisation de CPM au niveau du segment](#segment-level-report) à la place.

Pour générer des rapports sur l’utilisation des [!DNL CPM] au niveau du segment :

1. Accédez à **[!UICONTROL Audience Marketplace > Payables]**.
2. Sélectionnez l’onglet **[!UICONTROL Feed Usage]** .
3. Utilisez la zone de [!UICONTROL Search] pour filtrer les flux de données et identifier ceux pour lesquels vous devez créer des rapports d’utilisation.
4. Cliquez sur **[!UICONTROL Edit Feeds Usage]**.
5. Calculez l’utilisation des [!DNL CPM] pour chaque flux de données en fonction de l’[Attribution des coûts pour les flux de données CPM](#cost-attribution) et saisissez-la dans la colonne [!UICONTROL Usage].
6. Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé et passez en revue la boîte de dialogue de confirmation.

   ![confirm-feed-usage](assets/confirm-feed-usage.png)

7. Cliquez sur **[!UICONTROL Confirm]**.

<br> 

## Création de rapports en bloc

Pour réduire les erreurs et les frais généraux lors de la création de rapports sur l’utilisation des [!DNL CPM], vous pouvez utiliser l’option de création de rapports en bloc pour télécharger un fichier [!DNL CSV] contenant les flux de données et les segments, renseigner l’utilisation et la charger à nouveau dans [!DNL Audience Manager]. Vous pouvez utiliser les rapports en bloc pour signaler l’utilisation des flux et des segments.

Pour mettre à jour l’utilisation des [!DNL CPM] en bloc :

1. Accédez à **[!UICONTROL Audience Marketplace > Payables]**.
1. Sélectionnez l’onglet **[!UICONTROL Feed Usage]** ou **[!UICONTROL Segment Usage]** , selon le type de création de rapports que vous souhaitez mettre à jour.
1. Cliquez sur **[!UICONTROL Edit Feeds Usage]** ou **[!UICONTROL Edit Segments Usage]**.
1. Cliquez sur **[!UICONTROL download the current usage]** pour vous assurer d’utiliser un fichier CSV valide.
1. Ouvrez le fichier sur votre ordinateur et remplissez le rapport d’utilisation.
1. Cliquez sur **[!UICONTROL Choose a CSV file]** pour charger le rapport d’utilisation mis à jour.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] valide le fichier dès que vous le chargez et vous invite à vérifier s’il détecte des erreurs dans le fichier.

<br> 

### Erreurs de validation des rapports en bloc

| Message d’erreur | Description | Correction de l’affichage inapproprié comme titre de la valeur |
| ------------- | -------------| -----|
| Entrée non valide | [!DNL Audience Manager] a détecté une modification dans le schéma du fichier de [!DNL CSV], telle que des colonnes manquantes ou des modifications apportées au titre des colonnes. | Évitez de modifier la structure du tableau. |
| introuvables | Par [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] n’a pas pu identifier la combinaison [!UICONTROL Segment ID] et [!UICONTROL Destination ID]. Par [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] n’a pas pu identifier la combinaison [!UICONTROL Data Provider Name], [!UICONTROL Feed Name] et [!UICONTROL Use Case]. | Par [!UICONTROL Segment Level Reporting], vérifiez la validité de la combinaison [!UICONTROL Segment ID] et [!UICONTROL Destination ID]. Par [!UICONTROL Feed Level Reporting], vérifiez la validité de la combinaison [!UICONTROL Data Provider Name], [!UICONTROL Feed Name] et [!UICONTROL Use Case]. |
| Enregistrements en double trouvés | [!DNL Audience Manager] a détecté des enregistrements en double avec différentes valeurs d&#39;impression. | Passez en revue le rapport et assurez-vous de ne pas signaler différentes valeurs d’utilisation pour le même flux de données ou segment. |
| Valeurs non prises en charge | [!DNL Audience Manager] valeurs non numériques détectées dans la colonne [!DNL Audience Manager]. | Vérifiez l&#39;état et assurez-vous de n&#39;entrer que des valeurs numériques dans la colonne [!DNL Audience Manager]. |
| En-têtes manquants pour les champs obligatoires | [!DNL Audience Manager] a détecté des en-têtes de tableau manquants pour les champs obligatoires. Par [!UICONTROL Segment Level Reporting], les champs obligatoires sont les suivants : [!UICONTROL Segment ID], [!UICONTROL Destination ID]. Par [!UICONTROL Feed Level Reporting], les champs obligatoires sont les suivants : [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name], [!UICONTROL Use Case] | Vérifiez le rapport et assurez-vous que les en-têtes du tableau n’ont pas été falsifiés. |

>[!NOTE]
>La suppression de lignes du rapport d’utilisation des [!DNL CSV] n’a aucun effet sur le rapport d’utilisation existant. [!DNL Audience Manager] ne traite que les champs inclus dans le rapport.

<br> 

## Bonnes pratiques en matière de reporting [!DNL CPM]

<table id="table_E68FA2130D1C495FAB8982DFB6A31FD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recommandations </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Toujours signaler le nombre total d’impressions</b> </p> </td> 
   <td colname="col2"> <p>Pour les totaux d’impressions CPM : </p>
   <p> Indiquez le nombre total d’impressions sans utiliser de décimales. Audience Manager calcule automatiquement le CPM en fonction du nombre total que vous signalez.</p><p>Si vous devez signaler 1 234 567 impressions, signalez-le exactement comme cela. Il n’est pas nécessaire de diviser le nombre total d’impressions par 1 000 pour calculer le CPM.</p><p>Les caractéristiques utilisées pour optimiser votre contenu web ou votre application (optimisation du contenu) à l’aide d’outils tels qu’Adobe Target ou une destination Analytics ne contribuent pas aux totaux d’utilisation des plans CPM. Les fournisseurs de données sont généralement rémunérés pour l’optimisation de contenu à l’aide de forfaits.</p><p>Voir <a href="#cost-attribution">Attribution des coûts pour les flux de données CPM</a> pour plus d’informations. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Respectez l’intervalle de rapport mensuel</b> </p> </td> 
   <td colname="col2"> <p>Le système de rapports se ferme après le 5 de chaque mois. Si vous ne signalez pas l’utilisation de CPM d’ici là, vous devez ajouter ce montant au rapport pour le mois suivant. Supposons, par exemple, que vous utilisiez 1 000 impressions en octobre, que vous manquiez l’échéance de création de rapports d’octobre et que vous utilisiez 1 000 impressions en novembre. Dans ce cas, vous indiquez le total d’octobre et novembre (2000) en décembre, entre le 1er et le 5.</p><p><b>Conseil </b> : vous devez toujours essayer de signaler l’utilisation de CPM pour le mois précédent, entre le 1er et le 5e jour du mois suivant.</p><p>Vous pouvez signaler l’utilisation de CPM jusqu’au 5 du nouveau mois calendaire, mais cela n’est pas recommandé. La création de rapports sur l’utilisation de CPM avant le 5 de chaque mois donne à Audience Manager le temps de vérifier et de traiter les données.</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## Attribution des coûts pour les flux de données CPM {#cost-attribution}

Dans [!UICONTROL Audience Marketplace], vous devez autodéclarer les montants des impressions chaque mois, pour chacun de vos segments. Nous vous recommandons de signaler l’utilisation des [!DNL CPM] au niveau du segment, de sorte que l’attribution des coûts soit effectuée automatiquement.

<!-- marketplace_cpm_billing.xml -->

### Récapitulatif de facturation {#billing-summary}

Vous devez envoyer [!DNL CPM] montants d’impression des flux de données entre le 1er et le 5e jour de chaque mois calendaire. Pour ce faire, nous vous recommandons de [Signaler l’utilisation de CPM au niveau du segment](#segment-level-report).

>[!TIP]
>Lorsque vous signalez l’utilisation des [!DNL CPM] au niveau du segment, la section de création de rapports au niveau des flux de données est automatiquement complétée avec les quantités d’utilisation correspondantes.

Si vous devez [!UICONTROL Report CPM Usage at Data Feed Level], vous devez compiler individuellement toutes les impressions diffusées pour chaque flux au cours du mois calendaire précédent, et les signaler en fonction de l’affectation de facturation décrite dans cet article.

Après avoir signalé [!DNL CPM] numéro pour le mois civil précédent, [!DNL Adobe] procéderez comme suit :

* Créez une facture et facturez-vous en fonction du taux de [!DNL CPM] de chaque flux de données auquel vous êtes abonné.
* Payer les frais dus aux fournisseurs de données (vendeurs) en fonction de l’utilisation [!DNL CPM] déclarée.

>[!IMPORTANT]
>
>En tant qu&#39;acheteur, tous les totaux d&#39;impressions signalés doivent être véridiques et exacts. Si vous ne signalez pas les totaux d&#39;impressions avant le 5e jour de chaque mois, vous devez inclure les totaux du mois non déclaré du mois suivant.

<br> 

## Attribuer des impressions au niveau du flux en fonction des règles de qualification des caractéristiques {#assign-impressions}

Le cas d’utilisation [!UICONTROL Activation] vous permet d’utiliser des caractéristiques dans le flux de données correspondant pour créer des segments dans le [créateur de segments](../../../features/segments/segment-builder.md) et mapper ces segments à une destination. Les opérateurs booléens [!UICONTROL AND], [!UICONTROL OR] et [!UICONTROL NOT] vous permettent de définir les conditions de qualification des caractéristiques et des segments.

Lorsque vous [Signaler l’utilisation de CPM au niveau du flux de données](#feed-level-report), vous devez attribuer les impressions proportionnellement à chaque flux de données, en fonction des opérateurs [!DNL Boolean] utilisés dans les règles de qualification des caractéristiques. Le tableau suivant répertorie comment répartir correctement les impressions par type de caractéristique ou de règle booléenne.

>[!TIP]
>[Rapport sur l’utilisation de CPM au niveau du segment](#segment-level-report) pour que les rapports au niveau des flux de données soient effectués automatiquement par Audience Manager.

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Logique ou type de qualification de règle </th> 
   <th colname="col2" class="entry"> Répartition de la facturation </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ET </span> </p> </td> 
   <td colname="col2"> <p>Appliquez 100 % des totaux des impressions diffusées à toutes les caractéristiques du fournisseur dans un segment basé sur des règles qui utilise une condition BOOLÉENNE <span class="wintitle"> AND</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> OU </span> </p> </td> 
   <td colname="col2"> <p>Appliquez l’affectation pondérée des totaux des impressions diffusées à toutes les caractéristiques du fournisseur dans un segment basé sur des règles qui utilise une condition OR booléenne. L'allocation pondérée est calculée selon la formule suivante :</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NON</span> </p> </td> 
   <td colname="col2"> <p>Appliquez 100 % des totaux des impressions diffusées à toutes les caractéristiques du fournisseur dans un segment basé sur des règles qui utilise une condition booléenne <span class="wintitle"> NOT</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segments algorithmiques </p> </td> 
   <td colname="col2"> <p>Appliquez 100 % des totaux d’impressions diffusés à tous les flux du fournisseur dans un segment contenant des caractéristiques algorithmiques. </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## Exemples de facturation {#billing-examples}

Les exemples ci-dessous sont destinés à illustrer comment l’affectation de l’utilisation des [!DNL CPM] est effectuée au niveau des flux de données.

>[!IMPORTANT]
>Nous vous recommandons plutôt de [Signaler l’utilisation de CPM au niveau du segment](#segment-level-report) pour que ce processus soit exécuté automatiquement.

Examinons le scénario suivant :

![exemples-de-facturation](assets/billing-examples.png)

<br> 

### Cas 1 : Segments avec des règles de qualification ET

Ce segment contient 3 caractéristiques provenant de fournisseurs de données distincts. Comme la qualification du segment est basée sur une condition de [!UICONTROL AND], les visiteurs doivent réaliser les caractéristiques des trois flux pour être qualifiés pour le segment.

![](assets/billing-segment-and.png)

Avec une condition de [!UICONTROL AND], vous devez affecter 100 % des impressions reçues au cours du mois aux trois fournisseurs de données. Dans la section [!UICONTROL Audience Marketplace > Payables], vous attribuez 1 000 000 d’impressions à chaque fournisseur.

Cet exemple s’applique aux segments qui utilisent des opérateurs [!DNL Boolean] [!UICONTROL NOT] ou aux segments qui contiennent des caractéristiques algorithmiques.

<br> 

### Cas 2 : Segments avec des règles de qualification OU

Ce segment contient 3 caractéristiques provenant de fournisseurs de données distincts. Comme la qualification du segment est basée sur une condition de [!UICONTROL OR], les visiteurs doivent réaliser au moins l’une des trois caractéristiques pour être qualifiés pour le segment.

Nous ne pouvons pas déterminer quelle caractéristique est responsable d’une impression, car la qualification est basée sur une condition [!UICONTROL OR]. Par conséquent, dans la section [!UICONTROL Audience Marketplace > Payables], vous créditez chaque fournisseur d’une affectation pondérée du nombre total d’impressions, en fonction de la population de caractéristiques.

![billing-segment-or](assets/billing-segment-or.png)

<br> 

### Cas 3 : Segments avec des cas d’utilisation de modélisation et d’activation

Cet exemple décrit l’attribution basée sur deux cas d’utilisation de flux de données : modélisation et activation. Dans l’exemple, nous nous intéressons à deux fournisseurs de données, avec les informations suivantes :

![flux de données](assets/feed-use-cases.png)

Dans le tableau ci-dessous, le segment X contient deux caractéristiques, T1 et T2, avec la règle de segment T1 OU T2, où :

* T1 est une caractéristique du flux de données A ;
* T2 est une caractéristique algorithmique modélisée d’après les caractéristiques tierces des flux de données A et B.

Le segment est mappé à une destination et 1 000 000 d’impressions sont saisies pour ce segment en un mois, à l’aide de [Rapports au niveau du segment](#segment-level-report).

Sur ces 1 000 000 impressions :

* T1 représente 40 % de la population du segment, ce qui se traduit par 400 000 impressions pour le flux A.
* T2 représente 60 % de la population du segment, ce qui se traduit par 600 000 impressions pour le flux A et le flux B.

Au niveau du flux de données, la manière dont les impressions sont attribuées est la suivante :

* Le flux de données A reçoit 600 000 impressions de la caractéristique T2 (qui est modélisée sur les caractéristiques du flux de données A et du flux de données B, de sorte que les deux reçoivent les impressions) et 400 000 impressions de la caractéristique T1 (qui est une caractéristique du flux de données A), soit un total de 1 000 000 impressions.
* Le flux de données B reçoit 600 000 impressions de la caractéristique T2 (voir l’explication ci-dessus) et 0 impression de la caractéristique T1.

La répartition en un coup d’œil par flux de données et cas d’utilisation est la suivante :

![feed-down](assets/feed-breakdown-alt.png)

>[!NOTE]
>
>Pour le cas d’utilisation de modélisation, vous devez uniquement signaler l’utilisation de CPM lors de l’activation. Si vous exécutez uniquement un modèle, mais ne l’activez pas, aucun rapport d’utilisation n’est requis.

<br> 

## Affectation de facturation et d’impression pour les flux de données à frais fixes {#billing-flat-fee}

Un flux de données à frais fixes vous facture un montant fixe chaque mois, quelle que soit la date de début de l’abonnement ou le nombre d’impressions que vous utilisez. Les frais ne sont pas calculés au prorata pour une utilisation ou des intervalles mensuels partiels. Comme pour la facturation CPM, Adobe génère une facture et vous facture au taux mensuel et forfaitaire pour les flux de données auxquels vous êtes abonné.

Supposons, par exemple, que vous ayez décidé d’activer certaines caractéristiques dans un flux au milieu du mois. Vous serez toujours facturé au taux mensuel complet, quelle que soit la date à laquelle vous avez commencé l’abonnement ou activé les caractéristiques spécifiques.
