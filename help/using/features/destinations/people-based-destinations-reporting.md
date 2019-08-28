---
description: 'Les destinations basées sur les personnes introduisent la notion d''audiences partageables à Audience Manager. Cette mesure vous permet de comprendre le nombre d''adresses électroniques hachées que Audience Manager peut partager avec la plateforme de destination. '
seo-description: 'Les destinations basées sur les personnes introduisent la notion d''audiences partageables à Audience Manager. Cette mesure vous permet de comprendre le nombre d''adresses électroniques hachées que Audience Manager peut partager avec la plateforme de destination. '
seo-title: Audiences partageables
solution: Audience Manager
title: Audiences partageables
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# Audiences partageables {#shareable-audiences}

[!DNL People-Based Destinations] donner la notion d [!DNL Shareable Audiences] 'Audience Manager. Cette mesure vous permet de comprendre le nombre d'adresses électroniques hachées que Audience Manager peut partager avec la plateforme de destination.

[!DNL Shareable Audiences] est une mesure qui vous aide à interpréter les données d'audience dans le contexte de [!DNL People-Based Destinations]. Cette mesure est visible dans [!UICONTROL Destinations] la page et dans [!UICONTROL Segment] la page.

## Segmenter les audiences partageables {#segment-shareable-audiences}

La [!DNL Segment Shareable Audience] mesure de la page de segment indique le nombre d'adresses électroniques hachées de la source de données avec les [dpuuid correspondants](../../reference/ids-in-aam.md), qui remplissent également les critères du segment défini dans la période de recherche donnée, étant donné la règle de fusion du profil appliquée à ce dernier et qu'Audience Manager peut partager avec la plateforme de destination.

Cette mesure a une période d'affichage de 1 jour. Cela vous permet de comprendre la portée du public pour le segment dans une destination spécifique.

## Public partageable de destination {#destination-shareable-audience}

La [!DNL Destination Shareable Audience] mesure dans une page de destination basée sur people indique le nombre total d'adresses électroniques hachées issues de la source de données avec des [DPUUID correspondants](../../reference/ids-in-aam.md), qu'Audience Manager peut partager avec la plateforme de destination, de tous les segments mappés à cette destination.

![partable-audiences](assets/dest-shareable-audiences.png)

Cette mesure a une période de consultation de durée de vie. Vous pouvez ainsi comprendre l'échelle de l'audience que vous pouvez atteindre à partir de la source de données hachée.

## Exemple

Un client Audience Manager possède une source de données avec 1 000 [dpuuid](../../reference/ids-in-aam.md) (ID de gestion de la relation client). Ils assimilent 100 000 adresses électroniques hachées dans Audience Manager, pour les utiliser avec plusieurs destinations basées sur des personnes et effectuer une synchronisation des identifiants pour les 100 000 adresses électroniques hachées par rapport aux identifiants de la gestion de la relation client. Le client peut utiliser la [!DNL All Cross-Device Profiles] règle de fusion pour créer trois segments d'audience :

* Segment A dont le nombre de population est de 10 000, mappé à la destination A ;
* Segment B avec un nombre de population de 20 000, associé à la destination A ;
* Segment C avec un nombre de population de 50 000, associé à la destination B.

Dans ce scénario :

* Segment A Shareable Audience = 10 000 ;
* Segment B partagé = 20 000 ;
* Segment C partageable = 50 000 ;
* Destination A Public partageable = Segment A Audience partageable + Segment B public partagé = 30 000 ;
* Audience partageable B = Segment C Public partageable = 50 000.

![shareable-audiences-diagram](assets/shareable-audiences.png)

> [!NOTE]
>
> Dans l'exemple ci-dessus, cela ne signifie pas que toutes les adresses électroniques hachées des trois segments correspondent aux comptes existants des plateformes de destination. Cela signifie qu'Audience Manager envoie les identifiants hachés des trois segments à leurs destinations respectives. Lors de l'envoi de segments d'audience aux destinations basées sur des utilisateurs, la correspondance d'audience se produit côté partenaire. La destination A peut avoir jusqu'à 30 000 comptes d'utilisateurs correspondants, alors que la destination B peut avoir jusqu'à 50 000 comptes d'utilisateurs correspondants, mais il n'y a aucune garantie de taux de correspondance. Adobe n'a pas accès aux mesures spécifiques aux partenaires. Voir Taux [de correspondance](../../faq/faq-people-based-destinations.md#match-rates) des questions fréquentes sur la visibilité des destinations basées sur People dans les taux de correspondance.
