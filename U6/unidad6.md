# Unidad 6. Introducción a Linux

<div style="text-align:center"><img src="https://github.com/alexlopezprofe/SOM/assets/148449360/7357e3c4-9593-47b5-81f7-8744aacd1152" width="25%"></div>

Linux es un sistema operativo de código abierto, conocido por su estabilidad, seguridad y flexibilidad. Surgió en 1991 como un proyecto personal del programador finlandés Linus Torvalds, quien buscaba crear un sistema similar a UNIX pero que pudiera ser modificado y distribuido libremente.

Una de las características distintivas de Linux es su núcleo, el kernel Linux, que gestiona los recursos del hardware y permite que el sistema funcione. Aunque el kernel es solo una parte del sistema operativo completo, el término "Linux" se utiliza comúnmente para referirse a todo el sistema.

Linux se ha convertido en un componente fundamental en una amplia gama de dispositivos, desde servidores hasta dispositivos móviles y sistemas embebidos. También es la base de numerosas distribuciones, como Ubuntu, Fedora, Debian y CentOS, cada una con sus propias características y enfoques, pero todas compartiendo el núcleo Linux.

Una de las principales ventajas de Linux es su naturaleza de código abierto, lo que significa que su código fuente está disponible públicamente para que cualquiera lo examine, modifique y distribuya según sus necesidades. Esto ha llevado a una comunidad activa de desarrolladores y usuarios que contribuyen al desarrollo y mejora continua del sistema.

Además de su robustez y flexibilidad, Linux ofrece una amplia variedad de herramientas y aplicaciones gratuitas y de código abierto que cubren casi todas las necesidades informáticas, desde la navegación web hasta el desarrollo de software y la administración de servidores.

# Distribuciones de Linux

Las distribuciones de Linux, comúnmente llamadas "distros", son variantes del sistema operativo Linux que combinan el núcleo Linux con un conjunto específico de software y configuraciones para satisfacer las necesidades de diferentes usuarios y casos de uso. Cada distribución tiene su propia filosofía, objetivos y enfoque, lo que las hace únicas en términos de características, facilidad de uso, rendimiento y público objetivo.

Aquí hay una descripción general de algunas de las distribuciones de Linux más populares:

1. **Ubuntu**: Conocida por su facilidad de uso y amplia compatibilidad de hardware, Ubuntu es una de las distribuciones más populares tanto para usuarios domésticos como para servidores. Está basada en Debian y se centra en la facilidad de instalación, la estabilidad y el acceso a una gran cantidad de software a través de su gestor de paquetes.

2. **Debian**: Considerada una de las distribuciones más antiguas y estables, Debian es conocida por su compromiso con el software libre y su amplia selección de paquetes. Es la base de muchas otras distribuciones, incluyendo Ubuntu, y es popular entre usuarios avanzados y administradores de sistemas.

3. **Fedora**: Mantenida por la comunidad y respaldada por Red Hat, Fedora es conocida por su enfoque en la innovación y la adopción temprana de nuevas tecnologías. Es ideal para usuarios que desean estar a la vanguardia de las últimas características y mejoras en el software de código abierto.

4. **CentOS**: Derivada de la fuente abierta de Red Hat Enterprise Linux (RHEL), CentOS es una opción popular para servidores y entornos empresariales debido a su estabilidad y largo ciclo de vida de soporte. Es conocida por su compatibilidad con aplicaciones empresariales y su enfoque en la confiabilidad y seguridad.

5. **Linux Mint**: Basada en Ubuntu, Linux Mint se destaca por su facilidad de uso y su experiencia de escritorio amigable. Viene preinstalada con una variedad de software útil y está diseñada para ser familiar para usuarios que están migrando desde otros sistemas operativos como Windows.

6. **Arch Linux**: Dirigida a usuarios avanzados y entusiastas de Linux, Arch Linux sigue un enfoque de "hágalo usted mismo", donde los usuarios construyen su sistema desde cero seleccionando y configurando manualmente los componentes que desean. Es conocida por su simplicidad y minimalismo, así como por su comunidad activa y documentación detallada.

Estas son solo algunas de las muchas distribuciones de Linux disponibles, cada una con sus propias fortalezas, características y comunidad de usuarios. La elección de una distribución depende en gran medida de las necesidades y preferencias individuales del usuario.

## Carpetas relevantes en Linux

+ **/** **(root)**: Es la carpeta principal del sistema de archivos. Todas las demás carpetas y archivos se encuentran dentro de esta carpeta.
+  **/home**: Contiene las carpetas de inicio de los usuarios. Cada usuario tiene su propia carpeta dentro de /home que sirve como su espacio de trabajo personal.

```bash
user@user-virtual-machine:/home$ ls 
user
```

+  **/etc**: Almacena archivos de configuración del sistema. Aquí se encuentran archivos de configuración para diversos servicios y aplicaciones.
+  **/var**: Contiene datos variables, como archivos de registro (logs), correos electrónicos y otros datos que pueden cambiar con el tiempo.
+  **/bin y /usr/bin**: Contienen programas ejecutables (binarios) accesibles para todos los usuarios del sistema.
+  **/sbin y /usr/sbin**: Almacenan programas ejecutables de administración del sistema, generalmente reservados para usuarios con privilegios de administrador (root).
+  **/tmp**: Es un directorio temporal utilizado por aplicaciones para almacenar archivos temporales. El contenido de esta carpeta se borra cuando se reinicia el sistema.


# Información de los archivos

El comando `ls` Muestra el listado del directorio actual; si le añadimos la opcion `-l`, `ls -l` nos permite listar la información de tipo de archivo, de permisos, usuario, grupo, tamaño, fecha de modificación entre otras características más, del directorio actual.

```bash
ls -l 
> 
```

