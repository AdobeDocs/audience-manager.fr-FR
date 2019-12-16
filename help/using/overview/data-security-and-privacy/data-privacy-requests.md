---
description: Ce document décrit les détails techniques liés à la conformité aux règles de confidentialité des données pour Audience Manager.
seo-description: Ce document décrit les détails techniques liés à la conformité aux règles de confidentialité des données pour Audience Manager.
seo-title: Demandes de confidentialité de données
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: Demandes de confidentialité de données
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: ff4bf70c9012f99289ea82824a552db97430fbf2

---


# Demandes de confidentialité de données {#data-privacy-requests}

## Aperçu {#overview}

Ce document présente la gestion de la confidentialité des données individuelles et des demandes d’exclusion que vous pouvez envoyer à Audience Manager via l’interface utilisateur [de](https://gdprui.cloud.adobe.io/) Privacy Service et l’interface **[!DNL Privacy Service API]**.

Ces outils vous permettent d'envoyer des demandes de confidentialité de données aux consommateurs effectuées en vertu du RDPC et de l'ACCP.

Avant de lire cet article, nous vous recommandons de consulter le glossaire [du](../data-security-and-privacy/aam-gdpr-glossary.md) RDPC et le glossaire [de l’](aam-ccpa-glossary.md)ACCP afin de mieux comprendre la terminologie utilisée ici.

Vous pouvez envoyer des requêtes individuelles pour accéder aux données du client et les supprimer d’Audience Manager de deux manières :

* Via l’interface utilisateur [de](https://gdprui.cloud.adobe.io/)Privacy Service. Consultez la documentation [ici](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Par le **[!DNL Privacy Service API]**. Consultez la documentation [ici](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) et la référence API [ici](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

Lors de l’envoi de requêtes de confidentialité de données individuelles, vous pouvez envoyer les identifiants (ID) Audience Manager, comme décrit dans la section Identifiants **[](data-privacy-ids.md)** Audience Manager, ainsi que leurs identifiants d’espace de noms respectifs (ID de source de données).

Le service [](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) de confidentialité prend en charge deux types de requêtes : demandes d’accès aux données et de suppression de données.

## Demandes d’accès aux données {#access-data}

Vous pouvez envoyer des demandes d’accès aux données individuelles par l’intermédiaire de l’interface utilisateur [de](https://gdprui.cloud.adobe.io/) Privacy Service (documentation [ici](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) ou en appelant le [!DNL Privacy Service API] (documentation [ici](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) et  référence ici).[!DNL API][](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)

L’interface utilisateur [de](https://gdprui.cloud.adobe.io/) Privacy Service vous permet de créer de nouvelles demandes de tâche à l’aide du [!UICONTROL Request Builder] formulaire ou en téléchargeant un [!DNL JSON] fichier.

Pour voir à quoi ressemble un [!DNL JSON] fichier valide, vous pouvez [télécharger un exemple de fichier JSON](../data-security-and-privacy/assets/access_request.json).

Nous comprenons votre engagement à respecter vos demandes de confidentialité dans le délai imparti par la loi.

## Demandes de suppression de données{#delete-data}

Vous pouvez envoyer des demandes de suppression de données par l’intermédiaire de l’interface utilisateur [de](https://gdprui.cloud.adobe.io/) Privacy Service (documentation [ici](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) ou en appelant le [!DNL Privacy Service API] (documentation [ici](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) et référence API ici).[](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)

L’interface utilisateur [de](https://gdprui.cloud.adobe.io/) Privacy Service vous permet de créer de nouvelles demandes de tâche à l’aide du [!UICONTROL Request Builder] formulaire ou en téléchargeant un [!DNL JSON] fichier.

Pour voir à quoi ressemble un [!DNL JSON] fichier valide, vous pouvez [télécharger un exemple de fichier JSON](../data-security-and-privacy/assets/access_request.json).

Adobe comprend que vous vous engagez à respecter vos demandes de confidentialité des données dans les 30 jours. C’est pourquoi Adobe s’engage à traiter votre demande de suppression de données le plus rapidement possible.

En réponse aux demandes de suppression de données du client, Audience Manager supprime les caractéristiques et les segments associés à l’identifiant Audience Manager inclus dans la demande. En outre, les identifiants Audience Manager respectifs pour la personne ayant choisi de ne pas continuer la collecte de données par Audience Manager et les mappages d’ID respectifs seront supprimés.

Lorsque vous envoyez des identifiants déclarés, tels que [!DNL CRM] des identifiants inter-périphériques ou des identifiants de cookie, dans les demandes de confidentialité des données, Audience Manager effectue la suppression nécessaire sur tous les périphériques liés (jusqu’à 100 périphériques par identifiant déclaré).

Audience Manager tente d’avertir les partenaires d’activation des demandes de suppression en leur envoyant des informations de non-segmentation pour les objets de données demandant la suppression de certaines données. Cependant, certains partenaires d’activation :

1. Impossible de prendre en charge les requêtes de non-segmentation (ou de suppression de segment) d’Audience Manager et/ou
2. Ne peuvent pas recevoir de mises à jour d’Audience Manager avec une fréquence inférieure à 30 jours. Dans ce cas, les clients d’Audience Manager ne peuvent pas envoyer de demandes de suppression aux partenaires d’activation de manière automatisée via Audience Manager.

Dans ce cas, vous ne pouvez pas envoyer de demandes de suppression aux partenaires d’activation de manière automatisée via Audience Manager.

Téléchargez notre feuille [Excel de](assets/AAM-Partners-October2019.xlsx) partenaire pour savoir quels partenaires d’activation d’Audience Manager prennent en charge le non-segmentation.

## Demandes d’exclusion {#opt-out-requests}

Audience Manager prend en charge les normes à l’échelle du secteur en ce qui concerne la gestion des exclusions. Lisez la suite pour obtenir des informations complètes sur les types d’exclusion pris en charge par Audience Manager.

Bien que les demandes d’accès aux données et de suppression soient traitées par le biais de [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html), les demandes d’exclusion sont actuellement prises en charge par l’API DCS. Lisez la suite pour en savoir plus sur les appels d’API d’exclusion.

### Demandes d’exclusion globales

L’exclusion globale représente une exclusion dans Audience Manager et dans d’autres solutions Adobe Experience Cloud pour toutes les marques. Le tableau ci-dessous répertorie les méthodes utilisées pour l’exclusion globale :

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exclusion pour </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>La page <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Vos choix de confidentialité </a> propose des fonctionnalités d’1 clic qui permettent aux utilisateurs finaux de contrôler et d’exclure la collecte de données par les solutions publicitaires Adobe Experience Cloud (y compris Audience Manager). Consultez plus particulièrement la section réservée aux <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> clients professionnels </a> de la page Choix de confidentialité. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Appels d’API directs vers Audience Manager </p> </td> 
   <td colname="col2"> <p>Vos utilisateurs peuvent s’exclure de la collecte de données par toutes les marques d’Audience Manager en appelant l’API DCS ci-dessous et en incluant l’ID utilisateur <a href="../../reference/ids-in-aam.md"> d’Audience Manager </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Par conséquent, nous définirons <code>demdex=NOTARGET</code> et <code>dextp=NOTARGET</code> les cookies pour l’ID utilisateur d’Audience Manager envoyé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Appareils mobiles </p> </td> 
   <td colname="col2"> <p>Voir les paramètres d’exclusion et de confidentialité pour : </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Périphériques Android </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> Appareils iOS </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Vos utilisateurs finaux peuvent également se désabonner de la collecte de données globale en visitant les sites Web de nos partenaires du secteur.

* [La Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Suite aux demandes d’exclusion décrites ci-dessus :

* Audience Manager interrompt la collecte, la segmentation ou l’activation des données tant que l’utilisateur n’efface pas les cookies de son navigateur.
* Les données historiques sont supprimées du profil utilisateur au bout de 120 jours.

### Exclusion au niveau du partenaire avec appels d’ID déclarés

L’exclusion au niveau du partenaire vous permet d’exclure vos utilisateurs de la collecte de données par des partenaires Audience Manager spécifiques. Vous pouvez envoyer des demandes d’exclusion au niveau du partenaire pour les ID inter-périphériques, y compris les ID CRM et les adresses électroniques hachées.

Suite à une exclusion au niveau du partenaire avec un appel d’ID déclaré :

* L’ID [](../../reference/ids-in-aam.md) CRM est retiré de la collecte de données ;
* Le dernier ID de périphérique (ID[utilisateur unique](../../reference/ids-in-aam.md)Audience Manager) lié à l’ID [](../../reference/ids-in-aam.md) CRM est retiré de la collecte de données.
* Audience Manager cessera la collecte, la segmentation ou l’activation des données à partir de l’ID CRM et du dernier ID de périphérique lié à l’ID CRM ;
* Audience Manager dissocie l’ID CRM et le dernier ID de périphérique sélectionnés de tous les segments ;
* Les partenaires de destination reçoivent la demande de non-segmentation pour l’ID CRM et le dernier ID de périphérique. La non-segmentation fonctionne pour les destinations [en temps](data-privacy-requests.md#aam-partners-with-unsegmentation) réel et par lot.
* Aucune donnée d’historique n’est supprimée.

Lorsqu’Audience Manager reçoit une demande d’exclusion au niveau du partenaire, le fichier JSON renvoyé par le serveur de collecte de données contient le code [d’erreur 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), avec le message [!UICONTROL "Encountered opt out tag"], au lieu de l’ID utilisateur d’Audience Manager.

Vous pouvez faire une demande d’exclusion d’ID déclarée avec les paires `d_cid` et `d_cid_ic` clé-valeur. Les paramètres hérités, comme `d_dpid` et `d_dpuuid` fonctionnent toujours, sont considérés comme obsolètes. Voir [CID remplace DPID et DPUUID](../../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

#### Exclusion avec CID et CID_IC

Pour obtenir une description et une syntaxe, voir Variables [d’URL et Syntaxe pour les ID](../../features/declared-ids.md#variables-and-syntax)déclarés.

| Exclusion à l’aide de | Exemple de code |
|--- |--- |
| ID de fournisseur de données et ID d’utilisateur. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Code d’intégration et ID utilisateur. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Plusieurs paires clé-valeur d_cid et d_cid_ic. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Exclusion au niveau partenaire avec appels d'ID de périphérique

L’exclusion au niveau du partenaire vous permet d’exclure vos utilisateurs de la collecte de données par des partenaires Audience Manager spécifiques. Vous pouvez vous exclure de la collecte de données sur un ID de périphérique donné pour une marque en lançant les appels suivants à l’API [](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md)DCS :

| Exclusion à l’aide de | Exemple de code |
|--- |--- |
| Un ID utilisateur unique Audience Manager (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Un ID Experience Cloud (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

En savoir plus sur `uuid`Audience Manager `mid` et `imsOrgId` dans l’ [](/help/using/reference/ids-in-aam.md)index des identifiants.

Suite à une exclusion au niveau du partenaire avec un appel d’ID de périphérique :

* L’ID de périphérique est retiré de la collecte de données.
* Audience Manager interrompt la collecte, la segmentation ou l’activation des données pour le partenaire, à partir de l’ID du périphérique.
* Audience Manager dissocie l’ID de périphérique de tous les segments ;
* Les partenaires de destination reçoivent la demande de non-segmentation pour l’ID de périphérique. La non-segmentation fonctionne pour les destinations [en temps](data-privacy-requests.md#aam-partners-with-unsegmentation) réel et par lot.
* Aucune donnée d’historique n’est supprimée.

## Partenaires Audience Manager Avec Des Fonctionnalités D’Unsegmentation {#aam-partners-with-unsegmentation}

Afin de vous aider à automatiser vos demandes de confidentialité des données des consommateurs, Audience Manager tentera d’avertir les partenaires d’activation des demandes de suppression des objets de données en leur envoyant des informations de non-segmentation (ou de suppression de segment).

Cependant, certains de nos partenaires d’activation :

1. Impossible de prendre en charge les demandes de non-segmentation d’Audience Manager et/ou
2. Ne peuvent pas recevoir les mises à jour d’Audience Manager plus d’une fois par 30 jours.

Dans ce cas, vous ne pouvez pas envoyer de demandes de suppression aux partenaires d’activation de manière automatisée via Audience Manager.

Téléchargez notre feuille [Excel de](assets/AAM-Partners-December2019.xlsx) partenaire pour savoir quels partenaires d’activation d’Audience Manager prennent en charge le non-segmentation.

## Demandes de correction de données {#correction}

Dans la mesure où Audience Manager n’est pas la source des données, il existe un rôle limité pour la correction des données dans Audience Manager. La correction peut signifier que le consommateur a demandé à être soit disqualifié d'une caractéristique/segment incorrecte, soit qualifié à la caractéristique/segment désirée.

Les clients d’Audience Manager peuvent choisir de capturer les signaux/caractéristiques/segments pertinents par rapport aux profils d’utilisateur et d’envoyer ces informations par ingestion [de données](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) hors ligne à Audience Manager. Veuillez noter que l’utilisateur continuera à être qualifié pour la caractéristique d’origine et les segments s’il répète son comportement.
