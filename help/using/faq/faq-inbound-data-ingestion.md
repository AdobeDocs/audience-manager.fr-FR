---
description: Questions fréquentes sur l’importation de données hors ligne dans Audience Manager.
keywords: ftp ou s3;s3 ou ftp
seo-description: Questions fréquentes sur l’importation de données hors ligne dans Audience Manager.
seo-title: FAQ sur l'introduction des données client entrantes
solution: Audience Manager
title: FAQ sur l'introduction des données client entrantes
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
translation-type: tm+mt
source-git-commit: 28d1292140a56cf1627a8921876d9483221876ca

---


# FAQ sur l'introduction des données client entrantes{#inbound-customer-data-ingestion-faq}

Questions fréquentes sur l’importation de données hors ligne dans Audience Manager.

<br> 

<!-- 

c_inbound_crm_data_ingestion.xml

 -->

**Pouvez-vous résumer le processus d'intégration ?**

Le processus d’intégration se compose de deux composants principaux décrits dans la description [du processus de transfert des données par](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)lot. Il s’agit notamment :

* Synchronisation des identifiants
* Fichier de données entrant ( [!DNL .sync] fichier ou [!DNL .overwrite] fichier)

<!-- 

Removed the Data Translation File bullet from the list above.

 -->

Vous trouverez ci-dessous une liste de questions et réponses utiles après avoir examiné la documentation.

>[!NOTE]
>
>Les exemples de cette section sont simplifiés ou raccourcis à des fins de concision et de démonstration. Consultez la documentation relative à l’importation de données entrantes pour obtenir des spécifications détaillées sur les formats de fichier et la syntaxe.

<br> 

**Pouvez-vous résumer le processus de déploiement ?**

Nous vous recommandons ce qui suit :

* Consultez votre fournisseur de données pour formater le fichier de données entrant quotidiennement en fonction des [!DNL Adobe] spécifications.
* Transférez un fichier de données de test vers [!DNL Adobe] pour vérifier le format.
* Travaillez avec votre [!DNL Adobe] consultant pour produire une taxonomie adaptée à l'interprétation du contenu du fichier de données.
* Dans l’environnement de test/développement, vérifiez que la synchronisation des identifiants est configurée pour récupérer correctement l’identifiant visiteur du fournisseur de données et le transférer aux [!DNL Audience Manager] serveurs en temps réel.
* Déployez la synchronisation DIL/ID en production. La synchronisation des identifiants sera déjà configurée en tant que module dans le code DIL par votre conseiller Adobe.
* Transférez les fichiers de données de production vers [!DNL Audience Manager]. Compte tenu des dépendances des mappages de synchronisation des identifiants, il peut être logique de commencer à transférer les données jusqu’à une semaine après le déploiement du code de production, bien que vous puissiez commencer à transférer les fichiers de données dès que le code entre en production.

<br> 

**Quel mode FTP dois-je utiliser pour transférer des fichiers compressés ou chiffrés ?**

Voir Compression de [fichiers pour les fichiers](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)de transfert de données entrants.

<br> 

**Puis-je charger un fichier de données entrant (fichier[!DNL .sync]ou[!DNL .overwrite]) avant de déployer le code[!DNL Audience Manager]en production ?**

* Si le fournisseur de données est configuré pour utiliser le lien [de](../features/profile-merge-rules/merge-rules-overview.md) profil pour le ciblage sur plusieurs périphériques, les données disponibles pour le ciblage peu après qu’une synchronisation d’ID s’identifie à l’identifiant [!DNL Audience Manager] visiteur correspondant.

* Si le fournisseur de données n’est pas configuré pour utiliser la [!UICONTROL Profile Link] fonctionnalité, [!DNL Audience Manager] traite uniquement les données des identifiants de visiteur dans le fichier de données entrants qui ont été synchronisées/mises en correspondance avec un ID de [!DNL Audience Manager] visiteur.

