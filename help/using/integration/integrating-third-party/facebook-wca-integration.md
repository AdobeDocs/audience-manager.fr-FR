---
description: Cette page illustre le processus de création de pixels WCA (Custom Audiences) du site Web Facebook dans le but d’envoyer des segments d’audience Audience Manager basés sur le Web à Facebook, pour le ciblage des publicités en ligne avec une transparence améliorée.
seo-description: Cette page illustre le processus de création de pixels WCA (Custom Audiences) du site Web Facebook dans le but d’envoyer des segments d’audience Audience Manager basés sur le Web à Facebook, pour le ciblage des publicités en ligne avec une transparence améliorée.
seo-title: Intégration WCA Facebook
solution: Audience Manager
title: Intégration WCA Facebook
translation-type: tm+mt
source-git-commit: 28d1292140a56cf1627a8921876d9483221876ca

---


# Intégration WCA Facebook {#facebook-wca-integration}

Cette page illustre le processus de création de pixels WCA (Custom Audiences) du site Web Facebook dans le but d’envoyer des segments d’audience Audience Manager basés sur le Web à Facebook, pour le ciblage des publicités en ligne avec une transparence améliorée.

## Aperçu {#overview}

[Le site Web Facebook Audiences personnalisées (WCA)](https://www.facebook.com/business/help/449542958510885) vous permet de créer une liste des personnes qui ont visité certaines pages ou entrepris des actions particulières sur votre site Web. Audience Manager active l’activation dans WCA à l’aide de destinations URL, avec lesquelles vous pouvez configurer une intégration personnalisée basée sur les pixels pour envoyer des audiences Web à Facebook en vue du ciblage.

![Intégration WCA Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Cette fonctionnalité nécessite que vous sélectionniez l’option Public du site Web pour les plateformes sociales dans les destinations [](/help/using/features/destinations/create-url-destination.md)URL. Les plateformes sociales exigent que les informations des référents soient démasquées lorsqu’elles sont envoyées sur leur plateforme. Sachez que cela signifie que la plateforme/le partenaire de destination pourra voir les informations dans votre URL de référent.

## Conditions préalables {#prerequisites}

1. Compte de publicité Facebook
2. Segments Audience Manager, prêts à être attribués à votre nouvelle destination Facebook. Voici [comment créer un segment](/help/using/features/segments/segment-builder.md) dans l’interface utilisateur d’Audience Manager.
3. Adobe Experience Cloud ID Service (ECID) version 4.1.0 ou ultérieure. Téléchargez la dernière version **[ici](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. Bibliothèque d’intégration des données d’Audience Manager (DIL) version 9.0 ou ultérieure, téléchargeable **[ici](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Si vous utilisez le transfert côté [serveur (SSF)](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) pour importer des données dans Audience Manager, vous devez utiliser AppMeasurement version 2.12 ou ultérieure. Téléchargez AppMeasurement à l’aide du Gestionnaire [de code](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)Analytics.

Nous vous recommandons d’installer ou de mettre à niveau les bibliothèques des étapes 3 et 4 à l’aide d’ [Adobe Launch](https://docs.adobelaunch.com/) ou de la gestion [dynamique des balises](https://marketing.adobe.com/resources/help/en_US/dtm/)Adobe.

## Étape 1 - Création d’une destination Facebook dans Audience Manager {#step-1-create-facebook-destination}

Créez une destination d’URL dans Audience Manager et nommez-la Audiences personnalisées du site Web Facebook. Utilisez les paramètres ci-dessous lors de la création de la destination. Vous pouvez également vous reporter à la page [Configurer une destination](/help/using/features/destinations/create-url-destination.md) URL.

**Informations fondamentales**

* **Catégorie**: Personnalisé
* **Type**: URL
* Cochez la case Mappage **de destination** automatique, puis sélectionnez ID **de** segment.

**Étiquettes d’exportation de données**

Sélectionnez l’option **Cette destination peut permettre une combinaison avec des informations d’identification personnelle (PII)**.

>[!NOTE]
>
> Ce libellé d’exportation empêche l’inclusion dans les segments des données et données tierces dérivées des graphiques de périphériques.

**Configuration**

* **Type** d’URL : Sélectionnez l’audience **du site Web pour les plateformes** sociales. En sélectionnant cette option de type d’URL, Audience Manager n’obscurcit pas les informations sur l’URL du référent lors du déclenchement d’un pixel WCA Facebook.
* **Sérialiser**: Sélectionnez **Activer**.
* Dans le champ URL **de** base et URL **** sécurisée, saisissez le pixel Facebook WCA.
* **Délimiteur**: ,

Exemple d’URL de base : `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Exemple de pixel déclenché à partir de la page. Cet exemple montre un utilisateur admissible pour trois segments d’Audience Manager, avec les ID 3401321, 2993399, 3263410 :

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| Paramètre | Description |
---------|----------|
| `id` | Votre ID de pixel Facebook, que vous trouverez dans l’interface utilisateur du gestionnaire d’annonces Facebook lors de la création de pixels d’audience. |
| `ev` | Événement. Il s’agit d’une valeur arbitraire qui s’affichera dans l’interface utilisateur du gestionnaire d’annonces Facebook une fois que le pixel commencera à se déclencher sur le site. Pour plus d’informations, voir l’élément Inclure à l’ [étape 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience). |
| `cd[segID]` | Paramètre supplémentaire qui commence à être renseigné dans l’interface utilisateur du gestionnaire des annonces Facebook une fois que le pixel commence à se déclencher sur le site. `segID` est également arbitraire. |
| `%ALIAS%` | macro Audience Manager, qui sera remplacée dynamiquement par les identifiants de segment Audience Manager pour lesquels le visiteur du site est admissible, délimités par une virgule , |

La configuration de destination de l’URL doit se présenter comme suit :

![Configuration de la destination](/help/using/integration/assets/facebook-wca.png)

Enregistrez la destination. Ensuite, vous pouvez passer à l’étape Mappages des **segments** .

## Étape 2 - Mappages de segments - Associer le segment à la destination {#step-2-segment-mappings}

Dans le flux de travail [Configurer la destination](/help/using/features/destinations/create-url-destination.md) de l’URL, mappez le segment applicable à votre destination nouvellement créée. Notez que la valeur de mappage est automatiquement renseignée avec l’ID de segment d’Audience Manager.

Entrez une date de fin, le cas échéant, sans entrer de date de fin.

## Étape 3 - Création d’une audience dans le Gestionnaire d’annonces Facebook {#step-3-create-audience}

Voir [Création d’une audience](https://www.facebook.com/business/help/666509013483225) personnalisée d’un site Web dans la documentation d’aide de Facebook. Sélectionnez les options Créer une audience dans le tableau ci-dessous :


| Élément | Description |
---------|----------|
| Trafic du site Web | Combinaison personnalisée |
| Inclure | <ul><li>Sélectionnez **Evénement** &gt; Sélectionner **Adobe-Audience-Manager-Segment**. Il s’agit de la valeur du paramètre ev dans l’exemple de pixel de l’étape 1. Notez que si le pixel n’est pas encore déclenché, l’option **Evénement** ou **Adobe-Audience-Manager-Segment** peut ne pas apparaître dans l’interface utilisateur de Facebook.</li><li>Ajoutez un paramètre : Sélectionnez `segID`.</li><li><p>Sélectionnez l’opérateur **contains** .</p><p>Ceci est important, car les visiteurs peuvent être admissibles à plusieurs segments, il peut y avoir plusieurs ID de segment dans le paramètre de pixel. L’utilisation de l’opérateur égal à (=) peut ne pas rendre vos visiteurs admissibles au public et vous obtiendrez un volume inférieur.</p></li><li>Ajoutez une valeur : Saisissez l’identifiant du segment Audience Manager.</li></ul> |
| Ajouter une nouvelle condition | Paramètre facultatif. |
| Dans le dernier | Paramètre facultatif. |
| Nom de l’audience | Nous vous recommandons d’utiliser le même nom de segment Audience Manager pour assurer la cohérence, sauf si vous ajoutez des conditions supplémentaires à ce public. |

## Étape 4 - Affectation de l’audience à une campagne dans le Gestionnaire d’annonces Facebook {#step-4-assign-audience-to-campaign}

Après avoir créé l’audience personnalisée, affectez-la à une campagne publicitaire. Créez une nouvelle campagne ou modifiez une campagne existante. Votre audience nouvellement créée est répertoriée dans l’interface utilisateur de Facebook. Votre campagne publicitaire ciblera les utilisateurs qui ont vu le pixel près de leur navigateur lors de leur visite sur votre site, si Audience Manager les inclut dans le segment.

## Résumé {#summary}

Maintenant que vous avez affecté votre segment Audience Manager à la destination WCA Facebook, Audience Manager déclenche sélectivement le pixel WCA Facebook pour les utilisateurs d’un segment donné avec l’ID de segment correspondant dans le pixel afin de renseigner l’audience Facebook. Cela se traduit par une augmentation progressive de l’audience Facebook, plus la balise est déclenchée vers l’audience applicable sur votre site.

>[!NOTE]
>
> Si un utilisateur sort du segment Audience Manager, il n’existe actuellement aucun moyen pour Audience Manager d’informer Facebook de sa suppression du segment Audience Manager personnalisé.

