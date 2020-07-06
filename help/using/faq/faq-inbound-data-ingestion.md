---
description: Questions fréquentes sur l’introduction de données hors ligne dans Audience Manager.
keywords: ftp or s3;s3 or ftp
seo-description: Questions fréquentes sur l’introduction de données hors ligne dans Audience Manager.
seo-title: FAQ sur l’ingestion de données client entrantes
solution: Audience Manager
title: FAQ sur l’ingestion de données client entrantes
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
feature: Onboarding Offline Data
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# FAQ sur l’ingestion de données client entrantes {#inbound-customer-data-ingestion-faq}

Questions fréquentes sur l’introduction de données hors ligne dans Audience Manager.

 

**Pouvez-vous résumer le processus d’intégration ?**

Le processus d’intégration comprend deux étapes décrites dans la [présentation de l’envoi de données par lots à Audience Manager](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) :

* Étape 1 : synchroniser les identifiants des utilisateurs.
* Étape 2 : créer et transférer votre fichier de données entrant en respectant les exigences de format de fichier.

 

**Pouvez-vous résumer le processus de déploiement ?**

Nous recommandons de procéder comme suit :

* Contactez votre fournisseur de données pour formater le fichier de données entrant quotidien en fonction des spécifications d’Adobe. Consultez la documentation suivante pour connaître les exigences en matière de dénomination et de syntaxe des fichiers :
   * [Exigences en matière de nom et de contenu pour les fichiers de synchronisation d’identifiants](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)
   * [Contenu du fichier de données entrant : syntaxe, caractères non valides, variables et exemples](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)
   * [Exigences en matière de nom et de taille de fichier Amazon S3 pour les fichiers de données entrants](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* Contactez votre conseiller [!DNL Adobe] afin de transférer un fichier de données de test vers [!DNL Adobe] pour la vérification du format.
* Contactez votre conseiller [!DNL Adobe] pour produire une taxonomie adaptée à l’interprétation du contenu du fichier de données.
* Dans l’environnement d’évaluation/de développement, vérifiez que la synchronisation des identifiants est configurée de manière à récupérer correctement l’identifiant visiteur du fournisseur de données et à le transférer aux serveurs [!DNL Audience Manager] en temps réel.
* Déployez la synchronisation de DIL/des identifiants en production. La synchronisation des identifiants sera déjà configurée en tant que module dans le code DIL par votre conseiller Adobe.
* Transférez les fichiers de données de production vers [!DNL Audience Manager]. Étant donné les dépendances des mappages de synchronisation des identifiants, il peut être logique de commencer à transférer les données jusqu’à une semaine après le déploiement du code de production, bien que vous puissiez commencer à transférer les fichiers de données dès que le code entre en production.

 

**Quel mode FTP dois-je utiliser pour transférer des fichiers compressés ou chiffrés ?**

Voir [Compression de fichiers pour les fichiers de transfert de données entrants](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

>[!WARNING]
>
>Nous supprimons progressivement la prise en charge des configurations FTP. Même si l’ingestion de fichiers de données entrants est toujours prise en charge dans les intégrations FTP existantes, nous vous recommandons vivement d’utiliser Amazon S3 afin d’intégrer des données hors ligne pour les nouvelles intégrations. Pour plus d’informations, consultez [Exigences en matière de nom et de taille de fichier Amazon S3 pour les fichiers de données entrants](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md).

 

**Puis-je charger un fichier de données entrant (fichier [!DNL .sync] ou [!DNL .overwrite]) avant de déployer le code [!DNL Audience Manager] en production ?**

Oui. As long as you use a [!UICONTROL cross-device data source] to store the CRM data that you upload, Audience Manager always stores the data. In fact, following the [!UICONTROL Profile Merge Rules] enhancements that Audience Manager launched in October 2019 that allow for offline-only use cases, you can upload and action on data without deploying Audience Manager code into production at all. Voir :

* [Présentation des améliorations apportées aux stratégies de fusion de profils](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/overview-of-profile-merge-rule-enhancements.html)
* [!UICONTROL People-based Destinations] - [Personnalisation basée sur les données hors ligne uniquement](https://docs.adobe.com/content/help/fr-FR/audience-manager/user-guide/features/destinations/people-based/implementation-guide/people-based-destinations-workflow-offline.html)

<br> 

<!---
* If the data provider is configured to use [Profile Link](../features/profile-merge-rules/merge-rules-overview.md) for cross-device targeting, the data available for targeting shortly after an ID sync identifies to the matching [!DNL Audience Manager] visitor ID.

* If the data provider is not configured to use the [!UICONTROL Profile Link] feature, [!DNL Audience Manager] processes only the data for visitor IDs in the inbound data file that have been previously synced/matched back to an [!DNL Audience Manager] visitor ID.

Consider the following use cases in which the data provider is not configured to use [!UICONTROL Profile Merge]:

<table id="table_1A367ED6D016428FB21B3F3BC261BA98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Case 1</b> </p> </td> 
   <td colname="col2"> <p>On Monday, a visitor identified in the CRM database as visitor ABC logs in, which initiates a client-side ID sync. <span class="keyword"> Audience Manager</span> stores the mapping of visitor ABC to <span class="keyword"> Audience Manager</span> visitor 123. </p> <p>On Tuesday, the CRM database transfers a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager </span>server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender"="male","luxury_shopper"="yes"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">Recognizes visitor ABC from the stored ID sync mapping. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Associates the traits <code> male</code> and <code> luxury_shopper</code> with the visitor 123 profile. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 2</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the CRM database pushes a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager</span> does not have a record of this visitor (or an associated visitor ID) so this record is not processed. </p> <p>On Tuesday, visitor DEF logs in. This action initiates the first client-side ID sync for that visitor. This action maps visitor DEF to <span class="keyword"> Audience Manager</span> ID 456. However, this visitor does not have CRM data associated with their profile. As a result, <span class="keyword"> Audience Manager</span> does not go back and reprocess old files. </p> <p>On Wednesday, the CRM database pushes another data file to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes","dma"="paris"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">Recognizes visitor DEF from the stored ID sync mapping. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Associates the traits <code> female</code>, <code> paris</code>, and <code> wine_enthusiast</code> with the visitor 456 profile. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 3</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the <span class="keyword"> Audience Manager</span> server receives two files with the following records: </p> <p> <code> .sync</code> file containing: </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> <code> .overwrite</code> file containing: </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI "gender"="male" "wine_enthusiast"="no"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender"="female" "wine_enthusiast"="yes"</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> holds a mapped record of visitor JKL to ID 789, from a previous ID sync. </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">Recognizes visitor JKL from the stored ID sync mapping. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Associates the traits <code> female</code> and <code> wine_enthusiast</code> with visitor ID 789's profile. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">Ignores the trait association for visitor GHI, since its ID was only synced in the current batch. To associate traits with visitor GHI, you need to include them in future <code> .overwrite</code> files. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

-->

**À quelle heure dois-je transférer mon fichier ?**

[!DNL Audience Manager] recherche et traite les fichiers plusieurs fois par jour. Chargez vos données dès que vous êtes prêt.

 

**Quel est le délai nécessaire pour que les données d’un fichier chargé soient disponibles pour le ciblage ?**

Les données sont disponibles pour le ciblage après 48 heures. En outre, n’interprétez pas le message électronique « chargement réussi » comme une indication de disponibilité des données. Cela signifie uniquement qu’[!DNL Audience Manager] a récupéré le fichier et que la première étape du traitement a été terminée.

 

**À quelle fréquence dois-je envoyer les fichiers et ceux-ci doivent-ils être complets ou incrémentiels ?**

Il est recommandé d’envoyer un fichier incrémentiel par jour pour les nouveaux visiteurs et pour les visiteurs dont les données ont changé. De nombreux clients d’[!DNL Audience Manager] envoient un fichier complet par mois. Cependant, ces intervalles et incréments de fichier sont flexibles. Vous devez envoyer des données par incréments et à des moments qui vous conviennent.

 

**Pendant combien de temps Audience Manager conserve-t-il mes fichiers sur le serveur ?**

Les fichiers FTP sont supprimés après leur traitement. Les fichiers [!DNL S3] sont supprimés après 30 jours. Les fichiers qui ne peuvent pas être traités en raison d’erreurs de format, de syntaxe ou autres sont supprimés. Voir aussi [FAQ sur la rétention des données et la confidentialité](../faq/faq-privacy.md).

 

**Quelle est la différence entre les fichiers complets et incrémentiels ?**

* **Complet :** un fichier complet remplace tous les profils du visiteur existants et les remplace par les données contenues dans votre fichier. Les fichiers complets sont identifiés par la balise `.overwrite` annexée au nom du fichier. Vous pouvez utiliser un fichier `.overwrite` pour réinitialiser les caractéristiques du visiteur ou supprimer les caractéristiques caduques et obsolètes.

   >[!NOTE]
   >
   >Les fichiers [!DNL .overwrite] remplacent uniquement les données de profil [!DNL Audience Manager] associées à ce fournisseur de données. En d’autres termes, toutes les données [!DNL Audience Manager] associées au visiteur restent intactes après le traitement d’un fichier [!DNL .overwrite].

* **Incrémentiel :** un fichier incrémentiel ajoute de nouvelles données aux profils du visiteur existants. Les fichiers incrémentiels sont identifiés par la balise `.sync` annexée au nom du fichier. L’envoi dans un fichier incrémentiel n’efface ni ne remplace les profils existants.

Les cas d’utilisation suivants montrent comment ces types de fichiers affectent les profils du visiteur stockés.

| Cas d’utilisation | Description |
|---|---|
| Incrémentiel et complet | <ul><li>Contenu du fichier `.sync` du jour 1 : `visitor123 = a,b,c`</li><li>Contenu du fichier `.overwrite` du jour 2 : `visitor123 = c,d,e`</li><li>Contenu de l’identifiant 123 du profil du visiteur du jour 3 : `c,d,e`</li></ul> |
| Incrémentiel uniquement | <ul><li>Contenu du fichier `.sync` du jour 1 : `visitor123 = a,b,c`</li><li>Contenu du fichier `.sync` du jour 2 : `visitor123 = c,d,e`</li><li>Contenu de l’identifiant 123 du profil du visiteur du jour 3 : `a,b,c,d,e`</li></ul> |

Pour plus d’informations sur les types de fichiers complets et incrémentiels, voir :

* [Exigences en matière de nom et de taille de fichier Amazon S3 pour les données entrantes…](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**Que se passe-t-il si j’envoie un fichier avec des identifiants pour les visiteurs qui n’ont jamais effectué de synchronisation des identifiants sur la page ?**

Pendant le traitement, [!DNL Audience Manager] ignore cet enregistrement et passe à l’enregistrement suivant. Si un [DPID (identifiant de fournisseur de données)](../reference/ids-in-aam.md) est configuré en tant que DPID multi-appareils, les données qui sont ingérées avant l’enregistrement d’une synchronisation des identifiants sont disponibles et peuvent être utilisées peu après la synchronisation des identifiants.

 

**Qu’est-ce que l’horodatage, à quoi sert-il et pouvez-vous donner un exemple ?**

Les horodatages sont utilisés pour la journalisation et la conservation d’enregistrements. Ils sont requis par la syntaxe utilisée pour un nom de fichier entrant correctement formaté. Voir :

* [Exigences en matière de nom Amazon S3 pour les fichiers de données entrants](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**Qu&#39;est-ce qu&#39;une[!DNL Data Provider ID (DPID)]et comment puis-je l&#39;obtenir ?**

Votre conseiller Adobe attribuera un [DPID (identifiant de fournisseur de données)](../reference/ids-in-aam.md) à trois ou quatre chiffres à votre source de données particulière. Cet identifiant est unique et ne change pas.

 

**Jusqu’à quel point les fichiers de données quotidiens peuvent-ils être volumineux ?**

Voir [Compression de fichiers pour les fichiers de transfert de données entrants](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

 

**Audience Manager prend-il en charge la compression de fichiers ?**

Oui, voir :

* [Compression de fichiers pour les fichiers de transfert de données entrants](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).
* [Exigences en matière de nom Amazon S3 pour les fichiers de données entrants](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**La clé primaire de ma base de données de source de données est une adresse électronique. Est-elle considérée comme une information d’identification personnelle ?**

Oui. [!DNL Audience Manager] ne stocke pas d’adresses électroniques dans sa base de données. Les Visiteurs doivent se voir attribuer un identifiant généré de manière aléatoire ou une version avec hachage unique de l’adresse électronique avant d’initier les synchronisations d’identifiants.

 

**Le contenu du fichier de données est-il sensible à la casse ? Qu’en est-il de la synchronisation des identifiants ?**

Un fichier de données comporte deux composants de base : un [!UICONTROL User ID] (voir [!UICONTROL User ID] dans [Définition des variables de fichier](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined)) et des données de profil, généralement sous la forme de paires clé-valeur ou de codes. [!UICONTROL User ID] est sensible à la casse. En règle générale, les données de profil ou clé-valeur ne sont pas sensibles à la casse.

 

**Dois-je utiliser FTP ou [!DNL Amazon S3] pour transférer des fichiers ?**

Nous recommandons [!DNL Amazon S3], car le processus est plus simple. [!DNL Audience Manager] transfère les fichiers FTP vers [!DNL S3] dans tous les cas, le processus est donc plus simple si vous déposez vous-même les fichiers dans [!DNL Amazon S3]. En outre, les clients qui effectuent un chargement simultanément sur FTP partagent la bande passante du FTP. Ils doivent donc s’attendre à des vitesses de transfert plus lentes. [!DNL Amazon S3] est également répliqué et distribué. Il est donc généralement plus sûr et plus fiable qu’un serveur FTP. Pour plus d’informations, consultez [À propos d’Amazon S3](../reference/amazon-s3.md).

>[!WARNING]
>
>Nous supprimons progressivement la prise en charge des configurations FTP. While inbound data file ingestion is still supported in existing FTP integrations, we strongly recommend using [!DNL Amazon S3] to onboard offline data for new integrations. Pour plus d’informations, consultez [Exigences en matière de nom et de taille de fichier Amazon S3 pour les fichiers de données entrants](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md).

 

**Comment Audience Manager traite-t-il les fichiers entrants ?**

[!DNL Audience Manager] utilise [!DNL Amazon Simple Queue Service (SQS)] pour le traitement des données entrantes. Cela fonctionne comme suit :

1. Les clients d’[!DNL Audience Manager] chargent leurs données entrantes dans un compartiment [!DNL Amazon S3].
1. Les données entrent dans la file d’attente [!DNL Amazon SQS] pour être traitées par [!DNL Audience Manager].
1. [!DNL Audience Manager] lit jusqu’à 119 000 entrées de la file d’attente [!DNL Amazon SQS] et les sépare en 3 lots maximum. Les fichiers de chaque lot sont traités simultanément.

 

**Je dois charger plusieurs fichiers en même temps. Les fichiers seront-ils traités simultanément ?**

Cela dépend. [!DNL Audience Manager] lit jusqu’à 119 000 entrées de la file d’attente [!DNL Amazon SQS] et les sépare en 3 lots maximum. Vos fichiers ne seront traités simultanément que s’ils se retrouvent dans le même lot. Cependant, en raison de la quantité importante de données quotidiennement ingérées par [!DNL Audience Manager], nous ne pouvons garantir aucun ordre de traitement de fichiers.

>[!MORELIKETHIS]
>
>* [Description du processus de transfert de données par lots](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

