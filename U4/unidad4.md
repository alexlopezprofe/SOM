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


# Comandos

## Comandos del sistema

- **help**. Una buena forma de comenzar es mediante el comando “help” que nos mostrará una lista con todos los comandos disponibles. “Help + nombre de comando” nos mostrará información sobre un comando específico mientras que “Nombre de comando + /?” nos mostrará todos los modificadores y posibilidades del comando.
- **cls**: Limpia la pantalla
- **date**: Visualiza la fecha del sistema y permite modificarla
- **time**: Muestra la hora del sistema y permite modificarla
- **ver**: Muestra la versión de Windows que estamos utilizando
- **prompt**: Nos indica y cambia el símbolo del sistema [texto] [parámetros]

<th>Carácter</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr>
<td>$q</td>
<td>= (signo igual)</td>
</tr>
<tr>
<td>$$</td>
<td>$ (Signo del dólar)</td>
</tr>
<tr>
<td>$t</td>
<td>Hora actual</td>
</tr>
<tr>
<td>$d</td>
<td>Fecha actual</td>
</tr>
<tr>
<td>$p</td>
<td>Unidad y ruta de acceso actuales</td>
</tr>
<tr>
<td>$v</td>
<td>Número de versión de Windows</td>
</tr>
<tr>
<td>$n</td>
<td>Unidad actual</td>
</tr>
<tr>
<td>$g</td>
<td>&gt; (Signo mayor que)</td>
</tr>
<tr>
<td>$l</td>
<td>&lt; (Signo menor que)</td>
</tr>
<tr>
<td>$b</td>
<td><code>|</code> (Símbolo de barra vertical)</td>
</tr>
<tr>
<td>=?</td>
<td>ENTER-LINEFEED</td>
</tr>
<tr>
<td>$e</td>
<td>Código de escape ANSI (código 27)</td>
</tr>
<tr>
<td>$h</td>
<td>Retroceso (para eliminar un carácter escrito en la línea de comandos)</td>
</tr>
<tr>
<td>$a</td>
<td>& (Y comercial)</td>
</tr>
<tr>
<td>$c</td>
<td>( (Paréntesis izquierdo)</td>
</tr>
<tr>
<td>$f</td>
<td>) (Paréntesis derecho)</td>
</tr>
<tr>
<td>$s</td>
<td>Space</td>
</tr>
</tbody>
</table>

<h3 id="examples">Ejemplos de prompt</h3>
<p>Para establecer un indicador de comandos de dos líneas con la hora y la fecha actuales en la primera línea y el signo mayor que en la línea siguiente, escriba:</p>
<pre><code>prompt $d$s$s$t$_$g
</code></pre>
<p>El símbolo del sistema se cambia de la siguiente manera, donde la fecha y hora son actuales:</p>
<pre><code>Fri 06/01/2007  13:53:28.91
</code></pre>
<p>Para establecer el símbolo del sistema para que se muestre como una flecha (<code>--&gt;</code>), escriba:</p>
<pre><code>prompt --$g
</code></pre>
<p>Para cambiar manualmente el símbolo del sistema a la configuración predeterminada (la unidad actual y la ruta de acceso seguidas del signo mayor que), escriba:</p>
<pre><code>prompt $p$g
</code></pre>


## Comandos de gestión de directorios

- **dir** Muestra una lista de los archivos y subdirectorios de un directorio. Si se usa sin parámetros, este comando muestra la etiqueta de volumen y el número de serie del disco, seguido de una lista de directorios y archivos del disco (como los nombres y la fecha y hora en que se modificó por última vez). En el caso de archivos, este comando muestra la extensión de nombre y el tamaño en bytes. Este comando también muestra el total de archivos y directorios que aparecen, el tamaño acumulado y el espacio libre (en bytes) que queda en el disco.

[Más información de dir en la ayuda de Microsoft](https://learn.microsoft.com/es-es/windows-server/administration/windows-commands/dir)


# Bibliografía

- https://learn.microsoft.com/es-es/windows-server/administration/windows-commands/prompt