![image](https://github.com/alexlopezprofe/SOM/assets/148449360/4800ce34-370a-438e-804a-267d7d6817e4)

![image](https://github.com/alexlopezprofe/SOM/assets/148449360/13979e26-3499-4f2b-bf62-8565b4d5919e)

## Tipos de archivo:

| Símbolo | Tipo de archivo         | Descripción                                                              |
|---------|-------------------------|--------------------------------------------------------------------------|
| -       | Regular                 | Archivo de datos estándar                                               |
| d       | Directorio              | Contiene nombres de archivo y enlaces a otros archivos                   |
| l       | Enlace simbólico        | Puntero a otro archivo o directorio                                      |
| b       | Dispositivo de bloque   | Dispositivo de almacenamiento de datos que se lee y escribe en bloques   |
| c       | Dispositivo de caracteres | Dispositivo de entrada/salida que se lee y escribe en caracteres         |
| p       | Pipe (Tubo)             | Comunicación entre procesos, también conocido como FIFO (First In, First Out) |
| s       | Socket                  | Comunicación interprocesos a través de la red o del sistema de archivos  |
| -       | Enlace duro             | Nombre adicional (alias) para un archivo existente                       |

# Tipos de usuarios:

* usuario **root** (El todo poderoso)
	* Administrador del sistema
	* Acceso total a todos los archivos y directorios
	* Controla la administración de cuentas de usuarios
	* Tiene privilegios sobre todo el sistema 
	* Modifica, instala, detiene, reconfigura procesos del sistema.
* Usuarios **especiales**
	* bin, daemon, adm, lp, sync, shutdown, mail, operator, squid, apache, etc.
	* Se les conoce como cuentas de "no inicio de sesión" (nologin). 
	* Comúnmente como cuentas del sistema.	
	* Asumen distintos privilegios de root dependiendio de la cuenta.
	* No tienen contraseñas.	
	* Generalmente se crean automáticamente al momento de la instalación de Linux o de la aplicación.
* Usuarios **normales**
	* Se usan para usuarios individuales.
	* Cada usuario dispone de un directorio de trabajo, ubicado generalmente en /home.
	* Cada usuario puede personalizar su entorno de trabajo.
	* Tienen solo privilegios completos en su directorio de trabajo o HOME.

Un Sistema **Multiusuario** permite que dos o más usuarios utilicen sus programas.

# Permisos

En Linux, los permisos de archivos y carpetas son un componente importante para gestionar la seguridad y el acceso a la información almacenada en el sistema de archivos de tu equipo. Estos permisos definen quién puede leer, escribir o ejecutar un archivo o directorio y desempeñan un papel fundamental en la protección de la integridad del sistema y la privacidad de los datos.

Puede parecer simple, pero todo puede llegar a tener cierta complejidad a la hora de asignar los permisos en Linux. Todos ellos se pueden aplicar de diferentes formas. Tanto en red, con diferentes usuarios en un servidor, como en loca. Donde varios usuarios pueden manejar un mismo PC, con algunos recursos compartidos entre sí.

* **Lectura (r):** Es el primer permiso que podemos encontrarnos. Este nos da la opción de que un usuario pueda ver el contenido al que quiere acceder.
* **Escritura (w):** Nos da la posibilidad de otorgar poder sobre sobre un archivo. De esta forma podrá ser modificado, al igual que un directorio.
* **Ejecución (x):** Permite a los usuarios ejecutar diferentes parámetros dentro del equipo.
* **Sin permisos (-):** Nos indica que el usuario no tiene ningún tipo de permiso sobre el recurso de red o contenido compartido.

## Niveles de permisos

* **Propietario/Usuario (user - u):** El propietario es el usuario que creó el archivo o directorio. Este tiene el control total sobre los permisos y puede modificarlos según sus necesidades. Los permisos del propietario afectan directamente al usuario que creó el archivo.
*  **Grupo (group - g):** En Linux, los usuarios se organizan en grupos y un archivo o directorio puede pertenecer a uno de estos grupos. Los permisos asignados al grupo afectan a todos los usuarios que forman parte de ese grupo, permitiéndoles acceder y modificar archivos en conjunto.
*  **Otros (others - o):** Este conjunto de permisos se aplica a cualquier usuario que no sea el propietario ni esté en el grupo especificado. Los permisos otorgados o denegados a otros usuarios aseguran que el sistema permanezca protegido contra accesos no autorizados.
*  **Todos (all - a)):** Si se necesita otorgar permisos a todos
  
La combinación de estas tres categorías o niveles y sus respectivos permisos crea un sistema que permite el control sobre quién puede hacer qué con un archivo o directorio. El uso principal de los permisos en Linux es garantizar la seguridad y la privacidad de los datos, al tiempo que permite la colaboración y el acceso necesario para los usuarios autorizados.

![image](https://github.com/alexlopezprofe/SOM/assets/148449360/dc503d31-38d6-4a21-9840-dd27076bb072)

| Permiso                            | Notación simbólica | Notación octal |
|------------------------------------|---------------------|----------------|
| Sin permisos                       | `---`               | 0              |
| Ejecución                          | `--x`               | 1              |
| Escritura                          | `-w-`               | 2              |
| Escritura y ejecución              | `-wx`               | 3              |
| Lectura                            | `r--`               | 4              |
| Lectura y ejecución                | `r-x`               | 5              |
| Lectura y escritura                | `rw-`               | 6              |
| Lectura, escritura y ejecución     | `rwx`               | 7              |

| Permisos (Notación Octal) | Descripción                                                        |
|----------------------------|--------------------------------------------------------------------|
| `rw-------` (600)          | Sólo el propietario tiene el derecho de leer y escribir.           |
| `rw-r--r--` (644)          | Sólo el propietario tiene los permisos de leer y escribir; el grupo y los demás solo pueden leer. |
| `rwx------` (700)          | Sólo el propietario tiene los derechos de leer, escribir y ejecutar el archivo. |
| `rwxr-xr-x` (755)          | El propietario tiene los derechos de leer, escribir y ejecutar; el grupo y los demás solo pueden leer y ejecutar. |
| `rwx--x--x` (711)          | El propietario tiene los derechos de lectura, escritura y ejecución; el grupo y los demás solo pueden ejecutar. |
| `rw-rw-rw-` (666)          | Todo el mundo puede leer y escribir en el archivo. ¡No es una buena elección! |
| `rwxrwxrwx` (777)          | Todo el mundo puede leer, escribir y ejecutar. ¡Tampoco es una buena elección! |


## Cambio de permisos

Para cambiar los permisos de un archivo o directorio en Linux, puedes utilizar el comando `chmod`. Este comando te permite modificar los permisos de lectura, escritura y ejecución para el propietario del archivo, el grupo al que pertenece y para otros usuarios.

La sintaxis básica del comando `chmod` es la siguiente:

```
chmod [opciones] permisos archivo/directorio
```
| Opción                | Descripción                                                     |
|-----------------------|-----------------------------------------------------------------|
| `-c`, `--changes`     | Muestra únicamente los archivos modificados.                   |
| `-f`, `--silent`, `--quiet` | No muestra mensajes de error.                             |
| `-v`, `--verbose`     | Muestra mensajes detallados sobre los cambios realizados.       |
| `--reference=archivo`  | Utiliza los permisos del archivo de referencia.                |
| `--preserve-root`      | No cambia los permisos de `/` y `/..`.                          |
| `--no-preserve-root`   | Cambia los permisos de `/` y `/..`.                             |
| `-R`, `--recursive`    | Cambia los permisos de forma recursiva en directorios y su contenido. |
| `--help`               | Muestra el manual de ayuda del comando.                         |
| `--version`            | Muestra la versión del comando.                                 |


### Ejemplos notación simbólica:

| Ejemplo               | Descripción                                        | Resultado         |
|-----------------------|----------------------------------------------------|-------------------|
| `$ touch foto1.png`  | Creamos el archivo foto1.png                      | foto1.png        |
| `$ chmod a-rwx foto1.png` | Quitamos todos los permisos al archivo foto1.png | ---------         |
| `$ chmod u+rwx foto1.png` | Añadimos todos los permisos para el propietario  | rwx------         |
| `$ chmod g+x foto1.png` | Añadimos el permiso de ejecución para el grupo    | rwx--x---         |
| `$ chmod o+r foto1.png` | Añadimos el permiso de lectura para los otros usuarios | rwx--xr--         |
| `$ chmod u-rw foto1.png` | Eliminamos los permisos de lectura y escritura para el propietario | --x--xr--         |
| `$ chmod a=r foto1.png` | Establecemos como único permiso de lectura para los 3 grupos | r--r--r--         |
| `$ chmod a=rx foto1.png` | Establecemos los permisos de lectura y ejecución para los 3 grupos | r-xr-xr-x         |
| `$ chmod a=- foto1.png` | Quitamos todos los permisos                       | ---------         |
| `$ chmod u+rx,o+x foto1.png` | Añadimos los permisos de lectura y ejecución al propietario y ejecución a otros | r-x-----x         |
| `$ chmod g+rx,o-x foto1.png` | Añadimos permiso de lectura y ejecución al grupo y eliminamos permiso de ejecución a otros | r-xr-x---         |
| `$ chmod ug+wx,o-x foto1.png` | Añadimos permiso de escritura y ejecución al propietario y grupo, y eliminamos permiso de ejecución a otros | rwxrwx---         |
| `$ chmod a=rw foto1.png` | Permite a cualquiera modificar el contenido e incluso eliminar el archivo | rw-rw-rw-         |

### Ejemplos notación octal:

| Ejemplo               | Descripción                                        | Resultado         |
|-----------------------|----------------------------------------------------|-------------------|
| `$ touch foto2.png`  | Creamos el archivo foto2.png                      | foto2.png        |
| `$ chmod 000 foto2.png` | Quitamos todos los permisos al archivo foto2.png | ----------         |
| `$ chmod 700 foto2.png` | Añadimos todos los permisos para el propietario  | -rwx------         |
| `$ chmod 710 foto2.png` | Añadimos el permiso de ejecución para el grupo    | -rwx--x---         |
| `$ chmod 714 foto2.png` | Añadimos el permiso de lectura para los otros usuarios | -rwx--xr--         |
| `$ chmod 114 foto2.png` | Eliminamos los permisos de lectura y escritura para el propietario | ---x--xr--         |
| `$ chmod 444 foto2.png` | Establecemos como único permiso de lectura para los 3 grupos | -r--r--r--         |
| `$ chmod 555 foto2.png` | Establecemos los permisos de lectura y ejecución para los 3 grupos | -r-xr-xr-x         |
| `$ chmod 000 foto2.png` | Quitamos todos los permisos                       | ----------         |
| `$ chmod 501 foto2.png` | Añadimos los permisos de lectura y ejecución al propietario y ejecución a otros | -r-x-----x         |
| `$ chmod 550 foto2.png` | Añadimos permiso de lectura y ejecución al grupo y eliminamos permiso de ejecución a otros | -r-xr-x---         |
| `$ chmod 770 foto2.png` | Añadimos permiso de escritura y ejecución al propietario y grupo, y eliminamos permiso de ejecución a otros | -rwxrwx---         |
| `$ chmod 666 foto2.png` | Permite a cualquiera modificar el contenido e incluso eliminar el archivo | -rw-rw-rw-         |

### Recursividad

Si cambiamos los permisos a un directorio y deseamos que estos permisos tengan efecto sobre todos sus subdirectorios y archivos
sólo deberemos añadir la opción `–R`. 

```bash
$ chmod a=rw DIRECTORIO –R
```
# Gestión de usuarios

En los sistemas UNIX, hay cuatro archivos que constituyen la base de datos de los usuarios locales. Todos los archivos se caracterizan porque cada línea define una entidad distinta y porque los campos que constituyen cada entidad se separan por el carácter dos puntos (":").

>Antes de pasar a ver con qué ordenes podemos consultar y manipular esta base de datos, veamos las particularidades de cada archivo:
<dl id="etc-group">

Almacena la definición de los grupos locales, uno por línea. Su formato es el siguiente:

<div class="highlight-unixconfig notranslate"><div class="highlight"><pre><span></span>audio<span class="p">:</span><span class="s">x</span><span class="p">:</span><span class="m">29</span><span class="p">:</span>pepe,manolo,josem
</pre></div>
</div>
<p>O sea, cuatro campos:</p>
<ol class="arabic simple">
<li><p>El <strong>nombre</strong> del grupo (<em>audio</em> en este caso),</p></li>
<li><p>La <em>contraseña</em> de grupo. Esta contraseña sirve para dar acceso a un usuario a un grupo al que no pertenezca (para ello puede usarse el comando <a class="reference internal" href="#newgrp">newgrp</a>). En los <em>unices</em> modernos su valor es siempre la letra
«<kbd class="kbd docutils literal notranslate">x</kbd>», que significa que la contraseña se encuentra en el archivo
<a class="reference internal" href="#etc-gshadow"><span class="std std-ref">/etc/gshadow</span></a>.</p></li>
<li><p>El identificador del grupo (llamado <abbr title="Group IDentifier">GID</abbr>).</p></li>
<li><p>Los <strong>usuarios</strong> que pertenecen al grupo separados por comas. En esta lista
no aparecen los usuarios cuyo <em>grupo principal</em> sea este mismo grupo, ya
que su pertenencia al grupo puede deducirse de su  <a class="reference internal" href="#grupo-principal"><span class="std std-ref">registro en
/etc/passwd</span></a>.</p></li>
</ol>
</dd>
</dl>
<dl id="etc-passwd">
<dt><code class="file docutils literal notranslate"><span class="pre">/etc/passwd</span></code></dt><dd><p>Almacena los usuarios y sus datos. El formato de cada línea es el siguiente:</p>
<div class="highlight-unixconfig notranslate"><div class="highlight"><pre><span></span>josem<span class="p">:</span><span class="s">x</span><span class="p">:</span><span class="m">1000</span><span class="p">:</span><span class="m">1000</span><span class="p">:</span>Jose Miguel,,,<span class="p">:</span><span class="s">/home/josem</span><span class="p">:</span><span class="s">/bin/bash</span>
</pre></div>
</div>
<p id="grupo-principal">En este caso, los campos son siete:</p>
<ol class="arabic simple">
<li><p>El <strong>nombre</strong> de usuario.</p></li>
<li><p>La <strong>contraseña</strong>. Este campo, sin embargo, contiene en los <em>unices</em>
modernos<a class="footnote-reference brackets" href="#id8" id="id2" role="doc-noteref"><span class="fn-bracket">[</span>2<span class="fn-bracket">]</span></a> el carácter «<kbd class="kbd docutils literal notranslate">x</kbd>», que indica al sistema que la
contraseña debe buscarse en otro archivo (<a class="reference internal" href="#etc-shadow"><span class="std std-ref">/etc/shadow</span></a>,
que se analizará a continuación).</p></li>
<li><p>El identificador de usuario (<abbr title="User IDentifier">UID</abbr>) que es el código numérico asociado a
cada usuario. Este número es realmente el que se usa en el sistema de
archivos para determinar la propiedad de los archivos, así que en el fondo
es el identificador realmente importante y no el nombre de usuario, que
puede modificarse en cualquier momento sin provocar ningún efecto
traumático. Se discutirá después. Este mismo comentario es aplicable al
nombre de grupo y su <em>gid</em> asociado que se encuentran en
<code class="file docutils literal notranslate"><span class="pre">/etc/group</span></code>.</p></li>
<li><p>El <abbr title="Group IDentifier">GID</abbr> del <em>grupo principal</em>. Un usuario puede pertenece a varios
grupos y a efectos de permisos es irrelevante que un grupo determinado sea
o no su grupo principal, mientras pertenezca a él. Sin embargo, como
<a class="reference internal" href="05b.permisos.html#ugo"><span class="std std-ref">ya se verá</span></a>, todo archivo tiene un usuario propietario y un
grupo propietario. Cuando un usuario crea un archivo, tal archivo le
pertenecerá (esto es, el propio creador será el propietario) y el grupo
propietario será el grupo principal del usuario creador. Por tanto, si
este usuario <em>josem</em> crea un archivo pertenecerá al grupo de <abbr title="Group IDentifier">GID</abbr>
<strong>1000</strong> y no al grupo audio (<abbr title="Group IDentifier">GID</abbr> <strong>29</strong>), aunque
<em>josem</em> también pertenece a este último.</p></li>
<li><p>La <strong>información personal</strong> del usuario (nombre real, etc.), que suele
denominarse información <abbr title="General Comprehensive Operating System">GECOS</abbr>.</p></li>
<li><p>El <strong>directorio personal</strong> del usuario.</p></li>
<li><p>La <strong>shell</strong> predeterminada del usuario que se ejecutará al hacer ingreso en
el sistema. Las cuentas que no representan usuarios normales, sino que son
necesarias para el funcionamiento de ciertos programas suelen tener como
<em>shell</em> el comando <a class="reference internal" href="../07.avanzada/07.concatenacion.html#false"><span class="std std-ref">false</span></a> (<strong class="command">/bin/false</strong>), lo que
impide que puedan usarse de modo interactivo.</p></li>
</ol>
<div class="admonition note">
<p class="admonition-title">Nota</p>
<p>En algunos Linux, incluida Debian, existe el ejecutable
<strong class="command">/usr/sbin/nologin</strong> que se comporta como
<strong class="command">/bin/false</strong>, pero, además, muestra un mensaje de que la
cuenta se encuentra deshabilitada.</p>
</div>
<div class="admonition note">
<p class="admonition-title">Nota</p>
<p>En <code class="file docutils literal notranslate"><span class="pre">/etc/shells</span></code> se encuentra la lista de <em>shells</em> que
el sistema considera válidas. Los servicios que usa de modo interactivo
el usuario (<em>login</em>, <em>ssh</em>, <em>ftp</em>, etc.) suelen comprobar si la <em>shell</em>
se encuentra dentro de este listado y, si no es así, impiden el acceso.</p>
</div>
</dd>
</dl>
<dl id="etc-shadow">
<dt><code class="file docutils literal notranslate"><span class="pre">/etc/shadow</span></code></dt><dd><p>Almacena las contraseñas cifradas de los usuarios y campos adicionales
con información sobre ellas (caducidad, etc). En realidad, las contraseñas no
están propiamente cifradas, sino que se les aplica una <a class="reference internal" href="../../98.apendice/01.cryto/02.algo.html#hash"><span class="std std-ref">función de hash</span></a>. Por ejemplo, la información del usuario «<em>usuario</em>» es la
siguiente:</p>
<div class="highlight-unixconfig notranslate"><div class="highlight"><pre><span></span><span class="c"># getent shadow usuario</span>
usuario<span class="p">:</span><span class="s">$6$feeCGVjY$m4drjYETO7DNffE/8AwmTvRnTj8qmSMy8AhMq1jaNf3ZonyAFPVc64SsY/iWTR3LxtXKnD2hfavS1FXwelAyq1</span><span class="p">:</span><span class="m">17782</span><span class="p">:</span><span class="m">0</span><span class="p">:</span><span class="m">99999</span><span class="p">:</span><span class="m">7</span><span class="p">:::</span>
</pre></div>
</div>
<p>La contraseña es ell segundo campo, ese chorizo inmenso en el que se aprecian tres subcampos
separados por dólares:</p>
<dl>
<dt><code class="docutils literal notranslate"><span class="pre">6</span></code></dt><dd><p>Es el <a class="reference internal" href="../../98.apendice/01.cryto/02.algo.html#hash"><span class="std std-ref">algoritmo</span></a> usado, según la siguiente tabla:</p>
<table class="docutils align-default">
<thead>
<tr class="row-odd"><th class="head"><p>Código</p></th>
<th class="head"><p>Algoritmo</p></th>
</tr>
</thead>
<tbody>
<tr class="row-even"><td><p>1</p></td>
<td><p>MD5 (desaconsejado)</p></td>
</tr>
<tr class="row-odd"><td><p>2b</p></td>
<td><p>Blowfish</p></td>
</tr>
<tr class="row-even"><td><p>5</p></td>
<td><p>SHA-256</p></td>
</tr>
<tr class="row-odd"><td><p>6</p></td>
<td><p>SHA-512</p></td>
</tr>
<tr class="row-even"><td><p>7</p></td>
<td><p>Colin Percival</p></td>
</tr>
<tr class="row-odd"><td><p>y</p></td>
<td><p>Solar Designer</p></td>
</tr>
</tbody>
</table>
<p>Los posibles algoritmos se encuentran referidos en la página de manual de
<em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/crypt(5)">crypt(5)</a></em>.</p>
</dd>
<dt><code class="docutils literal notranslate"><span class="pre">feeCGVjY</span></code></dt><dd><p>Es <a class="reference external" href="https://es.wikipedia.org/wiki/Sal_(criptograf%C3%ADa)">la sal</a>
utilizada para la generación del resumen.</p>
</dd>
<dt><code class="docutils literal notranslate"><span class="pre">m4drjYETO7DNffE/8AwmTvRnTj8qmSMy8AhMq1jaNf3ZonyAFPVc64SsY/iWTR3LxtXKnD2hfavS1FXwelAyq1</span></code></dt><dd><p>El resumen resultante de aplicar a la contraseña el algoritmo usando la sal.</p>
</dd>
</dl>
<p id="index-0"><span id="mkpasswd"></span>Como de antemano sabemos que la contraseña en claro es «<em>usuario</em>», podemos
generar el resumen<a class="footnote-reference brackets" href="#id9" id="id3" role="doc-noteref"><span class="fn-bracket">[</span>3<span class="fn-bracket">]</span></a> que aparece en <code class="file docutils literal notranslate"><span class="pre">/etc/shadow</span></code> del siguiente
modo:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>mkpasswd<span class="w"> </span>-m<span class="w"> </span>sha512crypt<span class="w"> </span>-S<span class="w"> </span>feeCGVjY<span class="w"> </span>usuario
<span class="gp">$</span><span class="m">6</span><span class="nv">$feeCGVjY$m4drjYETO7DNffE</span>/8AwmTvRnTj8qmSMy8AhMq1jaNf3ZonyAFPVc64SsY/iWTR3LxtXKnD2hfavS1FXwelAyq1
</pre></div>
</div>
<p>La nombre para expresar el algoritmo puede obtenerse consultando los nombres
disponibles:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>mkpasswd<span class="w"> </span>-m<span class="w"> </span><span class="nb">help</span>
</pre></div>
</div>
</dd>
</dl>
<dl class="simple" id="etc-gshadow">
<dt><code class="file docutils literal notranslate"><span class="pre">/etc/gshadow</span></code></dt><dd><p>Almacena las contraseñas cifradas de los grupos. Sin embargo, es raro que
tales contraseñas existan, ya que este método para ganar accesos tiene la
debilidad de exigir que varios usuarios deban compartir una misma contraseña.
Por ello prescindiremos de analizar su formato.</p>
</dd>
</dl>
<div class="admonition warning">
<p class="admonition-title">Advertencia</p>
<p>Absténgase de alterar a mano los archivos anteriores. Existen
herramientas para hacerlo que trataremos a continuación.</p>
</div>
<section id="consulta">
<h2><span class="section-number">2.3.1.1. </span>Consulta<a class="headerlink" href="#consulta" title="Link to this heading">¶</a></h2>
<p>Hay varios comando relacionados con el propósito de conocer información acerca
de usuarios y grupos:</p>
<span id="index-1"></span><dl id="who">
<dt><em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/who">who</a></em></dt><dd><p>Muestra los usuarios que ingresaron en el sistema y en qué terminal se
encuentran:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>who
<span class="go">josem    pts/0        2016-10-12 08:35 (:0.0)</span>
<span class="go">josem    pts/1        2016-10-12 08:36 (tmux(3218).%0)</span>
<span class="go">josem    pts/2        2016-10-12 12:18 (tmux(3218).%5)</span>
</pre></div>
</div>
<div class="admonition note">
<p class="admonition-title">Nota</p>
<p>Es también útil el comando con el parámetro <code class="docutils literal notranslate"><span class="pre">-b</span></code> que permite conocer
cuándo se arrancó el sistema:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>who<span class="w"> </span>-b
<span class="go">         arranque del sistema 2016-10-12 08:33</span>
</pre></div>
</div>
</div>
<div class="admonition warning">
<p class="admonition-title">Advertencia</p>
<p>Se muestran sólo los usuarios con los que se abrió la terminal y no usuarios
a los que se haya podido acceder luego a través del comand <a class="reference internal" href="#su"><span class="std std-ref">su</span></a>.</p>
</div>
</dd>
</dl>
<span id="whoami"></span><dl id="index-2">
<dt><em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/whoami">whoami</a></em></dt><dd><p>Muestra quién es el usuario que se está utilizando:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>whoami
<span class="go">josem</span>
</pre></div>
</div>
</dd>
</dl>
<span id="logname"></span><dl id="index-3">
<dt><em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/logname">logname</a></em></dt><dd><p>Muestra cuál es el usuario con el que se ingresó en el sistema:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>logname
<span class="go">josem</span>
</pre></div>
</div>
<div class="admonition warning">
<p class="admonition-title">Advertencia</p>
<p>En ciertas ocasiones <strong class="command">whoami</strong> (o el explicado posteriormente
<a class="reference internal" href="#id"><span class="std std-ref">id</span></a>) y <strong class="command">logname</strong> no devuelven el mismo usuario. Véase
<a class="reference internal" href="#su"><span class="std std-ref">su</span></a> más adelante.</p>
</div>
</dd>
</dl>
<span id="groups"></span><dl id="index-4">
<dt><em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/groups">groups</a></em></dt><dd><p>Muestras los usuarios a los que pertenece el usuario que se proporciona como
argumento. Si no se especifica usuario, se sobreentiende que es aquel que
ejecuta la orden:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>groups<span class="w"> </span>josem
<span class="go">josem cdrom floppy audio dip video plugdev staff users netdev qemusers</span>
</pre></div>
</div>
</dd>
</dl>
<span id="index-5"></span><dl id="id">
<dt><em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/id">id</a></em></dt><dd><p>Sirve para obtener información del usuario cuyo nombre se proporciona como
argumento. Si no se especifica, se sobreentiende que es aquel que ejecuta la
orden:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>id<span class="w"> </span>josem
<span class="go">uid=1000(josem) gid=1000(josem) grupos=1000(josem),24(cdrom),25(floppy),29(audio),</span>
<span class="go">30(dip),44(video),46(plugdev),50(staff),100(users),107(netdev),117(qemusers)</span>
</pre></div>
</div>
<p>El comando puede usarse también para obtener información más precisa:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>id<span class="w"> </span>-u<span class="w"> </span>josem
<span class="go">1000</span>
<span class="gp">$ </span>id<span class="w"> </span>-g<span class="w"> </span>josem
<span class="go">1000</span>
<span class="gp">$ </span>id<span class="w"> </span>-G<span class="w"> </span>josem
<span class="go">1000 24 25 29 30 44 46 50 100 107 117</span>
</pre></div>
</div>
<p>Si se incluye el parámetro <kbd class="kbd docutils literal notranslate">-n</kbd>, se devuelven nombres y no números. Por
tanto:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>id<span class="w"> </span>-Gn<span class="w"> </span>josem
<span class="go">josem cdrom floppy audio dip video plugdev staff users netdev qemusers</span>
</pre></div>
</div>
<p>equivale a usar <a class="reference internal" href="#groups">groups</a>.</p>
</dd>
</dl>
<span id="index-6"></span><dl id="getent">
<dt><em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/getent">getent</a></em></dt><dd><p>Sirve para obtener la información de usuarios, grupos y contraseñas tal y como
se observa en los archivos <code class="file docutils literal notranslate"><span class="pre">/etc/passwd</span></code> y <code class="file docutils literal notranslate"><span class="pre">/etc/group</span></code>:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="go">getent (passwd|group|shadow) [&lt;nombre&gt;]</span>
</pre></div>
</div>
<p>Dependiendo de si el primer argumento es <code class="docutils literal notranslate"><span class="pre">passwd</span></code> o <code class="docutils literal notranslate"><span class="pre">group</span></code> o <code class="docutils literal notranslate"><span class="pre">shadow</span></code>,
se devuelve información sobre usuarios, grupos o contraseñas. El segundo
argumento es el nombre de usuario o de grupo del que se quiere obtener la
información. Si no se especifica ninguno, se devuelve la información de
todos:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>getent<span class="w"> </span>passwd<span class="w"> </span>josem
<span class="go">josem:x:1000:1000:Jose Miguel,,,:/home/josem:/bin/bash</span>
</pre></div>
</div>
<div class="admonition note">
<p class="admonition-title">Nota</p>
<p>Podría pensarse que usar <strong class="command">getent</strong> es equivalente a consultar
directamente el contenido de los archivos correspondientes, pero no es
así. <strong class="command">getent</strong> devuelve información sobre todos los usuarios y
grupos reconocidos por el sistema, algunos de los cuales pueden no ser
locales, sino estar definidos en servidores como <em>samba</em> o <em>openldap</em>.</p>
</div>
</dd>
</dl>
</section>
<section id="manipulacion">
<h2><span class="section-number">2.3.1.2. </span>Manipulación<a class="headerlink" href="#manipulacion" title="Link to this heading">¶</a></h2>
<p>La manipulación implica la creación, eliminación y modificación de usuarios y
grupos. Obviamente, es posible editar<a class="footnote-reference brackets" href="#id10" id="id4" role="doc-noteref"><span class="fn-bracket">[</span>4<span class="fn-bracket">]</span></a> directamente los archivos ya
mencionados, aunque es infinitamente más recomedable hacer uso de programas
específicos, que serán los que se traten a continuación.</p>
<span id="adduser"></span><dl id="index-7">
<dt><em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/adduser">adduser</a></em></dt><dd><p>Como su nombre indica, sirve para añadir un usuario local al sistema. Su
sintaxis es:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="go">adduser [opciones] &lt;nombre&gt;</span>
</pre></div>
</div>
<p>Y en su uso más básico no exige ninguna opción. Ejecutado de este modo, el
comando preguntará por la contraseña y la información <em>gecos</em>; y hará una
serie de presuposiciones algunas de ellas basadas en el contenido del archivo
de configuración <code class="file docutils literal notranslate"><span class="pre">/etc/adduser.conf</span></code>:</p>
<ul class="simple">
<li><p>El <abbr title="User IDentifier">UID</abbr> será el siguiente disponible dentro del rango de números
reservado para los usuarios que son personas,</p></li>
<li><p>Se creará un grupo con el mismo nombre que el usuario y se le
escogerá como grupo principal.</p></li>
<li><p>El usuario no pertenecerá a ningún grupo adicional.</p></li>
<li><p>El directorio personal será <code class="file docutils literal notranslate"><span class="pre">/home/nombre_del_usuario</span></code>.</p></li>
</ul>
<p>Por ejemplo:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>adduser<span class="w"> </span>nuevo
</pre></div>
</div>
<p>Creará un usuario de nombre <em>nuevo</em> bajo estos presupuestos. Conviene leer
la página del manual y el archivo <code class="file docutils literal notranslate"><span class="pre">/etc/adduser.conf</span></code> para saber cómo
alterar este comportamiento. No obstante, es interesante aclarar algo que se
llegará a descubrir si se lee el archivo de configuración.</p>
<p>Hay tres rangos de números definidos para los usuarios:</p>
<ol class="arabic simple">
<li><p>El rango <strong>1-99</strong> (<strong>0</strong> es siempre el identificador del administrador,
que se llama <strong>root</strong>) reservado a ciertos usuarios que vienen creados
desde la instalación por <em>Debian</em> (p.e. <em>www-data</em>).</p></li>
<li><p>El rango <strong>100-999</strong> se reserva a usuarios de sistema, esto es, usuarios
destinados a servir como ejecutores de ciertos programas, por lo
general, servicios (o <em>demonios</em> en la terminología de <em>unix</em>).</p></li>
<li><p>El rango <strong>1000-99999</strong> se destina a usuarios normales que son los que
usan interactivamente las personas que acceden el sistema.</p></li>
</ol>
<p>Es conveniente tener presente estos números si decidimos asignar nosotros
manualmente el <abbr title="User IDentifier">UID</abbr> al usuario. Pero lo más lógico y cómodo es dejar que
<strong class="command">adduser</strong> se encargue de asignar el identificador: jamás pondrá uno
menor a 100, normalmente usará uno por encima de 999, y sólo si se usa la
opción <code class="docutils literal notranslate"><span class="pre">--system</span></code> considerará el usuario como usuario de sistema y escogerá
un número entre 100 y 999.</p>
<p>También es importante reseñar que es imposible pasar a <strong class="command">adduser</strong> la
contraseña de usuario (lo más que puede hacerse es dejarlo sin contraseña) lo
que imposibilita usarlo para dar de alta usuarios funcionales
automáticamente. A menos, claro está, que se dejen sin contraseña y se use
luego otro comando como <a class="reference internal" href="#chpasswd">chpasswd</a>.</p>
<p>Un uso habitual de <strong class="command">adduser</strong> es añadir un usuario existente a un
grupo existente. Para ello basta con usarlo del siguiente modo:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>adduser<span class="w"> </span>nuevo<span class="w"> </span>disk
</pre></div>
</div>
<p>En este caso, <em>nuevo</em> es el usuario que existe y <em>disk</em>, el grupo existente
al que se añade tal usuario.</p>
<p>En realidad, <strong class="command">adduser</strong> es un <em>script</em> escrito en <a class="reference external" href="http://www.perl.org">perl</a> que evita tener que usar el <span class="target" id="index-8"></span>comando
de más bajo nivel <em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/useradd">useradd</a></em>. De hecho, la página de manual de este
último comando aconseja a los administradores de <em>Debian</em> usar
<strong class="command">adduser</strong>:</p>
<blockquote>
<div><p>useradd is a low level utility for adding users. On Debian, administrators
should usually use <em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/adduser(8)">adduser(8)</a></em> instead.</p>
</div></blockquote>
<p>Por esta razón, no entraremos a discutir el uso de <strong class="command">useradd</strong>;  ni
por la misma razón el <span class="target" id="index-9"></span>uso de <em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/userdel">userdel</a></em>.</p>
</dd>
</dl>
<span id="deluser"></span><dl id="index-10">
<dt><em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/deluser">deluser</a></em></dt><dd><p><em>Script</em> que sirve para borrar usuarios locales. En principio, sólo borra el
usuario (y su grupo principal si a este grupo sólo pertenecía él), pero
pueden usarse distintas opciones para borrar el directorio personal
(<code class="docutils literal notranslate"><span class="pre">--remove-home</span></code>) o todos los archivos del sistema que le pertenecen
(<code class="docutils literal notranslate"><span class="pre">--remove-all-files</span></code>):</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>deluser<span class="w"> </span>--remove-home<span class="w"> </span>nuevo
</pre></div>
</div>
<p>También es posible hacer copia de seguridad de los archivos antes de proceder
al borrado. Consúltese la página del manual.</p>
<p>Del mismo modo que <strong class="command">adduser</strong> permite añadir un usuario a un grupo,
deluser permite borrarlo, si se usa:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>deluser<span class="w"> </span>nuevo<span class="w"> </span>audio
</pre></div>
</div>
<p>Borra el usuario <em>nuevo</em> del grupo <em>audio</em>.</p>
<div class="admonition note">
<p class="admonition-title">Nota</p>
<p>Cuando se borra un usuario, si quedan en el sistema archivos que le
pertenecían estos seguirán teniendo como usuario propietario un usuario
con el <abbr title="User IDentifier">UID</abbr> que tenía el usuario que se borró. Si comprobamos el
propietario (con <a class="reference internal" href="../02.informacion/03.ficheros.html#stat"><span class="std std-ref">stat</span></a> o <a class="reference internal" href="../02.informacion/03.ficheros.html#ls"><span class="std std-ref">ls -l</span></a>) veremos que aparece directamente
el <abbr title="User IDentifier">UID</abbr> y no el nombre de usuario ya que al haberlo borrado el sistema no
puede obtener ningún usuario con ese <abbr title="User IDentifier">UID</abbr>. Por supuesto, si creáramos un
nuevo usuario forzando que su <abbr title="User IDentifier">UID</abbr> fuera el del borrado, todos los
archivos pasarían a ser de su propiedad.</p>
</div>
</dd>
</dl>
<span id="passwd"></span><dl id="index-11">
<dt><em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/passwd">passwd</a></em></dt><dd><p>Permite cambiar la contraseña de usuario de modo interactivo. Su sintaxis
es:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="go">passwd [opciones] [&lt;nombre&gt;]</span>
</pre></div>
</div>
<p>Posee diversas opciones que permiten a <strong class="command">passwd</strong> hacer algo más que
cambiar contraseñas (bloquear o desbloquear el usuario, hacer que expire la
contraseña inmediatamente, etc.):</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>passwd<span class="w"> </span>josem
</pre></div>
</div>
<p>Si no se especifica el nombre de usuario, el sistema entenderá que se quiere
operar sobre el usuario que ejecuta el comando. Una opción especialmente
interesante es <kbd class="kbd compound docutils literal notranslate"><kbd class="kbd docutils literal notranslate">-</kbd>-<kbd class="kbd docutils literal notranslate">expire</kbd></kbd> que provoca que se le exige al usuario cambiar
la contraseña la primera vez que accede al sistema.</p>
<div class="admonition note">
<p class="admonition-title">Nota</p>
<p><strong class="command">passwd</strong> siempre pide la contraseña actual antes de pedir la
nueva, excepto si el usuario que lo ejecuta es <em>root</em>.</p>
</div>
<div class="admonition note">
<p class="admonition-title">Nota</p>
<p>Puede configurarse la robustez mínima exigible para la contraseña a través
de <a class="reference internal" href="../../04.servidor/09.autenticacion/index.html#pam"><span class="std std-ref">PAM</span></a>.</p>
</div>
</dd>
</dl>
<span id="chpasswd"></span><dl id="index-12">
<dt><em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/chpasswd">chpasswd</a></em></dt><dd><p>Permite cambiar contraseñas de usuario de manera no interactiva, lo cual es
muy útil cuando se escriben <em>scripts</em>. El comando admite por la entrada
estándar líneas de la forma:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="go">usuario:contraseña</span>
</pre></div>
</div>
<p>e irá línea a línea asignando a cada usuario la contraseña proporcionada. Si
lo que se quiere es cambiar la contraseña de un usuario puede hacerse lo
siguiente haciendo uso de una <a class="reference internal" href="../08.redirecciones/index.html#ioredirect"><span class="std std-ref">redirección</span></a>:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span><span class="nb">echo</span><span class="w"> </span><span class="s2">&quot;usuario:contraseña&quot;</span><span class="w"> </span><span class="p">|</span><span class="w"> </span>chpasswd
</pre></div>
</div>
<p>Ahora bien, esto último plantea un problema de seguridad ya que la contraseña
sin cifrar acabará almacenada en el historial de <strong class="program">bash</strong>. Para
evitarlo, podríamos deshabilitar para la sesión el historial redefiniendo la
variable <a class="reference internal" href="../07.avanzada/08.interpretaciones.html#histfile"><span class="std std-ref">HISTFILE</span></a>:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span><span class="nv">HISTFILE</span><span class="o">=</span>/dev/null
</pre></div>
</div>
<p>Esto basta con hacerlo antes de salir de la sesión que es el momento en que los
comandos se almacenan en el archivo del historial (<code class="file docutils literal notranslate"><span class="pre">~/.bash_history</span></code>).</p>
<p>La orden permite también la opción <kbd class="kbd docutils literal notranslate">-e</kbd> que presupone que la contraseña
que se le pasa ya está cifrada. Esto tiene utilidad en algunos casos<a class="footnote-reference brackets" href="#id11" id="id5" role="doc-noteref"><span class="fn-bracket">[</span>5<span class="fn-bracket">]</span></a>:</p>
<ul>
<li><p>Cuando se quiere crear un usuario con contraseña nula, esto es, el usuario
accede escribiendo sólo su nombre de usuario:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp"># </span><span class="nb">echo</span><span class="w"> </span><span class="s2">&quot;usuario:&quot;</span><span class="w"> </span><span class="p">|</span><span class="w"> </span>chpasswd<span class="w"> </span>-e
</pre></div>
</div>
<div class="admonition warning">
<p class="admonition-title">Advertencia</p>
<p>Tenga cuidado, porque no todos los servicios aceptan por
defecto usuarios con contraseña nula.</p>
</div>
</li>
<li><p>Deshabilitar la contraseña, para lo cual se suele sustituir por un
asterisco:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp"># </span><span class="nb">echo</span><span class="w"> </span><span class="s2">&quot;usuario:*&quot;</span><span class="w"> </span><span class="p">|</span><span class="w"> </span>chpasswd<span class="w"> </span>-e
</pre></div>
</div>
</li>
</ul>
</dd>
</dl>
<span id="chfn"></span><dl id="index-13">
<dt><em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/chfn">chfn</a></em></dt><dd><p>Permite cambiar la información GECOS de un usuario. Esta información se
compone de distintos campos y <strong class="command">chfn</strong> nos permite modificarlos por
separado, por lo que tiene una opción distinta para cada campo. Por ejemplo:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp"># </span>chfn<span class="w"> </span>-f<span class="w"> </span><span class="s2">&quot;Usuario plebeyo&quot;</span><span class="w"> </span>usuario
</pre></div>
</div>
<p>permitiría cambiar el nombre completo del usuario <em>usuario</em>.</p>
</dd>
</dl>
<span id="chsh"></span><dl id="index-14">
<dt><em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/chsh">chsh</a></em></dt><dd><p>Permite cambiar la <em>shell</em> del usuario. Un usuario puede cambiar únicamente
su propia <em>shell</em>:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>chsh<span class="w"> </span>-s<span class="w"> </span>/bin/dash
</pre></div>
</div>
<p>mientras que el administrador puede cambiar la <em>shell</em> a
cualquier usuario:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp"># </span>chsh<span class="w"> </span>-s<span class="w"> </span>/bin/dash<span class="w"> </span>usuario
</pre></div>
</div>
</dd>
</dl>
<span id="usermod"></span><dl id="index-15">
<dt><em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/usermod">usermod</a></em></dt><dd><p>Permite modificar los datos de un usuario ya creado. Es el compañero de
<em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/useradd">useradd</a></em> y <em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/userdel">userdel</a></em>, pero en este caso si lo usaremos al
no existir alternativa.</p>
<p>Se puede hacer casi cualquier cosa: bloquear o desbloquear usuarios (lo cual
también es posible a través de <a class="reference internal" href="#passwd">passwd</a>), modificar la directorio personal,
cambiar el nombre de usuario o el grupo principal, etc. Todo está en su
página de manual. Algunos usos interesantes son:</p>
<ul>
<li><p>Cambia el nombre de usuario, pero también el directorio personal
moviendo los archivos que hubiera dentro del antiguo directorio:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>usermod<span class="w"> </span>-l<span class="w"> </span>otro<span class="w"> </span>-md<span class="w"> </span>/home/otro<span class="w"> </span>nuevo
</pre></div>
</div>
</li>
<li><p>Añade el usuario a dos grupos más (<em>audio</em> y <em>video</em>):</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>usermod<span class="w"> </span>-aG<span class="w"> </span>audio,video<span class="w"> </span>nuevo
</pre></div>
</div>
<p>Obsérvese que se incluye la opción <code class="docutils literal notranslate"><span class="pre">-a</span></code>, porque en caso contrario el
usuario nuevo sólo pasará a pertenecer a estos dos grupos, eliminándose
su pertenencia a los grupos en los que ya estaba (excepto su grupo
principal, claro).</p>
</li>
<li><p>El usuario dejará de poder iniciar sesiones interactivas:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>usermod<span class="w"> </span>-s<span class="w"> </span>/usr/sbin/nologin<span class="w"> </span>nuevo
</pre></div>
</div>
</li>
</ul>
</dd>
</dl>
<span id="groupmod"></span><dl id="index-16">
<dt><em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/groupmod">groupmod</a></em></dt><dd><p>Es a los grupos lo que <a class="reference internal" href="#usermod"><span class="std std-ref">usermod</span></a> a los usuarios. Algunos
usos útiles son cambiar el nombre del grupo:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp"># </span>groupmod<span class="w"> </span>-n<span class="w"> </span>nuevo_nombre<span class="w"> </span>antiguo_nombre
</pre></div>
</div>
<p>o definir cuáles son sus miembros:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp"># </span>groupmod<span class="w"> </span>-U<span class="w"> </span>usu1,usu2,usu3<span class="w"> </span>grupo
</pre></div>
</div>
<p>Esta orden define la lista completa de miembros, por lo que si el grupo tenía
otros miembros que no se incluyen, dejarán de serlo. Si lo que se quiere es
añadir nuevos miembros, entonces puede añadirse la opción <kbd class="kbd docutils literal notranslate">-a</kbd>:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp"># </span>groupmod<span class="w"> </span>-aU<span class="w"> </span>usu1,usu2,usu3<span class="w"> </span>grupo
</pre></div>
</div>
</dd>
</dl>
<span id="chage"></span><dl id="index-17">
<dt><em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/chage">chage</a></em></dt><dd><p>Ya se ha dejado escrito más arriba que las contraseñas se escriben en un
archivo
aparte llamado <code class="file docutils literal notranslate"><span class="pre">/etc/shadow</span></code>. Esto permite no sólo impedir el acceso a
los usuarios, sino añadir campos adicionales que informen sobre la política
de contraseñas: máximo tiempo de vigencia de la contraseña, obligatoriedad de
cambiarla en el siguiente acceso, etc.</p>
<div class="admonition seealso">
<p class="admonition-title">Ver también</p>
<p>Échele un ojo a la página de manual de <em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/shadow(5)">shadow(5)</a></em>.</p>
</div>
<p><strong class="command">chage</strong> es la orden que nos permite modificar de modo sencillo los
campos de <code class="file docutils literal notranslate"><span class="pre">/etc/shadow</span></code> a fin de alterar la política de contraseñas
de un usuario. Por tanto, es a las contraseñas lo que la orden a
<strong class="command">usermod</strong> a la información contenida en <code class="file docutils literal notranslate"><span class="pre">/etc/passwd</span></code></p>
<div class="admonition note">
<p class="admonition-title">Nota</p>
<p><strong class="command">chage</strong> permite cambiar todo lo referente a la contraseña,
excepto la contraseña misma, para lo cual hay que recurrir a
<strong class="command">chpasswd</strong> o <strong class="command">usermod</strong>. Tampoco sirve para definir la
complejidad de la contraseña, puesto que ello no se codifica en
<code class="file docutils literal notranslate"><span class="pre">/etc/shadow</span></code>.</p>
</div>
<p>Algunas operaciones útiles son:</p>
<ul>
<li><p>Comprobar la política de contraseñas (la propia, excepto <em>root</em> que puede
consultar todas):</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>chage<span class="w"> </span>-l<span class="w"> </span>usuario
</pre></div>
</div>
</li>
<li><p>Forzar el cambio de contraseña en el próximo ingreso:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp"># </span>chage<span class="w"> </span>-d0<span class="w"> </span>usuario
</pre></div>
</div>
</li>
<li><p>Establecer la vigencia de la contraseña (en días):</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp"># </span>chage<span class="w"> </span>-M30<span class="w"> </span>usuario
</pre></div>
</div>
<p>Pasados estos días (que se cuentan a partir del último cambio de
contraseña), se obligará al usuario a cambiar la contraseña antes de poder
acceder a la cuenta.</p>
</li>
<li><p>Establecer con cuántos días de antelación se empezará a avisar de que la
contraseñá está próxima a caducar:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp"># </span>chage<span class="w"> </span>-W5<span class="w"> </span>usuario
</pre></div>
</div>
</li>
<li><p>Establecer el límite de días que una cuenta con la contraseña caducada
permanecerá activa:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp"># </span>chage<span class="w"> </span>-l15<span class="w"> </span>usuario
</pre></div>
</div>
<p>Pasado este tiempo, la única forma de recuperar la cuenta será avisar al
administrador para que la desbloquee.</p>
</li>
</ul>
<div class="admonition note">
<p class="admonition-title">Nota</p>
<p><strong class="command">chage</strong> permite cambiar los valores para usuarios ya
existentes. Si nuestra intención, en cambio, fuera alterar los valores
predeterminados para que con ellos se creen los nuevos usuarios, entonces
deberemos editar el archivo <code class="file docutils literal notranslate"><span class="pre">/etc/login.defs</span></code> y en particular las
líneas:</p>
<div class="highlight-nginx notranslate"><div class="highlight"><pre><span></span><span class="k">PASS_MAX_DAYS</span><span class="w"> </span><span class="mi">30</span>
<span class="s">PASS_MIN_DAYS</span><span class="w"> </span><span class="mi">2</span>
<span class="s">PASS_WARN_AGE</span><span class="w"> </span><span class="mi">7</span>
</pre></div>
</div>
</div>
</dd>
</dl>
<span id="newgrp"></span><dl id="index-18">
<dt><em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/newgrp">newgrp</a></em></dt><dd><p>Cambia el grupo perdeterminado del usuario durante la sesión actual. Por
ejemplo, si <em>nuevo</em> ya pertenece al grupo <em>audio</em>:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>whoami
<span class="go">nuevo</span>
<span class="gp">$ </span>groups
<span class="go">nuevo audio video plugdev</span>
<span class="gp">$ </span>id<span class="w"> </span>-ng
<span class="go">nuevo</span>
<span class="gp">$ </span>newgrp<span class="w"> </span>audio
<span class="gp">$ </span>id<span class="w"> </span>-ng
<span class="go">audio</span>
</pre></div>
</div>
<p>Como se ve ahora el grupo principal de <em>nuevo</em> es <em>audio</em> y así será mientras
que no abandone la sesión abierta. En principio, no parece tener demasiada
utilidad en la medida en que los permisos que obtendrá el usuario serán los
mismos que ya tenía, puesto que ya pertenecía a <em>audio</em>. Sin embargo, si al
usuario se le incluyó en el grupo <em>audio</em> después de que abriera la sesión,
entonces para esa sesión el usuario no pertenece al grupo y debería abandonar
la sesión y volver a entrar para que recargue su membresía y pueda gozar de
los privilegios de los que goza en el nuevo grupo. Usando, sin embargo,
<strong class="command">newgrp</strong> el usuario redefinirá temporalmente <em>audio</em> como su grupo
principal y entonces sí podrá gozar de sus privilegios sin necesidad de
reingresar.</p>
<p>Si el usuario no pertenece al grupo, aún podrá redefinirlo temporalmente como
su grupo principal, pero sólo en caso de que para el grupo se haya definido
una contraseña (que deberá introducir) y ya se ha discutido que esto no es
algo demasiado seguro.</p>
</dd>
</dl>
</section>
<section id="cambio-de-identidad">
<h2><span class="section-number">2.3.1.3. </span>Cambio de identidad<a class="headerlink" href="#cambio-de-identidad" title="Link to this heading">¶</a></h2>
<p>En ocasiones, un usuario puede haber accedido con una determinada identidad al
sistema y requerir tener otra identidad para realizar una tarea determinada. Por
ejemplo, un usuario que se encuentra utilizando el sistema, pero que se ve en
la necesidad de convertirse en <em>root</em>, para realizar una tarea de
administración.</p>
<span id="su"></span><dl id="index-19">
<dt><em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/su">su</a></em></dt><dd><p>Permite identificarse con otra identidad a un usuario ya identificado en el
sistema, sin necesidad de salir y acceder a esta nueva identidad a través
del proceso de <em>login</em>:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>whoami
<span class="go">usuario</span>
<span class="gp">$ </span>su<span class="w"> </span>-<span class="w"> </span>otro
<span class="go">Contraseña:</span>
<span class="gp">$ </span>whoami
<span class="go">otro</span>
</pre></div>
</div>
<p>Mediante este comando el usuario actual podría convertirse en el usuario
<em>otro</em> si es que conoce la contraseña de este último. La opción <code class="docutils literal notranslate"><span class="pre">-</span></code> hace
que la conversión al nuevo usuario sea lo más parecida posible a como sería
si se hiciera mediante <em>login</em>.</p>
<p>La opción <code class="docutils literal notranslate"><span class="pre">-c</span></code> permite indicar el comando que se quiere ejecutar al
convertirse en el nuevo usuario. Al acabarse de ejecutar el comando, se
vuelve al usuario original:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>whoami
<span class="go">usuario</span>
<span class="gp">$ </span>su<span class="w"> </span>-<span class="w"> </span>otro<span class="w"> </span>-c<span class="w"> </span><span class="s2">&quot;whoami&quot;</span>
<span class="go">Contraseña:</span>
<span class="go">otro</span>
<span class="gp">$ </span>whoami
<span class="go">usuario</span>
</pre></div>
</div>
<p>Cuando no se especifica el nombre del nuevo usuario, se sobrentiende que es
<em>root</em>:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>su<span class="w"> </span>-
<span class="go">Contraseña:</span>
<span class="gp"># </span>whoami
<span class="go">root</span>
</pre></div>
</div>
<div class="admonition note">
<p class="admonition-title">Nota</p>
<p>Como <strong class="command">logname</strong> devuelve el nombre del usuario con que se ingresó
en el sistema, si se cambia con <strong class="command">su</strong> de usuario, seguirá
devolviendo el nombre original del usuario:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>whoami
<span class="go">usuario</span>
<span class="gp">$ </span>logname
<span class="go">usuario</span>
<span class="gp">$ </span>su<span class="w"> </span>-
<span class="go">Contraseña:</span>
<span class="gp"># </span>whoami
<span class="go">root</span>
<span class="gp"># </span>logname
<span class="go">usuario</span>
</pre></div>
</div>
</div>
<div class="admonition note">
<p class="admonition-title">Nota</p>
<p><strong class="command">su</strong> exige conocer la contraseña del usuario del que se quieren
obtener los privilegios. Además, nos convierte en tal usuario con lo que
se asumirán todos sus permisos. Existe otra manera de conseguir privilegios
de otro usuario que evita estos dos inconvenientes: <a class="reference internal" href="../09.admbasica/10.priv/01.sudo.html#sudo"><span class="std std-ref">sudo</span></a>.</p>
</div>
<div class="admonition warning">
<p class="admonition-title">Advertencia</p>
<p>En algunas distribuciones (p.e. <a class="reference external" href="https://www.ubuntu.com">Ubuntu</a>), el administrador carece de
contraseña, por lo que es imposible escalar privilegios con <strong class="command">su</strong>
y debe usarse <a class="reference internal" href="../09.admbasica/10.priv/01.sudo.html#sudo"><span class="std std-ref">sudo</span></a>. Por supuesto, basta con asignar una
contraseña a <em>root</em> para que <strong class="command">su</strong> pueda usarse como método para
escalar privilegios.</p>
</div>
<div class="admonition note">
<p class="admonition-title">Nota</p>
<p>En algunas distribuciones sólo le es permitido escalar privilegios
mediante <strong class="command">su</strong> al usuario que pertenece al grupo <em>wheel</em>. Esto se
logra manipulando <a class="reference internal" href="../../04.servidor/09.autenticacion/index.html#pam"><span class="std std-ref">el proceso de autenticación</span></a>; en particular,
usando el módulo <a class="reference internal" href="../../04.servidor/09.autenticacion/pam_modules/13.pam_wheel.html#pam-wheel"><span class="std std-ref">pam_wheel</span></a> en el proceso de autenticación de
<strong class="command">su</strong>. <em>Debian</em> contiene la línea, pero la tiene comentada.</p>
</div>
</dd>
</dl>
<span id="runuser"></span><dl id="index-20">
<dt><em class="manpage"><a class="manpage reference external" href="https://manpages.debian.org/runuser">runuser</a></em></dt><dd><p>Es una orden propia del administrador para que pueda ejecutar órdenes
puntuales como un usuario distinto<a class="footnote-reference brackets" href="#id12" id="id6" role="doc-noteref"><span class="fn-bracket">[</span>6<span class="fn-bracket">]</span></a>. Su uso más habitual es el
siguiente:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp"># </span>runuser<span class="w"> </span>-u<span class="w"> </span>usuario<span class="w"> </span>--<span class="w"> </span>whoami
<span class="go">usuario</span>
</pre></div>
</div>
<p>es decir, indicar con la opción <kbd class="kbd docutils literal notranslate">-u</kbd> cuál es el usuario en nombre del
cual se quiere ejcutar la orden, utilizar <kbd class="kbd docutils literal notranslate">--</kbd> para indicar que lo que
sigue es la orden y, finalmente, escribir la orden con todos sus argumentos.
En el ejemplo, hemos usado <a class="reference internal" href="#whoami"><span class="std std-ref">whoami</span></a> que no requiere de ninguno.</p>
</dd>
</dl>
</section>
<section id="ejercicios-sobre-consulta-y-gestion-de-usuarios">
<span id="ej-usu"></span><h2><span class="section-number">2.3.1.4. </span>Ejercicios sobre consulta y gestión de usuarios<a class="headerlink" href="#ejercicios-sobre-consulta-y-gestion-de-usuarios" title="Link to this heading">¶</a></h2>
<div class="admonition note">
<p class="admonition-title">Nota</p>
<p>Especifique mediante el uso del prompt adecuado
(<strong>#</strong> o <strong>$</strong>) si la operación requiere permisos de
administración o no.</p>
</div>
<ol class="arabic simple">
<li><p>Comprobar si existe el usuario <em>pepe</em>.</p></li>
<li><p>Crear el usuario <em>pepe</em> con directorio personal
<code class="file docutils literal notranslate"><span class="pre">/home/casita_de_pepe</span></code>.</p></li>
<li><p>Deshabilitar a <em>pepe</em> para que no pueda ingresar en el sistema.</p></li>
<li><p>Crear el usuario <em>bartolo</em> con <abbr title="User IDentifier">UID</abbr> 2000 y cuyo grupo principal sea
el mismo que el de <em>pepe</em>.</p></li>
<li><p>Habilitar el usuario <em>pepe</em>.</p></li>
<li><p>Cambiar el nombre de usuario <em>pepe</em> a <em>donjose</em>. Tambien se debe
cambiar su directorio personal para que sea <code class="file docutils literal notranslate"><span class="pre">/home/donjose</span></code>.</p></li>
<li><p>Crear un usuario <em>maria</em>, pero no crearle directorio personal.</p></li>
<li><p>Añadir el usuario <em>donjose</em> a los grupos <em>floppy</em> y <em>audio</em>.</p></li>
<li><p>Borrar el usuario <em>maria</em>.</p></li>
<li><p>Deshabilitar a <em>bartolo</em> cambiándole la <em>shell</em> predeterminada.</p></li>
</ol>
<p class="rubric">Notas al pie</p>
<aside class="footnote-list brackets">
<aside class="footnote brackets" id="id7" role="doc-footnote">
<span class="label"><span class="fn-bracket">[</span><a role="doc-backlink" href="#id1">1</a><span class="fn-bracket">]</span></span>
<p>Pueden existir también usuarios de red, definidos en algún servidor de
usuarios, pero es materia para <a class="reference internal" href="../../06.infraestructura/05.directorio/index.html#serv-directorio"><span class="std std-ref">otro epígrafe posterior</span></a>.</p>
</aside>
<aside class="footnote brackets" id="id8" role="doc-footnote">
<span class="label"><span class="fn-bracket">[</span><a role="doc-backlink" href="#id2">2</a><span class="fn-bracket">]</span></span>
<p>Y, en realidad, no tan modernos, ya que la innovación apareció a mediados
de los ochenta. El problema de almacenar también en <code class="file docutils literal notranslate"><span class="pre">/etc/passwd</span></code> la
contraseña es que a este archivo todos los usuarios tienen acceso y, por tanto,
todos pueden las contraseñas criptográficamente <em>resumidas</em> del resto, lo
cual es una vulnerabilidad ya que se presta a ataques de fuerza bruta.</p>
</aside>
<aside class="footnote brackets" id="id9" role="doc-footnote">
<span class="label"><span class="fn-bracket">[</span><a role="doc-backlink" href="#id3">3</a><span class="fn-bracket">]</span></span>
<p><strong class="command">mkpasswd</strong> pertenece al paquete <a class="reference external" href="https://packages.debian.org/stable/whois">whois</a>, que puede no estar
instalado en el sistema. También pueden generarse con <a class="reference internal" href="../../98.apendice/01.cryto/02.algo.html#openssl"><span class="std std-ref">openssl</span></a>, que estará instalado casi con total seguridad en el sistema, pero
no soporta todos los  algoritmos posibles:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp">$ </span>openssl<span class="w"> </span>passwd<span class="w"> </span>-6<span class="w"> </span>-salt<span class="w"> </span>feeCGVjY<span class="w"> </span>usuario
<span class="gp">$</span><span class="m">6</span><span class="nv">$feeCGVjY$m4drjYETO7DNffE</span>/8AwmTvRnTj8qmSMy8AhMq1jaNf3ZonyAFPVc64SsY/iWTR3LxtXKnD2hfavS1FXwelAyq1
</pre></div>
</div>
</aside>
<aside class="footnote brackets" id="id10" role="doc-footnote">
<span class="label"><span class="fn-bracket">[</span><a role="doc-backlink" href="#id4">4</a><span class="fn-bracket">]</span></span>
<p>No deben, de ningún modo, editarse los archivos a través del editor
normal, puesto que mientras se realiza la edición, podría darse el caso de
que otro usuario intentara modificarlo a través de una de las herramientas
específicas que existen. Si se tiene la mala idea de tocar a mano, debe
hacerse a través del <span class="target" id="index-21"></span>commando <strong class="command">vipw</strong>, que bloquea el
archivo para que ningún otro programa lo toque en tanto se completa la
modificación.</p>
</aside>
<aside class="footnote brackets" id="id11" role="doc-footnote">
<span class="label"><span class="fn-bracket">[</span><a role="doc-backlink" href="#id5">5</a><span class="fn-bracket">]</span></span>
<p>Aunque en estos casos es mejor usar la opción <a class="reference internal" href="#usermod"><span class="std std-ref">usermod</span></a>
con la opción <kbd class="kbd docutils literal notranslate">-p</kbd> y nos ahorramos la tubería. Por ejemplo:</p>
<div class="highlight-console notranslate"><div class="highlight"><pre><span></span><span class="gp"># </span>usermod<span class="w"> </span>-p<span class="w"> </span><span class="s2">&quot;&quot;</span><span class="w"> </span>usuario
</pre></div>
</div>
</aside>
<aside class="footnote brackets" id="id12" role="doc-footnote">
<span class="label"><span class="fn-bracket">[</span><a role="doc-backlink" href="#id6">6</a><span class="fn-bracket">]</span></span>
<p>Por tanto, podríamos emular su propósito con la opción <kbd class="kbd docutils literal notranslate">-c</kbd> de
<a class="reference internal" href="#su"><span class="std std-ref">su</span></a>.</p>
</aside>
</aside>
</section>
</section>


            <div class="clearer"></div>
          </div>
        </div>
      </div>
      <div class="sphinxsidebar" role="navigation" aria-label="main navigation">
        <div class="sphinxsidebarwrapper">
  <div>
    <h3><a href="../../index.html">Tabla de contenido</a></h3>
    <ul>
<li><a class="reference internal" href="#">2.3.1. Gestión de usuarios</a><ul>
<li><a class="reference internal" href="#consulta">2.3.1.1. Consulta</a></li>
<li><a class="reference internal" href="#manipulacion">2.3.1.2. Manipulación</a></li>
<li><a class="reference internal" href="#cambio-de-identidad">2.3.1.3. Cambio de identidad</a></li>
<li><a class="reference internal" href="#ejercicios-sobre-consulta-y-gestion-de-usuarios">2.3.1.4. Ejercicios sobre consulta y gestión de usuarios</a></li>
</ul>
</li>
</ul>

  </div>
  <div>
    <h4>Tema anterior</h4>
    <p class="topless"><a href="index.html"
                          title="capítulo anterior"><span class="section-number">2.3. </span>Seguridad del sistema</a></p>
  </div>
  <div>
    <h4>Próximo tema</h4>
    <p class="topless"><a href="05b.permisos.html"
                          title="próximo capítulo"><span class="section-number">2.3.2. </span>Permisos</a></p>
  </div>
  <div role="note" aria-label="source link">
    <h3>Esta página</h3>
    <ul class="this-page-menu">
      <li><a href="../../_sources/02.conbas/05.seguridad/05a.usuarios.rst.txt"
            rel="nofollow">Mostrar el código</a></li>
    </ul>
   </div>
<div id="searchbox" style="display: none" role="search">
  <h3 id="searchlabel">Búsqueda rápida</h3>
    <div class="searchformwrapper">
    <form class="search" action="../../search.html" method="get">
      <input type="text" name="q" aria-labelledby="searchlabel" autocomplete="off" autocorrect="off" autocapitalize="off" spellcheck="false"/>
      <input type="submit" value="Ir a" />
    </form>
    </div>
</div>
<script>document.getElementById('searchbox').style.display = "block"</script>
        </div>
      </div>
      <div class="clearer"></div>
    </div>
    <div class="related" role="navigation" aria-label="related navigation">
      <h3>Navegación</h3>
      <ul>
        <li class="right" style="margin-right: 10px">
          <a href="../../genindex.html" title="Índice General"
             >índice</a></li>
        <li class="right" >
          <a href="05b.permisos.html" title="2.3.2. Permisos"
             >siguiente</a> |</li>
        <li class="right" >
          <a href="index.html" title="2.3. Seguridad del sistema"
             >anterior</a> |</li>
        <li class="nav-item nav-item-0"><a href="../../index.html">documentación de Linuxnomicón - rolling</a> &#187;</li>
          <li class="nav-item nav-item-1"><a href="../index.html" ><span class="section-number">2. </span>Conceptos básicos</a> &#187;</li>
          <li class="nav-item nav-item-2"><a href="index.html" ><span class="section-number">2.3. </span>Seguridad del sistema</a> &#187;</li>
        <li class="nav-item nav-item-this"><a href=""><span class="section-number">2.3.1. </span>Gestión de usuarios</a></li> 
      </ul>
    </div>
    <div class="footer" role="contentinfo">
    &#169; Copyright CC BY 4.0, 2016-2024, José Miguel Sánchez Alés.
      Creado usando <a href="https://www.sphinx-doc.org/">Sphinx</a> 7.2.6.
    </div>
  </body>
</html>
