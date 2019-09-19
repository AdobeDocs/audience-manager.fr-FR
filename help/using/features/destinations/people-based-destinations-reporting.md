---
description: 'Les destinations basées sur les personnes présentent la notion d’audiences partageables dans Audience Manager. Cette mesure vous permet de comprendre le nombre d’adresses électroniques hachées qu’Audience Manager peut partager avec la plateforme de destination. '
seo-description: 'Les destinations basées sur les personnes présentent la notion d’audiences partageables dans Audience Manager. Cette mesure vous permet de comprendre le nombre d’adresses électroniques hachées qu’Audience Manager peut partager avec la plateforme de destination. '
seo-title: Audiences partagées
solution: Audience Manager
title: Audiences partagées
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# Audiences partagées {#shareable-audiences}

[!DNL People-Based Destinations] apportez la notion de [!DNL Shareable Audiences] dans Audience Manager. Cette mesure vous permet de comprendre le nombre d’adresses électroniques hachées qu’Audience Manager peut partager avec la plateforme de destination.

[!DNL Shareable Audiences] est une mesure qui vous aide à interpréter les données d’audience dans le contexte de [!DNL People-Based Destinations]. Vous pouvez voir cette mesure dans la [!UICONTROL Destinations] page et dans la [!UICONTROL Segment] page.

## Segmenter les audiences partageables {#segment-shareable-audiences}

La [!DNL Segment Shareable Audience] mesure dans la page de segments indique le nombre d’adresses électroniques hachées de la source de données avec des [DPUUID](../../reference/ids-in-aam.md)correspondants, qui sont également admissibles pour le segment défini au cours de la période de retour en arrière donnée, compte tenu de la règle de fusion de profil qui y est appliquée, et qu’Audience Manager peut partager avec la plateforme de destination.

Cette mesure a une période de rétrospective de 1 jour. Cela vous permet de comprendre la portée de l’audience pour le segment dans une destination spécifique.

## Audience partagée de destination {#destination-shareable-audience}

La [!DNL Destination Shareable Audience] mesure dans une page de destination basée sur les personnes indique le nombre total d’adresses électroniques hachées de la source de données avec des [DPUUID](../../reference/ids-in-aam.md)correspondants, qu’Audience Manager peut partager avec la plateforme de destination, de tous les segments mappés à cette destination.

![shareable-audiences](assets/dest-shareable-audiences.png)

Cette mesure a une période de recherche en arrière à vie. Cela vous permet de comprendre l’échelle de l’audience que vous pouvez atteindre à partir de la source de données des adresses électroniques hachées.

## Exemple

Un client Audience Manager dispose d’une source de données contenant 110 000 [DPUUID](../../reference/ids-in-aam.md) (CRM ID). Ils assimilent 100 000 adresses électroniques hachées dans Audience Manager, pour les utiliser avec plusieurs destinations basées sur des personnes, et effectuent une synchronisation des identifiants pour les 100 000 adresses électroniques hachées par rapport aux identifiants CRM. Le client peut utiliser la règle de [!DNL All Cross-Device Profiles] fusion pour créer trois segments d’audience :

* Segment A avec un nombre de 10 000 habitants, mappé à la destination A;
* Segment B avec un nombre de population de 20 000, mappé à la destination A;
* Segment C avec un nombre de population de 50 000, mappé à la destination B.

Dans ce scénario :

* Segmenter Un Public Partagé = 10 000 ;
* Segment B Audience partagée = 20 000 ;
* Segment C Audience partagée = 50 000 ;
* Destination A Audience Partagée = Segment A Audience Partagée + Segment B Audience Partagée = 30 000 ;
* Destination B Audience partagée = Segment C Audience partagée = 50 000.

![shareable-audiences-diagramme](assets/shareable-audiences.png)

> [!NOTE]
>
> Dans l’exemple ci-dessus, cela ne signifie pas que toutes les 80 000 adresses électroniques hachées des trois segments correspondent aux comptes existants dans les plateformes de destination. Cela signifie uniquement qu’Audience Manager envoie les identifiants de hachage des trois segments vers leurs destinations respectives. Lors de l’envoi de segments d’audience vers des destinations basées sur des personnes, la correspondance d’audience se produit côté partenaire. La destination A peut comporter jusqu’à 30 000 comptes d’utilisateurs correspondants, tandis que la destination B peut avoir jusqu’à 50 000 comptes d’utilisateurs correspondants, mais il n’existe aucune garantie de taux de correspondance. Adobe n’a pas accès aux mesures spécifiques aux partenaires. Voir Taux de [correspondance](../../faq/faq-people-based-destinations.md#match-rates) pour consulter la foire aux questions sur la visibilité des destinations basées sur les personnes dans les taux de correspondance.
