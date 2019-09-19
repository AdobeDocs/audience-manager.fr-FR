---
description: Les acheteurs de données Audience Marketplace acceptent de signaler toutes les impressions publicitaires diffusées à l’aide des caractéristiques contenues dans le flux de données dont le prix est calculé sur la base d’un coût par millier d’impressions publicitaires (CPM). L’utilisation du CPM est due le 5e jour de chaque mois calendaire et inclut les données du mois précédent. Les abonnés à des frais fixes n’ont pas besoin de signaler l’utilisation.
seo-description: Les acheteurs de données Audience Marketplace acceptent de signaler toutes les impressions publicitaires diffusées à l’aide des caractéristiques contenues dans le flux de données dont le prix est calculé sur la base d’un coût par millier d’impressions publicitaires (CPM). L’utilisation du CPM est due le 5e jour de chaque mois calendaire et inclut les données du mois précédent. Les abonnés à des frais fixes n’ont pas besoin de signaler l’utilisation.
seo-title: Facturation pour les acheteurs de flux de données
solution: Audience Manager
title: Facturation pour les acheteurs de flux de données
keywords: Création de rapports au niveau du segment, au niveau du segment, au niveau du segment
uuid: d7236667-282b-4160-9909-579721af4016
translation-type: tm+mt
source-git-commit: a8320894c0efcf46bd3236494e1aa7b1eded24d1

---


# Facturation pour les acheteurs de flux de données {#billing-for-data-feed-buyers}

Les acheteurs de données Audience Marketplace acceptent de signaler toutes les impressions publicitaires diffusées à l’aide des caractéristiques contenues dans le flux de données dont le prix est fixé sur un coût par millier d’impressions publicitaires ([!DNL CPM]). [!DNL CPM] l’utilisation est due le 5e jour de chaque mois calendaire et inclut les données du mois précédent. Les abonnés à des frais fixes n’ont pas besoin de signaler l’utilisation.

<br> 

## Comment signaler l'utilisation du CPM {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] les acheteurs de données acceptent de signaler toutes les impressions publicitaires diffusées à l’aide des caractéristiques contenues dans le flux de données, sur la base d’un coût par millier d’impressions publicitaires ([!DNL CPM]). [!DNL CPM] l’utilisation est due le 5 jour de chaque mois calendaire et inclut les données du mois précédent. Les abonnés à des frais fixes n’ont pas besoin de signaler l’utilisation.

[!UICONTROL Audience Marketplace] propose deux méthodes pour signaler [!DNL CPM] l’utilisation :

