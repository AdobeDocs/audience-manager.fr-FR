---
description: Les fichiers journaux peuvent vous permettre de capturer des données multimédia à partir des fichiers journaux de Google DCM et d'utiliser les données pour créer des caractéristiques dans Audience Manager. Récupérez les impressions, les clics et les conversions à partir des serveurs de publicité comme des caractéristiques sans avoir à utiliser d’appels de pixels.
keywords: journaux exploitables
seo-description: Les fichiers journaux peuvent vous permettre de capturer des données multimédia à partir des fichiers journaux de Google DCM et d'utiliser les données pour créer des caractéristiques dans Audience Manager. Récupérez les impressions, les clics et les conversions à partir des serveurs de publicité comme des caractéristiques sans avoir à utiliser d’appels de pixels.
seo-title: Fichiers journaux pratiques
solution: Audience Manager
title: Fichiers journaux pratiques
uuid: 4 c 47615 f-ed 47-41 ba -8694-1 d 7 de 4 f 55 d 62
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Fichiers journaux pratiques {#actionable-log-files}

[!UICONTROL Actionable Log Files] vous permettent de capturer des données de médias à partir [!DNL Google DCM] des fichiers journaux et d&#39;utiliser les données pour créer des caractéristiques dans Audience Manager. Récupérez les impressions, les clics et les conversions à partir des serveurs de publicité comme des caractéristiques sans avoir à utiliser d’appels de pixels.

>[!NOTE]
>
>Les styles de texte (`monospaced text`, *italiques*, crochets `[ ]` `( )`, etc.) dans ce document indique les éléments et options du code. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../reference/code-style-elements.md).

## Rôle {#purpose}

[!UICONTROL Actionable Log Files] rationaliser la capture des impressions, clics et conversions à partir des serveurs d&#39;annonces. Use this information for user segmentation without having to manually pixel media to send campaign attributes to [!DNL Audience Manager].

## Prise en main {#getting-started}

