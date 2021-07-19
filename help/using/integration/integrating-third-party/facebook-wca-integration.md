---
description: Cette page illustre le processus de création de pixels d’audiences personnalisées du site web Facebook (WCA) dans le but d’envoyer des segments d’audience d’Audience Manager basés sur le web à Facebook, à des fins de ciblage des publicités en ligne avec une transparence améliorée.
seo-description: Cette page illustre le processus de création de pixels d’audiences personnalisées du site web Facebook (WCA) dans le but d’envoyer des segments d’audience d’Audience Manager basés sur le web à Facebook, à des fins de ciblage des publicités en ligne avec une transparence améliorée.
seo-title: Intégration Facebook WCA
solution: Audience Manager
title: Intégration Facebook WCA
feature: Intégration tierce
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 5%

---

# [!DNL Facebook WCA] Analytics {#facebook-wca-integration}

Cette page illustre le processus de création de [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) pixels dans le but d’envoyer des segments d’audience [!DNL Audience Manager] web à [!DNL Facebook], pour le ciblage des publicités en ligne avec une transparence améliorée.

## Présentation {#overview}

[Les audiences personnalisées du site web facebook (WCA)](https://www.facebook.com/business/help/449542958510885) vous permettent de créer une liste des personnes qui ont consulté certaines pages ou entrepris des actions particulières sur votre site web. [!DNL Audience Manager] active l’activation dans  [!DNL WCA] à l’aide de  [!DNL URL] destinations, avec lesquelles vous pouvez configurer une intégration pixel personnalisée pour envoyer des audiences web à  [!DNL Facebook] pour le ciblage.

![Intégration Facebook WCA](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Cette fonctionnalité requiert que vous sélectionniez l’option [!UICONTROL Website] audience pour les plateformes sociales dans [Destinations d’URL](/help/using/features/destinations/create-url-destination.md). Les plateformes sociales exigent que les informations des référents soient démasquées lorsqu’elles sont envoyées à leur plateforme. Sachez que cela signifie que la plateforme/le partenaire de destination pourra voir les informations dans votre référent [!DNL URL].

## Conditions préalables {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segments, prêts à être affectés à votre nouvelle  [!DNL Facebook] destination. Voici [comment créer un segment](/help/using/features/segments/segment-builder.md) dans l’interface utilisateur de [!DNL Audience Manager].
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Version 4.1.0 ou ultérieure. Téléchargez la version la plus récente **[ici](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) version 9.0 ou ultérieure, téléchargeable  **[ici](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Si vous utilisez [Transfert côté serveur (SSF)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) pour importer des données dans [!DNL Audience Manager], vous devez utiliser AppMeasurement version 2.12 ou ultérieure. Téléchargez [!DNL AppMeasurement] à l’aide du [Gestionnaire de code Analytics](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html).

Nous vous recommandons d’installer ou de mettre à niveau les bibliothèques des étapes 3 et 4 à l’aide de [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html).

## Étape 1 - Créer une [!UICONTROL Facebook Destination] dans [!DNL Audience Manager] {#step-1-create-facebook-destination}

Créez un [!UICONTROL URL Destination] dans [!DNL Audience Manager] et nommez-le [!DNL Facebook Website Custom Audiences]. Utilisez les paramètres ci-dessous lors de la création de la destination. Vous pouvez également vous reporter à la page [Configuration d’une destination d’URL](/help/using/features/destinations/create-url-destination.md) .

### Informations fondamentales

* **[!UICONTROL Category]**: Personnalisé
* **[!UICONTROL Type]**:  [!DNL URL]
* Cochez la case **[!UICONTROL Auto-fill Destination Mapping]**, puis sélectionnez **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Sélectionnez l’option **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Cette étiquette d’exportation empêche l’inclusion dans les segments des données et données tierces dérivées des graphiques d’appareil.

### Configuration

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. En sélectionnant cette option [!UICONTROL URL Type] , [!DNL Audience Manager] n’obscurcit pas les informations du référent [!DNL URL] lors du déclenchement d’un pixel [!DNL Facebook WCA].
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* Dans les champs **[!UICONTROL Base URL]** et **[!UICONTROL Secure URL]**, saisissez le pixel [!DNL Facebook WCA].
* **[!UICONTROL Delimiter]**:  `,`

Exemple [!DNL URL] de base : `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Exemple de pixel déclenché à partir de la page. Cet exemple présente un utilisateur qui est admissible pour trois segments [!DNL Audience Manager], avec les ID 3401321, 2993399, 3263410 :

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Paramètre | Description |
|---------|----------|
| `id` | Votre [!DNL Facebook] ID de pixel, que vous pouvez trouver dans l’interface utilisateur [!DNL Facebook Ad Manager] lors de la création de pixels d’audience. |
| `ev` | Event.     Il s’agit d’une valeur arbitraire qui apparaîtra dans l’interface utilisateur [!DNL Facebook Ad Manager] une fois que le pixel commencera à se déclencher sur le site. Voir l’élément [!UICONTROL Include] dans [Étape 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience) pour plus d’informations. |
| `cd[segID]` | Paramètre supplémentaire qui commence à être renseigné dans l’interface utilisateur [!DNL Facebook Ad Manager] une fois que le pixel commence à se déclencher sur le site. `segID` est également arbitraire. |
| `%ALIAS%` | macro [!DNL Audience Manager] qui sera remplacée dynamiquement par les [!DNL Audience Manager] [!UICONTROL segment] identifiants auxquels le visiteur du site est admissible, délimités par des virgules , |

Votre configuration [!UICONTROL URL destination] doit ressembler à l’image ci-dessous :

![Configuration de la destination](/help/using/integration/assets/facebook-wca.png)

Enregistrez le [!UICONTROL destination]. Vous pouvez ensuite passer à l’étape **Mappages de segments** .

## Étape 2 - Mappages de segments - Mapper le segment à la destination {#step-2-segment-mappings}

Dans le workflow [Configurer la destination de l’URL](/help/using/features/destinations/create-url-destination.md), mappez le segment applicable à votre [!UICONTROL destination] nouvellement créé. Notez que la valeur de mappage est automatiquement renseignée avec la valeur [!DNL Audience Manager] [!UICONTROL segment ID].

Saisissez une date de fin, le cas échéant, ou laissez vide pour aucune date de fin.

## Étape 3 - Créer un [!UICONTROL Audience] dans [!DNL Facebook Ads Manager] {#step-3-create-audience}

Voir [Création d’un site Web Audience personnalisée](https://www.facebook.com/business/help/666509013483225) dans la [!DNL Facebook] documentation d’aide. Sélectionnez les options [!UICONTROL Create Audience] dans le tableau ci-dessous :

| Élément | Description |
|---------|----------|
| Trafic du site web | Combinaison personnalisée |
| Inclure | <ul><li>Sélectionnez **[!UICONTROL Event]** > Sélectionner **[!UICONTROL Adobe-Audience-Manager-Segment]**. Il s’agit de la valeur du paramètre `ev` dans l’exemple de pixel de l’étape 1. Notez que si le pixel doit encore se déclencher, l’option **[!UICONTROL Event]** ou **[!UICONTROL Adobe-Audience-Manager-Segment]** peuvent ne pas apparaître dans l’interface utilisateur [!DNL Facebook].</li><li>Ajoutez un paramètre : Sélectionnez `segID`.</li><li><p>Sélectionnez l’opérateur **contains** .</p><p>Ceci est important, car les visiteurs peuvent être inclus dans plusieurs segments. Il peut y avoir plusieurs [!UICONTROL segment IDs] dans le paramètre de pixel. L’utilisation de l’opérateur égal (`=`) peut ne pas qualifier vos visiteurs pour l’audience et vous constaterez un volume inférieur.</p></li><li>Ajoutez une valeur : Saisissez l’identifiant du segment [!DNL Audience Manager].</li></ul> |
| Ajouter une nouvelle condition | Paramètre facultatif. |
| Dans le dernier | Paramètre facultatif. |
| Nom de l’audience | Nous vous recommandons d’utiliser le même nom de segment [!DNL Audience Manager] pour assurer la cohérence, sauf si vous ajoutez des conditions supplémentaires à cette audience. |

## Étape 4 - Attribuer la balise [!UICONTROL Audience] à une [!UICONTROL Campaign] dans [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Après avoir créé la balise [!DNL Custom Audience], affectez-la à une campagne publicitaire. Créez une nouvelle campagne ou éditez une campagne existante. L&#39;audience que vous venez de créer est répertoriée dans l&#39;interface utilisateur [!DNL Facebook]. Votre campagne publicitaire ciblera les utilisateurs qui ont vu le pixel se déclencher sur leur navigateur lors de leur visite sur votre site, si [!DNL Audience Manager] les inclut dans le segment.

## Résumé {#summary}

Maintenant que vous avez attribué votre segment [!DNL Audience Manager] à la destination [!DNL Facebook WCA], [!DNL Audience Manager] déclenche de manière sélective le pixel [!DNL Facebook WCA] aux utilisateurs d’un segment donné avec l’identifiant de segment respectif dans le pixel pour renseigner la balise [!DNL Facebook Audience]. Cela se traduit par une augmentation progressive du [!DNL Facebook Audience], plus la balise est déclenchée vers l’audience applicable sur votre site.

>[!NOTE]
>
> Si un utilisateur sort du segment [!DNL Audience Manager], il n’existe actuellement aucun moyen pour [!DNL Audience Manager] d’informer [!DNL Facebook] de supprimer l’utilisateur de la balise [!DNL Custom Audience].

