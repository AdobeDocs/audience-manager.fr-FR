---
description: Cet article décrit deux fonctionnalités avancées pour le modèle d’allocation en double d’Audience Lab et le délai d’attente des segments.
seo-description: Cet article décrit deux fonctionnalités avancées pour le modèle d’allocation en double d’Audience Lab et le délai d’attente des segments.
seo-title: Fonction avancée d’Audience Lab
solution: Audience Manager
title: Fonction avancée d’Audience Lab
uuid: 0f57d634-caa0-40da-81a2-c23fbd299bfd
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# [!DNL Audience Lab] Fonctionnalité avancée {#audience-lab-advanced-functionality}

Cet article décrit deux fonctionnalités avancées pour [!DNL Audience Lab]: [!DNL Duplicate Allocation Template] et [!DNL Segment Holdout].

## Modèle d’allocation en double {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

Dans [!DNL Audience Lab], la [!DNL Allocation Template] représente les différentes sélections que vous effectuez lors de la création d’un groupe de tests :

* la répartition des dispositifs entre les segments d'essai;
* le mappage des segments de test vers les destinations ;
* Les caractéristiques de conversion que vous utilisez pour un groupe de tests ;
* Plage de dates au cours de laquelle le groupe de tests publie vers les destinations sélectionnées.

En dupliquant un modèle d’attribution, vous pouvez réutiliser la même distribution de segments et de destinations de test pour un segment de base différent, dans un nouveau groupe de test. Vous trouverez ci-dessous un exemple de modèle d’attribution. L’image est prise à partir de l’ [!UICONTROL Summary & Finalize] étape du processus de **création d’un groupe** de tests.

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### Utilisation d’un modèle d’allocation en double

Créez un groupe de tests initial, puis sélectionnez **[!UICONTROL Duplicate Allocation Template]** pour réutiliser les mêmes paramètres dans plusieurs groupes de tests. Par exemple, vous pouvez utiliser cette fonctionnalité si vous exécutez un test pour déterminer l’efficacité de plusieurs destinations pour plusieurs segments.

1. Dans l’affichage principal Audience Lab, recherchez le groupe de test dont vous souhaitez reproduire le modèle d’allocation dans un nouveau groupe de test. Dans la liste déroulante, sélectionnez **[!UICONTROL Duplicate Allocation Template]**.

   ![](assets/duplicate-allocation-template.png)

2. Dans l’ [!UICONTROL Create Test Group] assistant, vous pouvez spécifier un segment de base et renommer vos segments de test, le cas échéant.
3. Vous *ne pouvez pas* modifier :

   * la répartition des dispositifs entre les segments d'essai;
   * Le(s) trait(s) de conversion;
   * Association des segments de test aux destinations. Vous pouvez uniquement remplir la clé de mappage pour les destinations qui en ont besoin.
   * période au cours de laquelle votre groupe de test publiera vers les destinations sélectionnées.

4. Passez en revue les informations que vous avez ajoutées lors des étapes précédentes et sélectionnez **[!UICONTROL Finalize Group]**.

## Test de l'exclusion de segment {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] est une fonctionnalité avancée, activée sur demande du client. Veuillez contacter [!DNL Customer Care] ou [!DNL Adobe Consulting] activer cette fonction.

Utilisez cette fonctionnalité pour empêcher une partie de l’audience d’être incluse dans le test. Le pourcentage sélectionné est omis du test. De cette manière, vous pouvez mesurer et comparer le nombre de conversions à partir d’audiences ciblées (activées sur les destinations) et non ciblées (groupes d’attente).

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### Utilisation de l'exclusion des segments de test

1. Créez un groupe de tests à l’aide de l’ [!UICONTROL Create Test Group] assistant.
1. Au cours de l’ **[!UICONTROL Allocate Test Segment]** étape, vous pouvez sélectionner une partie de l’audience à exclure du test.

   ![Elément de liste](assets/test-segment-holdout.png)

1. Utilisez le curseur pour régler le nombre de périphériques que vous souhaitez retenir des tests. Notez que les segments 1 et 2 de test ne représentent désormais que 70 % du total des périphériques.

   ![](assets/test-segment-holdout-selected.png)

1. Passez en revue les autres étapes du **[!UICONTROL Create Test Group]** processus et sélectionnez **[!UICONTROL Finalize Group]** lorsque vous êtes satisfait de votre sélection. Vous disposez maintenant d’un groupe de test dont une partie de l’audience est exclue du test.
