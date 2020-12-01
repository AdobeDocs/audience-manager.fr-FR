---
description: Décrit les champs obligatoires, la syntaxe, les conventions d’affectation de nom et les tailles de fichiers à respecter lors de l’envoi de données à l’Audience Manager. Définissez les noms et tailles de vos fichiers en fonction de ces spécifications lorsque vous envoyez des données vers un répertoire FTP d’Audience Manager.
seo-description: Décrit les champs obligatoires, la syntaxe, les conventions d’affectation de nom et les tailles de fichiers à respecter lors de l’envoi de données à l’Audience Manager. Définissez les noms et tailles de vos fichiers en fonction de ces spécifications lorsque vous envoyez des données vers un répertoire FTP d’Audience Manager.
seo-title: Exigences en matière de nom et de taille de fichier FTP pour les fichiers de données entrants
solution: Audience Manager
title: Exigences en matière de nom et de taille de fichier FTP pour les fichiers de données entrants
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: f037a12af641da44ed67e62a249c41487da7ac07
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 8%

---


# [!DNL FTP]Exigences en matière de nom et de taille de fichier pour les fichiers de données entrants{#ftp-name-and-file-size-requirements-for-inbound-data-files}

Décrit les champs obligatoires, la syntaxe, les conventions d’affectation de nom et les tailles de fichiers à respecter lors de l’envoi de données à [!DNL Audience Manager]. Définissez les noms et les tailles de vos fichiers en fonction de ces spécifications lorsque vous envoyez des données à un répertoire d&#39;Audience Manager [!DNL FTP].

>[!WARNING]
>
>Nous supprimons progressivement la prise en charge des configurations [!DNL FTP]. Bien que l&#39;assimilation de fichiers de données entrants soit toujours prise en charge dans les intégrations [!DNL FTP] existantes, nous vous recommandons vivement d&#39;utiliser [!DNL Amazon S3] pour intégrer des données hors ligne pour les nouvelles intégrations. Pour plus d’informations, consultez [Exigences en matière de nom et de taille de fichier Amazon S3 pour les fichiers de données entrants](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md).

>[!NOTE]
>
>Les styles de texte (`monospaced text`, *italiques*, crochets `[ ]` `( )`, etc.) dans ce document, indiquez les éléments de code et les options. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../../reference/code-style-elements.md).

## Syntaxe du nom de fichier {#file-name-syntax}

