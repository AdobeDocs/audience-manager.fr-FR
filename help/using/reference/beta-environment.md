---
description: L’environnement bêta permet de tester la mise en oeuvre de votre Audience Manager. Les modifications effectuées en version bêta n’affectent pas les données de production. Contactez votre représentant Partenaires en solutions d’Audience Manager si vous souhaitez utiliser l’environnement bêta.
keywords: sandbox
seo-description: The beta environment is for testing your Audience Manager implementation. Changes made in beta do not affect production data. Contact your Audience Manager Partner Solutions representative if you're interested in using the beta environment.
seo-title: Beta Environment
solution: Audience Manager
title: Environnement bêta
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
feature: Reference
exl-id: a6a5e1c2-29a2-40bf-972c-87fb8716a394
source-git-commit: fce39268f1c8c4dd1b7ff21b61a9830a20fa0b4e
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 3%

---

# Environnement bêta {#beta-environment}

L’environnement bêta permet de tester la mise en oeuvre de votre Audience Manager. Les modifications effectuées en version bêta n’affectent pas les données de production. Contactez votre représentant Partenaires en solutions d’Audience Manager si vous souhaitez utiliser l’environnement bêta.

## Présentation

La fonctionnalité de l’environnement bveta est une réplique exacte de l’environnement de production, sans aucune fonctionnalité expérimentale ou non publiée. Vos informations de connexion de l’environnement de production sont valides dans l’environnement bêta.

**Mettre à jour le planning**

L’environnement bêta est mis à jour à la fin de chaque mois pendant les heures creuses.

>[!IMPORTANT]
>
>Notez que vos données client ([signaux, caractéristiques et segments](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html?lang=en)) n’est pas synchronisé entre les environnements de production et bêta.

## Trafic entrant

L’environnement bêta ne prend en charge le trafic entrant que pour la validation du nom de fichier et de la syntaxe du contenu. Comme aucun mappage d’ID n’a lieu dans l’environnement bêta, les clients ne verront aucune population de segments.

Par conséquent, la [!UICONTROL Onboarding Status] page sera toujours rapport [!UICONTROL No matching AAM ID] lors de l’ingestion des fichiers dans l’environnement bêta.

Nous conseillons à tous les clients d’effectuer des tests entrants sur leur environnement de production.

## Trafic sortant

Le trafic sortant n’est pas activé pour l’environnement bêta.

## Points de fin

| Service | URL/Nom d’hôte | Comment obtenir un accès |
|--- |--- | --- |
| S3 | Contactez votre représentant des solutions partenaires pour votre Audience Manager ou l’assistance clientèle. | Contactez votre représentant des solutions partenaires d’Audience Manager ou l’assistance clientèle pour configurer un compartiment Amazon S3 pour votre instance bêta. En savoir plus sur les [avantages de l’utilisation d’Amazon S3](../reference/amazon-s3.md). |
| DCS | `https://dcs-beta.demdex.net/...` | Voir [Accès au DCS dans l’environnement bêta](../reference/beta-environment.md#access-dcs-beta-environment). |
| IU | `https://bank-beta.demdex.com` | Les informations d’identification de votre environnement de production sont valides pour l’environnement bêta. |
| API | `https://api-beta.demdex.com/...` | Les informations d’identification de votre environnement de production sont valides pour l’environnement bêta. Nous vous recommandons de créer un utilisateur API générique, [voir détails](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## Accès au DCS dans l’environnement bêta {#access-dcs-beta-environment}

1. Effectuez un appel DCS à l’aide de l’URL [command](https://curl.haxx.se/docs/manpage.html). Curl est un outil permettant de transférer des données depuis ou vers un serveur, à l’aide de l’un des nombreux protocoles pris en charge.

   Par exemple :

   `curl -v https://dcs-beta.demdex.net/event`

1. Vérifiez que votre requête a été traitée par le serveur de collecte de données bêta en recherchant &quot;sandbox&quot; dans l’en-tête de réponse du serveur de collecte de données.

   Par exemple :

   ```
   curl -v http://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

<!--

1. Determine the load balancer's endpoint IP addresses.

   Run the `dig`  [command](https://en.wikipedia.org/wiki/Dig_(command)) to determine the IP address of the nearest load balancer. The `dig` command queries the Domain Name System and returns the name and IP addresses of the [!DNL Audience Manager] [!UICONTROL Data Collection Servers (DCS)].

   ```
   dig dcs-beta.demdex.net
   ...
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.87.15.51
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 50.16.150.8
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.2.228.100
   ```

2. Using one of the addresses in the above table, add a static DNS entry in the [!DNL /etc/hosts] file.

   On Windows, modify [!DNL c:\WINDOWS\system32\drivers\etc\hosts].

   For example:

   [!DNL 52.87.15.51 *`samplepartner`*.demdex.net]

   >[!NOTE]
   >
   >The addresses change occasionally, so you must keep your [!DNL /etc/hosts] file up to date.

   Additionally, if you need to set up ID synchronization, you must add a similar entry for [!DNL dpm.demdex.net.]

   [!DNL 52.87.15.51 dpm.demdex.net]. 

3. Make a DCS call, using the `curl` [command](https://curl.haxx.se/docs/manpage.html). Curl is a tool to transfer data from or to a server, using one of many supported protocols.

   For example:

   [!DNL https://<domain>/event?product=camera] 

4. Verify that your request was served by the beta DCS by looking for "sandbox" in the DCS response header.

   For example:

   ```
   curl -v https://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

   -->
