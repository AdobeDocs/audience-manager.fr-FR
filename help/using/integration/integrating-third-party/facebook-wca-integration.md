---
description: Cette page illustre le processus de création de pixels WCA (Web Website Custom Audiences) à des fins d'envoi de segments d'audience Audience Manager basés sur le Web à Facebook pour le ciblage publicitaire en ligne avec une transparence améliorée.
seo-description: Cette page illustre le processus de création de pixels WCA (Web Website Custom Audiences) à des fins d'envoi de segments d'audience Audience Manager basés sur le Web à Facebook pour le ciblage publicitaire en ligne avec une transparence améliorée.
seo-title: Intégration de Facebook WCA
solution: Audience Manager
title: Intégration de Facebook WCA
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Intégration de Facebook WCA {#facebook-wca-integration}

Cette page illustre le processus de création de pixels WCA (Web Website Custom Audiences) à des fins d'envoi de segments d'audience Audience Manager basés sur le Web à Facebook pour le ciblage publicitaire en ligne avec une transparence améliorée.

## Aperçu {#overview}

[Les audiences personnalisées Facebook (WCA)](https://www.facebook.com/business/help/449542958510885) vous permettent de créer une liste de personnes qui ont visité certaines pages ou ont effectué des actions spécifiques sur votre site Web. Audience Manager active l'activation dans WCA à l'aide de destinations URL. Vous pouvez configurer une intégration basée sur un pixel personnalisé pour envoyer des audiences Web à Facebook pour le ciblage.

![Intégration de Facebook WCA](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Cette fonctionnalité nécessite de sélectionner l'audience du site Web pour les plateformes sociales dans [les destinations URL](/help/using/features/destinations/create-url-destination.md). Les plateformes sociales exigent que les informations sur les référents ne soient pas masquées lorsqu'elles sont envoyées à leur plateforme. Veuillez tenir compte du fait que la plateforme/partenaire de destination sera en mesure de voir les informations contenues dans l'URL de votre référent.

## Conditions préalables {#prerequisites}

1. Compte publicitaire Facebook
2. Segments Audience Manager prêts à être attribués à votre nouvelle destination Facebook. Voici [comment créer un segment](/help/using/features/segments/segment-builder.md) dans l'interface utilisateur d'Audience Manager.
3. Adobe Experience Cloud ID Service (ECID) version 4.1.0 ou ultérieure. Téléchargez la dernière version **[ici](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. Bibliothèque d'intégration de données Audience Manager (DIL) version 9.0 ou ultérieure, téléchargeable à partir **[de là](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Si vous utilisez le transfert côté [serveur (SSF)](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) pour importer des données dans Audience Manager, vous devez utiliser appmeasurement version 2.12 ou ultérieure. Téléchargez appmeasurement à l'aide du Gestionnaire de code [Analytics](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).

Nous vous recommandons d'installer ou de mettre à niveau les bibliothèques aux étapes 3 et 4 à l'aide [d'Adobe Launch](https://docs.adobelaunch.com/) ou [de la gestion dynamique des balises d'Adobe](https://marketing.adobe.com/resources/help/en_US/dtm/).

## Étape 1 - Création d'une destination Facebook dans Audience Manager {#step-1-create-facebook-destination}

Créez une nouvelle destination d'URL dans Audience Manager et nommez-la Custom Website Custom Audiences. Utilisez les paramètres ci-dessous lors de la création de la destination. Vous pouvez également faire référence à [la page Configurer une destination](/help/using/features/destinations/create-url-destination.md) d'URL.

**Informations fondamentales**

* **Catégorie**: Personnalisé
* **Type**: URL
* Cochez **la** case Remplissage automatique de la destination, puis sélectionnez **ID du segment**.

**Étiquettes d'exportation des données**

Sélectionnez l'option **Cette destination peut permettre une combinaison avec des informations d'identification personnelle**.

>[!NOTE]
>
> Cette étiquette d'exportation empêche l'inclusion des données tierces et des données provenant des graphiques de périphériques dans les segments.

**Configuration**

* **Type d'URL**: Sélectionnez **Audience Web pour les plateformes sociales**. En sélectionnant cette option d'URL, Audience Manager n'assombrit pas les informations sur l'URL du référent lors du déclenchement d'un pixel WCA Facebook.
* **Sérialiser**: Sélectionnez **Activer**.
* Dans le champ **URL de base** et **URL** sécurisée, saisissez le pixel WCA Facebook.
* **Délimiteur**: ,

Exemple d'URL de base : `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Exemple de pixel déclenché à partir de la page. Cet exemple montre un utilisateur qui se qualifie pour trois segments Audience Manager, avec les identifiants 3401321, 2993399, 3263410 :

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| Paramètre | Description |
---------|----------|
| `id` | Votre ID de pixel Facebook, que vous trouverez dans l'interface utilisateur du Gestionnaire de publicités Facebook lors de la création de pixels d'audience. |
| `ev` | Événement. Valeur arbitraire qui apparaîtra dans l'interface utilisateur du gestionnaire de publicités Facebook une fois que le pixel commence à se déclencher sur le site. Pour plus d'informations, voir l'élément Inclure à [l'étape 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience). |
| `cd[segID]` | Paramètre supplémentaire qui commencera à remplir l'interface utilisateur de Facebook Manager Manager une fois que le pixel commence à se déclencher sur le site. `segID` est également arbitraire. |
| `%ALIAS%` | Une macro Audience Manager qui sera remplacée dynamiquement par les identifiants de segments Audience Manager que le visiteur du site qualifie pour, délimités par la virgule, |

La configuration de destination de l'URL doit ressembler à l'image ci-dessous :

![Configuration de la destination](/help/using/integration/assets/facebook-wca.png)

Enregistrez la destination. Vous pouvez ensuite passer à l' **étape Correspondances** de segment.

## Etape 2 - Correspondances de segments - Mappage de segment à destination {#step-2-segment-mappings}

Dans [le flux de](/help/using/features/destinations/create-url-destination.md#) travail de configuration de l'URL, faites correspondre le segment applicable à votre nouvelle destination. Notez que la valeur de mappage est renseignée automatiquement avec l'identifiant de segment Audience Manager.

Entrez une date de fin le cas échéant, sinon laissez vide sans date de fin.

## Étape 3 - Création d'une audience dans le gestionnaire des publicités Facebook {#step-3-create-audience}

Voir [Création d'une audience personnalisée du site Web](https://www.facebook.com/business/help/666509013483225) dans la documentation d'aide Facebook. Sélectionnez les options Créer un public dans le tableau ci-dessous :


| Élément | Description |
---------|----------|
| Trafic sur le site Web | Combinaison personnalisée |
| Inclure | <ul><li>Sélectionnez **Evénement** &gt; Sélectionner **Adobe-Audience-Manager-Segment**. Il s'agissait de la valeur du paramètre ev dans l'exemple de pixel de l'étape 1. Notez que si le pixel n'est pas encore déclenché, l'option **Evénement** ou **Adobe-Audience-Manager-Segment** peut ne pas apparaître dans l'interface utilisateur Facebook.</li><li>Ajoutez un paramètre : Sélectionnez `segID`.</li><li><p>Sélectionnez l'opérateur **contient** .</p><p>Cela est important, étant donné que les visiteurs peuvent remplir plusieurs critères, il se peut que le paramètre pixel contienne plusieurs ID de segment. L'utilisation de l'opérateur égal (=) peut ne pas qualifier vos visiteurs pour l'audience et vous constaterez un volume inférieur.</p></li><li>Ajoutez une valeur : Saisissez l'identifiant de segment Audience Manager.</li></ul> |
| Ajouter une nouvelle condition | Paramètre facultatif. |
| Dans le dernier | Paramètre facultatif. |
| Nom du public | Nous vous recommandons d'utiliser le même nom de segment Audience Manager pour une cohérence, sauf si vous ajoutez des conditions supplémentaires à ce public. |

## Étape 4 - Affectation de l'audience à une campagne dans le gestionnaire des publicités Facebook {#step-4-assign-audience-to-campaign}

Après avoir créé l'audience personnalisée, affectez-la à une campagne publicitaire. Créez une campagne ou modifiez une campagne existante ; le public nouvellement créé est répertorié dans l'interface utilisateur de Facebook. Votre campagne publicitaire cible les utilisateurs qui ont vu le pixel se déclencher sur leur navigateur lors de la visite de votre site, si Audience Manager les inclut dans le segment.

## Résumé {#summary}

Maintenant que vous avez affecté votre segment Audience Manager à la destination WCA Facebook, Audience Manager déclenche de manière sélective le pixel WCA Facebook pour les utilisateurs d'un segment donné avec l'identifiant de segment correspondant dans le pixel pour renseigner le public Facebook. Cela entraîne une augmentation progressive de l'audience Facebook, plus la balise est déclenchée pour l'audience concernée sur votre site.

>[!NOTE]
>
> Si un utilisateur quitte le segment Audience Manager, il n'existe actuellement aucun moyen pour Audience Manager d'informer Facebook de supprimer l'utilisateur de l'audience personnalisée.

