---
description: Décrit les paires clé-valeur courantes au niveau de la plateforme que vous pouvez utiliser pour cibler les utilisateurs avec des variables géographiques dans toutes les propriétés de votre compte Audience Manager.
seo-description: Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.
seo-title: Geotargeting With Platform-level Keys
solution: Audience Manager
title: Geotargeting avec des clés au niveau de la plateforme
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
exl-id: 449096f9-64fd-495f-ac1d-3181a4544279
source-git-commit: 2de7aba53e3c88d31270f2acb4fa29389f940312
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 2%

---

# Geotargeting avec des clés au niveau de la plateforme {#geotargeting-with-platform-level-keys}

Décrit les paires clé-valeur courantes au niveau de la plateforme que vous pouvez utiliser pour cibler les utilisateurs avec des variables géographiques dans toutes les propriétés de votre compte Audience Manager.

<!-- c_tb_platform_vars.xml -->

## Objectif des variables au niveau de la plateforme {#platform-variables}

Les variables au niveau de la plateforme vous permettent de prendre les données transmises à partir d’un site particulier et de les rendre disponibles pour le ciblage sur toutes les propriétés de votre compte [!DNL Audience Manager]. Ces variables sont formées par des [paires clé-valeur](../../reference/key-value-pairs-explained.md) avec la clé précédée de `d_` comme illustré ci-dessous.

## Ajout de valeurs aux clés au niveau de la plateforme {#adding-values}

Pour certaines clés au niveau de la plateforme, vous pouvez spécifier la valeur vous-même. Pour les autres, les clés sont associées aux adresses [!DNL IP] correspondantes transmises lors d’un appel d’événement. Dans les deux cas, vous devez toujours spécifier la valeur lors de la création des caractéristiques dans [!UICONTROL Trait Builder].

## Clés au niveau de la plateforme définies par l’utilisateur {#user-defined-keys}

Si vous disposez déjà d’un processus de définition et de collecte des paires clé-valeur ou si vous êtes en train de l’établir, utilisez cette option. Si vous souhaitez utiliser des clés prédéfinies par adresse IP, passez à la section suivante. Dans le cas de clés définies par l’utilisateur, vous spécifiez la valeur lors de la création de caractéristiques avec ces paires clé-valeur :

| Clé | Pour le ciblage |
|---|---|
| `d_zx` | Code postal (par exemple, `d_zx=10022`). |

## Clés au niveau de la plateforme définies par l’adresse IP {#keys-ip-address}

Nous travaillons avec [Digital Envoy](https://www.digitalenvoy.com/) pour obtenir et mettre à jour les données démographiques et géographiques des clés ci-dessous. Les valeurs de ces clés sont déterminées en faisant correspondre des adresses [!DNL IP] à des données géographiques et démographiques correspondantes. Cependant, vous devrez toujours saisir le paramètre de valeur lors de la création de la paire clé-valeur dans [!UICONTROL Trait Builder].

| Clé | Pour le ciblage |
|--- |--- |
| d_area_code | [Indicatifs régionaux de l&#39;Amérique du Nord](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes).  Par exemple : <ul><li>**Trait** : d_area_code=801</li><li>**Nom du caractère** : Utah</li></ul> |
| d_city | Villes et villages. Téléchargez la [liste des villes](assets/d_city.txt).  Par exemple : <ul><li>Caractéristique : d_city=bonn</li><li>Nom de la caractéristique : Bonn</li></ul> **Conseil** : Vous pouvez utiliser `d_city` associé à `d_country` pour vous assurer de ne pas cibler deux villes portant le même nom dans différents pays. Vous pouvez être encore plus spécifique dans votre ciblage à l’aide de `d_postal_code`. |
| d_country | Les valeurs correspondent aux codes pays ISO. Pour obtenir une liste de codes consultable, reportez-vous à la [Plateforme de navigation en ligne ISO](https://www.iso.org/obp/ui/#home). <br>  Le ciblage pour le Royaume-Uni est le seul cas particulier qui ne respecte pas la norme ISO 3166. Utilisez « UK » au lieu de « GB » pour le ciblage au Royaume-Uni.  Pour cibler les Antilles néerlandaises, le code « AN » est obsolète depuis 2010. La zone a été divisée en cinq unités territoriales distinctes. Cela implique que pour le ciblage aux Antilles néerlandaises, vous ne devez pas utiliser « AN », mais une combinaison des codes pays pour « CW », « SX » et « BQ ».  Par exemple : <br>  Caractéristique : d_country=CZ <br>  Nom de la caractéristique : République tchèque <br>  Caractéristique : d_country=UK <br>  Nom de la caractéristique : Royaume-Uni <br>  Caractéristique : d_country=CW OU d_country=SX OU d_country=BQ <br>  Nom de la caractéristique : Antilles néerlandaises |
| d_dma_code | Codes DMA de zone métropolitaine. Téléchargez la [liste des zones géographiques DMA](assets/DMAregions.csv) (format .csv).  Par exemple : <ul><li>Caractéristique : d_dma_code=807</li><li>Nom de la caractéristique : San Francisco</li></ul> |
| d_lat | Latitude (ex : d_lat=40.75). Téléchargez la [&#x200B; liste des latitudes &#x200B;](assets/d_lat.txt). |
| d_long | Longitude (ex : d_long=73.98). Téléchargez la [&#x200B; liste des longitudes &#x200B;](assets/d_long.txt). |
| d_postal_code | Codes postaux (exclure le code +4 étendu). Téléchargez la [&#x200B; liste des codes postaux &#x200B;](assets/d_postal_code.txt).  Par exemple : <ul><li>Caractéristique : d_postal_code=84004 </li><li>Nom de la caractéristique : Alpine</li></ul> |
| d_state | Abréviation de 2 caractères pour un état des États-Unis. Téléchargez la [liste des codes d’état](assets/d_state.txt).  Par exemple : <ul><li>Caractéristique : d_state=NY </li><li>Nom de la caractéristique : New York</li></ul>d_state contient des valeurs répétées pour différents états dans différents pays. Par exemple, la == d_state « on » correspond à plusieurs états : Ontario (au Canada), Ondo (au Nigeria), Oshana (en Namibie). Nous vous recommandons de coupler ce signal avec d_country par exemple pour un géociblage plus spécifique. |
| d_region | Identifiants alphanumériques régionaux. Téléchargez la [liste des régions](assets/Country_RegionCodes_City.csv).  Vous pouvez ensuite utiliser cette liste pour faire correspondre les identifiants de région aux noms de région. |
| d_isp | FAI/organisation. Téléchargez la [liste des FAI](assets/d_isp.txt). |

La liste [tous les signaux géolocalisés](assets/all.txt) comprend tous les signaux ci-dessus, dans l&#39;ordre suivant: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Exigences de préfixe pour les variables clés](../../features/traits/trait-variable-prefixes.md)