* **Création de rapports** au niveau du segment : il s’agit de la méthode de création de rapports d’ [!DNL CPM] utilisation recommandée. Lorsque vous signalez [!DNL CPM] l’utilisation au niveau du segment, la section de rapport au niveau du flux de données est automatiquement renseignée avec les montants d’utilisation correspondants, en fonction des algorithmes décrits dans la section Attribution des [coûts pour les flux](#cost-attribution)de données CPM.
* **Rapports** au niveau du flux de données : cette méthode nécessite de signaler individuellement l’ [!DNL CPM] utilisation de chaque flux de données, en fonction des algorithmes décrits dans la section Attribution des [coûts pour les flux](#cost-attribution)de données CPM. Toutefois, cette méthode est plus fastidieuse et sujette aux erreurs que les rapports au niveau des segments.

<br> 

## Utilisation du CPM des rapports au niveau du segment {#segment-level-report}

L’ [!UICONTROL Segment Usage] onglet vous permet de signaler l’utilisation au niveau du segment, tout en affichant les segments regroupés par destination à laquelle ils sont mappés.

Une fois l’ [!DNL CPM] utilisation de la création de rapports au niveau du segment, [!UICONTROL Audience Marketplace] affecte automatiquement les flux de données correspondants à l’utilisation correcte, en fonction de l’attribution de [coût pour les flux](#cost-attribution)de données CPM.

Pour signaler [!DNL CPM] l’utilisation au niveau du segment :

1. Allez-y **[!UICONTROL Audience Marketplace > Payables]**.
1. Sélectionnez l’ **[!UICONTROL Segment Usage]** onglet.
1. Renseignez l’utilisation de vos segments. Vous pouvez utiliser la [!UICONTROL Search] zone pour filtrer les segments si vous devez uniquement signaler l’utilisation de certains d’entre eux.
1. Cliquez sur **[!UICONTROL Edit Segments Usage]**.
1. Entrez le montant d' [!DNL CPM] utilisation dans la [!UICONTROL Usage] colonne.
1. Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé et consultez la boîte de dialogue de confirmation.

   ![verify-segment-usage](assets/confirm-segment-usage.png)

1. Cliquez sur **[!UICONTROL Confirm]**.

Consultez également notre démonstration vidéo sur la manière de signaler l’utilisation au niveau du segment :

>[!VIDEO](https://video.tv.adobe.com/v/25522/?captions=fre_fr)

 

## Utilisation du CPM des rapports au niveau du flux de données {#feed-level-report}

La création de rapports au niveau du flux de données est un processus plus fastidieux et plus susceptible d’entraîner des erreurs, car vous devez calculer individuellement [!DNL CPM] l’utilisation de chaque flux de données. Nous vous recommandons plutôt de [signaler l’utilisation du CPM au niveau](#segment-level-report) du segment.

Pour signaler [!DNL CPM] l’utilisation au niveau du segment :

1. Allez-y **[!UICONTROL Audience Marketplace > Payables]**.
2. Sélectionnez l’ **[!UICONTROL Feed Usage]** onglet.
3. Utilisez la [!UICONTROL Search] zone pour filtrer les flux de données et identifier ceux pour lesquels vous devez créer des rapports d’utilisation.
4. Cliquez sur **[!UICONTROL Edit Feeds Usage]**.
5. Calculez l’ [!DNL CPM] utilisation de chaque flux de données en fonction de l’attribution de [coût pour les flux](#cost-attribution)de données CPM, puis saisissez-le dans la [!UICONTROL Usage] colonne.
6. Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé et consultez la boîte de dialogue de confirmation.

   ![verify-feed-usage](assets/confirm-feed-usage.png)

7. Cliquez sur **[!UICONTROL Confirm]**.

<br> 

## Création de rapports en masse

Pour réduire les erreurs et les frais généraux lors de l’ [!DNL CPM] utilisation des rapports, vous pouvez utiliser l’option de création de rapports en masse pour télécharger un [!DNL CSV] fichier contenant les flux de données et les segments, renseigner l’utilisation et le télécharger à nouveau vers [!DNL Audience Manager]. Vous pouvez utiliser des rapports en masse pour signaler l’utilisation des flux et des segments.

Pour mettre à jour [!DNL CPM] l’utilisation en bloc :

1. Allez-y **[!UICONTROL Audience Marketplace > Payables]**.
1. Sélectionnez l’ **[!UICONTROL Feed Usage]** onglet ou **[!UICONTROL Segment Usage]** , selon le type de rapport à mettre à jour.
1. Cliquez sur **[!UICONTROL Edit Feeds Usage]** ou **[!UICONTROL Edit Segments Usage]**.
1. Cliquez sur **[!UICONTROL download the current usage]** pour vous assurer d’utiliser un fichier CSV valide.
1. Ouvrez le fichier sur votre ordinateur et renseignez le rapport d’utilisation.
1. Cliquez sur **[!UICONTROL Choose a CSV file]** pour télécharger le rapport d’utilisation mis à jour.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] valide le fichier dès que vous l’avez téléchargé et vous invite à le signaler s’il détecte des erreurs dans le fichier.

<br> 

### Erreurs de validation de création de rapports en masse

| Message d’erreur | Description | Correction de l’affichage inapproprié comme titre de la valeur |
| ------------- | -------------| -----|
| Entrée non valide | [!DNL Audience Manager] a détecté un changement dans le schéma de [!DNL CSV] fichier, tel que des colonnes manquantes ou des modifications dans les titres de colonnes. | Evitez de modifier la structure du tableau. |
| introuvables | Par exemple, [!UICONTROL Segment Level Reporting]il [!DNL Audience Manager] n’a pas pu identifier la [!UICONTROL Segment ID] combinaison et [!UICONTROL Destination ID] . Par exemple [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] n'a pas pu identifier la [!UICONTROL Data Provider Name], [!UICONTROL Feed Name]et [!UICONTROL Use Case] combinaison. | Pour [!UICONTROL Segment Level Reporting]cela, vérifiez la validité de la [!UICONTROL Segment ID] combinaison et [!UICONTROL Destination ID] . Pour [!UICONTROL Feed Level Reporting]cela, vérifiez la validité de la combinaison [!UICONTROL Data Provider Name], [!UICONTROL Feed Name]et [!UICONTROL Use Case] . |
| Dupliquer les enregistrements trouvés | [!DNL Audience Manager] détecté des enregistrements en double avec des valeurs d’impression différentes. | Consultez le rapport et veillez à ne pas signaler des valeurs d’utilisation différentes pour le même flux de données ou segment. |
| Valeurs non prises en charge | [!DNL Audience Manager] détecté des valeurs non numériques dans la [!DNL Audience Manager] colonne. | Consultez le rapport et veillez à n’entrer que des valeurs numériques dans la [!DNL Audience Manager] colonne. |
| En-têtes des champs obligatoires manquants | [!DNL Audience Manager] en-têtes de tableau manquants détectés pour les champs obligatoires. Pour [!UICONTROL Segment Level Reporting]cela, les champs obligatoires sont : [!UICONTROL Segment ID], [!UICONTROL Destination ID]. Pour [!UICONTROL Feed Level Reporting]cela, les champs obligatoires sont : [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name], [!UICONTROL Use Case] | Consultez le rapport et assurez-vous que les en-têtes de tableau n’ont pas été modifiés. |

>[!NOTE]
>La suppression de lignes du rapport [!DNL CSV] d’utilisation n’a aucun effet sur le rapport d’utilisation existant. [!DNL Audience Manager] traite uniquement les champs inclus dans le rapport.

<br> 

## [!DNL CPM] Bonnes pratiques en matière de création de rapports

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
   <td colname="col2"> <p>Pour les totaux d’impression CPM : </p>
   <p> Indiquez le nombre total d’impressions, sans utiliser de décimales. Audience Manager calcule automatiquement le CPM en fonction du nombre total de rapports.</p><p>Si vous devez signaler 1 234 567 impressions, signalez-le exactement comme cela. Il n’est pas nécessaire de diviser le nombre total d’impressions par 1 000 pour calculer le CPM.</p><p>Les caractéristiques utilisées pour optimiser le contenu Web ou d’application (optimisation du contenu) à l’aide d’outils tels qu’Adobe Target ou une destination Analytics ne contribuent pas aux totaux d’utilisation des plans CPM. Les fournisseurs de données sont généralement rémunérés pour l’optimisation du contenu à l’aide de forfaits.</p><p>Voir Attribution <a href="#cost-attribution">de coût pour les flux</a> de données CPM pour en savoir plus. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Se limiter à l’intervalle de création de rapports mensuel</b> </p> </td> 
   <td colname="col2"> <p>Le système de rapports se ferme après le 5 de chaque mois. Si vous ne signalez pas l'utilisation du CPM d'ici là, vous devez ajouter ce montant au rapport pour le mois suivant. Supposons, par exemple, que vous utilisiez 1 000 impressions en octobre, que vous manquiez l’échéance du rapport d’octobre et que vous utilisiez 1 000 impressions en novembre. Dans ce cas, vous signalez le total d’octobre et de novembre (2000) en décembre, entre le 1er et le 5.</p><p><b>Conseil</b>: Vous devez toujours essayer de rapporter l'utilisation du CPM pour le mois précédent entre le 1er et le 5 jours du mois suivant.</p><p>Vous pouvez signaler l’utilisation du CPM jusqu’au 5 du nouveau mois calendaire, mais cette opération n’est pas recommandée. La création de rapports sur l’utilisation du CPM avant le 5 de chaque mois donne à Audience Manager le temps de vérifier et de traiter les données.</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## Attribution de coût pour les flux de données CPM {#cost-attribution}

Dans [!UICONTROL Audience Marketplace] vous devez auto-déclarer les montants d’impression chaque mois, pour chacun de vos segments. Il est recommandé d’utiliser [!DNL CPM] les rapports au niveau du segment, de sorte que l’attribution des coûts soit effectuée automatiquement.

<!-- marketplace_cpm_billing.xml -->

### Résumé de la facturation {#billing-summary}

Vous devez envoyer des montants d’impression [!DNL CPM] de flux de données entre le 1er et le 5e jour de chaque mois calendaire. Pour ce faire, nous vous recommandons de [signaler l’utilisation du CPM au niveau](#segment-level-report)du segment.

>[!TIP]
>Lorsque vous signalez [!DNL CPM] l’utilisation au niveau du segment, la section de rapport au niveau du flux de données est automatiquement renseignée avec les montants d’utilisation correspondants.

Si nécessaire [!UICONTROL Report CPM Usage at Data Feed Level], vous devez compiler individuellement toutes les impressions distribuées pour chaque flux du mois calendaire précédent et les reporter en fonction de l’allocation de facturation décrite dans cet article.

Une fois le [!DNL CPM] numéro de rapport du mois civil précédent généré, [!DNL Adobe] procédez comme suit :

* Créez une facture et une facture en fonction du [!DNL CPM] taux de chaque flux de données souscrit.
* Payez les frais dus aux fournisseurs de données (vendeurs) en fonction de votre [!DNL CPM] utilisation déclarée.

>[!IMPORTANT]
>
>En tant qu’acheteur, tous les totaux d’impression signalés doivent être exacts et exacts. Si vous ne signalez pas les totaux des impressions avant le 5e jour de chaque mois, vous devez inclure les totaux pour le mois non déclaré du mois suivant.

<br> 

## Affecter des impressions au niveau du flux en fonction des règles de qualification des caractéristiques {#assign-impressions}

Le cas [!UICONTROL Activation] d’utilisation vous permet d’utiliser des caractéristiques dans le flux de données correspondant pour créer des segments dans le créateur [de](../../../features/segments/segment-builder.md) segments et mapper ces segments à une destination. Les opérateurs booléens [!UICONTROL AND], [!UICONTROL OR]et [!UICONTROL NOT] vous permettent de définir les conditions de qualification des caractéristiques et des segments.

Lorsque vous [signalez l’utilisation du CPM au niveau](#feed-level-report)du flux de données, vous devez allouer des impressions proportionnellement pour chaque flux de données, en fonction des [!DNL Boolean] opérateurs utilisés dans les règles de qualification des caractéristiques. Le tableau suivant indique comment allouer correctement les impressions par règle booléenne ou type de caractéristique.

>[!TIP]
>[Rapport sur l’utilisation du CPM au niveau](#segment-level-report) du segment pour que les rapports au niveau du flux de données soient automatiquement exécutés par Audience Manager.

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
   <td colname="col2"> <p>Appliquez 100 % des totaux d’impression distribués à toutes les caractéristiques du fournisseur dans un segment basé sur des règles qui utilise une condition Boolean <span class="wintitle"> AND</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> OU</span> </p> </td> 
   <td colname="col2"> <p>Appliquez une allocation pondérée des totaux d’impression distribués à toutes les caractéristiques du fournisseur dans un segment basé sur des règles qui utilise une condition OU booléenne. L’allocation pondérée est calculée à l’aide de la formule suivante :</p><p><code>(Population de caractéristiques / population de segments) * Nombre d'impressions * Coût du CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> SAUF</span> </p> </td> 
   <td colname="col2"> <p>Appliquez 100 % des totaux d’impression distribués à toutes les caractéristiques du fournisseur dans un segment basé sur des règles qui utilise une condition Boolean <span class="wintitle"> NOT</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segments algorithmiques </p> </td> 
   <td colname="col2"> <p>Appliquez 100 % des totaux d’impression distribués à tous les flux du fournisseur dans un segment contenant des caractéristiques algorithmiques. </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## Exemples de facturation {#billing-examples}

Les exemples ci-dessous illustrent la manière dont l’allocation de [!DNL CPM] l’utilisation est effectuée au niveau du flux de données.

>[!IMPORTANT]
>Nous vous recommandons plutôt de [signaler l’utilisation du CPM au niveau](#segment-level-report) du segment pour que ce processus soit effectué automatiquement.

Examinons le scénario suivant :

![exemple de facturation](assets/billing-examples.png)

<br> 

### Cas 1 : Segments avec règles de qualification ET

Ce segment contient 3 caractéristiques provenant de fournisseurs de données distincts. La qualification des segments étant basée sur une [!UICONTROL AND] condition, les visiteurs doivent réaliser les caractéristiques des trois flux pour être admissibles au segment.

![](assets/billing-segment-and.png)

Avec une [!UICONTROL AND] condition, vous devez affecter 100 % des impressions reçues au cours du mois aux trois fournisseurs de données. Dans la [!UICONTROL Audience Marketplace > Payables] section, vous attribuez à chaque fournisseur 1 000 000 impressions.

Cet exemple s’applique aux segments qui utilisent [!DNL Boolean] des opérateurs [!UICONTROL NOT] ou aux segments qui contiennent des caractéristiques algorithmiques.

<br> 

### Cas 2 : Segments avec règles de qualification OU

Ce segment contient 3 caractéristiques provenant de fournisseurs de données distincts. La qualification de segment étant basée sur une [!UICONTROL OR] condition, les visiteurs doivent réaliser au moins l’une des trois caractéristiques pour être admissibles au segment.

Nous ne pouvons pas dire quelle caractéristique est responsable d'une impression parce que la qualification est basée sur une [!UICONTROL OR] condition. Par conséquent, dans la [!UICONTROL Audience Marketplace > Payables] section, vous attribuez à chaque fournisseur une allocation pondérée du total des impressions, en fonction de la population de caractéristiques.

![facturation-segment-ou](assets/billing-segment-or.png)

<br> 

### Cas 3 : Segments avec des cas d’utilisation de la modélisation et de l’activation

Cet exemple décrit l’attribution en fonction de deux cas d’utilisation du flux de données : Modélisation et Activation. Dans cet exemple, nous examinons deux fournisseurs de données, avec les informations suivantes :

![flux de données](assets/feed-use-cases.png)

Dans le tableau ci-dessous, le segment X contient deux caractéristiques, T1 et T2, avec la règle de segmentation T1 OU T2, où :

* T1 est une caractéristique du flux de données A ;
* T2 est une caractéristique algorithmique modélisée selon des caractéristiques tierces du flux de données A et du flux de données B.

Le segment est mappé à une destination et 1 000 000 impressions sont entrées pour ce segment au cours d’un mois, à l’aide de la création de rapports [au niveau du](#segment-level-report)segment.

Parmi ces 1 000 000 impressions :

* T1 représente 40 % de la population du segment, ce qui se traduit par 400 000 impressions pour le flux A.
* T2 représente 60 % de la population de segments, ce qui se traduit par 600 000 impressions pour les flux A et B.

Au niveau du flux de données, la manière dont les impressions sont attribuées est la suivante :

* Le flux de données A reçoit 600 000 impressions de la caractéristique T2 (qui est modelée sur les caractéristiques du flux de données A et du flux de données B, de sorte que toutes deux reçoivent les impressions) et 400 000 impressions de la caractéristique T1 (qui est une caractéristique du flux de données A), totalisant 1 000 000 impressions.
* Le flux de données B reçoit 600 000 impressions de la caractéristique T2 (voir l’explication ci-dessus) et 0 impressions de la caractéristique T1.

La ventilation en un coup d’oeil par flux de données et par cas d’utilisation est la suivante :

![ventilation par flux](assets/feed-breakdown-alt.png)

<br> 

##  Attribution de la facturation et de l’impression pour les flux de données à frais fixes {#billing-flat-fee}

Un flux de données à frais fixes vous facture un montant fixe chaque mois, indépendamment du moment où l’abonnement commence ou du nombre d’impressions que vous utilisez. Les frais ne sont pas répartis au prorata pour l’utilisation partielle du mois ou des intervalles. Comme pour la facturation CPM, Adobe génère une facture et vous facture au tarif mensuel fixe pour vos flux de données abonnés.

Supposons, par exemple, que vous ayez décidé d’activer certaines caractéristiques dans un flux au milieu du mois. Vous serez toujours facturé au tarif mensuel complet, quelle que soit la date à laquelle vous avez démarré l’abonnement ou activé certaines caractéristiques.