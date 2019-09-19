---
description: Décrit les paires clé-valeur communes au niveau de la plateforme que vous pouvez utiliser pour cibler les utilisateurs avec des variables géographiques sur toutes les propriétés de votre compte Audience Manager.
seo-description: Décrit les paires clé-valeur communes au niveau de la plateforme que vous pouvez utiliser pour cibler les utilisateurs avec des variables géographiques sur toutes les propriétés de votre compte Audience Manager.
seo-title: Géociblage Avec Des Clés Au Niveau De La Plateforme
solution: Audience Manager
title: Géociblage Avec Des Clés Au Niveau De La Plateforme
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
translation-type: tm+mt
source-git-commit: c5c57423bcba8d4b3974a04c46dc7c7afc7484a0

---


# Geotargeting With Platform-level Keys {#geotargeting-with-platform-level-keys}

Décrit les paires clé-valeur communes au niveau de la plateforme que vous pouvez utiliser pour cibler les utilisateurs avec des variables géographiques sur toutes les propriétés de votre compte Audience Manager.

<!-- c_tb_platform_vars.xml -->

## Objectif des variables au niveau de la plateforme {#platform-variables}

Les variables de niveau plate-forme vous permettent de prendre en compte les données transmises à partir d’un site particulier et de les rendre disponibles pour le ciblage sur toutes les propriétés de votre [!DNL Audience Manager] compte. Ces variables sont formées par des paires [clé-valeur](../../reference/key-value-pairs-explained.md) avec la clé précédée du préfixe `d_` comme illustré ci-dessous.

## Ajout de valeurs aux clés de niveau plate-forme {#adding-values}

Pour certaines clés au niveau de la plate-forme, vous pouvez spécifier la valeur vous-même. Avec d’autres, les clés sont associées aux [!DNL IP] adresses correspondantes transmises lors d’un appel d’événement. Dans les deux cas, vous devez toujours spécifier la valeur lors de la création de caractéristiques dans [!UICONTROL Trait Builder].

## Clés définies par l’utilisateur au niveau de la plateforme {#user-defined-keys}

Vous spécifiez la valeur lors de la création de caractéristiques avec ces paires clé-valeur :

| Clé | Pour le ciblage |
|---|---|
| `d_zx` | Code postal (ex. : `d_zx=10022`). |

## Clés de niveau plateforme définies par adresse IP {#keys-ip-address}

Nous travaillons avec [Digital Envoy](https://www.digitalenvoy.com/) pour obtenir et mettre à jour les données démographiques et géographiques pour les clés ci-dessous. Les valeurs de ces clés sont déterminées par la correspondance [!DNL IP] des adresses avec les données géographiques et démographiques correspondantes. Cependant, vous devrez toujours saisir le paramètre value lors de la création de la paire clé-valeur dans [!UICONTROL Trait Builder].

| Clé | Pour le ciblage |
|--- |--- |
| d_area_code | [Codes](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes)régionaux nord-américains.  Par exemple : <ul><li>**Caractéristique**:  d_area_code=801</li><li>**Nom** du trait : Utah</li></ul> |
| d_city | Villes et villes. Téléchargez la liste des [villes](assets/d_city.txt).  Par exemple : <ul><li>Caractéristique :  d_city=bonn</li><li>Nom du trait : Bonn</li></ul> **Conseil**: Vous pouvez utiliser `d_city` couplé à `d_country` pour être sûr de ne pas cibler deux villes du même nom dans différents pays. Vous pouvez être encore plus précis dans votre ciblage en utilisant `d_postal_code`. |
| d_country | Les valeurs correspondent aux codes pays ISO. Pour obtenir la liste des codes pouvant faire l'objet d'une recherche, voir la plate-forme [de navigation en ligne](https://www.iso.org/obp/ui/#home)ISO. <br>  Le ciblage pour le Royaume-Uni est le seul cas particulier qui ne respecte pas la norme ISO 3166. Utilisez "Royaume-Uni" au lieu de "GB" pour le ciblage au Royaume-Uni.  Pour cibler les Antilles néerlandaises, le code "AN" est obsolète depuis 2010. La zone a été dissoute en cinq unités territoriales distinctes. Cela implique que pour le ciblage dans les Antilles néerlandaises, vous ne devriez pas utiliser "AN", mais une combinaison des codes de pays pour "CW", "SX" et "BQ".  Par exemple :  <br>Caractéristique :  d_country=CZ Nom <br>du trait : République tchèque <br>Trait :  d_country=UK <br>Trait Name : Royaume-Uni <br>:  d_country=CW OR d_country=SX OR d_country=BQ Nom <br>du trait : Antilles néerlandaises |
| d_dma_code | Codes DMA de zone métropolitaine. Téléchargez la liste des [régions](assets/DMAregions.csv) DMA (.csv format).  Par exemple : <ul><li>Caractéristique :  d_dma_code=807</li><li>Nom du trait : San Francisco</li></ul> |
| d_lat | Latitude (par exemple d_lat=40.75). Téléchargez la liste [des](assets/d_lat.txt)latitudes. |
| d_long | Longitude (p. ex. d_long=73,98). Téléchargez la liste [des](assets/d_long.txt)longitudes. |
| d_postal_code | Codes postaux (excluez le code +4 étendu). Téléchargez la liste [des codes](assets/d_postal_code.txt)postaux.  Par exemple : <ul><li>Caractéristique :  d_postal_code=84004 </li><li>Nom du trait : Alpin</li></ul> |
| d_state | Abréviation de 2 caractères pour un état américain. Téléchargez la liste [des codes](assets/d_state.txt)d’état.  Par exemple : <ul><li>Caractéristique :  d_state=NY </li><li>Nom du trait : New York</li></ul>d_state contient des valeurs répétées pour différents états dans différents pays. Par exemple, d_state == "on" correspond à plusieurs états : Ontario (au Canada), Ondo (au Nigeria), Oshana (en Namibie). Nous vous recommandons d’associer ce signal à d_country pour un géociblage plus spécifique. |
|  d_region | ID alphanumériques régionaux. Téléchargez la liste [des](assets/Country_RegionCodes_City.csv)régions.  Vous pouvez ensuite utiliser cette liste pour faire correspondre les ID de région aux noms de région. |
| d_isp | FAI/organisation. Téléchargez la liste des [FAI](assets/d_isp.txt). |

La liste de [tous les signaux](assets/all.csv) basés sur l'emplacement comprend tous les signaux ci-dessus, dans l'ordre suivant: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORE_LIKE_This]
>
>* [Préfixe requis pour les variables clés](../../features/traits/trait-variable-prefixes.md)

