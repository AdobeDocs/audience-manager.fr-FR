---
description: Décrit les exigences d’authentification et la mise en forme du texte utilisées dans la documentation de DIL au niveau de la classe.
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: Prise en main des API DIL au niveau de la classe
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
TQID: https://experienceleague.adobe.com/RlkKHc2IuInFWfWOnTKS94XhBmbDbQYjtQZI40DsU-8
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a8b0238e-1d43-4679-a3b4-5ba1bad83baaid: b82b475d-1e7d-46c6-9172-1f9c73004b11id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2: id: d7e573ad-4eda-46ec-90c4-239e75362af9
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 203
ht-degree: 0%

---

# Prise en main des API DIL au niveau de la classe{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>Depuis juillet 2023, Adobe a interrompu le développement du [!DNL Data Integration Library (DIL)] et de l’extension [!DNL DIL].
>
>Les clients existants peuvent continuer à utiliser leur implémentation [!DNL DIL]. Cependant, Adobe ne développera pas d’[!DNL DIL] au-delà de ce point. Nous recommandons aux clients d’évaluer [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) pour leur stratégie de collecte de données à long terme.
>
>Les clients qui souhaitent implémenter de nouvelles intégrations de collecte de données après juillet 2023 doivent utiliser [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) à la place.

Les API DIL de niveau classe vous permettent de créer et d’utiliser des objets Audience Manager par programmation. Les API au niveau de la classe fonctionnent avec les autres fonctions au niveau de l’instance pour définir des valeurs ou renvoyer des données.

## Prise en main des API DIL au niveau de la classe {#get-started}

Décrit les exigences d’authentification et la mise en forme du texte utilisés dans la documentation de [!UICONTROL DIL] au niveau de la classe.

<!-- 

c_class_start.xml

 -->

Lorsque vous utilisez les API [!UICONTROL DIL] au niveau de la classe :

* Access nécessite un nom de partenaire et un identifiant d&#39;espace de noms de conteneur (NSID). Contactez votre gestionnaire de compte Audience Manager pour obtenir ces informations.
* Remplacez tout exemple de texte *en italique* dans la documentation de l’API par la valeur, l’ID ou une autre variable, selon les besoins de la méthode que vous utilisez.
* [!UICONTROL DIL] écrit les données codées dans un cookie de destination. Par exemple, les espaces sont codés en `%20` et les points-virgules en `%3B`.
