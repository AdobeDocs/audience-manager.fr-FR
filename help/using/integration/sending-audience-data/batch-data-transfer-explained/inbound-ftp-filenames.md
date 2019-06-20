---
description: Décrit les champs obligatoires, la syntaxe, les conventions d'affectation de nom et les tailles de fichier à suivre lors de l'envoi de données à Audience Manager. Définissez les noms et tailles de vos fichiers conformément à ces spécifications lorsque vous envoyez des données à un répertoire FTP Audience Manager.
seo-description: Décrit les champs obligatoires, la syntaxe, les conventions d'affectation de nom et les tailles de fichier à suivre lors de l'envoi de données à Audience Manager. Définissez les noms et tailles de vos fichiers conformément à ces spécifications lorsque vous envoyez des données à un répertoire FTP Audience Manager.
seo-title: Exigences en matière de nom FTP et de taille de fichier pour les fichiers de données entrants
solution: Audience Manager
title: Exigences en matière de nom FTP et de taille de fichier pour les fichiers de données entrants
uuid: 49 eaafac -5 cb 0-482 f -872 a -84 c 056016 bdb
translation-type: tm+mt
source-git-commit: ec2d05290874a95e9cc9b8318fcc5e1e1986f5b9

---


# FTP Name and File Size Requirements for Inbound Data Files{#ftp-name-and-file-size-requirements-for-inbound-data-files}

Décrit les champs obligatoires, la syntaxe, les conventions d&#39;affectation de nom et les tailles de fichier à suivre lors de l&#39;envoi de données à Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager [!DNL FTP] directory.

>[!WARNING]
>
>Le transfert FTP pour les fichiers de données entrants n&#39;est plus pris en charge. Utilisez Amazon S 3 pour accéder aux données hors ligne. See [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) for details.

>[!NOTE]
>
>Les styles de texte (`monospaced text`, *italiques*, crochets `[ ]` `( )`, etc.) dans ce document indique les éléments et options du code. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../../reference/code-style-elements.md).

## File Name Syntax {#file-name-syntax}

[!DNL FTP] Les noms de fichier contiennent les éléments obligatoires et facultatifs suivants :

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

For other accepted file name formats, see [Custom Partner Integrations](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE] {importance = « high »}
>
>[!DNL Audience Manager] uniquement les processus [!DNL ASCII] et [!DNL UTF-8] les fichiers codés.

### Nommer les éléments

