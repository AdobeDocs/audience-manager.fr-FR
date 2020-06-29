---
description: Décrit les champs, la syntaxe et les conventions requis utilisés pour nommer un fichier de données sortant.
seo-description: Décrit les champs, la syntaxe et les conventions requis utilisés pour nommer un fichier de données sortant.
seo-title: Syntaxe et exemples du nom du fichier de données sortantes
solution: Audience Manager
title: Syntaxe et exemples du nom du fichier de données sortantes
uuid: effdcaf6-c37c-45f3-9d2f-a938a9da47a6
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 4%

---


# Nom du fichier de données sortantes : Syntaxe et exemples{#outbound-data-file-name-syntax-and-examples}

Décrit les champs, la syntaxe et les conventions requis utilisés pour nommer un fichier de données sortant.

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>Les éléments de style (`monospaced text`, *italique*, crochets `[ ]` `( )`, etc.) dans ce document, indiquez les éléments de code et les options. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../../reference/code-style-elements.md).

## Eléments de syntaxe et de nom de fichier {#syntax-file-name}

Les noms de fichiers sortants contiennent les éléments suivants. Tous les éléments ci-dessous sont facultatifs.

```
[SYNC_TYPE][_DID][_MASTER_DPID][_PID_ALIAS][_SYNC-MODE][_TIMESTAMP]SPLITNUM.sync[.gz]
```

### Paramètres

Le tableau définit les éléments d’un nom de fichier de données sortant.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elément Nom de fichier </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_TYPE </i></code> </p> </td> 
   <td colname="col2"> <p>Fait référence aux méthodes de transfert de données. Les méthodes de transfert comprennent : </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP - Transfert via SFTP </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> Amazon S3 </span> - Transfert vers <span class="keyword"> AWS Amazon </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DID </i></code> </p> </td> 
   <td colname="col2"> <p>ID de destination. </p> <p>En <span class="keyword"> Audience Manager </span>, une destination est l’instance de l’intégration où vous pouvez mapper vos segments cibles. Les clients peuvent avoir plusieurs destinations, en fonction des besoins de l’entreprise. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>MASTER_DPID </i></code> </p> </td> 
   <td colname="col2"> <p>Fournisseur de données ou ID de source de données. Cet identifiant identifie le type d’ID utilisateur présent dans le contenu du fichier. Les clés d’ID utilisateur les plus courantes sont : </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">20914 - <span class="keyword"> Identifiant publicitaire Google </span> (brut, non haché) </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">20915 - <span class="keyword"> ID Apple pour les annonceurs </span> (brut, non haché) </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">ID fournisseur - ID utilisateur tiers (Web/cookie) </li> 
     </ul> </p> <p>Voir Sources <a href="https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/global-data-sources.html">de données</a> globales pour plus d’informations.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID_ALIAS </i></code> </p> </td> 
   <td colname="col2"> Identificateur de client de la plateforme tierce. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_MODE </i></code> </p> </td> 
   <td colname="col2"> <p>Le mode de synchronisation est un espace réservé de macro qui ajoute une étiquette au nom de fichier en fonction du type de synchronisation. Les types de synchronisation sont complets et incrémentiels. Ils apparaîtront dans le nom de fichier sous la forme <code> iter </code> ou <code> full </code>. </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> iter </code>: Indique une synchronisation "itérative" ou incrémentielle. Un fichier incrémentiel contient uniquement les nouvelles données collectées depuis la dernière synchronisation. </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> full </code>: Indique une synchronisation "complète". Un fichier entièrement synchronisé contient d’anciennes données et toutes les nouvelles données collectées depuis la dernière synchronisation. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP </i></code> </p> </td> 
   <td colname="col2"> <p>Horodatage UNIX à 13 chiffres en millisecondes, dans le fuseau horaire UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>SPLITNUM</i></code></p> </td> 
   <td colname="col2"> <p>Entier. Identifie une partie d'un fichier qui a été fractionnée en plusieurs parties afin d'améliorer les temps de traitement. Le numéro indique à quelle partie du fichier d’origine les données appartiennent.</p>  <p>L’entier doit contenir au moins 3 chiffres, précédés de zéros, si la taille de fractionnement est inférieure à 100 parties.</p>  <p>Le fichier d'origine n'aura pas de numéro partagé. Le premier fichier scindé se terminera par 001. Voir les exemples ci-dessous. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (optional) </i></code> </p> </td> 
   <td colname="col2"> <p>Compression GZIP. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemples de noms de fichier {#file-name-examples}

### Scénario 1

Fichiers envoyés à un [!DNL Amazon S3] emplacement, avec *`PID_ALIAS="XYZCustomer"`* et [!DNL Google Advertiser IDs] dans le contenu du fichier.

Par exemple, fichiers incrémentiels :

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000001.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000002.sync.gz </code> </li> 
</ul>

Par exemple, fichiers complets :

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000001.sync.gz </code> </li> 
</ul>

### Scénario 2

Fichiers envoyés à [!DNL FTP] l’emplacement, sans *`PID_ALIAS`* et avec [!DNL Apple Advertiser IDs] le contenu du fichier :

Par exemple, fichiers incrémentiels :

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_iter_1486140843000001.sync.gz </code> </li> 
</ul>

Par exemple, fichiers complets :

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_full_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_full_1486140843000001.sync.gz </code> </li> 
</ul>

**Scénario 3**: Fichiers envoyés à [!DNL FTP] l’emplacement, avec *`PID_ALIAS="XYZCustomer"`* et un ID utilisateur tiers dans le contenu du fichier ( *`Vendor ID=45454`*) :

Par exemple, fichiers incrémentiels :

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
</ul>

Par exemple, fichiers complets :

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200001.sync.gz </code> </li> 
</ul>

## Contenu du fichier de données sortantes : Syntaxe et paramètres {#outbound-contents-syntax}

Décrit les champs, la syntaxe et les conventions requis utilisés pour organiser les informations dans un fichier de données sortant. Mettez en forme vos données selon ces spécifications.

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>Les éléments de style (`monospaced text`, *italique*, crochets `[ ]` `( )`, etc.) dans ce document, indiquez les éléments de code et les options. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../../reference/code-style-elements.md).

