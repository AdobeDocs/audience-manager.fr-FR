---
description: 'Les Destinations basées sur les personnes introduisent la notion d''Audiences partageables à l''Audience Manager. Cette mesure vous permet de comprendre le nombre d’adresses électroniques hachées que l’Audience Manager peut partager avec la plateforme de destination. '
seo-description: 'Les Destinations basées sur les personnes introduisent la notion d''Audiences partageables à l''Audience Manager. Cette mesure vous permet de comprendre le nombre d’adresses électroniques hachées que l’Audience Manager peut partager avec la plateforme de destination. '
seo-title: Audiences partageables
solution: Audience Manager
title: Audiences partageables
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 1%

---


# Audiences partageables {#shareable-audiences}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonction. Rien dans ce document n&#39;est un conseil juridique. Veuillez consulter votre propre conseiller juridique pour obtenir des conseils juridiques.

[!DNL People-Based Destinations] mettre en Audience Manager la notion d&#39; [!DNL Shareable Audiences] . Cette mesure vous permet de comprendre le nombre d’adresses électroniques hachées que l’Audience Manager peut partager avec la plateforme de destination.

[!DNL Shareable Audiences] est une mesure qui vous aide à interpréter les données d’audience dans le contexte de [!DNL People-Based Destinations]. Vous pouvez afficher cette mesure dans la [!UICONTROL Destinations] page et dans la [!UICONTROL Segment] page.

## Audiences partageables de segments {#segment-shareable-audiences}

La [!DNL Segment Shareable Audience] mesure de la page de segments indique le nombre d’adresses électroniques hachées de la source de données avec des [identifiants](../../reference/ids-in-aam.md)DPUUID correspondants, qui sont également admissibles pour le segment défini au cours de la période de recherche en arrière donnée, compte tenu de la règle de fusion de profil qui y est appliquée, et que cette Audience Manager peut partager avec la plateforme de destination.

Cette mesure a une période de recherche en arrière de 1 jour. Cela vous permet de comprendre la portée de l’audience pour le segment dans une destination spécifique.

## Audience partagée de destination {#destination-shareable-audience}

La [!DNL Destination Shareable Audience] mesure d’une page de destination basée sur les personnes indique le nombre total d’adresses électroniques hachées de la source de données avec des [identifiants](../../reference/ids-in-aam.md)DPUUID correspondants, que l’Audience Manager peut partager avec la plateforme de destination, de tous les segments mappés à cette destination.

![audiences partageables](assets/dest-shareable-audiences.png)

Cette mesure a une période de recherche en amont de durée de vie. Cela vous permet de comprendre l’échelle de l’audience que vous pouvez atteindre à partir de la source de données des adresses électroniques hachées.

## Exemple

Un client d’Audience Manager dispose d’une source de données contenant 110 000 [DPUUID](../../reference/ids-in-aam.md) (CRM ID). Ils assimilent 100 000 adresses électroniques hachées en Audience Manager, pour les utiliser avec plusieurs destinations basées sur des personnes, et effectuent une synchronisation des identifiants pour les 100 000 adresses électroniques hachées par rapport aux identifiants de gestion de la relation client. Le client peut utiliser la règle de [!DNL All Cross-Device Profiles] fusion pour créer trois segments d’audience :

* Segment A avec un nombre de 10 000 habitants, mappé à la destination A ;
* Segment B avec un nombre de 20 000 habitants, mappé à la destination A ;
* Segment C avec un nombre de population de 50 000, mappé à la destination B.

Dans ce scénario :

* Segment A Audience partagée = 10 000 ;
* Segment B Audience partagée = 20 000 ;
* Audience partagée du segment C = 50 000 ;
* Destination A Audience partageable = Segment A Audience partageable + Segment B Audience partagée = 30 000 ;
* Audience partagée de destination B = Audience partagée de segment C = 50 000.

![audiences partageables-diagramme](assets/shareable-audiences.png)

>[!NOTE]
>
>Dans l’exemple ci-dessus, cela ne signifie pas que les 80 000 adresses électroniques hachées des trois segments correspondent aux comptes existants sur les plateformes de destination. Cela signifie uniquement que l’Audience Manager envoie les identificateurs hachés des trois segments vers leurs destinations respectives. Lors de l’envoi de segments d’audience vers des destinations basées sur des personnes, la mise en correspondance des audiences se produit du côté partenaire. La destination A peut comporter jusqu&#39;à 30 000 comptes d&#39;utilisateurs correspondants, tandis que la destination B peut comporter jusqu&#39;à 50 000 comptes d&#39;utilisateurs correspondants, mais il n&#39;y a aucune garantie de taux de correspondance. Adobe n’a pas accès aux mesures spécifiques à un partenaire. Voir Taux [de](../../faq/faq-people-based-destinations.md#match-rates) correspondance pour obtenir des questions fréquentes sur la visibilité des Destinations basées sur les personnes dans les taux de correspondance.
