---
description: Une destination URL effectue des appels de pixels d’une page vers votre destination. Suivez ces instructions pour créer une destination d’URL avec Destination Builder.
seo-description: A URL destination makes pixel calls from a page to your destination. Follow these instructions to create a URL destination with Destination Builder.
seo-title: Configure a URL Destination
solution: Audience Manager
title: Configurer une destination d’URL
feature: Destination Basics
exl-id: b5af87c9-4460-43a7-9808-242eac876c39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 1%

---

# Configuration d’un [!DNL URL Destination] {#configure-url-destination}

Un [!DNL URL destination] effectue des appels de pixels d’une page à votre [!DNL destination]. Suivez ces instructions pour créer un [!DNL URL] [!DNL destination] avec [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Pour créer une nouvelle [!DNL URL] de [!DNL destination], accédez à **[!UICONTROL Audience Data > Destinations > Create New Destination]** et renseignez les sections comme décrit ci-dessous.

## Informations fondamentales {#basic-info}

Cette section contient des champs et des options qui lancent le processus de création de [!DNL URL destination]. Pour remplir cette section, procédez comme suit :

1. Cliquez sur **[!UICONTROL Basic Information]** pour afficher les contrôles.
2. Nommez le [!DNL destination] . Évitez les abréviations et les caractères spéciaux.
3. *(Facultatif)* Décrivez le [!DNL destination]. Une description concise est un moyen efficace de définir ou de fournir plus d’informations sur un [!DNL destination].
4. Dans la liste **[!UICONTROL Category]**, choisissez **[!UICONTROL Custom]**.
5. Dans la liste **[!UICONTROL Environment]**, sélectionnez l’environnement dans lequel déclencher le [!DNL URL destination].
6. Dans la liste **[!UICONTROL Type]**, cliquez sur **[!UICONTROL URL]**.
7. *(Facultatif)* Sélectionnez un **[!UICONTROL Auto-fill Destination Mapping]**. Les options incluent :
   * **[!UICONTROL Segment ID]** : ajoute et envoie automatiquement l’identifiant du segment à l’[!DNL destination].
   * **[!UICONTROL Integration Code Value]** : ajoute et envoie automatiquement le code d’intégration de segment au mappage de destination. Le code d’intégration est un identifiant unique créé et utilisé par le client. Il est limité à 255 caractères, au maximum.
8. Cliquez sur **[!UICONTROL Next]** pour accéder aux paramètres [!UICONTROL Configuration] ou sur **[!UICONTROL Data Export Labels]** pour appliquer des contrôles d’exportation au [!DNL destination].

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

Cette section contient des options qui appliquent des [contrôles d’exportation de données](../../features/data-export-controls.md) à une destination [!DNL URL]. Ignorez cette étape si vous n’utilisez pas de contrôles d’exportation des données. Pour remplir cette section, procédez comme suit :

1. Cliquez sur **[!UICONTROL Data Export Labels]** pour afficher les contrôles.
2. Sélectionnez un libellé qui correspond au contrôle d’exportation des données appliqué à la destination (voir [ Ajouter des libellés d’exportation à une destination ](/help/using/features/destinations/add-data-export-labels.md) pour plus de détails).
3. Cliquez sur **[!UICONTROL Save]**.

## Configuration {#configure-base-data}

Cette section contient des options permettant de définir un [!DNL URL] de base et des délimiteurs de données transmis par la chaîne de [!DNL URL]. Cette section est facultative. Pour remplir cette section, procédez comme suit :

1. Cliquez sur **[!UICONTROL Configuration]** pour afficher les contrôles.
1. *(Facultatif)* Cochez la case **[!UICONTROL Serialize]**.
Vous pouvez ainsi envoyer les segments à un [!DNL destination] de manière séquentielle au lieu d’effectuer des appels distincts pour chaque segment. La sérialisation permet de rendre les transferts de données efficaces. Si vous cochez cette case, les champs URL et délimiteur sont exposés. Pour plus d&#39;informations, voir [Paires clé-valeur standard et série](../../features/destinations/key-value-pairs.md).
1. Si vous sélectionnez **[!UICONTROL Serialize]**, vous devez également configurer les champs d’URL et de délimiteur décrits ci-dessous.

| Champ | Description |
|--- |--- |
| [!UICONTROL Base URL] | Partie de base d’un `HTTP` standard [!DNL URL] qui ne change pas. Vous devez également placer la `%ALIAS%` [macro d’espace réservé](../../features/destinations/destination-macros.md#destination-macros-defined) dans l’URL de base. Exemple : `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | La partie de base d’un `HTTPS` sécurisé [!DNL URL] qui ne change pas. En outre, vous devez placer le `%ALIAS%`   [ macro d’espace réservé ](../../features/destinations/destination-macros.md#destination-macros-defined) dans l’URL de base. Exemple : `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | Symbole qui sépare les variables de segment dans la chaîne [!DNL URL]. Il s’agit généralement d’une virgule ou d’un point-virgule. Obtenez ces informations auprès de votre partenaire de destination. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

Cette section vous permet de rechercher et d’ajouter des segments à votre [!UICONTROL destination]. Pour remplir cette section, procédez comme suit :

1. Cliquez sur **[!UICONTROL Segment Mappings]** pour afficher les contrôles.
1. Dans la zone de **[!UICONTROL Search and Add Segments]**, commencez à saisir le nom d’un segment ou cliquez **[!UICONTROL Browse All Segments]** parcourir une liste de segments disponibles.
1. Cliquez sur **[!UICONTROL Add Selected Segments]** lorsque vous trouvez le segment que vous souhaitez utiliser. L’ajout d’un segment ouvre la fenêtre de [!UICONTROL Edit Mapping].
1. En [!UICONTROL Edit Mapping] :
   * **[!UICONTROL Mappings]** : indiquez les paires clé-valeur utilisées par le segment.
   * **[!UICONTROL Start Date]** et **[!UICONTROL End Date]** : sélectionnez une date de début et une date de fin pour le [!DNL destination]. Si la date de fin est vide, le [!DNL destination] n’expire jamais.
1. Cliquez sur **[!UICONTROL Done]**.
