---
description: Cet article décrit les préfixes que vous devez joindre aux variables clés lors de la création de règles de caractéristiques.
seo-description: Cet article décrit les préfixes que vous devez joindre aux variables clés lors de la création de règles de caractéristiques.
seo-title: Exigences de préfixe pour les variables clés
solution: Audience Manager
title: Exigences de préfixe pour les variables clés
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
feature: Traits
translation-type: tm+mt
source-git-commit: 1c0d40082cd0753a9b4326aae764eb74aefb8be4
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 5%

---


# Exigences de préfixe pour les variables clés {#prefix-requirements-for-key-variables}

Cet article décrit les préfixes que vous devez joindre aux variables clés lors de la création de règles de caractéristiques.

<!-- r_tb_variable_prefixes.xml -->

## Objectif des préfixes de variables clés

Lorsque vous créez des règles [!UICONTROL Trait Builder], il est important de préfacer la variable clé avec un préfixe recommandé. Ces préfixes identifient le type de données transmises et permettent d&#39;éviter les conflits d&#39;espace de nommage dans [!DNL Audience Manager]. En règle générale, vous pouvez attribuer n’importe quel nom à une variable, mais les données d’une règle ne sont pas traitées si le nom de la variable clé ne correspond pas au nom de la variable dans un appel de événement.

## Préfixes pour les variables clés

Le tableau suivant définit les préfixes communs utilisés par [!UICONTROL Trait Builder].

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
   <td colname="col2"> <p>Au niveau <span class="keyword"> Audience Manager</span>. Ces données sont uniformes dans l'écosystème <span class="keyword"> Audience Manager</span>. Voir <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Attributs pris en charge pour les appels d’API DCS</a> pour obtenir une liste plus complète.</p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>Il contient des informations <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> d’en-tête HTTP</a>. Inclut des paramètres d’en-tête tels que <code> referer</code>,<code> IP</code>, <code> accept-language</code>, etc. </p> <p> <p>Remarque : Pour les clients utilisant des versions de DIL antérieures à la version 9.0, la collecte de données utilisant le signal <code> h_referer</code> ne fonctionne pas sur les navigateurs Safari. Avec l’introduction de <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, les navigateurs Safari peuvent classer le domaine demdex.net comme outil de suivi et tronquer le parrain sur la demande de collecte de données pour ne contenir que l’origine au lieu de l’URL complète. Voir <a href="../../dil/dil-overview.md#get-implement-dil-code">Obtention et implémentation du code du DIL</a> pour obtenir la dernière version du DIL.<p>Les signaux utilisant ce préfixe ne sont pas affichés dans <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">Recherche de signal</a>.</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>Nos serveurs de collecte de données <span class="wintitle"> </span> permettent de transmettre des paramètres privés. En gros, tout paramètre qui début avec <code> p_</code> sera utilisé pour l'évaluation des caractéristiques, mais il ne sera pas consigné en aval ni stocké. </p> <p>Exemple : étant donné <code> /event?p_age=23</code> et une caractéristique telle que <code> YoungPeople = p_age &lt; 25</code>, la caractéristique sera réalisée, mais la paire <code> p_age=23</code> clé-valeur sera supprimée après la demande et ne sera pas enregistrée. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Présentation des informations de base](../../features/traits/create-onboarded-rule-based-traits.md)
>* [Gestion des règles de caractéristiques](../../features/traits/manage-trait-rules.md#managing-trait-rules)

