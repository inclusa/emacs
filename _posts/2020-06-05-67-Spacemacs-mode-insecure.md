---
layout: post # Sustituye el layout si lo usas uno diferente
title: 67 Spacemacs mode insecure # Nombre generado automáticamente
---

Me encontré en la situación de que habían 7 paquestes que no se podian descargar porque, tal vez, no estaban actualizacos des del repositorio MELPA.

La situación se solucionó arrancando en modo insiguro la primera vez, de esta forma se actualizaon los paquestes necesarios. En adelante arrancamos Spacemacs como lo venimos haciendo y no hubo más problema.

```bash
emacs --insecure
```