### Syntaxe

Les champs du fichier de données s’affichent dans l’ordre suivant :

`UUID<SPACE>SEGMENT_1,SEGMENT_2<SPACE>REMOVED_SEGMENT_,...`

### Paramètres

Le tableau liste des variables qui définissent le contenu d’un fichier de données.

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
   <td colname="col2"> <p>ID utilisateur unique attribué par <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>&lt;SPACE&gt; </i></code> </p> </td> 
   <td colname="col2"> <p>Séparez les données UUID et de segmentation par un espace </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>ID de segment auquel appartient un visiteur. Séparez plusieurs segments par une virgule. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>REMOVED_SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>ID de segment à partir duquel l’utilisateur a été disqualifié. Séparez plusieurs segments par une virgule. Avec une synchronisation complète, vous pouvez ignorer les segments supprimés car le fichier de données contiendra la liste complète des segments actuels pour l’utilisateur. En règle générale, vous souhaitez connaître les segments auxquels un utilisateur appartient plutôt que ceux dont il a été supprimé. Voir aussi Nom <a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples"> du fichier de données sortantes : Syntaxe et exemples </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exemple : Format de fichier de base

Un fichier de données correctement formaté peut ressembler à l’exemple suivant. Cette entrée de fichier indique qu’un utilisateur est admissible pour les segments 24, 26 et 27. Si nécessaire, un espace sépare les ID `UUID` et les ID de segment. Un autre espace sépare les jeux d’ID de segment. Dans cet exemple, un utilisateur appartient aux segments 24, 26 et 27. Ils ont été supprimés des segments 25 et 28.

```
59767559181262060060278870901087098252  24,26,27  25,28
```
