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

* Vous devez configurer au moins une caractéristique **de** conversion. Vous pouvez configurer des caractéristiques de conversion dans le créateur [de](../../features/traits/create-onboarded-rule-based-traits.md)caractéristiques en sélectionnant **la conversion** comme type d&#39;événement. Pour plus d&#39;informations sur les caractéristiques de conversion et comment les configurer, nous avons préparé une [vidéo](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) pour vous.

   >[!IMPORTANT]
   >
   >[Les caractéristiques](../../features/traits/about-folder-traits.md) des dossiers **ne sont pas prises en charge** par [!UICONTROL Audience Lab]. La définition du [Type d&#39;événement](../../features/traits/create-onboarded-rule-based-traits.md) d&#39;une caractéristique de dossier en **conversion** ne générera aucune donnée dans [!UICONTROL Audience Lab] cette caractéristique de dossier spécifique.

* Pour les sociétés qui utilisent un Contrôle d&#39;accès [](../../features/administration/administration-overview.md)basé sur les rôles : Attribuez l’autorisation [!UICONTROL Audience Lab] de [caractères génériques à](../../features/administration/administration-overview.md#wild-card-permissions) **[!UICONTROL User Groups]** fournir l’accès. Cette autorisation permet à l’utilisateur de créer et de vue les résultats d’un test. Un utilisateur ne pourra utiliser que les segments d’une source de données pour laquelle il a **lu** et **mappé les privilèges de destination** . L&#39;utilisateur ne pourra utiliser que les caractéristiques de conversion d&#39;une source de données pour laquelle il dispose des autorisations de **&quot;lecture&quot;** . Un utilisateur ne pourra voir que les destinations auxquelles il a également accès. Ainsi, avant d’ajouter l’autorisation d’utilisation du [!DNL Audience Lab] caractère générique à un groupe, assurez-vous que le groupe dispose des éléments suivants :
   * l&#39;accès à la lecture des caractéristiques de conversion pertinentes ;
   * l&#39;accès à la lecture et à la mise en correspondance des segments pertinents pour les tests ;
   * accès aux destinations appropriées.

To create a new [!UICONTROL Segment Test Group]:

1. Sélectionnez **[!UICONTROL Create New Test Group]** dans le [!UICONTROL Audience Lab] tableau de bord pour début de l’assistant.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Remplissez un **[!UICONTROL Test Group Name]** et un **[!UICONTROL Description]**.
   * Sélectionnez le fichier **[!UICONTROL Base Segment]** en naviguant dans le navigateur de fichiers ou en saisissant des informations dans la barre de recherche, puis en appuyant sur **[!UICONTROL Choose Segment.]**
   * Vous pouvez enregistrer le groupe de tests en tant que brouillon et reprendre le travail dessus ultérieurement.
   * Une alerte s’affiche au cas où le segment de base que vous avez sélectionné serait déjà utilisé dans d’autres groupes de tests. L’utilisation du segment de base deux fois peut fausser les résultats de conversion pour les deux tests.

1. **[!UICONTROL Allocate Test Segments]**

   * Vous pouvez créer **jusqu’à 15 segments** de test et diviser le pourcentage de périphériques comme vous le souhaitez.
   * Vous pouvez modifier le nom des segments de test en cliquant dessus.
   * Les pourcentages se divisent automatiquement de manière égale à 100 % lorsque de nouveaux segments de test sont alloués. Vous pouvez ensuite modifier manuellement les pourcentages. Cochez la case après avoir modifié les pourcentages et assurez-vous qu’ils atteignent 100 %, sinon vous ne pourrez pas passer à l’étape suivante.

1. **[!UICONTROL Set a Control Segment]**

   * Sélectionnez un segment de contrôle si vous souhaitez réserver une partie du segment à utiliser comme Population témoin. Les Populations témoins vous permettent de voir l’impact des segments de test que vous avez créés par rapport à un banc d’essai.
   * Vous pouvez sélectionner un segment de test en tant que segment de contrôle dans la liste déroulante ou choisir **[!UICONTROL None]** de ne pas contrôler.
   * Cliquez **[!UICONTROL Next]** une fois que vous avez terminé.

1. **[!UICONTROL Select Conversion Traits]**

   * Ajoutez les caractéristiques de conversion en saisissant des informations dans la fenêtre des caractéristiques de conversion. Il s’agit d’une étape **obligatoire** et vous ne pouvez pas passer à l’étape suivante à moins d’ajouter au moins une caractéristique de conversion.
   * Vous pouvez ajouter jusqu’à 5 caractéristiques de conversion si vous le souhaitez.
   * Une alerte s’affiche au cas où vous sélectionneriez une caractéristique de conversion déjà utilisée pour d’autres groupes de tests.
   * Notez que l’Audience Manager ne prend pas en charge l’utilisation de caractéristiques [de](/help/using/features/traits/about-folder-traits.md) dossier en tant que caractéristiques de conversion. Si vous sélectionnez une caractéristique de dossier comme caractéristique de conversion, 0 agrégat et rapports de tendance sont affichés dans le test.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Tapez les destinations de votre choix dans le champ de recherche ou utilisez la flèche déroulante. [!UICONTROL Audience Lab] les segments de test peuvent être envoyés vers des destinations URL, de cookie ou de serveur à serveur.
   * Faites glisser les segments vers les destinations.
   * Après avoir déposé un segment dans une destination, renseignez le champ **[!UICONTROL Destination Mapping Value]** en aveugle.
   * Vous pouvez envoyer le même segment de test à plusieurs destinations et ajouter plusieurs segments de test à une seule destination.
   * Les destinations sont grisées si elles ne sont pas disponibles pour un certain segment de test en fonction des contrôles [d’exportation des](../../features/data-export-controls.md)données.
   * Les utilisateurs ne verront que les destinations auxquelles ils ont accès en fonction du groupe [d’utilisateurs](../../features/administration/administration-overview.md) RBAC auquel ils appartiennent.
   * Enfin, vous devez sélectionner une date de début pour votre groupe de tests. Cette date marque le début de la période au cours de laquelle votre groupe de tests sera publié vers les destinations. Sélectionnez **Aucune date** de fin pour une comparaison indéfinie des segments de test.

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] avec un profil authentifié ne sont pris en charge que dans les destinations en temps réel. Si un segment de test avec une règle de fusion de profil de cette configuration est envoyé vers une destination serveur à serveur basée sur des fichiers, les audiences peuvent ne pas être renseignées.

   Cliquez sur **[!UICONTROL Next]** pour revoir et finaliser votre groupe de tests.

