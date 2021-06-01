---
description: Décrit les paires clé-valeur courantes au niveau de la plateforme que vous pouvez utiliser pour cibler les utilisateurs avec des variables géographiques sur toutes les propriétés de votre compte d’Audience Manager.
seo-description: Décrit les paires clé-valeur courantes au niveau de la plateforme que vous pouvez utiliser pour cibler les utilisateurs avec des variables géographiques sur toutes les propriétés de votre compte d’Audience Manager.
seo-title: Géociblage à l’aide de clés au niveau des plateformes
solution: Audience Manager
title: Géociblage à l’aide de clés au niveau des plateformes
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: 'Caractéristiques '
exl-id: 449096f9-64fd-495f-ac1d-3181a4544279
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 4%

---

# Géociblage à l’aide de clés au niveau des plateformes {#geotargeting-with-platform-level-keys}

Décrit les paires clé-valeur courantes au niveau de la plateforme que vous pouvez utiliser pour cibler les utilisateurs avec des variables géographiques sur toutes les propriétés de votre compte d’Audience Manager.

<!-- c_tb_platform_vars.xml -->

## Objectif des variables au niveau de la plateforme {#platform-variables}

Les variables au niveau de la plateforme vous permettent de prendre les données transmises à partir d’un site particulier et de les rendre disponibles pour le ciblage sur toutes les propriétés de votre compte [!DNL Audience Manager]. Ces variables sont formées par des [paires clé-valeur](../../reference/key-value-pairs-explained.md) avec le préfixe clé `d_` comme illustré ci-dessous.

## Ajout de valeurs aux clés au niveau de la plateforme {#adding-values}

Pour certaines clés au niveau de la plateforme, vous pouvez spécifier la valeur vous-même. Avec d’autres, les clés sont associées aux adresses [!DNL IP] correspondantes transmises lors d’un appel d’événement. Dans les deux cas, vous devez toujours spécifier la valeur lors de la création de caractéristiques dans [!UICONTROL Trait Builder].

## Clés définies par l’utilisateur au niveau de la plateforme {#user-defined-keys}

Vous spécifiez la valeur lors de la création de caractéristiques avec ces paires clé-valeur :

| Clé | Pour le ciblage |
|---|---|
| `d_zx` | Code postal (par exemple, `d_zx=10022`). |

## Clés de niveau plateforme définies par adresse IP {#keys-ip-address}

Nous travaillons avec [Digital Envoy](https://www.digitalenvoy.com/) pour obtenir et mettre à jour les données démographiques et géographiques des clés ci-dessous. Les valeurs de ces clés sont déterminées en faisant correspondre les adresses [!DNL IP] aux données géographiques et démographiques correspondantes. Cependant, vous devrez toujours saisir le paramètre value lors de la création de la paire clé-valeur dans [!UICONTROL Trait Builder].

| Clé | Pour le ciblage |
|--- |--- |
| d_area_code | [Codes](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes) régionaux de l’Amérique du Nord.  Par exemple : <ul><li>**Caractéristique** : d_area_code=801</li><li>**Nom de la caractéristique** : Utah</li></ul> |
| d_city | Villes et villes. Téléchargez la [liste des villes](assets/d_city.txt).  Par exemple : <ul><li>Caractéristique :  d_city=bonn</li><li>Nom de la caractéristique : Bonn</li></ul> **Conseil** : Vous pouvez utiliser  `d_city` couplé avec  `d_country` pour vous assurer que vous ne ciblez pas deux villes portant le même nom dans différents pays. Vous pouvez être encore plus précis dans votre ciblage à l’aide de `d_postal_code`. |
| d_country | Les valeurs correspondent aux codes pays ISO. Pour obtenir une liste des codes pouvant faire l’objet d’une recherche, voir la [plateforme de navigation en ligne ISO](https://www.iso.org/obp/ui/#home). <br>  Le ciblage pour le Royaume-Uni est le seul cas particulier qui ne respecte pas la norme ISO 3166. Vous devez utiliser &quot;UK&quot; au lieu de &quot;GB&quot; pour le ciblage au Royaume-Uni.  Pour cibler les Antilles néerlandaises, le code &quot;AN&quot; est obsolète depuis 2010. La zone a été dissoute en cinq unités territoriales distinctes. Cela signifie que pour le ciblage aux Antilles néerlandaises, vous ne devriez pas utiliser &quot;AN&quot;, mais une combinaison des codes de pays pour &quot;CW&quot;, &quot;SX&quot; et &quot;BQ&quot;.  Par exemple :  <br>  Caractéristique :  d_country=CZ <br>  Nom de la caractéristique : République tchèque &lt;a2/  Caractéristique :  d_country=UK <br>  Nom de la caractéristique : Royaume-Uni <br>  Caractéristique :  d_country=CW OU d_country=SX OU d_country=BQ <br>  Nom de la caractéristique : Antilles néerlandaises<br> |
| d_dma_code | Codes DMA de l’agglomération. Téléchargez la [liste de régions DMA](assets/DMAregions.csv) (format .csv).  Par exemple : <ul><li>Caractéristique :  d_dma_code=807</li><li>Nom de la caractéristique : San Francisco</li></ul> |
| d_lat | Latitude (par exemple d_lat=40.75). Téléchargez la [liste des latitudes](assets/d_lat.txt). |
| d_long | Longitude (par exemple, d_long=73.98). Téléchargez la [liste de longitudes](assets/d_long.txt). |
| d_postal_code | Codes postaux (excluez le code +4 étendu). Téléchargez la [liste des codes postaux](assets/d_postal_code.txt).  Par exemple : <ul><li>Caractéristique :  d_postal_code=84004 </li><li>Nom de la caractéristique : Alpine</li></ul> |
| d_state | Abréviation de 2 caractères pour un état américain. Téléchargez la [liste des codes des états](assets/d_state.txt).  Par exemple : <ul><li>Caractéristique :  d_state=NY </li><li>Nom de la caractéristique : New York</li></ul>d_state contient des valeurs répétées pour différents états dans différents pays. Par exemple, d_state == &quot;on&quot; correspond à plusieurs états : Ontario (au Canada), Ondo (au Nigeria), Oshana (en Namibie). Nous vous recommandons de lier ce signal à d’autres, comme d_country, pour un géociblage plus spécifique. |
| d_region | ID alphanumériques régionaux. Téléchargez la [liste des régions](assets/Country_RegionCodes_City.csv).  Vous pouvez ensuite utiliser cette liste pour faire correspondre les identifiants de région aux noms de région. |
| d_isp | FAI/organisation. Téléchargez la [liste des FAI](assets/d_isp.txt). |

La liste de [tous les signaux basés sur l’emplacement](assets/all.txt) comprend tous les signaux ci-dessus, dans l’ordre suivant : `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Exigences de préfixe pour les variables clés](../../features/traits/trait-variable-prefixes.md)

