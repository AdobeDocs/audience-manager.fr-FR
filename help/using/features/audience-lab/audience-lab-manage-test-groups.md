---
description: Cette procédure vous guide tout au long des étapes nécessaires pour créer, modifier ou supprimer un groupe de tests dans Audience Lab.
seo-description: Cette procédure vous guide tout au long des étapes nécessaires pour créer, modifier ou supprimer un groupe de tests dans Audience Lab.
seo-title: Gestion des groupes de test
solution: Audience Manager
title: Gestion des groupes de test
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: 'Audience Lab '
exl-id: 1d07c8f1-34dc-4339-bd5d-87042a22f7e9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 1%

---

# Gestion des groupes de test {#manage-test-groups}

Cette procédure vous guide tout au long des étapes nécessaires pour créer, modifier ou supprimer un groupe de test dans [!UICONTROL Audience Lab].

## Création de groupes de test de segment {#create-test-groups}

### Conditions préalables

<!-- create-test-group.xml -->

* Vous devez configurer au moins une **caractéristique de conversion**. Vous pouvez configurer des caractéristiques de conversion dans le [créateur de caractéristiques](../../features/traits/create-onboarded-rule-based-traits.md) en sélectionnant **conversion** comme type d’événement. Pour plus d’informations sur les caractéristiques de conversion et sur la manière de les configurer, nous avons préparé une [vidéo](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) pour vous.

   >[!IMPORTANT]
   >
   >[Les ](../../features/traits/about-folder-traits.md) caractéristiques de dossier  **ne sont pas** prises en charge par  [!UICONTROL Audience Lab]. La définition du [type d’événement](../../features/traits/create-onboarded-rule-based-traits.md) d’une caractéristique de dossier sur **conversion** ne générera aucune donnée dans [!UICONTROL Audience Lab] pour cette caractéristique de dossier spécifique.

* Pour les entreprises qui utilisent [le contrôle d’accès en fonction du rôle](../../features/administration/administration-overview.md) : Attribuez l’autorisation [!UICONTROL Audience Lab] [caractère générique](../../features/administration/administration-overview.md#wild-card-permissions) à **[!UICONTROL User Groups]** pour fournir l’accès. Cette autorisation permet à l’utilisateur de créer et d’afficher les résultats d’un test. Un utilisateur ne peut utiliser que les segments d’une source de données pour lesquels il dispose des privilèges **read** et **map vers destination**. L’utilisateur ne pourra utiliser que les caractéristiques de conversion d’une source de données pour laquelle il dispose des autorisations **&quot;read&quot;**. Un utilisateur ne pourra voir que les destinations auxquelles il a également accès. Ainsi, avant d’ajouter l’autorisation de caractère générique [!DNL Audience Lab] à un groupe, assurez-vous que le groupe possède :
   * l’accès à la lecture des caractéristiques de conversion pertinentes ;
   * l’accès à la lecture et au mappage des segments pertinents pour les tests ;
   * l’accès aux destinations appropriées.

Pour créer [!UICONTROL Segment Test Group] :

1. Sélectionnez **[!UICONTROL Create New Test Group]** dans le tableau de bord [!UICONTROL Audience Lab] pour lancer l’assistant.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Renseignez un **[!UICONTROL Test Group Name]** et un **[!UICONTROL Description]**.
   * Sélectionnez **[!UICONTROL Base Segment]** en naviguant dans l’explorateur de fichiers ou en saisissant dans la barre de recherche, confirmez en appuyant sur **[!UICONTROL Choose Segment.]**
   * Vous pouvez enregistrer le groupe de test en tant que brouillon et reprendre son travail ultérieurement.
   * Une alerte s’affiche au cas où le segment de base que vous avez sélectionné serait déjà utilisé dans d’autres groupes de test. L’utilisation du segment de base deux fois peut fausser les résultats de conversion pour les deux tests.

1. **[!UICONTROL Allocate Test Segments]**

   * Vous pouvez créer **jusqu’à 15 segments de test** et diviser le pourcentage d’appareils comme vous le souhaitez.
   * Vous pouvez modifier le nom des segments de test en cliquant dessus.
   * Les pourcentages sont automatiquement divisés à 100 % lorsque de nouveaux segments de test sont alloués. Vous pouvez ensuite modifier manuellement les pourcentages. Cochez la case après avoir modifié les pourcentages et assurez-vous qu’ils totalisent jusqu’à 100 %. Sinon, vous ne pourrez pas passer à l’étape suivante.

1. **[!UICONTROL Set a Control Segment]**

   * Sélectionnez un segment témoin si vous souhaitez mettre de côté une partie du segment à utiliser comme groupe témoin. Les groupes de contrôle vous permettent de voir l’impact des segments de test que vous avez créés par rapport à une référence.
   * Vous pouvez sélectionner un segment de test comme segment de contrôle dans la liste déroulante ou sélectionner **[!UICONTROL None]** pour aucun contrôle.
   * Cliquez sur **[!UICONTROL Next]** lorsque vous avez terminé.

1. **[!UICONTROL Select Conversion Traits]**

   * Ajoutez des caractéristiques de conversion en saisissant dans la fenêtre des caractéristiques de conversion. Il s’agit d’une étape **obligatoire** et vous ne pouvez pas passer à l’étape suivante à moins d’ajouter au moins une caractéristique de conversion.
   * Si vous le souhaitez, vous pouvez ajouter jusqu’à 5 caractéristiques de conversion.
   * Une alerte s’affiche si vous sélectionnez une caractéristique de conversion déjà utilisée pour d’autres groupes de test.
   * Notez que l’Audience Manager ne prend pas en charge l’utilisation de [caractéristiques de dossier](/help/using/features/traits/about-folder-traits.md) comme caractéristiques de conversion. La sélection d’une caractéristique de dossier comme caractéristique de conversion génère 0 rapport d’agrégat et de tendance affiché dans le test.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Saisissez les destinations de votre choix dans le champ de recherche ou utilisez la flèche déroulante. [!UICONTROL Audience Lab] les segments de test peuvent être envoyés vers des destinations d’URL, de cookie ou de serveur à serveur.
   * Effectuez un glisser-déposer de segments vers les destinations.
   * Après avoir déposé un segment dans une destination, remplissez la balise **[!UICONTROL Destination Mapping Value]** en aveugle.
   * Vous pouvez envoyer le même segment de test à plusieurs destinations et ajouter plusieurs segments de test à une seule destination.
   * Les destinations sont grisées si elles ne sont pas disponibles pour un certain segment de test basé sur [Contrôles des exportations de données](../../features/data-export-controls.md).
   * Les utilisateurs ne verront que les destinations auxquelles ils ont accès en fonction du [groupe d’utilisateurs RBAC](../../features/administration/administration-overview.md) auquel ils appartiennent.
   * Enfin, vous devez sélectionner une date de début pour votre groupe de tests. Cette date marque le début de la période pendant laquelle votre groupe de test sera publié vers les destinations. Sélectionnez **No End Date** pour une comparaison indéfinie des segments de test.

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] avec un profil authentifié sont uniquement pris en charge dans les destinations en temps réel. Si un segment de test avec une règle de fusion de profils de cette configuration est envoyé vers une destination serveur à serveur basée sur un fichier, les audiences peuvent ne pas être renseignées.

   Cliquez sur **[!UICONTROL Next]** pour passer en revue et finaliser votre groupe de tests.

