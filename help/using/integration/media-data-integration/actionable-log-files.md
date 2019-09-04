---
description: Les fichiers journaux peuvent vous permettre de capturer des données multimédia à partir des fichiers journaux de Google DCM et d'utiliser les données pour créer des caractéristiques dans Audience Manager. Récupérez les impressions, les clics et les conversions à partir des serveurs de publicité comme des caractéristiques sans avoir à utiliser d’appels de pixels.
keywords: journaux exploitables
seo-description: Les fichiers journaux peuvent vous permettre de capturer des données multimédia à partir des fichiers journaux de Google DCM et d'utiliser les données pour créer des caractéristiques dans Audience Manager. Récupérez les impressions, les clics et les conversions à partir des serveurs de publicité comme des caractéristiques sans avoir à utiliser d’appels de pixels.
seo-title: Fichiers journaux pratiques
solution: Audience Manager
title: Fichiers journaux pratiques
uuid: 4 c 47615 f-ed 47-41 ba -8694-1 d 7 de 4 f 55 d 62
translation-type: tm+mt
source-git-commit: dbc96973ed2214d171fe32b7e1314d40c22c2d79

---


# Fichiers journaux pratiques {#actionable-log-files}

[!UICONTROL Actionable Log Files] vous permettent de capturer des données de médias à partir [!DNL Google DCM] des fichiers journaux et d'utiliser les données pour créer des caractéristiques dans Audience Manager. Récupérez les impressions, les clics et les conversions à partir des serveurs de publicité comme des caractéristiques sans avoir à utiliser d’appels de pixels.

>[!NOTE]
>
>Les styles de texte (`monospaced text`, *italiques*, crochets `[ ]` `( )`, etc.) dans ce document indique les éléments et options du code. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../reference/code-style-elements.md).

## Rôle {#purpose}

[!UICONTROL Actionable Log Files] rationaliser la capture des impressions, clics et conversions à partir des serveurs d'annonces. Utilisez ces informations pour la segmentation des utilisateurs sans avoir à recourir à un support de pixels manuellement pour envoyer [!DNL Audience Manager]des attributs de campagne.

## Prise en main {#getting-started}

