---
description: Décrit les paires clé-valeur communes au niveau de la plateforme que vous pouvez utiliser pour cible les utilisateurs avec des variables géographiques sur toutes les propriétés de votre compte d’Audience Manager.
seo-description: Décrit les paires clé-valeur communes au niveau de la plateforme que vous pouvez utiliser pour cible les utilisateurs avec des variables géographiques sur toutes les propriétés de votre compte d’Audience Manager.
seo-title: Géociblage avec des clés de niveau Platform
solution: Audience Manager
title: Géociblage avec des clés de niveau Platform
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 1%

---


# Geotargeting With Platform-level Keys {#geotargeting-with-platform-level-keys}

Décrit les paires clé-valeur communes au niveau de la plateforme que vous pouvez utiliser pour cible les utilisateurs avec des variables géographiques sur toutes les propriétés de votre compte d’Audience Manager.

<!-- c_tb_platform_vars.xml -->

## Objectif des variables de niveau Platform {#platform-variables}

Les variables de niveau Platform vous permettent de prendre les données transmises à partir d’un site particulier et de les rendre disponibles pour le ciblage sur toutes les propriétés de votre [!DNL Audience Manager] compte. Ces variables sont formées par des paires [](../../reference/key-value-pairs-explained.md) clé-valeur avec la clé préfixe par `d_` , comme illustré ci-dessous.

## Ajouter des valeurs aux clés de niveau Platform {#adding-values}

Pour certaines clés de niveau plate-forme, vous pouvez spécifier la valeur vous-même. Avec d’autres, les clés sont associées aux [!DNL IP] adresses correspondantes transmises lors d’un appel de événement. Dans les deux cas, vous devez toujours spécifier la valeur lors de la création de caractéristiques dans [!UICONTROL Trait Builder].

## Clés de niveau Platform définies par l’utilisateur {#user-defined-keys}

Vous spécifiez la valeur lors de la création de caractéristiques avec ces paires clé-valeur :

| Clé | Pour le ciblage |
|---|---|
| `d_zx` | Code postal (ex. : `d_zx=10022`). |

## Clés de niveau Platform définies par adresse IP {#keys-ip-address}

Nous travaillons avec [Digital Envoy](https://www.digitalenvoy.com/) pour obtenir et mettre à jour les données démographiques et géographiques pour les clés ci-dessous. Les valeurs de ces clés sont déterminées en faisant correspondre [!DNL IP] les adresses aux données géographiques et démographiques correspondantes. Cependant, vous devrez toujours entrer le paramètre value lors de la création de la paire clé-valeur dans [!UICONTROL Trait Builder].

| Clé | Pour le ciblage |
|--- |--- |
| d_area_code | [Codes](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes)régionaux nord-américains.  Par exemple : <ul><li>**Caractéristique**:  d_area_code=801</li><li>**Nom** de la caractéristique : Utah</li></ul> |
| d_city | Villes et villes. Téléchargez la liste [des](assets/d_city.txt)villes.  Par exemple : <ul><li>Caractéristique :  d_city=bonn</li><li>Nom de la caractéristique : Bonn</li></ul> **Conseil**: Vous pouvez utiliser `d_city` couplé `d_country` pour être sûr de ne pas cibler deux villes portant le même nom dans des pays différents. Vous pouvez être encore plus précis dans votre ciblage en utilisant `d_postal_code`. |
| d_country | Les valeurs correspondent aux codes de pays ISO. Pour obtenir une liste de codes pouvant faire l&#39;objet d&#39;une recherche, consultez le Platform [de navigation en ligne](https://www.iso.org/obp/ui/#home)ISO. <br>  Le ciblage pour le Royaume-Uni est le seul cas particulier qui n&#39;obéit pas à la norme ISO 3166. Vous devez utiliser &quot;Royaume-Uni&quot; au lieu de &quot;GB&quot; pour le ciblage au Royaume-Uni.  Pour cible aux Antilles néerlandaises, le code &quot;AN&quot; est abandonné depuis 2010. La zone a été dissoute en cinq unités territoriales distinctes. Cela signifie que pour le ciblage dans les Antilles néerlandaises, vous ne devriez pas utiliser &quot;AN&quot;, mais une combinaison des codes de pays pour &quot;CW&quot;, &quot;SX&quot; et &quot;BQ&quot;.  Par exemple :  <br>  Caractéristique :  d_country=CZ Nom de <br>caractéristique : République tchèque <br>Caractéristique :  d_country=UK <br>Trait Name : Royaume-Uni <br>Caractéristique :  d_country=CW OR d_country=SX OR d_country=BQ Nom de <br>caractéristique : Antilles néerlandaises |
| d_dma_code | Codes DMA de la zone métropolitaine. Téléchargez la liste [de région](assets/DMAregions.csv) DMA (format .csv).  Par exemple : <ul><li>Caractéristique :  d_dma_code=807</li><li>Nom de la caractéristique : San Francisco</li></ul> |
| d_lat | Latitude (par exemple d_lat=40,75). Téléchargez la liste [des](assets/d_lat.txt)latitudes. |
| d_long | Longitude (par ex. d_long=73,98). Téléchargez la liste [de](assets/d_long.txt)longitudes. |
| d_postal_code | Codes postaux (excluez le code +4 étendu). Téléchargez la liste [des codes](assets/d_postal_code.txt)postaux.  Par exemple : <ul><li>Caractéristique :  d_postal_code=84004 </li><li>Nom de la caractéristique : Alpin</li></ul> |
| d_state | abréviation à 2 caractères pour un état américain. Téléchargez la liste [des codes](assets/d_state.txt)d’état.  Par exemple : <ul><li>Caractéristique :  d_state=NY </li><li>Nom de la caractéristique : New York</li></ul>d_state contient des valeurs répétées pour différents états dans différents pays. Par exemple, d_state == &quot;on&quot; correspond à plusieurs états : Ontario (au Canada), Ondo (au Nigeria), Oshana (en Namibie). Nous vous recommandons d’associer ce signal à d_country pour un géociblage plus spécifique. |
| d_region | Identifiants alphanumériques régionaux. Téléchargez la liste [de](assets/Country_RegionCodes_City.csv)région.  Vous pouvez ensuite utiliser cette liste pour faire correspondre les ID de région aux noms de région. |
| d_isp | ISP/organisation. Téléchargez la Liste [](assets/d_isp.txt)ISP. |

La liste de [tous les signaux](assets/all.txt) basés sur l&#39;emplacement comprend tous les signaux ci-dessus, dans l&#39;ordre suivant : `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Préfixe requis pour les variables clés](../../features/traits/trait-variable-prefixes.md)

