---
description: Questions fréquentes sur l'importation des données hors ligne dans Audience Manager.
keywords: ftp ou s 3 ; s 3 ou ftp
seo-description: Questions fréquentes sur l'importation des données hors ligne dans Audience Manager.
seo-title: FAQ sur l'assimilation des données client inbound
solution: Audience Manager
title: FAQ sur l'assimilation des données client inbound
uuid: 491 e 9 ec 1-4731-46 a 8-86 e 7-d 8 c 613 e 6 cedc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Inbound Customer Data Ingestion FAQ{#inbound-customer-data-ingestion-faq}

Questions fréquentes sur l&#39;importation des données hors ligne dans Audience Manager.

<br> 

<!-- 

c_inbound_crm_data_ingestion.xml

 -->

**Pouvez-vous résumer le processus d&#39;intégration ?**

The onboarding process consists of 2 core components described in [Batch Data Transfer Process Described](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process). Cela implique :

* Synchronisation des identifiants
* Inbound Data File ( [!DNL .sync] file or [!DNL .overwrite] file)

<!-- 

Removed the Data Translation File bullet from the list above.

 -->

Vous trouverez ci-dessous une liste des questions et réponses qui peuvent s&#39;avérer utiles après avoir examiné la documentation.

>[!NOTE]
>
>Les exemples de cette section sont simplifiés ou raccourcis à des fins de concision et de démonstration. Reportez-vous à la documentation Ingestion des données entrantes pour obtenir des spécifications détaillées sur les formats de fichier et la syntaxe.

<br> 

**Pouvez-vous résumer le processus de déploiement ?**

Nous vous recommandons de :

* Work with your data provider to format the daily inbound data file according to [!DNL Adobe] specifications.
* Transfer a test data file to [!DNL Adobe] for format verification.
* Work with your [!DNL Adobe] consultant to produce a taxonomy suitable for interpreting the contents of the data file.
* In the staging/development environment, confirm that the ID sync is configured to properly pick up the data provider&#39;s visitor ID and transfer it to the [!DNL Audience Manager] servers in realtime.
* Déployez la synchronisation DIL/ID en production. La synchronisation des identifiants sera déjà configurée comme module dans le code DIL par votre consultant Adobe.
* Transfer production data files to [!DNL Audience Manager]. En raison des dépendances liées aux mappages de synchronisation des identifiants, il est logique de commencer à transférer des données jusqu&#39;à une semaine après le déploiement du code de production, bien que vous puissiez commencer à transférer les fichiers de données dès que le code est en production.

<br> 

**Quel mode FTP dois-je utiliser pour transférer des fichiers compressés ou chiffrés ?**

See [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**Puis-je charger un fichier de données entrant (fichier[!DNL .sync]ou[!DNL .overwrite]) avant de déployer le code[!DNL Audience Manager]en production ?**

* If the data provider is configured to use [Profile Link](../features/profile-merge-rules/merge-rules-overview.md) for cross-device targeting, the data available for targeting shortly after an ID sync identifies to the matching [!DNL Audience Manager] visitor ID.

* If the data provider is not configured to use the [!UICONTROL Profile Link] feature, [!DNL Audience Manager] processes only the data for visitor IDs in the inbound data file that have been previously synced/matched back to an [!DNL Audience Manager] visitor ID.

Consider the following use cases in which the data provider is not configured to use [!UICONTROL Profile Merge]:

<table id="table_1A367ED6D016428FB21B3F3BC261BA98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cas d’utilisation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Cas 1</b> </p> </td> 
   <td colname="col2"> <p>Le lundi, un visiteur identifié dans la base de données de gestion de la relation client, lorsque le visiteur ABC se connecte, démarre une synchronisation des identifiants côté client. <span class="keyword"> Audience Manager</span> stocke le mappage du visiteur ABC vers <span class="keyword"> le visiteur d'Audience Manager</span> 123. </p> <p>On Tuesday, the CRM database transfers a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager </span>server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC « gender » = « male », « luxury_ shopper » = "yes"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">Identifie le visiteur ABC depuis le mappage de synchronisation des identifiants stockés. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Associates the traits <code> male</code> and <code> luxury_shopper</code> with the visitor 123 profile. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Cas 2</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the CRM database pushes a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF « gender » = « women », « wine_ enthousiassiast » = "yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager</span> ne dispose pas d'un enregistrement de ce visiteur (ou d'un identifiant visiteur associé) de sorte que cet enregistrement n'est pas traité. </p> <p>Le mardi, le visiteur DEF s'identifie. Cette action initie la première synchronisation des identifiants côté client pour ce visiteur. This action maps visitor DEF to <span class="keyword"> Audience Manager</span> ID 456. Cependant, ce visiteur ne dispose pas de données de gestion de la relation client associées à son profil. As a result, <span class="keyword"> Audience Manager</span> does not go back and reprocess old files. </p> <p>On Wednesday, the CRM database pushes another data file to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF « gender » = « women », « wine_ enthousiassiast » = « yes », « dma » = "paris"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">Identifie le cookie DEF du mappage de synchronisation des identifiants stockés. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Associates the traits <code> female</code>, <code> paris</code>, and <code> wine_enthusiast</code> with the visitor 456 profile. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Cas 3</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the <span class="keyword"> Audience Manager</span> server receives two files with the following records: </p> <p> <code> Fichier. sync</code> contenant : </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> <code> Fichier. overwrite</code> contenant : </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI « gender » = « homme » « wine_ enthousiassiast » = "no"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL « gender » = « female_ enthousiassiast » = "yes"</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> dispose d'un enregistrement MKL du visiteur JKL à l'ID 789, à partir d'une synchronisation des identifiants précédente. </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">Identifie JKL du visiteur depuis le mappage de synchronisation des identifiants stockés. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Associates the traits <code> female</code> and <code> wine_enthusiast</code> with visitor ID 789's profile. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">Ignore l'association de caractéristique pour GHI du visiteur, car son identifiant n'a été synchronisé que dans le lot actuel. To associate traits with visitor GHI, you need to include them in future <code> .overwrite</code> files. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**À quelle heure dois-je transférer mon fichier ?**

[!DNL Audience Manager] recherche et traite plusieurs fichiers à plusieurs reprises tout au long de la journée. Téléchargez vos données dès que vous êtes prêt.

<br> 

**Combien de temps faut-il avant que les données d&#39;un fichier téléchargé ne soient disponibles pour le ciblage ?**

Les données sont disponibles pour le ciblage après 48 heures. Par ailleurs, n&#39;interprétez pas le message électronique « réussi » comme instruction indiquant que les données sont disponibles. This only means that [!DNL Audience Manager] has picked up the file and completed the first step of processing.

<br> 

**À quelle fréquence dois-je envoyer des fichiers et doivent-ils être des fichiers complets ou incrémentiels ?**

Il est recommandé d&#39;envoyer un fichier incrémentiel une fois par jour pour les nouveaux visiteurs et pour les visiteurs dont les données ont changé. Many [!DNL Audience Manager] customers send a full file once per month. Toutefois, ces intervalles et incréments sont flexibles. Vous devez envoyer des données par incréments et, en cas de logique, pour vous.

<br> 

**Pendant combien de temps Audience Manager conserve-t-il mes fichiers sur le serveur ?**

Les fichiers FTP sont supprimés après leur traitement. [!DNL S3] sont supprimées après 30 jours. Les fichiers qui ne peuvent pas être traités en raison d&#39;un format, d&#39;une syntaxe ou d&#39;autres erreurs sont supprimés. See also, [Privacy and Data Retention FAQ](../faq/faq-privacy.md).

<br> 

**Quelle est la différence entre les fichiers incrémentiels et complets ?**

* **Complet :** Un fichier complet écrase tous les profils de visiteurs existants et les remplace par les données contenues dans votre fichier. Full files are identified by the `.overwrite` tag appended to the file name. You can use a `.overwrite` file to reset visitor traits or remove stale, obsolete traits.

   >[!NOTE]
   >
   >The [!DNL .overwrite] files only overwrite [!DNL Audience Manager] profile data associated to this data provider. In other words, all [!DNL Adobe Analytics] data associated to the visitor remains intact after a [!DNL .overwrite] file has been processed.

* **Incrémentiel :** Un fichier incrémentiel ajoute de nouvelles données à vos profils de visiteurs existants. Incremental files are identified by the `.sync` tag appended to the file name. L&#39;envoi d&#39;un fichier incrémentiel n&#39;efface ni ne remplace les profils existants.

Les cas d&#39;utilisation suivants montrent comment ces types de fichier affectent les profils des visiteurs stockés.

<table id="table_CE43B49508384ABF8B25FA8A8FFE5362"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cas d’utilisation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Incrémentiel et Complet</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_E89301D815174D45B9B238F2CDE6CCC6"> 
      <li id="li_FA841FEEC0534AD59D1AB61DD5B9DEC4">Day 1 <code> .sync</code> file contents: <code> visitor123 = a,b,c</code> </li> 
      <li id="li_0E1A57B04D26481C8C41EBA63ACBEFE0">Day 2 <code> .overwrite</code> file contents: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_497A5604AD9A49A2ADE548C7CE158F0E"> Day 3 visitor profile ID 123 contains <code> c,d,e </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Incrémentiel uniquement</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8271C9796BD040E4B8DC64DCE4FE2AD3"> 
      <li id="li_347959BDE83549F794E6661C95097891">Day 1 <code> .sync</code> file contents: <code> visitor123 = a,b,c </code> </li> 
      <li id="li_B25D96526DE94171A3A5DC8DB7A19415">Day 2 <code> .sync</code> file contents: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_6E17809D49C74F4991B0B445469055E6">Day 3 visitor profile ID 123 contains <code> a,b,c,d,e</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Pour plus d&#39;informations sur les types de fichiers incrémentiels et complets, voir :

* [Exigences de taille et de fichier Amazon S 3 pour les données entrantes…](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Exigences en matière de nom FTP et de taille de fichier pour les fichiers de données entrants…](../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

<br> 

**Que se passe-t-il si j&#39;envoie un fichier avec des identifiants pour les visiteurs qui n&#39;ont jamais effectué la synchronisation des identifiants sur la page ?**

During processing, [!DNL Audience Manager] simply skips that record and moves on to the next. Si un DPID (ID de fournisseur de données) est configuré comme un DPID sur plusieurs périphériques, les données qui sont assimilées avant l&#39;enregistrement d&#39;une synchronisation des identifiants sont enregistrées et peuvent être utilisées peu après la synchronisation des identifiants.

<br> 

**Quel est l&#39;horodatage, à quoi sert-il et pouvez-vous fournir un exemple ?**

Les horodatages sont utilisés pour la journalisation et l&#39;enregistrement. Ils sont requis par la syntaxe utilisée pour un fichier entrant correctement formaté - nom. Voir :

* [Exigences en matière de nom Amazon S3 pour les fichiers de données entrants](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Exigences en matière de nom FTP et de taille de fichier pour les fichiers de données entrants…](../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

<br> 

**Qu&#39;est-ce qu&#39;un identifiant de fournisseur de données et comment puis-je l&#39;obtenir ?**

Votre consultant Adobe attribuera un DPID à trois ou quatre chiffres à votre source de données particulière. Cet ID est unique et ne change pas.

<br> 

**Quelle est la taille des fichiers de données quotidiens ?**

See [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**Audience Manager prend-il en charge la compression des fichiers ?**

Oui, voir:

* [Compression de fichier pour les fichiers de transfert de données entrants](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [Exigences en matière de nom Amazon S3 pour les fichiers de données entrants](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Exigences en matière de nom FTP pour les fichiers de données entrants](../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

<br> 

**La clé principale de ma base de données de source de données est une adresse électronique. Is that considered personally identifiable information?**

Oui. [!DNL Audience Manager] ne stocke pas les adresses électroniques dans notre base de données. Les visiteurs doivent se voir attribuer un ID aléatoire ou une version à hachage unique de l&#39;adresse électronique avant de lancer l&#39;ID.

<br> 

**Le contenu du fichier de données est-il sensible à la casse ? How about the ID sync?**

Un fichier de données comporte deux composants de base : Un utilisateur unique - id (UUID) et des données de profil, généralement sous la forme de paires ou de codes clé/valeur. L&#39;UUID est sensible à la casse. En règle générale, les données de profil ou de clé ne sont pas sensibles à la casse.

<br> 

**Dois-je utiliser FTP ou[!DNL Amazon S3]transférer des fichiers ?**

As best practice, we recommend [!DNL Amazon S3] because the process is simpler. [!DNL Audience Manager] transfère les fichiers FTP à [!DNL S3] quel point, le processus est donc plus rationnel si vous déposez les fichiers vous [!DNL Amazon S3] -même. En outre, les clients qui téléchargent simultanément vers FTP partagent la bande passante du FTP. Ils doivent donc s&#39;attendre à une vitesse de transfert plus lente. [!DNL Amazon S3] est également répliquée et distribuée, elle est donc généralement plus sûre et plus fiable qu&#39;un serveur FTP. For more information, see [About Amazon S3](../reference/amazon-s3.md).

<br> 

**Comment Audience Manager traite-t-il les fichiers entrants ?**

[!DNL Audience Manager] utilise [!DNL Amazon Simple Queue Service (SQS)] les données entrantes - traitement. Voici comment cela fonctionne :

1. [!DNL Audience Manager] les clients téléchargent leurs données entrantes dans un [!DNL Amazon S3] compartiment.

2. The data enters the [!DNL Amazon SQS] queue, waiting to be processed by [!DNL Audience Manager].

3. [!DNL Audience Manager] lit jusqu&#39;à 119 000 entrées à partir de [!DNL Amazon SQS] la file d&#39;attente et les scinde jusqu&#39;à 3 lots. Les fichiers de chaque lot sont traités simultanément.

<br> 

**Je dois télécharger plusieurs fichiers simultanément. Will the files be processed simultaneously?**

Cela dépend. [!DNL Audience Manager] lit jusqu&#39;à 119 000 entrées à partir de [!DNL Amazon SQS] la file d&#39;attente et les scinde jusqu&#39;à 3 lots. Vos fichiers seront traités simultanément uniquement s&#39;ils se terminent dans le même lot. However, due to the high amount of data ingested by [!DNL Audience Manager] on a daily basis, we cannot guarantee any file processing order.

>[!MORE_ LIKE_ THIS]
>
>* [Processus de transfert des données par lots décrit](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process)

