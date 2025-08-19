---
description: Cet article décrit les préfixes que vous devez attacher aux variables clés lors de la création de règles de caractéristique.
seo-description: This article describes the prefixes you must attach to key variables when creating trait rules.
seo-title: Prefix Requirements for Key Variables
solution: Audience Manager
title: Exigences de préfixe pour les variables clés
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
feature: Traits
exl-id: 67fe0c74-6831-48cb-90cf-417ebbf7f272
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---

# Exigences de préfixe pour les variables clés {#prefix-requirements-for-key-variables}

Cet article décrit les préfixes que vous devez attacher aux variables clés lors de la création de règles de caractéristique.

<!-- r_tb_variable_prefixes.xml -->

## Objectif des préfixes de variables clés

Lorsque vous créez des règles de [!UICONTROL Trait Builder], il est important de faire précéder la variable clé d’un préfixe recommandé. Ces préfixes identifient le type de données transmis et permettent d’éviter les conflits d’espace de noms dans [!DNL Audience Manager]. En règle générale, vous pouvez donner un nom à une variable, mais les données d’une règle ne sont pas traitées si le nom de la variable clé ne correspond pas au nom de la variable dans un appel d’événement.

## Préfixes des variables clés

Le tableau suivant définit les préfixes courants utilisés par [!UICONTROL Trait Builder].

<table id="table_CFEFA1DBDF904736B6EA2640B7AD26E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Préfixe de variable clé </th> 
   <th colname="col2" class="entry"> Identifie la variable </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code> c_</code> </td> 
   <td colname="col2"> <p>En tant que client spécifique. Il s’agit de données clés envoyées à partir de vos propres propriétés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p>Au niveau <span class="keyword"> Audience Manager</span>. Ces données sont uniformes dans l’écosystème <span class="keyword"> Audience Manager</span>. Consultez <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Attributs pris en charge pour les appels API DCS</a> pour une liste plus complète.</p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>Contient <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> en-tête HTTP </a> informations. Inclut des paramètres d’en-tête tels que <code> referer</code>, <code> IP</code>, <code> accept-language</code>, etc. </p> <p> <p>Remarque : pour les clients utilisant des versions de DIL antérieures à la version 9.0, la collecte de données à l’aide du signal <code> h_referer</code> ne fonctionne pas sur les navigateurs Safari. Avec l’introduction d’<a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, les navigateurs Safari peuvent classer le domaine demdex.net en tant que suivi et tronqueront le référent sur la demande de collecte de données pour ne contenir que l’origine au lieu de l’URL complète. Voir <a href="../../dil/dil-overview.md#get-implement-dil-code">Obtention et implémentation du code DIL</a> pour la dernière version de DIL.<p>Les signaux utilisant ce préfixe ne sont pas affichés dans <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">Recherche de signaux</a>.</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>Nos serveurs de collecte de données <span class="wintitle"></span> permettent la transmission de paramètres privés. Fondamentalement, tout paramètre commençant par <code> p_</code> sera utilisé pour l’évaluation des caractéristiques, mais il ne sera pas consigné en aval ni stocké. </p> <p>Exemple : étant donné la <code> /event?p_age=23</code> et une caractéristique comme <code> YoungPeople = p_age &lt; 25</code>, la caractéristique sera réalisée, mais la paire clé-valeur <code> p_age=23</code> sera abandonnée après la demande et ne sera pas consignée. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Présentation des informations de base](../../features/traits/create-onboarded-rule-based-traits.md)
>* [Gestion des règles de caractéristiques](../../features/traits/manage-trait-rules.md#managing-trait-rules)
