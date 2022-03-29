---
description: Décrit les champs, la syntaxe, les conventions de nommage et les tailles de fichier requis à respecter lors de l’envoi de données à Audience Manager. Définissez les noms et les tailles de vos fichiers en fonction de ces spécifications lorsque vous envoyez des données vers un répertoire FTP d’Audience Manager.
seo-description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager FTP directory.
seo-title: FTP Name and File Size Requirements for Inbound Data Files
solution: Audience Manager
title: Exigences en matière de nom et de taille de fichier FTP pour les fichiers de données entrants
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
feature: Inbound Data Transfers
exl-id: 9c889214-7075-4392-9ed5-f07b91e7b50a
source-git-commit: a5506a315a98afdf31f8f52fac09b9179f388f30
workflow-type: tm+mt
source-wordcount: '1096'
ht-degree: 6%

---

# [!DNL FTP]Exigences en matière de nom et de taille de fichier pour les fichiers de données entrants {#ftp-name-and-file-size-requirements-for-inbound-data-files}

Décrit les champs, la syntaxe, les conventions de dénomination et les tailles de fichiers requis à respecter lors de l’envoi de données à [!DNL Audience Manager]. Définissez les noms et les tailles de vos fichiers en fonction de ces spécifications lorsque vous envoyez des données à une Audience Manager. [!DNL FTP] répertoire .

>[!WARNING]
>
>Nous supprimons progressivement la prise en charge de [!DNL FTP] configurations. Bien que l’ingestion de fichiers de données entrants soit toujours prise en charge dans les [!DNL FTP] intégrations, il est vivement recommandé d’utiliser [!DNL Amazon S3] pour intégrer des données hors ligne pour les nouvelles intégrations. Pour plus d’informations, consultez [Exigences en matière de nom et de taille de fichier Amazon S3 pour les fichiers de données entrants](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md).

>[!NOTE]
>
>Les styles de texte (`monospaced text`, *italiques*, crochets `[ ]` `( )`, etc.) dans ce document, indiquez les éléments de code et les options. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../../reference/code-style-elements.md).

## Syntaxe du nom de fichier {#file-name-syntax}

