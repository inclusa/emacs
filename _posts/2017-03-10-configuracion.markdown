---
layout: post
title: 10 Configuración
date:  2017-03-10 00:00:00
---

Recordamos comandos esenciales

- Buscar archivo C-x f
- Deshacer C-x u
- Guardar C-x w
- Cambio de buffer C-x b
- Cerrar sessión C-x C-c
- Guardar C-x C-s

Vamos a mejorar la configuracion para evitar los mensajes de inicio. Abriremos el archivo `.emacs` y copiaremos:

```
;;; Sin mensaje de bienvenida:
(setq inhibit-startup-message t)
;
;;; No mostrar la barra del menú:
(menu-bar-mode -1)
;
;;; Reemplazar "yes" y "no" por "y" y "n"
(fset 'yes-or-no-p 'y-or-n-p)
;
;;; Mover a la papelera al borrar archivos y directorios:
(setq delete-by-moving-to-trash t
trash-directory "~/.local/share/Trash/files")
;
;;; guardar la sessión al cerrar emacs y restaurarla
;;; al arrancar-la de nuevo. Cero (0) para desactivar:
(desktop-save-mode 1)
;
;;; Para que se muestren todos los buffers abiertos al pulsar C-x b (ido):
(ido-mode 1)
;;; Ignorar determinados buffers.
(setq ido-ignore-buffers '("^ " "*Completions*" "*Shell Command Output*"
                           "*Messages*" "Async Shell Command" "*scratch*"
                           "*tramp*"))
```

