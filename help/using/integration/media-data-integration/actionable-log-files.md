---
description: Les fichiers journaux exploitables vous permettent de capturer des signaux de média à partir des fichiers journaux du serveur de publicités afin de créer des caractéristiques dans Audience Manager. Capturez les impressions, les clics et les conversions des serveurs de publicités en tant que caractéristiques sans avoir à ajouter de pixels.
keywords: journaux exploitables, alf, ALF
seo-description: Actionable Log Files allow you to capture media signals from ad server log files to create traits in Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to append pixels.
seo-title: Actionable Log Files
solution: Audience Manager
title: Fichiers journaux pratiques
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Log Files
exl-id: bd499931-4e02-4f64-82ba-46ef7c4ffd3c
source-git-commit: b3f97cfbbd5167f03a6951fcc571368e4a0d15a4
workflow-type: tm+mt
source-wordcount: '1601'
ht-degree: 2%

---

# Fichiers journaux pratiques {#actionable-log-files}

[!UICONTROL Actionable Log Files] vous permet de capturer des données multimédia à partir des fichiers journaux du serveur de publicités et d’utiliser les données pour créer des caractéristiques dans Audience Manager. Capturez les impressions, les clics et les conversions des serveurs de publicités en tant que caractéristiques sans avoir à ajouter [pixels](../../integration/media-data-integration/impression-data-pixels.md).

>[!NOTE]
>
>Les styles de texte (`monospaced text`, *italique*, crochets `[ ]` `( )`, etc.) de ce document indiquent les éléments de code et les options. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../reference/code-style-elements.md).

## Rôle {#purpose}

[!UICONTROL Actionable Log Files] rationalisez la façon dont vous capturez les impressions, les clics et les conversions à partir des serveurs de publicités. Utilisez ces informations pour la segmentation des utilisateurs et utilisatrices sans avoir à envoyer manuellement les pixels de média pour envoyer des attributs de campagne aux [!DNL Audience Manager].

## Prise en main {#getting-started}

Pour commencer à utiliser [!UICONTROL Actionable Log Files], vous devez importer les données du journal dans [!DNL Audience Manager]. Les liens suivants vous aideront à commencer :

