---
description: Une destination de cookie renvoie et écrit des données dans un cookie dans le navigateur de l'utilisateur. Le cookie contient des données qui peuvent être lues par d'autres plateformes qui ont accès à la page. Suivez ces instructions pour créer une destination de cookie avec [! UICONPREVDESTINATION Builder].
seo-description: Une destination de cookie renvoie et écrit des données dans un cookie dans le navigateur de l'utilisateur. Le cookie contient des données qui peuvent être lues par d'autres plateformes qui ont accès à la page. Suivez ces instructions pour créer une destination de cookie avec [! UICONPREVDESTINATION Builder].
seo-title: Configuration d'une destination de cookie
solution: Audience Manager
title: Configuration d'une destination de cookie
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# Configuration d'une destination de cookie {#create-cookie-destination}

Une destination de cookie renvoie et écrit des données dans un cookie dans le navigateur de l'utilisateur. Le cookie contient des données qui peuvent être lues par d'autres plateformes qui ont accès à la page. Suivez ces instructions pour créer une destination de cookie avec [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

Pour créer une destination de cookie, accédez **[!UICONTROL Audience Data > Destinations > Create New Destination]** aux sections et remplissez-les comme décrit ci-dessous.

## Informations fondamentales {#basic-information}

Cette section contient des champs et des options qui démarrent le processus de création de la destination des cookies. Pour terminer cette section :

1. Cliquez sur **[!UICONTROL Basic Information]** pour exposer les commandes.
2. Nommez la destination. Evitez les abréviations et les caractères spéciaux.
3. *(Facultatif)* Décrivez la destination. Une description concise permet de définir ou fournir plus d'informations sur une destination.
4. Dans **[!UICONTROL Category]** la liste, choisissez **[!UICONTROL Custom]**.
5. Dans **[!UICONTROL Environment]** la liste, sélectionnez **[!UICONTROL Browser]**. Vous ne pouvez pas configurer les destinations de cookie pour les environnements mobiles natifs, tels que les applications Android ou ios.
6. Dans **[!UICONTROL Type]** la liste, cliquez **[!UICONTROL Cookie]** sur.
7. *(Facultatif)* Sélectionnez une **[!UICONTROL Auto-fill Destination Mapping]**. Les options incluent :
   * **[!UICONTROL Segment ID]**: Ajoute automatiquement l'identifiant de segment à la destination.
   * **[!UICONTROL Integration Code Value]**: Ajoute automatiquement le code d'intégration de segment au mappage de destination. Le code d'intégration est un identifiant unique créé et utilisé par le client. Elle est limitée à 255 caractères maximum.
8. Cliquez pour **[!UICONTROL Next]** accéder aux [!UICONTROL Configuration] paramètres ou cliquez sur **[!UICONTROL Data Export Labels]** pour appliquer les commandes d'exportation à la destination.

## Étiquettes d'exportation des données {#data-export-labels-cookies}

Cette section contient des options qui appliquent [des contrôles d'exportation de données](../../features/data-export-controls.md) à une destination de cookie. Ignorez cette étape si vous n'utilisez pas les commandes d'exportation de données. Pour terminer cette section :

1. Cliquez sur **[!UICONTROL Data Export Labels]** pour exposer les commandes.
2. Sélectionnez un libellé correspondant au contrôle d'exportation des données appliqué à la destination (voir [Ajout de libellés d'exportation à une destination](/help/using/features/destinations/add-data-export-labels.md) pour plus de détails).
3. Cliquez sur **[!UICONTROL Save]**.

## Configuration {#configuration}

Cette section contient des champs et des options qui vous permettent de configurer le cookie pour votre destination.

>[!NOTE]
>
>[!DNL Audience Manager] code les données écrites dans le cookie de destination. Par exemple, les espaces sont codés sous forme `%20``%3B`de points-virgules codés.

Pour terminer cette section :

1. Cliquez pour **[!UICONTROL Configuration]** exposer les commandes
1. Nommez le cookie. Evitez les abréviations et les caractères spéciaux.
1. Choisissez une option de format de données. Ces options vous permettent de choisir les délimiteurs et les séparateurs pour les paires clé-valeur qui envoient des données de segment à une destination. Les options de format sont les suivantes :
   * **Clé unique :** Permet de définir la clé dans une paire clé-valeur. Vous définirez la valeur après avoir sélectionné un segment dans la [!UICONTROL Segment Mappings] section ci-dessous.
   * **Clé multi-clé :** Permet de définir la clé et la valeur d'une paire clé-valeur. Vous allez créer la paire clé-valeur après avoir sélectionné un segment dans la section Correspondances de segment ci-dessous.
Pour [plus d'informations sur ces éléments de données, voir Paires](../../features/destinations/key-value-pairs.md) standard et de clé-valeur.
1. Cliquez sur **[!UICONTROL Save]**.

Tous les autres paramètres sont facultatifs. Pour plus d'informations sur les paramètres **[!UICONTROL Cookie Domain]** et **[!UICONTROL Publish data to]** les paramètres, voir [Paramètres facultatifs pour les destinations de cookie](/help/using/features/destinations/cookie-destination-options.md).

## Correspondances de segments {#segments-mapping}

Cette section vous permet de rechercher et d'ajouter des segments à votre destination. Pour terminer cette section :

1. Cliquez sur **[!UICONTROL Segment Mappings]** pour exposer les commandes.
1. Dans **[!UICONTROL Search and Add Segments]** la zone, commencez à saisir le nom d'un segment ou cliquez sur **[!UICONTROL Browse All Segments]** pour parcourir la liste des segments disponibles.
1. Cliquez **[!UICONTROL Add Selected Segments]** sur le segment que vous souhaitez utiliser. L'ajout d'un segment ouvre [!UICONTROL Edit Mapping] la fenêtre.
1. Dans [!UICONTROL Edit Mapping] le dialogue :
   * **[!UICONTROL Mapping]** vous permet de définir une valeur pour la clé spécifiée dans la section Configuration ci-dessus.
   * **[!UICONTROL Publish from]** vous permet de définir la date de début et la date de fin de la destination. Si la date de fin est vide, la destination n'expire jamais.
1. Cliquez sur **[!UICONTROL Save]**.
1. Cliquez sur **[!UICONTROL Done]**.