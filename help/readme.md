---
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
translation-type: tm+mt
source-wordcount: '329'
ht-degree: 2%

---
# Instructions

**Remarque : Cette page (ou toute autre page readme.md) ne sera pas publiée dans la documentation destinée au client.**

## Table des matières

+ `TOC.md` à la racine du guide d’utilisateur fournit l’organisation des rubriques contenues dans le guide de cette solution.
+ Chaque guide d&#39;utilisateur possède son propre `TOC.md` unique, dans lequel vous pouvez commander toutes les pages/rubriques si nécessaire.
+ La première page de tous les guides d’utilisateur est `overview.md`.

## Guide de l’utilisateur

+ L&#39;introduction au guide d&#39;utilisation s&#39;appelle `overview.md`
+ Chaque rubrique du guide d’utilisateur possède son propre répertoire.
   + S’il existe une rubrique dans le guide appelée *Implémentation*, le répertoire correspondant est `/implementation`
+ Tous les fichiers d’image sont stockés dans `/assets` à la racine du guide d’utilisateur.
   + Toutes les images du répertoire `/assets` seront localisées.
   + Toutes les images du répertoire `/no-localize` ne seront pas localisées (surprise !). Cela permet de s’assurer, dans les versions localisées, que des fichiers spécifiques ne sont pas reproduits inutilement.

## Métadonnées du niveau du guide de l’utilisateur

+ Les métadonnées qui décrivent le guide d’utilisateur sont stockées dans `TOC.md`. Cela inclut :
   + product - nom du produit/de la fonctionnalité.
   + cloud - cloud auquel ce produit appartient.
   + audience - audience ou archétype à qui le guide est ciblé.
   + guide d’utilisateur - nom du guide d’utilisateur.

## Métadonnées au niveau de la page

+ Les métadonnées requises pour décrire un document sont stockées dans le cadre de chaque page. Cela inclut :
   + title - titre de la page.
   + description - description de la page.
   + seo-title - seo alternative title.
   + seo-description - titre alternatif à des fins d’optimisation du référencement.
   + short-title - (champ facultatif).
   + index - oui / non - la page sera indexée par la plateforme de recherche de l&#39;Adobe.
   + traduire - oui / non - cette page sera-t-elle localisée.
   + version - utilisée principalement pour AEM et Campaign, pour désigner la version du produit.
   + private-feature-pack - utilisé principalement pour les AEM.
   + bêta - est-ce que ce produit est en bêta ?
   + redirection : permet de créer une référence à une nouvelle page si nécessaire.
   + doc-type : référence (par défaut) / dépannage / développeur / tutorial / kb / livre blanc.

## Plus d’informations

Pour plus d&#39;instructions de publication, de guides de style, d&#39;exemples et d&#39;autres ressources, consultez le [Rapport de documentation collaborative](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
