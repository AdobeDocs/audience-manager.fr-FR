---
description: Une destination de cookie renvoie et écrit des données dans un cookie dans le navigateur de l’utilisateur. Le cookie contient des données qui peuvent être lues par d’autres plateformes ayant accès à la page. Suivez ces instructions pour créer une destination de cookie avec [!UICONTROL Destination Builder].
seo-description: Une destination de cookie renvoie et écrit des données dans un cookie dans le navigateur de l’utilisateur. Le cookie contient des données qui peuvent être lues par d’autres plateformes ayant accès à la page. Suivez ces instructions pour créer une destination de cookie avec [!UICONTROL Destination Builder].
seo-title: Configuration d’une destination de cookie
solution: Audience Manager
title: Configuration d’une destination de cookie
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# Configuration d’une destination de cookie {#create-cookie-destination}

Une destination de cookie renvoie et écrit des données dans un cookie dans le navigateur de l’utilisateur. Le cookie contient des données qui peuvent être lues par d’autres plateformes ayant accès à la page. Suivez ces instructions pour créer une destination de cookie avec [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

Pour créer une destination de cookie, accédez aux sections **[!UICONTROL Audience Data > Destinations > Create New Destination]** et complétez-les comme décrit ci-dessous.

## Informations fondamentales {#basic-information}

Cette section contient des champs et des options qui démarrent le processus de création de la destination du cookie. Pour compléter cette section :

1. Cliquez sur **[!UICONTROL Basic Information]** pour afficher les commandes.
2. Nommez la destination. Evitez les abréviations et les caractères spéciaux.
3. *(Facultatif)* Décrivez la destination. Une description concise est un moyen efficace de définir ou de fournir plus d’informations sur une destination.
4. Dans la **[!UICONTROL Category]** liste, choisissez **[!UICONTROL Custom]**.
5. Dans la **[!UICONTROL Environment]** liste, sélectionnez **[!UICONTROL Browser]**. Vous ne pouvez pas configurer de destinations de cookies pour les environnements mobiles natifs, tels que les applications Android ou iOS.
6. Dans la **[!UICONTROL Type]** liste, cliquez sur **[!UICONTROL Cookie]**.
7. *(Facultatif)* Sélectionnez un **[!UICONTROL Auto-fill Destination Mapping]**. Les options incluent :
   * **[!UICONTROL Segment ID]**: Ajoute et envoie automatiquement l’ID de segment à la destination.
   * **[!UICONTROL Integration Code Value]**: Ajoute et envoie automatiquement le code d’intégration de segment au mappage de destination. Le code d’intégration est un identifiant unique créé et utilisé par le client. Elle est limitée à 255 caractères au maximum.
8. Cliquez sur **[!UICONTROL Next]** pour accéder aux [!UICONTROL Configuration] paramètres ou sur **[!UICONTROL Data Export Labels]** pour appliquer des contrôles d’exportation à la destination.

## Étiquettes d’exportation de données {#data-export-labels-cookies}

Cette section contient des options qui appliquent des contrôles [d’exportation de](../../features/data-export-controls.md) données à une destination de cookie. Ignorez cette étape si vous n’utilisez pas les contrôles d’exportation de données. Pour compléter cette section :

1. Cliquez sur **[!UICONTROL Data Export Labels]** pour afficher les commandes.
2. Sélectionnez un libellé correspondant au contrôle d’exportation des données appliqué à la destination (voir [Ajouter des étiquettes d’exportation à une destination](/help/using/features/destinations/add-data-export-labels.md) pour plus d’informations).
3. Cliquez sur **[!UICONTROL Save]**.

## Configuration {#configuration}

Cette section contient des champs et des options qui vous permettent de configurer le cookie pour votre destination.

>[!NOTE]
>
>[!DNL Audience Manager] code les données écrites dans le cookie de destination. Par exemple, les espaces sont codés en tant que `%20` point-virgule et les points-virgules `%3B`.

Pour compléter cette section :

1. Cliquez **[!UICONTROL Configuration]** pour afficher les commandes
1. Attribuez un nom au cookie. Evitez les abréviations et les caractères spéciaux.
1. Choisissez un format de données. Ces options vous permettent de choisir les délimiteurs et les séparateurs pour les paires clé-valeur qui envoient des données de segment vers une destination. Les options de format sont les suivantes :
   * **** Clé unique : Permet de définir la clé dans une paire clé-valeur. Vous définirez la valeur après avoir sélectionné un segment dans la [!UICONTROL Segment Mappings] section ci-dessous.
   * **** Multi-clé : Permet de définir la clé et la valeur d’une paire clé-valeur. Vous allez créer la paire clé-valeur après avoir sélectionné un segment dans la section Mappages de segments ci-dessous.
Pour plus d’informations sur ces éléments de données, voir Paires [Standard et Série Key-Value](../../features/destinations/key-value-pairs.md) .
1. Cliquez sur **[!UICONTROL Save]**.

Tous les autres paramètres sont facultatifs. Pour plus d’informations sur les paramètres **[!UICONTROL Cookie Domain]** et **[!UICONTROL Publish data to]** , voir Paramètres [facultatifs pour les destinations](/help/using/features/destinations/cookie-destination-options.md)des cookies.

## Mappages de segments {#segments-mapping}

Cette section vous permet de rechercher et d’ajouter des segments à votre destination. Pour compléter cette section :

1. Cliquez sur **[!UICONTROL Segment Mappings]** pour afficher les commandes.
1. Dans la **[!UICONTROL Search and Add Segments]** zone, commencez à saisir le nom d’un segment ou cliquez **[!UICONTROL Browse All Segments]** sur pour parcourir la liste des segments disponibles.
1. Cliquez **[!UICONTROL Add Selected Segments]** lorsque vous trouvez le segment à utiliser. L’ajout d’un segment ouvre la [!UICONTROL Edit Mapping] fenêtre.
1. Dans la [!UICONTROL Edit Mapping] boîte de dialogue :
   * **[!UICONTROL Mapping]** vous permet de définir une valeur pour la clé spécifiée dans la section Configuration ci-dessus.
   * **[!UICONTROL Publish from]** vous permet de définir les dates de début et de fin pour la destination. Si la date de fin est vide, la destination n’expire jamais.
1. Cliquez sur **[!UICONTROL Save]**.
1. Cliquez sur **[!UICONTROL Done]**.