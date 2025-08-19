---
description: Audience Manager et Adobe Experience Platform Identity Service effectuent des appels vers le domaine demdex.net et reçoivent des données de ce domaine. Il peut sembler qu’Adobe travaille avec un domaine tiers inhabituel, mais ce n’est pas le cas. Cette section décrit les éléments d’un appel demdex.net.
seo-description: Audience Manager and the Adobe Experience Platform Identity Service make calls to and receive data from the demdex.net domain. This may seem like Adobe is working with an unusual third-party domain, but this is not the case. This section describes the elements in a demdex.net call.
seo-title: Understanding Calls to the Demdex Domain
solution: Audience Manager
title: Comprendre les appels vers le domaine Demdex
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: Reference
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 4%

---

# Comprendre les appels vers le domaine [!DNL Demdex] {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] et le [!DNL Adobe Experience Platform Identity Service] effectuent des appels vers le domaine `demdex.net` et reçoivent des données de ce domaine. Il peut sembler que [!DNL Adobe] travaille avec un domaine tiers inhabituel, mais ce n’est pas le cas. Cette section décrit les éléments d’un appel `demdex.net`.

| Élément d’appel | Description |
|---|---|
| `demdex.net` | Il s’agit d’un domaine hérité contrôlé par [!DNL Adobe]. Il reflète le nom d’origine d’[!DNL Audience Manager] ([!DNL Demdex]) précédant l’acquisition. [!DNL Adobe] a fait l’acquisition de [!DNL Demdex] en 2011 et a rebaptisé la société [!DNL Audience Manager]. Il est difficile de changer ce domaine, car il est étroitement lié à [!DNL Audience Manager], au [!DNL Adobe Experience Cloud ID Service] et à notre base d’utilisateurs installée. D’autres préfixes peuvent être attachés aux appels de `demdex.net` hérités (par exemple, `dcs.demdex.net`, `fast.demdex.net`, etc.). Quel que soit le préfixe, un appel à `something.demdex.net` est toujours un appel à [!DNL Adobe] et non à un domaine tiers inconnu ou suspect. |
| `dpm` | [!DNL DPM] est l’abréviation de [!DNL Data Provider Match]. Il indique aux systèmes [!DNL Adobe] internes qu’un appel de [!DNL Audience Manager] ou de l’[!DNL Adobe Experience Cloud ID Service] transmet des données client pour la synchronisation ou la demande d’un identifiant. Il s’agit de l’appel `demdex.net` le plus courant que vous verrez de [!DNL Audience Manager] ou du [!DNL Adobe Experience Cloud ID Service]. Principes de base des appels <br><br>[!DNL DPM] : <ul><li>[!DNL Audience Manager] : un appel [!DNL DPM] de [!DNL Audience Manager] envoie des données au [!DNL Data Collection Servers] et au [!DNL Profile Cache Servers]. Voir [Composants de la collecte de données](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service] : un appel [!DNL DPM] du [!DNL Adobe Experience Cloud ID Service] est une demande d’identifiant visiteur. Voir [Cookies et service d’identités Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=fr) et [Requête et définition d’ID par le service d’identités Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/intro/id-request.html?lang=fr).</li></ul><br>Remarque : [!DNL Adobe Experience Cloud ID Service] clients peuvent modifier le préfixe [!DNL DPM] dans le nom de domaine. Voir [audienceManager Server et audienceManagerServerSecure](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/subdomain-config.html?lang=fr). |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr)
>* [Cookies Audience Manager](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html?lang=fr)
