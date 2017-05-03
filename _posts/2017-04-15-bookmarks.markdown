---
layout: post
title: 24 Bookmarks
date: ds 15 abr 2017 07:02:06 CEST 
tags:
- bookmarks
description: Gestión de favoritos
---

Abrimos un archivo de bookmarks o favoritos


1. Abrimos el gestor de bookmarks o favoritos `M-x bookmark-bmenu-list` (**bookmark-list**).
2. Abrimos el fichero que queremos que se a un bookmark `Ctrl+x r m` y pondremos su nombre (**bookmark-bmenu-set**).
3. Listamos el archivo **bookmark-bmenu-list** `Ctrl+x r l`
4. Abrimos el archivo **bookmark-jump** `Ctrl+x r b`.
5. Borramos o Renombramos el bookmark
- Escribimos `d` para borrar item.
- Escribimos `x` para borrar marcadores.
- Escribimos `r` para borrar el título del ítem.
- Escribimos `s` para guardar los cambios.
6. Guardar el archivo bookmark. Llamamos **bookmark-save** o presionamos `s`.

Podemos configurar el archivo `.emacs` para que se vaya guardando automáticamente.

```emacs
(setq bookmark-save-flag 1) ; para que cada vez que cambie, se guarde

(setq bookmark-save-flag t) ; para que se guarde cuando salga

(setq bookmark-save-flag nil) ; para que nunca se autogruarde
```

Podremos configurar las teclas rápidas llamando a **describe-mode** `Ctrl + h m`.

Para iniciar el archivo al arrancar Emacs:

```emacs
(setq inhibit-splash-screen t)
(require 'bookmark)
(bookmark-bmenu-list)
(switch-to-buffer "*Bookmark List*")
```

Guardaremos el archivo en `~/.emacs.d/bookmarks`

Por defecto el camino del archivo bookmark está guardado en la variable `bookmark-default-file`. Llamaremos `describe-variable` `Ctrl+h v` para ver su valor.
