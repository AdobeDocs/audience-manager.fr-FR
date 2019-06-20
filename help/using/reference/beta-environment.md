---
description: L'environnement bêta est destiné à tester votre implémentation d'Audience Manager. Les modifications effectuées en version bêta n'affectent pas les données de production. Contactez votre gestionnaire de solutions partenaires Audience Manager si vous souhaitez utiliser l'environnement bêta.
keywords: sandbox
seo-description: L'environnement bêta est destiné à tester votre implémentation d'Audience Manager. Les modifications effectuées en version bêta n'affectent pas les données de production. Contactez votre gestionnaire de solutions partenaires Audience Manager si vous souhaitez utiliser l'environnement bêta.
seo-title: Environnement bêta
solution: Audience Manager
title: Environnement bêta
uuid: de 4 a 1 a 46-cfa 4-4 f 64-8569-48 a 7650 fd 8 cf
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# Environnement bêta {#beta-environment}

L&#39;environnement bêta est destiné à tester votre implémentation d&#39;Audience Manager. Les modifications effectuées en version bêta n&#39;affectent pas les données de production. Contactez votre gestionnaire de solutions partenaires Audience Manager si vous souhaitez utiliser l&#39;environnement bêta.

## Aperçu

L&#39;environnement bêta est une réplique exacte de l&#39;environnement de production, sans fonctionnalité expérimentale ou non publiée. Vos informations de connexion de l&#39;environnement de production sont valides dans l&#39;environnement bêta.

**Mettre à jour la planification**

L&#39;environnement bêta est mis à jour à la fin de chaque mois pendant les heures creuses.

**Trafic sortant**

Le trafic sortant n&#39;est pas activé pour l&#39;environnement bêta.

<!-- 

Added re: AAM-30826.

 -->

## Points de fin



| Service | URL/Nom d&#39;hôte | Obtention d&#39;un accès |
|--- |--- | --- |
| S3 | Contactez votre gestionnaire de solutions partenaires Audience Manager ou le service d&#39;assistance clientèle. | Contactez votre gestionnaire de solutions partenaires Audience Manager ou le service d&#39;assistance clientèle pour configurer un compartiment Amazon S 3 pour votre instance bêta. Read about the [advantages of using Amazon S3](../reference/amazon-s3.md). |
| DCS | `https://dcs-beta.demdex.net/...` | See [Accessing the DCS in the Beta Environment](../reference/beta-environment.md#access-dcs-beta-environment). |
| IU | `https://bank-beta.demdex.com` | Les informations d&#39;identification d&#39;environnement de production sont valides pour l&#39;environnement bêta. |
| API | `https://api-beta.demdex.com/...` | Les informations d&#39;identification d&#39;environnement de production sont valides pour l&#39;environnement bêta. We recommend that you create a generic API user, [see details](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## Accessing the DCS in the Beta Environment {#access-dcs-beta-environment}

1. Make a DCS call, using the curl [command](https://curl.haxx.se/docs/manpage.html). Curl est un outil permettant de transférer des données depuis ou vers un serveur, à l&#39;aide de l&#39;un des nombreux protocoles pris en charge.

   Par exemple :

   `curl -v https://dcs-beta.demdex.net/event`

1. Vérifiez que votre requête a été diffusée par le serveur de collecte de données bêta en recherchant « sandbox » dans l&#39;en-tête de réponse de DCS.

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