---
description: Les fichiers journaux activables vous permettent de capturer des signaux multimédia à partir de fichiers journaux de serveur publicitaire afin de créer des caractéristiques en Audience Manager. Capturez les impressions, les clics et les conversions à partir des serveurs d’annonces en tant que caractéristiques sans avoir à ajouter de pixels.
keywords: journaux exploitables, alf, ALF
seo-description: Les fichiers journaux activables vous permettent de capturer des signaux multimédia à partir de fichiers journaux de serveur publicitaire afin de créer des caractéristiques en Audience Manager. Capturez les impressions, les clics et les conversions à partir des serveurs d’annonces en tant que caractéristiques sans avoir à ajouter de pixels.
seo-title: Fichiers journaux pratiques
solution: Audience Manager
title: Fichiers journaux pratiques
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Log Files
translation-type: tm+mt
source-git-commit: a4d86fb0324a03002123f8713eb9786b5b74c38e
workflow-type: tm+mt
source-wordcount: '1609'
ht-degree: 3%

---


# Fichiers journaux pratiques {#actionable-log-files}

[!UICONTROL Actionable Log Files] vous permet de capturer des données multimédia à partir de fichiers journaux de serveur d’annonces et d’utiliser les données pour créer des caractéristiques en Audience Manager. Capturez les impressions, les clics et les conversions à partir des serveurs d’annonces en tant que caractéristiques sans avoir à ajouter [pixels](../../integration/media-data-integration/impression-data-pixels.md).

>[!NOTE]
>
>Les styles de texte (`monospaced text`, *italiques*, crochets `[ ]` `( )`, etc.) dans ce document, indiquez les éléments de code et les options. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../reference/code-style-elements.md).

## Rôle {#purpose}

[!UICONTROL Actionable Log Files] rationalisez la manière dont vous capturez les impressions, les clics et les conversions à partir des serveurs d’annonces. Utilisez ces informations pour la segmentation des utilisateurs sans avoir à utiliser manuellement des pixels médias pour envoyer des attributs de campagne à [!DNL Audience Manager].

## Prise en main {#getting-started}

Pour commencer avec [!UICONTROL Actionable Log Files], vous devez importer les données du journal dans [!DNL Audience Manager]. Les liens suivants vous aideront à démarrer :

