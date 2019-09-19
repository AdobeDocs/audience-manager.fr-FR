---
description: Le créateur de destinations vous permet de créer des destinations URL basées sur des cookies ou DNL. Vous ne pouvez pas créer de destinations serveur à serveur (S2S) avec le créateur de destinations, mais vous pouvez gérer leurs mappages de segments. Contactez votre consultant pour configurer une destination S2S. Le créateur de destinations se trouve sous Données d’audience > Destinations.
seo-description: Le créateur de destinations vous permet de créer des destinations URL basées sur des cookies ou DNL. Vous ne pouvez pas créer de destinations serveur à serveur (S2S) avec le créateur de destinations, mais vous pouvez gérer leurs mappages de segments. Contactez votre consultant pour configurer une destination S2S. Le créateur de destinations se trouve sous Données d’audience > Destinations.
seo-title: Créateur de destinations
solution: Audience Manager
title: Créateur de destinations
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---


# Créateur de destinations {#destination-builder}

[!UICONTROL Destination Builder] permet de créer des destinations ou basées sur des cookies. [!DNL URL] Vous ne pouvez pas créer de destinations serveur à serveur ([!DNL S2S]) avec [!UICONTROL Destination Builder], mais vous pouvez gérer leurs mappages de segments. Contactez votre consultant pour configurer une [!DNL S2S] destination. [!UICONTROL Destination Builder] se trouve dans **[!UICONTROL Audience Data > Destinations]**.

## Paramètres du créateur de destinations {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] se compose des sections et paramètres suivants :

| [!UICONTROL Destination Builder] Section | Rôle |
|--- |--- |
| Informations fondamentales | Utilisé pour nommer la destination, la décrire et sélectionner le type de destination ([!DNL URL] ou [!DNL cookie]) et la plateforme (all, [!DNL Android], browser ou [!DNL iOS]). |
| Configuration | Inclut des contrôles pour : <br/><ul><li>Transmission de données de valeur clé vers [!DNL URL] les destinations. Vous pouvez envoyer des données sous forme de paires clé-valeur individuelles ou sérialisées. Pour plus d'informations, reportez-vous à la section Sérialisation [de](../../features/destinations/key-value-pairs.md#destination-serialized) destination et paires [valeur-clé](../../features/destinations/key-value-pairs.md)standard et valeur-clé de série. </li><li>Éléments d’une destination de cookie, tels que le nom du cookie, le domaine, la taille, l’intervalle d’expiration, le format de données, etc.</li></ul> |
|  Mappages de segments | Permet de: <br/><ul><li>Recherchez, ajoutez et gérez les segments associés à tous les types de destination. </li><li>Définissez les priorités de remise sur les segments individuels (pour les segments [!DNL cookie]basés uniquement).</li></ul> |

## Méthodes de remise des données {#data-delivery-methods}

Envoyez des informations à une destination en les transmettant par le biais d’une [!DNL URL] chaîne, en les écrivant dans un navigateur [!DNL cookie]ou par le biais de transferts de données entre serveurs hors ligne.

* [!DNL URL] et les destinations basées sur des cookies transmettent les données de manière synchrone, lorsqu’un utilisateur effectue une action sur une page.
* La transmission de données serveur à serveur est asynchrone et peut survenir longtemps après qu’un utilisateur a quitté la page. Le type de remise sélectionné dépend des besoins de votre entreprise et de la manière dont un partenaire de données spécifique souhaite ou peut recevoir les données.

Voir [Comment choisir un type](../../features/destinations/destinations.md) de destination pour en savoir plus.