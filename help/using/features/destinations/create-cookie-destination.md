---
description: Une destination de cookie renvoie et écrit des données dans un cookie dans le navigateur de l’utilisateur. Le cookie contient des données qui peuvent être lues par d’autres plateformes ayant accès à la page. Suivez ces instructions pour créer une destination de cookie avec [!UICONTROL Destination Builder].
seo-description: A cookie destination returns and writes data to a cookie in the user's browser. The cookie contains data that can be read by other platforms that have access to the page. Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].
seo-title: Configure a Cookie Destination
solution: Audience Manager
title: Configuration d’une destination de cookie
feature: Destination Basics
exl-id: 32b8de66-e12d-48ec-82cf-9b0d335ae834
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 1%

---

# Configuration d’une destination de cookie {#create-cookie-destination}

Une destination de cookie renvoie et écrit des données dans un cookie dans le navigateur de l’utilisateur. Le cookie contient des données qui peuvent être lues par d’autres plateformes ayant accès à la page. Suivez ces instructions pour créer une destination de cookie avec [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

Pour créer une nouvelle destination de cookie, accédez à **[!UICONTROL Audience Data > Destinations > Create New Destination]** et renseignez les sections comme décrit ci-dessous.

## Informations fondamentales {#basic-information}

Cette section contient des champs et des options qui démarrent le processus de création de la destination du cookie. Pour remplir cette section, procédez comme suit :

1. Cliquez sur **[!UICONTROL Basic Information]** pour afficher les contrôles.
2. Nommez la destination. Évitez les abréviations et les caractères spéciaux.
3. *(Facultatif)* Décrivez la destination. Une description concise est un moyen efficace de définir ou de fournir plus d’informations sur une destination.
4. Dans la liste **[!UICONTROL Category]**, choisissez **[!UICONTROL Custom]**.
5. Dans la liste **[!UICONTROL Environment]**, sélectionnez **[!UICONTROL Browser]**. Vous ne pouvez pas configurer de destinations de cookies pour les environnements mobiles natifs, tels que les applications Android ou iOS.
6. Dans la liste **[!UICONTROL Type]**, cliquez sur **[!UICONTROL Cookie]**.
7. *(Facultatif)* Sélectionnez un **[!UICONTROL Auto-fill Destination Mapping]**. Les options incluent :
   * **[!UICONTROL Segment ID]** : ajoute et envoie automatiquement l’identifiant de segment à la destination.
   * **[!UICONTROL Integration Code Value]** : ajoute et envoie automatiquement le code d’intégration de segment au mappage de destination. Le code d’intégration est un identifiant unique créé et utilisé par le client. Il est limité à 255 caractères, au maximum.
8. Cliquez sur **[!UICONTROL Next]** pour accéder aux paramètres de [!UICONTROL Configuration] ou sur **[!UICONTROL Data Export Labels]** pour appliquer des contrôles d’exportation à la destination.

## Libellés d’exportation des données {#data-export-labels-cookies}

Cette section contient des options qui appliquent des [contrôles d’exportation de données](../../features/data-export-controls.md) à une destination de cookie. Ignorez cette étape si vous n’utilisez pas de contrôles d’exportation des données. Pour remplir cette section, procédez comme suit :

1. Cliquez sur **[!UICONTROL Data Export Labels]** pour afficher les contrôles.
2. Sélectionnez un libellé qui correspond au contrôle d’exportation des données appliqué à la destination (voir [ Ajouter des libellés d’exportation à une destination ](/help/using/features/destinations/add-data-export-labels.md) pour plus de détails).
3. Cliquez sur **[!UICONTROL Save]**.

## Configuration {#configuration}

Cette section contient des champs et des options qui vous permettent de configurer le cookie pour la destination.

>[!NOTE]
>
>[!DNL Audience Manager] code les données écrites dans le cookie de destination. Par exemple, les espaces sont codés en tant que `%20` et les points-virgules sont codés en tant que `%3B`.

Pour remplir cette section, procédez comme suit :

1. Cliquez sur **[!UICONTROL Configuration]** pour afficher les contrôles
1. Nommez le cookie . Évitez les abréviations et les caractères spéciaux.
1. Choisissez une option de format des données. Ces options vous permettent de choisir les délimiteurs et les séparateurs pour les paires clé-valeur qui envoient des données de segment vers une destination. Les options de format sont les suivantes :
   * **Clé unique :** permet de définir la clé dans une paire clé-valeur. Vous définissez la valeur après avoir sélectionné un segment dans la section [!UICONTROL Segment Mappings] ci-dessous.
   * **Clé multiple :** permet de définir la clé et la valeur d’une paire clé-valeur. Vous allez créer la paire clé-valeur après avoir sélectionné un segment dans la section Mappages de segments ci-dessous.
Voir [Paires clé-valeur standard et série](../../features/destinations/key-value-pairs.md) pour plus d’informations sur ces éléments de données.
1. Cliquez sur **[!UICONTROL Save]**.

Tous les autres paramètres sont facultatifs. Pour plus d’informations sur les paramètres **[!UICONTROL Cookie Domain]** et **[!UICONTROL Publish data to]**, voir [Paramètres facultatifs pour les destinations de cookie](/help/using/features/destinations/cookie-destination-options.md).

## Mappages de segments {#segments-mapping}

Cette section vous permet de rechercher et d’ajouter des segments à la destination. Pour remplir cette section, procédez comme suit :

1. Cliquez sur **[!UICONTROL Segment Mappings]** pour afficher les contrôles.
1. Dans la zone de **[!UICONTROL Search and Add Segments]**, commencez à saisir le nom d’un segment ou cliquez sur **[!UICONTROL Browse All Segments]** pour parcourir une liste de segments disponibles.
1. Cliquez sur **[!UICONTROL Add Selected Segments]** lorsque vous trouvez le segment que vous souhaitez utiliser. L’ajout d’un segment ouvre la fenêtre de [!UICONTROL Edit Mapping].
1. Dans la boîte de dialogue [!UICONTROL Edit Mapping] :
   * **[!UICONTROL Mapping]** permet de définir une valeur pour la clé spécifiée dans la section Configuration ci-dessus.
   * **[!UICONTROL Publish from]** permet de définir les dates de début et de fin de la destination. Si la date de fin est vide, la destination n’expire jamais.
1. Cliquez sur **[!UICONTROL Save]**.
1. Cliquez sur **[!UICONTROL Done]**.
