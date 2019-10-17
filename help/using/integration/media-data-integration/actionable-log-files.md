---
description: Les fichiers journaux exploitables vous permettent de capturer les signaux du média à partir des fichiers journaux du serveur d’annonces afin de créer des caractéristiques dans Audience Manager. Capturez les impressions, les clics et les conversions depuis les serveurs d’annonces en tant que caractéristiques sans avoir à ajouter de pixels.
keywords: journaux exploitables, alf, ALF
seo-description: Les fichiers journaux exploitables vous permettent de capturer les signaux du média à partir des fichiers journaux du serveur d’annonces afin de créer des caractéristiques dans Audience Manager. Capturez les impressions, les clics et les conversions depuis les serveurs d’annonces en tant que caractéristiques sans avoir à utiliser l’ajout de pixels.
seo-title: Fichiers journaux pratiques
solution: Audience Manager
title: Fichiers journaux pratiques
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
translation-type: tm+mt
source-git-commit: 5643b1490738aa452e45517610d31e37c361a780

---


# Fichiers journaux pratiques {#actionable-log-files}

[!UICONTROL Actionable Log Files] vous permet de capturer des données multimédia à partir de fichiers journaux de serveur d’annonces et d’utiliser les données pour créer des caractéristiques dans Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to append [pixels](../../integration/media-data-integration/impression-data-pixels.md).

>[!NOTE]
>
>Les styles de texte (`monospaced text`, *italiques*, crochets `[ ]` `( )`, etc.) dans ce document, indiquez les éléments de code et les options. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../reference/code-style-elements.md).

## Rôle {#purpose}

[!UICONTROL Actionable Log Files] rationalisez la manière dont vous capturez les impressions, les clics et les conversions à partir des serveurs d’annonces. Utilisez ces informations pour la segmentation de l’utilisateur sans avoir à utiliser manuellement les pixels médias pour envoyer les attributs de campagne à [!DNL Audience Manager].

## Prise en main {#getting-started}

Pour commencer [!UICONTROL Actionable Log Files], vous devez importer les données du journal dans [!DNL Audience Manager]. Les liens suivants vous aideront à démarrer :

* Pour [!UICONTROL Google DCM] consulter les journaux, reportez-vous à la section [Importation de fichiers de données DCM dans Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) et *contactez votre* [!DNL Audience Manager] consultant.
* Pour consulter d’autres journaux de serveur d’annonces, voir Fichiers [de](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) données et de métadonnées *et contactez votre* [!DNL Audience Manager] consultant.

