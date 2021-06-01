---
description: Une destination de cookie renvoie et écrit des données dans un cookie dans le navigateur de l’utilisateur. Le cookie contient des données qui peuvent être lues par d’autres plateformes ayant accès à la page. Suivez ces instructions pour créer une destination de cookie avec [!UICONTROL Destination Builder].
seo-description: Une destination de cookie renvoie et écrit des données dans un cookie dans le navigateur de l’utilisateur. Le cookie contient des données qui peuvent être lues par d’autres plateformes ayant accès à la page. Suivez ces instructions pour créer une destination de cookie avec [!UICONTROL Destination Builder].
seo-title: Configuration d’une destination de cookie
solution: Audience Manager
title: Configuration d’une destination de cookie
feature: Concepts de base des destinations
exl-id: 32b8de66-e12d-48ec-82cf-9b0d335ae834
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 3%

---

# Configuration d’une destination de cookie {#create-cookie-destination}

Une destination de cookie renvoie et écrit des données dans un cookie dans le navigateur de l’utilisateur. Le cookie contient des données qui peuvent être lues par d’autres plateformes ayant accès à la page. Suivez ces instructions pour créer une destination de cookie avec [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

Pour créer une destination de cookie, accédez à **[!UICONTROL Audience Data > Destinations > Create New Destination]** et remplissez les sections comme décrit ci-dessous.

## Informations fondamentales {#basic-information}

Cette section contient des champs et des options qui démarrent le processus de création de destination de cookie. Pour terminer cette section :

1. Cliquez sur **[!UICONTROL Basic Information]** pour afficher les contrôles.
2. Nommez la destination. Évitez les abréviations et les caractères spéciaux.
3. *(Facultatif)* Décrivez la destination. Une description concise est un moyen efficace de définir ou de fournir plus d’informations sur une destination.
4. Dans la liste **[!UICONTROL Category]**, choisissez **[!UICONTROL Custom]**.
5. Dans la liste **[!UICONTROL Environment]**, sélectionnez **[!UICONTROL Browser]**. Vous ne pouvez pas configurer de destinations de cookie pour les environnements mobiles natifs, tels que les applications Android ou iOS.
6. Dans la liste **[!UICONTROL Type]**, cliquez sur **[!UICONTROL Cookie]**.
7. *(Facultatif)* Sélectionnez un  **[!UICONTROL Auto-fill Destination Mapping]**. Les options incluent :
   * **[!UICONTROL Segment ID]**: Ajoute et envoie automatiquement l’identifiant du segment à la destination.
   * **[!UICONTROL Integration Code Value]**: Ajoute et envoie automatiquement le code d’intégration du segment au mappage de destination. Le code d’intégration est un identifiant unique créé et utilisé par le client. Elle est limitée à 255 caractères, au maximum.
8. Cliquez sur **[!UICONTROL Next]** pour accéder aux paramètres [!UICONTROL Configuration] ou cliquez sur **[!UICONTROL Data Export Labels]** pour appliquer des contrôles d’exportation à la destination.

## Étiquettes d’exportation de données {#data-export-labels-cookies}

Cette section contient des options qui s’appliquent [aux contrôles d’exportation de données](../../features/data-export-controls.md) à une destination de cookie. Ignorez cette étape si vous n’utilisez pas les contrôles d’exportation des données. Pour terminer cette section :

1. Cliquez sur **[!UICONTROL Data Export Labels]** pour afficher les contrôles.
2. Sélectionnez un libellé correspondant au contrôle d’exportation des données appliqué à la destination (voir [Ajout de libellés d’exportation vers une destination](/help/using/features/destinations/add-data-export-labels.md) pour plus de détails).
3. Cliquez sur **[!UICONTROL Save]**.

## Configuration {#configuration}

Cette section contient des champs et des options qui vous permettent de configurer le cookie pour votre destination.

>[!NOTE]
>
>[!DNL Audience Manager] code les données écrites dans le cookie de destination. Par exemple, les espaces sont codés en tant que `%20` et les points-virgules sont codés en tant que `%3B`.

Pour terminer cette section :

1. Cliquez sur **[!UICONTROL Configuration]** pour afficher les contrôles.
1. Nommez le cookie. Évitez les abréviations et les caractères spéciaux.
1. Choisissez une option de format de données. Ces options vous permettent de choisir les délimiteurs et les séparateurs pour les paires clé-valeur qui envoient des données de segment vers une destination. Les options de format incluent :
   * **Clé unique :** permet de définir la clé dans une paire clé-valeur. Vous définirez la valeur après avoir sélectionné un segment dans la section [!UICONTROL Segment Mappings] ci-dessous.
   * **Multi-clé :** permet de définir la clé et la valeur d’une paire clé-valeur. Vous allez créer la paire clé-valeur après avoir sélectionné un segment dans la section Mappages de segments ci-dessous.
Voir [Paires clé-valeur standard et de série](../../features/destinations/key-value-pairs.md) pour plus d’informations sur ces éléments de données.
1. Cliquez sur **[!UICONTROL Save]**.

Tous les autres paramètres sont facultatifs. Pour plus d’informations sur les paramètres **[!UICONTROL Cookie Domain]** et **[!UICONTROL Publish data to]**, voir [Paramètres facultatifs pour les destinations de cookie](/help/using/features/destinations/cookie-destination-options.md).

## Mappages de segments {#segments-mapping}

Cette section vous permet de rechercher et d’ajouter des segments à votre destination. Pour terminer cette section :

1. Cliquez sur **[!UICONTROL Segment Mappings]** pour afficher les contrôles.
1. Dans la zone **[!UICONTROL Search and Add Segments]**, commencez à saisir le nom d’un segment ou cliquez sur **[!UICONTROL Browse All Segments]** pour parcourir la liste des segments disponibles.
1. Cliquez sur **[!UICONTROL Add Selected Segments]** lorsque vous trouvez le segment à utiliser. L’ajout d’un segment ouvre la fenêtre [!UICONTROL Edit Mapping].
1. Dans la boîte de dialogue [!UICONTROL Edit Mapping] :
   * **[!UICONTROL Mapping]** permet de définir une valeur pour la clé spécifiée dans la section Configuration ci-dessus.
   * **[!UICONTROL Publish from]** permet de définir les dates de début et de fin de la destination. Si la date de fin est vide, la destination n’expire jamais.
1. Cliquez sur **[!UICONTROL Save]**.
1. Cliquez sur **[!UICONTROL Done]**.
