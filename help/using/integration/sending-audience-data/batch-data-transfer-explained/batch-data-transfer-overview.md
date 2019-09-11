---
description: Présentation des clients techniques et non techniciens qui souhaitent importer des données d'autres systèmes (hors ligne) dans Audience Manager.
keywords: inbound, batch, batch upload, batch data
seo-description: Présentation des clients techniques et non techniciens qui souhaitent importer des données d'autres systèmes (hors ligne) dans Audience Manager. Pour ce faire, utilisez l'option de téléchargement par lot dans Audience Manager.
seo-title: Envoi de données batch à l'aperçu Audience Manager
solution: Audience Manager
title: Envoi de données batch à l'aperçu Audience Manager
uuid: 472583 b 1-5057-4 add -8 e 3 c -5 e 50762 c 88 e 0
translation-type: tm+mt
source-git-commit: 2e3adc8f0b2fe6efd9ca57f1d763ee4476d2edee

---


# Envoi de données batch à l'aperçu Audience Manager{#send-batch-data-to-audience-manager-overview}

Présentation des clients techniques et non techniciens qui souhaitent importer des données d'autres systèmes (hors ligne) dans Audience Manager.

## Avantages

<!-- c_offline_to_online.xml -->

Vous pouvez rendre les données d'autres systèmes disponibles dans Audience Manager. Notre système peut vous aider à déverrouiller la valeur et à exploiter les données utilisateur que vous avez collectées précédemment. Ceci inclut les informations sur les achats, les enquêtes client, les données d'enregistrement, [!DNL CRM] les bases de données, etc. Chaque intégration présente ses propres défis, mais tous partagent ces étapes courantes. Consultez ce document pour réduire l'effort nécessaire pour importer vos données hors ligne en ligne.

## Étape 1 : Synchroniser l'utilisateur - Identifiants

Lors de la synchronisation, Audience Manager attribue des identifiants uniques aux clients et aux utilisateurs. Ces identifiants sont appelés [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) et [!UICONTROL Unique User ID] ([!UICONTROL UUID]), respectivement. Audience Manager utilise [!UICONTROL DPID] et [!UICONTROL UUID] identifie les utilisateurs et les qualifie pour les caractéristiques, les segments, les groupes d'audiences et les rapports. De plus[!UICONTROL DIL], notre code de collecte de données recherche ces identifiants pour capturer les données des visiteurs de votre site Web. Lorsque cette étape est terminée, Audience Manager et votre référentiel hors ligne doivent contenir les identifiants correspondants pour chaque enregistrement utilisateur.

Remarques importantes concernant cette étape :

* **Placement d'ID client :** Audience Manager doit savoir où figure votre ID client sur votre site Web (par exemple, il est stocké dans un cookie, une variable Analytics, dans le code de page, etc.).
* **Exclure[!DNL PII]:** Utilisateur - les identifiants ne doivent pas contenir d'informations personnelles identifiables ([!DNL PII]).
* **Respect de la casse et du contenu :** Lors d'une synchronisation de données en temps réel, l'utilisateur - les identifiants capturés depuis votre site par Audience Manager doivent correspondre aux ID transmis depuis votre référentiel hors ligne. Par exemple, si des enregistrements hors ligne contiennent des informations, [!DNL User123]mais que votre site effectue le rendu de cet identifiant, [!DNL USER123]Audience Manager le voit comme des visiteurs différents. Par conséquent, les informations en ligne de ce visiteur ne peuvent pas être associées aux enregistrements correspondants dans votre base de données hors ligne. Les ID doivent correspondre exactement.

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

## Étape 2 : Format du fichier de données

Les noms et le contenu des fichiers suivent des directives strictes. Vous *devez* nommer et organiser les fichiers de données conformément à ces spécifications dans ce guide. Voir :

* [Exigences en matière de nom Amazon S3 pour les fichiers de données entrants](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Contenu du fichier de données entrant : Syntaxe, variables et exemples](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Les données en ligne sont disponibles pour les actions marketing hors ligne

Lorsque vous importez des données hors ligne en ligne, vous pouvez toujours utiliser ces informations pour les campagnes hors ligne. Pour ce faire, Audience Manager exporte les informations de caractéristique et de segment sur un [!DNL FTP] ou [!DNL Amazon S3] plusieurs emplacements de votre choix. Contactez votre gestionnaire de solutions partenaires pour obtenir d'autres informations ou d'autres informations.

## Environnements

Audience Manager fournit les environnements suivants pour le dépôt de fichier :

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
   <td colname="col2"> <p> <code> demdex-s 2 s-clients-sandbox-us-east -1</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Lecture technique supplémentaire

Les ingénieurs informatiques, les développeurs ou les équipes techniques/d'implémentation doivent consulter [le processus de transfert des données par lots décrit](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) et les autres articles de cette section. Ces articles fournissent des détails sur les protocoles de transfert, le contenu du fichier et le fichier - exigences en matière de nom.