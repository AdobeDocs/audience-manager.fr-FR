---
description: Cette page illustre le processus de création de pixels WCA (Audiences personnalisées du site Web Facebook) afin d’envoyer des segments d’audience d’Audience Manager basés sur le Web à Facebook, pour le ciblage des annonces en ligne avec une transparence accrue.
seo-description: Cette page illustre le processus de création de pixels WCA (Audiences personnalisées du site Web Facebook) afin d’envoyer des segments d’audience d’Audience Manager basés sur le Web à Facebook, pour le ciblage des annonces en ligne avec une transparence accrue.
seo-title: Intégration WCA Facebook
solution: Audience Manager
title: Intégration WCA Facebook
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 2%

---


# [!DNL Facebook WCA] Analytics {#facebook-wca-integration}

Cette page illustre le processus de création de [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) pixels pour l’envoi de segments d’ [!DNL Audience Manager] audience basés sur le Web vers [!DNL Facebook], pour le ciblage des annonces en ligne avec une transparence accrue.

## Aperçu {#overview}

[Les Audiences personnalisées (WCA)](https://www.facebook.com/business/help/449542958510885) du site Web Facebook vous permettent de créer une liste de personnes qui ont visité certaines pages ou effectué certaines actions particulières sur votre site Web. [!DNL Audience Manager] permet l’activation dans [!DNL WCA] l’utilisation de [!DNL URL] destinations, avec lesquelles vous pouvez configurer une intégration personnalisée basée sur les pixels pour envoyer des audiences Web à [!DNL Facebook] des fins de ciblage.

![Intégration WCA Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Cette fonctionnalité nécessite que vous sélectionniez l’option [!UICONTROL Website] audience pour les plateformes sociales dans les destinations [](/help/using/features/destinations/create-url-destination.md)URL. Les plateformes sociales exigent que les informations de parrain soient démasquées lorsqu’elles sont envoyées sur leur plateforme. Sachez que cela signifie que la plateforme/partenaire de destination pourra voir les informations dans votre parrain [!DNL URL].

## Conditions préalables {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segments, prêts à être attribués à votre nouvelle [!DNL Facebook] destination. Voici [comment créer un segment](/help/using/features/segments/segment-builder.md) dans l’ [!DNL Audience Manager] interface utilisateur.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Version 4.1.0 ou ultérieure. Téléchargez la dernière version **[ici](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) version 9.0 ou ultérieure, téléchargeable **[ici](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Sinon, si vous utilisez le transfert côté[serveur (SSF)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)pour importer des données dans[!DNL Audience Manager], vous devez utiliser AppMeasurement version 2.12 ou ultérieure. Téléchargez[!DNL AppMeasurement]à l’aide du Gestionnaire[de code](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html)Analytics.

Nous vous recommandons d’installer ou de mettre à niveau les bibliothèques des étapes 3 et 4 à l’aide du lancement [d’](https://docs.adobelaunch.com/) Adobe Experience Platform ou de la gestion [dynamique des balises de Adobe](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html).

## Etape 1 - Création d’une [!UICONTROL Facebook Destination] section [!DNL Audience Manager] {#step-1-create-facebook-destination}

Créez un nouveau [!UICONTROL URL Destination] dans [!DNL Audience Manager] et nommez-le [!DNL Facebook Website Custom Audiences]. Utilisez les paramètres ci-dessous lors de la création de la destination. Vous pouvez également vous reporter à la page [Configurer une URL de destination](/help/using/features/destinations/create-url-destination.md) .

### Informations fondamentales

* **[!UICONTROL Category]**: Personnalisé
* **[!UICONTROL Type]**: [!DNL URL]
* Cochez la **[!UICONTROL Auto-fill Destination Mapping]** case, puis sélectionnez **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Sélectionnez l’option **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Cette étiquette d’exportation empêche l’inclusion dans les segments des données et données tierces dérivées des graphiques de périphérique.

### Configuration

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. En sélectionnant cette [!UICONTROL URL Type] option, [!DNL Audience Manager] n’obscurcit pas les informations du parrain [!DNL URL] lors du déclenchement d’un [!DNL Facebook WCA] pixel.
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* Dans le champ **[!UICONTROL Base URL]** et **[!UICONTROL Secure URL]** , entrez le [!DNL Facebook WCA] pixel.
* **[!UICONTROL Delimiter]**: `,`

Exemple [!DNL URL] de base : `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Exemple de pixel déclenché à partir de la page. Cet exemple montre un utilisateur admissible pour trois [!DNL Audience Manager] segments, avec les ID 3401321, 2993399, 3263410 :

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Paramètre | Description |
---------|----------|
| `id` | Votre ID de [!DNL Facebook] pixel, que vous pouvez trouver dans l’interface [!DNL Facebook Ad Manager] utilisateur lors de la création de pixels d’audience. |
| `ev` | Event.     Il s’agit d’une valeur arbitraire qui apparaîtra dans l’interface [!DNL Facebook Ad Manager] utilisateur une fois que le pixel commencera à se déclencher sur le site. Pour plus d’informations, voir l’ [!UICONTROL Include] élément de l’ [étape 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience). |
| `cd[segID]` | Un autre paramètre, qui commence à être renseigné dans l’interface [!DNL Facebook Ad Manager] utilisateur une fois que le pixel commence à se déclencher sur le site. `segID` est aussi arbitraire. |
| `%ALIAS%` | Une [!DNL Audience Manager] macro, qui sera dynamiquement remplacée par les [!DNL Audience Manager] [!UICONTROL segment] identifiants pour lesquels le visiteur du site est admissible, délimités par une virgule, |

Votre [!UICONTROL URL destination] configuration doit se présenter comme suit :

![Configuration de destination](/help/using/integration/assets/facebook-wca.png)

Enregistrez le [!UICONTROL destination]. Ensuite, vous pouvez passer à l’étape Correspondances **des** segments.

## Étape 2 - Mappages de segments - Mapper un segment à la destination {#step-2-segment-mappings}

Dans le flux de travaux [Configurer la destination](/help/using/features/destinations/create-url-destination.md) de l’URL, mappez le segment applicable à votre nouveau segment [!UICONTROL destination]créé. Notez que la valeur de mappage est automatiquement renseignée avec la [!DNL Audience Manager][!UICONTROL segment ID].

Entrez une date de fin, le cas échéant, ou laissez vide pour ne pas saisir de date de fin.

## Etape 3 : création d’un [!UICONTROL Audience] élément [!DNL Facebook Ads Manager] {#step-3-create-audience}

Voir [Création d’une Audience](https://www.facebook.com/business/help/666509013483225) personnalisée d’un site Web dans la [!DNL Facebook] documentation d’aide. Sélectionnez les [!UICONTROL Create Audience] options du tableau ci-dessous :

| Élément | Description |
---------|----------|
| Trafic du site Web | Combinaison personnalisée |
| Inclure | <ul><li>Choisissez **[!UICONTROL Event]** > Sélectionner **[!UICONTROL Adobe-Audience-Manager-Segment]**. Il s’agit de la valeur du `ev` paramètre dans l’exemple de pixel de l’étape 1. Notez que si le pixel doit encore se déclencher, l’ **[!UICONTROL Event]** option ou **[!UICONTROL Adobe-Audience-Manager-Segment]** peut ne pas apparaître dans l’interface [!DNL Facebook] utilisateur.</li><li>Ajoutez un paramètre : Sélectionnez `segID`.</li><li><p>Sélectionnez l’opérateur **contient** .</p><p>Ceci est important, puisque les visiteurs peuvent être inclus dans plusieurs segments, il peut y avoir plusieurs segments [!UICONTROL segment IDs] dans le paramètre de pixel. L&#39;utilisation de l&#39;opérateur égal (`=`) peut ne pas qualifier vos visiteurs pour l&#39;audience, et vous observerez un volume inférieur.</p></li><li>Ajoutez une valeur : Saisissez l’ID du [!DNL Audience Manager] segment.</li></ul> |
| Ajouter une nouvelle condition | Paramètre facultatif. |
| Dans le dernier | Paramètre facultatif. |
| Nom de l’Audience | Nous vous recommandons d’utiliser le même nom de [!DNL Audience Manager] segment pour assurer la cohérence, sauf si vous ajoutez des conditions supplémentaires à cette Audience. |

## Étape 4 - Affecter le [!UICONTROL Audience] à un [!UICONTROL Campaign] dans [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Après avoir créé le fichier [!DNL Custom Audience], affectez-le à une campagne publicitaire. Créez une nouvelle campagne ou modifiez une campagne existante. Votre audience nouvellement créée est répertoriée dans l’interface [!DNL Facebook] utilisateur. Votre campagne publicitaire cible les utilisateurs qui ont vu le pixel se déclencher sur leur navigateur lors de leur visite sur votre site, si [!DNL Audience Manager] elle les inclut dans le segment.

## Résumé {#summary}

Maintenant que vous avez affecté votre [!DNL Audience Manager] segment à la [!DNL Facebook WCA] destination, [!DNL Audience Manager] déclenche sélectivement le pixel pour les utilisateurs d’un segment donné avec l’ID de segment correspondant dans le pixel pour renseigner le [!DNL Facebook WCA] [!DNL Facebook Audience]. Ceci se traduit par une augmentation progressive du nombre de déclenchements de la balise [!DNL Facebook Audience] à l’audience applicable de votre site.

>[!NOTE]
>
> Si un utilisateur sort du [!DNL Audience Manager] segment, il n’existe actuellement aucun moyen [!DNL Audience Manager] d’informer [!DNL Facebook] de la suppression de l’utilisateur du [!DNL Custom Audience].

