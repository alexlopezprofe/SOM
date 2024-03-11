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


# Variables en Shell Script

En programación, una **variable** es un espacio de almacenamiento con un nombre simbólico (identificador) que se utiliza para contener y representar un valor o información modificable durante la ejecución de un programa. 

Cada variable tiene un tipo de datos que define la naturaleza del valor que puede almacenar, como enteros, flotantes, cadenas de texto, entre otros. La capacidad de cambiar el valor de una variable a lo largo del programa proporciona flexibilidad y permite la adaptación del software a diferentes situaciones y condiciones.

Las variables se asignan con "=" sin espacios entre el nombre de la variable.

## Ejemplos de variables

```bash
MI_VARIABLE="tiene un valor"
la_2da_variable="tiene otro valor"
mi_variable="es distinta a MI_VARIABLE"
numerica=8
numerica="me arrepenti, ahora es un string"
array=(1 2 3 4)
```
> `variable.sh`

![image](https://github.com/alexlopezprofe/SOM/assets/148449360/d333d395-33e2-49e4-9c67-1c360c969934)

```bash
#!/bin/bash
# Variable.sh

Variable1="Alex"
Edad=18

echo "El profesor" $Variable1 "No tiene" $Edad "años" 
```

Salida:

![image](https://github.com/alexlopezprofe/SOM/assets/148449360/f980ec14-2143-4d7a-9767-3854bce65feb)

```bash
root@alexlopez-virtual-machine:/home/test# sh ./variable.sh 
El profesor Alex No tiene 18 años
```

# Parámetros
Los scripts pueden recibir parámetros al momento de ejecutarlos. Para acceder a estos parámetros, existe un conjunto de variables especiales:

```bash
$0 es el nombre del script tal como se lo invocó
$1 a $9 son los parámetros en el orden que se los recibió, del primero al noveno
$* son todos los parámetros que recibió el script
$# es la cantidad de parámetros que recibió el script
```

```bash
echo "Este script fue invocado como: $0"
echo "El primer parámetro recibido fue: $1"
echo "El segundo parámetro recibido fue: $2"
echo "El tercer parámetro recibido fue: $3"
echo "El cuarto parámetro recibido fue: $4"
echo "El quinto parámetro recibido fue: $5"
echo "El sexto parámetro recibido fue: $6"
echo "El séptimo parámetro recibido fue: $7"
echo "El octavo parámetro recibido fue: $8"
echo "El noveno parámetro recibido fue: $9"
echo "Todos los parámetros recibidos fueron: $*"
echo "El script recibió $# parámetros"
```
> parametros.sh

```
#! /bin/bash
#parametros.sh. Le pasamos dos parametros e imprime el que esta en la posicion 1 y 2
echo "Hola" $1;
echo "Hola" $2;
echo "Nombre del fichero:" $0;
echo "Numero de parametros": $#;
echo "Todos los parametros menos el 0": $*;
```
En la ejecución del script 'parametros.sh' le pasamos el parámetro `$1=Juan` y el `$2=Luis`
![image](https://github.com/alexlopezprofe/SOM/assets/148449360/2b106d1d-be4b-4207-a665-e22c6b20c1e8)

# Lectura de datos del teclado (uso de instruccion read)

A veces es necesario pasar valores por teclado y asignarlos a una variable. Un ejemplo donde se suele hacer es en los scripts que contienen puntos de menú. Para almacenar una entrada por teclado se usa el comando `read`.

```bash
#!/bin/bash
#Ejemplo #2: Script que muestra como asignar valores a variables en forma interactiva por el usuario, uso de la funcion read.
#pedir el dato al usuario
echo 'Introduzca un  valor para la variable var1:'
#leer el dato del teclado y guardarlo en la variable de usuario var1
read var1
#Mostrar el valor de la variable de usuario
echo $var1
```


# Bibliografía

* https://bioinf.comav.upv.es/courses/unix/scripts_bash.html
* https://github.com/victorhtorres/Terminal-y-linea-de-comandos