1. **[!UICONTROL Summary & Finalize]**

   * Vérifiez les informations que vous avez ajoutées aux étapes précédentes et sélectionnez **[!UICONTROL Finalize Group]**.
   * N’oubliez pas qu’une fois que vous avez finalisé un groupe de test, il peut être dupliqué ou supprimé, mais pas modifié.

   >[!NOTE]
   >* Vous pouvez enregistrer les groupes de test à tout moment dans le processus de création et revenir à l’assistant ultérieurement. Le statut du groupe de test est **[!UICONTROL Draft]** et le groupe de test n’envoie aucune donnée aux destinations tant que vous n’avez pas finalisé le groupe de test de segment.
   >* Pour les tests préliminaires, vous pouvez revenir en arrière et modifier les groupes de test en cliquant sur **[!UICONTROL Edit]** dans la carte du groupe de test dans la vue [!UICONTROL Audience Lab] principale.


## Modifier des groupes de test de segment {#edit-test-groups}

Dans [!UICONTROL Audience Lab], vous ne pouvez modifier que les groupes de test préliminaires. Dans l’assistant [!UICONTROL Create Segment Test Group], vous pouvez enregistrer votre groupe de test en tant que brouillon et reprendre son travail ultérieurement.

1. Accédez à la vue principale [!UICONTROL Audience Lab].
1. Recherchez vos groupes de test de brouillon et sélectionnez le contrôle **[!UICONTROL Edit]** dans la carte du groupe de test.
1. Reprenez l’assistant [Créer un groupe de test de segment](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) et sélectionnez **[!UICONTROL Finalize Group]** lorsque vous avez terminé.

## Suppression de groupes de test de segment {#delete-test-groups}

1. Accédez à la vue principale [!UICONTROL Audience Lab].
1. Recherchez le groupe de test à supprimer. Vous pouvez effectuer l’une des opérations suivantes :

   * appuyez sur la commande **[!UICONTROL Delete]** dans la carte du groupe de test, ou
   * appuyez sur le titre du groupe de test dans la carte du groupe de test pour accéder à la vue [Informations sur le groupe de test](../../features/audience-lab/audience-lab-information-view.md) et appuyez sur le contrôle **[!UICONTROL Delete]** dans la barre de titre.

1. Pour les [segments de test terminés](../../features/audience-lab/audience-lab.md#status), une alerte vous invite à télécharger le fichier CSV pour enregistrer le rapport si vous le souhaitez.
