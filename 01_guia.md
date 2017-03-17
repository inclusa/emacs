#Emacs


#emacs | 00 Inicio de bitácora
#dia_00

`Meta`: Dominar Emacs nivel inicial en 30 dias.

Nomenclatura:

`C` - Control
`M` - Meta, tecla Alt izquierda o ESC
`S` - Shift o mayúscula

- [Referència](http://www.merlos.org/linux/2003/05/emacs.html)

1. Arrancar Emacs sense entorn de finestres

emacs --no-window-system

2. Gestió de finestres

C-x 1	>> Ver una sóla ventana.
C-x 2   >> Divide la ventana actual en dos filas
C-x 3   >> Divide la ventana actual en dos columnas
C-x 0   >> (cero) Elimina la ventana actual.
C-x b   >> Cambiar el buffer de la venana actual. En minibuffer aparece prompt
C-x o   >> Cambiar de ventana cuando el aréa de trabajo está dividida en 
           varias ventanas


#emacs | 01 Arrancando
#dia_01

1. Arrancar Emacs modo gráfico

`emacs`

2. Arrancar Emacs modo terminal

`emacs --no-window-system`

3. Suspender ejecución Emacs

`C-z`

4. Detiene Emacs y pregunta si guarda el fichero

`C-x C-c`

#emacs | 02 Zonas
#dia_02

1. `Barra de menú`: situada arriba

2. `Point` o punto de escritura en una `ventana de edición` o ventanas si decidimos partirlas: situada en la parte central.

3. `Línea de modo`: situada abajo, en video inverso. Muestra información variada

4. `Área de eco` y `minibuffer`: ambos aparecen en la última línea

- `Área de eco`: aparece sólo al escribir una combinación de teclas. Lo escrito hace eco o tiene su salida en la pantalla.

-- `Minibúffer`: sirve para escribir argumentos que se hayan de pasar a un comando

#emacs | 03 Edición en ventanas
#dia_03

1. Borra ventana activa 

`C-x 0`

2. Borra todas las ventanas menos la activa

`C-x 1`

3. Divide horizontalmente la ventana activa en dos ventans

`C-x 2`

4. Lleva el cursos a la próxima ventana

`C-x o`

5. Desplaza hacia abajo el texto de la próxima ventana, como si hiciéramos AvPág

`C-M-v`

#emacs | 04 Ficheros y buffers
#dia_04

`Buffer`: zona de memoria en la que se encuentra el texto objeto de edición. Es volátil.

`Fichero`: conjunto de datos almacenados en el disco. Es inmodificable, aunque se puede borrar y crear otro fichero con distinto nombre y mismo contenido.

Cuando leemos un fichero, lo que realmente hacermos es copiarlo en memoria RAM (buffer), durante su edición lo modificamos en esa zona de memoria. el fichero permanece inalterado hasta que demos la orden específica de grabar en el disco las modificaciones.

No todos los `buffers` corresponden a `ficheros`.

Cuando se inicia Emacs aparecen estos dos buffers:

- *scratch*
- *messages*

Obsérvese que van entre asteríscos, lo que indica no es un buffer asociado a un fichero.

1. Cerrar el búffer, no modifica el fichero si está guardado, no lo crea en caso de no estarlo.

`C-x k`

2. Incluir acentos: incluye esto `(set-keyboard-coding-system 'utf-8) ` en el fichero `.emacs`

#emacs | 05 Visitar (abrir) Ficheros
#dia_05

1. Abrir fichero

`C-c C-f`

2. Abrir directorio

`C-x d`

3. Grabar en disco

`C-x C-s`

4. Grabar el buffer con otro nombre

`C-x C-w`

5. En edición de buffers simuntáneos nos preguntará si se ha modificado y si queremos guardarlo

`C-x s`

6. Cerrar buffer, sin guardar, no modifica archivo creado

`C-x k`

#emacs | 06 Manejo de zonas
#dia_06

1. Cambia a otro buffer solicitando el nombre. Si se proporciona el nombre de un buffer no abierto, se crea uno con dicho nombre y se cambia a él.

`C-x b`

2. Selecciona otra ventana

`C-x o`

3. Borra la ventana seleccionada

`C-x 0`

4. Borra todas las ventanas excepto la seleccionada

`C-x  1`

5. Selecciona un buffer en una ventana nueva

`C-x 4 b`

6. Visita un fichero y sitúa un buffer en otra venta, que se convierte en la seleccionada

`C-x 4 f`

7. Borra la ventana seleccionada y cierra, mata el buffer que contenia

`C-x 4 0`

#emacs | 07 Ayuda
#dia_07

1. Crear una ventana con ayuda

`M-x o`

2. Llegar a la ventana nueva. Pulsar dos veces estos comandos

`C-x o`

3. Bajar hasta el comando elegido y pulsar enter

#emacs | 08 Buffer
#dia_08

Para entender el concepto debemos tener saber que el buffer se refiere a la memoria RAM.

Cuando abrimos un archivo en el disco (memoria ROM) ocupa un espacio en la memoria RAM.

El buffer se refiere al espacio concreto que ocupa este archivo en RAM.

Por ejemplo, cuando en Python (lenguaje de programación) asignamos una variable `s` a un valor `5`, así:

```
s = 5
```

El la variable `s` queda almacenada en la memoria RAM y cuando la llamamos `$s` nos devueve su valor, en este caso `5`.

Así el buffer se refiere al archivo cargado en ram.

Fíjate que en Emacs tenemos dos buffers que se cargan siempre:

*scratch*
*Messages*

Que esten cargados con asteriscos `*` indica que estan en RAM (buffer) pero no escritos en disco (ROM).

Así, si visitas `*Messages` observarás que tiene la función de `log` o bitácora donde se van acumulando los mensajes que te va dando Emacs.

Cuando sales, si no guardas los buffers en archivos específicos, se borran de la RAM liberándo el espacio, por lo que normalmente guardarmos en disco los archivos para volver a recuperarlos cuando iniciemos el sistema.

`.` Indica que se trabaja en ese buffer

`%` Indica sólo lectura

`*` Indica que ese buffer está modificado

https://www.gnu.org/software/emacs/manual/html_node/emacs/List-Buffers.html