Tenez compte des cas d’utilisation suivants où le fournisseur de données n’est pas configuré pour utiliser [!UICONTROL Profile Merge]:

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
   <td colname="col2"> <p>Lundi, un visiteur identifié dans la base de données CRM comme étant le visiteur auquel ABC se connecte, ce qui initie une synchronisation d’ID côté client. <span class="keyword"> Audience Manager</span> stocke le mappage du visiteur ABC au <span class="keyword"> visiteur Audience Manager</span> 123. </p> <p>Le mardi, la base de données CRM transfère un fichier de données (<span class="filepath"> .sync</span>) vers le <span class="keyword"> serveur Audience Manager </span>avec l’enregistrement suivant : </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender"="male","luxueux_acheteur"="oui"</code> </li> 
     </ul> </p> <p>Dans ce cas, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">Reconnaît le visiteur ABC à partir du mappage de synchronisation des identifiants stockés. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Associe les caractéristiques <code> masculine</code> et <code> luxueuse_shopper</code> au profil 123 du visiteur. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Cas 2</b> </p> </td> 
   <td colname="col2"> <p>Lundi, la base de données CRM envoie un fichier de données (<span class="filepath"> .sync</span>) au serveur <span class="keyword"> Audience Manager</span> avec l’enregistrement suivant : </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="femelle","wine_enthousiassiast"="yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager</span> n’a pas d’enregistrement de ce visiteur (ou d’un identifiant visiteur associé). Cet enregistrement n’est donc pas traité. </p> <p>Le mardi, le service d’identification des visiteurs se connecte. Cette action initie la première synchronisation d’ID côté client pour ce visiteur. Cette action mappe le DEF du visiteur à l’ID <span class="keyword"> Audience Manager</span> 456. Toutefois, ce visiteur ne dispose pas de données CRM associées à son profil. Par conséquent, <span class="keyword"> Audience Manager</span> ne revient pas en arrière et ne retraite pas les anciens fichiers. </p> <p>Mercredi, la base de données CRM envoie un autre fichier de données au serveur <span class="keyword"> Audience Manager</span> avec l’enregistrement suivant : </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="femelle","wine_enthousiaste"="yes","dma"="paris"</code> </li> 
     </ul> </p> <p>Dans ce cas, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">Reconnaît le DEF du visiteur à partir du mappage de synchronisation des identifiants stockés. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Associe les caractéristiques <code> femelle</code>, <code> paris</code>et <code> wine_enthousiaste</code> au profil du visiteur 456. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Cas 3</b> </p> </td> 
   <td colname="col2"> <p>Le lundi, le serveur <span class="keyword"> Audience Manager</span> reçoit deux fichiers avec les enregistrements suivants : </p> <p> <code> Fichier .sync</code> contenant : </p> <p> 
     <ul class="simplelist"> 
      <li><code> 123456789 GHI</code> </li> 
     </ul> </p> <p> <code> fichier .overwrite</code> contenant : </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI "gender"="masculin" "wine_enthousiassiast"="non"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender"="femelle" "wine_enthousiassiast"="yes"</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> conserve un enregistrement mappé du visiteur JKL sur l’ID 789, à partir d’une synchronisation d’ID précédente. </p> <p>Dans ce cas, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">Reconnaît le JKL du visiteur à partir du mappage de synchronisation des identifiants stockés. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Associe les caractéristiques <code> femelle</code> et <code> wine_enthousiaste</code> au profil du visiteur ID 789. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">Ignore l’association de caractéristiques pour le GHI du visiteur, car son ID n’a été synchronisé que dans le lot actuel. Pour associer des caractéristiques au GHI du visiteur, vous devez les inclure dans les futurs fichiers <code> .overwrite</code> . </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**À quelle heure dois-je transférer mon dossier ?**

[!DNL Audience Manager] recherche et traite les fichiers plusieurs fois par jour. Téléchargez vos données dès que vous êtes prêt.

<br> 

**Combien de temps faut-il avant que les données d’un fichier téléchargé ne soient disponibles pour le ciblage ?**

Les données sont disponibles pour le ciblage après 48 heures. En outre, n’interprétez pas le message "Téléchargement réussi" comme une déclaration indiquant que les données sont disponibles. Cela signifie uniquement que [!DNL Audience Manager] le fichier a été récupéré et que la première étape du traitement a été terminée.

