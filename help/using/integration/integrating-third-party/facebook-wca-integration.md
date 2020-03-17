---
description: Cette page illustre le processus de création de pixels de  personnalisés (WCA) du site Web de Facebook dans le but d’envoyer des segments de de Gestionnaire de de contenu Web à Facebook, pour le ciblage des publicités en ligne avec une transparence améliorée.
seo-description: Cette page illustre le processus de création de pixels de  personnalisés (WCA) du site Web de Facebook dans le but d’envoyer des segments de de Gestionnaire de de contenu Web à Facebook, pour le ciblage des publicités en ligne avec une transparence améliorée.
seo-title: Intégration WCA Facebook
solution: Audience Manager
title: Intégration WCA Facebook
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# Intégration WCA Facebook {#facebook-wca-integration}

Cette page illustre le processus de création de pixels de  personnalisés (WCA) du site Web de Facebook dans le but d’envoyer des segments de de Gestionnaire de de contenu Web à Facebook, pour le ciblage des publicités en ligne avec une transparence améliorée.

## Aperçu {#overview}

[Site Web Facebook Custom   (WCA)](https://www.facebook.com/business/help/449542958510885) vous permet de créer un de personnes qui ont visité certaines pages ou effectué des actions particulières sur votre site Web.  Gestionnaire de  de active  dans WCA à l’aide de destinations URL, avec lesquelles vous pouvez configurer une intégration personnalisée basée sur les pixels pour envoyer desWeb à Facebook pour le ciblage.

![Intégration WCA Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Cette fonctionnalité nécessite que vous sélectionniez l’option  site Web  pour les plateformes sociales dans les destinations [](/help/using/features/destinations/create-url-destination.md)URL. Les plateformes sociales exigent que les informations  des soient démasquées lorsqu’elles sont envoyées sur leur plateforme. Sachez que cela signifie que la plateforme/le partenaire de destination pourra voir les informations dans l&#39;URL de votre .

## Conditions préalables {#prerequisites}

1. Compte de publicité Facebook
2.  segments du Gestionnaire de  de, prêts à être attribués à votre nouvelle destination Facebook. Voici [comment créer un segment](/help/using/features/segments/segment-builder.md) dans l’interface utilisateur   Manager.
3. Adobe Experience Platform Identity Service (ECID) version 4.1.0 ou ultérieure. Téléchargez la dernière version **[ici](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4.  bibliothèque d’intégration de données de Manager (DIL) version 9.0 ou ultérieure, téléchargeable **[ici](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Si vous utilisez le transfert côté[serveur (SSF)](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html)pour importer des données dans  Gestionnaire de  de, vous devez utiliser AppMeasurement version 2.12 ou ultérieure. Téléchargez AppMeasurement à l’aide du Gestionnaire[de code](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)Analytics.

Nous vous recommandons d’installer ou de mettre à niveau les bibliothèques des étapes 3 et 4 à l’aide d’ [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) ou [Adobe Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/).

## Étape 1 - Création d’une destination Facebook dans  Gestionnaire de  de {#step-1-create-facebook-destination}

Créez une nouvelle destination URL dans  Gestionnaire de  de et nommez-la le Site Web Facebook de  personnalisés. Utilisez les paramètres ci-dessous lors de la création de la destination. Vous pouvez également vous reporter à la page [Configurer une destination](/help/using/features/destinations/create-url-destination.md) URL.

**Informations fondamentales**

* ****: Personnalisé
* **Type**: URL
* Cochez la case Mappage **de destination** automatique, puis sélectionnez ID **de** segment.

**Étiquettes d’exportation de données**

Sélectionnez l’option **Cette destination peut permettre une combinaison avec des informations d’identification personnelle (PII)**.

>[!NOTE]
>
> Ce libellé d’exportation empêche l’inclusion dans les segments des données et données tierces dérivées des graphiques de périphériques.

**Configuration**

* **Type** d’URL : Sélectionnez **Site Web   pour les plateformes** sociales. En sélectionnant cette option de type d’URL,  Gestionnaire de  de n’obscurcit pas les informations d’URL de l’lors du déclenchement d’un pixel WCA Facebook.
* **Sérialiser**: Sélectionnez **Activer**.
* Dans le champ URL **de** base et URL **** sécurisée, saisissez le pixel Facebook WCA.
* **Délimiteur**: ,

Exemple d’URL de base : `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Exemple de pixel déclenché à partir de la page. Cet exemple montre un utilisateur qui est admissible pour trois segments   Manager, avec les ID 3401321, 2993399, 3263410 :

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| Paramètre | Description |
---------|----------|
| `id` | Votre ID de pixel Facebook, que vous trouverez dans l’interface utilisateur du Gestionnaire d’annonces Facebook lors de la création   pixels. |
| `ev` | Événement. Il s’agit d’une valeur arbitraire qui s’affichera dans l’interface utilisateur du gestionnaire d’annonces Facebook une fois que le pixel commencera à se déclencher sur le site. Pour plus d’informations, voir l’élément Inclure à l’ [étape 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience). |
| `cd[segID]` | Paramètre supplémentaire qui commence à être renseigné dans l’interface utilisateur du gestionnaire des annonces Facebook une fois que le pixel commence à se déclencher sur le site. `segID` est également arbitraire. |
| `%ALIAS%` | Une macro  Gestionnaire de  de, qui sera remplacée dynamiquement par les ID de segments du Gestionnaire de de  de site auxquels le de site est admissible, délimités par une virgule , |

La configuration de destination de l’URL doit se présenter comme suit :

![Configuration de la destination](/help/using/integration/assets/facebook-wca.png)

Enregistrez la destination. Ensuite, vous pouvez passer à l’étape Mappages des **segments** .

## Étape 2 - Mappages de segments - Associer le segment à la destination {#step-2-segment-mappings}

Dans le flux de travail [Configurer la destination](/help/using/features/destinations/create-url-destination.md) de l’URL, mappez le segment applicable à votre destination nouvellement créée. Notez que la valeur de mappage est automatiquement renseignée avec l’ID de segment   Manager.

Entrez une date de fin, le cas échéant, sans entrer de date de fin.

## Etape 3 - Création d’un   dans le Gestionnaire d’annonces Facebook {#step-3-create-audience}

Reportez-vous à la page [Création d’un site Web  personnalisé](https://www.facebook.com/business/help/666509013483225) dans la documentation d’aide de Facebook. Sélectionnez les options Créer   de dans le tableau ci-dessous :


| Élément | Description |
---------|----------|
| Trafic du site Web | Combinaison personnalisée |
| Inclure | <ul><li>Sélectionnez **** > Sélectionnez **Adobe--Manager-Segment**. Il s’agit de la valeur du paramètre ev dans l’exemple de pixel de l’étape 1. Notez que si le pixel n’est pas encore déclenché, l’option **** ou l’option **Adobe--Manager-Segment** peut ne pas apparaître dans l’interface utilisateur de Facebook.</li><li>Ajouter un paramètre : Sélectionnez `segID`.</li><li><p>Sélectionnez l’opérateur **contains** .</p><p>Ceci est important, car les peuvent être admissibles pour plusieurs segments, il peut y avoir plusieurs ID de segment dans le paramètre de pixel. L&#39;utilisation de l&#39;opérateur égal à (=) peut ne pas qualifier vos pour la   et vous obtiendrez un volume inférieur.</p></li><li>Ajouter une valeur : Saisissez l’ID de segment  Gestionnaire de .</li></ul> |
| Ajouter nouvelle condition | Paramètre facultatif. |
| Dans le dernier | Paramètre facultatif. |
|  nom  | Nous vous recommandons d’utiliser le même nom de segment  Gestionnaire de  pour plus de cohérence, à moins que vous n’ajoutiez d’autres conditions à ce . |

## Étape 4 - Affectation du   à un Campaign dans le Gestionnaire d’annonces Facebook {#step-4-assign-audience-to-campaign}

Une fois le  personnalisé créé, affectez-le à une campagne publicitaire. Créez une nouvelle campagne ou modifiez une campagne existante. Vous trouverez votre nouveau  dans l’interface utilisateur de Facebook. Votre campagne publicitaire  les utilisateurs qui ont vu le pixel près de leur navigateur lors de leur visite sur votre site, si  Gestionnaire de  de les inclut dans le segment.

## Résumé {#summary}

Maintenant que vous avez affecté votre segment  Gestionnaire de  de à la destination WCA Facebook, le Gestionnaire de de  déclenche sélectivement le pixel WCA Facebook pour les utilisateurs d’un segment donné avec l’ID de segment correspondant dans le pixel afin de renseigner le Facebook. Cela se traduit par une augmentation progressive du  Facebook  plus la balise est déclenchée vers le de  de votre site applicable.

>[!NOTE]
>
> Si un utilisateur sort du segment  Gestionnaire de  de, il n’existe actuellement aucun moyen pour le Gestionnaire de de  d’informer Facebook de la suppression de l’utilisateur du personnalisé.

