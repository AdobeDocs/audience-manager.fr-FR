---
description: Décrit les paires clé-valeur de niveau plate-forme courantes que vous pouvez utiliser pour cibler les utilisateurs avec des variables géographiques sur toutes les propriétés de votre compte Audience Manager.
seo-description: Décrit les paires clé-valeur de niveau plate-forme courantes que vous pouvez utiliser pour cibler les utilisateurs avec des variables géographiques sur toutes les propriétés de votre compte Audience Manager.
seo-title: Géociblage avec clés au niveau de la plateforme
solution: Audience Manager
title: Géociblage avec clés au niveau de la plateforme
uuid: c 7 e 4 cbfe-e 564-404 e-a 565-bbe 5 fd 2 fb 519
translation-type: tm+mt
source-git-commit: c5c57423bcba8d4b3974a04c46dc7c7afc7484a0

---


# Geotargeting With Platform-level Keys {#geotargeting-with-platform-level-keys}

Décrit les paires clé-valeur de niveau plate-forme courantes que vous pouvez utiliser pour cibler les utilisateurs avec des variables géographiques sur toutes les propriétés de votre compte Audience Manager.

<!-- c_tb_platform_vars.xml -->

## Purpose of Platform-level Variables {#platform-variables}

Platform-level variables let you take data passed in from a particular site and make it available for targeting across all the properties in your [!DNL Audience Manager] account. These variables are formed by [key-value pairs](../../reference/key-value-pairs-explained.md) with the key prefixed by `d_` as shown below.

## Adding Values to Platform Level Keys {#adding-values}

Pour certaines clés de niveau plateforme, vous pouvez spécifier la valeur vous-même. With others, the keys are associated with corresponding [!DNL IP] addresses passed in on an event call. In either case, you still need to specify the value when building traits in [!UICONTROL Trait Builder].

## User Defined Platform-Level Keys {#user-defined-keys}

Vous spécifiez la valeur lors de la création de caractéristiques avec ces paires clé-valeur :

| Clé | Pour le ciblage |
|---|---|
| `d_zx` | ZIP code (e.g., `d_zx=10022`). |

## Platform Level Keys Defined by IP Address {#keys-ip-address}

We work with [Digital Envoy](https://www.digitalenvoy.com/) to obtain and update the demographic and geographic data for the keys below. The values for these keys are determined by matching [!DNL IP] addresses to corresponding geographic and demographic data. However, you'll still have to enter the value parameter when creating the key-value pair in [!UICONTROL Trait Builder].

| Clé | Pour le ciblage |
|--- |--- |
| d_ area_ code | [Codes région de l'Amérique du Nord](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes). Par exemple : <ul><li>**Caractéristique**: d_ area_ code = 801</li><li>**Nom de la caractéristique**: Utah</li></ul> |
| d_ city | Villes et villes. Download the [cities list](assets/d_city.txt).  Par exemple : <ul><li>Caractéristique : d_ city = bonn</li><li>Nom de la caractéristique : Bonn</li></ul> **Conseil**: Vous pouvez utiliser `d_city` couplé `d_country` pour vous assurer que vous ne ciblez pas deux villes portant le même nom dans différents pays. You can be even more specific in your targeting by using `d_postal_code`. |
| d_ country | Les valeurs correspondent aux codes pays ISO. For a searchable list of codes, see the [ISO Online Browsing Platform](https://www.iso.org/obp/ui/#home). <br>Le ciblage pour le Royaume-Uni est le seul cas spécial qui n'obéit pas à ISO 3166. Utilisez « Royaume-Uni » plutôt que « GB » pour le ciblage au Royaume-Uni. Pour cibler les Antilles néerlandaises, le code « AN » est devenu obsolète depuis 2010. La zone a été divisée en cinq unités territoriales distinctes. Cela signifie que, pour le ciblage aux Antilles néerlandaises, vous ne devez pas utiliser « AN », mais une combinaison des codes pays pour « CW », « SX » et « BQ ».  » » For example:  <br>  Trait:  d_country=CZ  <br>  Trait Name: Czech Republic <br>  Trait:  d_country=UK <br>  Trait Name: United Kingdom  <br>  Trait:  d_country=CW OR d_country=SX OR d_country=BQ  <br>  Trait Name: Netherlands Antilles |
| d_ dma_ code | Codes DMA Zone métropolitaine. Download the [DMA region list](assets/DMAregions.csv) (.csv format).  Par exemple : <ul><li>Caractéristique : d_ dma_ code = 807</li><li>Nom de la caractéristique : San Francisco</li></ul> |
| d_ lat | Latitude (ex. : d_ lat = 40.75). Download the [latitudes list](assets/d_lat.txt). |
| d_ long | Longitude (ex. : d_ long = 73.98). Download the [longitudes list](assets/d_long.txt). |
| d_ postal_ code | Codes postaux (excluez le code +4 étendu). Download the  [postal codes list](assets/d_postal_code.txt).  Par exemple : <ul><li>Caractéristique : d_ postal_ code = 84004 </li><li>Nom de la caractéristique : Alpine</li></ul> |
| d_ state | Abréviation de 2 caractères pour un état US. Download the [states codes list](assets/d_state.txt).  Par exemple : <ul><li>Caractéristique : d_ state = NY </li><li>Nom de la caractéristique : New York</li></ul>d_ state contient des valeurs répétées pour différents états dans différents pays. Par exemple, d_ state = = « on » correspond à plusieurs états : Ontario (au Canada), Ondo (au Nigéria), Oshana (en Namibie). Nous vous recommandons de regrouper ce signal avec d'autres, tels que d_ country, pour un géociblage plus spécifique. |
| d_ region | Identifiants alphanumériques régionaux. Download the [region list](assets/Country_RegionCodes_City.csv).  Vous pouvez ensuite utiliser cette liste pour faire correspondre les identifiants de région aux noms de région. |
| d_ isp | Fournisseur de services Internet/organisation. Download the [ISP List](assets/d_isp.txt). |

The list of [all location-based signals](assets/all.csv) comprises all the signals above, in the following order: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORE_ LIKE_ THIS]
>
>* [Exigences en matière de préfixe pour les variables clés](../../features/traits/trait-variable-prefixes.md)

