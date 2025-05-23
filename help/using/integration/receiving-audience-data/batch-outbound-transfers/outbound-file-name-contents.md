---
description: Décrit les champs, la syntaxe et les conventions requis pour nommer un fichier de données sortant.
seo-description: Describes the required fields, syntax, and conventions used to name an outbound data file.
seo-title: Outbound Data File Name  Syntax and Examples
solution: Audience Manager
title: Syntaxe du nom de fichier de données sortantes et exemples
uuid: effdcaf6-c37c-45f3-9d2f-a938a9da47a6
feature: Outbound Data Transfers
exl-id: 0944da72-5a8d-45a2-951e-b2988eb3d490
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 5%

---

# Nom du fichier de données sortantes : syntaxe et exemples{#outbound-data-file-name-syntax-and-examples}

Décrit les champs, la syntaxe et les conventions requis pour nommer un fichier de données sortant.

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>Les éléments de style (`monospaced text`, *italics*, crochets `[ ]` `( )`, etc.) dans ce document, indiquez les éléments de code et les options. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../../reference/code-style-elements.md).

## Syntaxe et éléments de nom de fichier {#syntax-file-name}

Les noms des fichiers sortants contiennent les éléments suivants. Tous les éléments ci-dessous sont facultatifs.

```
[SYNC_TYPE][_DID][_MASTER_DPID][_PID_ALIAS][_SYNC-MODE][_TIMESTAMP]SPLITNUM.sync[.gz]
```

### Paramètres

Le tableau définit les éléments d’un nom de fichier de données sortant.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elément Nom du fichier </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_TYPE </i></code> </p> </td> 
   <td colname="col2"> <p>Fait référence aux méthodes de transfert de données. Les méthodes de transfert incluent : </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP : transfert par SFTP </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> Amazon S3 </span> - Transfert vers <span class="keyword"> Amazon AWS </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DID </i></code> </p> </td> 
   <td colname="col2"> <p>ID de destination. </p> <p>Dans l’ <span class="keyword"> Audience Manager </span>, une destination est l’instance de l’intégration où vous pouvez mapper vos segments ciblés. Les clients peuvent avoir plusieurs destinations, en fonction des besoins de l’entreprise. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>MASTER_DPID </i></code> </p> </td> 
   <td colname="col2"> <p>ID de fournisseur de données ou de source de données. Cet identifiant identifie le type d’ID utilisateur présent dans le contenu du fichier. Les clés d’ID utilisateur les plus courantes sont les suivantes : </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">20914 - <span class="keyword"> Google Advertiser ID </span> (brut, non haché) </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">20915 - <span class="keyword"> Apple ID pour les annonceurs </span> (brut, non haché) </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">Identifiant du fournisseur - identifiants d’utilisateur tiers (web/cookie) </li> 
     </ul> </p> <p>Consultez les <a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/global-data-sources.html?lang=fr">sources de données globales</a> pour en savoir plus.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID_ALIAS </i></code> </p> </td> 
   <td colname="col2"> Identifiant client de la plateforme tierce. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_MODE </i></code> </p> </td> 
   <td colname="col2"> <p>Le mode de synchronisation est un espace réservé de macro qui ajoute un libellé au nom du fichier en fonction du type de synchronisation. Les types de synchronisation incluent complète et incrémentielle. Ils s’affichent dans le nom de fichier sous la forme <code> iter </code> ou <code> full </code>. </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> iter </code> : indique une synchronisation "itérative" ou incrémentale. Un fichier incrémentiel contient uniquement les nouvelles données collectées depuis la dernière synchronisation. </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> full </code> : indique une synchronisation "complète". Un fichier entièrement synchronisé contient d’anciennes données et toutes les nouvelles données collectées depuis la dernière synchronisation. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP </i></code> </p> </td> 
   <td colname="col2"> <p>Horodatage UNIX à 13 chiffres en millisecondes, dans le fuseau horaire UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>SPLITNUM</i></code></p> </td> 
   <td colname="col2"> <p>Entier. Identifie une partie d’un fichier qui a été divisée en plusieurs parties afin d’améliorer les temps de traitement. Le nombre indique à quelle partie du fichier d’origine appartiennent les données.</p>  <p>L’entier doit contenir au moins 3 chiffres, précédés de zéros, si la taille de division est inférieure à 100 parties.</p>  <p>Le fichier d’origine ne comportera aucun numéro partagé. Le premier fichier partagé se termine par 001. Voir les exemples ci-dessous. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (optional) </i></code> </p> </td> 
   <td colname="col2"> <p>compression GZIP. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemples de noms de fichier {#file-name-examples}

### Scénario 1

Fichiers envoyés à un emplacement [!DNL Amazon S3], avec *`PID_ALIAS="XYZCustomer"`* et [!DNL Google Advertiser IDs] dans le contenu du fichier.

Par exemple, les fichiers incrémentiels :

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000001.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000002.sync.gz </code> </li> 
</ul>

Par exemple, des fichiers complets :

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000001.sync.gz </code> </li> 
</ul>

### Scénario 2

Fichiers envoyés à l’emplacement [!DNL FTP], sans *`PID_ALIAS`* et avec [!DNL Apple Advertiser IDs] dans le contenu du fichier :

Par exemple, les fichiers incrémentiels :

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_iter_1486140843000001.sync.gz </code> </li> 
</ul>

Par exemple, des fichiers complets :

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_full_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_full_1486140843000001.sync.gz </code> </li> 
</ul>

**Scénario 3** : fichiers envoyés à l’emplacement [!DNL FTP], avec *`PID_ALIAS="XYZCustomer"`* et un identifiant utilisateur tiers dans le contenu du fichier ( *`Vendor ID=45454`*) :

Par exemple, les fichiers incrémentiels :

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
</ul>

Par exemple, des fichiers complets :

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200001.sync.gz </code> </li> 
</ul>

## Contenu du fichier de données sortant : syntaxe et paramètres {#outbound-contents-syntax}

Décrit les champs, la syntaxe et les conventions requis pour organiser les informations dans un fichier de données sortant. Mettez en forme vos données en fonction de ces spécifications.

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>Les éléments de style (`monospaced text`, *italics*, crochets `[ ]` `( )`, etc.) dans ce document, indiquez les éléments de code et les options. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../../reference/code-style-elements.md).

