# Introducción a Shell-script en Linux

<!--<img align="right" src="https://picsum.photos/300/200" alt="image" />
Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five 
centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.-->

La estructura básica de un script en Linux es la siguiente

```bash
#!/bin/bash
# Este es nuestro primer programa
echo "Hello world"
```
* A la expresión ```**#!/bin/bash``** se le conoce como el **Shebang**
* La segunda línea es un **comentario**, los comentarios en Shell Script comienzan con **#**
* El espacio en blanco después de la # no es obligatorio, pero va a mejorar el comentario de la legibilidad.
*  La tercera línea tenemos el comando ```echo``` que sirve para imprimir texto en la pantalla.
*  Los scripts se guardan con la etension **.sh**

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

Le damos permisos de ejecución: ```chmod +x task.sh```

Recuerda que para dar todos los permisos a un archivo: ```chmod 777 Hello_World.sh```. Recuerda que otorgar el permiso 777 no es recomendable en entornos en producción.

## Ejecución de un script

### sh
```sudo sh ./Hello_World.sh```

![image](https://github.com/alexlopezprofe/SOM/assets/148449360/9b50a031-5626-47c2-a6dd-bc195b953e82)
.::
Si estamos como root

```sh ./Hello_World.sh``` 

![image](https://github.com/alexlopezprofe/SOM/assets/148449360/e641cf02-36f8-487f-a4ea-916d91266680)

### bash

Bash es una ampliación de sh, es posible Por lo tanto algunas construcciones/funciones que funcionan en bash puede que no funcionen en sh mientras que todo lo que funciona en sh debería funcionar en bash.

```bash ./Hello_World.sh```

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
# Comparaciones numéricas y de cadenas
En esta sección, vamos a aprender algunos conceptos básicos de las comparaciones de shell de bash numérico y de cadena. Usando comparaciones, podemos comparar cadenas (palabras, oraciones) o números enteros sin procesar o como variables. La siguiente tabla enumera operadores de comparación rudimentarios para números y cadenas:

<table class="uk-table uk-table-striped uk-table-condensed"><caption><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Bash Shell Numérico y comparaciones de cadenas</font></font></caption> <thead> <tr> <th><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Descripción</font></font></th> <th><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Comparación numérica</font></font></th> <th><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Comparación de cadenas</font></font></th> </tr> </thead><tfoot> <tr> <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Ejemplo de comparación de shell: </font></font></td> <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">[100 -eq 50]; </font><font style="vertical-align: inherit;">echo $?</font></font></td> <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">["GNU" = "UNIX"]; </font><font style="vertical-align: inherit;">echo $?</font></font></td> </tr> </tfoot> <tbody> <tr> <td class="uk-text-primary uk-text-bold"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">menos que</font></font></td> <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">-lt</font></font></td> <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">&lt;</font></font></td> </tr> <tr> <td class="uk-text-primary uk-text-bold"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">mas grande que</font></font></td> <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">-gt</font></font></td> <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">&gt;</font></font></td> </tr> <tr> <td class="uk-text-primary uk-text-bold"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">igual</font></font></td> <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">-eq</font></font></td> <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">=</font></font></td> </tr> <tr> <td class="uk-text-primary uk-text-bold"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">no es igual</font></font></td> <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">-ne</font></font></td> <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">! =</font></font></td> </tr> <tr><td class="uk-text-primary uk-text-bold"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">menor o igual</font></font></td> <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">-le</font></font></td> <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">N / A</font></font></td> </tr>  <tr><td class="uk-text-primary uk-text-bold"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">mayor o igual</font></font></td> <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">-ge</font></font></td> <td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">N / A</font></font></td> </tr> </tbody> </table>

## Ejemplo de comparación numérica

```bash
#!/bin/bash

if [ "$a" -eq "$b" ]; then
	echo "\$a es IGUAL que \$b"
fi

if [ "$a" -ne "$b" ]; then
	echo "\$a NO ES IGUAL que \$b"
fi

if [ "$a" -gt "$b" ]; then
	echo "\$a es MAYOR que \$b"
fi

if [ "$a" -lt "$b" ]; then
	echo "\$a es MENOR que \$b"
fi

if [ "$a" -ge "$b" ]; then
	echo "\$a es MAYOR O IGUAL que \$b"
fi

if [ "$a" -le "$b" ]; then
	echo "\$a es MENOR O IGUAL que \$b"
fi
```

## Otro ejemplo de comparación numérica

```bash
#!bin/bash

echo "Ingresa tu edad: "
read AGE
if ["$AGE" -lt 20] || ["$AGE" -ge 50]; then
	echo "No esta en el rango 20-50.";
	elif ["$AGE" -ge 20 ] && ["$AGE" -lt 30]; then
		echo "Estas en los 20.";
	elif ["$AGE" -ge 30] && ["$AGE" -lt 40]; then
		echo "Estas en los 30.";
	elif ["$AGE" -ge 40] && ["$AGE" -lt 50]; then
		echo "Estas en los 40.";
