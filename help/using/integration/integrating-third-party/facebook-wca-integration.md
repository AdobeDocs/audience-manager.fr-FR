---
description: Cette page illustre le processus de création de pixels d’Audiences personnalisées (WCA) du site Web de Facebook afin d’envoyer des segments d’audience d’Audience Manager Web à Facebook, pour le ciblage des publicités en ligne avec une transparence accrue.
seo-description: Cette page illustre le processus de création de pixels d’Audiences personnalisées (WCA) du site Web de Facebook afin d’envoyer des segments d’audience d’Audience Manager Web à Facebook, pour le ciblage des publicités en ligne avec une transparence accrue.
seo-title: Intégration Facebook WCA
solution: Audience Manager
title: Intégration Facebook WCA
feature: Intégration tierce
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
translation-type: tm+mt
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 5%

---

# [!DNL Facebook WCA] Analytics {#facebook-wca-integration}

Cette page illustre le processus de création de [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) pixels pour l’envoi de segments d’audience [!DNL Audience Manager] Web à [!DNL Facebook], pour le ciblage des publicités en ligne avec une transparence améliorée.

## Présentation {#overview}

[Facebook Website Custom Audiences (WCA) vous ](https://www.facebook.com/business/help/449542958510885) permet de créer une liste de personnes qui ont visité certaines pages ou entrepris des actions particulières sur votre site Web. [!DNL Audience Manager] permet l’activation lors de l’ [!DNL WCA] utilisation de  [!DNL URL] destinations, avec lesquelles vous pouvez configurer une intégration personnalisée basée sur les pixels pour envoyer des audiences Web  [!DNL Facebook] pour le ciblage.

![Intégration Facebook WCA](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Cette fonctionnalité nécessite que vous sélectionniez l’option [!UICONTROL Website] audience pour les plateformes sociales dans [destinations URL](/help/using/features/destinations/create-url-destination.md). Les plateformes sociales exigent que les informations du parrain soient démasquées lorsqu’elles sont envoyées sur leur plateforme. Sachez que cela signifie que la plateforme/le partenaire de destination pourra voir les informations dans votre parrain [!DNL URL].

## Conditions préalables {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segments, prêts à être attribués à votre nouvelle  [!DNL Facebook] destination. Voici [comment créer un segment](/help/using/features/segments/segment-builder.md) dans l&#39;interface utilisateur [!DNL Audience Manager].
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Version 4.1.0 ou ultérieure. Téléchargez la version la plus récente **[ici](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) version 9.0 ou ultérieure, téléchargeable  **[ici](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Si vous utilisez [Transfert côté serveur (SSF)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) pour importer des données dans [!DNL Audience Manager], vous devez utiliser AppMeasurement version 2.12 ou ultérieure. Téléchargez [!DNL AppMeasurement] à l’aide du [Gestionnaire de code Analytics](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html).

Nous vous recommandons d’installer ou de mettre à niveau les bibliothèques aux étapes 3 et 4 en utilisant [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html).

## Étape 1 - Créer un [!UICONTROL Facebook Destination] dans [!DNL Audience Manager] {#step-1-create-facebook-destination}

Créez un [!UICONTROL URL Destination] dans [!DNL Audience Manager] et nommez-le [!DNL Facebook Website Custom Audiences]. Utilisez les paramètres ci-dessous lors de la création de la destination. Vous pouvez également vous reporter à la page [Configurer une URL de destination](/help/using/features/destinations/create-url-destination.md).

### Informations fondamentales

* **[!UICONTROL Category]**: Personnalisé
* **[!UICONTROL Type]**:  [!DNL URL]
* Cochez la case **[!UICONTROL Auto-fill Destination Mapping]**, puis sélectionnez **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Sélectionnez l&#39;option **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Cette étiquette d’exportation empêche l’inclusion dans les segments des données et données tierces dérivées des graphiques de périphérique.

### Configuration

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. En sélectionnant cette option [!UICONTROL URL Type], [!DNL Audience Manager] n&#39;obscurcit pas les informations de parrain [!DNL URL] lors du déclenchement d&#39;un pixel [!DNL Facebook WCA].
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* Dans les champs **[!UICONTROL Base URL]** et **[!UICONTROL Secure URL]**, saisissez le pixel [!DNL Facebook WCA].
* **[!UICONTROL Delimiter]**:  `,`

Exemple de base [!DNL URL] : `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Exemple de pixel déclenché à partir de la page. Cet exemple montre un utilisateur qui est admissible pour trois segments [!DNL Audience Manager] avec les ID 3401321, 2993399, 3263410 :

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Paramètre | Description |
---------|----------|
| `id` | Votre ID de pixel [!DNL Facebook], que vous trouverez dans l’interface utilisateur [!DNL Facebook Ad Manager] lors de la création de pixels d’audience. |
| `ev` | Event.     Il s’agit d’une valeur arbitraire qui apparaîtra dans l’interface utilisateur [!DNL Facebook Ad Manager] une fois que le pixel commencera à se déclencher sur le site. Pour plus d’informations, voir l’élément [!UICONTROL Include] dans [Étape 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience). |
| `cd[segID]` | Un autre paramètre, qui commencera à être renseigné dans l&#39;interface utilisateur [!DNL Facebook Ad Manager] une fois que le pixel commencera à se déclencher sur le site. `segID` est aussi arbitraire. |
| `%ALIAS%` | Une macro [!DNL Audience Manager], qui sera dynamiquement remplacée par les [!DNL Audience Manager] [!UICONTROL segment] identifiants pour lesquels le visiteur du site est admissible, délimités par des virgules, |

Votre configuration [!UICONTROL URL destination] doit ressembler à l&#39;image ci-dessous :

![Configuration de destination](/help/using/integration/assets/facebook-wca.png)

Enregistrez le [!UICONTROL destination]. Ensuite, vous pouvez passer à l’étape **Mappages de segments**.

## Étape 2 - Mappages de segments - Mapper le segment à la destination {#step-2-segment-mappings}

Dans le flux de travaux [Configurer la destination de l’URL](/help/using/features/destinations/create-url-destination.md), mappez le segment approprié à votre [!UICONTROL destination] nouvellement créé. Notez que la valeur de mappage est automatiquement renseignée par [!DNL Audience Manager] [!UICONTROL segment ID].

Entrez une date de fin, le cas échéant, ou laissez vide pour ne pas saisir de date de fin.

## Étape 3 - Créer un [!UICONTROL Audience] dans [!DNL Facebook Ads Manager] {#step-3-create-audience}

Voir [Création d’une Audience personnalisée d’un site Web](https://www.facebook.com/business/help/666509013483225) dans la [!DNL Facebook] documentation d’aide. Sélectionnez les options [!UICONTROL Create Audience] dans le tableau ci-dessous :

| Élément | Description |
---------|----------|
| Trafic du site Web | Combinaison personnalisée |
| Inclure | <ul><li>Sélectionnez **[!UICONTROL Event]** > Sélectionner **[!UICONTROL Adobe-Audience-Manager-Segment]**. Il s’agit de la valeur du paramètre `ev` dans l’exemple de pixel de l’étape 1. Notez que si le pixel n&#39;est pas encore déclenché, l&#39;option **[!UICONTROL Event]** ou **[!UICONTROL Adobe-Audience-Manager-Segment]** peut ne pas apparaître dans l&#39;interface utilisateur [!DNL Facebook].</li><li>Ajoutez un paramètre : Sélectionnez `segID`.</li><li><p>Sélectionnez l&#39;opérateur **contient**.</p><p>Ceci est important, étant donné que les visiteurs peuvent être inclus dans plusieurs segments, il peut y avoir plusieurs [!UICONTROL segment IDs] dans le paramètre de pixel. L&#39;utilisation de l&#39;opérateur égal (`=`) peut ne pas qualifier vos visiteurs pour l&#39;audience et vous obtiendrez un volume inférieur.</p></li><li>Ajoutez une valeur : Saisissez l&#39;ID de segment [!DNL Audience Manager].</li></ul> |
| Ajouter une nouvelle condition | Paramètre facultatif. |
| Dans le dernier | Paramètre facultatif. |
| Nom de l’Audience | Nous vous recommandons d’utiliser le même nom de segment [!DNL Audience Manager] pour assurer la cohérence, sauf si vous ajoutez des conditions supplémentaires à cette Audience. |

## Étape 4 - Affecter le [!UICONTROL Audience] à un [!UICONTROL Campaign] dans [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Après avoir créé le [!DNL Custom Audience], affectez-le à une campagne publicitaire. Créez une nouvelle campagne ou modifiez une campagne existante. Votre audience nouvellement créée est répertoriée dans l&#39;interface utilisateur [!DNL Facebook]. Votre campagne publicitaire cible les utilisateurs qui ont vu le pixel se déclencher sur leur navigateur lors de leur visite sur votre site, si [!DNL Audience Manager] les inclut dans le segment.

## Résumé {#summary}

Maintenant que vous avez affecté votre segment [!DNL Audience Manager] à la destination [!DNL Facebook WCA], [!DNL Audience Manager] déclenche sélectivement le pixel [!DNL Facebook WCA] aux utilisateurs d’un segment donné avec l’ID de segment correspondant dans le pixel pour renseigner le [!DNL Facebook Audience]. Ceci se traduit par une augmentation progressive de la balise [!DNL Facebook Audience] plus la balise est déclenchée vers l’audience applicable de votre site.

>[!NOTE]
>
> Si un utilisateur sort du segment [!DNL Audience Manager], [!DNL Audience Manager] n&#39;a actuellement aucun moyen d&#39;informer [!DNL Facebook] de supprimer l&#39;utilisateur de [!DNL Custom Audience].

