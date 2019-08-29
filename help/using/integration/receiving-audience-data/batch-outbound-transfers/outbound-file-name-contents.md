---
description: Décrit les champs obligatoires, la syntaxe et les conventions utilisées pour nommer un fichier de données sortant.
seo-description: Décrit les champs obligatoires, la syntaxe et les conventions utilisées pour nommer un fichier de données sortant.
seo-title: Fichier de données sortantes - nom syntaxe et exemples
solution: Audience Manager
title: Fichier de données sortantes - nom syntaxe et exemples
uuid: effdfac 6-c 37 c -45 f 3-9 d 2 f-a 938 a 9 da 47 a 6
translation-type: tm+mt
source-git-commit: 11663e962254bbcab90105d72af003b2a7056744

---


# Fichier de données sortantes - nom : Syntaxe et exemples{#outbound-data-file-name-syntax-and-examples}

Décrit les champs obligatoires, la syntaxe et les conventions utilisées pour nommer un fichier de données sortant.

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>Les éléments de style (`monospaced text`, *italique*, crochets `[ ]``( )`, etc.) dans ce document indique les éléments et options du code. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../../reference/code-style-elements.md).

## Syntaxe et fichier - nom des éléments {#syntax-file-name}

Les noms de fichiers sortants contiennent les éléments suivants. Tous les éléments ci-dessous sont facultatifs.

```
[SYNC_TYPE][_DID][_MASTER_DPID][_PID_ALIAS][_SYNC-MODE][_TIMESTAMP]SPLITNUM.sync[.gz]
```

### Paramètres

Le tableau définit les éléments d'un fichier de données sortant - nom.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fichier - nom de l'élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_ TYPE </i></code> </p> </td> 
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
   <td colname="col1"> <p> <code><i>MASTER_ DPID </i></code> </p> </td> 
   <td colname="col2"> <p>Fournisseur de données ou ID de source de données. Cet ID identifie le type d'utilisateur - id présent dans le contenu du fichier. Utilisateur le plus courant - clés d'ID : </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">20914 - <span class="keyword"> Identifiant publicitaire Google </span> (brut, unhashed) </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">20915 - <span class="keyword"> ID Apple pour Advertisers </span> (brut, non haché) </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">ID fournisseur - utilisateur tiers - id (web/cookie) </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID_ ALIAS </i></code> </p> </td> 
   <td colname="col2"> Identifiant client de la plateforme tierce. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_ MODE </i></code> </p> </td> 
   <td colname="col2"> <p>Le mode de synchronisation est un espace réservé de macro qui ajoute une étiquette au fichier - nom basé sur le type de synchronisation. Les types de synchronisation sont complets et incrémentés. Ils s'affichent dans le fichier : nom en <code> tant qu'iter </code> ou <code> complet </code>. </p> 
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
   <td colname="col1"> <p><code><i>SPLITNUM</i></code></p> </td> 
   <td colname="col2"> <p>Entier. Identifie une partie d'un fichier qui a été divisée en plusieurs parties afin d'améliorer les temps de traitement. Le nombre indique la partie du fichier d'origine auquel les données appartiennent.</p>  <p>L'entier doit comporter au moins 3 chiffres, précédés de zéros, si la taille fractionnée est inférieure à 100 parties.</p>  <p>Le fichier d'origine n'aura pas de numéro de division. Le premier fichier fractionné se termine par 001. Voir les exemples ci-dessous. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (facultatif) </i></code> </p> </td> 
   <td colname="col2"> <p>Compression GZIP. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Fichier - nom exemples {#file-name-examples}

### Scénario 1

Fichiers envoyés à un [!DNL Amazon S3] emplacement, avec *`PID-ALIAS="XYZCustomer"`* et avec [!DNL Google Advertiser IDs] dans le contenu du fichier.

Fichiers incrémentiels :

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000001.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000002.sync.gz </code> </li> 
</ul>

Fichiers complets :

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000001.sync.gz </code> </li> 
</ul>

### Scénario 2

Fichiers envoyés à [!DNL FTP] l'emplacement, sans *`PID-ALIAS`* et avec [!DNL Apple Advertiser IDs] dans le contenu du fichier :

Fichiers incrémentiels :

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_iter_1486140843000001.sync.gz </code> </li> 
</ul>

Fichiers complets :

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_full_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_full_1486140843000001.sync.gz </code> </li> 
</ul>

**Scénario 3**: Fichiers envoyés à [!DNL FTP] l'emplacement, avec *`PID-ALIAS="XYZCustomer"`* et avec User - id tiers - id dans le contenu du fichier ( *`Vendor ID=45454`*) :

Fichiers incrémentiels :

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
</ul>

Fichiers complets :

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200001.sync.gz </code> </li> 
</ul>

## Contenu du fichier de données sortantes : Syntaxe et paramètres {#outbound-contents-syntax}

Décrit les champs, la syntaxe et les conventions nécessaires pour organiser les informations dans un fichier de données sortant. Mettez en forme vos données conformément à ces spécifications.

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>Les éléments de style (`monospaced text`, *italique*, crochets `[ ]``( )`, etc.) dans ce document indique les éléments et options du code. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../../reference/code-style-elements.md).

### Syntaxe

Les champs du fichier de données s'affichent dans cet ordre :

`UUID<SPACE>SEGMENT_1,SEGMENT_2<SPACE>REMOVED_SEGMENT_,...`

### Paramètres

Le tableau répertorie les variables qui définissent le contenu d'un fichier de données.

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
   <td colname="col2"> <p>Utilisateur unique - id attribué par <span class="keyword"> Audience Manager </span>. </p> </td> 
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
   <td colname="col2"> <p>Identifiant de segment à partir duquel l'utilisateur a été disqualifié. Séparez plusieurs segments par une virgule. Avec une synchronisation complète, vous pouvez ignorer les segments supprimés car le fichier de données contiendra la liste complète des segments actuels pour l'utilisateur. En général, vous souhaitez connaître les segments auxquels un utilisateur appartient plutôt que ceux qu'il a supprimés. Voir aussi <a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples"> Fichier de données sortantes - nom : Syntaxe et exemples </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exemple : Format de fichier de base

Un fichier de données correctement formaté peut ressembler à l'exemple suivant. Cette entrée de fichier indique qu'un utilisateur est admissible pour les segments 24, 26 et 27. Si nécessaire, un espace sépare les identifiants `UUID` et les segments. Un autre espace sépare les ensembles d'ID de segment. Dans cet exemple, un utilisateur appartient aux segments 24, 26 et 27. Elles ont été supprimées des segments 25 et 28.

```
59767559181262060060278870901087098252  24,26,27  25,28
```
