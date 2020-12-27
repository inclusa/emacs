---
layout: post # Sustituye el layout si lo usas uno diferente
title: 68 Tracking time # Nombre generado automáticamente
---

### Introducción

**Tracking time** o seguimiento del tiempo es una herramienta realmente útil para realizar análisis de efectividad en el trabajo.

### Tracking time con OrgMode

Para realizar un seguimiento del tiempo mediante OrgMode deberemos activar el reloj `C-c C-x C-i`.

En el momento en que realizamos esta acción tendremos el siguinete texto en el documento:

```OrgMode
:LOGBOOK:
CLOCK: [2020-12-27 Sun 09:00]
:END:
```

Cuando desactivemos el reloj con el comando `C-c C-x C-o` obtendremos lo siguiente:


```OrgMode
:LOGBOOK:
CLOCK: [2020-12-27 Sun 09:00]--[2020-12-27 Sun 09:05] => 0:05
:END:
```
### Comandos importantes

Key          | Calls                | Action
-------------|----------------------|---------------------------------------
C-c C-x C-i  | org-clock-in 	    | Activa el reloj
C-c C-x C-x  | org-clock-in-last    | Activa el reloj desde la última parada
C-c C-x C-o  | org-clock-out 	    | Para el reloj
C-c C-x C-j  | org-clock-goto 	    | Salta hasta la línia donde paramos el reloj
C-c C-x C-q  | org-clock-cancel     | Cancela la cuenta del reloj
C-c C-x C-d  | org-clock-display    | Muestra el tiempo dedicado en las cabeceras
C-c C-x C-r  | org-clock-report     | Genera un informe de la actividad del reloj
C-c C-x C-z  | org-resolve-clocks   | Resolve any half-open clocks

### Genera un informe de los registros de tiempo

Podemos generar el informare así: `C-c C-x C-r`. De esta forma nos generará un nuevo informe/tabla, aunque lo podremos generar manualment así `C-c C-c`.

```OrgMode
#+BEGIN: clocktable
#+END:
```

Ahora escribiremos las ociones en la línea `BEGIN`:

```OrgMode
#+BEGIN: clocktable :maxlevel 4 :scope agenda :block thismonth
#+END:
```
Las opciones del informe del reloj son las siguentes:

Option          | Description
----------------|----------------------------------------------------------------------
:maxlevel       | Máximo nivel de profundidad de las tiempos listados en la tabla
:scope          | Vista considerara en el informe
:block          | Bloque de tiempo a considerar
:tstart         | Bloque desde que empieza a considerarlo el reloj
:tend           | Cuando se considera que el tiempo habría acabado
:wstart         | Empieza un dia específico de la semana, 1 significa Monday
:mstart         | Empieza un día específico del mes, 1 significa el primer dia del mes
:tags           | Solo incluye tiempo que coincidadn con estas tareas

Más explicaciones en [OrgMode.org - The clock table](https://orgmode.org/manual/The-clock-table.html)

Fuente: [writequit.org](https://writequit.org/denver-emacs/presentations/2017-04-11-time-clocking-with-org.html#tracking-time-with-org)

