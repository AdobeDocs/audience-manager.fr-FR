---
description: Présentation destinée aux clients techniques et non techniques qui souhaitent importer dans l’Audience Manager des données d’autres systèmes (hors ligne).
keywords: entrée, lot, chargement par lots, données de lot
seo-description: An overview for technical and non-technical customers who want to bring data from other systems (offline) into Audience Manager. To do so, use the batch upload option in Audience Manager.
seo-title: Send Batch Data to Audience Manager Overview
solution: Audience Manager
title: Présentation de l’envoi de données par lots à l’Audience Manager
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
source-git-commit: f02e6bcfb7ff3560d9624c3dce7ff065a3a75748
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 4%

---

# Présentation de l’envoi de données par lots vers [!DNL Audience Manager] {#send-batch-data-to-audience-manager-overview}

Présentation pour les clients techniques et non techniques qui souhaitent importer des données d’autres systèmes (hors ligne) dans [!DNL Audience Manager].

## Avantages

Vous pouvez rendre les données d&#39;autres systèmes disponibles dans [!DNL Audience Manager]. Notre système peut vous aider à déverrouiller la valeur et à exploiter les données utilisateur que vous avez collectées précédemment. Cela inclut des informations sur les achats, les enquêtes sur les clients, les données d&#39;enregistrement, les [!DNL CRM] bases de données, etc. Bien que chaque intégration présente ses propres défis, elles partagent toutes ces étapes communes. Consultez ce matériel pour réduire les efforts nécessaires pour mettre en ligne vos données hors ligne.

## Étape 1 : synchroniser les identifiants utilisateur

Pendant la synchronisation, [!DNL Audience Manager] affecte des identifiants uniques aux clients et à leurs utilisateurs. Ces identifiants sont connus sous les noms [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) et [!UICONTROL Unique User ID] ([!UICONTROL UUID]), respectivement. [!DNL Audience Manager] utilise les [!UICONTROL DPID] et [!UICONTROL UUID] pour identifier les utilisateurs et les qualifier pour [!UICONTROL traits], [!UICONTROL segments], les groupes d’audience et pour la création de rapports. De plus, notre code de collecte de données ([!UICONTROL DIL]) recherche ces identifiants pour capturer les données de visiteur de votre site web. Une fois cette étape terminée, [!DNL Audience Manager] et votre référentiel hors ligne doivent contenir les identifiants correspondants pour chaque enregistrement d’utilisateur.

Remarques importantes concernant cette étape :

* **Emplacement de l’ID client :** [!DNL Audience Manager] doit savoir où votre ID client apparaît sur votre site web (par exemple, s’il est stocké dans un cookie, une variable Analytics, dans le code de page, etc.).
* **Exclure [!DNL PII] :** les identifiants d’utilisateur ne doivent pas contenir d’informations d’identification personnelle ([!DNL PII]).
* **Respect de la casse et du contenu :** Lors d’une synchronisation des données en temps réel, les identifiants utilisateur capturés sur votre site par [!DNL Audience Manager] doivent correspondre aux identifiants transmis à partir de votre référentiel hors ligne. Par exemple, si des enregistrements hors ligne contiennent des informations sur [!DNL User123], mais que votre site effectue le rendu de cet identifiant comme [!DNL USER123], [!DNL Audience Manager] les voit comme des visiteurs différents. Par conséquent, les informations en ligne de ce visiteur ne peuvent pas être associées aux enregistrements correspondants dans votre base de données hors ligne. Les identifiants doivent correspondre exactement.

Voir [Synchronisation des identifiants pour les transferts de données entrants](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Étape 2 : format du fichier de données

Les noms de fichier et le contenu suivent des directives strictes. Vous *devez* nommer et organiser les fichiers de données conformément à ces spécifications dans ce guide. Voir :

* [Exigences en matière de nom Amazon S3 pour les fichiers de données entrants](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Contenu du fichier de données entrant : syntaxe, variables et exemples](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Les données en ligne sont disponibles pour les efforts de marketing hors ligne

Lorsque vous mettez des données hors ligne en ligne, vous pouvez toujours utiliser ces informations pour les campagnes hors ligne. Pour ce faire, [!DNL Audience Manager] exporte les informations sur les caractéristiques et les segments vers un emplacement [!DNL FTP] ou [!DNL Amazon S3] de votre choix. Pour obtenir des informations ou une assistance supplémentaires, contactez votre responsable Partenaires en solutions .

## Environnements

[!DNL Audience Manager] fournit les environnements suivants pour le dépôt de fichiers :

| Environnement | Service | Emplacement |
|---------|----------|---------|
| Production | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients</li><li>ftp-in.demdex.com</li></ul> |
| Environnement Beta | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients-sandbox-us-east-1</li><li>sandbox-ftp-in.demdex.com</li></ul> |

{style="table-layout:auto"}

## Autres lectures techniques

Les ingénieurs système, les développeurs ou les équipes techniques/d’implémentation doivent consulter la section [Processus de transfert de données par lots décrit](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) et les autres articles de cette section. Ces articles fournissent des détails sur les protocoles de transfert, le contenu du fichier et les exigences en matière de nom de fichier.