fi

```


## Ejemplo de comparación de cadenas

```bash
#!/bin/bash

if [ "$a" = "$b" ]; then
	echo "\$a es IGUAL que \$b"
fi

if [ "$a" == "$b" ]; then
	echo "\$a es IGUAL que \$b"
fi

if [ "$a" != "$b" ]; then
	echo "\$a NO ES IGUAL que \$b"
fi

if [ "$a" \> "$b" ]; then
	echo "\$a es MAYOR que \$b"
fi

if [ "$a" \< "$b" ]; then
	echo "\$a es MENOR que \$b"
fi

if [ -z "$a" ]; then
	echo "\$a ES NULO"
fi

if [ -n "$a" ]; then
	echo "\$a NO ES NULO"
fi
```

# Operaciones Aritméticas 

## Operadores aritméticos

En Bash, los operadores aritméticos son símbolos que se utilizan para realizar operaciones matemáticas en expresiones numéricas. Algunos de los operadores aritméticos más comunes en Bash son:

1. **Suma (`+`)**: Se utiliza para sumar dos valores.
   
2. **Resta (`-`)**: Se utiliza para restar el segundo valor del primero.

3. **Multiplicación (`*`)**: Se utiliza para multiplicar dos valores.

4. **División (`/`)**: Se utiliza para dividir el primer valor por el segundo.

5. **Módulo (`%`)**: Devuelve el resto de la división entera del primer valor por el segundo.

6. **Incremento (`++`)**: Aumenta el valor de una variable en uno.

7. **Decremento (`--`)**: Reduce el valor de una variable en uno.

En shell script, puedes realizar operaciones aritméticas utilizando varias técnicas.

## Usando la Expresión `$(( ))`
La forma más común de realizar operaciones aritméticas en Bash es mediante la expresión `$(( ))`. Dentro de esta expresión, puedes colocar cualquier operación aritmética básica.

Por ejemplo:

```bash
resultado=$((5 + 3))
echo "El resultado es $resultado"
```


```bash
suma=$((10 + 5))
resta=$((20 - 8))
multiplicacion=$((4 * 6))
division=$((25 / 5))
modulo=$((10 % 3))

echo "Suma: $suma"
echo "Resta: $resta"
echo "Multiplicación: $multiplicacion"
echo "División: $division"
echo "Módulo: $modulo"
```

## Utilizando `expr`
Otra forma de realizar operaciones aritméticas es utilizando el comando `expr`.

Por ejemplo:

```bash
resultado=`expr 10 + 20`
echo "El resultado es $resultado"
```

## Utilizando `let`
También puedes usar el comando `let` para realizar operaciones aritméticas.

Por ejemplo:

```bash
let resultado=10+5
echo "El resultado es $resultado"
```

# Control de flujo

Los scripts se ejecutan línea a línea hasta llegar al final, sin embargo, muchas veces nos interesará modificar ese comportamiento de manera que el programa pueda responder de un modo u otro dependiendo de las cirscunstancias o pueda repetir trozos de código.

![alt text](image.png)

## Condicionales

Los condicionales en Bash se utilizan para ejecutar bloques de código basados en el resultado de una expresión condicional.

### Ejemplo de condicional "if-else":

Su forma más sencilla es:

```bash
if CONDICION; then
    comandos
fi 
```
Si la CONDICION es verdadera, ejecuta los comandos especificados, si es falsa, no hace nada.


A esto le podemos añadir que ejecute otras instrucción únicamente si la condición es falsa:
```bash
if CONDICION; then
  comandos
else
  otros comandos
fi
```

Y por último podemos encadenar distintas condiciones:
```bash
if CONDICION; then
  comandos
elif CONDICION; then
  otros comandos
else
  otros comandos distintos
fi
```

**Ejemplo**
```bash
# Definir una variable

edad=20

# Condicional if-else
if [ $edad -ge 18 ]; then
    echo "Eres mayor de edad."
else
    echo "Eres menor de edad."
fi
```

En el ejemplo anterior, se evalúa si la variable edad es mayor o igual a 18. Si es verdadero, se imprime "Eres mayor de edad."; de lo contrario, se imprime "Eres menor de edad.".

## Estructura CASE

La sentencia case ejecutará unas instrucciones u otras en función del valor que encuentre en una variable o expresión. Es útil cuando la cantidad de valores a considerar es elevada ya que es una estructura muy legible y fácil de interpretar. En esta ocasión valor NO es un únicamente verdadero o falso, sino que contiene un dato y en función de él ejecutaremos una líneas u otras.

```bash
case valor in
         exp1)
             ...
             ultimaorden1;;
         exp2)
             ...
             ultimaorden2;;
         expN)
             ...
            ultimaordenN;;
  esac
```
La ultima orden de cada bloque termina con doble punto y coma para indicar que termina el “CASE”

**Ejemplo**
```bash
case $1 in
         "rm")
             echo "has elegido el comando borrar";;
         "cp")
             echo "has elegido el comando copiar";;
         "ls")
             echo "has elegido el comando listar";;