* Pour les journaux [!UICONTROL Google Campaign Manager], voir [Importer les fichiers de données Google Campaign Manager dans Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *et* contacter votre consultant [!DNL Audience Manager].
* Pour les journaux [!UICONTROL Google Ad Manager] (anciennement Google DFP), consultez [Importation de fichiers de données Google Ad Manager dans Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *et* contactez votre consultant [!DNL Audience Manager].
* Pour obtenir d’autres journaux du serveur de publicités, consultez [Fichiers de données et de métadonnées](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *et* contactez votre consultant [!DNL Audience Manager].

Si vous importez déjà des données de journal dans [!DNL Audience Manager], demandez à votre consultant [!DNL Audience Manager] ou à l’[Assistance clientèle](https://helpx.adobe.com/fr/contact/enterprise-support.ec.html) de vous [!UICONTROL Actionable Log Files].

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/fr/contact/enterprise-support.ec.html) to get started.

-->

## Utilisation de fichiers journaux exploitables {#working-with-actionable-log-files}

Avec [!UICONTROL Actionable Log Files], les informations des journaux du serveur de publicités sont capturées de [!DNL Audience Manager] même manière que vous le feriez pour capturer des données à partir d’interactions de sites web en temps réel. [!DNL Audience Manager] se connecte au stockage des journaux de votre serveur de publicités, analyse les informations des journaux et envoie les données des journaux en tant que signaux exploitables à nos serveurs de collecte de données [Data Collection Servers](../../reference/system-components/components-data-collection.md#dcs-pcs).

Vous devez encore configurer des caractéristiques basées sur des règles pour capturer les signaux exploitables. Découvrez comment configurer des caractéristiques basées sur des règles dans l’interface utilisateur d’[Audience Manager](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) ou à l’aide de nos [outils de gestion en bloc](../../reference/bulk-management-tools/bulk-create.md). Faites défiler l’écran jusqu’à la section [ Signaux exploitables ](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) pour obtenir la liste de toutes les clés que vous pouvez utiliser dans les caractéristiques basées sur des règles.

>[!IMPORTANT]
>
>Nous vous recommandons d’implémenter [!UICONTROL Actionable Log Files] *au lieu* [ Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md). Nous déconseillons l’utilisation des deux options, car cela entraîne une augmentation des décomptes de fréquence pour les caractéristiques.

## Signaux exploitables {#actionable-signals}

Les signaux sont les [plus petites unités de données](../../reference/signal-trait-segment.md) en [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] vous permet de capturer les valeurs de l’annonceur, de l’unité opérationnelle, des créations et des campagnes dans les événements d’impression, les événements de clic et les événements de conversion comme des signaux des journaux du serveur de publicités.

>[!IMPORTANT]
>
>Les [!UICONTROL Actionable Log Files] sont pris en charge pour les serveurs de publicités suivants :
>&#x200B;> <br>
>
> * [Google Campaign Manager](#dcm-logs-signals)
> * [Google Ad Manager](#ad-manager-logs-signals)
> * [Adobe Advertising Cloud, Flashtalking et Sizmek](#generic-logs-signals)

N’oubliez pas que pour utiliser ces informations pour la création et la segmentation d’audiences, vous devez configurer vous-même les caractéristiques basées sur des règles.

### Signaux exploitables des journaux de Google Campaign Manager {#dcm-logs-signals}

Le tableau répertorie les signaux activables provenant des fichiers journaux [!DNL Google Campaign Manager] :

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
   <td colname="col3"> <p>Disponible uniquement pour les événements de conversion. </p> <p>Représente l’identifiant numérique de l’activité de conversion dans Google Campaign Manager. Ce champ est mappé à l’ID d’activité de Google Campaign Manager. </p> <p> <p>Conseil : vous pouvez capturer plusieurs activités de conversion ou des activités spécifiques à partir de Google Campaign Manager. Créez des caractéristiques à l’aide de <code> d_conversion = activity ID</code> pour chaque activité de conversion à partir de Google Campaign Manager. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Disponible uniquement pour les événements de conversion. </p> <p>Ce champ est mappé sur l’ID de conversion dans Google Campaign Manager. Indique l’activité précédant la conversion de l’utilisateur à partir de Google Campaign Manager. </p> <p>Les valeurs acceptées sont les suivantes : </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> pour les conversions après clic. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> pour les conversions après impression. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> pour les conversions non correspondantes. La conversion ne peut pas être mise en correspondance avec une activité précédente. </li> 
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
   <td colname="col3"><p>Code d’intégration de la source de données de l’annonceur. Notez que cela n’est pas lié aux sources de données Audience Manager.</p> <p>Ce champ est mappé à l’ID de groupe d’annonceurs de Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>Identifiant de l’unité opérationnelle. Ce champ est mappé à l’ID publicitaire de Google Campaign Manager. </p> </td> 
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
   <td colname="col3"> <p>Creative ID fourni par Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> Le montant des ventes en USD, à la puissance de -6. Multipliez par 1 000 000 pour obtenir un montant en dollars.</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Indique le type d’événement. Audience Manager lit le type d’événement à partir du nom du fichier journal de Google Campaign Manager et le transforme en signal exploitable. </p> <p>Les valeurs acceptées sont les suivantes : </p> <p> 
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
   <td colname="col3"> <p>Identifiant de la source de données que vous utilisez pour capturer les données du gestionnaire de campagne Google. Voir <a href="../../features/manage-datasources.md#create-data-source"> Création d’une Source de données</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Les signaux décrits dans le tableau sont capturés en [!DNL Audience Manager] comme un appel `HTTP` temps réel. L’exemple d’appel ci-dessous contient des informations sur un événement de conversion provenant de l’adresse [!DNL Google Campaign Manager]. Les appels ne doivent pas nécessairement inclure *tous* les signaux de l’exemple d’appel.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

Pour un fichier journal [!DNL Google Campaign Manager] de taille moyenne de 2 millions de lignes, toutes les caractéristiques créées à partir de signaux exploitables sont réalisées environ une heure après le traitement des journaux.

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>La date et l’heure d’événement fournies dans les journaux [!DNL Google Campaign Manager] seront respectées et transmises au [!UICONTROL Data Collection Servers].
>
>* Si aucun horodatage n’est disponible pour une ligne de données dans le fichier journal [!DNL Google Campaign Manager], nous utilisons l’heure de l’appel `HTTP` comme horodatage d’événement.
>* Si la ligne de données du fichier journal [!DNL Google Campaign Manager] contient un horodatage incorrect, nous ignorons la ligne entière.

<br> 

### Signaux exploitables des journaux [!DNL Google Ad Manager] {#ad-manager-logs-signals}

Le tableau répertorie les signaux activables provenant des fichiers journaux [!DNL Google Ad Manager] :


| Nom de l’en-tête dans le fichier journal | Signal | Description |
|---------|----------|---------|
| `LineItemId` | `d_lineitem` | Identifiant numérique de l’élément de ligne Ad Manager diffusé |
| `OrderId` | `d_orderid` | Identifiant numérique de la commande Ad Manager qui contenait l’élément de ligne diffusé et le contenu créatif. |
| `CreativeId` | `d_creative` | Identifiant numérique de la création Ad Manager diffusée. |
| `-` | `d_event` | Indique le type d’événement. Audience Manager lit le type d’événement à partir du nom du fichier journal d’Ad Manager et le transforme en signal exploitable. Les valeurs acceptées sont : <br> <ul><li>d_event = imp pour les impressions.</li><li>d_event = clic pour les clics.</li><li>d_event = conv pour les conversions et les activités.</li></ul> |
| `-` | `d_src` | Identifiant de la source de données que vous utilisez pour capturer les données Ad Manager. Voir [Comment créer une Source de données](/help/using/features/manage-datasources.md). |

Les signaux décrits dans le tableau sont capturés dans Audience Manager comme un appel HTTP en temps réel. L’exemple d’appel ci-dessous contient des informations sur un événement de conversion provenant de Google Ad Manager. Les appels ne doivent pas nécessairement inclure tous les signaux dans l&#39;exemple d&#39;appel.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>La date et l’heure d’événement fournies dans les journaux [!DNL Google Ad Manager] seront respectées et transmises au [!UICONTROL Data Collection Servers].
>
>
>* Si aucun horodatage n’est disponible pour une ligne de données dans le fichier journal [!DNL Google Ad Manager], nous utilisons l’heure de l’appel `HTTP` comme horodatage d’événement.
>* Si la ligne de données du fichier journal [!DNL Google Ad Manager] contient un horodatage incorrect, nous ignorons la ligne entière.

<br> 

### Signaux exploitables à partir des journaux des serveurs de publicités Adobe Advertising Cloud, Flashtalking et Sizmek {#generic-logs-signals}

Tout d’abord, vous devez déposer les journaux de votre serveur de publicités dans nos compartiments Amazon S3. Pour ce faire, lisez [Fichiers de données pour les rapports Audience Optimization et fichiers journaux exploitables](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *et* contactez votre consultant [!DNL Audience Manager]. Le tableau répertorie les signaux activables des fichiers journaux du serveur de publicités :

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
      <li id="li_29D3FF8919B7404297E80BACA913117A"> Impression <code> 0</code> </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code> Clic </li> 
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
   <td colname="col3"> <p>Code d’intégration de la source de données de l’annonceur. Notez que ce champ n’est pas associé aux <a href="../../features/datasources-list-and-settings.md">sources de données Audience Manager.</a></p></td> 
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
   <td colname="col3"> <p>Identifiant Creative du fichier journal. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> Montant d’achat ou autre montant de conversion. Type de données : Flottant. </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Indique le type d’événement. Audience Manager lit le type d’événement à partir du nom du fichier journal et le transforme en signal exploitable. Voir <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">conventions de dénomination des fichiers journaux</a>. </p> <p>Les valeurs acceptées sont les suivantes : </p> <p> 
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
   <td colname="col3"> <p>Identifiant de la source de données que vous utilisez pour capturer les données du journal. Voir <a href="../../features/manage-datasources.md#create-data-source"> Création d’une Source de données</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Les signaux décrits dans le tableau sont capturés en [!DNL Audience Manager] comme un appel `HTTP` temps réel. Les appels ne doivent pas nécessairement inclure *tous* les signaux de l’exemple d’appel.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Utilisation de signaux exploitables dans l’interface utilisateur d’Audience Manager {#actionable-signals-in-ui}

Vous pouvez afficher vos signaux activables entrants dans l’interface [ Recherche de signaux ](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md).

Accédez à **Données d’audience** (1) > **Signaux** (2) > **Rechercher** (3) et sélectionnez le filtre **Fichiers journaux exploitables** (4).

![ Signaux exploitables dans l’interface utilisateur ](/help/using/integration/assets/alf-in-signals.png)

Pour créer des caractéristiques basées sur des règles à l’aide de vos signaux activables, sélectionnez **Fichiers journaux activables** (1), sélectionnez les signaux activables que vous souhaitez utiliser comme règles de caractéristique (2), puis appuyez sur **Créer une caractéristique à partir des signaux sélectionnés** (3).

![Création de caractéristiques à partir de signaux](/help/using/integration/assets/alf-create-trait.png)


## Cas d’utilisation {#use-cases}

L’un des avantages de l’implémentation de [!UICONTROL Actionable Log Files] est la possibilité d’appliquer des contrôles [récence et fréquence](../../features/segments/recency-and-frequency.md) à toutes les caractéristiques [basées sur des règles](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) qui contiennent des signaux exploitables. Vous pouvez ainsi, par exemple, limiter la fréquence du nombre de fois qu’une création particulière est présentée à un utilisateur ou une utilisatrice, dans une campagne multimédia. Lisez [Suppression instantanée sur plusieurs appareils](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) pour savoir comment procéder. Voici d’autres cas d’utilisation :

### Recibler les utilisateurs

Recibler les utilisateurs qui ont vu creative 123 mais n’ont pas cliqué ni effectué de conversion et leur montrer creative 456. Procédez comme suit :

1. Créez une caractéristique pour capturer les utilisateurs qui ont vu le contenu créatif. Supposons que vous nommiez le trait [!DNL Creative Trait 123]. Utilisez la règle de caractéristique :

   `d_creative == 123 AND d_event == imp`

2. Créez une caractéristique pour capturer les utilisateurs qui cliquent ou effectuent une conversion. Imaginons que vous donniez un nom à cette [!DNL Click and Converter]. Utilisez la règle de caractéristique :

   `d_event == click OR d_event=conv`

3. Créez un segment pour renseigner les utilisateurs qui ont vu Creative 123 mais n’ont pas cliqué ni effectué de conversion. Nommez-le [!DNL Retarget Users] et utilisez la règle de segment :

   `Creative Trait 123 AND NOT Click and Converter`

4. Mappez le segment [!DNL Retarget Users] à une destination et ciblez les utilisateurs de la destination avec des créations 456.

### Utiliser l’activité de projecteur Google Campaign Manager dans les rapports Audience Optimization ou dans Audience Lab

[Les balises Floodlight](https://support.google.com/dcm/partner/answer/4293719?hl=en) permettent aux annonceurs de suivre les conversions des utilisateurs. Avec [!UICONTROL Actionable Log Files], vous pouvez effectuer le suivi des conversions [!DNL Google Campaign Manager] dans les [rapports Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md) ou dans [Audience Lab](../../features/audience-lab/audience-lab.md) :

1. Créez une caractéristique et utilisez la règle de caractéristique suivante pour capturer une conversion à partir des journaux du serveur de publicités :

   `d_event == conv AND d_conversion == 123`

   Lors de la création de la caractéristique dans l’[!UICONTROL UI] Audience Manager, sélectionnez [!UICONTROL Conversion] comme [!UICONTROL Event Type].

2. Une fois la caractéristique créée, la conversion fait l’objet d’un rapport dans le [!UICONTROL Audience Optimization Reports] et dans le [!UICONTROL Audience Lab].

>[!MORELIKETHIS]
>
>* [Importer Des Fichiers De Données Google Campaign Manager Dans Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Rapports d’Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md)
