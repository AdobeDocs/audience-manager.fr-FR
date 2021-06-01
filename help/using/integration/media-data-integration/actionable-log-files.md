---
description: Les fichiers journaux pratiques vous permettent de capturer des signaux multimédia à partir de fichiers journaux de serveur de publicités afin de créer des caractéristiques dans Audience Manager. Capturez les impressions, les clics et les conversions à partir des serveurs d’annonces en tant que caractéristiques sans avoir à ajouter de pixels.
keywords: logs activables, alf, ALF
seo-description: Les fichiers journaux pratiques vous permettent de capturer des signaux multimédia à partir de fichiers journaux de serveur de publicités afin de créer des caractéristiques dans Audience Manager. Capturez les impressions, les clics et les conversions à partir des serveurs d’annonces en tant que caractéristiques sans avoir à ajouter de pixels.
seo-title: Fichiers journaux pratiques
solution: Audience Manager
title: Fichiers journaux pratiques
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Fichiers journaux
exl-id: bd499931-4e02-4f64-82ba-46ef7c4ffd3c
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1611'
ht-degree: 3%

---

# Fichiers journaux pratiques {#actionable-log-files}

[!UICONTROL Actionable Log Files] vous permettent de capturer des données multimédia à partir de fichiers journaux du serveur d’annonces et d’utiliser les données pour créer des caractéristiques dans Audience Manager. Capturez les impressions, les clics et les conversions à partir des serveurs de publicités en tant que caractéristiques sans avoir à ajouter [pixels](../../integration/media-data-integration/impression-data-pixels.md).

>[!NOTE]
>
>Les styles de texte (`monospaced text`, *italiques*, crochets `[ ]` `( )`, etc.) dans ce document, indiquez les éléments de code et les options. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../reference/code-style-elements.md).

## Rôle {#purpose}

[!UICONTROL Actionable Log Files] rationaliser la manière dont vous capturez les impressions, les clics et les conversions à partir des serveurs d’annonces. Utilisez ces informations pour la segmentation des utilisateurs sans avoir à utiliser manuellement des supports de pixel pour envoyer des attributs de campagne à [!DNL Audience Manager].

## Prise en main {#getting-started}

Pour commencer à utiliser [!UICONTROL Actionable Log Files], vous devez importer les données du journal dans [!DNL Audience Manager]. Les liens suivants vous aideront à démarrer :

