---
description: Une présentation de DIL et de son fonctionnement.
seo-description: Une présentation de DIL et de son fonctionnement.
seo-title: Présentation de la bibliothèque d'intégration des données (DIL)
keywords: 'dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil dil, dil, dil, dil, '
solution: Audience Manager
title: Présentation de la bibliothèque d'intégration des données (DIL)
uuid: 77 b 12 f 35-81 e 4-4639-ada 6-bf 982 f 27 b 36 e
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# Présentation de la bibliothèque d'intégration des données (DIL){#understanding-the-data-integration-library-dil}

Présentation, prise en main et méthodes de code disponibles dans la bibliothèque de code DIL Audience Manager.

>[!IMPORTANT]
>
>Starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. Il repose sur le service d'ID pour la synchronisation des identifiants et les destinations d'URL. Une erreur se produit lorsque le service d'ID est absent, ancien ou non configuré.
>
>Nous vous recommandons d'utiliser Adobe Launch pour implémenter et gérer les bibliothèques du service DIL et Experience Cloud ID.

Vous pouvez toutefois télécharger les dernières versions d'Experience Cloud et DIL depuis notre page github. Voir les liens de téléchargement ci-dessous :

* Téléchargement du service [Experience Cloud ID](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Télécharger [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Objectif de DIL {#purpose-dil}

[!UICONTROL DIL] est une bibliothèque API. Vous pouvez le considérer comme un corps de code d'aide pour [!DNL Adobe Audience Manager]. Il n'est pas nécessaire d'utiliser [!DNL Audience Manager], mais les méthodes et fonctions [!UICONTROL DIL] fournies indiquent que vous n'avez pas à développer votre propre code pour envoyer des données. [!DNL Audience Manager] En outre [!UICONTROL DIL] , est différent de l'API fournie par le service [Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/). Ce service est conçu pour gérer l'identité des visiteurs dans différentes [!DNL Experience Cloud] solutions. Par contre, [!UICONTROL DIL] est conçu pour :

* Lancer des appels d'événement et envoyer des données au serveur de collecte [de données](../reference/system-components/components-data-collection.md).
* Envoyer des données aux [destinations](../features/destinations/destinations.md).

## Obtention et implémentation du code DIL {#get-implement-dil-code}

[!UICONTROL DIL] peut être téléchargé **[ici](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Please note that starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. Il repose sur le service d'ID pour la synchronisation des identifiants et les destinations d'URL. Une erreur se produit lorsque le service d'ID est absent, ancien ou non configuré.

Plutôt que de travailler et [!UICONTROL DIL] de configurer [!DNL Audience Manager] manuellement, nous vous recommandons d'utiliser [Adobe Launch](https://docs.adobelaunch.com/) à la place. [!DNL Adobe Launch] est l'outil d'implémentation recommandé, car il simplifie le déploiement, le placement et la gestion des versions du code. En savoir plus sur l'extension [Audience Manager](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) dans Adobe Launch.

Adobe Launch est le successeur d ['Adobe Dynamic Tag Manager](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM]).

## Exemple d'appel {#sample-code}

[!UICONTROL DIL] envoie des données [!DNL Audience Manager] à un appel d'événement. Un appel d'événement est une requête HTTP HTTP de votre page. Elle utilise une `POST` méthode pour envoyer des données dans le corps de la requête.

| Elément d'appel d'événement | Description |
|--- |--- |
| URL | Les appels d'événement DIL utilisent la syntaxe suivante : `https://adobe.demdex.net/event?_ts =`*`UNIX UTC timestamp`* |
| Corps | Comme illustré dans l'exemple ci-dessous, DIL transmet les données sous forme de paires clé-valeur. Les caractères de préfixe spéciaux identifient les paires clé-valeur comme gestionnaire d'audience ou variables partenaires.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Voir également :
* [Exigences en matière de préfixe pour les variables clés](../features/traits/trait-variable-prefixes.md)
* [Attributs pris en charge pour les appels d'API DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Liens associés

* [Cas d'utilisation DIL et exemples de code](/help/using/dil/dil-use-cases.md)
* [Méthodes DIL de niveau classe](/help/using/dil/dil-class-overview/dil-start.md)
* [Méthodes DIL au niveau de l'instance](/help/using/dil/dil-instance-methods.md)
* [Modules DIL](/help/using/dil/dil-modules.md)
* [Outils DIL](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)