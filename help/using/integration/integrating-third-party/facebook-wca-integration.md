---
description: Cette page illustre le processus de création de pixels d’audiences personnalisées du site web Facebook (WCA) dans le but d’envoyer des segments d’audience d’Audience Manager basés sur le web à Facebook, à des fins de ciblage des publicités en ligne avec une transparence améliorée.
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Intégration Facebook WCA
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 4%

---

# [!DNL Facebook WCA] Analytics {#facebook-wca-integration}

Cette page illustre le processus de création [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) pixels dans le but d’envoyer du contenu web [!DNL Audience Manager] segments ciblés vers [!DNL Facebook], pour le ciblage des publicités en ligne avec une meilleure transparence.

## Présentation {#overview}

[Audiences personnalisées du site web facebook (WCA)](https://www.facebook.com/business/help/449542958510885) vous permet de créer une liste des personnes qui ont consulté certaines pages ou effectué certaines actions sur votre site web. [!DNL Audience Manager] active l’activation dans [!DNL WCA] using [!DNL URL] destinations, avec lesquelles vous pouvez configurer une intégration personnalisée basée sur les pixels pour envoyer des audiences web à [!DNL Facebook] pour le ciblage.

![Intégration Facebook WCA](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Cette fonctionnalité requiert que vous sélectionniez [!UICONTROL Website] l’option audience pour les plateformes sociales dans [Destinations d’URL](/help/using/features/destinations/create-url-destination.md). Les plateformes sociales exigent que les informations des référents soient démasquées lorsqu’elles sont envoyées à leur plateforme. Sachez que cela signifie que la plateforme/le partenaire de destination pourra voir les informations dans votre référent. [!DNL URL].

## Conditions préalables {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segments, prêts à être affectés à votre nouvelle [!DNL Facebook] destination. Voici [comment créer un segment](/help/using/features/segments/segment-builder.md) dans le [!DNL Audience Manager] Interface utilisateur.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Version 4.1.0 ou ultérieure. Téléchargez la version la plus récente **[ici](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) version 9.0 ou ultérieure, téléchargeable à partir de **[here](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Si vous utilisez [Transfert côté serveur (SSF)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) pour importer des données dans [!DNL Audience Manager], vous devez utiliser AppMeasurement version 2.12 ou ultérieure. Télécharger [!DNL AppMeasurement] en utilisant la variable [Gestionnaire de code Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html).

Nous vous recommandons d’installer ou de mettre à niveau les bibliothèques des étapes 3 et 4 en utilisant [Balises Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html).

## Étape 1 - Création d’une [!UICONTROL Facebook Destination] in [!DNL Audience Manager] {#step-1-create-facebook-destination}

Créer [!UICONTROL URL Destination] in [!DNL Audience Manager] et nommez-le [!DNL Facebook Website Custom Audiences]. Utilisez les paramètres ci-dessous lors de la création de la destination. Vous pouvez également consulter la section [Configuration d’une destination d’URL](/help/using/features/destinations/create-url-destination.md) page.

### Informations fondamentales

* **[!UICONTROL Category]**: Personnalisé
* **[!UICONTROL Type]**: [!DNL URL]
* Sélectionnez la **[!UICONTROL Auto-fill Destination Mapping]** , puis sélectionnez **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Sélectionner l’option **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Cette étiquette d’exportation empêche l’inclusion dans les segments des données et données tierces dérivées des graphiques d’appareil.

### Configuration

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. En sélectionnant [!UICONTROL URL Type] option, [!DNL Audience Manager] n’obscurcit pas le référent ; [!DNL URL] informations lors du déclenchement d’une [!DNL Facebook WCA] pixel.
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* Dans le **[!UICONTROL Base URL]** et **[!UICONTROL Secure URL]** , saisissez la [!DNL Facebook WCA] pixel.
* **[!UICONTROL Delimiter]**: `,`

Base [!DNL URL] exemple : `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Exemple de pixel déclenché à partir de la page. Cet exemple montre un utilisateur qui a droit à trois [!DNL Audience Manager] avec les identifiants 3401321, 2993399, 3263410 :

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Paramètre | Description |
|---------|----------|
| `id` | Votre [!DNL Facebook] ID de pixel, que vous pouvez trouver dans la variable [!DNL Facebook Ad Manager] l’interface utilisateur lors de la création des pixels d’audience. |
| `ev` | Event.     Il s’agit d’une valeur arbitraire qui apparaîtra dans la variable [!DNL Facebook Ad Manager] une fois que le pixel a commencé à se déclencher sur le site. Voir [!UICONTROL Include] élément dans [Étape 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience), pour plus d’informations. |
| `cd[segID]` | Un autre paramètre, qui commence à apparaître dans la variable [!DNL Facebook Ad Manager] une fois que le pixel a commencé à se déclencher sur le site. `segID` est également arbitraire. |
| `%ALIAS%` | Un [!DNL Audience Manager] qui sera remplacée dynamiquement par la fonction [!DNL Audience Manager] [!UICONTROL segment] ID pour lesquels le visiteur du site est admissible, délimités par une virgule , |

Votre [!UICONTROL URL destination] La configuration doit se présenter comme dans l’image ci-dessous :

![Configuration de la destination](/help/using/integration/assets/facebook-wca.png)

Enregistrez le [!UICONTROL destination]. Vous pouvez ensuite passer à la **Mappages de segments** étape .

## Étape 2 - Mappages de segments - Mapper le segment à la destination {#step-2-segment-mappings}

Dans le [Configuration de la destination de l’URL](/help/using/features/destinations/create-url-destination.md) , mappez le segment applicable à votre nouveau processus [!UICONTROL destination]. Notez que la valeur de mappage est automatiquement renseignée avec la variable [!DNL Audience Manager] [!UICONTROL segment ID].

Saisissez une date de fin, le cas échéant, ou laissez vide pour aucune date de fin.

## Étape 3 - Créez une [!UICONTROL Audience] dans [!DNL Facebook Ads Manager] {#step-3-create-audience}

Voir [Création d’une audience personnalisée de site web](https://www.facebook.com/business/help/666509013483225) dans le [!DNL Facebook] documentation d’aide. Sélectionnez la [!UICONTROL Create Audience] options du tableau ci-dessous :

| Élément | Description |
|---------|----------|
| Trafic du site web | Combinaison personnalisée |
| Inclure | <ul><li>Sélectionner **[!UICONTROL Event]** > Sélectionner **[!UICONTROL Adobe-Audience-Manager-Segment]**. Il s’agissait de la valeur de la variable `ev` dans l’exemple de pixel à l’étape 1. Notez que si le pixel n’est pas encore déclenché, la variable **[!UICONTROL Event]** ou **[!UICONTROL Adobe-Audience-Manager-Segment]** peut ne pas apparaître dans la variable [!DNL Facebook] de l’interface utilisateur.</li><li>Ajoutez un paramètre : Sélectionner `segID`.</li><li><p>Sélectionnez la **contains** de l’opérateur.</p><p>Ceci est important, car les visiteurs peuvent être inclus dans plusieurs segments. Il peut y avoir plusieurs segments. [!UICONTROL segment IDs] dans le paramètre pixel . Utiliser les valeurs égales (`=`) peut ne pas qualifier vos visiteurs pour l’audience et vous constaterez un volume plus faible.</p></li><li>Ajoutez une valeur : Saisissez le [!DNL Audience Manager] identifiant du segment.</li></ul> |
| Ajouter une nouvelle condition | Paramètre facultatif. |
| Dans le dernier | Paramètre facultatif. |
| Nom de l’audience | Nous vous recommandons d’utiliser la même [!DNL Audience Manager] nom du segment pour assurer la cohérence, sauf si vous ajoutez des conditions supplémentaires à cette audience. |

## Étape 4 - Attribution de la variable [!UICONTROL Audience] à [!UICONTROL Campaign] in [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Après avoir créé la variable [!DNL Custom Audience], affectez-le à une campagne publicitaire. Créez une campagne ou modifiez une campagne existante. L’audience que vous venez de créer est alors répertoriée dans la section [!DNL Facebook] de l’interface utilisateur. Votre campagne publicitaire ciblera les utilisateurs qui ont vu le pixel près de leur navigateur lors de leur visite sur votre site, si [!DNL Audience Manager] les inclut dans le segment .

## Résumé {#summary}

Maintenant que vous avez attribué votre [!DNL Audience Manager] vers le [!DNL Facebook WCA] destination, [!DNL Audience Manager] déclenche de manière sélective la variable [!DNL Facebook WCA] aux utilisateurs d’un segment donné avec l’identifiant de segment correspondant dans le pixel pour renseigner la variable [!DNL Facebook Audience]. Cela se traduit par une augmentation progressive des [!DNL Facebook Audience] plus la balise est déclenchée vers l’audience applicable sur votre site.

>[!NOTE]
>
> Si un utilisateur abandonne la fonction [!DNL Audience Manager] , il n’existe actuellement aucun moyen pour [!DNL Audience Manager] informer [!DNL Facebook] pour supprimer l’utilisateur de l’événement [!DNL Custom Audience].
