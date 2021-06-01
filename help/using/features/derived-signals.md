---
description: Un signal dérivé qualifie les visiteurs du site pour des caractéristiques supplémentaires en fonction d’une caractéristique qu’ils ont déjà vue. En d’autres termes, une qualification de caractéristique supplémentaire peut être dérivée d’une caractéristique actuellement exposée, même si un utilisateur n’a jamais vu la nouvelle caractéristique auparavant.
seo-description: Un signal dérivé qualifie les visiteurs du site pour des caractéristiques supplémentaires en fonction d’une caractéristique qu’ils ont déjà vue. En d’autres termes, une qualification de caractéristique supplémentaire peut être dérivée d’une caractéristique actuellement exposée, même si un utilisateur n’a jamais vu la nouvelle caractéristique auparavant.
seo-title: Signaux dérivés
solution: Audience Manager
title: Signaux dérivés
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: 'Caractéristiques '
exl-id: 64bc004a-a31a-49bb-aa58-323fbc92f76f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 2%

---

# Signaux dérivés {#derived-signals}

Un [!UICONTROL derived signal] qualifie les visiteurs du site pour des caractéristiques supplémentaires en fonction d’une caractéristique qu’ils ont déjà vue. En d’autres termes, une qualification de caractéristique supplémentaire peut être dérivée d’une caractéristique actuellement exposée, même si un utilisateur n’a jamais vu la nouvelle caractéristique auparavant.

<!-- c_tb_derived_signal.xml -->

## Objectif des signaux dérivés

Dans [!DNL Audience Manager], vous pouvez créer une relation entre les signaux (ou les règles de caractéristiques) transmis lors d’un appel d’événement à d’autres signaux ou caractéristiques spécifiés. Supposons, par exemple, qu’un appel d’événement transfère un signal composé de la valeur-clé [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`). [!DNL Audience Manager] connecte ce signal à tout autre signal créé avec l’ [!UICONTROL derived signals] outil. Bien que les signaux associés puissent être des valeurs-clés que vous spécifiez, ils sont plus utiles lorsqu’ils sont liés à des signaux existants déjà configurés en tant que règles [!UICONTROL Trait Builder]. Par exemple, dans l’illustration ci-dessous, lorsqu’une action de l’utilisateur déclenche le signal [!DNL "product = new car"] , cet utilisateur peut également être admissible pour les caractéristiques définies par les signaux de clé et de valeur cible.

![](assets/derived_signal_example.png)

## Emplacement des signaux dérivés

Créez et gérez [!UICONTROL derived signals] dans **[!UICONTROL Tools > Derived Signals]** à partir de la navigation de la barre latérale.

## Création d’un signal dérivé {#create}

<!-- t_tb_create_derived.xml -->

Pour créer un [!UICONTROL derived signal] :

1. Sélectionnez **[!UICONTROL Derived Signals]** dans le menu [!UICONTROL Tools].
1. Fournissez un :
   * *(Facultatif)* [!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. Cliquez sur **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>La limite de caractères pour les champs [!UICONTROL Source Key], [!UICONTROL Source Value], [!UICONTROL Target Key] et [!UICONTROL Target Value] est de 228 caractères.

## Modification d’un signal dérivé {#edit}

<!-- t_tb_edit_derived.xml -->

Pour modifier un [!UICONTROL derived signal] :

1. Pointez sur le signal, puis cliquez sur **[!UICONTROL Edit]**.
2. Effectuez les modifications requises de code, clé ou valeur, puis cliquez sur **[!UICONTROL Save]**.

## Suppression d’un signal dérivé {#delete}

<!-- t_tb_delete_derived.xml -->

Pour supprimer une balise [!UICONTROL derived signal], passez la souris sur le signal, puis cliquez sur **[!UICONTROL Delete]**.