[!DNL FTP] les noms de fichier contiennent les éléments obligatoires et facultatifs suivants :

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Pour connaître les autres formats de nom de fichier acceptés, voir [Intégrations de partenaire personnalisées](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>[!DNL Audience Manager] traite uniquement  [!DNL ASCII] et  [!DNL UTF-8] les fichiers codés.

### Nommer les éléments

Le tableau définit les éléments dans un nom de fichier [!DNL FTP].

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
   <td colname="col2"> <p>Chemin d’accès et nom de votre répertoire FTP <span class="keyword"> Audience Manager</span>. Contactez votre gestionnaire de compte pour connaître le répertoire FTP et les informations d’identification. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Un identifiant qui indique à <span class="keyword"> Audience Manager</span> si un fichier de données contient vos propres ID utilisateur, ID Android, ID iOS ou autres ID appartenant à <a href="/help/using/features/global-data-sources.md"> les sources de données globales </a>. Accepte les options suivantes :</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>ID de source de données (également appelé ID du fournisseur de données) : </b> Il s’agit d’un identifiant unique attribué par l’Audience Manager à une source de données (reportez-vous à l’ <a href="/help/using/reference/ids-in-aam.md"> index d’Audience Manager des ID  </a>). Utilisez cet ID affecté dans un nom de fichier lors de l’envoi de données contenant vos propres ID utilisateur. Par exemple, <code>...ftp_dpm_21_123456789.sync</code> indique à <span class="keyword"> Audience Manager</span> des données embarquées à des ID appartenant à la source de données 21. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Identifiants Android (GAID) : </b> utilisez ID 20914 dans un nom de fichier de données s’il contient des identifiants Android. Vous devez utiliser le champ <code><i>_DPID_TARGET_DATA_OWNER</i></code> lorsque vous utilisez des ID Android. Par exemple, <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> indique à <span class="keyword"> Audience Manager</span> que le fichier de données contient uniquement des identifiants Android et que ces identifiants doivent correspondre aux caractéristiques appartenant à la source de données <code><i>_DPID_TARGET_DATA_OWNER</i></code>.</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>ID iOS (IDFA) : </b> utilisez ID 20915 dans un nom de fichier de données s’il contient des ID iOS. Vous devez utiliser le champ <code><i>_DPID_TARGET_DATA_OWNER</i></code> lorsque vous utilisez des ID iOS. Par exemple, <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> indique à <span class="keyword"> Audience Manager</span> que le fichier de données contient uniquement des ID iOS et que ces identifiants doivent correspondre aux caractéristiques de la source de données <code><i>_DPID_TARGET_DATA_OWNER</i></code>.</li>
     <li> <b>ID appartenant à d’autres sources</b> de données globales : Vous pouvez embarquer des identifiants Roku pour la publicité (RIDA), des identifiants Microsoft Advertising (MAID) et d’autres identifiants. Utilisez l’identifiant correspondant à chaque source de données, comme décrit dans l’article <a href="/help/using/features/global-data-sources.md"> sources de données globales </a>.</li> 
    </ul> <p> <p>Remarque :  Ne mélangez pas les types d’ID dans vos fichiers de données. Par exemple, si votre nom de fichier contient l’identifiant Android, n’insérez pas d’ID iOS ou vos propres ID dans le fichier de données. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Ce champ indique à l’Audience Manager à quelle source de données intégrer les données. Ce champ est obligatoire si vous définissez le DPID sur un ID Android, un ID iOS ou un autre ID appartenant à des sources de données globales. Cela permet à <span class="keyword"> Audience Manager</span> de lier les données de fichier à votre organisation. </p> <p>Par exemple : </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> indique à l’Audience Manager que vous définissez des ID de client appartenant à la source de données 33 pour les caractéristiques ou les signaux appartenant à la source de données 21. </li> 
     <li> <b>Identifiants Android (GAID) : </b> <code>...ftp_dpm_20914_21_1234567890.sync</code> indique à  <span class="keyword"> Audience </span> Manager que le fichier de données contient uniquement des identifiants Android et que ces identifiants doivent correspondre aux caractéristiques de la source de données 21.</li> 
     <li> <b>Identifiants iOS (IDFA) : </b> <code>...ftp_dpm_20915_21_1234567890.sync</code> indique à  <span class="keyword"> Audience </span> Manager que le fichier de données contient uniquement des identifiants iOS et que ces identifiants doivent correspondre aux caractéristiques de la source de données 21.</li>
     <li> <b>ID appartenant à d’autres sources</b> de données globales :  <code>...ftp_dpm_121963_21_1234567890.sync</code> indique à  <span class="keyword"> Audience </span> Manager que le fichier de données contient uniquement des identifiants Roku et que ces identifiants doivent être inclus dans les caractéristiques appartenant à la source de données 21. Utilisez l’identifiant correspondant à chaque source de données, comme décrit dans l’article <a href="/help/using/features/global-data-sources.md"> sources de données globales </a>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Options de synchronisation comprenant : </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Scénario normal lorsque des fournisseurs de données tiers envoient des caractéristiques par utilisateur pour être ajoutées ou supprimées dans le système d’Audience Manager. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Permet aux clients et aux fournisseurs de données d’envoyer une liste de caractéristiques par utilisateur qui doit remplacer toutes les caractéristiques existantes de cet utilisateur pour une source de données donnée en Audience Manager. Vous n’avez pas besoin d’inclure tous vos utilisateurs dans un fichier de remplacement. Incluez uniquement les utilisateurs que vous souhaitez modifier. Les caractéristiques qui ne sont pas attribuées à la source de données de cible ne seront pas effacées. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Entier. Utilisé lorsque vous divisez des fichiers volumineux en plusieurs parties afin d’améliorer les temps de traitement. Le numéro indique la partie du fichier d'origine que vous envoyez. </p> <p>Pour un traitement efficace des fichiers, fractionnez vos fichiers de données comme indiqué : </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Non compressé : 1 Go </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Comprimé : 200 à 300 Mo </li> 
    </ul> <p>Voir les 2 premiers exemples de noms de fichier <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"></a> ci-dessous. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Horodatage UTC UNIX à 10 chiffres en secondes. L’horodatage permet de rendre chaque nom de fichier unique. </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip est le format de compression autorisé pour un nom de fichier FTP. Si vous utilisez la compression de fichier, assurez-vous que le nom de fichier possède l’extension appropriée. </p> <p>Les fichiers compressés doivent être de 3 Go ou moins. Si vos fichiers sont plus volumineux, contactez le service d’assistance clientèle. Bien que l'Audience Manager puisse gérer des fichiers volumineux, nous pouvons vous aider à réduire la taille de vos fichiers et à rendre les transferts de données plus efficaces. Voir <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">Compression de fichiers pour les fichiers de transfert de données entrants</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemples de noms de fichier {#file-name-examples}

Les exemples suivants montrent des noms de fichier correctement formatés. Vos noms de fichier peuvent ressembler.

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

[Téléchargez ](assets/ftp_dpm_1234_1445374061.overwrite) le fichier d’exemple si vous avez besoin d’exemples supplémentaires. Ce fichier est enregistré avec l&#39;extension de fichier `.overwrite`. Ouvrez-le dans un éditeur de texte simple.

## Taille de fichier acceptée {#accepted-file-sizes}

Tenez compte des chiffres ci-dessous pour le traitement le plus rapide/le plus précoce de vos fichiers ainsi que pour les limites de taille de fichier lorsque vous envoyez des données dans un répertoire [!DNL Audience Manager] / [!DNL FTP].

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
   <td colname="col2"> <p>200 à 300 Mo </p> </td> 
   <td colname="col3"> <p>3 Go </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Non compressé</b> </td> 
   <td colname="col2"> <p>1 Go </p> </td> 
   <td colname="col3"> <p>5 Go </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Exigences en matière de nom Amazon S3 pour les fichiers de données entrants](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