1. **[!UICONTROL Summary & Finalize]**

   * Passez en revue les informations que vous avez ajoutées lors des étapes précédentes et sélectionnez **[!UICONTROL Finalize Group]**.
   * N’oubliez pas qu’une fois que vous avez terminé un groupe de tests, il peut être dupliqué ou supprimé, mais pas modifié.

   >[!NOTE]
   >* Vous pouvez enregistrer les groupes de tests à tout moment du processus de création et revenir à l’assistant ultérieurement. L&#39;état du groupe de tests sera **[!UICONTROL Draft]** défini et le groupe de tests n&#39;enverra aucune donnée aux destinations tant que vous n&#39;aurez pas terminé le groupe de tests de segment.
   >* Pour les tests préliminaires, vous pouvez revenir en arrière et modifier les groupes de tests en cliquant sur **[!UICONTROL Edit]** la carte du groupe de tests dans la [!UICONTROL Audience Lab] vue principale.


## Modifier les groupes de tests de segments {#edit-test-groups}

Dans [!UICONTROL Audience Lab], vous ne pouvez modifier que les groupes de tests préliminaires. Dans l&#39; [!UICONTROL Create Segment Test Group] assistant, vous pouvez enregistrer votre groupe de tests en tant que brouillon et reprendre à travailler dessus ultérieurement.

1. Accédez à la vue [!UICONTROL Audience Lab] principale.
1. Recherchez vos groupes de tests préliminaires et sélectionnez le **[!UICONTROL Edit]** contrôle dans la carte du groupe de tests.
1. Reprenez l&#39;Assistant [Créer un groupe](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) de test de segment et sélectionnez **[!UICONTROL Finalize Group]** une fois terminé.

## Suppression de groupes de tests de segments {#delete-test-groups}

1. Accédez à la vue [!UICONTROL Audience Lab] principale.
1. Recherchez le groupe de tests à supprimer. Vous pouvez :

   * appuyez sur la **[!UICONTROL Delete]** commande dans la carte du groupe de tests, ou
   * appuyez sur le titre du groupe de tests dans la carte du groupe de tests pour accéder à la vue d&#39;informations [du groupe de](../../features/audience-lab/audience-lab-information-view.md) tests et appuyez sur la **[!UICONTROL Delete]** commande dans la barre de titre.

1. Pour les segments [de test](../../features/audience-lab/audience-lab.md#status)terminés, une alerte vous invite à télécharger le fichier CSV pour enregistrer le rapports si vous le souhaitez.