### Syntaxe

Les champs du fichier de données s’affichent dans l’ordre suivant :

`UUID<SPACE>SEGMENT_1,SEGMENT_2<SPACE>REMOVED_SEGMENT_,...`

### Paramètres

Le tableau répertorie les variables qui définissent le contenu d’un fichier de données.

<table id="table_109BA747CFDA40108370EFEB208C7E11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>UUID </i></code> </p> </td> 
   <td colname="col2"> <p>Identifiant utilisateur unique attribué par l’Audience Manager <span class="keyword"> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>&lt;SPACE&gt; </i></code> </p> </td> 
   <td colname="col2"> <p>Séparez l’UUID et les données de segment par un espace. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>Identifiant du segment auquel appartient un visiteur. Séparez plusieurs segments par une virgule. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>REMOVED_SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>Identifiant du segment à partir duquel l’utilisateur a été disqualifié. Séparez plusieurs segments par une virgule. Avec une synchronisation complète, vous pouvez ignorer les segments supprimés, car le fichier de données contiendra la liste complète des segments en cours pour l’utilisateur. En règle générale, vous souhaitez connaître les segments auxquels appartient un utilisateur plutôt que ceux dont il a été supprimé. Voir aussi <a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples"> Nom de fichier de données sortantes : syntaxe et exemples </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exemple : format de fichier de base

Un fichier de données correctement formaté peut ressembler à l’exemple suivant. Cette entrée de fichier indique qu’un utilisateur est admissible pour les segments 24, 26 et 27. Au besoin, un espace sépare les `UUID` et les identifiants de segment. Un autre espace sépare les jeux d’identifiants de segment. Dans cet exemple, un utilisateur appartient aux segments 24, 26 et 27. Ils ont été supprimés des segments 25 et 28.

```
59767559181262060060278870901087098252  24,26,27  25,28
```