esac
```

## Bucle for

```bash
for VARIABLE in SERIE; do
    bloque de comandos
done
```
**Ejemplos**

> [!NOTE]  
> Los tres siguientes ejemplos de bucle for son equivalentes. Itera sobre los números del 1 al 5 e imprime el mensaje "Iteración x" en cada iteración.


```bash
# Bucle for para iterar sobre una lista de elementos
for i in {1..5}; do
    echo "Iteración $i"
done
```

```bash
for i in 1 2 3 4 5; do
   echo "Iteración $i"
done
```
```bash
for i in $(seq 1 5); do
  echo "Iteración $i"
done

```

**Ejemplo con palabras**

```bash
for palabra in uno dos tres cuatro cinco; do
  echo $palabra
done
```

### Bucle for tipo C

De forma similar al bucle for usado en C generamos un bucle for que estará iterando hasta que la variable que inicialicemos ( en el ejemplo '$i') alcance un determinado valor i = 100. Es util si queremos realizar una accion un numero determinado de veces.

```
for ((inicializacion; condicion; incremento)); do
   bloque de sentencias
done
```
**Ejemplo**
```
for ((i = 0 ; i < 100 ; i++)); do
  echo $i
done
```

## Bucle while

```bash
while [ condición ]; do
[COMANDOS]
done
```
**Ejemplo**
```bash
# Bucle while para repetir una acción mientras se cumpla una condición
contador=0
while [ $contador -lt 5 ]; do
    echo "El contador es: $contador"
    ((contador++))
done
```
En este ejemplo, se ejecuta un bucle while que incrementa el contador en cada iteración y muestra su valor hasta que el contador sea menor que 5.

# Arrays Shell Script
Los arrays son una estructura de datos que nos permite almacenar múltiples valores en una sola variable. En shell script, los arrays pueden contener números, cadenas de texto u otros datos.

## Declaración de Arrays
Para declarar un array en shell script, utilizamos la siguiente sintaxis:

```bash
nombre_array=(valor1 valor2 valor3 ...)
```
**Por ejemplo:**
```bash
nombres=("Juan" "María" "Carlos" "Luisa")
edades=(20 25 30 35)
```

## Acceso a los Elementos

Para acceder a los elementos de un array, utilizamos su índice entre corchetes [ ]. Los índices en shell script comienzan desde 0.

**Acceder al primer elemento del array nombres**
```bash 
echo ${nombres[0]}
```
**Acceder al segundo elemento del array edades**
```bash
echo ${edades[1]}
```

**Acceso a varios elementos del array**
```
digito1=${numero:0:1}
dosprimerosdigitos=${numero:0:2}
tresdigitos=${numero:1:3}
```

* **Numero* es una variable que contiene un valor, probablemente un número. Esta variable se está utilizando como entrada para la expansión de parámetros.
* :0:1: Esta parte es una especificación de la expansión de parámetros. Está diciendo que deseamos extraer una porción del contenido de la variable numero.
* El primer número después del primer : (en este caso, 0) indica el índice inicial desde el cual deseamos extraer el contenido. En Bash, los índices comienzan desde 0, por lo que 0 significa que estamos comenzando desde el primer carácter de la cadena.
* El segundo número después del segundo : (en este caso, 1) indica la cantidad de caracteres que deseamos extraer. Aquí, 1 significa que solo queremos extraer un solo carácter.
* digito1 contendrá el primer dígito del valor almacenado en la variable numero. Por ejemplo, si numero es "12345", entonces digito1 contendrá "1".
* dosprimerosdigitos contendrá los dos primeros dígito del valor almacenado en la variable numero. Por ejemplo, si numero es "12345", entonces digito1 contendrá "12".
* tresdigitos. Por ejemplo, si numero es "12345", entonces digito1 contendrá "234".



### Longitud del Array
Podemos obtener la longitud de un array utilizando la expresión 

```
${#nombre_array[@]}.
```

**Obtener la longitud del array nombres**
```bash
echo "La longitud del array nombres es: ${#nombres[@]}"
```
## Iteración a través de un Array
Podemos iterar a través de un array utilizando un bucle for.

# Iterar a través del array nombres
```bash
for nombre in "${nombres[@]}"
do
    echo "Nombre: $nombre"
done
```
### Modificación de Elementos
Podemos modificar un elemento del array asignándole un nuevo valor.

```bash
edades[1]=28
```
Añadir Elementos
Podemos añadir elementos a un array utilizando el operador +=.

### Añadir un nuevo nombre al array nombres
```
nombres+=("Ana")
```
### Eliminar Elementos
Para eliminar un elemento de un array, podemos utilizar la palabra clave unset.

```
unset edades[1]
```


# Bibliografía

* https://bioinf.comav.upv.es/courses/unix/scripts_bash.html
* https://github.com/victorhtorres/Terminal-y-linea-de-comandos
* https://github.com/hatsem78/tutorial_bash_script_lunux
