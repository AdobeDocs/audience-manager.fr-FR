---
description: Audience Manager et le service d'identité Adobe Experience Platform appellent et reçoivent les données du domaine demdex.net. Il peut sembler que l'Adobe travaille avec un domaine tiers inhabituel, mais ce n'est pas le cas. Cette section décrit les éléments d’un appel demdex.net.
seo-description: Audience Manager et le service d'identité Adobe Experience Platform appellent et reçoivent les données du domaine demdex.net. Il peut sembler que l'Adobe travaille avec un domaine tiers inhabituel, mais ce n'est pas le cas. Cette section décrit les éléments d’un appel demdex.net.
seo-title: Signification des appels vers le domaine Demdex
solution: Audience Manager
title: Signification des appels vers le domaine Demdex
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 15%

---


# Présentation des appels au domaine [!DNL Demdex] {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] et les  [!DNL Adobe Experience Platform Identity Service] appels à et les données reçues du  `demdex.net` domaine. Il peut sembler que [!DNL Adobe] fonctionne avec un domaine tiers inhabituel, mais ce n&#39;est pas le cas. Cette section décrit les éléments d&#39;un appel `demdex.net`.

| Elément Appel | Description |
|---|---|
| `demdex.net` | Il s’agit d’un domaine hérité contrôlé par [!DNL Adobe]. Il reflète le nom d’origine de [!DNL Audience Manager] ([!DNL Demdex]). [!DNL Adobe] a fait l’acquisition de [!DNL Demdex] en 2011 et a rebaptisé la société [!DNL Audience Manager]. Il est difficile de modifier ce domaine car il est étroitement lié à [!DNL Audience Manager], à [!DNL Adobe Experience Cloud ID Service] et à notre base d&#39;utilisateurs installée. Vous pouvez voir d&#39;autres préfixes attachés aux appels `demdex.net` hérités (par exemple, `dcs.demdex.net`, `fast.demdex.net`, etc.). Quel que soit le préfixe, un appel à `something.demdex.net` est toujours un appel à [!DNL Adobe] et non à un domaine tiers inconnu ou suspect. |
| `dpm` | [!DNL DPM] est une abréviation de  [!DNL Data Provider Match]. Il indique aux systèmes internes [!DNL Adobe] qu&#39;un appel de [!DNL Audience Manager] ou de [!DNL Adobe Experience Cloud ID Service] transmet les données client pour synchronisation ou demande un identifiant. Il s&#39;agit de l&#39;appel le plus courant `demdex.net` que vous verrez de [!DNL Audience Manager] ou de [!DNL Adobe Experience Cloud ID Service]. <br><br>[!DNL DPM] Concepts de base des appels : <ul><li>[!DNL Audience Manager]: Un  [!DNL DPM] appel de  [!DNL Audience Manager] envoie des données à la  [!DNL Data Collection Servers] et  [!DNL Profile Cache Servers]à. Voir [Composants de la collecte de données](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: Un  [!DNL DPM] appel de la  [!DNL Adobe Experience Cloud ID Service] est une demande d’identifiant de visiteur. Voir [Cookies et Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/fr-FR/id-service/using/intro/cookies.html) et [Comment le service d&#39;identité Adobe Experience Platform demande et définit des identifiants](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html).</li></ul><br>Remarque :  [!DNL Adobe Experience Cloud ID Service] les clients peuvent modifier le  [!DNL DPM] préfixe dans le nom de domaine. Voir [serveur audienceManager et audienceManagerServerSecure](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/fr-FR/id-service/using/home.html)
>* [Cookies Audience Manager](https://docs.adobe.com/content/help/fr-FR/core-services/interface/ec-cookies/cookies-am.html)

