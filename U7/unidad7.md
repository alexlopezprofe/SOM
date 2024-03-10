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

```sudo nano nombre_archivo```

```sudo nano Hello_World.sh```

![image](https://github.com/alexlopezprofe/SOM/assets/148449360/31639694-bee9-4b19-ba7b-b63a340b557e)

+ Para guardar los cambios `Control` + `o` y pulsamos `Enter` 

![image](https://github.com/alexlopezprofe/SOM/assets/148449360/2b5dd9a1-6bbe-4ff8-a888-8e987e579a12)

+ Para salir `Control` + `x`

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

## gedit

Gedit es un editor de texto inluido por defecto en Ubuntu (y en otras distribuciones de LInux)

```gedit Hello_World.sh```

## Visual Studio Code

Otra posibilidad es instalar el editor en entorno gráfico **Visual Studio Code** Se puede descargar desde: https://code.visualstudio.com/download.

Las instrucciones de la instalación se Visual Studio Code en Ubuntu pueden ver en: https://ubunlog.com/visual-studio-code-editor-codigo-abierto-ubuntu-20-04/

# Ejecución de scripts en Linux

## Permisos de ejecución
Para ejecutar un script, primero tenemos que estar seguros que tenga permisos de ejecución.

Recuerda que para dar todos los permisos a un archivo: ```chmod 777 Hello_World.sh```

## Ejecución de un script

```sudo sh ./Hello_World.sh```

![image](https://github.com/alexlopezprofe/SOM/assets/148449360/9b50a031-5626-47c2-a6dd-bc195b953e82)

Si estamos como root

```sh ./Hello_World.sh``` 

![image](https://github.com/alexlopezprofe/SOM/assets/148449360/e641cf02-36f8-487f-a4ea-916d91266680)


# Bibliografía

* https://bioinf.comav.upv.es/courses/unix/scripts_bash.html
