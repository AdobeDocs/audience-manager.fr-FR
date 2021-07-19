---
description: Une destination d’URL effectue des appels de pixel d’une page vers votre destination. Suivez ces instructions pour créer une destination d’URL avec le créateur de destinations.
seo-description: Une destination d’URL effectue des appels de pixel d’une page vers votre destination. Suivez ces instructions pour créer une destination d’URL avec le créateur de destinations.
seo-title: Configuration d’une destination d’URL
solution: Audience Manager
title: Configuration d’une destination d’URL
feature: Concepts de base des destinations
exl-id: b5af87c9-4460-43a7-9808-242eac876c39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 3%

---

# Configuration d’un [!DNL URL Destination] {#configure-url-destination}

Un [!DNL URL destination] effectue des appels de pixel d’une page vers votre [!DNL destination]. Suivez ces instructions pour créer une [!DNL URL] [!DNL destination] avec [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Pour créer une [!DNL URL] [!DNL destination], accédez à **[!UICONTROL Audience Data > Destinations > Create New Destination]** et complétez les sections comme décrit ci-dessous.

## Informations fondamentales {#basic-info}

Cette section contient des champs et des options qui démarrent le processus de création de [!DNL URL destination]. Pour terminer cette section :

1. Cliquez sur **[!UICONTROL Basic Information]** pour afficher les contrôles.
2. Nommez le [!DNL destination]. Évitez les abréviations et les caractères spéciaux.
3. *(Facultatif)* Décrivez le  [!DNL destination]. Une description concise est un moyen efficace de définir ou de fournir plus d’informations sur une [!DNL destination].
4. Dans la liste **[!UICONTROL Category]**, choisissez **[!UICONTROL Custom]**.
5. Dans la liste **[!UICONTROL Environment]**, sélectionnez l&#39;environnement dans lequel déclencher la balise [!DNL URL destination].
6. Dans la liste **[!UICONTROL Type]**, cliquez sur **[!UICONTROL URL]**.
7. *(Facultatif)* Sélectionnez un  **[!UICONTROL Auto-fill Destination Mapping]**. Les options incluent :
   * **[!UICONTROL Segment ID]**: Ajoute et envoie automatiquement l’identifiant du segment à  [!DNL destination].
   * **[!UICONTROL Integration Code Value]**: Ajoute et envoie automatiquement le code d’intégration du segment au mappage de destination. Le code d’intégration est un identifiant unique créé et utilisé par le client. Elle est limitée à 255 caractères, au maximum.
8. Cliquez sur **[!UICONTROL Next]** pour accéder aux paramètres [!UICONTROL Configuration] ou cliquez sur **[!UICONTROL Data Export Labels]** pour appliquer des contrôles d’exportation à [!DNL destination].

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

Cette section contient des options qui s’appliquent [aux contrôles d’exportation de données](../../features/data-export-controls.md) à une destination [!DNL URL]. Ignorez cette étape si vous n’utilisez pas les contrôles d’exportation des données. Pour terminer cette section :

1. Cliquez sur **[!UICONTROL Data Export Labels]** pour afficher les contrôles.
2. Sélectionnez un libellé correspondant au contrôle d’exportation des données appliqué à la destination (voir [Ajout de libellés d’exportation vers une destination](/help/using/features/destinations/add-data-export-labels.md) pour plus d’informations).
3. Cliquez sur **[!UICONTROL Save]**.

## Configuration {#configure-base-data}

Cette section contient des options qui vous permettent de définir une base [!DNL URL] et des délimiteurs de données transmis par la chaîne [!DNL URL]. Cette section est facultative. Pour terminer cette section :

1. Cliquez sur **[!UICONTROL Configuration]** pour afficher les contrôles.
1. *(Facultatif)* Cochez la  **[!UICONTROL Serialize]** case.
Vous pouvez ainsi envoyer des segments à une [!DNL destination] de manière séquentielle plutôt que d’effectuer des appels distincts pour chaque segment. La sérialisation permet d’optimiser les transferts de données. Cette case à cocher expose les champs URL et délimiteur. Pour plus d’informations, voir [Paires clé-valeur standard et série](../../features/destinations/key-value-pairs.md).
1. Si vous sélectionnez **[!UICONTROL Serialize]**, vous devez également configurer les champs URL et délimiteur décrits ci-dessous.

| Champ | Description |
|--- |--- |
| [!UICONTROL Base URL] | Partie de base d’une `HTTP` [!DNL URL] standard qui ne change pas. Vous devez également placer la `%ALIAS%` [macro d’espace réservé](../../features/destinations/destination-macros.md#destination-macros-defined) dans l’URL de base. Exemple: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | La partie de base d’un `HTTPS` [!DNL URL] sécurisé qui ne change pas. Vous devez également placer la balise `%ALIAS%`   [macro d’espace réservé](../../features/destinations/destination-macros.md#destination-macros-defined) dans l’URL de base. Exemple: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | Symbole qui sépare les variables de segment dans la chaîne [!DNL URL]. Il s’agit généralement d’une virgule ou d’un point-virgule. Obtenez ces informations auprès de votre partenaire de destination. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

Cette section vous permet de rechercher et d’ajouter des segments à votre [!UICONTROL destination]. Pour terminer cette section :

1. Cliquez sur **[!UICONTROL Segment Mappings]** pour afficher les contrôles.
1. Dans la zone **[!UICONTROL Search and Add Segments]**, commencez à saisir le nom d’un segment ou cliquez sur **[!UICONTROL Browse All Segments]** parcourir la liste des segments disponibles.
1. Cliquez sur **[!UICONTROL Add Selected Segments]** lorsque vous trouvez le segment à utiliser. L’ajout d’un segment ouvre la fenêtre [!UICONTROL Edit Mapping].
1. Dans [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Fournissez les paires clé-valeur utilisées par le segment.
   * **[!UICONTROL Start Date]** et  **[!UICONTROL End Date]**: Choisissez une date de début et une date de fin pour le  [!DNL destination]. Si la date de fin est vide, la valeur [!DNL destination] n’expire jamais.
1. Cliquez sur **[!UICONTROL Done]**.
