---
description: Un signal dérivé qualifie les visiteurs du site pour des caractéristiques supplémentaires en fonction d'une caractéristique qu'ils ont déjà vue. En d’autres termes, une qualification de caractéristique supplémentaire peut être dérivée d’une caractéristique actuellement exposée, même si un utilisateur n’a jamais vu la nouvelle caractéristique auparavant.
seo-description: Un signal dérivé qualifie les visiteurs du site pour des caractéristiques supplémentaires en fonction d'une caractéristique qu'ils ont déjà vue. En d’autres termes, une qualification de caractéristique supplémentaire peut être dérivée d’une caractéristique actuellement exposée, même si un utilisateur n’a jamais vu la nouvelle caractéristique auparavant.
seo-title: Signaux dérivés
solution: Audience Manager
title: Signaux dérivés
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 0%

---


# Signaux dérivés {#derived-signals}

Un site [!UICONTROL derived signal] qualifie les visiteurs pour des caractéristiques supplémentaires en fonction d’une caractéristique qu’ils ont déjà vue. En d’autres termes, une qualification de caractéristique supplémentaire peut être dérivée d’une caractéristique actuellement exposée, même si un utilisateur n’a jamais vu la nouvelle caractéristique auparavant.

<!-- c_tb_derived_signal.xml -->

## Objet des signaux dérivés

Dans [!DNL Audience Manager], vous pouvez créer une relation entre les signaux (ou les règles de caractéristiques) transmis au cours d’un appel de événement à d’autres signaux ou caractéristiques spécifiés. Supposons, par exemple, qu’un appel de événement soit transmis dans un signal composé de la valeur-clé [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`). [!DNL Audience Manager] connecterait ce signal à tout autre signal créé avec l&#39; [!UICONTROL derived signals] outil. Bien que les signaux associés puissent être des valeurs clés que vous spécifiez, ils sont plus utiles lorsqu&#39;ils sont liés à des signaux existants déjà configurés en tant que [!UICONTROL Trait Builder] règles. Par exemple, dans l’illustration ci-dessous, lorsqu’une action de l’utilisateur déclenche le signal [!DNL "product = new car"] selon lequel l’utilisateur peut également être admissible pour les caractéristiques définies par la clé de cible et les signaux de valeur.

![](assets/derived_signal_example.png)

## Emplacement des signaux dérivés

Créez et gérez dans [!UICONTROL derived signals]**[!UICONTROL Tools > Derived Signals]** à partir de la barre de navigation latérale.

## Créer un signal dérivé {#create}

<!-- t_tb_create_derived.xml -->

Pour créer un [!UICONTROL derived signal]:

1. Sélectionnez **[!UICONTROL Derived Signals]** dans le [!UICONTROL Tools] menu.
1. Fournissez un :
   * *(Facultatif)* [!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. Cliquez sur **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>La limite de caractères pour les [!UICONTROL Source Key], [!UICONTROL Source Value], [!UICONTROL Target Key]et [!UICONTROL Target Value] champs est de 228 caractères.

## Modifier un signal dérivé {#edit}

<!-- t_tb_edit_derived.xml -->

To edit a [!UICONTROL derived signal]:

1. Passez la souris sur le signal, puis cliquez sur **[!UICONTROL Edit]**.
2. Effectuez les modifications requises du code, de la clé ou de la valeur, puis cliquez sur **[!UICONTROL Save]**.

## Supprimer un signal dérivé {#delete}

<!-- t_tb_delete_derived.xml -->

Pour supprimer un [!UICONTROL derived signal]signal, passez la souris dessus, puis cliquez sur **[!UICONTROL Delete]**.
