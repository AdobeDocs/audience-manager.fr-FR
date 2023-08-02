---
description: Décrit les exigences d’authentification et le formatage du texte utilisé dans la documentation du DIL de niveau classe.
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: Prise en main des API DIL au niveau de la classe
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 8%

---

# Prise en main des API DIL au niveau de la classe{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>Depuis juillet 2023, l’Adobe a cessé de développer la [!DNL Data Integration Library (DIL)] et la variable [!DNL DIL] extension .
>
>Les clients existants peuvent continuer à utiliser leurs [!DNL DIL] implémentation. Cependant, l’Adobe ne se développera pas. [!DNL DIL] au-delà de ce point. Les clients sont encouragés à évaluer [SDK Web Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) pour leur stratégie de collecte de données à long terme.
>
>Les clients qui souhaitent mettre en oeuvre de nouvelles intégrations de collecte de données après juillet 2023 doivent utiliser [SDK Web Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) au lieu de .

Les API de DIL de niveau classe vous permettent de créer et d’utiliser des objets d’Audience Manager par programmation. Les API de classe fonctionnent avec les autres fonctions de niveau instance pour définir des valeurs ou renvoyer des données.

## Prise en main des API DIL au niveau de la classe {#get-started}

Décrit les exigences d’authentification et le formatage du texte utilisé au niveau de la classe [!UICONTROL DIL] la documentation.

<!-- 

c_class_start.xml

 -->

Lorsque vous utilisez le niveau de classe [!UICONTROL DIL] API :

* L’accès nécessite un nom de partenaire et un identifiant d’espace de noms de conteneur (NSID). Contactez votre gestionnaire de compte d’Audience Manager pour obtenir ces informations.
* Remplacer un exemple *italicized* texte dans la documentation de l’API avec la valeur, l’identifiant ou une autre variable, comme requis par la méthode que vous utilisez.
* [!UICONTROL DIL] écrit des données codées dans un cookie de destination. Par exemple, les espaces sont codés comme `%20` et points-virgules comme `%3B`.
