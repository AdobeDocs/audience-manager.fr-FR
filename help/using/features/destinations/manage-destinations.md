---
description: La page d'entrée Destination répertorie toutes les destinations de serveur, de cookie et de serveur à serveur. Il offre des fonctionnalités permettant de créer, de modifier, de rechercher et de créer des rapports sur les destinations. La page d'entrée se trouve dans Données d'audience > Destinations.
seo-description: La page d'entrée Destination répertorie toutes les destinations de serveur, de cookie et de serveur à serveur. Il offre des fonctionnalités permettant de créer, de modifier, de rechercher et de créer des rapports sur les destinations. La page d'entrée se trouve dans Données d'audience > Destinations.
seo-title: Gérer les destinations
solution: Audience Manager
title: Gérer les destinations
uuid: 6 b 66 ff 42-0075-49 a 7-a 58 f -7 f 8 ea 2295 fdc
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# Gérer les destinations {#manage-destinations}

La page [!UICONTROL Destination] d'entrée répertorie toutes les [!DNL URL]destinations de serveur, de cookie et de serveur à serveur. Il offre des fonctionnalités permettant de créer, de modifier, de rechercher et de créer des rapports sur les destinations. La page d'entrée se trouve **[!UICONTROL Audience Data > Destinations]** dans.

## Page d'entrée par défaut {#default-landing-page}

<!-- destinations-home.xml -->

La page d'entrée par défaut répertorie vos destinations, en fonction du type. Vous pouvez filtrer les destinations à l'aide des quatre onglets disponibles :

* **Tout**: affiche tous les types de destinations.
* **Adobe Experience Cloud**: affiche les destinations qui envoient des données à d'autres solutions Adobe Experience Cloud. Actuellement, la seule option prise en charge est Adobe Analytics. See [Configure an Analytics Destination](/help/using/features/destinations/create-analytics-destination.md).
* **Plateformes intégrées**: montre les destinations basées sur les utilisateurs et les périphériques (également appelées destinations serveur à serveur). Notez que les destinations basées sur les personnes sont actuellement une fonctionnalité bêta uniquement disponible pour les clients sélectionnés.
* **Personnalisé**: affiche les destinations de cookie et d'URL.


![](assets/destinations-landing.png)

## Page d'entrée Audiences adressables {#audiences-landing-page}

Pour afficher les données d'audience et les taux de correspondance de votre destination de serveur à serveur, sélectionnez **[!UICONTROL Integrated Platforms > Device-Based]**.

