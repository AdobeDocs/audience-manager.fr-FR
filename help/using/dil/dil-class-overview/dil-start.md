---
description: Décrit les exigences d’authentification et la mise en forme du texte utilisées dans la documentation de DIL au niveau de la classe.
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: Prise en main des API DIL au niveau de la classe
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 0%

---

# Prise en main des API DIL au niveau de la classe{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>Depuis juillet 2023, Adobe a interrompu le développement du [!DNL Data Integration Library (DIL)] et de l’extension [!DNL DIL].
>
>Les clients existants peuvent continuer à utiliser leur implémentation [!DNL DIL]. Cependant, Adobe ne développera pas d’[!DNL DIL] au-delà de ce point. Nous recommandons aux clients d’évaluer [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=fr) pour leur stratégie de collecte de données à long terme.
>
>Les clients qui souhaitent implémenter de nouvelles intégrations de collecte de données après juillet 2023 doivent utiliser [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=fr) à la place.

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
