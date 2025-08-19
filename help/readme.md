---
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 2%

---
# Instructions

**Remarque : cette page (ou toute page readme.md) ne sera pas publiée dans la documentation destinée aux clients**

## TABLE DES MATIÈRES

+ `TOC.md` racine du guide d’utilisation fournit l’organisation des rubriques contenues dans le guide de cette solution.
+ Chaque guide de l’utilisateur possède son propre `TOC.md` unique, dans lequel vous pouvez classer toutes les pages/rubriques selon vos besoins.
+ La première page de tous les guides de l’utilisateur est `overview.md`.

## Guide d’utilisation

+ L’introduction au guide de l’utilisateur s’appelle `overview.md`
+ Chaque rubrique du guide d’utilisation possède son propre répertoire distinct.
   + S’il existe dans le guide une rubrique appelée *Implémentation*, le répertoire correspondant est `/implementation`
+ Toutes les ressources d’image sont stockées dans `/assets` à la racine du guide d’utilisation.
   + Toutes les images du répertoire `/assets` seront localisées.
   + Les images du répertoire `/no-localize` ne seront pas localisées (c&#39;est une surprise !). Vous pouvez l’utiliser pour vous assurer que dans les versions verrouillées, des ressources spécifiques ne sont pas reproduites inutilement.

## Métadonnées du niveau du guide de l’utilisateur

+ Les métadonnées qui décrivent le guide d’utilisation sont stockées dans le `TOC.md` . Cela inclut :
   + produit - nom du produit/de la fonctionnalité.
   + cloud : cloud auquel appartient ce produit.
   + audience : audience ou archétype ciblé(e) par le guide.
   + guide de l’utilisateur : nom du guide de l’utilisateur.

## Métadonnées au niveau de la page

+ Les métadonnées requises pour décrire un document sont stockées dans le cadre de chaque page individuelle. Cela inclut :
   + titre - titre de la page.
   + description : description de la page.
   + seo-title : titre alternatif de l’optimisation du moteur de recherche.
   + seo-description - titre alternatif à des fins de SEO.
   + titre court - (champ facultatif).
   + index - oui/non - la page sera-t-elle indexée par la plateforme de recherche Adobe ?
   + traduire - oui/non - cette page sera-t-elle localisée ?
   + version : utilisé principalement pour AEM et Campaign, pour indiquer la version du produit.
   + private-feature-pack - utilisé principalement pour AEM.
   + version bêta - ce produit est-il en version bêta ?
   + redirection - peut être utilisé pour créer une référence à une nouvelle page, le cas échéant.
   + type de document : référence (par défaut) / dépannage / développeur / tutoriel / ko / livre blanc.

## Plus d’informations

Pour obtenir des instructions supplémentaires sur la publication, des guides de style, des exemples et d’autres ressources, consultez le [référentiel de documentation collaborative](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
