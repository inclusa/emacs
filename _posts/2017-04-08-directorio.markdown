---
layout: post
title: 23 Directorio
date: 2017-04-08 00:00:00 
description: Configurar directorio por defecto
---

Para configurar el *directorio por defecto* y que, así nos apunte rápidamente al directorio donde trabajajos editaremos el archivo `.emacs` e insertaremos este código:

```emacs
(setq default-directory "~Documents/BulletJournal/")

```

De esta forma, cada vez que abramos un archivo con `C-x f` ya estaremos en el directorio `~Documents/BulletJournal/`