Si vous importez déjà des données de journal dans [!DNL Audience Manager], demandez à votre [!DNL Audience Manager] consultant ou au service d’assistance [](https://helpx.adobe.com/contact/enterprise-support.ec.html) clientèle de [!UICONTROL Actionable Log Files] vous activer.

>[!IMPORTANT]
>
> Fin 2019, [!UICONTROL Actionable Log Files] la disponibilité des nouveaux serveurs d’annonces va commencer à augmenter. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

## Utilisation de fichiers journaux utilisables {#working-with-actionable-log-files}

Avec [!UICONTROL Actionable Log Files]cela, les informations des journaux du serveur d’annonces sont capturées [!DNL Audience Manager] de la même manière que les données des interactions du site Web en temps réel. [!DNL Audience Manager] se connecte au stockage du journal du serveur d’annonces, analyse les informations des journaux et envoie les données du journal sous forme de signaux exploitables aux serveurs [de collecte de](../../reference/system-components/components-data-collection.md#dcs-pcs)données.

Vous devez encore configurer des caractéristiques basées sur des règles pour capturer les signaux exploitables. Découvrez comment configurer des caractéristiques basées sur des règles dans l’interface utilisateur [d’](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) Audience Manager ou à l’aide des outils [de gestion en](../../reference/bulk-management-tools/bulk-create.md)masse. Faites défiler l’écran jusqu’à la section Signaux [](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) actifs pour obtenir la liste de toutes les clés que vous pouvez utiliser dans les caractéristiques basées sur des règles.

>[!IMPORTANT]
>
>Nous vous recommandons de mettre en oeuvre [!UICONTROL Actionable Log Files] au lieu *des appels* en [](../../integration/media-data-integration/impression-data-pixels.md)pixels. Nous décourageons l'utilisation des deux options, car cela entraîne une augmentation du nombre de fréquences pour les caractéristiques.

## Signaux utilisables {#actionable-signals}

Les signaux sont les [plus petites unités](../../reference/signal-trait-segment.md) de données dans [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] vous permet de capturer les valeurs de l’annonceur, de l’unité opérationnelle, de l’élément créatif et de la campagne dans les événements d’impression, les événements de clic et les événements de conversion en tant que signaux provenant des journaux du serveur d’annonces.

N’oubliez pas que pour utiliser ces informations pour la création et la segmentation d’audiences, vous devez vous-même configurer les caractéristiques basées sur des règles.

### Signaux utilisables à partir des journaux Google DCM {#dcm-logs-signals}

Le tableau répertorie les signaux interactifs provenant des fichiers [!DNL DCM] journaux :

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nom d’en-tête dans le fichier journal </th> 
   <th colname="col2" class="entry"> Signal </th> 
   <th colname="col3" class="entry"> Description </th> 
   <th colname="col4" class="entry"> Exemple de valeur </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Activity ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col3"> <p>Disponible uniquement pour les événements de conversion. </p> <p>Représente l’ID numérique de l’activité de conversion dans DCM. Ce champ correspond à l’ID d’activité de DCM. </p> <p> <p>Conseil : Vous pouvez capturer plusieurs activités de conversion ou des activités spécifiques à partir de DCM. Créez des caractéristiques à l’aide <code> d_conversion = activity ID</code> de chaque activité de conversion à partir de DCM. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Disponible uniquement pour les événements de conversion. </p> <p>Ce champ correspond à l’ID de conversion dans DCM. Indique l’activité précédant la conversion de l’utilisateur à partir de DCM. </p> <p>Les valeurs acceptées sont les suivantes : </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> pour les conversions après clic. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> pour les conversions après impression. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> pour les conversions sans correspondance. La conversion ne peut pas correspondre à une activité précédente. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">Date et heure UTC pour l’événement d’impression, de clic ou de conversion. Représenté en microsecondes depuis 1970-01-01 00:00:00 UTC.</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>Code d’intégration de la source de données de l’annonceur. Notez que ceci n’est pas lié aux sources de données Audience Manager.</p> <p>Ce champ correspond à l’identifiant du groupe publicitaire de DCM. </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>Identifiant de l’unité opérationnelle. Ce champ correspond à l’identifiant publicitaire de DCM. </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>ID de campagne fourni par DCM.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>ID créatif fourni par DCM. </p> </td> 
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
   <td colname="col3"> <p>Indique le type d’événement. Audience Manager lit le type d’événement à partir du nom du fichier journal DCM et le transforme en signal exploitable. </p> <p>Les valeurs acceptées sont les suivantes : </p> <p> 
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
   <td colname="col3"> <p>ID de la source de données que vous utilisez pour capturer les données DCM. Voir <a href="../../features/manage-datasources.md#create-data-source"> Comment créer une source</a>de données. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Les signaux décrits dans le tableau sont capturés [!DNL Audience Manager] comme un appel en temps réel `HTTP` . L’exemple d’appel ci-dessous contient des informations sur un événement de conversion provenant de [!DNL DCM]. Les appels ne doivent pas nécessairement inclure *tous* les signaux dans l’exemple d’appel.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

Pour un fichier journal de taille moyenne de 2 millions de lignes, toutes les caractéristiques créées à partir de signaux exploitables sont réalisées dans l'heure environ après le traitement des journaux. [!DNL DCM]

>[!NOTE] {importance="high"}
>
>L’horodatage de l’événement fourni dans les [!DNL DCM] journaux sera respecté et transmis au [!UICONTROL Data Collection Servers].
>
>* Si un horodatage n’est pas disponible pour une ligne de données dans le fichier [!DNL DCM] journal, nous utilisons l’heure de l’ `HTTP` appel comme horodatage de l’événement.
>* Si la ligne de données du fichier [!DNL DCM] journal contient un horodatage incorrect, nous ignorons la ligne entière.


<br> 

### Signaux utilisables à partir des journaux de serveur d’annonces génériques {#generic-logs-signals}

Tout d’abord, vous devez déposer les journaux de votre serveur d’annonces dans nos compartiments Amazon S3. Pour ce faire, lisez Fichiers de [données pour les rapports d’optimisation de l’audience et les fichiers](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) journaux utilisables *et contactez votre* [!DNL Audience Manager] consultant. Le tableau répertorie les signaux exploitables provenant des fichiers journaux génériques :

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nom d’en-tête dans le fichier journal </th> 
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
   <td colname="col3"> <p> Date et heure UTC pour l’événement d’impression, de clic ou de conversion. Utilisez la fonctionnalité   <code>yyyy-dd-mm hh:mm:ss format.</code> </p></td> 
   <td colname="col4"> <p> <code>2019-30-08 11:23:00</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>Code d’intégration de la source de données de l’annonceur. Notez que ce champ n’est pas lié aux sources de données <a href="../../features/datasources-list-and-settings.md">Audience Manager.</a></p></td> 
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
   <td colname="col3"> <p>ID de campagne du fichier journal.</p> </td> 
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
   <td colname="col3"> <p>Indique le type d’événement. Audience Manager lit le type d’événement à partir du nom du fichier journal et le transforme en signal exploitable. Voir Conventions <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">d’attribution des noms aux fichiers</a>journaux. </p> <p>Les valeurs acceptées sont les suivantes : </p> <p> 
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
   <td colname="col3"> <p>ID de la source de données que vous utilisez pour capturer les données du journal. Voir <a href="../../features/manage-datasources.md#create-data-source"> Comment créer une source</a>de données. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Les signaux décrits dans le tableau sont capturés [!DNL Audience Manager] comme un appel en temps réel `HTTP` . Les appels ne doivent pas nécessairement inclure *tous* les signaux dans l’exemple d’appel.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Utilisation de signaux tactiles dans l’interface utilisateur d’Audience Manager {#actionable-signals-in-ui}

Vous pouvez afficher vos signaux interactifs entrants dans l’interface de recherche [des](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md) signaux.

Accédez à Données **** d’audience (1) &gt; **Signaux** (2) &gt; **Rechercher** (3) et sélectionnez le filtre Fichiers journaux **utilisables (4).**

![Signaux actifs dans l’interface utilisateur](/help/using/integration/assets/alf-in-signals.png)

Pour créer des caractéristiques basées sur des règles à l’aide de vos signaux exploitables, sélectionnez Fichiers **journaux** exploitables (1), sélectionnez les signaux exploitables à utiliser comme règles de caractéristiques (2) et appuyez sur **Créer un trait à partir de signaux** sélectionnés (3).

![Créer des caractéristiques à partir de signaux](/help/using/integration/assets/alf-create-trait.png)

## Cas d’utilisation {#use-cases}

L’un des avantages de la mise en oeuvre [!UICONTROL Actionable Log Files] est l’option d’appliquer des contrôles de [récence et de fréquence](../../features/segments/recency-and-frequency.md) à toute caractéristique [basée sur des](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) règles qui contient des signaux exploitables. Cela vous permet, par exemple, de limiter le nombre de fois où un utilisateur voit apparaître un élément créatif particulier dans une campagne multimédia. Lisez Suppression [](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) instantanée de plusieurs périphériques pour savoir comment procéder. Les autres cas d'utilisation sont les suivants :

### Recibler les utilisateurs

Reciblez les utilisateurs qui ont vu la version 123 de Creative mais n’ont pas cliqué ou converti et leur ont présenté la version 456. Procédez comme suit :

1. Créez une caractéristique pour capturer les utilisateurs qui ont vu le contenu créatif. Disons que vous nommez le trait [!DNL Creative Trait 123]. Utilisez la règle de caractéristiques :

   `d_creative == 123 AND d_event == imp`

2. Créez une caractéristique pour capturer les utilisateurs qui cliquent ou convertissent. Disons que vous nommez celui-ci [!DNL Click and Converter]. Utilisez la règle de caractéristiques :

   `d_event == click OR d_event=conv`

3. Créez un segment à renseigner auprès des utilisateurs qui ont vu Creative 123 mais n’ont pas cliqué ou converti. Nommez-le [!DNL Retarget Users] et utilisez la règle de segmentation :

   `Creative Trait 123 AND NOT Click and Converter`

4. Faites correspondre le segment [!DNL Retarget Users] à une destination et ciblez les utilisateurs dans la destination avec Creative 456.

### Utilisation de l’activité Floodlight DCM dans les rapports Optimisation de l’audience ou dans Audience Lab

[Les balises](https://support.google.com/dcm/partner/answer/4293719?hl=en) Floodlight permettent aux annonceurs de suivre les conversions des utilisateurs. Avec [!UICONTROL Actionable Log Files]cela, vous pouvez effectuer le suivi des [!DNL DCM] conversions dans les rapports [d’optimisation de l’](../../reporting/audience-optimization-reports/audience-optimization-reports.md) audience ou dans [Audience Lab](../../features/audience-lab/audience-lab.md):

1. Créez une caractéristique et utilisez la règle de caractéristique suivante pour capturer une conversion à partir des journaux du serveur d’annonces :

   `d_event == conv AND d_conversion == 123`

   Lors de la création de la caractéristique dans Audience Manager [!UICONTROL UI], sélectionnez [!UICONTROL Conversion] comme [!UICONTROL Event Type].

2. Une fois que vous avez créé la caractéristique, la conversion commence à faire l’objet d’un rapport dans le [!UICONTROL Audience Optimization Reports] et [!UICONTROL Audience Lab].

>[!MORE_LIKE_This]
>
>* [Importation Des Fichiers De Données DCM Dans Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Rapports Optimisation de l’audience](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

