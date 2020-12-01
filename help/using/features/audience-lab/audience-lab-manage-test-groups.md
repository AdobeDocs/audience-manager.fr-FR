---
description: Cette procédure vous guide tout au long des étapes nécessaires pour créer, modifier ou supprimer un groupe de tests dans Audience Lab.
seo-description: Cette procédure vous guide tout au long des étapes nécessaires pour créer, modifier ou supprimer un groupe de tests dans Audience Lab.
seo-title: Gestion des groupes de test
solution: Audience Manager
title: Gestion des groupes de test
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1003'
ht-degree: 0%

---


# Gestion des groupes de test {#manage-test-groups}

Cette procédure vous guide tout au long des étapes nécessaires pour créer, modifier ou supprimer un groupe de tests dans [!UICONTROL Audience Lab].

## Créer des groupes de tests de segments {#create-test-groups}

### Conditions préalables

<!-- create-test-group.xml -->

* Vous devez avoir configuré au moins une **caractéristique de conversion**. Vous pouvez configurer des caractéristiques de conversion dans le [créateur de caractéristiques](../../features/traits/create-onboarded-rule-based-traits.md), en sélectionnant **conversion** comme type d&#39;événement. Pour plus d&#39;informations sur les caractéristiques de conversion et sur la façon de les configurer, nous avons préparé une [vidéo](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) pour vous.

   >[!IMPORTANT]
   >
   >[Les dossiers ](../../features/traits/about-folder-traits.md) traînés  **ne sont** pas  [!UICONTROL Audience Lab]pris en charge parle gouvernement. La définition du [Type d&#39;événement](../../features/traits/create-onboarded-rule-based-traits.md) d&#39;une caractéristique de dossier sur **conversion** ne génère aucune donnée dans [!UICONTROL Audience Lab] pour cette caractéristique de dossier spécifique.

* Pour les sociétés qui utilisent [un Contrôle d&#39;accès basé sur le rôle](../../features/administration/administration-overview.md) : Attribuez l&#39;autorisation [!UICONTROL Audience Lab] [générique](../../features/administration/administration-overview.md#wild-card-permissions) à **[!UICONTROL User Groups]** pour fournir l&#39;accès. Cette autorisation permet à l’utilisateur de créer et de vue les résultats d’un test. Un utilisateur ne peut utiliser que les segments d&#39;une source de données pour lesquels il dispose de privilèges **read** et **map** et &lt;a2/>destination&lt;a3/>. L’utilisateur ne pourra utiliser que les caractéristiques de conversion d’une source de données pour laquelle il dispose d’autorisations **&quot;read&quot;**. Un utilisateur ne pourra voir que les destinations auxquelles il a également accès. Ainsi, avant d&#39;ajouter l&#39;autorisation de caractère générique [!DNL Audience Lab] à un groupe, assurez-vous que le groupe dispose des éléments suivants :
   * l&#39;accès à la lecture des caractéristiques de conversion pertinentes ;
   * l&#39;accès à la lecture et à la mise en correspondance des segments pertinents pour les tests ;
   * accès aux destinations appropriées.

Pour créer [!UICONTROL Segment Test Group] :

1. Sélectionnez **[!UICONTROL Create New Test Group]** dans le tableau de bord [!UICONTROL Audience Lab] pour début de l&#39;Assistant.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Renseignez les champs **[!UICONTROL Test Group Name]** et **[!UICONTROL Description]**.
   * Choisissez **[!UICONTROL Base Segment]** en naviguant dans le navigateur de fichiers ou en saisissant dans la barre de recherche, confirmez en appuyant sur **[!UICONTROL Choose Segment.]**
   * Vous pouvez enregistrer le groupe de tests en tant que brouillon et reprendre le travail dessus ultérieurement.
   * Une alerte s’affiche au cas où le segment de base que vous avez sélectionné serait déjà utilisé dans d’autres groupes de tests. L’utilisation du segment de base deux fois peut fausser les résultats de conversion pour les deux tests.

1. **[!UICONTROL Allocate Test Segments]**

   * Vous pouvez créer **jusqu’à 15 segments de test** et diviser le pourcentage de périphériques comme vous le souhaitez.
   * Vous pouvez modifier le nom des segments de test en cliquant dessus.
   * Les pourcentages se divisent automatiquement de manière égale à 100 % lorsque de nouveaux segments de test sont alloués. Vous pouvez ensuite modifier manuellement les pourcentages. Cochez la case après avoir modifié les pourcentages et assurez-vous qu’ils atteignent 100 %, sinon vous ne pourrez pas passer à l’étape suivante.

1. **[!UICONTROL Set a Control Segment]**

   * Sélectionnez un segment de contrôle si vous souhaitez réserver une partie du segment à utiliser comme Population témoin. Les Populations témoins vous permettent de comparer l’impact des segments de test que vous avez créés à celui d’un banc d’essai.
   * Vous pouvez sélectionner un segment de test en tant que segment de contrôle dans la liste déroulante, ou vous pouvez choisir **[!UICONTROL None]** sans contrôle.
   * Cliquez sur **[!UICONTROL Next]** lorsque vous avez terminé.

1. **[!UICONTROL Select Conversion Traits]**

   * Ajoutez les caractéristiques de conversion en saisissant des informations dans la fenêtre des caractéristiques de conversion. Il s’agit d’une étape **obligatoire** et vous ne pouvez pas passer à l’étape suivante à moins d’ajouter au moins une caractéristique de conversion.
   * Vous pouvez ajouter jusqu’à 5 caractéristiques de conversion si vous le souhaitez.
   * Une alerte s’affiche au cas où vous sélectionneriez une caractéristique de conversion déjà utilisée pour d’autres groupes de tests.
   * Notez que l’Audience Manager ne prend pas en charge l’utilisation de [caractéristiques de dossier](/help/using/features/traits/about-folder-traits.md) comme caractéristiques de conversion. Si vous sélectionnez une caractéristique de dossier comme caractéristique de conversion, 0 agrégat et rapports de tendance sont affichés dans le test.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Tapez les destinations de votre choix dans le champ de recherche ou utilisez la flèche déroulante. [!UICONTROL Audience Lab] les segments de test peuvent être envoyés vers des destinations URL, de cookie ou de serveur à serveur.
   * Faites glisser les segments vers les destinations.
   * Après avoir déposé un segment dans une destination, renseignez **[!UICONTROL Destination Mapping Value]** dans l’aveugle.
   * Vous pouvez envoyer le même segment de test à plusieurs destinations et ajouter plusieurs segments de test à une seule destination.
   * Les destinations sont grisées si elles ne sont pas disponibles pour un certain segment de test basé sur [Contrôles d’exportation de données](../../features/data-export-controls.md).
   * Les utilisateurs ne verront que les destinations auxquelles ils ont accès en fonction du [groupe d’utilisateurs RBAC](../../features/administration/administration-overview.md) auquel ils appartiennent.
   * Enfin, vous devez sélectionner une date de début pour votre groupe de tests. Cette date marque le début de la période au cours de laquelle votre groupe de tests sera publié vers les destinations. Sélectionnez **Aucune date de fin** pour une comparaison indéfinie des segments de test.

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] avec un profil authentifié ne sont pris en charge que dans les destinations en temps réel. Si un segment de test avec une règle de fusion de profil de cette configuration est envoyé vers une destination serveur à serveur basée sur des fichiers, les audiences peuvent ne pas être renseignées.

   Cliquez sur **[!UICONTROL Next]** pour revoir et finaliser votre groupe de tests.

1. **[!UICONTROL Summary & Finalize]**

   * Passez en revue les informations que vous avez ajoutées aux étapes précédentes et sélectionnez **[!UICONTROL Finalize Group]**.
   * N’oubliez pas qu’une fois que vous avez terminé un groupe de tests, il peut être dupliqué ou supprimé, mais pas modifié.

   >[!NOTE]
   >* Vous pouvez enregistrer les groupes de tests à tout moment du processus de création et revenir à l’assistant ultérieurement. L&#39;état du groupe de tests est **[!UICONTROL Draft]** et le groupe de tests n&#39;envoie aucune donnée vers les destinations tant que vous n&#39;avez pas terminé le groupe de tests de segment.
   >* Pour les tests préliminaires, vous pouvez revenir en arrière et modifier les groupes de tests en cliquant sur **[!UICONTROL Edit]** dans la carte du groupe de tests dans la vue principale [!UICONTROL Audience Lab].


## Modifier les groupes de tests de segment {#edit-test-groups}

Dans [!UICONTROL Audience Lab], vous ne pouvez modifier que les groupes de tests préliminaires. Dans l&#39;assistant [!UICONTROL Create Segment Test Group], vous pouvez enregistrer votre groupe de tests en tant que brouillon et reprendre à travailler dessus ultérieurement.

1. Accédez à la vue principale [!UICONTROL Audience Lab].
1. Recherchez vos groupes de tests préliminaires et sélectionnez le contrôle **[!UICONTROL Edit]** dans la carte du groupe de tests.
1. Reprenez l&#39;Assistant [Créer un groupe de test de segment](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) et sélectionnez **[!UICONTROL Finalize Group]** lorsque vous avez terminé.

## Supprimer des groupes de tests de segments {#delete-test-groups}

1. Accédez à la vue principale [!UICONTROL Audience Lab].
1. Recherchez le groupe de tests à supprimer. Vous pouvez :

   * appuyez sur le contrôle **[!UICONTROL Delete]** dans la carte du groupe de tests, ou
   * appuyez sur le titre du groupe de tests dans la carte du groupe de tests pour accéder à la vue [Informations du groupe de tests](../../features/audience-lab/audience-lab-information-view.md) et appuyez sur le contrôle **[!UICONTROL Delete]** dans la barre de titre.

1. Pour [les segments de test terminés](../../features/audience-lab/audience-lab.md#status), une alerte vous invite à télécharger le fichier CSV pour enregistrer le rapports si vous le souhaitez.
