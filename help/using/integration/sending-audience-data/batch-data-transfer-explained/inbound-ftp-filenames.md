---
description: Décrit les champs obligatoires, la syntaxe, les conventions d’affectation des noms et les tailles de fichiers à respecter lors de l’envoi de données à Audience Manager. Définissez les noms et les tailles de vos fichiers selon ces spécifications lorsque vous envoyez des données vers un répertoire FTP d’Audience Manager.
seo-description: Décrit les champs obligatoires, la syntaxe, les conventions d’affectation des noms et les tailles de fichiers à respecter lors de l’envoi de données à Audience Manager. Définissez les noms et les tailles de vos fichiers selon ces spécifications lorsque vous envoyez des données vers un répertoire FTP d’Audience Manager.
seo-title: Exigences relatives au nom FTP et à la taille des fichiers pour les fichiers de données entrants
solution: Audience Manager
title: Exigences relatives au nom FTP et à la taille des fichiers pour les fichiers de données entrants
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
translation-type: tm+mt
source-git-commit: ec2d05290874a95e9cc9b8318fcc5e1e1986f5b9

---


# Exigences relatives au nom FTP et à la taille des fichiers pour les fichiers de données entrants{#ftp-name-and-file-size-requirements-for-inbound-data-files}

Décrit les champs obligatoires, la syntaxe, les conventions d’affectation des noms et les tailles de fichiers à respecter lors de l’envoi de données à Audience Manager. Définissez les noms et les tailles de vos fichiers en fonction de ces spécifications lorsque vous envoyez des données vers un [!DNL FTP] répertoire Audience Manager.

>[!WARNING]
>
>Le transfert FTP pour les fichiers de données entrants n’est plus pris en charge. Utilisez Amazon S3 pour embarquer des données hors ligne. Pour plus d’informations, voir Exigences en matière de nom et de taille de fichier [Amazon S3 pour les fichiers](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) de données entrants.

>[!NOTE]
>
>Les styles de texte (`monospaced text`, *italiques*, crochets `[ ]` `( )`, etc.) dans ce document, indiquez les éléments de code et les options. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../../reference/code-style-elements.md).

## Syntaxe du nom de fichier {#file-name-syntax}

[!DNL FTP] les noms de fichier contiennent les éléments obligatoires et facultatifs suivants :

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Pour connaître les autres formats de nom de fichier acceptés, reportez-vous à la page Intégrations [de partenaire](/help/using/integration/sending-audience-data/custom-partner-integrations.md)personnalisées.

>[!NOTE] {importance="high"}
>
>[!DNL Audience Manager] traite uniquement [!DNL ASCII] et les fichiers [!DNL UTF-8] codés.

### Eléments de nom

