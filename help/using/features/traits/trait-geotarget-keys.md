---
description: Décrit les paires clé-valeur communes au niveau de la plateforme que vous pouvez utiliser pour cible les utilisateurs avec des variables géographiques sur toutes les propriétés de votre compte d’Audience Manager.
seo-description: Décrit les paires clé-valeur communes au niveau de la plateforme que vous pouvez utiliser pour cible les utilisateurs avec des variables géographiques sur toutes les propriétés de votre compte d’Audience Manager.
seo-title: Géociblage à l’aide de clés au niveau des plateformes
solution: Audience Manager
title: Géociblage à l’aide de clés au niveau des plateformes
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 4%

---


# Géociblage à l’aide de clés au niveau des plateformes {#geotargeting-with-platform-level-keys}

Décrit les paires clé-valeur communes au niveau de la plateforme que vous pouvez utiliser pour cible les utilisateurs avec des variables géographiques sur toutes les propriétés de votre compte d’Audience Manager.

<!-- c_tb_platform_vars.xml -->

## Objet des variables au niveau de la plate-forme {#platform-variables}

Les variables au niveau de la plate-forme vous permettent de prendre les données transmises à partir d&#39;un site particulier et de les rendre disponibles pour le ciblage sur toutes les propriétés de votre compte [!DNL Audience Manager]. Ces variables sont formées par des paires [clé-valeur](../../reference/key-value-pairs-explained.md) avec la clé précédée de `d_` comme indiqué ci-dessous.

## Ajouter des valeurs aux clés de niveau plate-forme {#adding-values}

Pour certaines clés de niveau plate-forme, vous pouvez spécifier la valeur vous-même. Avec d&#39;autres, les clés sont associées aux adresses [!DNL IP] correspondantes transmises lors d&#39;un appel de événement. Dans les deux cas, vous devez toujours spécifier la valeur lors de la création de caractéristiques dans [!UICONTROL Trait Builder].

## Clés définies par l&#39;utilisateur au niveau de la plate-forme {#user-defined-keys}

Vous spécifiez la valeur lors de la création de caractéristiques avec ces paires clé-valeur :

| Clé | Pour le ciblage |
|---|---|
| `d_zx` | Code postal (par exemple, `d_zx=10022`). |

## Clés de niveau plate-forme définies par adresse IP {#keys-ip-address}

Nous collaborons avec [Digital Envoy](https://www.digitalenvoy.com/) pour obtenir et mettre à jour les données démographiques et géographiques pour les clés ci-dessous. Les valeurs de ces clés sont déterminées en faisant correspondre les adresses [!DNL IP] aux données géographiques et démographiques correspondantes. Cependant, vous devrez toujours entrer le paramètre value lors de la création de la paire clé-valeur dans [!UICONTROL Trait Builder].

| Clé | Pour le ciblage |
|--- |--- |
| d_area_code | [Codes](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes) régionaux nord-américains.  Par exemple : <ul><li>**Caractéristique** : d_area_code=801</li><li>**Nom** de la caractéristique : Utah</li></ul> |
| d_city | Villes et villes. Téléchargez la [liste des villes](assets/d_city.txt).  Par exemple : <ul><li>Caractéristique :  d_city=bonn</li><li>Nom de la caractéristique : Bonn</li></ul> **Conseil** : Vous pouvez utiliser  `d_city` couplé avec  `d_country` pour vous assurer que vous ne ciblez pas deux villes portant le même nom dans des pays différents. Vous pouvez être encore plus précis dans votre ciblage en utilisant `d_postal_code`. |
| d_country | Les valeurs correspondent aux codes de pays ISO. Pour obtenir une liste de codes pouvant faire l&#39;objet d&#39;une recherche, voir la [plate-forme de navigation en ligne ISO](https://www.iso.org/obp/ui/#home). <br>  Le ciblage pour le Royaume-Uni est le seul cas particulier qui n&#39;obéit pas à la norme ISO 3166. Vous devez utiliser &quot;Royaume-Uni&quot; au lieu de &quot;GB&quot; pour le ciblage au Royaume-Uni.  Pour cible aux Antilles néerlandaises, le code &quot;AN&quot; est abandonné depuis 2010. La zone a été dissoute en cinq unités territoriales distinctes. Cela signifie que pour le ciblage dans les Antilles néerlandaises, vous ne devriez pas utiliser &quot;AN&quot;, mais une combinaison des codes de pays pour &quot;CW&quot;, &quot;SX&quot; et &quot;BQ&quot;.  Par exemple :  <br>  Caractéristique :  d_country=CZ <br>  Nom de la caractéristique : République tchèque <br>  Caractéristique :  d_country=UK <br>  Nom de la caractéristique : Royaume-Uni <br>  Caractéristique :  d_country=CW OU d_country=SX OU d_country=BQ <br>  Nom de la caractéristique : Antilles néerlandaises |
| d_dma_code | Codes DMA de la zone métropolitaine. Téléchargez la [liste de région DMA](assets/DMAregions.csv) (format .csv).  Par exemple : <ul><li>Caractéristique :  d_dma_code=807</li><li>Nom de la caractéristique : San Francisco</li></ul> |
| d_lat | Latitude (par exemple d_lat=40,75). Téléchargez la liste [latitudes](assets/d_lat.txt). |
| d_long | Longitude (par ex. d_long=73,98). Téléchargez la [liste de longitudes](assets/d_long.txt). |
| d_postal_code | Codes postaux (excluez le code +4 étendu). Téléchargez la [liste des codes postaux](assets/d_postal_code.txt).  Par exemple : <ul><li>Caractéristique :  d_postal_code=84004 </li><li>Nom de la caractéristique : Alpin</li></ul> |
| d_state | abréviation à 2 caractères pour un état américain. Téléchargez la liste [codes états](assets/d_state.txt).  Par exemple : <ul><li>Caractéristique :  d_state=NY </li><li>Nom de la caractéristique : New York</li></ul>d_state contient des valeurs répétées pour différents états dans différents pays. Par exemple, d_state == &quot;on&quot; correspond à plusieurs états : Ontario (au Canada), Ondo (au Nigeria), Oshana (en Namibie). Nous vous recommandons d’associer ce signal à d_country pour un géociblage plus spécifique. |
| d_region | Identifiants alphanumériques régionaux. Téléchargez la [liste de région](assets/Country_RegionCodes_City.csv).  Vous pouvez ensuite utiliser cette liste pour faire correspondre les ID de région aux noms de région. |
| d_isp | ISP/organisation. Téléchargez la [Liste ISP](assets/d_isp.txt). |

La liste de [tous les signaux basés sur l&#39;emplacement](assets/all.txt) comprend tous les signaux ci-dessus, dans l&#39;ordre suivant : `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Exigences de préfixe pour les variables clés](../../features/traits/trait-variable-prefixes.md)

