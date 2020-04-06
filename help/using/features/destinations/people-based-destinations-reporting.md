---
description: 'Les Destinations basées sur les personnes introduisent la notion de partagé  à  Gestionnaire de. Cette mesure vous permet de comprendre le nombre d’adresses électroniques hachées  Gestionnaire de  de pouvant être partagées avec la plateforme de destination. '
seo-description: 'Les Destinations basées sur les personnes introduisent la notion de partagé  à  Gestionnaire de. Cette mesure vous permet de comprendre le nombre d’adresses électroniques hachées  Gestionnaire de  de pouvant être partagées avec la plateforme de destination. '
seo-title: ' de partage '
solution: Audience Manager
title: ' de partage '
translation-type: tm+mt
source-git-commit: 75fe1e0f7321107930a28e354ca2f4a256a477ac

---


#  de partage {#shareable-audiences}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans ce document n&#39;est un conseil juridique. Veuillez consulter votre propre conseiller juridique pour obtenir des conseils juridiques.

[!DNL People-Based Destinations] apportez la notion de [!DNL Shareable Audiences] à   Manager. Cette mesure vous permet de comprendre le nombre d’adresses électroniques hachées  Gestionnaire de  de pouvant être partagées avec la plateforme de destination.

[!DNL Shareable Audiences] est une mesure qui vous aide à interpréter  données  dans le contexte de [!DNL People-Based Destinations]. Vous pouvez voir cette mesure dans la [!UICONTROL Destinations] page et dans la [!UICONTROL Segment] page.

## Partage de segments  {#segment-shareable-audiences}

La [!DNL Segment Shareable Audience] mesure dans la page de segments indique le nombre d’adresses électroniques hachées de la source de données avec des [identifiants DPUUID](../../reference/ids-in-aam.md)correspondants, qui sont également admissibles pour le segment défini dans la période de retour en arrière donnée, compte tenu de la règle de fusion de  de appliquée sur celle-ci, et que  Gestionnaire de  de peut partager avec la plateforme de destination.

Cette mesure a une période de rétrospective d’un jour. Cela vous permet de comprendre la portée   du segment dans une destination spécifique.

## Partage  destination {#destination-shareable-audience}

La [!DNL Destination Shareable Audience] mesure dans une page de destination basée sur les personnes indique le nombre total d’adresses électroniques hachées de la source de données avec des [DPUUID](../../reference/ids-in-aam.md)correspondants, que  Gestionnaire de  de peut partager avec la plateforme de destination, de tous les segments mappés à cette destination.

![partageable-](assets/dest-shareable-audiences.png)

Cette mesure a une période de recherche en arrière à vie. Cela vous permet de comprendre l’échelle du  que vous pouvez atteindre à partir de la source de données des adresses électroniques hachées.

## Exemple

Un client   Manager dispose d’une source de données avec 110 000 [DPUUID](../../reference/ids-in-aam.md) (CRM ID). Ils assimilent 100 000 adresses électroniques hachées dans  Gestionnaire de  de, pour les utiliser avec plusieurs destinations basées sur des personnes, et effectuent une synchronisation des identifiants pour les 100 000 adresses électroniques hachées par rapport aux identifiants de gestion de la relation client. Le client peut utiliser la règle de [!DNL All Cross-Device Profiles] fusion pour créer trois segments  de  :

* Segment A avec un nombre de 10 000 habitants, mappé à la destination A;
* Segment B avec un nombre de population de 20 000, mappé à la destination A;
* Segment C avec un nombre de population de 50 000, mappé à la destination B.

Dans ce scénario :

* Segment A Partager   = 10 000;
* Segment B Partager   = 20 000;
* Segment C Partager   = 50 000;
* Destination A  Partager  = Segment A Partager Un  + Segment B Partager = 30 000 ;
* Destination B Partager   = Segment C Partager  = 50 000.

![partagé--diagramme](assets/shareable-audiences.png)

>[!NOTE]
>
>Dans l’exemple ci-dessus, cela ne signifie pas que toutes les 80 000 adresses électroniques hachées des trois segments correspondent aux comptes existants dans les plateformes de destination. Cela signifie uniquement que  Gestionnaire de  de envoie les identifiants de hachage des trois segments vers leurs destinations respectives. Lors de l’envoi de segments   vers des destinations basées sur des personnes, la correspondance des  se produit côté partenaire. La destination A peut comporter jusqu’à 30 000 comptes d’utilisateurs correspondants, tandis que la destination B peut avoir jusqu’à 50 000 comptes d’utilisateurs correspondants, mais il n’existe aucune garantie de taux de correspondance. Adobe n’a pas accès aux mesures spécifiques aux partenaires. Voir Taux de [correspondance](../../faq/faq-people-based-destinations.md#match-rates) pour consulter la foire aux questions sur la visibilité des Destinations basées sur les personnes dans les taux de correspondance.
