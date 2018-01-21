---
layout: post # 
title: 54 Activar imagenes en línea # Generat automàticament
date: 2018-01-21 # Data
description: Activar imágenes  # Argument
keywords: images # Paraules clau
coments: Activar imágenes en línea # Comentaris
---

Para activar las imágenes en línea deberemos incluir en la cabecera del documento:

```emacs
#+STARTUP: inlineimages
```

De esta forma, al incluir una imagen así:

```emacs
[[./image/emacs.png]]
```

Obtendremos la imagen incrustada en el documento.

Por otra parte, podemos activar la imagen, en caso de no poner cabeceras, con esta combinación de teclas:

```emacs
C-c C-x C-v
```
