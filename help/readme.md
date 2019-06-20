---
source-git-commit: dee392312d8e0381c714a99b5d537c767107c9bc
translation-type: tm+mt

---
# Instructions

**Remarque : Cette page (ou toute page readme. md) ne sera pas publiée dans la documentation destinée aux clients.**

## Table des matières

+ `TOC.md` à la racine du guide de l&#39;utilisateur fournit l&#39;organisation des rubriques contenues dans le guide de cette solution.
+ Each user guide will have its own unique `TOC.md`, in which you can order all the pages/topics as necessary.
+ The first page of all user guides is `overview.md`.

## Guide de l’utilisateur

+ The introduction to the user guide is called `overview.md`
+ Chaque rubrique du guide de l&#39;utilisateur possède son propre répertoire.
   + If there is a topic in the guide called *Implementation*, the corresponding directory is `/implementation`
+ All image assets are stored in `/assets` at the root of the user guide.
   + All images in the `/assets` directory will be localized.
   + Any images in the `/no-localize` directory will not be localized (there&#39;s a surprise!). Ceci permet de garantir que dans les versions loc, les ressources spécifiques ne sont pas reproduites inutilement.

## meta de niveau Guide de l&#39;utilisateur - données

+ Meta data which describes the user guide is stored in the `TOC.md`. Cela inclut :
   + product - nom du produit/fonctionnalité.
   + cloud - cloud auquel ce produit appartient.
   + audience - audience ou archétype à laquelle le guide est ciblé.
   + user-guide - nom du guide de l&#39;utilisateur.

## Métadonnées au niveau de la page - données

+ Métadonnées : les données requises pour décrire un document sont stockées dans chaque page individuelle. Cela inclut :
   + title - titre de la page.
   + description - description de la page.
   + seo-title - titre alternatif.
   + seo-description - titre alternatif pour le référencement.
   + short-title - (champ facultatif).
   + index - oui/non - la page sera indexée par la plateforme de recherche d&#39;Adobe.
   + translate - yes/no - cette page sera localisée.
   + version utilisée principalement pour AEM et Campaign, pour indiquer la version du produit.
   + private-feature-pack - utilisé principalement pour AEM.
   + bêta : ce produit est-il en version bêta ?
   + redirect - peut être utilisée pour créer une référence à une nouvelle page, le cas échéant.
   + doc-type : référence (par défaut)/dépannage/développeur/développeur/kb/whitepboy.

## Plus d’informations

For more publishing instructions, style guides, samples and other resources, please visit the [Collaborative Documentation Repo](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
