---
description: Cette page illustre le processus de création de pixels d’audiences personnalisées (WCA) de site web Facebook dans le but d’envoyer des segments d’audience Audience Manager web vers Facebook, pour un ciblage d’annonce en ligne avec une transparence améliorée.
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Intégration WCA Facebook
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: 6dc931b88666515cf51ab89ce1a54bbcf9995679
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 1%

---

# Intégration [!DNL Facebook WCA] {#facebook-wca-integration}

Cette page illustre le processus de création de pixels [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) dans le but d’envoyer des segments d’audience [!DNL Audience Manager] web vers [!DNL Facebook], pour un ciblage d’annonce en ligne avec une transparence améliorée.

>[!IMPORTANT]
>
>Il ne s’agit pas d’une intégration personnalisée entre Audience Manager et Facebook.

## Présentation {#overview}

[Audiences personnalisées de site web Facebook (WCA))](https://www.facebook.com/business/help/610516375684216?id=2469097953376494) permet de créer une liste de personnes qui ont visité certaines pages ou effectué des actions spécifiques sur votre site web. [!DNL Audience Manager] active l’activation dans les [!DNL WCA] à l’aide de destinations [!DNL URL], avec lesquelles vous pouvez configurer une intégration personnalisée basée sur les pixels pour envoyer des audiences web aux [!DNL Facebook] pour le ciblage.

![Intégration Facebook WCA](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Cette fonctionnalité nécessite de sélectionner l’option [!UICONTROL Website] l’audience pour les plateformes sociales dans [destinations d’URL](/help/using/features/destinations/create-url-destination.md). Les plateformes sociales exigent que les informations de référent soient démasquées lorsqu’elles sont envoyées à leur plateforme. Sachez que cela signifie que la plateforme/le partenaire de destination pourra voir les informations dans votre [!DNL URL] de référent.

## Conditions préalables {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] des segments, prêts à être affectés à votre nouvelle destination [!DNL Facebook]. Voici [comment créer un segment](/help/using/features/segments/segment-builder.md) dans l’interface utilisateur de [!DNL Audience Manager].
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Version 4.1.0 ou ultérieure. Téléchargez la dernière version **[ici](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) version 9.0 ou ultérieure, téléchargeable **[ici](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Si vous utilisez [Transfert côté serveur (SSF)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=fr) pour importer des données dans [!DNL Audience Manager], vous devez également utiliser AppMeasurement version 2.12 ou ultérieure. Téléchargez [!DNL AppMeasurement] à l’aide du [Gestionnaire de code Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html?lang=fr).

Nous vous recommandons d’installer ou de mettre à niveau les bibliothèques des étapes 3 et 4 à l’aide de [Adobe Experience Platform Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr).

## Étape 1 : création d’un [!UICONTROL Facebook Destination] dans [!DNL Audience Manager] {#step-1-create-facebook-destination}

Créez un [!UICONTROL URL Destination] dans [!DNL Audience Manager] et nommez-le [!DNL Facebook Website Custom Audiences]. Utilisez les paramètres ci-dessous lors de la création de la destination. Vous pouvez également vous reporter à la page [Configurer une destination d’URL](/help/using/features/destinations/create-url-destination.md).

### Informations fondamentales

* **[!UICONTROL Category]** : Personnalisé
* **[!UICONTROL Type]** : [!DNL URL]
* Cochez la case **[!UICONTROL Auto-fill Destination Mapping]**, puis sélectionnez **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Sélectionnez l’option **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Ce libellé d’exportation empêche l’inclusion de données tierces et de données dérivées de graphiques d’appareils dans les segments.

### Configuration

* **[!UICONTROL URL type]** : sélectionnez **[!UICONTROL Website audience for social platforms]**. En sélectionnant cette option de [!UICONTROL URL Type], [!DNL Audience Manager] ne masque pas les informations de [!DNL URL] du référent lors du déclenchement d’un pixel d’[!DNL Facebook WCA].
* **[!UICONTROL Serialize]** : sélectionnez **[!UICONTROL Enable]**.
* Dans le champ **[!UICONTROL Base URL]** et **[!UICONTROL Secure URL]** , saisissez le pixel d’[!DNL Facebook WCA].
* **[!UICONTROL Delimiter]** : `,`

Exemple de [!DNL URL] de base : `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Exemple de pixel déclenché depuis la page. Cet exemple montre un utilisateur qui remplit les critères pour trois segments [!DNL Audience Manager], avec les ID 3401321, 2993399 et 3263410 :

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Paramètre | Description |
|---------|----------|
| `id` | Identifiant en pixels [!DNL Facebook], que vous pouvez trouver dans l’interface utilisateur [!DNL Facebook Ad Manager] lors de la création de pixels d’audience. |
| `ev` | Événement. Il s’agit d’une valeur arbitraire qui apparaîtra dans l’interface utilisateur [!DNL Facebook Ad Manager] une fois que le pixel commencera à se déclencher sur le site. Pour plus d’informations[!UICONTROL Include] reportez-vous à l’élément [ à l’étape ](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience) 3. |
| `cd[segID]` | Un paramètre supplémentaire, qui commencera à être renseigné dans l’interface utilisateur [!DNL Facebook Ad Manager] une fois que le pixel commencera à se déclencher sur le site. `segID` est également arbitraire. |
| `%ALIAS%` | Une macro [!DNL Audience Manager], qui sera remplacée dynamiquement par les identifiants de [!DNL Audience Manager] [!UICONTROL segment] pour lesquels le visiteur du site est éligible, délimités par une virgule , |

Votre configuration [!UICONTROL URL destination] doit se présenter comme dans l’image ci-dessous :

![Configuration de la destination](/help/using/integration/assets/facebook-wca.png)

Enregistrez le [!UICONTROL destination]. Vous pouvez ensuite passer à l’étape **Mappages de segments**.

## Étape 2 - Mappages de segments - Mapper un segment à la destination {#step-2-segment-mappings}

Dans le workflow [ Configurer la destination de l’URL ](/help/using/features/destinations/create-url-destination.md), mappez le segment applicable à votre [!UICONTROL destination] nouvellement créé. Notez que la valeur de mappage est automatiquement renseignée avec le [!DNL Audience Manager] [!UICONTROL segment ID].

Saisissez une date de fin, le cas échéant, ou laissez le champ vide sans date de fin.

## Étape 3 : création d’un [!UICONTROL Audience] dans [!DNL Facebook Ads Manager] {#step-3-create-audience}

Voir [Création d’une audience personnalisée de site web](https://www.facebook.com/business/help/666509013483225) dans la documentation d’aide [!DNL Facebook]. Sélectionnez les options [!UICONTROL Create Audience] dans le tableau ci-dessous :

| Élément | Description |
|---------|----------|
| Trafic du site Web | Combinaison personnalisée |
| Inclure | <ul><li>Sélectionnez **[!UICONTROL Event]** > Sélectionner **[!UICONTROL Adobe-Audience-Manager-Segment]**. Il s’agit de la valeur du paramètre `ev` dans l’exemple de pixel de l’étape 1. Notez que si le pixel doit encore se déclencher, l’option ou le **[!UICONTROL Event]** **[!UICONTROL Adobe-Audience-Manager-Segment]** peut ne pas apparaître dans l’interface utilisateur [!DNL Facebook].</li><li>Ajoutez un paramètre : sélectionnez `segID`.</li><li><p>Sélectionnez l’opérateur **contains**.</p><p>Ce point est important. Étant donné que les visiteurs peuvent être qualifiés pour plusieurs segments, le paramètre de pixel peut comporter plusieurs [!UICONTROL segment IDs]. L’utilisation de l’opérateur égal à (`=`) peut ne pas qualifier vos visiteurs pour l’audience et vous observerez un volume inférieur.</p></li><li>Ajoutez une valeur : saisissez l’identifiant de segment [!DNL Audience Manager].</li></ul> |
| Ajouter une nouvelle condition | Paramètre facultatif. |
| Dans la dernière | Paramètre facultatif. |
| Nom de l’audience | Par souci de cohérence, nous vous recommandons d’utiliser le même nom de segment [!DNL Audience Manager], sauf si vous ajoutez des conditions supplémentaires à cette audience. |

## Étape 4 - Attribuer le [!UICONTROL Audience] à un [!UICONTROL Campaign] dans [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Après avoir créé le [!DNL Custom Audience], affectez-le à une campagne publicitaire. Créez une campagne ou modifiez une campagne existante et vous constaterez que l’audience que vous venez de créer est répertoriée dans l’interface utilisateur d’[!DNL Facebook]. Votre campagne publicitaire cible les utilisateurs et utilisatrices qui ont vu le pixel se déclencher sur leur navigateur lors de leur visite sur votre site, si [!DNL Audience Manager] les inclut dans le segment.

## Résumé {#summary}

Maintenant que vous avez affecté votre segment de [!DNL Audience Manager] à la destination de [!DNL Facebook WCA], [!DNL Audience Manager] déclenchera de manière sélective le pixel de [!DNL Facebook WCA] pour les utilisateurs d’un segment donné avec l’identifiant de segment correspondant dans le pixel pour remplir le [!DNL Facebook Audience]. Cela entraîne une augmentation progressive de la [!DNL Facebook Audience] plus la balise est déclenchée vers l’audience applicable sur votre site.

>[!NOTE]
>
> Si un utilisateur ou une utilisatrice est exclu du segment [!DNL Audience Manager], il n’existe actuellement aucun moyen pour [!DNL Audience Manager] d’informer le [!DNL Facebook] ou la utilisatrice de le [!DNL Custom Audience].
>
