# Introducción a Shell-script en Linux

La estructura básica de un script en Linux es la siguiente

```bash
#!/bin/bash
# Este es nuestro primer programa
echo "Hello world"
```
A la expresión ```**#!/bin/bash``** se le conoce como el **Shebang**
La segunda línea es un **comentario**, los comentarios en Shell Script comienzan con **#**

> El espacio en blanco después de la # no es obligatorio, pero va a mejorar el comentario de la legibilidad.

En la tercera línea tenemos el comando ```echo``` que sirve para imprimir texto en la pantalla.

Los scripts se guardan con la etension **.sh**

# Edición de archivos de texto en Linux

## nano
En los sistemas Linux existen varios editores de texto de linea de comandos, uno de ellos es **nano**

Para editar un archivo en nano:

```nano nombre_archivo```

En la parte inferior de la ventana, se encuentra una lista de los atajos de comandos más básicos para usar con el editor Nano.

<img width="581" alt="image" src="https://github.com/alexlopezprofe/SOM/assets/148449360/71d9e6ce-4e2c-44da-a5ae-1ed0166bddcf">


### Hotkey Notation

* `^` = `Control`
* `M-` = `Alt` ("Meta" key)


### Save As...

```
^O
```

### Quit

```
^X
```

### Undo/Redo

```
M-U

M-E
```

### Cancel Nano Command

```
^C
```

### Next Search Result

```
^W
```

### Find and Replace

```
^\
A
```

### Regular Expressions

```
^W
M-R

^\
M-R
```

### Cut

```
^K
```

### Copy

```
M-6
```

### Paste

```
^U
```

### Set mark

```
M-A
```

### Indent/Dedent Line or Marked Block Rigidly

```
M-}

M-{
```

### Auto-Indent Current Line or Marked Region

```
TAB
```

### Start/End of File

```
M-\

M-/
```

### Start/End of Line

```
^A

^E
```

### Delete

```
DEL
```

### Edición de archivos en Linux

Ahora que tienes el fichero creado, si intentas ejecutarlo verás que no podrás. Esto es debido a que cualquier fichero nuevo que se crea y se ubica en el directorio personal de usuario, tiene el siguiente esquema de permisos:



## Visual Studio Code

Otra posibilidad es instalar el editor en entorno gráfico **Visual Studio Code** Se puede descargar desde: https://code.visualstudio.com/download.

Las instrucciones de la instalación se Visual Studio Code en Ubuntu pueden ver en: https://ubunlog.com/visual-studio-code-editor-codigo-abierto-ubuntu-20-04/

# Ejecución de scripts en Linux

# Bibliografía

* https://bioinf.comav.upv.es/courses/unix/scripts_bash.html
