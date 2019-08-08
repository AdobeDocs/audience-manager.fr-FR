---
description: Une destination d'URL lance les appels de pixels d'une page vers votre destination. Suivez ces instructions pour créer une destination URL avec le créateur de destinations.
seo-description: Une destination d'URL lance les appels de pixels d'une page vers votre destination. Suivez ces instructions pour créer une destination URL avec le créateur de destinations.
seo-title: Configuration d'une destination d'URL
solution: Audience Manager
title: Configuration d'une destination d'URL
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---



# Configuration d'une destination d'URL {#configure-url-destination}

Une [!DNL URL] destination effectue des appels de pixels d'une page vers votre destination. Suivez ces instructions pour créer [!DNL URL] une destination avec [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Pour créer [!DNL URL] une destination, accédez **[!UICONTROL Audience Data > Destinations > Create New Destination]** aux sections et remplissez-les comme décrit ci-dessous.

## Informations fondamentales {#basic-info}

Cette section contient des champs et des options qui démarrent le processus de création de la cible d'URL. Pour terminer cette section :

1. Cliquez sur **[!UICONTROL Basic Information]** pour exposer les commandes.
2. Nommez la destination. Evitez les abréviations et les caractères spéciaux.
3. *(Facultatif)* Décrivez la destination. Une description concise permet de définir ou fournir plus d'informations sur une destination.
4. Dans **[!UICONTROL Category]** la liste, choisissez **[!UICONTROL Custom]**.
5. Dans **[!UICONTROL Environment]** la liste, sélectionnez l'environnement dans lequel déclencher la destination de l'URL.
6. Dans **[!UICONTROL Type]** la liste, cliquez **[!UICONTROL URL]** sur.
7. *(Facultatif)* Sélectionnez une **[!UICONTROL Auto-fill Destination Mapping]**. Les options incluent :
   * **[!UICONTROL Segment ID]**: Ajoute automatiquement l'identifiant de segment à la destination.
   * **[!UICONTROL Integration Code Value]**: Ajoute automatiquement le code d'intégration de segment au mappage de destination. Le code d'intégration est un identifiant unique créé et utilisé par le client. Elle est limitée à 255 caractères maximum.
8. Cliquez pour **[!UICONTROL Next]** accéder aux [!UICONTROL Configuration] paramètres ou cliquez sur **[!UICONTROL Data Export Labels]** pour appliquer les commandes d'exportation à la destination.

## Étiquettes d'exportation des données {#data-export-labels-dest}

Cette section contient des options qui appliquent [des commandes d'exportation de données](../../features/data-export-controls.md) à [!DNL URL] une destination. Ignorez cette étape si vous n'utilisez pas les commandes d'exportation de données. Pour terminer cette section :

1. Cliquez sur **[!UICONTROL Data Export Labels]** pour exposer les commandes.
2. Sélectionnez un libellé correspondant au contrôle d'exportation de données appliqué à la destination (voir [Ajout de libellés d'exportation à une destination](/help/using/features/destinations/add-data-export-labels.md) pour plus de détails).
3. Cliquez sur **[!UICONTROL Save]**.

## Configuration {#configure-base-data}

Cette section contient des options vous permettant de définir une base [!DNL URL] et des délimiteurs de données transmis par [!DNL URL] la chaîne. Cette section est facultative. Pour terminer cette section :

1. Cliquez sur **[!UICONTROL Configuration]** pour exposer les commandes.
1. *(Facultatif)* Cochez **[!UICONTROL Serialize]** la case.
Vous pouvez ainsi envoyer des segments à une destination de manière séquentielle plutôt que d'effectuer des appels distincts pour chaque segment. La sérialisation facilite le transfert de données. Cette case à cocher affiche les champs URL et délimiteurs. Pour plus d'informations, voir [Paires standard et de clé-valeur](../../features/destinations/key-value-pairs.md).
1. Si vous sélectionnez **[!UICONTROL Serialize]**, vous devez également configurer l'URL et les champs de délimiteur décrits ci-dessous.

| Champ | Description |
|--- |--- |
| URL de base | Partie base d'une norme `HTTP`[!DNL URL] qui ne change pas. Vous devez également placer la `%ALIAS%`[macro d'espace réservé](../../features/destinations/destination-macros.md#destination-macros-defined) dans l'URL de base. Exemple: `https://www.myCompany.com/%alias%...` |
| URL sécurisée | Partie base d'un sûr `HTTPS`[!DNL URL] qui ne change pas. Vous devez également placer la `%ALIAS%`[macro d'espace réservé](../../features/destinations/destination-macros.md#destination-macros-defined) dans l'URL de base. Exemple: `https://www.myCompany.com/%alias%...` |
| Délimiteur | Symbole qui sépare les variables de segment dans [!DNL URL] la chaîne. Il s'agit généralement d'une virgule ou d'un point-virgule. Obtenez ces informations auprès de votre partenaire de destination. |

## Correspondances de segments {#segment-mappings}

Cette section vous permet de rechercher et d'ajouter des segments à votre destination. Pour terminer cette section :

1. Cliquez sur **[!UICONTROL Segment Mappings]** pour exposer les commandes.
1. Dans **[!UICONTROL Search and Add Segments]** la zone, commencez à saisir le nom d'un segment ou cliquez **[!UICONTROL Browse All Segments]** sur Parcourir une liste des segments disponibles.
1. Cliquez **[!UICONTROL Add Selected Segments]** sur le segment que vous souhaitez utiliser. L'ajout d'un segment ouvre [!UICONTROL Edit Mapping] la fenêtre.
1. Dans [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Fournissez les paires clé-valeur utilisées par le segment.
   * **[!UICONTROL Start Date]** et **[!UICONTROL End Date]**: Choisissez une date de début et de fin pour la destination. Si la date de fin est vide, la destination n'expire jamais.
1. Cliquez sur **[!UICONTROL Done]**.