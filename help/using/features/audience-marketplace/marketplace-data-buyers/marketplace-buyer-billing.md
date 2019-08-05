---
description: Les acheteurs de données Audience Marketplace acceptent de signaler toutes les impressions publicitaires diffusées à l'aide de caractéristiques contenues dans le prix du flux de données sur la base d'un coût par millier d'impressions publicitaires (CPM). L'utilisation du CPM est due le cinquième jour de chaque mois calendaire et inclut les données du mois précédent. Les abonnés à frais plats n'ont pas besoin d'utiliser des rapports.
seo-description: Les acheteurs de données Audience Marketplace acceptent de signaler toutes les impressions publicitaires diffusées à l'aide de caractéristiques contenues dans le prix du flux de données sur la base d'un coût par millier d'impressions publicitaires (CPM). L'utilisation du CPM est due le cinquième jour de chaque mois calendaire et inclut les données du mois précédent. Les abonnés à frais plats n'ont pas besoin d'utiliser des rapports.
seo-title: Facturation des acheteurs de flux de données
solution: Audience Manager
title: Facturation des acheteurs de flux de données
keywords: Création de rapports au niveau du segment, niveau segment, niveau segment
uuid: d 7236667-282 b -4160-9909-579721 af 4016
translation-type: tm+mt
source-git-commit: dab5b255f966e63d51cc4d236d37bb0cb4eb960c

---


# Facturation des acheteurs de flux de données {#billing-for-data-feed-buyers}

Les acheteurs de données Audience Marketplace acceptent de signaler toutes les impressions publicitaires diffusées à l'aide de caractéristiques contenues dans le prix du flux de données sur un coût par millier d'impressions publicitaires ([!DNL CPM]). [!DNL CPM] l'utilisation est due le cinquième jour de chaque mois calendaire et inclut les données du mois précédent. Les abonnés à frais plats n'ont pas besoin d'utiliser des rapports.

<br> 

## Utilisation de l'utilisation du CPM {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] Les acheteurs de données acceptent de signaler toutes les impressions publicitaires diffusées à l'aide de caractéristiques contenues dans le flux de données sur un coût par millier d'impressions publicitaires ([!DNL CPM]). [!DNL CPM] l'utilisation est due au 5 jour de chaque mois calendaire et inclut les données du mois précédent. Les abonnés à frais plats n'ont pas besoin d'utiliser des rapports.

[!UICONTROL Audience Marketplace] offre deux méthodes de rapport [!DNL CPM] :

