---
description: Présentation destinée aux clients techniques et non techniques qui souhaitent mettre en Audience Manager des données provenant d’autres systèmes (hors ligne).
keywords: inbound, batch, batch upload, batch data
seo-description: Présentation destinée aux clients techniques et non techniques qui souhaitent mettre en Audience Manager des données provenant d’autres systèmes (hors ligne). Pour ce faire, utilisez l’option de téléchargement par lot dans l’Audience Manager.
seo-title: Présentation de l’envoi de données par lots vers Audience Manager
solution: Audience Manager
title: Présentation de l’envoi de données par lots vers Audience Manager
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 6%

---


# Send Batch Data to [!DNL Audience Manager] Overview {#send-batch-data-to-audience-manager-overview}

Présentation destinée aux clients techniques et non techniques qui souhaitent importer des données d’autres systèmes (hors ligne) dans [!DNL Audience Manager].

## Avantages

Vous pouvez rendre les données d&#39;autres systèmes disponibles dans [!DNL Audience Manager]. Notre système peut vous aider à déverrouiller la valeur et à exploiter les données utilisateur que vous avez collectées précédemment. Il s’agit notamment d’informations sur les achats, les questionnaires client, les données d’enregistrement, les [!DNL CRM] bases de données, etc. Bien que chaque intégration présente ses propres défis, elles partagent toutes ces étapes communes. Consultez ce document afin de réduire les efforts nécessaires pour mettre en ligne vos données hors ligne.

## Étape 1 : Synchronisation des ID utilisateur

Au cours de la synchronisation, [!DNL Audience Manager] affecte des identifiants uniques aux clients et à leurs utilisateurs. Ces identifiants sont connus sous les noms [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) et [!UICONTROL Unique User ID] ([!UICONTROL UUID]), respectivement. [!DNL Audience Manager] utilise la méthode [!UICONTROL DPID] et [!UICONTROL UUID] pour identifier les utilisateurs et les qualifier pour [!UICONTROL traits], [!UICONTROL segments]les groupes d’audiences et pour le rapports. De plus, notre code de collecte de données ([!UICONTROL DIL]) recherche ces identifiants pour capturer les données de visiteur de votre site Web. Une fois cette étape terminée, [!DNL Audience Manager] et votre référentiel hors ligne doit contenir les ID correspondants pour chaque enregistrement d’utilisateur.

Remarques importantes concernant cette étape :

* **Emplacement de l’ID client :** [!DNL Audience Manager] doit savoir où s’affiche l’identifiant client sur votre site Web (par exemple, s’il est stocké dans un cookie, une variable Analytics, dans un code de page, etc.).
* **Exclure[!DNL PII]:** Les identifiants d’utilisateur ne doivent pas contenir d’informations d’identification personnelle ([!DNL PII]).
* **Respect de la casse et du contenu :** Lors d’une synchronisation des données en temps réel, les identifiants d’utilisateur capturés sur votre site par [!DNL Audience Manager] doivent correspondre aux identifiants transmis à partir de votre référentiel hors ligne. Par exemple, si les enregistrements hors ligne contiennent des informations sur [!DNL User123], mais que votre site effectue le rendu de cet identifiant [!DNL USER123], [!DNL Audience Manager] les voit comme des visiteurs différents. Par conséquent, les informations en ligne de ce visiteur ne peuvent pas être associées aux enregistrements correspondants dans votre base de données hors ligne. Les identifiants doivent correspondre exactement.

See [ID Synchronization for Inbound Data Transfers](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Étape 2 : Format du fichier de données

Les noms de fichier et le contenu suivent des directives strictes. Vous *devez* nommer et organiser les fichiers de données conformément à ces spécifications dans ce guide. Voir :

* [Exigences en matière de nom Amazon S3 pour les fichiers de données entrants](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Contenu du fichier de données entrantes : Syntaxe, variables et exemples](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Les données en ligne sont disponibles pour les actions marketing hors ligne

Lorsque vous mettez en ligne des données hors ligne, vous pouvez toujours utiliser ces informations pour les campagnes hors ligne. Pour ce faire, [!DNL Audience Manager] exporte les informations sur les caractéristiques et les segments vers un [!DNL FTP] emplacement ou un [!DNL Amazon S3] emplacement de votre choix. Contactez votre responsable Solutions Partenaires pour obtenir des informations ou de l&#39;aide supplémentaires.

## Environnements

[!DNL Audience Manager] fournit les environnements suivants pour la liste déroulante des fichiers :

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

Les ingénieurs système, les développeurs ou les équipes techniques/d&#39;implémentation doivent examiner le processus de transfert de données par [lot décrit](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) et les autres articles de cette section. Ces articles fournissent des détails sur les protocoles de transfert, le contenu des fichiers et les exigences en matière de nom de fichier.