Le tableau définit les éléments d’un nom de [!DNL FTP] fichier.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elément Nom de fichier </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_dpm_</code> </p> </td> 
   <td colname="col2"> <p>Chemin d’accès et nom du répertoire FTP d’Audience Manager <span class="keyword"></span> . Contactez votre gestionnaire de compte pour connaître le répertoire FTP et les informations d’identification. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>Un identifiant qui indique à <span class="keyword"> Audience Manager</span> si un fichier de données contient vos propres ID utilisateur, Android ou iOS. Accepte les options suivantes : </p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b></b> ID du partenaire de données :Il s’agit d’un identifiant unique attribué par Audience Manager à votre entreprise ou organisation. Utilisez cet ID affecté dans un nom de fichier lors de l’envoi de données contenant vos propres ID utilisateur. Par exemple, <code>...ftp_dpm_21_123456789.sync</code> indique à <span class="keyword"> Audience Manager</span> qu’un partenaire avec l’ID 21 a envoyé le fichier et qu’il contient les ID utilisateur attribués par ce partenaire. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b></b> Identifiants Android (GAID) : Utilisez l’ID 20914 dans un nom de fichier de données s’il contient un ID Android. Par exemple, <code>...ftp_dpm_20914_123456789.sync</code> indique à <span class="keyword"> Audience Manager</span> que le fichier de données contient uniquement des ID Android. </li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b></b> ID iOS (IDFA) : Utilisez l’ID 20915 dans un nom de fichier de données s’il contient des ID iOS. Par exemple, <code>...ftp_dpm_20915_123456789.sync</code> indique à <span class="keyword"> Audience Manager</span> que le fichier de données contient uniquement des ID iOS. </li> 
    </ul> <p> <p>Remarque :  Ne mélangez pas les types d’ID dans vos fichiers de données. Par exemple, si votre nom de fichier contient l’identifiant Android, ne placez pas d’ID iOS ni vos propres ID dans le fichier de données. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i></code> </p> </td> 
   <td colname="col2"> <p>Espace réservé pour un ID. Vous pouvez, par exemple, le définir sur votre <span class="keyword"> ID Audience Manager</span> si vous définissez le DPID sur un ID de source de données ou un ID Android ou iOS. Cela permet à <span class="keyword"> Audience Manager</span> de lier les données de fichier à votre entreprise. </p> <p>Par exemple : </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> <code>...ftp_dpm_33_21_1234567890.sync</code> montre un partenaire dont l’ID 21 a envoyé des données à partir d’une source de données qui utilise l’ID 33. </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> <code>...ftp_dpm_20914_21_1234567890.sync</code> montre qu’un partenaire avec l’ID 21 a envoyé des données contenant des ID Android. </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> <code>...ftp_dpm_20915_21_1234567890.sync</code> montre qu’un partenaire avec l’ID 21 a envoyé des données contenant des ID iOS. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync|.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Options de synchronisation comprenant : </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Scénario normal lorsque des fournisseurs de données tiers envoient des caractéristiques par utilisateur pour être ajoutées ou supprimées dans le système Audience Manager. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> écraser</code>: Permet aux clients et aux fournisseurs de données d’envoyer une liste de caractéristiques par utilisateur qui doit remplacer toutes les caractéristiques existantes de cet utilisateur pour une source de données donnée dans Audience Manager. Vous n’avez pas besoin d’inclure tous vos utilisateurs dans un fichier de remplacement. Incluez uniquement les utilisateurs que vous souhaitez modifier. Les caractéristiques qui ne sont pas attribuées à la source de données cible ne seront pas effacées. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i></code>] </p> </td> 
   <td colname="col2"> <p>Entier. Utilisé lorsque vous divisez des fichiers volumineux en plusieurs parties afin d’améliorer les temps de traitement. Le numéro indique la partie du fichier d’origine que vous envoyez. </p> <p>Pour un traitement de fichiers efficace, répartissez vos fichiers de données comme indiqué : </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Non compressé : 1 Go </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Compressé : 200 à 300 Mo </li> 
    </ul> <p>Voir les 2 premiers exemples <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> de noms de</a> fichier ci-dessous. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>HORODATAGE</i></code> </p> </td> 
   <td colname="col2"> <p>Horodatage UTC UNIX à 10 chiffres en secondes. L’horodatage permet de rendre chaque nom de fichier unique. </p> 
    <draft-comment> 
     <p> <p>Remarque :  Audience Manager n’utilise pas l’horodatage lors du traitement des fichiers entrants. L’horodatage du nom de fichier a été abandonné dans Audience Manager, mais il est toujours nécessaire pour une compatibilité descendante. </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip est le format de compression autorisé pour un nom de fichier FTP. Si vous utilisez la compression de fichier, assurez-vous que le nom de fichier possède l’extension appropriée. </p> <p>Les fichiers compressés doivent être de 3 Go ou moins. Si vos fichiers sont plus volumineux, contactez le service à la clientèle. Bien qu’Audience Manager puisse gérer des fichiers volumineux, nous pouvons vous aider à réduire la taille de vos fichiers et à rendre les transferts de données plus efficaces. Voir <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> Compression de fichiers pour les fichiers</a> de transfert de données entrants. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemples de noms de fichier {#file-name-examples}

Les exemples suivants montrent des noms de fichier correctement formatés. Vos noms de fichier peuvent être similaires.

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

[Téléchargez](assets/ftp_dpm_1234_1445374061.overwrite) le fichier d’exemple si vous avez besoin d’exemples supplémentaires. Ce fichier est enregistré avec l’extension de `.overwrite` fichier. Ouvrez-le dans un éditeur de texte simple.

## Taille de fichier acceptée {#accepted-file-sizes}

Tenez compte des chiffres ci-dessous pour le traitement le plus rapide/le plus précoce de vos fichiers ainsi que pour les limitations de taille de fichier lorsque vous envoyez des données vers un [!DNL Audience Manager] / [!DNL FTP] répertoire.

<table id="table_59FCC63806684DF8BE54A1EAF224A234"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de fichier </th> 
   <th colname="col2" class="entry"> Taille optimale </th> 
   <th colname="col3" class="entry"> Taille maximale </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Compressé</b> </td> 
   <td colname="col2"> <p> 200 à 300 Mo </p> </td> 
   <td colname="col3"> <p>3 Go </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Non compressé</b> </td> 
   <td colname="col2"> <p>1 Go </p> </td> 
   <td colname="col3"> <p>5 Go </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_This]
>
>* [Exigences en matière de nom Amazon S3 pour les fichiers de données entrants](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

