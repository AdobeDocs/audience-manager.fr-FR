---
description: Une destination URL effectue des appels en pixels d’une page à votre destination. Suivez ces instructions pour créer une destination URL avec le créateur de destinations.
seo-description: Une destination URL effectue des appels en pixels d’une page à votre destination. Suivez ces instructions pour créer une destination URL avec le créateur de destinations.
seo-title: Configuration d’une destination d’URL
solution: Audience Manager
title: Configuration d’une destination d’URL
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 3%

---



# Configuration d’une [!DNL URL Destination] {#configure-url-destination}

Un [!DNL URL destination] effectue des appels en pixels d’une page à votre [!DNL destination]. Suivez ces instructions pour créer un [!DNL URL][!DNL destination] avec [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Pour créer une nouvelle [!DNL URL][!DNL destination], accédez **[!UICONTROL Audience Data > Destinations > Create New Destination]** aux sections et complétez-les comme décrit ci-dessous.

## Informations fondamentales {#basic-info}

Cette section contient des champs et des options qui début le processus de [!DNL URL destination] création. Pour compléter cette section :

1. Cliquez sur **[!UICONTROL Basic Information]** pour afficher les commandes.
2. Nommez le [!DNL destination]. Evitez les abréviations et les caractères spéciaux.
3. *(Facultatif)* Décrivez le [!DNL destination]. Une description concise est un moyen efficace de définir ou de fournir plus d&#39;informations sur un [!DNL destination]objet.
4. Dans la **[!UICONTROL Category]** liste, choisissez **[!UICONTROL Custom]**.
5. Dans la **[!UICONTROL Environment]** liste, sélectionnez l’environnement dans lequel déclencher la [!DNL URL destination]variable.
6. Dans la **[!UICONTROL Type]** liste, cliquez sur **[!UICONTROL URL]**.
7. *(Facultatif)* Sélectionnez un **[!UICONTROL Auto-fill Destination Mapping]** objet. Les options incluent :
   * **[!UICONTROL Segment ID]**: Ajoute et envoie automatiquement l’ID de segment à la [!DNL destination]variable.
   * **[!UICONTROL Integration Code Value]**: Ajoute et envoie automatiquement le code d’intégration de segment au mappage de destination. Le code d’intégration est un identifiant unique créé et utilisé par le client. Il ne peut pas contenir plus de 255 caractères.
8. Cliquez sur **[!UICONTROL Next]** pour accéder aux [!UICONTROL Configuration] paramètres ou sur **[!UICONTROL Data Export Labels]** pour appliquer des contrôles d’exportation au [!DNL destination].

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

Cette section contient des options qui appliquent des contrôles [d&#39;exportation de](../../features/data-export-controls.md) données à une [!DNL URL] destination. Ignorez cette étape si vous n’utilisez pas les contrôles d’exportation de données. Pour compléter cette section :

1. Cliquez sur **[!UICONTROL Data Export Labels]** pour afficher les commandes.
2. Sélectionnez une étiquette correspondant au contrôle d&#39;exportation des données appliqué à la destination (voir [Ajouter des étiquettes d&#39;exportation à une destination](/help/using/features/destinations/add-data-export-labels.md) pour plus d&#39;informations).
3. Cliquez sur **[!UICONTROL Save]**.

## Configuration {#configure-base-data}

Cette section contient des options qui vous permettent de définir une base [!DNL URL] et des délimiteurs de données transmis par la [!DNL URL] chaîne. Cette section est facultative. Pour compléter cette section :

1. Cliquez sur **[!UICONTROL Configuration]** pour afficher les commandes.
1. *(Facultatif)* Cochez la **[!UICONTROL Serialize]** case.
Vous pouvez ainsi envoyer les segments vers un segment [!DNL destination] séquentiellement plutôt que d’effectuer des appels distincts pour chaque segment. La sérialisation permet de rendre les transferts de données efficaces. La sélection de cette case à cocher expose les champs URL et délimiteur. Pour plus d’informations, voir Paires [de valeur de clé](../../features/destinations/key-value-pairs.md)standard et série.
1. Si vous sélectionnez **[!UICONTROL Serialize]**, vous devez également configurer les champs URL et délimiteur décrits ci-dessous.

| Champ | Description |
|--- |--- |
| [!UICONTROL Base URL] | Partie de base d’une norme `HTTP`[!DNL URL] qui ne change pas. Vous devez également placer la macro `%ALIAS%` d’ [](../../features/destinations/destination-macros.md#destination-macros-defined) espace réservé dans l’URL de base. Exemple: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | Partie de base d’une sécurité `HTTPS`[!DNL URL] qui ne change pas. Vous devez également placer la macro `%ALIAS%` d’ [](../../features/destinations/destination-macros.md#destination-macros-defined) espace réservé dans l’URL de base. Exemple: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | Symbole qui sépare les variables de segment dans la [!DNL URL] chaîne. Il s’agit généralement d’une virgule ou d’un point-virgule. Obtenez ces informations auprès de votre partenaire de destination. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

Cette section vous permet de rechercher et d’ajouter des segments à votre [!UICONTROL destination]site. Pour compléter cette section :

1. Cliquez sur **[!UICONTROL Segment Mappings]** pour afficher les commandes.
1. Dans la **[!UICONTROL Search and Add Segments]** zone, début en saisissant le nom d’un segment ou en cliquant sur **[!UICONTROL Browse All Segments]** parcourir une liste de segments disponibles.
1. Cliquez **[!UICONTROL Add Selected Segments]** lorsque vous trouvez le segment à utiliser. Ajouter un segment ouvre la [!UICONTROL Edit Mapping] fenêtre.
1. Dans [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Fournissez les paires clé-valeur utilisées par le segment.
   * **[!UICONTROL Start Date]** et **[!UICONTROL End Date]**: Choisissez un début et une date de fin pour le [!DNL destination]. Si la date de fin est vide, la date [!DNL destination] n’expire jamais.
1. Cliquez sur **[!UICONTROL Done]**.