---
description: Les composants d’action de données incluent les flux de données client, le serveur de collecte de données, les éditeurs SFTP/S3/HTTP, IRIS et le serveur de cache de profil.
seo-description: Data action components include Customer Data Feeds, the Data Collection Server, SFTP/S3/HTTP publishers, IRIS, and the Profile Cache Server.
seo-title: Data Action Components
solution: Audience Manager
title: Composants de l’action de données
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: System Components
exl-id: 8065c19f-1930-4164-a952-1686aa5cb622
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 1%

---

# Composants de l’action de données{#data-action-components}

Les composants d’action de données incluent les flux de données client, le serveur de collecte de données, les éditeurs SFTP/S3/HTTP, IRIS et le serveur de cache de profil.

<!-- 

c_compact.xml

 -->

Les composants d’action sont des systèmes et des processus qui vous permettent de déplacer des données dans et hors du [!DNL Audience Manager] et (à défaut d’une meilleure expression) d’en faire des choses. Ces composants [!DNL Audience Manager] incluent :

## Flux de données client (CDF) {#cdf}

[!UICONTROL CDF] fichiers sont envoyés toutes les heures aux clients. Ils contiennent des identifiants d’utilisateur ainsi que les identifiants de segment, les identifiants de caractéristique et d’autres données associées. Pour plus d’informations, voir [ Présentation des flux de données client ](../../features/cdf-files.md).

## Data Collection Server (DCS) {#dcs}

Voir [Composants de la collecte de données](../../reference/system-components/components-data-collection.md).

## SFTP/S3 {#sftp-s3}

Les éditeurs [!UICONTROL SFTP/S3] reçoivent des données d’ID synchronisées de la [!UICONTROL Outbound Feed Converter]. Lorsque ces fichiers sont prêts, les [!UICONTROL SFTP/S3 publishers] envoient ces données vers une destination spécifiée par le client. Ces fichiers contiennent des données d’ID synchronisées avec un mappage de type « un à plusieurs » des ID utilisateur [!DNL Audience Manager] (UUID) aux éléments suivants :

* Identifiant de l’appareil/identifiants du fournisseur de données (DPUUID)
* Identifiants de segment qualifiés
* Identifiants de caractéristiques

[!DNL Audience Manager] clients n’ont pas accès aux fonctionnalités qui contrôlent directement le [!UICONTROL SFPT/S3 publishers]. Les clients utilisent ce service indirectement lorsqu’ils créent et envoient des données aux destinations. Le système [!UICONTROL SFTP/S3] est essentiellement un processus de tâche automatisé qui s’exécute à intervalles planifiés.

## IRIS {#iris}

Dans la mythologie grecque, [!UICONTROL Iris] est une figure qui voyage et délivre des messages rapidement. Le système [!UICONTROL IRIS] est un homonyme qui reflète les caractéristiques de cette figure du monde antique. En termes modernes, [!UICONTROL IRIS] est un service de synchronisation des cookies et de transfert de données à faible latence et à haute fréquence.

[!UICONTROL IRIS] fonctionne avec le même type de données que le système [!UICONTROL SFTP/S3]. Cependant, [!UICONTROL IRIS] est différent, car il envoie des données aux destinations en temps réel plutôt qu’à des intervalles définis. Il s’agit d’un système distinct, car les éditeurs [!UICONTROL SFTP/S3] ne peuvent pas envoyer de données vers une destination HTTP et ils ne sont pas conçus pour les transferts de données en temps réel.

Il n’existe aucune commande de l’interface utilisateur qui permet aux clients de travailler directement avec [!UICONTROL IRIS]. Les clients travaillent avec [!UICONTROL IRIS] indirectement lorsqu’ils créent et envoient des données aux destinations, ainsi que pour d’autres processus nécessitant des transferts de données rapides.

Voici quelques exemples de services et de fonctionnalités [!UICONTROL IRIS] :

* Synchronisation rapide (dans les 30 secondes) des cookies et des segments. Il peut synchroniser le cookie [!DNL Audience Manager], les cookies partenaires ou les deux.
* Transferts de données en temps réel. [!UICONTROL IRIS] est chargé d’envoyer des événements de qualification de segment en temps réel à un partenaire ou à une autre destination. Ces données sont au format JSON et envoyées via une requête HTTP `POST`.

* Transferts de données en bloc de serveur à serveur : si vous échangez de grandes quantités de données avec [!DNL Audience Manager], [!UICONTROL IRIS] est le système avec lequel vos serveurs s’engagent pour transférer les données.

* Une infrastructure fiable qui fonctionne à grande échelle et tolère les pannes. Les systèmes qui alimentent [!UICONTROL IRIS] comprennent Amazon SQS, Amazon EC2 et Cassandra.

**Règles de mappage de segments**

Pour optimiser le trafic entre les destinations de [!UICONTROL IRIS] et de segment, [!UICONTROL IRIS] envoie des segments vers les destinations en fonction d’un ensemble de règles.

1. **Qualification du nouveau segment** : lorsqu’un appareil remplit les conditions d’un nouveau segment, [!UICONTROL IRIS] envoie tous les segments associés à cet appareil vers toutes les destinations mappées à ces segments.

1. **Nouvelle disqualification de segment** : lorsqu’un appareil n’est plus admissible pour un segment, [!UICONTROL IRIS] envoie toutes les qualifications et disqualifications de segment associées à cet appareil à toutes les destinations mappées à ces segments.

1. **Mises à jour du mappage de destination** : lorsqu’un mappage de destination est mis à jour, [!UICONTROL IRIS] envoie tous les segments associés à un appareil vers toutes les destinations mappées à ces segments, la prochaine fois qu’Audience Manager verra l’appareil.

1. **Mises à jour du graphique d’appareil** : lorsqu’un identifiant d’appareil est ajouté ou supprimé du graphique d’appareil utilisé pour évaluer un segment, [!UICONTROL IRIS] envoie tous les segments associés à cet appareil à toutes les destinations mappées à ces segments, la prochaine fois qu’Audience Manager verra l’appareil.

>[!IMPORTANT]
>
>Si Audience Manager ne détecte aucune des mises à jour ci-dessus pendant 3 jours consécutifs, [!UICONTROL IRIS] envoie tous les segments associés à un appareil vers toutes les destinations mappées à ces segments, la prochaine fois qu’Audience Manager verra l’appareil.

**Fichier de données d’exemple**

L’exemple suivant contient des données de segment en temps réel provenant de [!UICONTROL IRIS]. Gardez à l’esprit qu’il s’agit uniquement de données d’exemple. Chaque client peut avoir des exigences de mise en forme différentes, de sorte que le contenu peut varier.

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

## Serveur de cache de profils (PCS) {#pcs}

Voir [Composants de la collecte de données](../../reference/system-components/components-data-collection.md).
