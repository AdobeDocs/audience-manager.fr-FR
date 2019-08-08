---
description: Le créateur de destinations permet de créer des destinations d'URL avec cookie ou DNL. Vous ne pouvez pas créer de destinations de serveur à serveur (S 2 S) avec le créateur de destinations, mais vous pouvez gérer leurs mappages de segments. Contactez votre consultant pour configurer une destination S 2 S. Le créateur de destinations est situé dans Données d'audience > Destinations.
seo-description: Le créateur de destinations permet de créer des destinations d'URL avec cookie ou DNL. Vous ne pouvez pas créer de destinations de serveur à serveur (S 2 S) avec le créateur de destinations, mais vous pouvez gérer leurs mappages de segments. Contactez votre consultant pour configurer une destination S 2 S. Le créateur de destinations est situé dans Données d'audience > Destinations.
seo-title: Créateur de destinations
solution: Audience Manager
title: Créateur de destinations
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---


# Créateur de destinations {#destination-builder}

[!UICONTROL Destination Builder] vous permet de créer des destinations ou [!DNL URL] des destinations. Vous ne pouvez pas créer de destinations de serveur à serveur avec[!DNL S2S][!UICONTROL Destination Builder], mais vous pouvez gérer leurs mappages de segments. Contactez votre conseiller pour configurer [!DNL S2S] une destination. [!UICONTROL Destination Builder] se trouve **[!UICONTROL Audience Data > Destinations]** dans.

## Paramètres du créateur de destinations {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] se compose des sections et paramètres suivants :

| [!UICONTROL Destination Builder] Section | Rôle |
|--- |--- |
| Informations fondamentales | Utilisé pour nommer la destination, la décrire et sélectionner le type de destination ([!DNL URL] ou [!DNL cookie]) et la plateforme (tous, [!DNL Android]navigateur ou [!DNL iOS]). |
| Configuration | Inclut les commandes pour : <br/><ul><li>Transmission de données clé-valeur aux [!DNL URL] destinations. Vous pouvez envoyer des données sous la forme de paires clé-valeur individuelles ou sérialisées. Pour plus d'informations, reportez-vous à [la section Sérialisation](../../features/destinations/key-value-pairs.md#destination-serialized) de destination et [paires](../../features/destinations/key-value-pairs.md)Standard/Valeurs de série. </li><li>Eléments d'une destination de cookie, tels que le nom du cookie, le domaine, la taille, l'intervalle d'expiration, le format de données, etc.</li></ul> |
| Correspondances de segments | Permet de: <br/><ul><li>Recherchez, ajoutez et gérez les segments associés à tous les types de destination. </li><li>Définissez les priorités de remise sur des segments individuels (pour [!DNL cookie]les segments basés sur les segments uniquement).</li></ul> |

## Méthodes de remise des données {#data-delivery-methods}

Envoyez des informations à une destination en le transmettant par le biais d' [!DNL URL] une chaîne, en écrivant dans un navigateur [!DNL cookie]ou en transférant des données serveur à serveur hors ligne.

* [!DNL URL] et les destinations basées sur cookie transmettent les données de manière synchrone lorsqu'un utilisateur agit sur une page.
* La transmission de données serveur à serveur est asynchrone et peut survenir longtemps après la sortie de la page par un utilisateur. Le type de livraison que vous sélectionnez dépend des besoins de votre entreprise et de la manière dont un partenaire de données particulier souhaite ou peut recevoir des données.

Pour [plus d'informations, voir Choix d'un type](../../features/destinations/destinations.md) de destination.