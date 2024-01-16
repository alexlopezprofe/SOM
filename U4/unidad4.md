# Unidad 4. Comandos de consola de Windows (CMD) ​

```
var sumar2 = function(numero) {
  return numero + 2;
}
```

# Introducción

Los comandos de Windows son una herencia de los primeros sistemas operativos que funcionaban en MSDOS. En ellos todas las instrucciones tenían que ser ejecutadas manualmente mediante comandos.
El uso de estos comandos mantiene plena su vigencia en el día de hoy, ya que permite realizar tareas de forma más flexible y rápida.

Todos los sistemas Windows incluyen una serie de comandos que permiten transmitir órdenes directamente al sistema operativo. Son simples instrucciones que se pueden usar de formas diferentes, la más conocida de ellas es introduciéndolos en la consola de CMD, aunque también se pueden utilizar en scripts o en archivos batch.

Muchos comandos han sido recientemente agregados ya que solo se empleaban como herramientas en paquetes o kits independientes para ser usados por profesionales. En cada versión de Windows liberada, son perfeccionados con opciones y modificadores nuevos, los que lo hacen aún más potentes.

Sin embargo, la línea de comandos muestra su potencia, por ejemplo, para ejecutar tareas repetitivas, en ocasiones donde se bloquea la interfaz gráfica o incluso para acceder a cierta información que no está disponible de ninguna otra manera. La aplicación tiene su equivalente en la consola de Mac OS X o en la terminal de Linux. Ésta mucho más potente aunque Windows también tiene la interfaz de consola PowerShell destinada a administradores de sistemas y con mayores posibilidades de este símbolo del sistema al que nos acercamos en su funcionamiento básico en este tema.

# Acceso al símbolo del sistema

Para iniciar la línea de comandos basta con pulsar la tecla Windows de nuestro teclado y escribir CMD y pulsar intro, otra alternativa es usar el atajo de teclado Windows + R y escribir CMD y pulsar el botón Aceptar.

Podemos acceder al símbolo del sistema de Windows en **modo usuario** --> *abrir* y en **modo administrador** --> *Ejecutar como administrador*, la primera limitada y la segunda más potente y con acceso a todo el equipo.

![image](https://github.com/alexlopezprofe/SOM/assets/148449360/66c50fe1-0c2e-4e16-81fb-4db42abe58be)

![image](https://github.com/alexlopezprofe/SOM/assets/148449360/613f3277-8b9e-4462-8c2c-56eea0c45951)

# Unidades, archivos, directorios y rutas
Una unidad es un dispositivo que se usa para almencenar información. Una unidad se designa con una letra. Por ejemplo a: c:

![image](https://github.com/alexlopezprofe/SOM/assets/148449360/c151bf71-9ce5-4d3e-ba79-164c9bda3da1)


Un archivo es un elemento que almacena un conjunto de datos para su posterior. Un archivo se define mediante un nombre, seguido de un punto y una extensión. Esta extensión suele ser una combinación de letras y números (normalmente solo letras) de 3 o 4 caracteres.

<center>archivo.txt</center>

## Consideraciones

- El nombre de los archivos no puede superar los 259 caracteres
- El sistema se distingue entre mayúsculas y minúsculas
- Los siguientes caracteres no se pueden utilizar para nombrar archivos o directorios \, /,  :,  *,  ?,  ",  <,  >,  \|
- Intentaremos evitar los espacios utilizando un guion bajo_
- Si un archivo o directorio lleva espacios y queremos acceder a él deberemos utilizar comillas “”
- Intentaremos evitar los caracteres especiales además de la ñ y ç para nombrar archivos y directorios

  ## Ruta de acceso

Hay dos tipos de ruta que debemos diferenciar:

- **Ruta absoluta:** Se indica toda la ruta del archivo incluyendo el directorio raíz.

```
C:\carpeta1\carpeta2\archivo1.doc

```
- **Ruta relativa:** Se indica la ruta a partir de donde este en ese momento situado. No se incluye el directorio raíz. Por ejemplo, si estamos en la ruta

```
:\carpeta1
```
y queremos acceder al archivo1 que está dentro de la carpeta2, seria:
```
carpeta2\archivo1.


Para ir al directorio padre, usamos dos puntos seguidos (..)



# Bibliografía

- 

