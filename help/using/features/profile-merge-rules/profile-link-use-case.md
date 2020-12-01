---
description: Recommendations et utilisation de cas pour le reciblage de segments et la qualification de segment personnalisée avec le graphique de périphérique Lien de Profil.
seo-description: Recommendations et utilisation de cas pour le reciblage de segments et la qualification de segment personnalisée avec le graphique de périphérique Lien de Profil.
seo-title: Cas d’utilisation des représentations graphiques des appareils Profile Link
solution: Audience Manager
title: Cas d’utilisation des représentations graphiques des appareils Profile Link
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 9%

---


# Cas d’utilisation des représentations graphiques des appareils Profile Link {#profile-link-device-graph-use-cases}

Recommendations et cas d’utilisation pour le reciblage de segments et la qualification de segment personnalisée avec le [!UICONTROL Profile Link Device Graph].

## Recommandations {#recommendations}

Examinez le graphique de périphérique [!UICONTROL Profile Link] pour les campagnes qui :

* Posséder un niveau élevé d’authentification sur l’ensemble de leurs propriétés numériques. Utilisez une option [graphique de périphérique externe](merge-rule-definitions.md#device-options) si vous avez un petit nombre d&#39;utilisateurs authentifiés.
* Exiger un ciblage précis des audiences connues. [!UICONTROL Profile Link Device Graph] est créé à l’aide de données authentifiées propriétaires.
* Cible d’audiences connues dans leurs états authentifiés et non authentifiés en temps réel.

![](assets/merge-rule-triangle2.png)

## Ciblage sur plusieurs périphériques {#cross-device-personalization}

Disons que John possède trois appareils qu&#39;il utilise régulièrement pour rechercher des forfaits vacances : son ordinateur portable ([!DNL Device 1]), son smartphone ([!DNL Device 2]) et sa tablette ([!DNL Device 3]). Cependant, John utilise ses appareils pour rechercher différents articles des offres spéciales :

* Il utilise son ordinateur portable pour rechercher des vols ;
* Il utilise son smartphone pour rechercher des hôtels ;
* Il utilise sa tablette pour rechercher des visites guidées.

Même si John n&#39;est pas authentifié sur les trois périphériques mentionnés ci-dessus, en utilisant la règle **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]**, un fournisseur de packages de vacances peut associer ces périphériques au profil authentifié de John, en supposant qu&#39;il était la dernière personne à s&#39;authentifier sur les trois périphériques.

![dernier-dispositif-graphique](assets/last-device-graph.png)

Comme l’Audience Manager qualifie chaque profil de périphérique qui a participé à la fusion de profils pour un segment, les trois profils de périphérique sont segmentés. [!UICONTROL Profile Link Device Graph] permet à l&#39;Audience Manager d&#39;examiner le comportement sur les trois périphériques et de qualifier chaque périphérique pour un segment pour lequel aucun profil de périphérique unique ne peut être identifié seul.

Grâce à cette [!UICONTROL Profile Merge Rule] méthode, les marketeurs peuvent proposer une expérience cohérente à tous les périphériques appartenant à une seule personne, en fonction de l’activité de l’utilisateur et non de l’activité de chaque périphérique.

![personnalisation sur plusieurs périphériques](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [Cas d’utilisation des représentations graphiques externes des appareils](external-graph-use-cases.md)
>* [Cas d’utilisation généraux des stratégies de fusion de profils](merge-rule-targeting-options.md)
>* [FAQ sur les règles de fusion de profils](../../faq/faq-profile-merge.md)

