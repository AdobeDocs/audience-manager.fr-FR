---
description: Les destinations basées sur les personnes présentent la notion d’audiences partageables à l’Audience Manager. Cette mesure vous aide à comprendre le nombre d’adresses électroniques hachées que l’Audience Manager peut partager avec la plateforme de destination.
seo-description: People-Based Destinations introduce the notion of Shareable Audiences to Audience Manager. This metric helps you understand how many of the hashed email addresses Audience Manager can share with the destination platform.
seo-title: Shareable Audiences
solution: Audience Manager
title: Audiences partageables
feature: People-based Destinations
exl-id: 2860c105-1091-4779-bf40-e66faa941af0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 0%

---

# Audiences partageables {#shareable-audiences}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans le présent article n&#39;est un avis juridique. Veuillez consulter votre propre service juridique pour obtenir des conseils juridiques.

[!DNL People-Based Destinations] amenez la notion de [!DNL Shareable Audiences] à l&#39;Audience Manager. Cette mesure vous aide à comprendre le nombre d’adresses électroniques hachées que l’Audience Manager peut partager avec la plateforme de destination.

[!DNL Shareable Audiences] est une mesure qui vous aide à interpréter les données d’audience dans le contexte de [!DNL People-Based Destinations]. Vous pouvez voir cette mesure dans la page [!UICONTROL Destinations] et dans la page [!UICONTROL Segment].

## Audiences partageables de segments {#segment-shareable-audiences}

La mesure [!DNL Segment Shareable Audience] de la page de segment indique le nombre d’adresses électroniques hachées de la source de données avec les [DPUUIDs](../../reference/ids-in-aam.md) correspondants, qui remplissent également les critères pour le segment défini pendant la période d’analyse donnée, étant donné la règle de fusion de profils qui lui est appliquée, et cette Audience Manager peut partager avec la plateforme de destination.

Cette mesure comporte une période de recherche en amont d’un jour. Vous pouvez ainsi comprendre la portée de l’audience pour le segment dans une destination spécifique.

## Audience partagée de destination {#destination-shareable-audience}

La mesure [!DNL Destination Shareable Audience] d’une page de destination basée sur les personnes indique le nombre total d’adresses électroniques hachées de la source de données avec les [DPUUIDs](../../reference/ids-in-aam.md) correspondants, que l’Audience Manager peut partager avec la plateforme de destination, de tous les segments mappés à cette destination.

![shareable-audiences](assets/dest-shareable-audiences.png)

Cette mesure a une période de recherche en amont de la durée de vie. Vous pouvez ainsi comprendre l’échelle de l’audience que vous pouvez atteindre à partir de la source de données des adresses électroniques hachées.

## Exemple

Un client d’Audience Manager dispose d’une source de données avec 110 000 [DPUUIDs](../../reference/ids-in-aam.md) (ID de gestion de la relation client). Ils ingèrent 100 000 adresses électroniques hachées en Audience Manager, les utilisent avec plusieurs destinations basées sur les personnes et effectuent une synchronisation des identifiants pour les 100 000 adresses électroniques hachées par rapport aux identifiants CRM. Le client peut utiliser la règle de fusion [!DNL All Cross-Device Profiles] pour créer trois segments d’audience :

* Segment A avec un décompte de population de 10 000, mappé à la destination A ;
* Segment B avec un décompte de population de 20 000, mappé à la destination A ;
* Segment C avec un nombre de population de 50 000, mappé à la destination B.

Dans ce scénario :

* Segmenter Une Audience Partagée = 10 000 ;
* Segment B Audience partagée = 20 000 ;
* Segment C Audience partagée = 50 000 ;
* Destination A Audience Partagée = Segment A Audience Partagée + Segment B Audience Partable = 30 000 ;
* Audience partagée destination B = Segment C Audience partagée = 50 000.

![shareable-audiences-diagramme](assets/shareable-audiences.png)

>[!NOTE]
>
>Dans l’exemple ci-dessus, cela ne signifie pas que les 80 000 adresses électroniques hachées des trois segments correspondent aux comptes existants dans les plateformes de destination. Cela signifie uniquement que l’Audience Manager envoie les identifiants hachés des trois segments vers leurs destinations respectives. Lors de l’envoi de segments d’audience vers des destinations basées sur des personnes, la mise en correspondance de l’audience se fait côté partenaire. La destination A peut comporter jusqu’à 30 000 comptes utilisateur correspondants, tandis que la destination B peut en avoir jusqu’à 50 000, mais il n’y a aucune garantie de taux de correspondance. Adobe n’a pas accès aux mesures spécifiques aux partenaires. Voir [Taux de correspondance](../../faq/faq-people-based-destinations.md#match-rates) pour consulter les questions fréquentes sur la visibilité des destinations basées sur les personnes dans les taux de correspondance.
