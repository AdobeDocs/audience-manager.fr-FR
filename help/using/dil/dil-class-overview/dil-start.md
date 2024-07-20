---
description: Décrit les exigences d’authentification et le formatage du texte utilisé dans la documentation du DIL de niveau classe.
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: Prise en main des API de DIL au niveau de la classe
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 0%

---

# Prise en main des API de DIL au niveau de la classe{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>Depuis juillet 2023, Adobe a arrêté le développement de l’extension [!DNL Data Integration Library (DIL)] et [!DNL DIL].
>
>Les clients existants peuvent continuer à utiliser leur implémentation [!DNL DIL]. Cependant, l’Adobe ne développera pas [!DNL DIL] au-delà de ce point. Nous recommandons aux clients d’évaluer le [SDK Web Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) pour leur stratégie de collecte de données à long terme.
>
>Les clients qui souhaitent mettre en oeuvre de nouvelles intégrations de collecte de données après juillet 2023 doivent utiliser [SDK Web Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) à la place.

Les API de DIL de niveau classe vous permettent de créer et d’utiliser des objets d’Audience Manager par programmation. Les API de classe fonctionnent avec les autres fonctions de niveau instance pour définir des valeurs ou renvoyer des données.

## Prise en main des API de DIL au niveau de la classe {#get-started}

Décrit les exigences d’authentification et le formatage du texte utilisé dans la documentation de niveau classe [!UICONTROL DIL].

<!-- 

c_class_start.xml

 -->

Lors de l’utilisation des API [!UICONTROL DIL] de niveau classe :

* L’accès nécessite un nom de partenaire et un identifiant d’espace de noms de conteneur (NSID). Contactez votre gestionnaire de compte d’Audience Manager pour obtenir ces informations.
* Remplacez tout exemple de texte *italicized* dans la documentation de l’API par une valeur, un identifiant ou toute autre variable, comme requis par la méthode que vous utilisez.
* [!UICONTROL DIL] écrit des données codées dans un cookie de destination. Par exemple, les espaces sont codés en tant que `%20` et les points-virgules comme `%3B`.