<br> 

**À quelle fréquence dois-je envoyer des fichiers et ceux-ci doivent-ils être complets ou incrémentiels ?**

Il est recommandé d’envoyer un fichier incrémentiel une fois par jour pour les nouveaux visiteurs et les visiteurs dont les données ont changé. De nombreux [!DNL Audience Manager] clients envoient un fichier complet une fois par mois. Toutefois, ces intervalles et incréments de fichier sont flexibles. Vous devez envoyer des données par incréments et parfois cela vous semble logique.

<br> 

**Combien de temps Audience Manager conserve-t-il mes fichiers sur le serveur ?**

Les fichiers FTP sont supprimés après leur traitement. [!DNL S3] sont supprimés après 30 jours. Les fichiers qui ne peuvent pas être traités en raison d’erreurs de format, de syntaxe ou autres sont supprimés. Voir aussi FAQ [sur la](../faq/faq-privacy.md)confidentialité et la rétention des données.

<br> 

**Quelle est la différence entre les fichiers complets et incrémentiels ?**

* **** Complet : Un fichier complet écrase tous vos profils de visiteurs existants et les remplace par les données contenues dans votre fichier. Les fichiers complets sont identifiés par la `.overwrite` balise annexée au nom du fichier. Vous pouvez utiliser un `.overwrite` fichier pour réinitialiser les caractéristiques des visiteurs ou supprimer les caractéristiques obsolètes et obsolètes.

   >[!NOTE]
   >
   >Les [!DNL .overwrite] fichiers remplacent uniquement les données [!DNL Audience Manager] de profil associées à ce fournisseur de données. En d’autres termes, toutes les [!DNL Adobe Analytics] données associées au visiteur restent intactes après le traitement d’un [!DNL .overwrite] fichier.

* **** Incrémentiel : Un fichier incrémentiel ajoute de nouvelles données à vos profils de visiteurs existants. Les fichiers incrémentiels sont identifiés par la `.sync` balise annexée au nom du fichier. L’envoi dans un fichier incrémentiel n’efface ni ne remplace les profils existants.

Les cas d’utilisation suivants montrent comment ces types de fichiers affectent les profils de visiteurs stockés.

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
      <li id="li_FA841FEEC0534AD59D1AB61DD5B9DEC4">Contenu du fichier .sync <code></code> Jour 1 : <code> visitor123 = a,b,c</code> </li> 
      <li id="li_0E1A57B04D26481C8C41EBA63ACBEFE0">Jour 2 <code> .écraser</code> le contenu du fichier : <code> visitor123 = c,d,e</code> </li> 
      <li id="li_497A5604AD9A49A2ADE548C7CE158F0E"> L’identifiant de profil du visiteur 123 du jour 3 contient <code> c,d,e </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Incrémentiel uniquement</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8271C9796BD040E4B8DC64DCE4FE2AD3"> 
      <li id="li_347959BDE83549F794E6661C95097891">Contenu du fichier .sync <code></code> Jour 1 : <code> visitor123 = a,b,c </code> </li> 
      <li id="li_B25D96526DE94171A3A5DC8DB7A19415">Contenu du fichier .sync <code></code> Jour 2 : <code> visitor123 = c,d,e</code> </li> 
      <li id="li_6E17809D49C74F4991B0B445469055E6">L’identifiant de profil du visiteur 123 du jour 3 contient <code> a, b, c, d, e</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Pour plus d’informations sur les types de fichiers complets et incrémentiels, voir :

