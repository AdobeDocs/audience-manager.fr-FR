---
description: Les composants d'action de données comprennent les flux de données client, le serveur de collecte de données, les éditeurs SFTP/S 3/HTTP, IRIS et le serveur de cache de profil.
seo-description: Les composants d'action de données comprennent les flux de données client, le serveur de collecte de données, les éditeurs SFTP/S 3/HTTP, IRIS et le serveur de cache de profil.
seo-title: Composants d'action de données
solution: Audience Manager
title: Composants d'action de données
uuid: c 4 c 4 cc 46-8 c 96-4 ef 5-8269-571 cc 5 ac 9276
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Action Components{#data-action-components}

Les composants d'action de données comprennent les flux de données client, le serveur de collecte de données, les éditeurs SFTP/S 3/HTTP, IRIS et le serveur de cache de profil.

<!-- 

c_compact.xml

 -->

Action components are systems and processes that let you move data in and out of [!DNL Audience Manager] and (for the lack of a better phrase) do things with it. These [!DNL Audience Manager] components include:

## Customer Data Feeds (CDF) {#cdf}

[!UICONTROL CDF] sont des fichiers envoyés par heure aux clients. Ils contiennent un utilisateur - id avec les ID de segment associés, les ID de caractéristique et d'autres données. For more information, see [Customer Data Feed Overview](../../features/cdf-files.md).

## Data Collection Server (DCS) {#dcs}

See [Data Collection Components](../../reference/system-components/components-data-collection.md).

## SFTP/S3 {#sftp-s3}

[!UICONTROL SFTP/S3] Les éditeurs reçoivent des données d'ID synchronisées depuis [!UICONTROL Outbound Feed Converter]la section. When these files are ready, the [!UICONTROL SFTP/S3 publishers] send this data to a destination specified by the client. These files contain synchronized ID data with a one-to-many mapping of [!DNL Audience Manager] user IDs (UUID) to:

* ID de périphérique/ID de fournisseur de données (DPUUID)
* ID de segment qualifiés
* ID de caractéristique

[!DNL Audience Manager] Les clients n'ont pas accès aux fonctionnalités qui contrôlent directement le [!UICONTROL SFPT/S3 publishers]contenu. Les clients utilisent ce service indirectement lorsqu'ils créent et envoient des données vers des destinations. The [!UICONTROL SFTP/S3] system is, essentially, an automated job process that runs at scheduled intervals.

## IRIS {#iris}

In Greek mythology, [!UICONTROL Iris] is a figure who travels and delivers messages rapidly. [!UICONTROL IRIS] Le système est un nom de nom qui reflète les caractéristiques de cette illustration du monde antique. In modern terms, [!UICONTROL IRIS] is a low-latency, high-frequency cookie synchronization and data transfer service.

[!UICONTROL IRIS] fonctionne avec le même type de données que [!UICONTROL SFTP/S3] le système. However, [!UICONTROL IRIS] is different because it sends data to destinations in real time rather than at set intervals. This is a separate system because the [!UICONTROL SFTP/S3] publishers can't send data to an HTTP destination and they're not designed for real-time data transfers.

There are no UI controls that let customers work directly with [!UICONTROL IRIS]. Customers work with [!UICONTROL IRIS] indirectly when they create and send data to destinations, and for other processes that require rapid data transfers.

Examples of [!UICONTROL IRIS] services and features include:

* Synchronisation rapide (sous 30 secondes) pour les cookies et les segments. It can synchronize the [!DNL Audience Manager] cookie, partner cookies, or both.
* Transferts de données en temps réel. [!UICONTROL IRIS] est responsable de l'envoi d'événements de qualification des segments en temps réel à un partenaire ou à une autre destination. This data is JSON-formatted and sent via an HTTP `POST` request.

* Bulk server-to-server data transfers: If you exchange large amounts of data with [!DNL Audience Manager], [!UICONTROL IRIS] is the system that your servers engage with to transfer data.

* Infrastructure fiable qui fonctionne à l'échelle et tolère les erreurs. Systems that power [!UICONTROL IRIS] include Amazon SQS, Amazon EC2, and Cassandra.

**Règles de mappage des segments**

To optimize traffic between [!UICONTROL IRIS] and segment destinations, [!UICONTROL IRIS] sends segments to destinations based on a set of rules.

1. **Nouvelle qualification des segments**: lorsqu'un périphérique est admissible pour un nouveau segment, [!UICONTROL IRIS] envoie tous les segments associés à ce périphérique à toutes les destinations associées à ces segments.

1. **Nouvelle exclusion des segments**: lorsqu'un périphérique ne se qualifie plus pour un segment, [!UICONTROL IRIS] envoie toutes les qualifications et les exclusions de segment associées à ce dispositif à toutes les destinations associées à ces segments.

1. **Mises à jour de mappage de destination**: lorsqu'un mappage de destination est mis à jour, [!UICONTROL IRIS] envoie tous les segments associés à un périphérique à toutes les destinations mappées à ces segments, la prochaine fois qu'Audience Manager voit le périphérique.

1. **Mises à jour du graphique de périphérique**: lorsqu'un ID de périphérique est ajouté ou supprimé du graphique de périphérique utilisé pour évaluer un segment, [!UICONTROL IRIS] envoie tous les segments associés à ce périphérique à toutes les destinations associées à ces segments, la prochaine fois qu'Audience Manager voit le périphérique.

>[!IMPORTANT]
>
>If Audience Manager doesn't detect any of the updates above for 3 consecutive days, [!UICONTROL IRIS] sends all segments associated to a device to all of the destinations mapped to these segments, the next time Audience Manager sees the device.

**Exemple de fichier de données**

The following example contains real-time segment data from [!UICONTROL IRIS]. N'oubliez pas qu'il s'agit uniquement de données d'exemple. Chaque client peut avoir des exigences de formatage différentes pour que le contenu puisse varier.

```
{
    "ProcessTime": "Tue Jul 21 19:12:45 UTC 2015",
    "Client_ID": "111111",
    "AAM_Destination_Id": "22222",
    "User_count": "5",
    "Users": [
        {
            "AAM_UUID": "28272096202945091600036434734793744071",
            "DataPartner_UUID": "CAESEFdv5pk-Lurd8vL9Yfb3qFg",
            "Segments": [
                {
                    "Segment_ID": "1200598",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:12 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "35183292386788708387827965829455926157",
            "DataPartner_UUID": "CAESEF_d8blvZjchQ2WTzdB65yk",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:15 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "28012470144260632050402316345856327572",
            "DataPartner_UUID": "CAESEEPfHBiRjhkzvBPXQ-0MFRE|UzCESAAABOnFeHJy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:33 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "18981483751565214534184221210627150539",
            "DataPartner_UUID": "CAK4NDH0ESEE6NBEhoWDkB7s7ZY|VPYFQQAAASXPElL0",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:36 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "04761851136483019318109155624251711702",
            "DataPartner_UUID": "CAESEDkM5aSaKMV8MfaBhgSspmE|VYnTNwAAASzvVhxy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:42 UTC 2015"
                }
            ]
        }
    ]
}
```

## Profile Cache Server (PCS) {#pcs}

See [Data Collection Components](../../reference/system-components/components-data-collection.md).
