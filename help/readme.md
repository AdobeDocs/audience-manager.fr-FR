---
source-git-commit: dee392312d8e0381c714a99b5d537c767107c9bc
translation-type: tm+mt

---
# Instructions

**Remarque : Cette page (ou n’importe quelle page readme.md) ne sera pas publiée sur la documentation destinée au client.**

## Table des matières

+ `TOC.md` à la racine du guide de l’utilisateur fournit l’organisation des rubriques contenues dans le guide de cette solution.
+ Chaque guide d'utilisateur a son propre nom unique `TOC.md`, dans lequel vous pouvez commander toutes les pages/rubriques si nécessaire.
+ La première page de tous les guides d’utilisation est `overview.md`.

## Guide de l’utilisateur

+ L’introduction au guide de l’utilisateur s’appelle `overview.md`
+ Chaque rubrique du guide de l’utilisateur possède son propre répertoire.
   + S’il existe une rubrique dans le guide appelée *Implémentation*, le répertoire correspondant est `/implementation`
+ Tous les fichiers d’image sont stockés `/assets` à la racine du guide de l’utilisateur.
   + Toutes les images du `/assets` répertoire seront localisées.
   + Toutes les images du `/no-localize` répertoire ne seront pas localisées (c'est une surprise !). Cela permet de garantir dans les versions localisées que des fichiers spécifiques ne sont pas reproduits inutilement.

## Métadonnées de niveau guide de l’utilisateur

+ Les métadonnées qui décrivent le guide de l’utilisateur sont stockées dans le `TOC.md`. Cela inclut :
   + product - nom du produit/de la fonctionnalité.
   + cloud - cloud auquel ce produit appartient.
   + audience - public ou archétype auquel le guide est ciblé.
   + guide-utilisateur - nom du guide d’utilisateur.

## Métadonnées au niveau de la page

+ Les métadonnées requises pour décrire un document sont stockées dans le cadre de chaque page. Cela inclut :
   + title - titre de la page.
   + description - description de la page.
   + seo-title - seo titre alternatif.
   + seo-description - titre alternatif à des fins d’optimisation du référencement.
   + short-title - (champ facultatif).
   + index - oui / non - la page sera indexée par la plateforme de recherche d’Adobe.
   + traduisez - oui / non - cette page sera localisée.
   + version - utilisée principalement pour AEM et Campaign, pour indiquer la version du produit.
   + private-feature-pack - utilisé principalement pour AEM.
   + bêta - est-ce que ce produit est en version bêta ?
   + redirection : permet de créer une référence à une nouvelle page si cela est nécessaire.
   + doc-type : reference (par défaut) / dépannage / développeur / tutorial / kb / livre blanc.

## Plus d’informations

Pour plus d’instructions de publication, de guides de style, d’exemples et d’autres ressources, consultez le rapport Documentation [collaborative](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
