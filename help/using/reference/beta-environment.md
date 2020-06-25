---
description: L’environnement bêta permet de tester la mise en oeuvre de votre Audience Manager. Les modifications effectuées en version bêta n’affectent pas les données de production. Si vous souhaitez utiliser l'environnement bêta, contactez votre représentant Solutions partenaires d'Audience Manager.
keywords: sandbox
seo-description: L’environnement bêta permet de tester la mise en oeuvre de votre Audience Manager. Les modifications effectuées en version bêta n’affectent pas les données de production. Si vous souhaitez utiliser l'environnement bêta, contactez votre représentant Solutions partenaires d'Audience Manager.
seo-title: Environnement bêta
solution: Audience Manager
title: Environnement bêta
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 4%

---


# Environnement bêta {#beta-environment}

L’environnement bêta permet de tester la mise en oeuvre de votre Audience Manager. Les modifications effectuées en version bêta n’affectent pas les données de production. Si vous souhaitez utiliser l&#39;environnement bêta, contactez votre représentant Solutions partenaires d&#39;Audience Manager.

## Aperçu

L&#39;environnement bêta est une réplique exacte de l&#39;environnement de production, sans aucune fonctionnalité expérimentale ou non publiée. Vos informations de connexion à partir de l’environnement de production sont valides dans l’environnement bêta.

**Mettre à jour le calendrier**

L&#39;environnement bêta est mis à jour à la fin de chaque mois pendant les heures creuses.

**Trafic sortant**

Le trafic sortant n&#39;est pas activé pour l&#39;environnement bêta.

<!-- 

Added re: AAM-30826.

 -->

## Points de terminaison



| Service | URL/nom d’hôte | Comment obtenir un accès |
|--- |--- | --- |
| S3 | Contactez votre représentant des solutions partenaires d’Audience Manager ou le service d’assistance clientèle | Contactez votre représentant Solutions partenaires d’Audience Manager ou le service d’assistance clientèle pour configurer un compartiment Amazon S3 pour votre instance bêta. Découvrez les [avantages de l’utilisation d’Amazon S3](../reference/amazon-s3.md). |
| DCS | `https://dcs-beta.demdex.net/...` | Reportez-vous à [Accès au DCS dans l’Environnement](../reference/beta-environment.md#access-dcs-beta-environment)bêta. |
| IU | `https://bank-beta.demdex.com` | Vos informations d’identification d’environnement de production sont valides pour l’environnement bêta. |
| API | `https://api-beta.demdex.com/...` | Vos informations d’identification d’environnement de production sont valides pour l’environnement bêta. Nous vous recommandons de créer un utilisateur d&#39;API générique, [voir les détails](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## Accès au serveur de collecte de données dans l’Environnement bêta {#access-dcs-beta-environment}

1. Effectuez un appel DCS à l’aide de la [commande curl](https://curl.haxx.se/docs/manpage.html). Curl est un outil permettant de transférer des données depuis ou vers un serveur, en utilisant l&#39;un des nombreux protocoles pris en charge.

   Par exemple :

   `curl -v https://dcs-beta.demdex.net/event`

1. Vérifiez que votre demande a été traitée par le serveur de collecte de données bêta en recherchant &quot;sandbox&quot; dans l’en-tête de réponse du serveur de collecte de données.

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