The table defines the elements in an [!DNL FTP] file name.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fichier - nom de l'élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_ dpm_</code> </p> </td> 
   <td colname="col2"> <p>The path to and name of your <span class="keyword"> Audience Manager</span> FTP directory. Contactez votre gestionnaire de compte pour connaître le répertoire FTP et les informations d'identification. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>An lD that tells <span class="keyword"> Audience Manager</span> if a data file contains your own user IDs or Android or iOS IDs. Accepte les options suivantes : </p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>ID du partenaire de données :</b> Il s'agit d'un identifiant unique attribué par Audience Manager à votre société ou organisation. Utilisez l'ID attribué dans un fichier - nom lors de l'envoi de données contenant votre propre utilisateur - id. For example, <code>...ftp_dpm_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that a partner with ID 21 sent the file and it contains user IDs assigned by that partner. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID (GAID) :</b> Utilisez l'ID 20914 dans un fichier de données - nom s'il contient un ID Android. For example, <code>...ftp_dpm_20914_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains Android IDs only. </li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>ID ios (IDFA) :</b> Utilisez l'ID 20915 dans un fichier de données - nom s'il contient des ID ios. For example, <code>...ftp_dpm_20915_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains iOS IDs only. </li> 
    </ul> <p> <p>Remarque : Ne mélanger pas de types d'ID dans vos fichiers de données. Par exemple, si votre fichier comporte l'identifiant Android, ne placez pas d'ID ios ni vos propres ID dans le fichier de données. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>_ DPID_ TARGET_ DATA_ OWNER</i></code> </p> </td> 
   <td colname="col2"> <p>Balise d'emplacement pour un identifiant. For example, you could set it to your <span class="keyword"> Audience Manager</span> ID if you set the DPID to a data source ID or an Android or iOS ID. This lets <span class="keyword"> Audience Manager</span> link the file data back to your organization. </p> <p>Par exemple : </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> <code>… ftp_ dpm_ 33_ 21_ 1234567890. sync</code> indique qu'un partenaire avec l'ID 21 a envoyé des données à partir d'une source de données utilisant l'ID 33. </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> <code>… ftp_ dpm_ 20914_ 21_ 1234567890. sync</code> indique qu'un partenaire avec l'ID 21 a envoyé des données contenant des ID Android. </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> <code>… ftp_ dpm_ 20915_ 21_ 1234567890. sync</code> indique qu'un partenaire avec l'ID 21 a envoyé des données qui contiennent des ID ios. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (. sync |. overwrite))</code> </p> </td> 
   <td colname="col2"> <p>Options de synchronisation qui incluent : </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> synchronisation</code>: Scénario normal lorsque des fournisseurs de données tiers envoient des caractéristiques par utilisateur à ajouter ou à supprimer dans le système Audience Manager. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Permet aux clients et aux fournisseurs de données d'envoyer une liste de caractéristiques par utilisateur qui doit remplacer toutes les caractéristiques existantes de cet utilisateur pour une source de données donnée dans Audience Manager. Il n'est pas nécessaire d'inclure tous les utilisateurs dans un fichier de remplacement. Incluez uniquement les utilisateurs que vous souhaitez modifier. Les caractéristiques qui ne sont pas affectées à la source de données cible ne seront pas effacées. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_ NUMBER</i></code>] </p> </td> 
   <td colname="col2"> <p>Entier. Utilisé lorsque vous fractionnez des fichiers volumineux en plusieurs parties afin d'améliorer les temps de traitement. Le nombre indique la partie du fichier d'origine dans lequel vous envoyez le fichier. </p> <p>Pour un traitement efficace des fichiers, divisez vos fichiers de données comme indiqué ci-dessous : </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Décompressé : 1 Go </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Compressé : 200-300 Mo </li> 
    </ul> <p>See the first 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> file name examples</a> below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP</i></code> </p> </td> 
   <td colname="col2"> <p>Horodatage UTC UNIX de 10 chiffres, en secondes. L'horodatage permet de rendre chaque fichier unique. </p> 
    <draft-comment> 
     <p> <p>Remarque : Audience Manager n'utilise pas l'horodatage pendant le traitement des fichiers entrants. L'horodatage du nom de fichier est obsolète dans Audience Manager, mais il est toujours requis pour la compatibilité ascendante. </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip est le format de compression autorisé pour un fichier FTP - nom. Si vous utilisez la compression de fichiers, assurez-vous que le fichier comporte l'extension appropriée. </p> <p>Les fichiers compressés doivent être de 3 Go ou plus. Si vos fichiers sont plus volumineux, contactez le service à la clientèle. Bien qu'Audience Manager puisse gérer des fichiers volumineux, nous pouvons vous aider à réduire la taille de vos fichiers et à améliorer l'efficacité des transferts de données. See <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> File Compression for Inbound Data Transfer Files</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Name Examples {#file-name-examples}

Les exemples suivants montrent les noms de fichier correctement formatés. Vos noms de fichier peuvent être similaires.

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_ dpm_ 478_ 1366545717. overwrite</code> </li> 
</ul>

[Téléchargez](assets/ftp_dpm_1234_1445374061.overwrite) le fichier d&#39;exemple si vous avez besoin d&#39;exemples supplémentaires. This file is saved with the `.overwrite` file extension. Ouvrez-le avec un éditeur de texte simple.

## Accepted File Sizes {#accepted-file-sizes}

Consider the figures below for fastest/earliest processing of your files as well as for file size limitations when you send data to an [!DNL Audience Manager] / [!DNL FTP] directory.

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
   <td colname="col2"> <p>200-300 Mo </p> </td> 
   <td colname="col3"> <p>3 Go </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Décompressé</b> </td> 
   <td colname="col2"> <p>1 Go </p> </td> 
   <td colname="col3"> <p>5 Go </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Exigences en matière de nom Amazon S3 pour les fichiers de données entrants](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

