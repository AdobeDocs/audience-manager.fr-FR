---
description: L'Audience Manager et le service d'identité de l'Adobe Experience Platform appellent et reçoivent les données du domaine demdex.net. Il peut sembler que Adobe travaille avec un domaine tiers inhabituel, mais ce n'est pas le cas. Cette section décrit les éléments d’un appel demdex.net.
seo-description: L'Audience Manager et le service d'identité de l'Adobe Experience Platform appellent et reçoivent les données du domaine demdex.net. Il peut sembler que Adobe travaille avec un domaine tiers inhabituel, mais ce n'est pas le cas. Cette section décrit les éléments d’un appel demdex.net.
seo-title: Signification des appels vers le domaine Demdex
solution: Audience Manager
title: Signification des appels vers le domaine Demdex
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 4%

---


# Understanding Calls to the [!DNL Demdex] Domain {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] et le [!DNL Adobe Experience Platform Identity Service] fait des appels et reçoit des données du `demdex.net` domaine. Cela peut sembler [!DNL Adobe] fonctionner avec un domaine tiers inhabituel, mais ce n&#39;est pas le cas. Cette section décrit les éléments d’un `demdex.net` appel.

| Elément Appel | Description |
|---|---|
| `demdex.net` | Il s&#39;agit d&#39;un domaine hérité contrôlé par [!DNL Adobe]. Il reflète le nom original de [!DNL Audience Manager] ([!DNL Demdex]) préacquisition. [!DNL Adobe] acquis [!DNL Demdex] en 2011 et rebaptisé la société [!DNL Audience Manager]. Il est difficile de modifier ce domaine car il est étroitement lié à [!DNL Audience Manager], au [!DNL Adobe Experience Cloud ID Service]et à notre base d&#39;utilisateurs installée. D’autres préfixes peuvent être associés à des `demdex.net` appels hérités (par ex. `dcs.demdex.net`, `fast.demdex.net`etc.). Quel que soit le préfixe, un appel à `something.demdex.net` est toujours un appel vers [!DNL Adobe] un domaine tiers inconnu ou suspect, et non vers un domaine tiers suspect. |
| `dpm` | [!DNL DPM] est une abréviation de [!DNL Data Provider Match]. Il indique aux systèmes internes [!DNL Adobe] qu’un appel de [!DNL Audience Manager] ou de la [!DNL Adobe Experience Cloud ID Service] société transmet des données client pour synchronisation ou demande un identifiant. Il s&#39;agit de l&#39; `demdex.net` appel le plus courant que vous verrez depuis [!DNL Audience Manager] ou depuis [!DNL Adobe Experience Cloud ID Service]. <br><br>[!DNL DPM] Concepts de base des appels : <ul><li>[!DNL Audience Manager]: Un [!DNL DPM] appel de [!DNL Audience Manager] envoie des données au [!DNL Data Collection Servers] et [!DNL Profile Cache Servers]. Voir Composants [de collecte de](../reference/system-components/components-data-collection.md)données.</li><li>[!DNL Adobe Experience Cloud ID Service]: Un [!DNL DPM] appel de la [!DNL Adobe Experience Cloud ID Service] est une demande d’identifiant de visiteur. Voir [Cookies et Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html) et [How the Adobe Experience Platform Identity Service request and Sets ID](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html).</li></ul><br>Remarque : [!DNL Adobe Experience Cloud ID Service] les clients peuvent modifier le [!DNL DPM] préfixe dans le nom de domaine. Voir [audienceManager Server et audienceManagerServerSecure](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Cookies Audience Manager](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html)