Pour commencer avec [!UICONTROL Actionable Log Files]les rapports Optimisation [de l'audience](../../reporting/audience-optimization-reports/audience-optimization-reports.md), vous devez importer les données du journal DCM dans [!DNL Audience Manager]. Voir [Importer des fichiers de données DCM dans Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *et* contactez votre [!DNL Audience Manager] consultant.

Si vous importez déjà des données [!UICONTROL DCM] de journal dans [!DNL Audience Manager], demandez à [!DNL Audience Manager] votre conseiller ou [au service d'assistance](https://helpx.adobe.com/contact/enterprise-support.ec.html) clientèle de vous activer [!UICONTROL Actionable Log Files] .

>[!NOTE] {importance = « high »}
>
>[!UICONTROL Actionable Log Files] ne fonctionne qu'avec [!DNL Google DCM] les fichiers journaux.

## Utilisation des fichiers journaux exploitables {#working-with-actionable-log-files}

Avec, [!UICONTROL Actionable Log Files]les informations des [!DNL DCM] journaux sont capturées de [!DNL Audience Manager] la même façon que vous capturez les données à partir des interactions du site Web en temps réel. [!DNL Audience Manager] se connecte à [!DNL Google Cloud] votre stockage, analyse les informations des [!DNL DCM] journaux et envoie les données du journal comme signaux exploitables à nos [serveurs de collecte de données](../../reference/system-components/components-data-collection.md#dcs-pcs).

Vous devez toujours configurer des caractéristiques basées sur des règles pour capturer les signaux exploitables. Découvrez comment configurer des caractéristiques basées sur des règles dans l'interface utilisateur [d'Audience Manager](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) ou en utilisant nos [outils de gestion en masse](../../reference/bulk-management-tools/bulk-create.md). Faites défiler la section Signaux [utilisables pour](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) obtenir la liste de toutes les clés que vous pouvez utiliser dans des caractéristiques basées sur des règles.

Dans le cas d'un fichier [!DNL DCM] journal de taille moyenne de 2 millions de lignes, toutes les caractéristiques créées à partir de signaux exploitables sont réalisées dans environ une heure après le traitement des journaux.

>[!IMPORTANT] {importance = « high »}
>
>Nous recommandons la mise en œuvre [!UICONTROL Actionable Log Files]*plutôt que les appels* [Pixel](../../integration/media-data-integration/impression-data-pixels.md). Nous déconseillons l'utilisation des deux options car cela entraîne une augmentation du nombre de fréquences pour les caractéristiques.

## Signaux exploitables {#actionable-signals}

Les signaux sont les [plus petits unités de données](../../reference/signal-trait-segment.md) dans [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] vous permettent de capturer les valeurs de l'annonceur, de l'unité opérationnelle, de l'élément créatif et de la campagne dans les événements d'impression, les événements de clic et les événements de conversion comme signaux des [!DNL DCM] journaux.

N'oubliez pas que pour utiliser ces informations pour la création et la segmentation d'audiences, vous devez configurer vous-même les caractéristiques basées sur des règles. Le tableau répertorie les signaux exploitables des fichiers [!DNL DCM] journaux :

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
   <td colname="col2"> <p>Disponible uniquement pour les événements de conversion. </p> <p>Représente l'ID numérique de l'activité de conversion dans DCM. Ce champ fait correspondre l'ID d'activité à DCM. </p> <p> <p>Conseil : Vous pouvez capturer plusieurs activités de conversion ou spécifiques à partir de DCM. Créez des caractéristiques à l'aide de <code> d_ conversion = ID d'activité</code> pour chaque activité de conversion à partir de DCM. </p> </p> </td> 
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
   <td colname="col2"> <p>Identifiant publicitaire.</p> <p>Code d'intégration de la source de données de votre annonceur. Notez que cela n'est pas lié aux sources de données d'Audience Manager.</p> <p>Ce champ fait correspondre l'identifiant de groupe publicitaire à DCM. </p> </td> 
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
   <td colname="col2"> <p>ID de la source de données utilisée pour capturer les données DCM. Voir <a href="../../features/manage-datasources.md#create-data-source"> Création d'une source de données</a>. </p> </td> 
   <td colname="col3"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Les signaux décrits dans le tableau sont capturés dans [!DNL Audience Manager] un `HTTP` appel en temps réel. L'exemple d'appel ci-dessous contient des informations sur [!DNL DCM]un événement de conversion. Les appels ne doivent pas nécessairement inclure *tous* les signaux dans l'appel d'exemple.

```
https://sample.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

>[!NOTE] {importance = « high »}
>
>L'horodatage d'événement fourni dans [!DNL DCM] les journaux sera honoré et transmis à [!UICONTROL Data Collection Servers]l'objet.
>
>* Si un horodatage n'est pas disponible pour une ligne de données du fichier [!DNL DCM] journal, nous utilisons l'heure de l' `HTTP` appel comme horodatage d'événement.
>* Si la ligne de données du [!DNL DCM] fichier journal contient un horodatage mal structuré, nous ignorons la ligne entière.


## Cas d’utilisation {#use-cases}

L'une des avantages de la mise en œuvre [!UICONTROL Actionable Log Files] est l'option permettant d'appliquer [des commandes de récence et de fréquence](../../features/segments/recency-and-frequency.md) à n'importe quelle [caractéristique](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) basée sur des règles contenant des signaux exploitables. Cela vous permet, par exemple, de limiter le nombre de fois où un utilisateur affiche un élément créatif particulier dans une campagne multimédia. Autres cas d'utilisation :

### Reciblage des utilisateurs

Reciblage des utilisateurs qui ont vu Creative 123 mais qui n'ont pas cliqué ou ne sont pas convertis et qui leur montrent Creative 456. Procédez comme suit :

1. Créez une caractéristique pour capturer les utilisateurs qui ont vu le créatif. Imaginons que vous nommiez la caractéristique [!DNL Creative Trait 123]. Utilisez la règle de caractéristique :

   `d_creative == 123 AND d_event == imp`

1. Créez une caractéristique pour capturer les utilisateurs qui cliquent ou effectuent une conversion. Imaginons que vous [!DNL Click and Converter]nommiez celui-ci. Utilisez la règle de caractéristique :

   `d_event == click OR d_event=conv`

1. Créez un segment à renseigner avec les utilisateurs qui ont vu Creative 123 mais qui n'ont pas cliqué ou ne sont pas convertis. Nommez-le [!DNL Retarget Users] et utilisez la règle de segmentation :

   `Creative Trait 123 AND NOT Click and Converter`

1. Faites correspondre le segment [!DNL Retarget Users] à une destination et ciblez les utilisateurs dans la destination avec Creative 456.

### Utilisation de l'activité Floodlight DCM dans les rapports Optimisation de l'audience ou dans Audience Lab

[Les balises Floodlight](https://support.google.com/dcm/partner/answer/4293719?hl=en) permettent aux publicitaires de suivre les conversions des utilisateurs. Avec [!UICONTROL Actionable Log Files], vous pouvez effectuer le suivi des [!DNL DCM] conversions dans les rapports Optimisation [d'audience](../../reporting/audience-optimization-reports/audience-optimization-reports.md) ou [Audience Lab](../../features/audience-lab/audience-lab.md):

1. Créez une caractéristique et utilisez la règle de caractéristique suivante pour capturer une conversion à partir des journaux du serveur d'annonces :

   `d_event == conv AND d_conversion == 123`

   Lors de la création de la caractéristique dans Audience Manager [!UICONTROL UI], sélectionnez [!UICONTROL Conversion] l' [!UICONTROL Event Type]élément.

2. Une fois la caractéristique créée, la conversion commence à être rapportée dans [!UICONTROL Audience Optimization Reports] le rapport et dans [!UICONTROL Audience Lab].

>[!MORE_ LIKE_ THIS]
>
>* [Importer des fichiers de données DCM dans Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Rapports Optimisation de l'audience](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