To get started with [!UICONTROL Actionable Log Files], and to use our [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md), you need to import DCM log data into [!DNL Audience Manager]. See [Import DCM Data Files Into Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *and* contact your [!DNL Audience Manager] consultant.

If you are already importing [!UICONTROL DCM] log data into [!DNL Audience Manager], ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to enable [!UICONTROL Actionable Log Files] for you.

>[!NOTE] {importance = « high »}
>
>[!UICONTROL Actionable Log Files] ne fonctionne qu&#39;avec [!DNL Google DCM] les fichiers journaux.

## Working with Actionable Log Files {#working-with-actionable-log-files}

With [!UICONTROL Actionable Log Files], the information from [!DNL DCM] logs is captured in [!DNL Audience Manager] the same way that you would capture data from real-time website interactions. [!DNL Audience Manager] se connecte à [!DNL Google Cloud] votre stockage, analyse les informations des [!DNL DCM] journaux et envoie les données du journal comme signaux exploitables à nos [serveurs de collecte de données](../../reference/system-components/components-data-collection.md#dcs-pcs).

Vous devez toujours configurer des caractéristiques basées sur des règles pour capturer les signaux exploitables. See how to set up rule-based traits either in the [Audience Manager UI](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) or using our [Bulk Management Tools](../../reference/bulk-management-tools/bulk-create.md). Scroll down to the [Actionable Signals](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) section for a list of all the keys you can use in rule-based traits.

For an average-sized [!DNL DCM] log file of 2 million lines, any traits created from actionable signals are realized within approximately one hour after we process the logs.

>[!IMPORTANT] {importance = « high »}
>
>We recommend implementing [!UICONTROL Actionable Log Files] *instead of*  [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md). Nous déconseillons l&#39;utilisation des deux options car cela entraîne une augmentation du nombre de fréquences pour les caractéristiques.

## Actionable Signals {#actionable-signals}

Signals are the [smallest data units](../../reference/signal-trait-segment.md) in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] vous permettent de capturer les valeurs de l&#39;annonceur, de l&#39;unité opérationnelle, de l&#39;élément créatif et de la campagne dans les événements d&#39;impression, les événements de clic et les événements de conversion comme signaux des [!DNL DCM] journaux.

N&#39;oubliez pas que pour utiliser ces informations pour la création et la segmentation d&#39;audiences, vous devez configurer vous-même les caractéristiques basées sur des règles. The table lists the actionable signals from [!DNL DCM] log files:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Signal </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Exemple de valeur </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ event</code> </p> </td> 
   <td colname="col2"> <p>Indique le type d'événement de DCM. </p> <p>Les valeurs acceptées sont les suivantes : </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_ event = imp</code> pour les impressions. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_ event = clic</code> pour les clics. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_ event = conv</code> pour les conversions. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> imp, clic, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ conversion</code> </p> </td> 
   <td colname="col2"> <p>Disponible uniquement pour les événements de conversion. </p> <p>Représente l'ID numérique de l'activité de conversion dans DCM. Ce champ fait correspondre l'ID d'activité à DCM. </p> <p> <p>Conseil : Vous pouvez capturer plusieurs activités de conversion ou spécifiques à partir de DCM. Create traits using <code> d_conversion = activity ID</code> for each conversion activity from DCM. </p> </p> </td> 
   <td colname="col3"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ conversiontype</code> </p> </td> 
   <td colname="col2"> <p>Disponible uniquement pour les événements de conversion. </p> <p>Ce champ correspond à l'ID de conversion dans DCM. Indique l'activité précédant la conversion des utilisateurs de DCM. </p> <p>Les valeurs acceptées sont les suivantes : </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> pour les conversions après clic. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> pour les conversions post-impression. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> pour les conversions non correspondances. La conversion ne peut pas correspondre à une activité précédente. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> 0,1,2</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ adsrc</code> </p> </td> 
   <td colname="col2"> <p>Identifiant publicitaire. Ce champ fait correspondre l'identifiant de groupe publicitaire à DCM. </p> </td> 
   <td colname="col3"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ bu</code> </p> </td> 
   <td colname="col2"> <p>ID d'unité opérationnelle. Ce champ fait correspondre l'identifiant publicitaire à DCM. </p> </td> 
   <td colname="col3"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ campaign</code> </p> </td> 
   <td colname="col2"> <p>ID de campagne fourni par DCM. </p> </td> 
   <td colname="col3"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ creative</code> </p> </td> 
   <td colname="col2"> <p>ID créatif fourni par DCM. </p> </td> 
   <td colname="col3"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ src</code> </p> </td> 
   <td colname="col2"> <p>ID de la source de données utilisée pour capturer les données DCM. See <a href="../../features/manage-datasources.md#create-data-source"> How to Create a Data Source</a>. </p> </td> 
   <td colname="col3"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

The signals described in the table are captured in [!DNL Audience Manager] like a real-time `HTTP` call. The example call below contains information on a conversion event from [!DNL DCM]. Calls do not necessarily have to include *all* the signals in the example call.

```
https://sample.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

>[!NOTE] {importance = « high »}
>
>The event timestamp provided in the [!DNL DCM] logs will be honored and passed to the [!UICONTROL Data Collection Servers].
>
>* If a timestamp isn&#39;t available for a data row in the [!DNL DCM] log file, we use the time of the `HTTP` call as the event timestamp.
>* If the data row in the [!DNL DCM] log file contains a malformed timestamp, we ignore the entire row.


## Cas d’utilisation {#use-cases}

One benefit of implementing [!UICONTROL Actionable Log Files] is the option to apply [recency and frequency](../../features/segments/recency-and-frequency.md) controls to any [rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) that contain actionable signals. Cela vous permet, par exemple, de limiter le nombre de fois où un utilisateur affiche un élément créatif particulier dans une campagne multimédia. Autres cas d&#39;utilisation :

### Reciblage des utilisateurs

Reciblage des utilisateurs qui ont vu Creative 123 mais qui n&#39;ont pas cliqué ou ne sont pas convertis et qui leur montrent Creative 456. Procédez comme suit :

1. Créez une caractéristique pour capturer les utilisateurs qui ont vu le créatif. Let&#39;s say you name the trait [!DNL Creative Trait 123]. Utilisez la règle de caractéristique :

   `d_creative == 123 AND d_event == imp`

1. Créez une caractéristique pour capturer les utilisateurs qui cliquent ou effectuent une conversion. Let&#39;s say you name this one [!DNL Click and Converter]. Utilisez la règle de caractéristique :

   `d_event == click OR d_event=conv`

1. Créez un segment à renseigner avec les utilisateurs qui ont vu Creative 123 mais qui n&#39;ont pas cliqué ou ne sont pas convertis. Name it [!DNL Retarget Users] and use the segment rule:

   `Creative Trait 123 AND NOT Click and Converter`

1. Map the segment [!DNL Retarget Users] to a destination and target users in the destination with creative 456.

### Utilisation de l&#39;activité Floodlight DCM dans les rapports Optimisation de l&#39;audience ou dans Audience Lab

[Les balises Floodlight](https://support.google.com/dcm/partner/answer/4293719?hl=en) permettent aux publicitaires de suivre les conversions des utilisateurs. With [!UICONTROL Actionable Log Files], you can track the [!DNL DCM] conversions in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md) or in [Audience Lab](../../features/audience-lab/audience-lab.md):

1. Créez une caractéristique et utilisez la règle de caractéristique suivante pour capturer une conversion à partir des journaux du serveur d&#39;annonces :

   `d_event == conv AND d_conversion == 123`

   When creating the trait in the Audience Manager [!UICONTROL UI], select [!UICONTROL Conversion] as the [!UICONTROL Event Type].

2. Once you have created the trait, the conversion will begin to be reported against in the [!UICONTROL Audience Optimization Reports] and in [!UICONTROL Audience Lab].

>[!MORE_ LIKE_ THIS]
>
>* [Importer des fichiers de données DCM dans Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Rapports Optimisation de l&#39;audience](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

