---
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 2%

---
# Instructions

**Remarque : Cette page (ou toute page readme.md) ne sera pas publiée dans la documentation destinée aux clients**

## Table des matières

+ `TOC.md` à la racine du guide de l’utilisateur fournit l’organisation des rubriques contenues dans le guide de cette solution.
+ Chaque guide de l’utilisateur possède son propre `TOC.md`, dans lequel vous pouvez classer toutes les pages/rubriques selon vos besoins.
+ La première page de tous les guides d’utilisateur est `overview.md`.

## Guide d’utilisation

+ L’introduction au guide de l’utilisateur s’appelle `overview.md`
+ Chaque rubrique du guide de l’utilisateur possède son propre répertoire.
   + S’il existe une rubrique dans le guide appelée *Implémentation*, le répertoire correspondant est `/implementation`
+ Toutes les ressources d’image sont stockées dans `/assets` à la racine du guide de l’utilisateur.
   + Toutes les images du répertoire `/assets` seront localisées.
   + Les images du répertoire `/no-localize` ne seront pas localisées (c&#39;est une surprise !). Cela peut être utilisé pour garantir dans les versions loc que des ressources spécifiques ne sont pas reproduites inutilement.

## Métadonnées au niveau du guide de l’utilisateur

+ Les métadonnées qui décrivent le guide de l’utilisateur sont stockées dans le `TOC.md`. Cela inclut :
   + product - nom du produit/de la fonctionnalité.
   + cloud : cloud auquel ce produit appartient.
   + audience : audience ou archétype à qui le guide est ciblé.
   + user-guide - nom du guide de l’utilisateur.

## Métadonnées de niveau page

+ Les métadonnées requises pour décrire un document sont stockées dans chaque page. Cela inclut :
   + title : titre de la page.
   + description - description de la page.
   + seo-title - autre titre du seo.
   + seo-description - autre titre à des fins d’optimisation pour les moteurs de recherche.
   + short-title - (champ facultatif).
   + index - yes/no - la page sera indexée par la plateforme de recherche d’Adobe.
   + translate - yes/no - cette page sera localisée.
   + version : utilisée principalement pour AEM et Campaign, pour indiquer la version du produit.
   + private-feature-pack - utilisé principalement pour AEM.
   + beta - ce produit est-il en version bêta ?
   + redirect : peut être utilisé pour créer une référence à une nouvelle page si nécessaire.
   + doc-type : référence (par défaut)/dépannage/développeur/tutoriel/kb/livre blanc.

## Plus d’informations

Pour plus d’instructions de publication, de guides de style, d’exemples et d’autres ressources, consultez le [référentiel de documentation collaborative](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
