---
description: Cette page illustre le processus de création de pixels WCA (Audiences personnalisées du site Web Facebook) afin d’envoyer des segments d’audience du Gestionnaire d’Audiences Web à Facebook, pour le ciblage des annonces en ligne avec une transparence accrue.
seo-description: Cette page illustre le processus de création de pixels WCA (Audiences personnalisées du site Web Facebook) afin d’envoyer des segments d’audience du Gestionnaire d’Audiences Web à Facebook, pour le ciblage des annonces en ligne avec une transparence accrue.
seo-title: Intégration WCA Facebook
solution: Audience Manager
title: Intégration WCA Facebook
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Intégration WCA Facebook {#facebook-wca-integration}

Cette page illustre le processus de création de pixels WCA (Audiences personnalisées du site Web Facebook) afin d’envoyer des segments d’audience du Gestionnaire d’Audiences Web à Facebook, pour le ciblage des annonces en ligne avec une transparence accrue.

## Aperçu {#overview}

[Les Audiences personnalisées (WCA)](https://www.facebook.com/business/help/449542958510885) du site Web Facebook vous permettent de créer une liste de personnes qui ont visité certaines pages ou effectué certaines actions particulières sur votre site Web. Audience Manager active l’activation dans WCA à l’aide de destinations URL, avec lesquelles vous pouvez configurer une intégration personnalisée basée sur les pixels pour envoyer des audiences Web à Facebook pour le ciblage.

![Intégration WCA Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Cette fonctionnalité nécessite que vous sélectionniez l’option audience de site Web pour les plateformes sociales dans les destinations [](/help/using/features/destinations/create-url-destination.md)URL. Les plateformes sociales exigent que les informations de parrain soient démasquées lorsqu’elles sont envoyées sur leur plateforme. Sachez que cela signifie que la plateforme/le partenaire de destination pourra voir les informations dans votre URL de parrain.

## Conditions préalables {#prerequisites}

1. Compte d’annonce Facebook
2. Segments Audience Manager, prêts à être attribués à votre nouvelle destination Facebook. Voici [comment créer un segment](/help/using/features/segments/segment-builder.md) dans l’interface utilisateur d’Audience Manager.
3. Adobe Experience Platform Identity Service (ECID) version 4.1.0 ou ultérieure. Téléchargez la dernière version **[ici](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. La bibliothèque d’intégration des données d’Audience Manager (DIL) version 9.0 ou ultérieure peut être téléchargée **[ici](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Si vous utilisez le transfert côté[serveur (SSF)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)pour importer des données dans Audience Manager, vous devez utiliser AppMeasurement version 2.12 ou ultérieure. Téléchargez AppMeasurement à l’aide du Gestionnaire[de code](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html)Analytics.

Nous vous recommandons d’installer ou de mettre à niveau les bibliothèques des étapes 3 et 4 à l’aide d’ [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) ou de la gestion [dynamique des balises](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html)Adobe.

## Etape 1 - Création d’une destination Facebook dans Audience Manager {#step-1-create-facebook-destination}

Créez une destination d’URL dans le Gestionnaire d’Audiences et nommez-la Audiences personnalisées du site Web Facebook. Utilisez les paramètres ci-dessous lors de la création de la destination. Vous pouvez également vous reporter à la page [Configurer une URL de destination](/help/using/features/destinations/create-url-destination.md) .

**Informations fondamentales**

* **Catégorie**: Personnalisé
* **Type**: URL
* Activez la case à cocher Mappage **de destination** automatique, puis sélectionnez ID **de** segment.

**Étiquettes des exportations de données**

Sélectionnez l’option **Cette destination peut permettre une combinaison avec des informations d’identification personnelle (PII)**.

>[!NOTE]
>
> Cette étiquette d’exportation empêche l’inclusion dans les segments des données et données tierces dérivées des graphiques de périphérique.

**Configuration**

* **Type** d’URL : Sélectionnez audience de **site Web pour les plateformes** sociales. En sélectionnant cette option de type d’URL, Audience Manager n’obscurcit pas les informations d’URL du parrain lors du déclenchement d’un pixel WCA Facebook.
* **Sérialiser**: Sélectionnez **Activer**.
* Dans les champs URL **de** base et URL **** sécurisée, saisissez le pixel Facebook WCA.
* **Délimiteur**: ,

Exemple d’URL de base : `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Exemple de pixel déclenché à partir de la page. Cet exemple montre un utilisateur qui est admissible pour trois segments Audience Manager, avec les ID 3401321, 2993399, 3263410 :

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| Paramètre | Description |
---------|----------|
| `id` | Votre ID de pixel Facebook, que vous trouverez dans l’interface utilisateur du gestionnaire d’annonces Facebook lors de la création de pixels d’audience. |
| `ev` | Événement. Il s’agit d’une valeur arbitraire qui apparaîtra dans l’interface utilisateur du gestionnaire d’annonces Facebook une fois que le pixel commencera à se déclencher sur le site. Pour plus d’informations, voir l’élément Inclure à l’ [étape 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience). |
| `cd[segID]` | Un autre paramètre, qui commencera à être renseigné dans l’interface utilisateur du gestionnaire d’annonces Facebook une fois que le pixel commencera à se déclencher sur le site. `segID` est aussi arbitraire. |
| `%ALIAS%` | Une macro Audience Manager, qui sera remplacée dynamiquement par les ID de segment Audience Manager pour lesquels le visiteur du site est admissible, délimités par une virgule, |

La configuration de la destination de l’URL doit se présenter dans l’image ci-dessous :

![Configuration de destination](/help/using/integration/assets/facebook-wca.png)

Enregistrez la destination. Ensuite, vous pouvez passer à l’étape Correspondances **des** segments.

## Étape 2 - Mappages de segments - Mapper un segment à la destination {#step-2-segment-mappings}

Dans le processus [Configurer la destination](/help/using/features/destinations/create-url-destination.md) de l’URL, mappez le segment applicable à votre destination nouvellement créée. Notez que la valeur de mappage est automatiquement renseignée avec l’ID de segment du Gestionnaire d’Audiences.

Entrez une date de fin, le cas échéant, ou laissez vide pour ne pas saisir de date de fin.

## Etape 3 - Création d’une Audience dans le Gestionnaire d’annonces Facebook {#step-3-create-audience}

Voir [Création d’une Audience](https://www.facebook.com/business/help/666509013483225) personnalisée d’un site Web dans la documentation d’aide de Facebook. Sélectionnez les options Créer une Audience dans le tableau ci-dessous :


| Élément | Description |
---------|----------|
| Trafic du site Web | Combinaison personnalisée |
| Inclure | <ul><li>Sélectionnez **Événement** > Sélectionner **Adobe-Audience-Manager-Segment**. Il s’agit de la valeur du paramètre ev dans l’exemple de pixel de l’étape 1. Notez que si le pixel n’est pas encore déclenché, l’option **Événement** ou **Adobe-Audience-Manager-Segment** peut ne pas apparaître dans l’interface utilisateur de Facebook.</li><li>Ajouter un paramètre : Sélectionnez `segID`.</li><li><p>Sélectionnez l’opérateur **contient** .</p><p>Ceci est important, puisque les visiteurs peuvent être inclus dans plusieurs segments, il peut y avoir plusieurs ID de segment dans le paramètre pixel. L&#39;utilisation de l&#39;opérateur égal (=) peut ne pas qualifier vos visiteurs pour l&#39;audience et vous obtiendrez un volume inférieur.</p></li><li>Ajouter une valeur : Saisissez l’ID du segment Gestionnaire d’Audiences.</li></ul> |
| Ajouter nouvelle condition | Paramètre facultatif. |
| Dans le dernier | Paramètre facultatif. |
| Nom de l’Audience | Nous vous recommandons d’utiliser le même nom de segment Audience Manager pour assurer la cohérence, sauf si vous ajoutez des conditions supplémentaires à cette Audience. |

## Etape 4 - Affectation de l’Audience à un Campaign dans le Gestionnaire d’annonces Facebook {#step-4-assign-audience-to-campaign}

Après avoir créé l’Audience personnalisée, affectez-la à une campagne publicitaire. Créez une nouvelle campagne ou modifiez une campagne existante. Votre Audience nouvellement créée est répertoriée dans l’interface utilisateur de Facebook. Votre campagne publicitaire cible les utilisateurs qui ont vu le pixel se déclencher sur leur navigateur lors de leur visite sur votre site, si Audience Manager les inclut dans le segment.

## Résumé {#summary}

Maintenant que vous avez affecté votre segment Audience Manager à la destination WCA de Facebook, Audience Manager déclenche sélectivement le pixel WCA de Facebook pour les utilisateurs d’un segment donné avec l’ID de segment correspondant dans le pixel pour renseigner l’Audience Facebook. Cela se traduit par une augmentation progressive de l’Audience Facebook, plus la balise est déclenchée sur l’audience applicable de votre site.

>[!NOTE]
>
> Si un utilisateur sort du segment Gestionnaire d’Audiences, il n’existe actuellement aucun moyen pour Audience Manager d’informer Facebook de sa suppression de l’Audience personnalisée.

