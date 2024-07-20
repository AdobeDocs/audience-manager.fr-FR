---
description: Audience Manager et le service Adobe Experience Platform Identity appellent et reçoivent des données du domaine demdex.net . Il peut sembler que l’Adobe fonctionne avec un domaine tiers inhabituel, mais ce n’est pas le cas. Cette section décrit les éléments d’un appel demdex.net .
seo-description: Audience Manager and the Adobe Experience Platform Identity Service make calls to and receive data from the demdex.net domain. This may seem like Adobe is working with an unusual third-party domain, but this is not the case. This section describes the elements in a demdex.net call.
seo-title: Understanding Calls to the Demdex Domain
solution: Audience Manager
title: Signification des appels vers le domaine Demdex
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: Reference
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 4%

---

# Signification des appels vers le domaine [!DNL Demdex] {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] et [!DNL Adobe Experience Platform Identity Service] appellent et reçoivent des données du domaine `demdex.net`. Il peut sembler que [!DNL Adobe] fonctionne avec un domaine tiers inhabituel, mais ce n’est pas le cas. Cette section décrit les éléments d’un appel `demdex.net`.

| Elément d’appel | Description |
|---|---|
| `demdex.net` | Il s’agit d’un domaine hérité contrôlé par [!DNL Adobe]. Il reflète le nom d’origine, préacquisition de [!DNL Audience Manager] ([!DNL Demdex]). [!DNL Adobe] a fait l’acquisition de [!DNL Demdex] en 2011 et a rebaptisé la société [!DNL Audience Manager]. Il est difficile de modifier ce domaine car il est étroitement lié à [!DNL Audience Manager], à [!DNL Adobe Experience Cloud ID Service] et à notre base d’utilisateurs installée. D’autres préfixes peuvent être associés aux appels `demdex.net` hérités (par exemple, `dcs.demdex.net`, `fast.demdex.net`, etc.). Quel que soit le préfixe, un appel vers `something.demdex.net` est toujours un appel vers [!DNL Adobe] et non vers un domaine tiers inconnu ou suspect. |
| `dpm` | [!DNL DPM] est une abréviation de [!DNL Data Provider Match]. Il indique aux systèmes internes [!DNL Adobe] qu’un appel de [!DNL Audience Manager] ou de [!DNL Adobe Experience Cloud ID Service] transmet des données client pour synchronisation ou demande un identifiant. Il s’agit de l’appel `demdex.net` le plus courant que vous verrez depuis [!DNL Audience Manager] ou [!DNL Adobe Experience Cloud ID Service]. <br><br>[!DNL DPM] - Principes de base des appels : <ul><li>[!DNL Audience Manager] : un appel [!DNL DPM] de [!DNL Audience Manager] envoie des données à [!DNL Data Collection Servers] et [!DNL Profile Cache Servers]. Voir [Composants de la collecte de données](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service] : un appel [!DNL DPM] de [!DNL Adobe Experience Cloud ID Service] est une demande d’identifiant visiteur. Voir [Cookies et service Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) et [Requête et définition d’ID par le service Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/intro/id-request.html).</li></ul><br>Remarque : les clients [!DNL Adobe Experience Cloud ID Service] peuvent modifier le préfixe [!DNL DPM] dans le nom de domaine. Voir [audienceManager Server et audienceManagerServerSecure](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Service Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html)
>* [Cookies d’Audience Manager](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html)
