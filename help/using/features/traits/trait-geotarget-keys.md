---
description: Décrit les paires clé-valeur courantes au niveau de la plateforme que vous pouvez utiliser pour cibler les utilisateurs avec des variables géographiques sur toutes les propriétés de votre compte d’Audience Manager.
seo-description: Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.
seo-title: Geotargeting With Platform-level Keys
solution: Audience Manager
title: Geotargeting avec clés au niveau de la plateforme
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
exl-id: 449096f9-64fd-495f-ac1d-3181a4544279
source-git-commit: 2de7aba53e3c88d31270f2acb4fa29389f940312
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 2%

---

# Geotargeting avec clés au niveau de la plateforme {#geotargeting-with-platform-level-keys}

Décrit les paires clé-valeur courantes au niveau de la plateforme que vous pouvez utiliser pour cibler les utilisateurs avec des variables géographiques sur toutes les propriétés de votre compte d’Audience Manager.

<!-- c_tb_platform_vars.xml -->

## Objectif des variables au niveau de la plateforme {#platform-variables}

Les variables au niveau de la plateforme vous permettent de prendre les données transmises à partir d’un site particulier et de les rendre disponibles pour le ciblage sur toutes les propriétés de votre compte [!DNL Audience Manager]. Ces variables sont formées par [paires clé-valeur](../../reference/key-value-pairs-explained.md) avec le préfixe clé `d_` comme illustré ci-dessous.

## Ajout de valeurs aux clés au niveau des plateformes {#adding-values}

Pour certaines clés au niveau de la plateforme, vous pouvez spécifier la valeur vous-même. Avec d’autres, les clés sont associées aux adresses [!DNL IP] correspondantes transmises lors d’un appel d’événement. Dans les deux cas, vous devez toujours spécifier la valeur lors de la création de caractéristiques dans [!UICONTROL Trait Builder].

## Clés définies par l’utilisateur au niveau de la plateforme {#user-defined-keys}

Si vous avez déjà, ou que vous créez, un processus pour définir et collecter des paires clé-valeur, utilisez cette option. Si vous souhaitez utiliser des clés prédéfinies par adresse IP, passez à la section suivante. Dans le cas de clés définies par l’utilisateur, vous spécifiez la valeur lors de la création de caractéristiques avec ces paires clé-valeur :

| Clé | Pour le ciblage |
|---|---|
| `d_zx` | Code postal (par exemple, `d_zx=10022`). |

## Clés au niveau de la plateforme définies par adresse IP {#keys-ip-address}

Nous travaillons avec [Digital Envoy](https://www.digitalenvoy.com/) pour obtenir et mettre à jour les données démographiques et géographiques des clés ci-dessous. Les valeurs de ces clés sont déterminées en faisant correspondre [!DNL IP] adresses aux données géographiques et démographiques correspondantes. Cependant, vous devrez toujours saisir le paramètre value lors de la création de la paire clé-valeur dans [!UICONTROL Trait Builder].

| Clé | Pour le ciblage |
|--- |--- |
| d_area_code | [Codes de zone nord-américains](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes).  Par exemple : <ul><li>**Caractéristique** : d_area_code=801</li><li>**Nom de caractéristique** : Utah</li></ul> |
| d_city | Villes et villes. Téléchargez la [liste des villes](assets/d_city.txt).  Par exemple : <ul><li>Caractéristique : d_city=bonn</li><li>Nom de la caractéristique : Bonn</li></ul> **Conseil** : Vous pouvez utiliser `d_city` couplé à `d_country` pour vous assurer que vous ne ciblez pas deux villes portant le même nom dans différents pays. Vous pouvez être encore plus précis dans votre ciblage en utilisant `d_postal_code`. |
| d_country | Les valeurs correspondent aux codes pays ISO. Pour obtenir une liste des codes pouvant faire l’objet d’une recherche, voir la [plateforme de navigation en ligne ISO](https://www.iso.org/obp/ui/#home). <br>  Le ciblage pour le Royaume-Uni est le seul cas particulier qui ne respecte pas la norme ISO 3166. Vous devez utiliser &quot;UK&quot; au lieu de &quot;GB&quot; pour le ciblage au Royaume-Uni.  Pour cibler les Antilles néerlandaises, le code &quot;AN&quot; est obsolète depuis 2010. La zone a été dissoute en cinq unités territoriales distinctes. Cela signifie que pour le ciblage aux Antilles néerlandaises, vous ne devriez pas utiliser &quot;AN&quot;, mais une combinaison des codes de pays pour &quot;CW&quot;, &quot;SX&quot; et &quot;BQ&quot;.  Par exemple : <br>  Caractéristique : d_country=CZ <br>  Nom de la caractéristique : République tchèque <br>  Caractéristique : d_country=UK <br>  Nom de la caractéristique : Royaume-Uni <br>  Caractéristique : d_country=CW OU d_country=SX OU d_country=BQ <br>  Nom de caractéristique : Antilles néerlandaises |
| d_dma_code | Codes DMA de l’agglomération. Téléchargez la [liste de régions DMA](assets/DMAregions.csv) (format .csv).  Par exemple : <ul><li>Caractéristique : d_dma_code=807</li><li>Nom de la caractéristique : San Francisco</li></ul> |
| d_lat | Latitude (par exemple d_lat=40.75). Téléchargez la [liste des latitudes](assets/d_lat.txt). |
| d_long | Longitude (par exemple, d_long=73.98). Téléchargez la [liste de longitudes](assets/d_long.txt). |
| d_postal_code | Codes postaux (excluez le code +4 étendu). Téléchargez la [liste de codes postaux](assets/d_postal_code.txt).  Par exemple : <ul><li>Caractéristique : d_postal_code=84004 </li><li>Nom de la caractéristique : Alpine</li></ul> |
| d_state | Abréviation de 2 caractères pour un état américain. Téléchargez la [liste des codes d’état](assets/d_state.txt).  Par exemple : <ul><li>Caractéristique : d_state=NY </li><li>Nom de la caractéristique : New York</li></ul>d_state contient des valeurs répétées pour différents états dans différents pays. Par exemple, d_state == &quot;on&quot; correspond à plusieurs états : Ontario (au Canada), Ondo (au Nigeria), Oshana (en Namibie). Nous vous recommandons de lier ce signal à d’autres, comme d_country, pour un géociblage plus spécifique. |
| d_region | ID alphanumériques régionaux. Téléchargez la [liste des régions](assets/Country_RegionCodes_City.csv).  Vous pouvez ensuite utiliser cette liste pour faire correspondre les identifiants de région aux noms de région. |
| d_isp | Fournisseur d’accès Internet/organisation. Téléchargez la [liste des FAI](assets/d_isp.txt). |

La liste de [tous les signaux basés sur l&#39;emplacement](assets/all.txt) comprend tous les signaux ci-dessus, dans l&#39;ordre suivant : `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Exigences de préfixe pour les variables clés](../../features/traits/trait-variable-prefixes.md)

