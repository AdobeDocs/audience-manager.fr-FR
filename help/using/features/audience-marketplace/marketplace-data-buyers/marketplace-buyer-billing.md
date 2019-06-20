---
description: Les acheteurs de données Audience Marketplace acceptent de signaler toutes les impressions publicitaires diffusées à l'aide de caractéristiques contenues dans le prix du flux de données sur la base d'un coût par millier d'impressions publicitaires (CPM). L'utilisation du CPM est due le cinquième jour de chaque mois calendaire et inclut les données du mois précédent. Les abonnés à frais plats n'ont pas besoin d'utiliser des rapports.
seo-description: Les acheteurs de données Audience Marketplace acceptent de signaler toutes les impressions publicitaires diffusées à l'aide de caractéristiques contenues dans le prix du flux de données sur la base d'un coût par millier d'impressions publicitaires (CPM). L'utilisation du CPM est due le cinquième jour de chaque mois calendaire et inclut les données du mois précédent. Les abonnés à frais plats n'ont pas besoin d'utiliser des rapports.
seo-title: Facturation des acheteurs de flux de données
solution: Audience Manager
title: Facturation des acheteurs de flux de données
topic: API DIL
uuid: d 7236667-282 b -4160-9909-579721 af 4016
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# Billing for Data Feed Buyers {#billing-for-data-feed-buyers}

Audience Marketplace data buyers agree to report all ad impressions served using traits contained in the data feed priced on a cost per thousand ad impressions ([!DNL CPM]) basis. [!DNL CPM] l&#39;utilisation est due le cinquième jour de chaque mois calendaire et inclut les données du mois précédent. Les abonnés à frais plats n&#39;ont pas besoin d&#39;utiliser des rapports.

## How to Report CPM Usage {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] Les acheteurs de données acceptent de signaler toutes les impressions publicitaires diffusées à l&#39;aide de caractéristiques contenues dans le flux de données sur un coût par millier d&#39;impressions publicitaires ([!DNL CPM]). [!DNL CPM] l&#39;utilisation est due au 5 jour de chaque mois calendaire et inclut les données du mois précédent. Les abonnés à frais plats n&#39;ont pas besoin d&#39;utiliser des rapports.

[!UICONTROL Audience Marketplace] offre deux méthodes de rapport [!DNL CPM] :

* **Création de rapports au niveau du segment**: il s&#39;agit de la méthode recommandée [!DNL CPM] de création de rapports d&#39;utilisation. When you report [!DNL CPM] usage at segment level, the data feed-level reporting section is automatically filled in with the corresponding usage amounts, based on the algorithms described in [Cost Attribution for CPM Data Feeds](#cost-attribution).
* **Rapports au niveau du flux de données**: cette méthode exige que vous rapportiez individuellement l [!DNL CPM] &#39;utilisation pour chaque flux de données, en fonction des algorithmes décrits dans [Attribution de coûts pour les flux de données CPM](#cost-attribution). Toutefois, cette méthode est plus fastidieuse et présente une erreur que la création de rapports au niveau du segment.

## Report CPM Usage at Segment Level {#segment-level-report}

[!UICONTROL Segment Usage] L&#39;onglet vous permet de rapporter l&#39;utilisation au niveau du segment, tout en affichant les segments regroupés par les destinations auxquelles ils sont associés.

