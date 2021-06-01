---
description: Les composants d’action de données comprennent les flux de données client, le serveur de collecte de données, les éditeurs SFTP/S3/HTTP, IRIS et le serveur de cache de profil.
seo-description: Les composants d’action de données comprennent les flux de données client, le serveur de collecte de données, les éditeurs SFTP/S3/HTTP, IRIS et le serveur de cache de profil.
seo-title: Composants d’action de données
solution: Audience Manager
title: Composants d’action de données
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: 'Composants système '
exl-id: 8065c19f-1930-4164-a952-1686aa5cb622
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 3%

---

# Composants d’action de données{#data-action-components}

Les composants d’action de données comprennent les flux de données client, le serveur de collecte de données, les éditeurs SFTP/S3/HTTP, IRIS et le serveur de cache de profil.

<!-- 

c_compact.xml

 -->

Les composants d’action sont des systèmes et des processus qui vous permettent de déplacer des données dans et hors de [!DNL Audience Manager] et (faute d’une meilleure expression) d’en faire quelque chose. Ces [!DNL Audience Manager] composants incluent :

## Flux de données client (CDF) {#cdf}

[!UICONTROL CDF] sont des fichiers envoyés toutes les heures aux clients. Ils contiennent des identifiants d’utilisateur ainsi que des identifiants de segment, de caractéristiques et d’autres données associés. Pour plus d’informations, voir [Présentation du flux de données client](../../features/cdf-files.md).

## Serveur de collecte de données (DCS) {#dcs}

Voir [Composants de la collecte de données](../../reference/system-components/components-data-collection.md).

## SFTP/S3 {#sftp-s3}

Les éditeurs [!UICONTROL SFTP/S3] reçoivent les données d’ID synchronisées de [!UICONTROL Outbound Feed Converter]. Lorsque ces fichiers sont prêts, la balise [!UICONTROL SFTP/S3 publishers] envoie ces données vers une destination spécifiée par le client. Ces fichiers contiennent des données d’ID synchronisées avec un mappage de [!DNL Audience Manager] identifiants utilisateur (UUID) à :

* ID d’appareil/ID de fournisseur de données (DPUUID)
* ID de segment qualifiés
* ID de caractéristique

[!DNL Audience Manager] Les clients n’ont pas accès aux fonctionnalités qui contrôlent directement le  [!UICONTROL SFPT/S3 publishers]. Les clients utilisent ce service indirectement lorsqu’ils créent et envoient des données vers des destinations. Le système [!UICONTROL SFTP/S3] est essentiellement un processus de tâche automatisé qui s’exécute à des intervalles planifiés.

## IRIS {#iris}

Dans la mythologie grecque, [!UICONTROL Iris] est une figure qui voyage et diffuse des messages rapidement. Le système [!UICONTROL IRIS] est un homonyme qui reflète les caractéristiques de cette figure de l&#39;ancien monde. En termes modernes, [!UICONTROL IRIS] est un service de synchronisation et de transfert de données de cookies à faible latence et à haute fréquence.

[!UICONTROL IRIS] fonctionne avec le même type de données que le  [!UICONTROL SFTP/S3] système. Cependant, [!UICONTROL IRIS] est différent, car il envoie des données vers les destinations en temps réel plutôt qu’à des intervalles définis. Il s’agit d’un système distinct, car les éditeurs [!UICONTROL SFTP/S3] ne peuvent pas envoyer de données vers une destination HTTP et ils ne sont pas conçus pour les transferts de données en temps réel.

Il n’existe aucun contrôle d’interface utilisateur qui permet aux clients de travailler directement avec [!UICONTROL IRIS]. Les clients travaillent indirectement avec [!UICONTROL IRIS] lorsqu’ils créent et envoient des données vers des destinations et pour d’autres processus qui nécessitent des transferts de données rapides.

Voici quelques exemples de services et de fonctionnalités [!UICONTROL IRIS] :

* Synchronisation rapide (dans les 30 secondes) des cookies et des segments. Il peut synchroniser le cookie [!DNL Audience Manager], les cookies de partenaire ou les deux.
* Transferts de données en temps réel. [!UICONTROL IRIS] est chargé d’envoyer des événements de qualification de segment en temps réel à un partenaire ou à une autre destination. Ces données sont au format JSON et envoyées via une requête HTTP `POST`.

* Transferts de données serveur à serveur en bloc : Si vous échangez de grandes quantités de données avec [!DNL Audience Manager], [!UICONTROL IRIS] est le système avec lequel vos serveurs interagissent pour transférer des données.

* Une infrastructure fiable qui fonctionne à grande échelle et qui tolère les défauts. Les systèmes qui alimentent [!UICONTROL IRIS] incluent Amazon SQS, Amazon EC2 et Cassandra.

**Règles de mappage des segments**

Pour optimiser le trafic entre les [!UICONTROL IRIS] et les destinations de segment, [!UICONTROL IRIS] envoie des segments vers des destinations en fonction d’un ensemble de règles.

1. **Nouvelle qualification** du segment : lorsqu’un appareil est admissible pour un nouveau segment,  [!UICONTROL IRIS] envoie tous les segments associés à cet appareil vers toutes les destinations mappées à ces segments.

1. **Nouvelle disqualification** des segments : lorsqu’un appareil n’est plus admissible pour un segment,  [!UICONTROL IRIS] envoie toutes les qualifications et les disqualifications de segment associées à cet appareil à toutes les destinations mappées à ces segments.

1. **Mises à jour** du mapping de destination : lorsqu’un mappage de destination est mis à jour,  [!UICONTROL IRIS] envoie tous les segments associés à un appareil vers toutes les destinations mappées à ces segments, la prochaine fois que l’Audience Manager voit l’appareil.

1. **Mises à jour** du graphique d’appareil : lorsqu’un identifiant d’appareil est ajouté ou supprimé du graphique d’appareil utilisé pour évaluer un segment,  [!UICONTROL IRIS] envoie tous les segments associés à cet appareil à toutes les destinations mappées à ces segments, la prochaine fois que l’Audience Manager voit l’appareil.

>[!IMPORTANT]
>
>Si l’Audience Manager ne détecte aucune des mises à jour ci-dessus pendant 3 jours consécutifs, [!UICONTROL IRIS] envoie tous les segments associés à un appareil à toutes les destinations mappées à ces segments, la prochaine fois que l’Audience Manager voit l’appareil.

**Exemple de fichier de données**

L’exemple suivant contient des données de segment en temps réel provenant de [!UICONTROL IRIS]. Gardez à l’esprit qu’il s’agit uniquement d’exemples de données. Chaque client peut avoir des exigences de mise en forme différentes afin que le contenu puisse varier.

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
