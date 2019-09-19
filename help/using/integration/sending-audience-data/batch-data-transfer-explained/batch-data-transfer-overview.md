---
description: Présentation destinée aux clients techniques et non techniques qui souhaitent importer des données d’autres systèmes (hors ligne) dans Audience Manager.
keywords: entrée, lot, transfert par lot, données par lot
seo-description: Présentation destinée aux clients techniques et non techniques qui souhaitent importer des données d’autres systèmes (hors ligne) dans Audience Manager. Pour ce faire, utilisez l’option de téléchargement par lot dans Audience Manager.
seo-title: ' Présentation de l’envoi de données par lots à Audience Manager'
solution: Audience Manager
title: ' Présentation de l’envoi de données par lots à Audience Manager'
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
translation-type: tm+mt
source-git-commit: 2e3adc8f0b2fe6efd9ca57f1d763ee4476d2edee

---


#  Présentation de l’envoi de données par lots à Audience Manager{#send-batch-data-to-audience-manager-overview}

Présentation destinée aux clients techniques et non techniques qui souhaitent importer des données d’autres systèmes (hors ligne) dans Audience Manager.

## Avantages

<!-- c_offline_to_online.xml -->

Vous pouvez rendre les données d’autres systèmes disponibles dans Audience Manager. Notre système peut vous aider à déverrouiller la valeur et à exploiter les données utilisateur que vous avez collectées précédemment. Cela inclut des informations sur les achats, les enquêtes sur les clients, les données d'enregistrement, les [!DNL CRM] bases de données, etc. Bien que chaque intégration présente ses propres défis, elles partagent toutes ces étapes communes. Consultez ce document pour réduire les efforts nécessaires pour mettre en ligne vos données hors ligne.

## Étape 1 : Synchronisation des ID utilisateur

Lors de la synchronisation, Audience Manager affecte des ID uniques aux clients et à leurs utilisateurs. Ces identifiants sont appelés respectivement [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) et [!UICONTROL Unique User ID] ([!UICONTROL UUID]). Audience Manager utilise le [!UICONTROL DPID] et [!UICONTROL UUID] pour identifier les utilisateurs et les qualifier pour les caractéristiques, les segments, les groupes d’audiences et les rapports. De plus, notre code de collecte de données ([!UICONTROL DIL]) recherche ces identifiants pour capturer les données des visiteurs de votre site Web. Une fois cette étape terminée, Audience Manager et votre référentiel hors ligne doivent contenir les ID correspondants pour chaque enregistrement utilisateur.

Remarques importantes concernant cette étape :

* **** Emplacement de l’ID client : Audience Manager doit savoir où votre ID client apparaît sur votre site Web (s’il est stocké dans un cookie, une variable Analytics, un code de page, etc.).
* **[!DNL PII]Exclure**: Les ID utilisateur ne doivent pas contenir d’informations d’identification personnelle ([!DNL PII]).
* **** Respect de la casse et du contenu : Lors d’une synchronisation des données en temps réel, les ID utilisateur capturés sur votre site par Audience Manager doivent correspondre aux ID transmis à partir de votre référentiel hors ligne. Si, par exemple, les enregistrements hors ligne contiennent des informations sur [!DNL User123], mais que votre site effectue le rendu de cet identifiant comme [!DNL USER123], Audience Manager les voit comme des visiteurs différents. Par conséquent, les informations en ligne de ce visiteur ne peuvent pas être associées aux enregistrements correspondants dans votre base de données hors ligne. Les ID doivent correspondre exactement.

See [ID Synchronization for Inbound Data Transfers](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

<!-- 

<p> <b>Step 2: Create a Translation File</b> </p> 
<p>A translation file classifies data according to uniform and logical hierarchy. It is a taxonomy that helps you organize information from general categories (e.g., geography) to more precise classifications (e.g., <i>geography > United States > New York</i>). Also, it labels data with to easy to understand names such as "gender=male" or "color=green" instead of with your internal SKUs, abbreviations, or other names. The file lets Audience Manager display this information in a readable, logical manner. You and your data partners must create and share the translation file with Audience Manager before any real-time or server-to-server data transfers can begin. You can update this file on a schedule relevant to your business needs. </p> 
<p>Important considerations about this step: </p> 
<ul id="ul_6A05AECB0BD649B1BF1B34058E9008E2"> 
 <li id="li_39817ED898F14156A77FCAC066FE0968"> <b>Create a comprehensive list:</b> The translation file must include all the possible values that can be passed in on a particular key. For example, if you have category key called "color" and it accepts the values "red," "green," and "blue," the translation file must contain <i>all</i> those elements. </li> 
 <li id="li_19CAD7683BCF45278E2991C1EDBC9903"> <b>Case and content sensitivity:</b> The key-values in the file must match the values actually passed in to Audience Manager from your website. </li> 
</ul> 
<p>See DATA TRANSLATION FILE. </p>

 -->

## Étape 2 :Format du fichier de données

Les noms de fichier et le contenu suivent des consignes strictes. Vous *devez* nommer et organiser les fichiers de données selon ces spécifications dans ce guide. Voir :

* [Exigences en matière de nom Amazon S3 pour les fichiers de données entrants](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Contenu du fichier de données entrantes : Syntaxe, variables et exemples](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Les données en ligne sont disponibles pour les efforts de marketing hors ligne

Lorsque vous mettez en ligne des données hors ligne, vous pouvez toujours utiliser ces informations pour des campagnes hors ligne. Pour ce faire, Audience Manager exporte les informations sur les caractéristiques et les segments vers un [!DNL FTP] emplacement ou [!DNL Amazon S3] un emplacement de votre choix. Contactez votre responsable Solutions Partenaires pour obtenir des informations ou de l'aide.

## Environnements

Audience Manager fournit les environnements suivants pour le dépôt de fichiers :

<table id="table_A61AA64578944B23B5A7355F2A76E882"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Environnement </th> 
   <th colname="col02" class="entry"> Service </th> 
   <th colname="col2" class="entry"> Emplacement </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <b>Production</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p> <code> ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s2s-clients</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <b>Environnement bêta</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p><code> sandbox-ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s2s-clients-sandbox-us-east-1</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Autres lectures techniques

Les ingénieurs système, les développeurs ou les équipes techniques/d’implémentation doivent examiner le processus de transfert de données par [lot décrit](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) et les autres articles de cette section. Ces articles fournissent des détails sur les protocoles de transfert, le contenu des fichiers et les exigences en matière de nom de fichier.