* Pour [!UICONTROL Google Campaign Manager] journaux, voir [Importer des fichiers de données Google Campaign Manager en Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *et* contacter votre [!DNL Audience Manager] consultant.
* Pour [!UICONTROL Google Ad Manager] (anciennement Google DFP), voir [Importer des fichiers de données Google Ad Manager dans l’Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *et* contacter votre [!DNL Audience Manager] consultant.
* Pour consulter d’autres journaux de serveur d’annonces, voir [Fichiers de données et de métadonnées](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *et* contactez votre [!DNL Audience Manager] consultant.

Si vous importez déjà des données de journal dans [!DNL Audience Manager], demandez à votre [!DNL Audience Manager] consultant ou [service à la clientèle](https://helpx.adobe.com/fr/contact/enterprise-support.ec.html) d&#39;activer [!UICONTROL Actionable Log Files] pour vous.

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

-->

## Utilisation de fichiers journaux utilisables {#working-with-actionable-log-files}

Avec [!UICONTROL Actionable Log Files], les informations des journaux du serveur publicitaire sont capturées dans [!DNL Audience Manager] de la même manière que vous capturiez les données des interactions du site Web en temps réel. [!DNL Audience Manager] se connecte à votre enregistrement de journal de serveur d’annonces, analyse les informations des journaux et envoie les données du journal sous forme de signaux exploitables à nos serveurs [ de collecte de ](../../reference/system-components/components-data-collection.md#dcs-pcs)données.

Vous devez encore configurer des caractéristiques basées sur des règles pour capturer les signaux exploitables. Découvrez comment configurer des caractéristiques basées sur des règles dans l&#39;[interface utilisateur de l&#39;Audience Manager](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) ou en utilisant nos [outils de gestion en bloc](../../reference/bulk-management-tools/bulk-create.md). Faites défiler l&#39;écran jusqu&#39;à la section [Signaux actifs](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) pour obtenir une liste de toutes les clés que vous pouvez utiliser dans les caractéristiques basées sur des règles.

>[!IMPORTANT]
>
>Nous vous recommandons d’implémenter [!UICONTROL Actionable Log Files] *au lieu de* [Appels en pixels](../../integration/media-data-integration/impression-data-pixels.md). Nous décourageons l&#39;utilisation des deux options, car cela conduit à une augmentation du nombre de fréquences pour les caractéristiques.

## Signaux actifs {#actionable-signals}

Les signaux sont les [plus petites unités de données](../../reference/signal-trait-segment.md) dans [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] vous permet de capturer les valeurs de l’annonceur, de l’unité opérationnelle, de l’élément créatif et de la campagne dans les événements d’impression, les événements de clic et les événements de conversion en tant que signaux provenant des journaux du serveur d’annonces.

N’oubliez pas que pour utiliser ces informations pour la création et la segmentation d’audiences, vous devez vous-même configurer les caractéristiques basées sur des règles.

### Signaux utilisables à partir des journaux Google Campaign Manager {#dcm-logs-signals}

Le tableau liste les signaux activables provenant des fichiers journaux [!DNL Google Campaign Manager] :

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nom d'en-tête dans le fichier journal </th> 
   <th colname="col2" class="entry"> Signal </th> 
   <th colname="col3" class="entry"> Description </th> 
   <th colname="col4" class="entry"> Exemple de valeur </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Activity ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col3"> <p>Disponible uniquement pour les événements de conversion. </p> <p>Représente l’identifiant numérique de l’activité de conversion dans Google Campaign Manager. Ce champ correspond à l’ID d’Activité de Google Campaign Manager. </p> <p> <p>Conseil : Vous pouvez capturer plusieurs activités de conversion ou des données spécifiques à partir de Google Campaign Manager. Créez des caractéristiques à l’aide de <code> d_conversion = activity ID</code> pour chaque activité de conversion à partir de Google Campaign Manager. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Disponible uniquement pour les événements de conversion. </p> <p>Ce champ correspond à l’ID de conversion dans Google Campaign Manager. Indique l’activité précédant la conversion d’utilisateur à partir du Gestionnaire de Campaign de Google. </p> <p>Les valeurs acceptées sont les suivantes : </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> pour les conversions après clic. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> pour les conversions après impression. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> pour les conversions sans correspondance. Impossible de faire correspondre la conversion à une activité précédente. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">Date et heure UTC pour le événement d’impression, de clic ou de conversion. Représenté en microsecondes depuis 1970-01-01 00:00:00 UTC.</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>Code d’intégration de la source de données de l’annonceur. Notez que ceci n’est pas lié aux sources de données d’Audience Manager.</p> <p>Ce champ correspond à l’identifiant du groupe publicitaire de Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>ID d'unité opérationnelle. Ce champ correspond à l’identifiant publicitaire de Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>ID Campaign fourni par Google Campaign Manager.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>ID de création fourni par Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> Le montant des ventes en USD, au pouvoir de -6. Multiplier par 1 000 000 pour voir comme un montant en dollars.</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Indique le type d'événement. L’Audience Manager lit le type d'événement à partir du nom du fichier journal de Google Campaign Manager et le transforme en un signal utilisable. </p> <p>Les valeurs acceptées sont les suivantes : </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> pour les impressions. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> pour les clics. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> pour les conversions. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>ID de la source de données que vous utilisez pour capturer les données Google Campaign Manager. Voir <a href="../../features/manage-datasources.md#create-data-source"> Comment créer une source de données</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Les signaux décrits dans le tableau sont capturés dans [!DNL Audience Manager] comme un appel `HTTP` en temps réel. L&#39;exemple d&#39;appel ci-dessous contient des informations sur un événement de conversion de [!DNL Google Campaign Manager]. Les appels ne doivent pas nécessairement inclure *tous* les signaux dans l&#39;exemple d&#39;appel.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

Pour un fichier journal de taille moyenne [!DNL Google Campaign Manager] de 2 millions de lignes, toutes les caractéristiques créées à partir de signaux exploitables sont réalisées dans l&#39;heure environ après le traitement des journaux.

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>L&#39;horodatage événement fourni dans les journaux [!DNL Google Campaign Manager] sera respecté et transmis à [!UICONTROL Data Collection Servers].
>
>* Si un horodatage n&#39;est pas disponible pour une ligne de données dans le fichier journal [!DNL Google Campaign Manager], nous utilisons l&#39;heure de l&#39;appel `HTTP` comme horodatage événement.
>* Si la ligne de données du fichier journal [!DNL Google Campaign Manager] contient un horodatage incorrect, nous ignorons la ligne entière.


<br> 

### Signaux utilisables à partir des journaux [!DNL Google Ad Manager] {#ad-manager-logs-signals}

Le tableau liste les signaux activables provenant des fichiers journaux [!DNL Google Ad Manager] :


| Nom d&#39;en-tête dans le fichier journal | Signal | Description |
---------|----------|---------
| `LineItemId` | `d_lineitem` | ID numérique de l’élément de ligne Ad Manager livré |
| `OrderId` | `d_orderid` | ID numérique de la commande du gestionnaire d’annonces qui contenait l’élément de ligne livré et le créatif. |
| `CreativeId` | `d_creative` | ID numérique du créatif Ad Manager diffusé. |
| `-` | `d_event` | Indique le type d&#39;événement. L’Audience Manager lit le type d&#39;événement du nom du fichier journal d’Ad Manager et le transforme en signal utilisable. Les valeurs acceptées sont les suivantes : <br> <ul><li>d_événement = imp pour les impressions.</li><li>d_événement = clic pour les clics.</li><li>d_événement = conv pour les conversions et les activités.</li></ul> |
| `-` | `d_src` | ID de la source de données que vous utilisez pour capturer les données d’Ad Manager. Voir [Comment créer une source de données](/help/using/features/manage-datasources.md). |

Les signaux décrits dans le tableau sont capturés en Audience Manager comme un appel HTTP en temps réel. L’exemple d’appel ci-dessous contient des informations sur un événement de conversion provenant de Google Ad Manager. Les appels n&#39;ont pas nécessairement à inclure tous les signaux dans l&#39;exemple d&#39;appel.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>L&#39;horodatage événement fourni dans les journaux [!DNL Google Ad Manager] sera respecté et transmis à [!UICONTROL Data Collection Servers].
>
>* Si un horodatage n&#39;est pas disponible pour une ligne de données dans le fichier journal [!DNL Google Ad Manager], nous utilisons l&#39;heure de l&#39;appel `HTTP` comme horodatage événement.
>* Si la ligne de données du fichier journal [!DNL Google Ad Manager] contient un horodatage incorrect, nous ignorons la ligne entière.


<br> 

### Signaux utilisables à partir des journaux génériques du serveur d’annonces {#generic-logs-signals}

Tout d’abord, vous devez déposer vos journaux de serveur d’annonces dans nos compartiments Amazon S3. Pour ce faire, consultez [Fichiers de données pour les rapports d&#39;Audience Optimization et les fichiers journaux utilisables](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *et* contactez votre [!DNL Audience Manager] consultant. Le tableau liste les signaux exploitables provenant des fichiers journaux génériques :

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nom d'en-tête dans le fichier journal </th> 
   <th colname="col2" class="entry"> Signal </th> 
   <th colname="col3" class="entry"> Description </th> 
   <th colname="col4" class="entry"> Exemple de valeur </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Event-Type</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Indique si une conversion correspond ou non. Les options incluent : </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 0</code> Impression </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code> Cliquez sur </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> Non attribué ou inconnu </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> Date et heure UTC pour le événement d’impression, de clic ou de conversion. Utilisez le format <code>yyyy-MM-dd HH:mm:ss</code>. </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>Code d’intégration de la source de données de l’annonceur. Notez que ce champ n'est pas lié aux <a href="../../features/datasources-list-and-settings.md">sources de données d'Audience Manager.</a></p></td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>BU-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>ID d'unité opérationnelle.  </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>ID Campaign du fichier journal.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>ID créatif du fichier journal. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> Achat ou autre montant de conversion. Type de données : Flottant. </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Indique le type d'événement. L'Audience Manager lit le type d'événement du nom du fichier journal et le transforme en signal utilisable. Voir <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">conventions d’attribution de noms aux fichiers journaux</a>. </p> <p>Les valeurs acceptées sont les suivantes : </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> pour les impressions. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> pour les clics. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> pour les conversions. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>ID de la source de données que vous utilisez pour capturer les données du journal. Voir <a href="../../features/manage-datasources.md#create-data-source"> Comment créer une source de données</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Les signaux décrits dans le tableau sont capturés dans [!DNL Audience Manager] comme un appel `HTTP` en temps réel. Les appels ne doivent pas nécessairement inclure *tous* les signaux dans l&#39;exemple d&#39;appel.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Utilisation de signaux tactiles dans l&#39;interface utilisateur de l&#39;Audience Manager {#actionable-signals-in-ui}

Vous pouvez vue vos signaux interactifs entrants dans l&#39;interface [Signals Search](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md).

Accédez à **Données d&#39;Audience** (1) > **Signaux** (2) > **Rechercher** (3) et sélectionnez le filtre **Fichiers journaux utilisables** (4).

![Signaux utilisables dans l’interface utilisateur](/help/using/integration/assets/alf-in-signals.png)

Pour créer des caractéristiques basées sur des règles à l’aide de vos signaux exploitables, sélectionnez **Fichiers journaux exploitables** (1), sélectionnez les signaux exploitables à utiliser comme règles de caractéristiques (2), puis appuyez sur **Créer un trait à partir des signaux sélectionnés** (3).

![Créer des caractéristiques à partir de signaux](/help/using/integration/assets/alf-create-trait.png)


## Cas d’utilisation {#use-cases}

L&#39;un des avantages de la mise en oeuvre de [!UICONTROL Actionable Log Files] est l&#39;option d&#39;appliquer des contrôles [récence et fréquence](../../features/segments/recency-and-frequency.md) à toute [caractéristique basée sur des règles](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) qui contient des signaux exploitables. Cela vous permet, par exemple, de limiter le nombre de fois où un utilisateur voit apparaître un élément créatif particulier dans une campagne multimédia. Consultez la section [Suppression instantanée de plusieurs périphériques](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) pour savoir comment procéder. Les autres cas d&#39;utilisation sont les suivants :

### Recibler les utilisateurs

Retargez les utilisateurs qui ont vu la version 123 de Creative mais n’ont pas cliqué ou converti pour afficher la version 456. Procédez comme suit :

1. Créez une caractéristique pour capturer les utilisateurs qui ont vu le contenu créatif. Supposons que vous nommiez le trait [!DNL Creative Trait 123]. Utilisez la règle de caractéristiques :

   `d_creative == 123 AND d_event == imp`

2. Créez une caractéristique pour capturer les utilisateurs qui cliquent ou convertissent. Supposons que vous nommiez celui-ci [!DNL Click and Converter]. Utilisez la règle de caractéristiques :

   `d_event == click OR d_event=conv`

3. Créez un segment à renseigner auprès des utilisateurs qui ont vu Creative 123 mais n’ont pas cliqué ou converti. Nommez-le [!DNL Retarget Users] et utilisez la règle de segmentation :

   `Creative Trait 123 AND NOT Click and Converter`

4. Faites correspondre le segment [!DNL Retarget Users] à une destination et aux utilisateurs de cible de la destination avec Creative 456.

### Utilisation de l’Activité Google Campaign Manager Floodlight dans les rapports d’Audience Optimization ou dans Audience Lab

[Floodlight ](https://support.google.com/dcm/partner/answer/4293719?hl=en) permet aux annonceurs pouvant être ciblés de suivre les conversions d’utilisateurs. Avec [!UICONTROL Actionable Log Files], vous pouvez suivre les conversions [!DNL Google Campaign Manager] dans les [rapports d&#39;Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md) ou dans [laboratoire d&#39;Audience](../../features/audience-lab/audience-lab.md) :

1. Créez une caractéristique et utilisez la règle de caractéristique suivante pour capturer une conversion à partir des journaux du serveur d’annonces :

   `d_event == conv AND d_conversion == 123`

   Lors de la création de la caractéristique dans l&#39;Audience Manager [!UICONTROL UI], sélectionnez [!UICONTROL Conversion] comme [!UICONTROL Event Type].

2. Une fois que vous avez créé la caractéristique, la conversion commencera à être rapportée dans [!UICONTROL Audience Optimization Reports] et dans [!UICONTROL Audience Lab].

>[!MORELIKETHIS]
>
>* [Importer les fichiers de données Google Campaign Manager dans l’Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Rapports d’Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

