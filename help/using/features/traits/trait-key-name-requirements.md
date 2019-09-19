---
description: Cet article décrit les conventions d’affectation de nom utilisées par la variable clé dans une paire clé-valeur.
seo-description: Cet article décrit les conventions d’affectation de nom utilisées par la variable clé dans une paire clé-valeur.
seo-title: Exigences de nom pour les variables clés
solution: Audience Manager
title: Exigences de nom pour les variables clés
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
translation-type: tm+mt
source-git-commit: bdbc2525a13eb04898b0a844ba478cde07e83252

---


# Exigences de nom pour les variables clés {#name-requirements-for-key-variables}

Cet article décrit les conventions d’affectation de nom utilisées par la variable clé dans une paire clé-valeur.

## Exigences de nommage des clés

<!-- c_tb_key_name_requirements.xml -->

Dans [!UICONTROL Expression Builder]ce cas, le nom d’une variable clé dans une paire clé-valeur peut être composé de n’importe quel nombre de chiffres suivi de 1 (ou plus) lettre, d’un tiret, d’un trait de soulignement et de chiffres supplémentaires.

* Noms de clés valides : `price123`, `123price`, `price-123`, `c_price123`.

* Noms de clés non valides : `123`, `price!123`.

## Préfixe des variables clés avec `c_`

Le `c_` préfixe est *toujours* requis si les paramètres qui envoient des données sur une URL d’appel d’événement utilisent cette syntaxe.