* **Création de rapports au niveau du segment**: il s'agit de la méthode recommandée [!DNL CPM] de création de rapports d'utilisation. Lorsque vous créez un rapport [!DNL CPM] sur l'utilisation au niveau du segment, la section de création de rapports au niveau du flux de données est automatiquement renseignée avec les montants d'utilisation correspondants, en fonction des algorithmes décrits dans [Attribution de coûts pour les flux de données CPM](#cost-attribution).
* **Rapports au niveau du flux de données**: cette méthode exige que vous rapportiez individuellement l [!DNL CPM] 'utilisation pour chaque flux de données, en fonction des algorithmes décrits dans [Attribution de coûts pour les flux de données CPM](#cost-attribution). Toutefois, cette méthode est plus fastidieuse et présente une erreur que la création de rapports au niveau du segment.

<br> 

## Utilisation du CPM pour le niveau du segment {#segment-level-report}

[!UICONTROL Segment Usage] L'onglet vous permet de rapporter l'utilisation au niveau du segment, tout en affichant les segments regroupés par les destinations auxquelles ils sont associés.

Après l'utilisation de la création de rapports [!DNL CPM] au niveau du segment, [!UICONTROL Audience Marketplace] affecte automatiquement les flux de données correspondants à l'utilisation correcte, en fonction de l'attribution [de coûts pour les flux de données CPM](#cost-attribution).

Pour signaler [!DNL CPM] l'utilisation au niveau du segment :

1. Accédez **[!UICONTROL Audience Marketplace > Payables]**&#x200B;à.
2. Sélectionnez **[!UICONTROL Segment Usage]** l'onglet.
3. Renseignez l'utilisation de vos segments. Vous pouvez utiliser [!UICONTROL Search] la case pour filtrer les segments si vous n'avez qu'à les rapporter pour certains d'entre eux.
4. Cliquez sur **[!UICONTROL Edit Segments Usage]**.
5. Entrez le montant [!DNL CPM] d'utilisation dans [!UICONTROL Usage] la colonne.
6. Cliquez **[!UICONTROL Save]** une fois que vous avez terminé et passez en revue la boîte de dialogue de confirmation.
   ![confirm-segment-usage](assets/confirm-segment-usage.png)
7. Cliquez sur **[!UICONTROL Confirm]**.

<br> 

## Utilisation du rapport CPM au niveau du flux de données {#feed-level-report}

Les rapports au niveau des flux de données sont plus fastidieux et présentent un processus d'erreur plus fastidieux, puisque vous devez calculer individuellement [!DNL CPM] l'utilisation pour chaque flux de données. Nous vous recommandons de [reporter l'utilisation CPM au niveau du segment](#segment-level-report) à la place.

Pour signaler [!DNL CPM] l'utilisation au niveau du segment :

1. Accédez **[!UICONTROL Audience Marketplace > Payables]**&#x200B;à.
2. Sélectionnez **[!UICONTROL Feed Usage]** l'onglet.
3. Utilisez [!UICONTROL Search] la case pour filtrer les flux de données et identifier ceux dont vous avez besoin pour créer des rapports.
4. Cliquez sur **[!UICONTROL Edit Feeds Usage]**.
5. Calculez [!DNL CPM] l'utilisation de chaque flux de données en fonction de [l'attribution de coûts pour les flux de données CPM](#cost-attribution), puis saisissez-la dans [!UICONTROL Usage] la colonne.
6. Cliquez **[!UICONTROL Save]** une fois que vous avez terminé et passez en revue la boîte de dialogue de confirmation.

   ![confirm-feed-usage](assets/confirm-feed-usage.png)

7. Cliquez sur **[!UICONTROL Confirm]**.

<br> 

## Création de rapports en masse

Pour réduire les erreurs et la surcharge lors de la création de rapports [!DNL CPM] , vous pouvez utiliser l'option de création de rapports en masse pour télécharger un [!DNL CSV] fichier contenant les flux de données et les segments, remplir l'utilisation et le télécharger à nouveau [!DNL Audience Manager]. Vous pouvez utiliser des rapports en masse pour rapporter l'utilisation des flux et des segments.

Pour mettre à jour [!DNL CPM] l'utilisation en bloc :

1. Accédez **[!UICONTROL Audience Marketplace > Payables]**&#x200B;à.
1. Sélectionnez l'onglet **[!UICONTROL Feed Usage]** ou **[!UICONTROL Segment Usage]** l'onglet, selon le type de rapport à mettre à jour.
1. Cliquez **[!UICONTROL Edit Feeds Usage]** ou **[!UICONTROL Edit Segments Usage]**.
1. Cliquez sur pour **[!UICONTROL download the current usage]** vous assurer d'utiliser un fichier CSV valide.
1. Ouvrez le fichier sur votre ordinateur et remplissez le rapport d'utilisation.
1. Cliquez sur **[!UICONTROL Choose a CSV file]** pour charger le rapport d'utilisation mis à jour.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] valide le fichier dès que vous le téléchargez et vous invite s'il détecte des erreurs dans le fichier.

<br> 

### Erreurs de validation de rapport en masse

| Message d’erreur | Description | Correction de l’affichage inapproprié comme titre de la valeur |
| ------------- | -------------| -----|
| Entrée non valide | [!DNL Audience Manager] détection d'une modification du schéma [!DNL CSV] de fichier, par exemple des colonnes manquantes ou des modifications dans les titres des colonnes. | Evitez de modifier la structure du tableau. |
| introuvables | For [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] could not identify the [!UICONTROL Segment ID] and [!UICONTROL Destination ID] combination. For [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] could not identify the [!UICONTROL Data Provider Name][!UICONTROL Feed Name], and [!UICONTROL Use Case] combination. | Pour [!UICONTROL Segment Level Reporting]ce faire, vérifiez la validité de [!UICONTROL Segment ID] la [!UICONTROL Destination ID] combinaison et de la combinaison. For [!UICONTROL Feed Level Reporting], check the valid of the [!UICONTROL Data Provider Name][!UICONTROL Feed Name], and [!UICONTROL Use Case] combination. |
| Duplication des enregistrements trouvés | [!DNL Audience Manager] détecté des enregistrements en double avec des valeurs d'impression différentes. | Examinez le rapport et veillez à ne pas signaler les différentes valeurs d'utilisation pour le même flux de données ou le même segment. |
| Valeurs non prises en charge | [!DNL Audience Manager] valeurs non numériques détectées dans [!DNL Audience Manager] la colonne. | Examinez le rapport et veillez à saisir uniquement des valeurs numériques dans [!DNL Audience Manager] la colonne. |
| En-têtes des champs obligatoires manquants | [!DNL Audience Manager] détecté les en-têtes de tableau manquants pour les champs obligatoires. Pour [!UICONTROL Segment Level Reporting], les champs obligatoires sont les suivants : [!UICONTROL Segment ID][!UICONTROL Destination ID]. Pour [!UICONTROL Feed Level Reporting], les champs obligatoires sont les suivants : [!UICONTROL Data Provider Name][!UICONTROL Data Feed Name], [!UICONTROL Use Case] | Examinez le rapport et assurez-vous que les en-têtes du tableau n'ont pas été modifiés. |

>[!NOTE]
>La suppression de lignes du rapport [!DNL CSV] d'utilisation n'a aucun effet sur le rapport d'utilisation existant. [!DNL Audience Manager] traite uniquement les champs inclus dans le rapport.

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
   <td colname="col1"> <p><b>Toujours reporter le nombre total d'impressions</b> </p> </td> 
   <td colname="col2"> <p>Pour les totaux d'impression CPM : </p>
   <p> Signalez le nombre total d'impressions, sans utiliser les décimales. Audience Manager calcule automatiquement le CPM en fonction du nombre total de rapports que vous avez générés.</p><p>Si vous avez besoin d'un rapport de 1 234 567 impressions, signalez-le exactement comme cela. Il n'est pas nécessaire de diviser le nombre total d'impressions par 1 000 pour calculer le CPM.</p><p>Les caractéristiques utilisées pour optimiser le contenu Web ou d'application (optimisation du contenu) à l'aide d'outils tels qu'Adobe Target ou une destination Analytics ne contribuent pas aux totaux d'utilisation pour les plans CPM. En règle générale, les fournisseurs de données sont rémunérés pour l'optimisation du contenu à l'aide de formules à forfait fixe.</p><p>Pour <a href="#cost-attribution">plus d'informations, voir Attribution de coûts pour les flux</a> de données CPM. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Respecter l'intervalle de création de rapports mensuel</b> </p> </td> 
   <td colname="col2"> <p>Le système de rapports se ferme après le cinquième de chaque mois. Si vous ne signalez pas l'utilisation du CPM d'ici alors, vous devez ajouter ce montant au rapport pour le mois suivant. Par exemple, supposons que vous utilisez 1 000 impressions en octobre, manquez l'échéance de création de rapports d'octobre et que 1 000 impressions soient utilisées en novembre. Dans ce cas, vous signalez le total d'octobre et de novembre (2000) en décembre entre le 1 er et le cinquième.</p><p><b>Conseil</b>: Vous devez toujours essayer de reporter l'utilisation du CPM pour le mois précédent entre le 1 er et le 5 ème jour du mois suivant.</p><p>Vous pouvez reporter l'utilisation du CPM aussi tard que le cinquième du nouveau mois calendaire, mais cela n'est pas recommandé. La création de rapports sur l'utilisation du CPM avant le cinquième de chaque mois donne à Audience Manager le temps de vérifier et de traiter les données.</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## Attribution de coûts pour les flux de données CPM {#cost-attribution}

Dans ce cas [!UICONTROL Audience Marketplace] , vous devez fournir un rapport automatique sur les montants d'impression chaque mois pour chacun de vos segments. Nous recommandons l'utilisation de rapports [!DNL CPM] au niveau du segment, de sorte que l'attribution des coûts soit effectuée automatiquement.

<!-- marketplace_cpm_billing.xml -->

### Résumé de la facturation {#billing-summary}

Vous devez envoyer [!DNL CPM] les montants d'impression du flux de données entre le 1 er et le 5 e jour de chaque mois calendaire. Pour ce faire, nous vous recommandons [de signaler l'utilisation CPM au niveau du segment](#segment-level-report).

>[!TIP]
>Lorsque vous créez un rapport [!DNL CPM] sur l'utilisation au niveau du segment, la section de création de rapports au niveau du flux de données est automatiquement renseignée avec les montants d'utilisation correspondants.

Si vous le souhaitez, [!UICONTROL Report CPM Usage at Data Feed Level]vous devez compiler individuellement toutes les impressions diffusées pour chaque flux au mois calendaire précédent et les rapporter en fonction de l'allocation de facturation décrite dans cet article.

Après avoir identifié [!DNL CPM] le numéro du mois précédent, [!DNL Adobe] procédez comme suit :

* Créez une facture et facturez-la selon [!DNL CPM] le taux de chaque flux de données abonné.
* Paiement des fournisseurs de données (vendeurs) dus à [!DNL CPM] votre utilisation rapportée.

>[!IMPORTANT]
>
>En tant qu'acheteur, tous les totaux d'impressions signalés doivent être vrais et précis. Si vous ne parvenez pas à signaler les totaux d'impressions selon le cinquième jour de chaque mois, vous devez inclure les totaux pour le mois non signalé dans le mois suivant.

<br> 

## Affecter des impressions au niveau du flux en fonction des règles de qualification des caractéristiques {#assign-impressions}

Le cas [!UICONTROL Activation] d'utilisation vous permet d'utiliser des caractéristiques dans le flux de données correspondant pour créer des segments dans [le créateur](../../../features/segments/segment-builder.md#topic_E166819D26B94A868376BA54E10E4B74) de segments et mapper ces segments à une destination. Opérateurs [!UICONTROL AND]booléens, [!UICONTROL OR]et [!UICONTROL NOT] vous permettent de définir les conditions de qualification des caractéristiques et des segments.

Lorsque [vous signalez l'utilisation CPM au niveau du flux de données](#feed-level-report), vous devez allouer des impressions proportionnellement pour chaque flux de données, selon les [!DNL Boolean] opérateurs utilisés dans les règles de qualification des caractéristiques. Le tableau suivant indique comment allouer correctement les impressions par type de règle ou de caractéristique booléenne.

>[!TIP]
>[Utiliser l'utilisation CPM au niveau du segment](#segment-level-report) pour que les rapports au niveau du flux de données soient automatiquement générés par Audience Manager.

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
   <td colname="col2"> <p>Appliquez 100 % des totaux d'impression remis à l'ensemble des caractéristiques du fournisseur dans un segment basé sur des règles qui utilise une condition <span class="wintitle"> ET</span> booléenne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> OU</span> </p> </td> 
   <td colname="col2"> <p>Appliquez l'attribution pondérée des totaux d'impression remis à toutes les caractéristiques du fournisseur d'un segment basé sur des règles utilisant une condition OU booléenne. L'allocation pondérée est calculée à l'aide de la formule suivante :</p><p><code>(Population de caractéristiques/Population de segments) * Nombre d'impressions * Coût du CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> SAUF</span> </p> </td> 
   <td colname="col2"> <p>Appliquez 100 % des totaux d'impression remis à l'ensemble des caractéristiques du fournisseur dans un segment basé sur des règles qui utilise une condition <span class="wintitle"> NOT</span> booléenne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segments algorithmiques </p> </td> 
   <td colname="col2"> <p>Appliquez 100 % des totaux d'impression remis à tous les flux de fournisseur d'un segment contenant des caractéristiques algorithmiques. </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## Exemples de facturation {#billing-examples}

Les exemples ci-dessous montrent comment l'affectation [!DNL CPM] d'utilisation est effectuée au niveau du flux de données.

>[!IMPORTANT]
>Nous vous recommandons de [reporter l'utilisation CPM au niveau](#segment-level-report) du segment pour que ce processus soit effectué automatiquement.

Examinons le scénario suivant :

![facturation-exemples](assets/billing-examples.png)

<br> 

### Cas 1 : Segments avec règles de qualification ET

Ce segment contient trois caractéristiques provenant de fournisseurs de données distincts. La qualification des segments étant basée sur une [!UICONTROL AND] condition, les visiteurs doivent se rendre compte des caractéristiques des trois flux pour remplir le segment.

![](assets/billing-segment-and.png)

Avec une [!UICONTROL AND] condition, vous devez affecter 100 % des impressions reçues pendant le mois aux trois fournisseurs de données. Dans la [!UICONTROL Audience Marketplace > Payables] section, vous créditez chaque fournisseur de 1 000 000 impressions.

Cet exemple s'applique aux segments qui utilisent [!DNL Boolean][!UICONTROL NOT] des opérateurs ou aux segments contenant des caractéristiques algorithmiques.

<br> 

### Cas 2 : Segments avec règles de qualification OU

Ce segment contient trois caractéristiques provenant de fournisseurs de données distincts. La qualification des segments étant basée sur une [!UICONTROL OR] condition, les visiteurs doivent effectuer au moins l'une des trois caractéristiques pour remplir le segment.

Nous ne pouvons pas déterminer la caractéristique responsable d'une impression car la qualification est basée sur une [!UICONTROL OR] condition. Par conséquent, dans [!UICONTROL Audience Marketplace > Payables] la section, vous créditez chaque fournisseur avec une allocation pondérée du nombre total d'impressions, en fonction de la population de caractéristiques.

![facturation-segment-ou](assets/billing-segment-or.png)

<br> 

### Cas 3 : Segments avec cas d'utilisation de modélisation et d'activation

Cet exemple décrit l'attribution basée sur deux cas d'utilisation des flux de données - Modélisation et Activation. Dans cet exemple, nous examinons deux fournisseurs de données avec les informations suivantes :

![data-feed](assets/feed-use-cases.png)

Dans le tableau ci-dessous, le segment X contient deux caractéristiques, T 1 et T 2, avec la règle de segment T 1 OU T 2, où :

* T 1 est une caractéristique du flux de données A ;
* T 2 est une caractéristique algorithmique modélisée après des caractéristiques tierces issues du flux de données A et du flux de données B.

Le segment est associé à une destination et 1 000 000 impressions sont saisies pour ce segment au cours d'un mois, à l'aide de la création de rapports [au niveau du segment](#segment-level-report).

Parmi ces 1 000 000 impressions :

* T 1 comprend 40 % de la population de segments, ce qui traduit 4 000 impressions pour le flux A.
* T 2 comprend 60 % de la population de segments, ce qui traduit 600 000 impressions pour le flux A et le flux B.

Au niveau d'un flux de données, la manière dont les impressions sont allouées est :

* Le flux de données A reçoit 600 000 impressions de caractéristique T 2 (modélisée sur des caractéristiques issues du flux de données A et du flux de données B, de sorte qu'elles reçoivent toutes les deux les impressions) et 400 000 impressions de caractéristique T 1 (une caractéristique issue du flux de données A), totalisant 1 000 000 impressions.
* Le flux de données B reçoit 600 000 impressions de caractéristique T 2 (voir explication ci-dessus) et 0 impression de la caractéristique T 1.

La ventilation à un seul coup d'œil par flux de données et cas d'utilisation se présente comme suit :

![flux-ventilation](assets/feed-breakdown-alt.png)

<br> 

## Attribution de facturation et d'impression pour les flux de données de frais plats {#billing-flat-fee}

Un flux de données de frais fixe facture un montant fixe chaque mois, quel que soit le moment où commence l'abonnement ou le nombre d'impressions que vous utilisez. Les frais ne sont pas calculés au prorata pour un mois partiel ou des intervalles. A l'instar de la facturation CPM, Adobe génère une facture et facture le montant mensuel et plat des flux de données abonnés.

Supposons, par exemple, que vous ayez décidé d'activer certaines caractéristiques dans un flux au milieu du mois. Vous serez toujours facturé à la fréquence complète, quel que soit le moment où vous avez démarré l'abonnement ou que vous avez activé des caractéristiques spécifiques.