---
description: Cette page illustre le processus de création de pixels WCA (Web Website Custom Audiences) à des fins d'envoi de segments d'audience Audience Manager basés sur le Web à Facebook pour le ciblage publicitaire en ligne avec une transparence améliorée.
seo-description: Cette page illustre le processus de création de pixels WCA (Web Website Custom Audiences) à des fins d'envoi de segments d'audience Audience Manager basés sur le Web à Facebook pour le ciblage publicitaire en ligne avec une transparence améliorée.
seo-title: Intégration de Facebook WCA
solution: Audience Manager
title: Intégration de Facebook WCA
translation-type: tm+mt
source-git-commit: 56999c1968a486bed0e2e672a4de1774d049e09d

---


# Facebook WCA Integration {#facebook-wca-integration}

Cette page illustre le processus de création de pixels WCA (Web Website Custom Audiences) à des fins d&#39;envoi de segments d&#39;audience Audience Manager basés sur le Web à Facebook pour le ciblage publicitaire en ligne avec une transparence améliorée.

## Aperçu {#overview}

[Les audiences personnalisées Facebook (WCA)](https://www.facebook.com/business/help/449542958510885) vous permettent de créer une liste de personnes qui ont visité certaines pages ou ont effectué des actions spécifiques sur votre site Web. Audience Manager active l&#39;activation dans WCA à l&#39;aide de destinations URL. Vous pouvez configurer une intégration basée sur un pixel personnalisé pour envoyer des audiences Web à Facebook pour le ciblage.

![Intégration de Facebook WCA](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> This capability requires that you select the Website audience for social platforms option in [URL destinations](/help/using/features/destinations/manage-destinations.md#configure-url-destination). Les plateformes sociales exigent que les informations sur les référents ne soient pas masquées lorsqu&#39;elles sont envoyées à leur plateforme. Veuillez tenir compte du fait que la plateforme/partenaire de destination sera en mesure de voir les informations contenues dans l&#39;URL de votre référent.

## Conditions préalables {#prerequisites}

1. Compte publicitaire Facebook
2. Segments Audience Manager prêts à être attribués à votre nouvelle destination Facebook. Here is [how to create a segment](/help/using/features/segments/segment-builder.md) in the Audience Manager UI.
3. Adobe Experience Cloud ID Service (ECID) version 4.1.0 ou ultérieure. Download the latest version **[here](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. Audience Manager Data Integration Library (DIL) version 9.0 or newer, downloadable from **[here](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Alternatively, if you use [Server-Side Forwarding (SSF)](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) to import data into Audience Manager, you must use AppMeasurement version 2.12 or newer. Download AppMeasurement using the [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).

We recommend that you install or upgrade the libraries in steps 3 and 4 using [Adobe Launch](https://docs.adobelaunch.com/) or [Adobe Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/).

## Step 1 - Create a Facebook Destination in Audience Manager {#step-1-create-facebook-destination}

Créez une nouvelle destination d&#39;URL dans Audience Manager et nommez-la Custom Website Custom Audiences. Utilisez les paramètres ci-dessous lors de la création de la destination. You can also refer to the [Configure a URL Destination](/help/using/features/destinations/manage-destinations.md#configure-url-destination) page.

**Informations fondamentales**

* **Catégorie**: Personnalisé
* **Type**: URL
* Select the **Auto-fill Destination Mapping** check box, then select **Segment ID**.

**Étiquettes d&#39;exportation des données**

Select the option **This destination may enable a combination with personally identifiable information (PII)**.

>[!NOTE]
>
> Cette étiquette d&#39;exportation empêche l&#39;inclusion des données tierces et des données provenant des graphiques de périphériques dans les segments.

**Configuration**

* **Type d&#39;URL**: Sélectionnez **Audience Web pour les plateformes sociales**. En sélectionnant cette option d&#39;URL, Audience Manager n&#39;assombrit pas les informations sur l&#39;URL du référent lors du déclenchement d&#39;un pixel WCA Facebook.
* **Sérialiser**: Sélectionnez **Activer**.
* In the **Base URL** and **Secure URL** field, enter the Facebook WCA pixel.
* **Délimiteur**: ,

Base URL example: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Exemple de pixel déclenché à partir de la page. Cet exemple montre un utilisateur qui se qualifie pour trois segments Audience Manager, avec les identifiants 3401321, 2993399, 3263410 :

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| Paramètre | Description |
---------|----------|
| `id` | Votre ID de pixel Facebook, que vous trouverez dans l&#39;interface utilisateur du Gestionnaire de publicités Facebook lors de la création de pixels d&#39;audience. |
| `ev` | Événement. Valeur arbitraire qui apparaîtra dans l&#39;interface utilisateur du gestionnaire de publicités Facebook une fois que le pixel commence à se déclencher sur le site. See the Include item in [Step 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience), for more information. |
| `cd[segID]` | Paramètre supplémentaire qui commencera à remplir l&#39;interface utilisateur de Facebook Manager Manager une fois que le pixel commence à se déclencher sur le site. `segID` est également arbitraire. |
| `%ALIAS%` | Une macro Audience Manager qui sera remplacée dynamiquement par les identifiants de segments Audience Manager que le visiteur du site qualifie pour, délimités par la virgule, |

La configuration de destination de l&#39;URL doit ressembler à l&#39;image ci-dessous :

![Configuration de la destination](/help/using/integration/assets/facebook-wca.png)

Enregistrez la destination. Then, you can proceed to the **Segment Mappings** step.

## Step 2 - Segment Mappings - Map Segment to Destination {#step-2-segment-mappings}

In the [Configure URL destination](/help/using/features/destinations/manage-destinations.md#configure-url-destination) workflow, map the applicable segment to your newly created destination. Notez que la valeur de mappage est renseignée automatiquement avec l&#39;identifiant de segment Audience Manager.

Entrez une date de fin le cas échéant, sinon laissez vide sans date de fin.

## Step 3 - Create an Audience within Facebook Ads Manager {#step-3-create-audience}

See [Create a Website Custom Audience](https://www.facebook.com/business/help/666509013483225) in the Facebook help documentation. Sélectionnez les options Créer un public dans le tableau ci-dessous :


| Élément | Description |
---------|----------|
| Trafic sur le site Web | Combinaison personnalisée |
| Inclure | <ul><li>Select **Event** &gt; Select **Adobe-Audience-Manager-Segment**. Il s&#39;agissait de la valeur du paramètre ev dans l&#39;exemple de pixel de l&#39;étape 1. Note that if the pixel is yet to fire, the **Event** option or **Adobe-Audience-Manager-Segment** may not appear in the Facebook UI.</li><li>Add a parameter: Select `segID`.</li><li><p>Select the **contains** operator.</p><p>Cela est important, étant donné que les visiteurs peuvent remplir plusieurs critères, il se peut que le paramètre pixel contienne plusieurs ID de segment. L&#39;utilisation de l&#39;opérateur égal (=) peut ne pas qualifier vos visiteurs pour l&#39;audience et vous constaterez un volume inférieur.</p></li><li>Ajoutez une valeur : Saisissez l&#39;identifiant de segment Audience Manager.</li></ul> |
| Ajouter une nouvelle condition | Paramètre facultatif. |
| Dans le dernier | Paramètre facultatif. |
| Nom du public | Nous vous recommandons d&#39;utiliser le même nom de segment Audience Manager pour une cohérence, sauf si vous ajoutez des conditions supplémentaires à ce public. |

## Step 4 - Assign the Audience to a Campaign in Facebook Ads Manager {#step-4-assign-audience-to-campaign}

Après avoir créé l&#39;audience personnalisée, affectez-la à une campagne publicitaire. Créez une campagne ou modifiez une campagne existante ; le public nouvellement créé est répertorié dans l&#39;interface utilisateur de Facebook. Votre campagne publicitaire cible les utilisateurs qui ont vu le pixel se déclencher sur leur navigateur lors de la visite de votre site, si Audience Manager les inclut dans le segment.

## Résumé {#summary}

Maintenant que vous avez affecté votre segment Audience Manager à la destination WCA Facebook, Audience Manager déclenche de manière sélective le pixel WCA Facebook pour les utilisateurs d&#39;un segment donné avec l&#39;identifiant de segment correspondant dans le pixel pour renseigner le public Facebook. Cela entraîne une augmentation progressive de l&#39;audience Facebook, plus la balise est déclenchée pour l&#39;audience concernée sur votre site.

>[!NOTE]
>
> Si un utilisateur quitte le segment Audience Manager, il n&#39;existe actuellement aucun moyen pour Audience Manager d&#39;informer Facebook de supprimer l&#39;utilisateur de l&#39;audience personnalisée.

