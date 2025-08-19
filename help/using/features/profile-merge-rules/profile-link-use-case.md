---
description: Recommandations et cas d’utilisation pour le reciblage de segment et la qualification de segment personnalisée avec le graphique d’appareil Profile Link.
seo-description: Recommendations and use cases for segment retargeting and personalized segment qualification with the Profile Link device graph.
seo-title: Profile Link Device Graph Use Cases
solution: Audience Manager
title: Cas D’Utilisation Du Graphique D’Appareil Profile Link
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge
exl-id: 8712d02f-c431-4116-8807-41f9e2dda44c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 4%

---

# Cas D’Utilisation Du Graphique D’Appareil Profile Link {#profile-link-device-graph-use-cases}

Recommandations et cas d’utilisation pour le reciblage de segment et la qualification de segment personnalisée avec le [!UICONTROL Profile Link Device Graph].

## Recommandations {#recommendations}

Tenez compte du graphique d’appareil [!UICONTROL Profile Link] pour les campagnes qui :

* Disposent d’un haut niveau d’authentification pour leurs propriétés numériques. Utilisez une option [graphique d’appareil externe](merge-rule-definitions.md#device-options) si vous disposez d’un petit nombre d’utilisateurs authentifiés.
* Exiger un ciblage précis des audiences connues. Le [!UICONTROL Profile Link Device Graph] est créé à l’aide de données authentifiées propriétaires.
* Ciblez les audiences connues sur leurs états authentifié et non authentifié en temps réel.

![](assets/merge-rule-triangle2.png)

## Ciblage sur l’ensemble des appareils {#cross-device-personalization}

Imaginons que John possède trois appareils qu’il utilise régulièrement pour rechercher des offres de forfaits vacances : son ordinateur portable ([!DNL Device 1]), son smartphone ([!DNL Device 2]) et sa tablette ([!DNL Device 3]). Cependant, John utilise ses appareils pour rechercher différents articles des offres groupées :

* Il utilise son ordinateur portable pour rechercher des vols ;
* Il utilise son smartphone pour rechercher des hôtels ;
* Il utilise sa tablette pour rechercher des visites guidées.

Même si John n’est pas authentifié sur les trois appareils mentionnés ci-dessus, en utilisant la règle **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]**, un fournisseur de forfaits vacances peut associer ces appareils au profil authentifié de John, en supposant qu’il ait été la dernière personne à s’authentifier sur les trois appareils.

![last-device-graph](assets/last-device-graph.png)

Comme Audience Manager qualifie chaque profil d’appareil ayant participé à la fusion de profils pour un segment, les trois profils d’appareil sont segmentés. Le [!UICONTROL Profile Link Device Graph] permet à Audience Manager d’examiner le comportement sur les trois appareils et de qualifier chaque appareil pour un segment pour lequel aucun profil d’appareil n’est qualifié seul.

Cette [!UICONTROL Profile Merge Rule] permet aux spécialistes marketing de fournir une expérience cohérente à tous les appareils appartenant à une seule personne, en fonction de l’activité de l’utilisateur et non de l’activité de chaque appareil.

![personnalisation sur l’ensemble des appareils](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [Cas d’utilisation des représentations graphiques externes des appareils](external-graph-use-cases.md)
>* [Cas d’utilisation généraux des stratégies de fusion de profils](merge-rule-targeting-options.md)
>* [FAQ sur les règles de fusion de profil](../../faq/faq-profile-merge.md)
