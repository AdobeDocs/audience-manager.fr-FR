---
description: Décrit les champs obligatoires, la syntaxe et les conventions utilisées pour nommer un fichier de données sortant.
seo-description: Décrit les champs obligatoires, la syntaxe et les conventions utilisées pour nommer un fichier de données sortant.
seo-title: Fichier de données sortantes - nom syntaxe et exemples
solution: Audience Manager
title: Fichier de données sortantes - nom syntaxe et exemples
uuid: effdfac 6-c 37 c -45 f 3-9 d 2 f-a 938 a 9 da 47 a 6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Outbound Data File Name: Syntax and Examples{#outbound-data-file-name-syntax-and-examples}

Décrit les champs obligatoires, la syntaxe et les conventions utilisées pour nommer un fichier de données sortant.

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>The style elements (`monospaced text`, *italics*, brackets `[ ]` `( )`, etc.) dans ce document indique les éléments et options du code. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../../reference/code-style-elements.md).

## Syntax and File Name Elements {#syntax-file-name}

Les noms de fichiers sortants contiennent les éléments obligatoires et facultatifs suivants :

```
SYNC-TYPE_ DID_ MASTER-DPID_ [PID-ALIAS]_ SYNC-MODE_ TIMESTAMP[- SPLIT_NUMBER].sync[.gz]
```

### Paramètres

Le tableau définit les éléments d&#39;un fichier de données sortant - nom.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fichier - nom de l'élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC-TYPE </i></code> </p> </td> 
   <td colname="col2"> <p>Fait référence aux méthodes de transfert de données. Les méthodes de transfert incluent : </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP - Transfert avec SFTP </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> Amazon S 3 </span> - Transfert vers <span class="keyword"> Amazon AWS </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DID </i></code> </p> </td> 
   <td colname="col2"> <p>ID de destination. </p> <p><span class="keyword"> Dans Audience Manager </span>, une destination correspond à l'instance de l'intégration où vous pouvez mapper vos segments cibles. Les clients peuvent avoir plusieurs destinations en fonction des besoins commerciaux. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>MASTER-DPID </i></code> </p> </td> 
   <td colname="col2"> <p>Fournisseur de données ou ID de source de données. Cet ID identifie le type d'utilisateur - id présent dans le contenu du fichier. Utilisateur le plus courant - clés d'ID : </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">20914 - <span class="keyword"> Google Advertiser ID </span> (raw, unhashed) </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">20915 - <span class="keyword"> Apple ID for Advertisers </span> (raw, unhashed) </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">ID fournisseur - utilisateur tiers - id (web/cookie) </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID-ALIAS </i></code> </p> </td> 
   <td colname="col2"> Identifiant client de la plateforme tierce. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC-MODE </i></code> </p> </td> 
   <td colname="col2"> <p>Le mode de synchronisation est un espace réservé de macro qui ajoute une étiquette au fichier - nom basé sur le type de synchronisation. Les types de synchronisation sont complets et incrémentés. They'll appear in the file name as <code> iter </code> or <code> full </code>. </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> iter </code>: Indique une synchronisation itérative ou incrémentielle. Un fichier incrémentiel contient uniquement de nouvelles données collectées depuis la dernière synchronisation. </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> full </code>: Indique une synchronisation « complète ». Un fichier entièrement synchronisé contient des données anciennes et toutes les nouvelles données collectées depuis la dernière synchronisation. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP </i></code> </p> </td> 
   <td colname="col2"> <p>Horodatage UNIX à 13 chiffres en millisecondes, dans le fuseau horaire UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [<code><i>-SPLIT_NUMBER </i></code>] </p> </td> 
   <td colname="col2"> <p>Entier. Identifie une partie d'un fichier qui a été divisée en plusieurs parties afin d'améliorer les temps de traitement. Le nombre indique la partie du fichier d'origine auquel les données appartiennent. </p> <p>Le fichier d'origine n'aura pas de numéro de division. Le premier fichier fractionné commence par 1. Voir les exemples ci-dessous. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (facultatif) </i></code> </p> </td> 
   <td colname="col2"> <p>Compression GZIP. </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Name Examples {#file-name-examples}

### Scénario 1

Files sent over to an [!DNL Amazon S3] location, with *`PID-ALIAS="XYZCustomer"`* and with [!DNL Google Advertiser IDs] in the file content.

Fichiers incrémentiels :

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000-1.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000-10.sync.gz </code> </li> 
</ul>

Fichiers complets :

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000-1.sync.gz </code> </li> 
</ul>

### Scénario 2

Files sent over to [!DNL FTP] location, without *`PID-ALIAS`* and with [!DNL Apple Advertiser IDs] in the file content:

Fichiers incrémentiels :

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_iter_1486140843000-1.sync.gz </code> </li> 
</ul>

Fichiers complets :

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_full_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_full_1486140843000-1.sync.gz </code> </li> 
</ul>

**Scénario 3**: Fichiers envoyés à [!DNL FTP] l&#39;emplacement, avec *`PID-ALIAS="XYZCustomer"`* et avec User - id tiers - id dans le contenu du fichier ( *`Vendor ID=45454`*) :

Fichiers incrémentiels :

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000-1.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000-10.sync.gz </code> </li> 
</ul>

Fichiers complets :

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200-1.sync.gz </code> </li> 
</ul>

## Outbound Data File Contents: Syntax and Parameters {#outbound-contents-syntax}

Décrit les champs, la syntaxe et les conventions nécessaires pour organiser les informations dans un fichier de données sortant. Mettez en forme vos données conformément à ces spécifications.

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>The style elements (`monospaced text`, *italics*, brackets `[ ]` `( )`, etc.) dans ce document indique les éléments et options du code. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../../reference/code-style-elements.md).

### Syntaxe

Les champs du fichier de données s&#39;affichent dans cet ordre :

`UUID<SPACE>SEGMENT_1,SEGMENT_2<SPACE>REMOVED_SEGMENT_,...`

### Paramètres

Le tableau répertorie les variables qui définissent le contenu d&#39;un fichier de données.

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
   <td colname="col2"> <p>A unique user ID assigned by <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>&lt; ESPACE &gt; </i></code> </p> </td> 
   <td colname="col2"> <p>Séparation de l'UUID et des données de segmentation avec un espace </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SEGMENT_ N </i></code> </p> </td> 
   <td colname="col2"> <p>Identifiant de segment auquel un visiteur appartient. Séparez plusieurs segments par une virgule. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>REMOVED_ SEGMENT_ N </i></code> </p> </td> 
   <td colname="col2"> <p>Identifiant de segment à partir duquel l'utilisateur a été disqualifié. Séparez plusieurs segments par une virgule. Avec une synchronisation complète, vous pouvez ignorer les segments supprimés car le fichier de données contiendra la liste complète des segments actuels pour l'utilisateur. En général, vous souhaitez connaître les segments auxquels un utilisateur appartient plutôt que ceux qu'il a supprimés. See also <a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples"> Outbound Data File Name: Syntax and Examples </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exemple : Format de fichier de base

Un fichier de données correctement formaté peut ressembler à l&#39;exemple suivant. Cette entrée de fichier indique qu&#39;un utilisateur est admissible pour les segments 24, 26 et 27. As required, a space separates the `UUID` and segment IDs. Un autre espace sépare les ensembles d&#39;ID de segment. Dans cet exemple, un utilisateur appartient aux segments 24, 26 et 27. Elles ont été supprimées des segments 25 et 28.

```
59767559181262060060278870901087098252  24,26,27  25,28
```