* [Exigences en matière de nom et de taille de fichier Amazon S3 pour les données entrantes...](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

<br> 

**Que se passe-t-il si j’envoie un fichier avec des identifiants pour les visiteurs qui n’ont jamais effectué la synchronisation des identifiants de page ?**

Lors du traitement, [!DNL Audience Manager] il se contente d’ignorer cet enregistrement et de passer au suivant. Si un DPID (ID du fournisseur de données) est configuré en tant que DPID sur plusieurs périphériques, les données qui sont assimilées avant l’enregistrement d’une synchronisation des identifiants sont disponibles et peuvent être utilisées peu après la synchronisation des identifiants.

<br> 

**Quel est le cachet temporel, à quoi sert-il, et pouvez-vous donner un exemple?**

Les horodatages sont utilisés pour la consignation et la tenue de registres. Elles sont requises par la syntaxe utilisée pour un nom de fichier entrant correctement formaté. Voir :

* [Exigences en matière de nom Amazon S3 pour les fichiers de données entrants](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**Qu’est-ce qu’un ID de fournisseur de données (DPID) et comment l’obtenir ?**

Votre conseiller Adobe attribuera un DPID à trois ou quatre chiffres à votre source de données particulière. Cet identifiant est unique et ne change pas.

<br> 

**Quelle est la taille des fichiers de données quotidiens ?**

Voir Compression de [fichiers pour les fichiers](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)de transfert de données entrants.

<br> 

**Audience Manager prend-il en charge la compression de fichiers ?**

Oui, voir:

* [Compression de fichiers pour les fichiers de transfert de données entrants](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [Exigences en matière de nom Amazon S3 pour les fichiers de données entrants](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**La clé principale de ma base de données de source de données est une adresse électronique. Est-ce considéré comme des informations personnelles identifiables ?**

Oui. [!DNL Audience Manager] ne stocke pas les adresses électroniques dans notre base de données. Les visiteurs doivent se voir attribuer un ID aléatoire ou une version avec un hachage à sens unique de l’adresse électronique avant de commencer la synchronisation des identifiants.

<br> 

**Le contenu du fichier de données est-il sensible à la casse ? Et la synchronisation des identifiants ?**

Il existe deux composants de base d’un fichier de données : ID utilisateur unique (UUID) et données de profil, généralement sous la forme de paires clé-valeur ou de codes. L’UUID est sensible à la casse. En règle générale, les données de profil ou de valeur de clé ne sont pas sensibles à la casse.

<br> 

**Dois-je utiliser FTP ou[!DNL Amazon S3]transférer des fichiers ?**

En règle générale, nous vous recommandons [!DNL Amazon S3] d’opter pour une méthode plus simple. [!DNL Audience Manager] transfère les fichiers FTP vers [!DNL S3] indépendamment, de sorte que le processus soit plus rationnel si vous déposez les fichiers [!DNL Amazon S3] vous-même. En outre, les clients qui téléchargent simultanément sur FTP partagent la bande passante du FTP, ce qui devrait les rendre plus lents. [!DNL Amazon S3] est également répliquée et distribuée. Il est donc généralement plus sûr et plus fiable qu’un serveur FTP. Pour plus d’informations, voir [A propos d’Amazon S3](../reference/amazon-s3.md).

<br> 

**Comment Audience Manager traite-t-il les fichiers entrants ?**

[!DNL Audience Manager] utilise [!DNL Amazon Simple Queue Service (SQS)] le traitement des données entrantes. Voici comment cela fonctionne :

1. [!DNL Audience Manager] les clients téléchargent leurs données entrantes dans un [!DNL Amazon S3] compartiment.

2. Les données entrent dans la [!DNL Amazon SQS] file d’attente, en attente d’être traitées par [!DNL Audience Manager].

3. [!DNL Audience Manager] lit jusqu’à 119 000 entrées de la [!DNL Amazon SQS] file d’attente et les sépare en 3 lots au maximum. Les fichiers de chaque lot sont traités simultanément.

<br> 

**Je dois télécharger plusieurs fichiers en même temps. Les fichiers seront-ils traités simultanément ?**

Ça dépend. [!DNL Audience Manager] lit jusqu’à 119 000 entrées de la [!DNL Amazon SQS] file d’attente et les sépare en 3 lots au maximum. Vos fichiers ne seront traités simultanément que s’ils se retrouvent dans le même lot. Cependant, en raison de la quantité importante de données ingérées [!DNL Audience Manager] quotidiennement, nous ne pouvons garantir aucun ordre de traitement de fichiers.

>[!MORE_LIKE_This]
>
>* [Description du processus de transfert de données par lot](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

