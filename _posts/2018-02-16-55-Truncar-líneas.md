---
layout: post #
title: 55 Truncar líneas # Generat automàticament
date: 2018-02-16 # Data
description:  # Argument
keywords: hook truncar líneas # Paraules clau
coments:  # Comentaris
---

Para establecer un `hook`, que no es otra cosa que realizar algo en cierta situación determinada, deberemos configurar el archivo `.emacs` de nuestro `home` estableciendo el código que realice esta función.

En esta ocasión nuestro objetivo es que nos trunque las línias largas para poder leerlas en la siguiente línea y, así, tener que desplazarnos hacia la derecha.

Para ello editamos `.emacs` y añadiremos este código:

```emacs
(defun my-compilation-mode-hook ()
  (setq truncate-lines nil) ;; automatically becomes buffer local
    (set (make-local-variable 'truncate-partial-width-windows) nil))
    (add-hook 'compilation-mode-hook 'my-compilation-mode-hook)')')))
```
