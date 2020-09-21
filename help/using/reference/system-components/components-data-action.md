---
description: Les composants d’action de données comprennent les flux de données client, le serveur de collecte de données, les éditeurs SFTP/S3/HTTP, IRIS et le serveur de cache de Profil.
seo-description: Les composants d’action de données comprennent les flux de données client, le serveur de collecte de données, les éditeurs SFTP/S3/HTTP, IRIS et le serveur de cache de Profil.
seo-title: Composants d’action de données
solution: Audience Manager
title: Composants d’action de données
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: system components
translation-type: tm+mt
source-git-commit: a41f0beffba686f283a2933ad7066cb124e4d380
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 3%

---


# Composants d’action de données{#data-action-components}

Les composants d’action de données comprennent les flux de données client, le serveur de collecte de données, les éditeurs SFTP/S3/HTTP, IRIS et le serveur de cache de Profil.

<!-- 

c_compact.xml

 -->

Les composants d’action sont des systèmes et des processus qui vous permettent de déplacer des données entre [!DNL Audience Manager] et hors et (faute d’une meilleure expression) de faire des choses avec. Ces [!DNL Audience Manager] composants sont les suivants :

## Flux de données client (CDF) {#cdf}

[!UICONTROL CDF] sont des fichiers envoyés toutes les heures aux clients. Ils contiennent des ID d’utilisateur ainsi que des ID de segment associés, des ID de caractéristiques et d’autres données. Pour plus d’informations, voir Présentation [des flux de données](../../features/cdf-files.md)client.

## Serveur de collecte de données (DCS) {#dcs}

Voir [Composants de la collecte de données](../../reference/system-components/components-data-collection.md).

## SFTP/S3 {#sftp-s3}

Les [!UICONTROL SFTP/S3] éditeurs reçoivent les données d’ID synchronisées de la [!UICONTROL Outbound Feed Converter]suite. Lorsque ces fichiers sont prêts, ils [!UICONTROL SFTP/S3 publishers] envoient ces données à une destination spécifiée par le client. Ces fichiers contiennent des données d’ID synchronisées avec un mappage de type &quot;un à plusieurs&quot; d’ID [!DNL Audience Manager] utilisateur (UUID) à :

* ID de périphérique/ID de fournisseur de données (DPUUID)
* ID de segment qualifiés
* ID de caractéristiques

[!DNL Audience Manager] les clients n&#39;ont pas accès à des fonctionnalités qui contrôlent directement le [!UICONTROL SFPT/S3 publishers]. Les clients utilisent ce service indirectement lorsqu’ils créent et envoient des données vers des destinations. Le [!UICONTROL SFTP/S3] système est essentiellement un processus de travail automatisé qui s&#39;exécute à intervalles réguliers.

## IRIS {#iris}

Dans la mythologie grecque, [!UICONTROL Iris] est une figure qui voyage et livre rapidement des messages. Le [!UICONTROL IRIS] système est un homonyme qui reflète les caractéristiques de ce personnage de l&#39;ancien monde. En termes modernes, [!UICONTROL IRIS] il s’agit d’un service de synchronisation de cookies à faible latence et haute fréquence et de transfert de données.

[!UICONTROL IRIS] fonctionne avec le même type de données que le [!UICONTROL SFTP/S3] système. Cependant, [!UICONTROL IRIS] est différent, car il envoie des données vers des destinations en temps réel plutôt qu’à des intervalles définis. Il s’agit d’un système distinct, car les [!UICONTROL SFTP/S3] éditeurs ne peuvent pas envoyer de données vers une destination HTTP et ne sont pas conçus pour les transferts de données en temps réel.

Il n’existe aucun contrôle d’interface utilisateur permettant aux clients de travailler directement avec [!UICONTROL IRIS]. Les clients travaillent avec [!UICONTROL IRIS] indirectement lorsqu’ils créent et envoient des données vers des destinations, ainsi que pour d’autres processus qui nécessitent des transferts rapides de données.

Voici quelques exemples de [!UICONTROL IRIS] services et de fonctionnalités :

* Synchronisation rapide (dans les 30 secondes) des cookies et des segments. Il peut synchroniser le [!DNL Audience Manager] cookie, les cookies partenaires ou les deux.
* Transferts de données en temps réel. [!UICONTROL IRIS] est chargé d&#39;envoyer des événements de qualification de segment en temps réel à un partenaire ou à une autre destination. Ces données sont au format JSON et envoyées via une `POST` requête HTTP.

* Transferts de données serveur à serveur en bloc : Si vous échangez de grandes quantités de données avec [!DNL Audience Manager], [!UICONTROL IRIS] est le système avec lequel vos serveurs s’engagent pour transférer des données.

* Une infrastructure fiable qui fonctionne à grande échelle et tolère les pannes. Les systèmes qui fonctionnent [!UICONTROL IRIS] incluent Amazon SQS, Amazon EC2 et Cassandra.

**Règles de mappage de segments**

Pour optimiser le trafic entre les destinations [!UICONTROL IRIS] et les destinations de segments, [!UICONTROL IRIS] envoie des segments vers des destinations en fonction d’un ensemble de règles.

1. **Nouvelle qualification** de segment : lorsqu’un périphérique est admissible pour un nouveau segment, [!UICONTROL IRIS] envoie tous les segments associés à ce périphérique à toutes les destinations mises en correspondance avec ces segments.

1. **Nouvelle exclusion** de segment : lorsqu&#39;un périphérique n&#39;est plus admissible pour un segment, [!UICONTROL IRIS] envoie toutes les qualifications et les disqualifications de segment associées à ce périphérique à toutes les destinations associées à ces segments.

1. **Mises à jour** du mappage de destination : lorsqu’un mappage de destination est mis à jour, [!UICONTROL IRIS] envoie tous les segments associés à un périphérique vers toutes les destinations mises en correspondance avec ces segments, la prochaine fois que l’Audience Manager voit le périphérique.

1. **Mises à jour** du graphique du périphérique : lorsqu’un identifiant de périphérique est ajouté ou supprimé du graphique de périphérique utilisé pour évaluer un segment, [!UICONTROL IRIS] envoie tous les segments associés à ce périphérique à toutes les destinations mises en correspondance avec ces segments, la prochaine fois que l’Audience Manager voit le périphérique.

>[!IMPORTANT]
>
>Si l’Audience Manager ne détecte aucune des mises à jour ci-dessus pendant 3 jours consécutifs, [!UICONTROL IRIS] envoie tous les segments associés à un périphérique à toutes les destinations mises en correspondance avec ces segments, la prochaine fois que l’Audience Manager voit le périphérique.

**Exemple de fichier de données**

L’exemple suivant contient des données de segment en temps réel provenant de [!UICONTROL IRIS]la section. N’oubliez pas qu’il s’agit uniquement d’exemples de données. Chaque client peut avoir des exigences de formatage différentes pour que le contenu puisse varier.

```json
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

## Serveur de cache de profil (PCS) {#pcs}

Voir [Composants de la collecte de données](../../reference/system-components/components-data-collection.md).
