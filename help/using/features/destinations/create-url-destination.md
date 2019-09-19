---
description: Une destination URL effectue des appels de pixels d’une page vers votre destination. Suivez ces instructions pour créer une destination URL avec le créateur de destinations.
seo-description: Une destination URL effectue des appels de pixels d’une page vers votre destination. Suivez ces instructions pour créer une destination URL avec le créateur de destinations.
seo-title: Configuration d’une destination d’URL
solution: Audience Manager
title: Configuration d’une destination d’URL
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---



# Configuration d’une destination d’URL {#configure-url-destination}

Une [!DNL URL] destination effectue des appels de pixels d’une page vers votre destination. Suivez ces instructions pour créer une [!DNL URL] destination avec [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Pour créer une nouvelle [!DNL URL] destination, accédez aux sections **[!UICONTROL Audience Data > Destinations > Create New Destination]** et complétez-les comme décrit ci-dessous.

## Informations fondamentales {#basic-info}

Cette section contient des champs et des options qui démarrent le processus de création de destination de l’URL. Pour compléter cette section :

1. Cliquez sur **[!UICONTROL Basic Information]** pour afficher les commandes.
2. Nommez la destination. Evitez les abréviations et les caractères spéciaux.
3. *(Facultatif)* Décrivez la destination. Une description concise est un moyen efficace de définir ou de fournir plus d’informations sur une destination.
4. Dans la **[!UICONTROL Category]** liste, choisissez **[!UICONTROL Custom]**.
5. Dans la **[!UICONTROL Environment]** liste, sélectionnez l’environnement dans lequel déclencher la destination de l’URL.
6. Dans la **[!UICONTROL Type]** liste, cliquez sur **[!UICONTROL URL]**.
7. *(Facultatif)* Sélectionnez un **[!UICONTROL Auto-fill Destination Mapping]**. Les options incluent :
   * **[!UICONTROL Segment ID]**: Ajoute et envoie automatiquement l’ID de segment à la destination.
   * **[!UICONTROL Integration Code Value]**: Ajoute et envoie automatiquement le code d’intégration de segment au mappage de destination. Le code d’intégration est un identifiant unique créé et utilisé par le client. Elle est limitée à 255 caractères au maximum.
8. Cliquez sur **[!UICONTROL Next]** pour accéder aux [!UICONTROL Configuration] paramètres ou sur **[!UICONTROL Data Export Labels]** pour appliquer des contrôles d’exportation à la destination.

## Étiquettes d’exportation de données {#data-export-labels-dest}

Cette section contient des options qui appliquent des contrôles [d’exportation de](../../features/data-export-controls.md) données à une [!DNL URL] destination. Ignorez cette étape si vous n’utilisez pas les contrôles d’exportation de données. Pour compléter cette section :

1. Cliquez sur **[!UICONTROL Data Export Labels]** pour afficher les commandes.
2. Sélectionnez un libellé correspondant au contrôle d’exportation des données appliqué à la destination (voir [Ajouter des étiquettes d’exportation à une destination](/help/using/features/destinations/add-data-export-labels.md) pour plus d’informations).
3. Cliquez sur **[!UICONTROL Save]**.

## Configuration {#configure-base-data}

Cette section contient des options qui vous permettent de définir une base [!DNL URL] et des délimiteurs de données transmis par la [!DNL URL] chaîne. Cette section est facultative. Pour compléter cette section :

1. Cliquez sur **[!UICONTROL Configuration]** pour afficher les commandes.
1. *(Facultatif)* Cochez la **[!UICONTROL Serialize]** case.
Vous pouvez ainsi envoyer les segments vers une destination de manière séquentielle plutôt que d’effectuer des appels distincts pour chaque segment. La sérialisation permet d’optimiser les transferts de données. Si vous activez cette case à cocher, les champs URL et délimiteur sont exposés. Pour plus d’informations, voir Paires [Standard et Valeur de clé de série](../../features/destinations/key-value-pairs.md).
1. Si vous sélectionnez **[!UICONTROL Serialize]**, vous devez également configurer les champs URL et délimiteur décrits ci-dessous.

| Champ | Description |
|--- |--- |
| URL de base | Partie de base d’une norme `HTTP` qui ne change pas [!DNL URL] . Vous devez également placer la macro `%ALIAS%` d’ [](../../features/destinations/destination-macros.md#destination-macros-defined) espace réservé dans l’URL de base. Exemple: `https://www.myCompany.com/%alias%...` |
| URL sécurisée | La partie de base d’une sécurité `HTTPS` qui ne change pas [!DNL URL] . Vous devez également placer la macro `%ALIAS%` d’ [](../../features/destinations/destination-macros.md#destination-macros-defined) espace réservé dans l’URL de base. Exemple: `https://www.myCompany.com/%alias%...` |
| Délimiteur | Symbole qui sépare les variables de segment dans la [!DNL URL] chaîne. Il s’agit généralement d’une virgule ou d’un point-virgule. Obtenez ces informations auprès de votre partenaire de destination. |

## Mappages de segments {#segment-mappings}

Cette section vous permet de rechercher et d’ajouter des segments à votre destination. Pour compléter cette section :

1. Cliquez sur **[!UICONTROL Segment Mappings]** pour afficher les commandes.
1. Dans la **[!UICONTROL Search and Add Segments]** zone, commencez à saisir le nom d’un segment ou cliquez sur **[!UICONTROL Browse All Segments]** Parcourir la liste des segments disponibles.
1. Cliquez **[!UICONTROL Add Selected Segments]** lorsque vous trouvez le segment à utiliser. L’ajout d’un segment ouvre la [!UICONTROL Edit Mapping] fenêtre.
1. Dans [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Fournissez les paires clé-valeur utilisées par le segment.
   * **[!UICONTROL Start Date]** et **[!UICONTROL End Date]**: Choisissez une date de début et de fin pour la destination. Si la date de fin est vide, la destination n’expire jamais.
1. Cliquez sur **[!UICONTROL Done]**.