[!DNL FTP] Les noms de fichier contiennent les éléments obligatoires et facultatifs suivants :

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Pour connaître les autres formats de nom de fichier acceptés, voir [Intégrations personnalisées des partenaires](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>[!DNL Audience Manager] processus uniquement [!DNL ASCII] et [!DNL UTF-8] fichiers codés.

### Nom Elements

Le tableau définit les éléments d’une [!DNL FTP] nom du fichier.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elément Nom du fichier </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_dpm_</code> </p> </td> 
   <td colname="col2"> <p>Le chemin d’accès et le nom de votre <span class="keyword"> Audience Manager</span> Répertoire FTP. Contactez votre gestionnaire de compte pour connaître le répertoire FTP et les informations d’identification. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Un identifiant qui indique <span class="keyword"> Audience Manager</span> si un fichier de données contient vos propres ID utilisateur, Android, iOS ID ou autres ID appartenant à <a href="/help/using/features/global-data-sources.md"> sources de données globales</a>. Accepte les options suivantes :</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>ID de source de données (également appelé ID de fournisseur de données) :</b> Il s’agit d’un identifiant unique attribué par l’Audience Manager à une source de données (voir l’Audience Manager <a href="/help/using/reference/ids-in-aam.md"> index des identifiants </a>). Utilisez cet identifiant attribué dans un nom de fichier lors de l’envoi de données contenant vos propres identifiants utilisateur. Par exemple : <code>...ftp_dpm_21_123456789.sync</code> indique <span class="keyword"> Audience Manager</span> pour intégrer des données à des identifiants appartenant à la source de données 21. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Identifiants Android (GAID) :</b> Utilisez ID 20914 dans un nom de fichier de données s’il contient des identifiants Android. Vous devez utiliser le champ <code><i>_DPID_TARGET_DATA_OWNER</i></code> lorsque vous utilisez des identifiants Android. Par exemple : <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> indique <span class="keyword"> Audience Manager</span> que le fichier de données contient uniquement des identifiants Android et que ces identifiants doivent être qualifiés pour les caractéristiques appartenant à la variable <code><i>_DPID_TARGET_DATA_OWNER</i></code> source de données.</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS ID (IDFA) :</b> Utilisez l’ID 20915 dans un nom de fichier de données s’il contient des iOS ID. Vous devez utiliser le champ <code><i>_DPID_TARGET_DATA_OWNER</i></code> lorsque vous utilisez des iOS ID. Par exemple : <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> indique <span class="keyword"> Audience Manager</span> que le fichier de données contient uniquement des iOS ID et que ces ID doivent être qualifiés pour les caractéristiques appartenant à la variable <code><i>_DPID_TARGET_DATA_OWNER</i></code> source de données.</li>
     <li> <b>ID appartenant à d’autres sources de données globales</b>: Vous pouvez intégrer des identifiants Roku pour la publicité (RIDA), des identifiants Microsoft Advertising (MAID) et d’autres identifiants. Utilisez l’identifiant correspondant à chaque source de données, comme décrit dans la section <a href="/help/using/features/global-data-sources.md"> article relatif aux sources de données globales</a>.</li> 
    </ul> <p> <p>Remarque : Ne mélangez pas les types d’ID dans vos fichiers de données. Si, par exemple, votre nom de fichier contient l’identifiant Android, ne placez pas d’iOS ID ni vos propres identifiants dans le fichier de données. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Ce champ indique à l’Audience Manager à quelle source de données intégrer les données. Ce champ est obligatoire si vous définissez le DPID sur un Android ID ou un iOS ID ou un autre ID appartenant à des sources de données globales. Cette variable permet de <span class="keyword"> Audience Manager</span> liez les données de fichier à votre organisation. <br> Cette source de données cible doit appartenir à votre entreprise. À des fins de partage de données de deuxième niveau, pour ingérer des données dans une source de données cible appartenant à une autre entreprise, vous devez disposer d’un mappage d’accès entre votre entreprise et la source de données cible. Contactez votre conseiller en Adobe ou le service clientèle pour configurer le mappage.</p><p><b>Remarque importante :</b> You <i>ne pas</i> Vous devez demander un mappage pour les relations de partage de données existantes (pour les sources de données cibles appartenant à d’autres sociétés dans lesquelles vous avez intégré des données avant le 14 mars 2022). Le mappage n’est pas non plus requis lors de l’intégration de données dans des sources de données cibles appartenant à votre PID. </p> <p>Par exemple : </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> indique à l’Audience Manager que vous qualifiez des ID de client appartenant à la source de données 33 pour des caractéristiques ou des signaux appartenant à la source de données 21. </li> 
     <li> <b>Identifiants Android (GAID) :</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> indique <span class="keyword"> Audience Manager</span> que le fichier de données contient uniquement des identifiants Android et que ces identifiants doivent correspondre aux caractéristiques appartenant à la source de données 21.</li> 
     <li> <b>iOS ID (IDFA) :</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> indique <span class="keyword"> Audience Manager</span> que le fichier de données contient uniquement des iOS ID et que ces ID doivent être qualifiés pour les caractéristiques appartenant à la source de données 21.</li>
     <li> <b>ID appartenant à d’autres sources de données globales</b>: <code>...ftp_dpm_121963_21_1234567890.sync</code> indique <span class="keyword"> Audience Manager</span> que le fichier de données contient uniquement des identifiants Roku et que ceux-ci doivent correspondre aux caractéristiques appartenant à la source de données 21. Utilisez l’identifiant correspondant à chaque source de données, comme décrit dans la section <a href="/help/using/features/global-data-sources.md"> article relatif aux sources de données globales</a>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Options de synchronisation comprenant : </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Scénario normal lorsque des fournisseurs de données tiers envoient des caractéristiques par utilisateur pour être ajoutés ou supprimés dans le système d’Audience Manager. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Permet aux clients et aux fournisseurs de données d’envoyer une liste de caractéristiques par utilisateur qui doit remplacer toutes les caractéristiques existantes de cet utilisateur pour une source de données donnée dans l’Audience Manager. Vous n’avez pas besoin d’inclure tous vos utilisateurs dans un fichier de remplacement. Incluez uniquement les utilisateurs que vous souhaitez modifier. Les caractéristiques qui ne sont pas affectées à la source de données cible ne seront pas effacées. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Entier. Utilisé lorsque vous divisez des fichiers volumineux en plusieurs parties afin d’améliorer les temps de traitement. Le numéro indique la partie du fichier d’origine que vous envoyez. </p> <p>Pour optimiser le traitement des fichiers, divisez vos fichiers de données comme indiqué : </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Décompressé : 1 Go </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Compressé : 200 à 300 Mo </li> 
    </ul> <p>Voir les 2 premières <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> exemples de nom de fichier</a> ci-dessous. </p> </td> 
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
   <td colname="col2"> <p>Gzip est le format de compression autorisé pour un nom de fichier FTP. Si vous utilisez la compression de fichier, assurez-vous que le nom de fichier possède l’extension appropriée. </p> <p>Les fichiers compressés doivent être de 3 Go ou moins. Si vos fichiers sont plus volumineux, contactez l’assistance clientèle. Bien que l’Audience Manager puisse gérer des fichiers volumineux, nous pouvons vous aider à réduire la taille de vos fichiers et à optimiser les transferts de données. Voir <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">Compression de fichiers pour les fichiers de transfert de données entrants</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemples de noms de fichier {#file-name-examples}

Les exemples suivants présentent des noms de fichier correctement formatés. Vos noms de fichier peuvent ressembler à ceux-ci.

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

[Télécharger](assets/ftp_dpm_1234_1445374061.overwrite) le fichier d’exemple si vous avez besoin d’exemples supplémentaires. Ce fichier est enregistré avec le `.overwrite` extension de fichier. Ouvrez-le à l’aide d’un simple éditeur de texte.

## Tailles de fichiers acceptées {#accepted-file-sizes}

Tenez compte des chiffres ci-dessous pour le traitement le plus rapide/le plus ancien de vos fichiers ainsi que pour les limites de taille de fichier lorsque vous envoyez des données à un [!DNL Audience Manager] / [!DNL FTP] répertoire .

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
   <td colname="col1"><b>Décompressé</b> </td> 
   <td colname="col2"> <p>1 Go </p> </td> 
   <td colname="col3"> <p>5 Go </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Exigences en matière de nom Amazon S3 pour les fichiers de données entrants](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

