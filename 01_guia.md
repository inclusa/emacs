# Emacs

Indice


[00 Inicio de bitácora](#00-inicio-de-bitácora)

[01 Arrancando](#01-arrancando)

[02 Zonas](#02-zonas)

[03 Edición en ventanas](#03-edición-en-ventanas)

[04 Ficheros y buffers](#04-ficheros-y-buffers)

[05 Visitar (abrir) Ficheros](#05-visitar-abrir-ficheros)

[06 Manejo de zonas](#06-manejo-de-zonas)

[07 Buffer](#07-buffer)

[08 Cifrado](#08-cifrado)

[09 Configuración](#9-Configuración)

[10 Gestión de ventanas](#10-Gestión-de-ventanas)


# 00 Inicio de bitácora
#dia_00

`Meta`: Dominar Emacs nivel inicial en 30 dias.

Nomenclatura:

`C` - Control

`M` - Meta, tecla Alt izquierda o ESC

`S` - Shift o mayúscula

- [Referència](http://www.merlos.org/linux/2003/05/emacs.html)



# 01 Arrancando
#dia_01

1. Arrancar Emacs modo gráfico

	emacs

2. Arrancar Emacs modo terminal

	emacs --no-window-system

3. Suspender ejecución Emacs

	C-z

4. Detiene Emacs y pregunta si guarda el fichero

	C-x C-c

# 02 Zonas
#dia_02

1. `Barra de menú`: situada arriba

2. `Point` o punto de escritura en una `ventana de edición` o ventanas si decidimos partirlas: situada en la parte central.

3. `Línea de modo`: situada abajo, en video inverso. Muestra información variada

4. `Área de eco` y `minibuffer`: ambos aparecen en la última línea

- `Área de eco`: aparece sólo al escribir una combinación de teclas. Lo escrito hace eco o tiene su salida en la pantalla.
- `Minibúffer`: sirve para escribir argumentos que se hayan de pasar a un comando

Para salir del minibuffer, zona donde escribimos comandos, debemos apretar C-g, ya que de lo contrario, se encadenaran los comandos.

# 03 Edición en ventanas
#dia_04

Aclaraciones

`C-x C-c` - Pulsas `Control` y con la tecla de `Control` pulsada pulsas primero `x` y después `c`.

`C-x k` - Pulsas `Control` y `x`. Levantas el dedo de la tecla `Control` y pulsas `k`.


Limpiar minibuffer

`C-g` - Este comando limpia el minibuffer para no encadenar comandos. Una vez limpio ya podemos introducir la secuencia.



1. Borra ventana activa 

	C-x 0

2. Borra todas las ventanas menos la activa

	C-x 1

3. Divide horizontalmente la ventana activa en dos ventans

	C-x 2

4. Lleva el cursos a la próxima ventana

	C-x o

5. Desplaza hacia abajo el texto de la próxima ventana, como si hiciéramos AvPág

	C-M-v

# 04 Ficheros y buffers
#dia_04

`Buffer`: zona de memoria en la que se encuentra el texto objeto de edición. Es volátil.

`Fichero`: conjunto de datos almacenados en el disco. Es inmodificable, aunque se puede borrar y crear otro fichero con distinto nombre y mismo contenido.

Cuando leemos un fichero, lo que realmente hacermos es copiarlo en memoria RAM (buffer), durante su edición lo modificamos en esa zona de memoria. el fichero permanece inalterado hasta que demos la orden específica de grabar en el disco las modificaciones.

No todos los `buffers` corresponden a `ficheros`.

Cuando se inicia Emacs aparecen estos dos buffers:

- `*scratch*`
- `*messages*`

Obsérvese que van entre asteríscos, lo que indica no es un buffer asociado a un fichero.

1. Cerrar el búffer, no modifica el fichero si está guardado, no lo crea en caso de no estarlo.

	C-x k

2. Incluir acentos: incluye esto `(set-keyboard-coding-system 'utf-8) ` en el fichero `.emacs`

# 05 Visitar (abrir) Ficheros
#dia_05

1. Abrir fichero

	C-c C-f

2. Abrir directorio

	C-x d

3. Grabar en disco

	C-x C-s

4. Grabar el buffer con otro nombre

	C-x C-w

5. En edición de buffers simuntáneos nos preguntará si se ha modificado y si queremos guardarlo

	C-x s

6. Cerrar buffer, sin guardar, no modifica archivo creado

	C-x k

# 06 Manejo de zonas
#dia_06

1. Cambia a otro buffer solicitando el nombre. Si se proporciona el nombre de un buffer no abierto, se crea uno con dicho nombre y se cambia a él.

	C-x b

2. Selecciona otra ventana

	C-x o

3. Borra la ventana seleccionada

	C-x 0

4. Borra todas las ventanas excepto la seleccionada

	C-x  1

5. Selecciona un buffer en una ventana nueva

	C-x 4 b

6. Visita un fichero y sitúa un buffer en otra venta, que se convierte en la seleccionada

	C-x 4 f

7. Borra la ventana seleccionada y cierra, mata el buffer que contenia

	C-x 4 0


# 07 Buffer
#dia_07

Para entender el concepto de `buffer` debemos tener en cuenta que el `buffer` se refiere a la memoria RAM.

Cuando abrimos un archivo en el disco (memoria ROM) ocupa un espacio específico, mapeado, en la memoria RAM.

El `buffer` se refiere al espacio concreto que ocupa este archivo en RAM.

Por ejemplo, cuando en Python (lenguaje de programación) asignamos una variable `s` a un valor `5`, así:

```
s = 5
```

El la variable `s` queda almacenada en un espacio concreto de la memoria RAM y cuando la llamamos `$s` nos devueve su valor, en este caso `5`.

Así el buffer se refiere al archivo cargado en RAM, que desaparecerá cuando apaguemos el ordenador o salgamos del programa.

Fijemonos en el menú Buffers de Emacs. Encontramos tres buffers que se cargan siempre:

*GNU Emacs* %
*scratch*
*Messages* %

Que esten cargados con asteriscos `*` indica que estan en RAM (buffer) pero no escritos en disco (ROM).

Así, si visitas `*Messages` observarás que tiene la función de `log` o bitácora donde se van acumulando los mensajes que te va dando Emacs.

Cuando sales, si no guardas los buffers en archivos específicos, se borran de la RAM liberándo el espacio, por lo que normalmente, guardarmos en disco los archivos para volver a recuperarlos cuando iniciemos el sistema.

`.` Indica que se trabaja en ese buffer

`%` Indica sólo lectura

`*` Indica que ese buffer está modificado (este símbolo sale cuando listamos los buffers no en el menú, que significa que está en RAM)

https://www.gnu.org/software/emacs/manual/html_node/emacs/List-Buffers.html


# 08 Cifrado
#dia_08

Emacs utiliza por defecto el cifrado de GPG.

De esta manera para podemos cifrar y descrifrar documentos tanto para `claves simétricas`, una clave como para `claves asimétricas`, dos claves: pública y privada).

Empecemos por lo sencillo: `cifrado simétrico`.

Si creamos un documento llamado `a.txt`, lo guardamos.

Ahora lo podremos cifrar desde el menú:

```
Tools > Encryption/Decryption > Encrypt file...
```

Lo que hace, por detrás es esto, pero no lo vemos:

```
gpg -c a.txt
```

Para desdifrar lo que hace es, pero no lo vemos:

```
gpg -d a.txt.gpg
```

Genera un archivo nuevo `a.txt.gpg`, antes nos pide dos veces que le pongamos una contraseña.

El resultado son dos archivos:

`a.txt` Sin cifrar

`a.txt.gpg` Cifrado

Subiríamos a la nube el segundo.

Al recuperarlo deberíamos nos pedirá la clave de cifrado.

Al guardarlo, nos volverá a pedir la clave de cifrado dos veces.

Con este procedimineto siempre mantendremos cifrado nuestro archivo, el cual tendrá una primera capa de seguridad, ya no será tan accesible.


# 09 Configuración
#dia_09

Recordamos comandos esenciales

Buscar archivo C-x f
Deshacer C-x u
Guardar C-x w
Cambio de buffer C-x b
Cerrar sessión C-x C-c
Guardar C-x C-s

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


# 10 Gestión de ventanas
#dia_10

	C-x 1 - Ver una sola ventana.
	
	C-x 2 - Divide la ventana actual en dos filas
	
	C-x 3 - Divide la ventana actual en dos columnas
	
	C-x 0 - (cero) Elimina la ventana actual.
	
	C-x b - Cambiar el buffer de la venana actual. En minibuffer aparece prompt
	
	C-x o - Cambiar de ventana cuando el aréa de trabajo está dividida en varias ventanas