After reporting [!DNL CPM] usage at segment level, [!UICONTROL Audience Marketplace] automatically assigns the corresponding data feeds the correct usage, based on the [Cost Attribution for CPM Data Feeds](#cost-attribution).

To report [!DNL CPM] usage at segment level:

1. Go to **[!UICONTROL Audience Marketplace > Payables]**.
2. Select the **[!UICONTROL Segment Usage]** tab.
3. Renseignez l&#39;utilisation de vos segments. You can use the [!UICONTROL Search] box to filter the segments if you only need to report usage for some of them.
4. Cliquez sur **[!UICONTROL Edit Segments Usage]**.
5. Enter the [!DNL CPM] usage amount in the [!UICONTROL Usage] column.
6. Click **[!UICONTROL Save]** when you&#39;re done and review the confirmation dialog.
   ![confirm-segment-usage](assets/confirm-segment-usage.png)
7. Cliquez sur **[!UICONTROL Confirm]**.

## Report CPM Usage at Data Feed Level {#feed-level-report}

Data feed-level reporting is a more tedious and prone to error process, since you must individually calculate [!DNL CPM] usage for each data feed. We recommend that you [Report CPM Usage at Segment Level](#segment-level-report) instead.

To report [!DNL CPM] usage at segment level:

1. Go to **[!UICONTROL Audience Marketplace > Payables]**.
2. Select the **[!UICONTROL Feed Usage]** tab.
3. Use the [!UICONTROL Search] box to filter the data feeds and identify the ones that you need to report usage for.
4. Cliquez sur **[!UICONTROL Edit Feeds Usage]**.
5. Calculate the [!DNL CPM] usage for each data feed based on the [Cost Attribution for CPM Data Feeds](#cost-attribution), and enter it in the [!UICONTROL Usage] column.
6. Click **[!UICONTROL Save]** when you&#39;re done and review the confirmation dialog.

   ![confirm-feed-usage](assets/confirm-feed-usage.png)

7. Cliquez sur **[!UICONTROL Confirm]**.

## Création de rapports en masse

To reduce errors and overhead while reporting [!DNL CPM] usage, you can use the bulk reporting option to download a [!DNL CSV] file containing the data feeds and segments, fill in the usage, and upload it back to [!DNL Audience Manager]. Vous pouvez utiliser des rapports en masse pour rapporter l&#39;utilisation des flux et des segments.

To update [!DNL CPM] usage in bulk:

1. Go to **[!UICONTROL Audience Marketplace > Payables]**.
1. Select the **[!UICONTROL Feed Usage]** or **[!UICONTROL Segment Usage]** tab, depending on the type of reporting that you want to update.
1. Click **[!UICONTROL Edit Feeds Usage]** or **[!UICONTROL Edit Segments Usage]**.
1. Click **[!UICONTROL download the current usage]** to make sure you use a valid CSV file.
1. Ouvrez le fichier sur votre ordinateur et remplissez le rapport d&#39;utilisation.
1. Click **[!UICONTROL Choose a CSV file]** to upload the updated usage report.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] valide le fichier dès que vous le téléchargez et vous invite s&#39;il détecte des erreurs dans le fichier.

### Erreurs de validation de rapport en masse

| Message d’erreur | Description | Correction de l’affichage inapproprié comme titre de la valeur |
| ------------- | -------------| -----|
| Entrée non valide | [!DNL Audience Manager] détection d&#39;une modification du schéma [!DNL CSV] de fichier, par exemple des colonnes manquantes ou des modifications dans les titres des colonnes. | Evitez de modifier la structure du tableau. |
| introuvables | For [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] could not identify the [!UICONTROL Segment ID] and [!UICONTROL Destination ID] combination. For [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] could not identify the [!UICONTROL Data Provider Name], [!UICONTROL Feed Name], and [!UICONTROL Use Case] combination. | For [!UICONTROL Segment Level Reporting], check the validity of the [!UICONTROL Segment ID] and [!UICONTROL Destination ID] combination. For [!UICONTROL Feed Level Reporting], check the validity of the [!UICONTROL Data Provider Name], [!UICONTROL Feed Name], and [!UICONTROL Use Case] combination. |
| Duplication des enregistrements trouvés | [!DNL Audience Manager] détecté des enregistrements en double avec des valeurs d&#39;impression différentes. | Examinez le rapport et veillez à ne pas signaler les différentes valeurs d&#39;utilisation pour le même flux de données ou le même segment. |
| Valeurs non prises en charge | [!DNL Audience Manager] valeurs non numériques détectées dans [!DNL Audience Manager] la colonne. | Review the report and make sure you only enter numerical values in the [!DNL Audience Manager] column. |
| En-têtes des champs obligatoires manquants | [!DNL Audience Manager] détecté les en-têtes de tableau manquants pour les champs obligatoires. For [!UICONTROL Segment Level Reporting], the mandatory fields are: [!UICONTROL Segment ID], [!UICONTROL Destination ID]. For [!UICONTROL Feed Level Reporting], the mandatory fields are: [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name],  [!UICONTROL Use Case] | Examinez le rapport et assurez-vous que les en-têtes du tableau n&#39;ont pas été modifiés. |

>[!NOTE]
>Removing rows from the [!DNL CSV] usage report does not have any effect on the existing usage report. [!DNL Audience Manager] traite uniquement les champs inclus dans le rapport.

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
   <td colname="col1"> <p><b>Toujours reporter le nombre total d'impressions</b> </p> </td> 
   <td colname="col2"> <p>Pour les totaux d'impression CPM : </p>
   <p> Signalez le nombre total d'impressions, sans utiliser les décimales. Audience Manager calcule automatiquement le CPM en fonction du nombre total de rapports que vous avez générés.</p><p>Si vous avez besoin d'un rapport de 1 234 567 impressions, signalez-le exactement comme cela. Il n'est pas nécessaire de diviser le nombre total d'impressions par 1 000 pour calculer le CPM.</p><p>Les caractéristiques utilisées pour optimiser le contenu Web ou d'application (optimisation du contenu) à l'aide d'outils tels qu'Adobe Target ou une destination Analytics ne contribuent pas aux totaux d'utilisation pour les plans CPM. En règle générale, les fournisseurs de données sont rémunérés pour l'optimisation du contenu à l'aide de formules à forfait fixe.</p><p>See <a href="#cost-attribution">Cost Attribution for CPM Data Feeds</a> for more information. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Respecter l'intervalle de création de rapports mensuel</b> </p> </td> 
   <td colname="col2"> <p>Le système de rapports se ferme après le cinquième de chaque mois. Si vous ne signalez pas l'utilisation du CPM d'ici alors, vous devez ajouter ce montant au rapport pour le mois suivant. Par exemple, supposons que vous utilisez 1 000 impressions en octobre, manquez l'échéance de création de rapports d'octobre et que 1 000 impressions soient utilisées en novembre. Dans ce cas, vous signalez le total d'octobre et de novembre (2000) en décembre entre le 1 er et le cinquième.</p><p><b>Conseil</b>: Vous devez toujours essayer de reporter l'utilisation du CPM pour le mois précédent entre le 1 er et le 5 ème jour du mois suivant.</p><p>Vous pouvez reporter l'utilisation du CPM aussi tard que le cinquième du nouveau mois calendaire, mais cela n'est pas recommandé. La création de rapports sur l'utilisation du CPM avant le cinquième de chaque mois donne à Audience Manager le temps de vérifier et de traiter les données.</p> </td>
  </tr> 
 </tbody> 
</table>

## Cost Attribution for CPM Data Feeds {#cost-attribution}

In [!UICONTROL Audience Marketplace] you must self-report impression amounts each month, for each of your segments. We recommend reporting [!DNL CPM] usage at segment level, so that cost attribution is done automatically.

<!-- marketplace_cpm_billing.xml -->

### Billing Summary {#billing-summary}

You must submit [!DNL CPM] data feed impression amounts between the 1st and the 5th days of each calendar month. To do this correctly, we recommend that you [Report CPM Usage at Segment Level](#segment-level-report).

>[!TIP]
>When you report [!DNL CPM] usage at segment level, the data feed-level reporting section is automatically filled in with the corresponding usage amounts.

Should you need to [!UICONTROL Report CPM Usage at Data Feed Level], you must individually compile all impressions delivered for each feed in the previous calendar month, and report them according to the billing allocation described in this article.

After you report [!DNL CPM] number for the previous calendar month, [!DNL Adobe] will do the following:

* Create an invoice and bill you based on the [!DNL CPM] rate for each subscribed data feed.
* Pay data providers (sellers) fees owed based on your reported [!DNL CPM] use.

>[!IMPORTANT]
>
>En tant qu&#39;acheteur, tous les totaux d&#39;impressions signalés doivent être vrais et précis. Si vous ne parvenez pas à signaler les totaux d&#39;impressions selon le cinquième jour de chaque mois, vous devez inclure les totaux pour le mois non signalé dans le mois suivant.

## Assign Impressions at Feed Level Based on Trait Qualification Rules {#assign-impressions}

The [!UICONTROL Activation] use case lets you use traits in the corresponding data feed to create segments in [Segment Builder](../../../features/segments/segment-builder.md#topic_E166819D26B94A868376BA54E10E4B74) and map those segments to a destination. The Boolean operators [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT] let you set the conditions for trait and segment qualification.

When you [Report CPM Usage at Data Feed Level](#feed-level-report), you must allocate impressions proportionally for each data feed, according to the [!DNL Boolean] operators used in the trait qualification rules. Le tableau suivant indique comment allouer correctement les impressions par type de règle ou de caractéristique booléenne.

>[!TIP]
>[Utiliser l&#39;utilisation CPM au niveau du segment](#segment-level-report) pour que les rapports au niveau du flux de données soient automatiquement générés par Audience Manager.

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Logique ou type de qualification de règle </th> 
   <th colname="col2" class="entry"> Facturation de la facturation </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> AND</span> </p> </td> 
   <td colname="col2"> <p>Apply 100% of the delivered impression totals to all the provider traits in a rules-based segment that uses a Boolean <span class="wintitle"> AND</span> condition. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> OU</span> </p> </td> 
   <td colname="col2"> <p>Appliquez l'attribution pondérée des totaux d'impression remis à toutes les caractéristiques du fournisseur d'un segment basé sur des règles utilisant une condition OU booléenne. L'allocation pondérée est calculée à l'aide de la formule suivante :</p><p><code>(Population de caractéristiques/Population de segments) * Nombre d'impressions * Coût du CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> SAUF</span> </p> </td> 
   <td colname="col2"> <p>Apply 100% of the delivered impression totals to all the provider traits in a rules-based segment that uses a Boolean <span class="wintitle"> NOT</span> condition. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segments algorithmiques </p> </td> 
   <td colname="col2"> <p>Appliquez 100 % des totaux d'impression remis à tous les flux de fournisseur d'un segment contenant des caractéristiques algorithmiques. </p> </td> 
  </tr>
 </tbody>
</table>

## Billing Examples {#billing-examples}

The examples below are meant to illustrate how [!DNL CPM] usage allocation is done at data feed level.

>[!MPORTANT]
>We recommend that you [Report CPM Usage at Segment Level](#segment-level-report) instead, to have this process done automatically.

Examinons le scénario suivant :

![facturation-exemples](assets/billing-examples.png)

### Cas 1 : Segments avec règles de qualification ET

Ce segment contient trois caractéristiques provenant de fournisseurs de données distincts. Since segment qualification is based on an [!UICONTROL AND] condition, visitors have to realize the traits from all three feeds to qualify for the segment.

![](assets/billing-segment-and.png)

With an [!UICONTROL AND] condition, you must assign 100% of the impressions received during the month to all three data providers. In the [!UICONTROL Audience Marketplace > Payables] section, you credit each provider with 1,000,000 impressions.

This example applies to segments that use [!DNL Boolean] [!UICONTROL NOT] operators or for segments that contain algorithmic traits.

### Cas 2 : Segments avec règles de qualification OU

Ce segment contient trois caractéristiques provenant de fournisseurs de données distincts. Since segment qualification is based on an [!UICONTROL OR] condition, visitors have to realize at least one of the three traits to qualify for the segment.

We cannot tell which trait is responsible for an impression because qualification is based on an [!UICONTROL OR] condition. As a result, in the [!UICONTROL Audience Marketplace > Payables] section you credit each provider with a weighted allocation of the total impressions, based on trait population.

![facturation-segment-ou](assets/billing-segment-or.png)

>[!MORE_ LIKE_ THIS]
>
>* [Attribution de facturation et d&#39;impression pour les flux de données de frais plats](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)


## Billing and Impression Allocation for Flat Fee Data Feeds {#billing-flat-fee}

Un flux de données de frais fixe facture un montant fixe chaque mois, quel que soit le moment où commence l&#39;abonnement ou le nombre d&#39;impressions que vous utilisez. Les frais ne sont pas calculés au prorata pour un mois partiel ou des intervalles. A l&#39;instar de la facturation CPM, Adobe génère une facture et facture le montant mensuel et plat des flux de données abonnés.

Supposons, par exemple, que vous ayez décidé d&#39;activer certaines caractéristiques dans un flux au milieu du mois. Vous serez toujours facturé à la fréquence complète, quel que soit le moment où vous avez démarré l&#39;abonnement ou que vous avez activé des caractéristiques spécifiques.