Pour plus d'informations sur les informations affichées, voir [Interface d'audiences adressables](/help/using/features/addressable-audiences.md#addressable-audience-interface).

![](/help/using/features/assets/addressable-audiences-landing.png)

## Configuration d'une destination d'URL {#configure-url-destination}

Une [!DNL URL] destination effectue des appels de pixels d'une page vers votre destination. Suivez ces instructions pour créer [!DNL URL] une destination avec [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Pour créer [!DNL URL] une destination, accédez **[!UICONTROL Audience Data > Destinations > Create New Destination]** aux sections et remplissez-les comme décrit ci-dessous.

### Informations fondamentales {#basic-info}

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

### Étiquettes d'exportation des données {#data-export-labels-dest}

Cette section contient des options qui appliquent [des commandes d'exportation de données](../../features/data-export-controls.md) à [!DNL URL] une destination. Ignorez cette étape si vous n'utilisez pas les commandes d'exportation de données. Pour terminer cette section :

1. Cliquez sur **[!UICONTROL Data Export Labels]** pour exposer les commandes.
2. Sélectionnez un libellé correspondant au contrôle d'exportation de données appliqué à la destination (voir [Ajout de libellés d'exportation à une destination](../../features/destinations/manage-destinations.md#add-data-export-labels) pour plus de détails).
3. Cliquez sur **[!UICONTROL Save]**.

### Configuration {#configure-base-data}

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

### Correspondances de segments {#segment-mappings}

Cette section vous permet de rechercher et d'ajouter des segments à votre destination. Pour terminer cette section :

1. Cliquez sur **[!UICONTROL Segment Mappings]** pour exposer les commandes.
1. Dans **[!UICONTROL Search and Add Segments]** la zone, commencez à saisir le nom d'un segment ou cliquez **[!UICONTROL Browse All Segments]** sur Parcourir une liste des segments disponibles.
1. Cliquez **[!UICONTROL Add Selected Segments]** sur le segment que vous souhaitez utiliser. L'ajout d'un segment ouvre [!UICONTROL Edit Mapping] la fenêtre.
1. Dans [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Fournissez les paires clé-valeur utilisées par le segment.
   * **[!UICONTROL Start Date]** et **[!UICONTROL End Date]**: Choisissez une date de début et de fin pour la destination. Si la date de fin est vide, la destination n'expire jamais.
1. Cliquez sur **[!UICONTROL Done]**.

## Ajout ou modification de segments pour les destinations serveur à serveur {#add-edit-segments}

Vous pouvez uniquement ajouter ou modifier des segments pour une destination de serveur à serveur ([!DNL S2S]). Vous ne pouvez pas créer [!DNL S2S] de destinations avec [!UICONTROL Destination Builder]. Contactez votre conseiller pour configurer [!DNL S2S] les destinations. Suivez ces instructions pour ajouter ou modifier des segments pour [!DNL S2S] une destination.

<!-- destination-s2s-edit.xml -->

Pour ajouter ou modifier des correspondances de segments pour [!DNL S2S] une destination :

1. Accédez **[!UICONTROL Audience Data > Destinations]**&#x200B;à. Sélectionnez **Plateformes intégrées &gt; Périphérique et** recherchez [!DNL S2S] la destination avec laquelle vous souhaitez travailler.
2. Dans [!UICONTROL Action] la colonne, cliquez sur l'icône représentant un crayon pour modifier la destination.
   * Dans **[!UICONTROL Search and Add Segments]** la zone, commencez à saisir le nom d'un segment ou cliquez **[!UICONTROL Browse All Segments]** sur Parcourir une liste des segments disponibles.
   * Cliquez **[!UICONTROL Add Selected Segments]** sur le segment que vous souhaitez utiliser. L'ajout d'un segment ouvre [!UICONTROL Edit Mapping] la fenêtre.
   * Dans [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Définissez une valeur pour la paire [clé-valeur](../../features/destinations/key-value-pairs.md) utilisée par cette destination.
      * **[!UICONTROL Start Date]** et **[!UICONTROL End Date]**: Choisissez une date de début et de fin pour la destination. Si la date de fin est vide, la destination n'expire jamais.
3. Cliquez **[!UICONTROL Save]** sur, puis **[!UICONTROL Done]** sur.

## Ajout d'étiquettes d'exportation de données à une destination {#add-data-export-labels}

[!DNL Data Export Labels] travailler avec le jeu [!DNL Export Controls] que vous avez défini sur une source de données. [!DNL Data Export Labels] vous éviter d'ajouter des caractéristiques restreintes à un segment et d'envoyer des données de segment à une destination. Vous pouvez définir plusieurs étiquettes d'exportation dans une nouvelle ou une [!DNL cookie][!DNL URL] nouvelle destination.

>[!NOTE]
>
>Pour ajouter une étiquette d'exportation, vous devez disposer des autorisations *d'administrateur ou* des privilèges suffisants pour créer ou modifier une destination.

<!-- t_export_labels.xml -->

Pour ajouter des étiquettes d'exportation à une destination :

1. Cliquez sur **[!UICONTROL Audience Data]**:
   * Pour les nouvelles destinations : Cliquez **[!UICONTROL Create New Destination]** sur. Remplissez [!UICONTROL Basic Information] la section avant de sélectionner une étiquette d'exportation de données. Voir [Création d'une destination de cookie](../../features/destinations/manage-destinations.md#create-cookie-destination) ou [Création d'une destination d'URL](../../features/destinations/manage-destinations.md#configure-url-destination) pour plus d'informations.
   * Pour les destinations existantes : Utilisez [!DNL Search] la zone pour trouver votre destination ou faites défiler la liste et cliquez sur le nom de la destination pour l'ouvrir.
1. Sélectionnez [!DNL Data Export Label]. Laissez les cases vides si vous ne souhaitez pas définir de restrictions d'exportation. Les étiquettes d'exportation incluent les options suivantes :
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Les restrictions d'exportation ne fonctionnent que si vous définissez un contrôle d'exportation [correspondant](../../features/data-export-controls.md) sur une source de données.
1. Cliquez sur **[!UICONTROL Save]**.

>[!MORE_ LIKE_ THIS]
>
>* [Création d'une source de données](../../features/manage-datasources.md#create-data-source)

