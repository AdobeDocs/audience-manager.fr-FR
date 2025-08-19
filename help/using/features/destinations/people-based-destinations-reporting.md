---
description: Les destinations basées sur les personnes présentent la notion d’audiences partageables à Audience Manager. Cette mesure vous aide à comprendre le nombre d’adresses e-mail hachées qu’Audience Manager peut partager avec la plateforme de destination.
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
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans le présent document n&#39;est un avis juridique. Veuillez consulter votre propre service juridique pour obtenir des conseils juridiques.

[!DNL People-Based Destinations] la notion de [!DNL Shareable Audiences] dans Audience Manager. Cette mesure vous aide à comprendre le nombre d’adresses e-mail hachées qu’Audience Manager peut partager avec la plateforme de destination.

[!DNL Shareable Audiences] est une mesure qui vous aide à interpréter les données d’audience dans le contexte de la [!DNL People-Based Destinations]. Cette mesure est visible dans la page [!UICONTROL Destinations] et dans la page [!UICONTROL Segment].

## Segmenter les audiences partageables {#segment-shareable-audiences}

La mesure [!DNL Segment Shareable Audience] de la page de segment indique le nombre d’adresses e-mail hachées à partir de la source de données avec les [DPUUIDs](../../reference/ids-in-aam.md) correspondants qui remplissent également les critères pour le segment défini au cours de la période d’analyse donnée, compte tenu de la règle de fusion de profil qui lui est appliquée et qu’Audience Manager peut partager avec la plateforme de destination.

Cette mesure comporte une période de recherche en amont d’un jour. Cela vous permet de comprendre la portée de l’audience pour le segment dans une destination spécifique.

## Audience Partageable De Destination {#destination-shareable-audience}

La mesure [!DNL Destination Shareable Audience] dans une page de destination basée sur les personnes indique le nombre total d’adresses e-mail hachées de la source de données avec les [DPUUID](../../reference/ids-in-aam.md) correspondants qu’Audience Manager peut partager avec la plateforme de destination, à partir de tous les segments mappés à cette destination.

![audiences-partageables](assets/dest-shareable-audiences.png)

Cette mesure dispose d’une période de recherche en amont de durée de vie. Cela vous permet de comprendre l’échelle de l’audience que vous pouvez atteindre à partir de la source de données des adresses e-mail hachées.

## Exemple

Un client Audience Manager dispose d’une source de données de 110 000 [DPUUID](../../reference/ids-in-aam.md) (identifiants CRM). Ils ingèrent 100 000 adresses e-mail hachées dans Audience Manager afin de les utiliser avec plusieurs destinations basées sur des personnes et effectuent une synchronisation des identifiants pour les 100 000 adresses e-mail hachées par rapport aux identifiants CRM. Le client peut utiliser la règle de fusion [!DNL All Cross-Device Profiles] pour créer trois segments d’audience :

* le segment A avec un nombre de population de 10 000, mappé à la destination A ;
* le segment B avec un nombre de populations de 20 000, mappé à la destination A ;
* Segment C avec un nombre de population de 50 000, mappé à la destination B.

Dans ce scénario :

* Segment A Audience Partageable = 10 000 ;
* Segment B Audience Partageable = 20 000 ;
* Audience Partageable Du Segment C = 50 000 ;
* Destination A Audience Partageable = Segment A Audience Partageable + Segment B Audience Partageable = 30 000 ;
* Audience Partageable De Destination B = Audience Partageable De Segment C = 50 000.

![diagramme-audiences-partageables](assets/shareable-audiences.png)

>[!NOTE]
>
>Dans l’exemple ci-dessus, cela ne signifie pas que les 80 000 adresses e-mail hachées des trois segments correspondent tous aux comptes existants dans les plateformes de destination. Cela signifie uniquement qu’Audience Manager envoie les identifiants hachés des trois segments vers leurs destinations respectives. Lors de l’envoi de segments d’audience vers des destinations basées sur des personnes, la correspondance d’audience se produit côté partenaire. La destination A peut avoir jusqu’à 30 000 comptes utilisateur correspondants, tandis que la destination B peut avoir jusqu’à 50 000 comptes utilisateur correspondants, mais il n’existe aucune garantie de taux de correspondance. Adobe n’a pas accès aux mesures spécifiques aux partenaires. Consultez [Taux de correspondance](../../faq/faq-people-based-destinations.md#match-rates) pour les questions fréquentes sur la visibilité des destinations basées sur les personnes dans les taux de correspondance.