* Pour [!UICONTROL Google Campaign Manager] journaux, voir [Importer des fichiers de données Google Campaign Manager dans l’Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *et* contactez votre [!DNL Audience Manager] consultant.
* Pour [!UICONTROL Google Ad Manager] (anciennement Google DFP), voir [Importation de fichiers de données Google Ad Manager dans l’Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *et* contactez votre [!DNL Audience Manager] consultant.
* Pour consulter d’autres journaux de serveur d’annonces, voir [Fichiers de données et de métadonnées](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *et* contactez votre [!DNL Audience Manager] consultant.

Si vous importez déjà des données de journal dans [!DNL Audience Manager], demandez à votre [!DNL Audience Manager] consultant ou [l’assistance clientèle](https://helpx.adobe.com/fr/contact/enterprise-support.ec.html) d’activer [!UICONTROL Actionable Log Files] pour vous.

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

-->

## Utilisation de fichiers journaux pratiques {#working-with-actionable-log-files}

Avec [!UICONTROL Actionable Log Files], les informations des journaux du serveur de publicités sont capturées dans [!DNL Audience Manager] de la même manière que vous le feriez pour capturer des données provenant d’interactions web en temps réel. [!DNL Audience Manager] se connecte à votre stockage de journaux de serveur d’annonces, analyse les informations des journaux et envoie les données de journaux sous forme de signaux pratiques à nos serveurs de collecte de  [données](../../reference/system-components/components-data-collection.md#dcs-pcs).

Vous devez toujours configurer des caractéristiques basées sur des règles pour capturer les signaux exploitables. Découvrez comment configurer des caractéristiques basées sur des règles dans l’ [interface utilisateur de l’Audience Manager](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) ou en utilisant nos [outils de gestion en bloc](../../reference/bulk-management-tools/bulk-create.md). Faites défiler jusqu’à la section [Signaux pratiques](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) pour obtenir la liste de toutes les clés que vous pouvez utiliser dans les caractéristiques basées sur des règles.

>[!IMPORTANT]
>
>Nous vous recommandons d’implémenter [!UICONTROL Actionable Log Files] *au lieu de* [Appels de pixel](../../integration/media-data-integration/impression-data-pixels.md). Nous décourageons l’utilisation des deux options, car cela entraîne une augmentation du nombre de fréquences pour les caractéristiques.

## Signaux pratiques {#actionable-signals}

Les signaux sont les [plus petites unités de données](../../reference/signal-trait-segment.md) dans [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] vous permettent de capturer des valeurs d’annonceur, d’unité opérationnelle, de créatif et de campagne dans des événements d’impression, des événements de clic et des événements de conversion en tant que signaux provenant de journaux de serveur d’annonces.

N’oubliez pas que pour utiliser ces informations pour la création et la segmentation d’audiences, vous devez configurer vous-même les caractéristiques basées sur des règles.

### Signaux pratiques à partir des journaux Google Campaign Manager {#dcm-logs-signals}

Le tableau répertorie les signaux exploitables provenant des fichiers journaux [!DNL Google Campaign Manager] :

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nom de l’en-tête dans le fichier journal </th> 
   <th colname="col2" class="entry"> Signal </th> 
   <th colname="col3" class="entry"> Description </th> 
   <th colname="col4" class="entry"> Exemple de valeur </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Activity ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col3"> <p>Disponible uniquement pour les événements de conversion. </p> <p>Représente l’identifiant numérique de l’activité de conversion dans Google Campaign Manager. Ce champ correspond à l’ID d’activité de Google Campaign Manager. </p> <p> <p>Conseil : Vous pouvez capturer plusieurs activités de conversion ou des activités de conversion spécifiques à partir de Google Campaign Manager. Créez des caractéristiques à l’aide de <code> d_conversion = activity ID</code> pour chaque activité de conversion à partir de Google Campaign Manager. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Disponible uniquement pour les événements de conversion. </p> <p>Ce champ correspond à l’ID de conversion dans Google Campaign Manager. Indique l’activité précédant la conversion de l’utilisateur à partir de Google Campaign Manager. </p> <p>Les valeurs acceptées sont les suivantes : </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> pour les conversions après clic. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> pour les conversions après impression. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> pour les conversions sans correspondance. La conversion ne peut pas être mise en correspondance avec une activité précédente. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">Date et heure UTC de l’événement d’impression, de clic ou de conversion. Représenté en microsecondes depuis 1970-01-01 00:00:00 UTC.</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>Code d’intégration de la source de données de votre annonceur. Notez que cela n’est pas lié aux sources de données d’Audience Manager.</p> <p>Ce champ correspond à l’identifiant de groupe publicitaire de Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>Identifiant de l’unité opérationnelle. Ce champ correspond à l’identifiant publicitaire de Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>Identifiant de campagne fourni par Google Campaign Manager.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>ID d’élément créatif fourni par Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> Le montant des ventes en USD, à la puissance de -6. Multipliez par 1 000 000 pour voir comme un dollar.</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Indique le type d’événement. L’Audience Manager lit le type d’événement à partir du nom de fichier journal de Google Campaign Manager et le transforme en signal exploitable. </p> <p>Les valeurs acceptées sont les suivantes : </p> <p> 
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
   <td colname="col3"> <p>L’identifiant de la source de données que vous utilisez pour capturer les données de Google Campaign Manager. Voir <a href="../../features/manage-datasources.md#create-data-source"> Comment créer une source de données</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Les signaux décrits dans le tableau sont capturés dans [!DNL Audience Manager] comme un appel `HTTP` en temps réel. L’exemple d’appel ci-dessous contient des informations sur un événement de conversion de [!DNL Google Campaign Manager]. Les appels ne doivent pas nécessairement inclure *tous* les signaux dans l’exemple d’appel.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

Pour un fichier journal de taille [!DNL Google Campaign Manager] moyenne de 2 millions de lignes, toutes les caractéristiques créées à partir de signaux exploitables sont réalisées environ une heure après le traitement des logs.

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>L’horodatage de l’événement fourni dans les journaux [!DNL Google Campaign Manager] sera respecté et transmis à [!UICONTROL Data Collection Servers].
>
>* Si aucun horodatage n’est disponible pour une ligne de données dans le fichier journal [!DNL Google Campaign Manager] , nous utilisons l’heure de l’appel `HTTP` comme horodatage de l’événement.
>* Si la ligne de données du fichier journal [!DNL Google Campaign Manager] contient un horodatage incorrect, nous ignorons la ligne entière.


<br> 

### Signaux pratiques à partir de [!DNL Google Ad Manager] journaux {#ad-manager-logs-signals}

Le tableau répertorie les signaux exploitables provenant des fichiers journaux [!DNL Google Ad Manager] :


| Nom de l’en-tête dans le fichier journal | Signal | Description |
---------|----------|---------
| `LineItemId` | `d_lineitem` | Identifiant numérique pour l’élément de ligne Ad Manager diffusé. |
| `OrderId` | `d_orderid` | Identifiant numérique de la commande du gestionnaire d’annonces qui contenait l’élément de ligne diffusé et le contenu créatif. |
| `CreativeId` | `d_creative` | Identifiant numérique pour le créatif Ad Manager diffusé. |
| `-` | `d_event` | Indique le type d’événement. L’Audience Manager lit le type d’événement à partir du nom du fichier journal du gestionnaire d’annonces publicitaires et le transforme en signal exploitable. Les valeurs acceptées sont les suivantes : <br> <ul><li>d_event = imp pour les impressions.</li><li>d_event = clic pour les clics.</li><li>d_event = conv pour les conversions et les activités.</li></ul> |
| `-` | `d_src` | L’identifiant de la source de données que vous utilisez pour capturer les données Ad Manager. Voir [Comment créer une source de données](/help/using/features/manage-datasources.md). |

Les signaux décrits dans le tableau sont capturés en Audience Manager comme un appel HTTP en temps réel. L’exemple d’appel ci-dessous contient des informations sur un événement de conversion de Google Ad Manager. Les appels ne doivent pas nécessairement inclure tous les signaux dans l’exemple d’appel.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>L’horodatage de l’événement fourni dans les journaux [!DNL Google Ad Manager] sera respecté et transmis à [!UICONTROL Data Collection Servers].
>
>* Si aucun horodatage n’est disponible pour une ligne de données dans le fichier journal [!DNL Google Ad Manager] , nous utilisons l’heure de l’appel `HTTP` comme horodatage de l’événement.
>* Si la ligne de données du fichier journal [!DNL Google Ad Manager] contient un horodatage incorrect, nous ignorons la ligne entière.


<br> 

### Signaux pratiques à partir des journaux de serveur de publicités génériques {#generic-logs-signals}

Tout d’abord, vous devez déposer vos journaux de serveur d’annonces dans nos compartiments Amazon S3. Pour ce faire, lisez [Fichiers de données pour les rapports d’Audience Optimization et les fichiers journaux pratiques](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *et* contactez votre [!DNL Audience Manager] consultant. Le tableau répertorie les signaux exploitables provenant de fichiers journaux génériques :

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nom de l’en-tête dans le fichier journal </th> 
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
   <td colname="col3"> <p> Date et heure UTC de l’événement d’impression, de clic ou de conversion. Utilisez le format <code>yyyy-MM-dd HH:mm:ss</code> . </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>Code d’intégration de la source de données de votre annonceur. Notez que ce champ n’est pas lié aux <a href="../../features/datasources-list-and-settings.md">sources de données d’Audience Manager.</a></p></td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>BU-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>Identifiant de l’unité opérationnelle.  </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>Identifiant de campagne du fichier journal.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>ID d’élément créatif du fichier journal. </p> </td> 
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
   <td colname="col3"> <p>Indique le type d’événement. L’Audience Manager lit le type d’événement à partir du nom du fichier journal et le transforme en signal exploitable. Voir <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">conventions d’appellation des fichiers journaux</a>. </p> <p>Les valeurs acceptées sont les suivantes : </p> <p> 
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
   <td colname="col3"> <p>L’identifiant de la source de données que vous utilisez pour capturer les données de journal. Voir <a href="../../features/manage-datasources.md#create-data-source"> Comment créer une source de données</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Les signaux décrits dans le tableau sont capturés dans [!DNL Audience Manager] comme un appel `HTTP` en temps réel. Les appels ne doivent pas nécessairement inclure *tous* les signaux dans l’exemple d’appel.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Utilisation de signaux pratiques dans l’interface utilisateur de l’Audience Manager {#actionable-signals-in-ui}

Vous pouvez afficher vos signaux activables entrants dans l’interface [Recherche de signaux](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md) .

Accédez à **Données d’audience** (1) > **Signaux** (2) > **Rechercher** (3) et sélectionnez le filtre **Fichiers journaux pratiques** (4).

![Signaux pratiques dans l’interface utilisateur](/help/using/integration/assets/alf-in-signals.png)

Pour créer des caractéristiques basées sur des règles à l’aide de vos signaux activables, sélectionnez **Fichiers journaux activables** (1), sélectionnez les signaux activables que vous souhaitez utiliser comme règles de caractéristiques (2), puis appuyez sur **Créer une caractéristique à partir des signaux sélectionnés** (3).

![Création de caractéristiques à partir de signaux](/help/using/integration/assets/alf-create-trait.png)


## Cas d’utilisation {#use-cases}

L’un des avantages de l’implémentation de [!UICONTROL Actionable Log Files] est l’option d’application des contrôles [récence et fréquence](../../features/segments/recency-and-frequency.md) à toute [caractéristique basée sur des règles](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) contenant des signaux exploitables. Cela vous permet, par exemple, de limiter la fréquence à laquelle un utilisateur voit apparaître un élément créatif particulier dans une campagne multimédia. Lisez la section [Suppression instantanée multi-appareils](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) pour savoir comment procéder. Voici d’autres cas pratiques :

### Utilisateurs de Reciblage

Reciblez les utilisateurs qui ont vu creative 123 mais n’ont pas cliqué ni converti et leur ont présenté creative 456. Procédez comme suit :

1. Créez une caractéristique pour capturer les utilisateurs qui ont vu le contenu créatif. Supposons que vous nommiez la caractéristique [!DNL Creative Trait 123]. Utilisez la règle de caractéristique :

   `d_creative == 123 AND d_event == imp`

2. Créez une caractéristique pour capturer les utilisateurs qui cliquent ou convertissent. Supposons que vous nommiez celui-ci [!DNL Click and Converter]. Utilisez la règle de caractéristique :

   `d_event == click OR d_event=conv`

3. Créez un segment à remplir avec les utilisateurs qui ont vu creative 123 mais n’ont pas cliqué ni converti. Nommez-le [!DNL Retarget Users] et utilisez la règle de segment :

   `Creative Trait 123 AND NOT Click and Converter`

4. Faites correspondre le segment [!DNL Retarget Users] à une destination et ciblez les utilisateurs dans la destination avec creative 456.

### Utilisation de l’activité Floodlight de Google Campaign Manager dans les rapports d’Audience Optimization ou dans Audience Lab

[Floodlight ](https://support.google.com/dcm/partner/answer/4293719?hl=en) permet aux annonceurs publicitaires pouvant cibler de suivre les conversions des utilisateurs. Avec [!UICONTROL Actionable Log Files], vous pouvez effectuer le suivi des conversions [!DNL Google Campaign Manager] dans les [rapports d’Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md) ou dans [Audience Lab](../../features/audience-lab/audience-lab.md) :

1. Créez une caractéristique et utilisez la règle de caractéristique suivante pour capturer une conversion à partir des journaux du serveur d’annonces :

   `d_event == conv AND d_conversion == 123`

   Lors de la création de la caractéristique dans l’Audience Manager [!UICONTROL UI], sélectionnez [!UICONTROL Conversion] comme [!UICONTROL Event Type].

2. Une fois que vous avez créé la caractéristique, la conversion commence à faire l’objet d’un rapport dans [!UICONTROL Audience Optimization Reports] et dans [!UICONTROL Audience Lab].

>[!MORELIKETHIS]
>
>* [Importation des fichiers de données Google Campaign Manager dans Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
* [Rapports d’Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

