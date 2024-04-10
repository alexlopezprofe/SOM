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

Si cambiamos los permisos a un directorio y deseamos que estos permisos tengan efecto sobre todos sus subdirectorios y archivos sólo deberemos añadir la opción `–R`. 

```bash
$ chmod a=rw DIRECTORIO –R
```

# Gestión de usuarios

En los sistemas UNIX, existen unos archivos que constituyen la base de datos de los usuarios locales. Todos los archivos se caracterizan porque cada línea define una entidad distinta y porque los campos que constituyen cada entidad se separan por el carácter dos puntos '''(":")```.

## **/etc/passwd** 

Mantiene la información principal de cada cuenta: nombre de usuario, UID, GID, login shell, directorio home, contraseña (en sistemas antiguos), ...
 
 Ejemplo de líneas de /etc/passwd:

```
root:x:0:0:root:/root:/bin/bash
pepe:x:1002:1002:Pepe Pótamo,123,981234321,:/home/pepe:/bin/bash
```

donde se indican (si aparecen :: seguidos, el campo está vacío):

* pepe: identificación de usuario en el sistema, que deberían tener las siguientes características:
	*únicos en toda la organización (no sólo en la máquina local) preferiblemente corto, en minúsculas y sin caracteres acentuados (para evitar problemas)
	* fácil de recordar
	* de formato fijo para todos los usuarios (p.e. nombre+apellido)
* x: contraseña encriptada
	* si aparece una x la contraseña está en el fichero /etc/shadow
* 1002: UID número identificador del usuario
	* para usuarios normales, número entre 1000 y 32767 (o 65535 en sistemas actuales)
	* números por debajo de 1000 para usuarios especiales del sistema (root usualmente número 0)
	* el UID para un usuario debería ser único, y el mismo para todas las máquinas
* se debe evitar reutilizar un UID, para evitar problemas de pertenencia de archivos
* 1002: GID código del grupo principal al que pertenece el usuario
* Pepe Pótamo,123,...: información GECOS
	* cualquier cosa, usualmente el nombre completo del usuario y información adicional (n. de despacho, teléfono, etc.)
* /home/pepe: directorio personal del usuario
* /bin/bash: shell interactivo que utilizará el usuario

## Fichero /etc/shadow

En sistemas actuales, fichero sin permiso de lectura que guarda las contraseñas encriptadas de los usuarios y campos adicionales con información sobre ellas (caducidad, etc). En realidad, las contraseñas no están propiamente cifradas, sino que se les aplica una función de hash. Contiene para cada usuario la contraseña encriptada y otros campos separados por :

```
pepe:$1$.QKDPc5E$SWlkjRWexrXYgc98F.:12825:0:90:5:30:13096:
```

* día, contado como número de días desde el 1/1/1970 (también conocido como epoch), en que la contraseña se cambió por última vez
	* si vale 0 se fuerza a que el usuario cambia su contraseña la primera vez que se conecta
* número de días antes de que pueda ser cambiada
* número de días de validez de la contraseña
* días en que se avisa al usuario de que la contraseña va a caducar
* días, una vez expirada, en que se deshabilitará la cuenta
* día, desde el 1/1/1970, en que la cuenta se inhabilitará
* si no aparece nada, la cuenta no se inhabilita nunca
* un campo reservado

## Fichero /etc/group
Información sobre los grupos de usuarios

```
users:x:100:pepe,elena
```

donde tenemos:
* nombre del grupo
* contraseña del grupo (no suele usarse)
	* si x, se guarda en el fichero ```/etc/gshadow```
		* grupo:contraseña:administradores:miembros
* GID identificador numérico del grupo
* lista de usuarios que pertenecen al grupo

## Comandos útiles para la gestión de usuarios:

* ```sudo adduser nombredeusuario```
Comando utilizado para añadir un usuario. Nos solicitará contraseña y confirmación de contraseña, nombre
completo, número de despacho, número de teléfono del trabajo, número de teléfono de casa y otros aspectos. 

* ```sudo useradd nombredeusuario```
Comando utilizado para añadir un usuario de forma simplificada y rápida. No nos solicita ningún dato al respecto de dicho usuario. Debemos ejecutar la orden passwd nombreusuario para asignarle contraseña ya que
por defecto vendría deshabilitada. Además, no generaría la carpeta vinculada al usuario (si miramos en /home no estaría creada la carpeta /home/prueba2).

* ```sudo usermod nombredeusuario```
* 
nos permite modificar los datos relativos a un determinado usuario. Algunos de los modificadores más utilizados serían:

* sudo ```usermod -d /home/pepe –m nombreusuario``` cambiaría el directorio asignado dicho usuario y además con el –m mandaría toda la información de su actual directorio de usuario al nuevo. Por ejemplo, imagina que

ahora quiero que el usuario prueba1 tenga toda su información en /home/newprueba1.
Así se vería ahora en el archivo de configuración de usuarios /etc/passwd.
Aparte de esta modificación se habrá modificado el nombre del directorio /home/prueba1 por el de
/home/newprueba1.
• sudo usermod -g mtx2122 nombreusuario cambiaría el grupo de referencia de todos los archivos y carpetas
del usuario por el de mtx2122. Por ejemplo, imagina que ahora quiero que el grupo inicial (o de referencia)
del usuario prueba1 sea mtx2122.
IES MUTXAMEL
Carrer Mondúber s/n 03110
MUTXAMEL (ALACANT)
03014551@gva.es
Tel: 965936475|Fax: 965936476
portal.edu.gva.es/.iesmutxamel
• sudo usermod -l nombrenuevo nombreantiguo cambiaría el nombre de usuario. Debemos tener cuidado
porque, aunque ha cambiado el nombre el directorio vinculado sería el mismo que tenía anteriormente.
Así se vería en el archivo de configuración de usuarios /etc/passwd
• sudo usermod -a -G nuevogrupo nombreusuario. Añade al usuario a un grupo que está creado en el sistema.
Con el comando id podríamos ver que nuevop1 pertenece al grupo aprobados.
• sudo usermod -e 2022-02-28 nombreusuario . Establece una fecha de expiración de la cuenta. Según el
ejemplo, la cuenta del usuario expirará el 28 de febrero. Podemos consultar la fecha en /etc/shadow (apartado
desactiva, días transcurridos desde el 1/1/1970 hasta la desactivación de la cuenta). Si dejamos la fecha en
blanco Recuerda que una vez bloqueado un usuario, para poder volver a activarlo deberemos modificar su
fecha de expiración y reiniciar su contraseña.
• sudo usermod -L nombreusuario . Bloquea la contraseña de un usuario
• sudo usermod -U nombreusuario. Permite desbloquear la contraseña que está bloqueada.
sudo passwd nombredeusuario
Permite asignar una contraseña a un determinado usuario. Podemos aprovechar para utilizar las opciones –x
para establecer el plazo de caducidad de la contraseña, -w para establecer el plazo de aviso al usuario, y con
–n establece el plazo de la antelación sobre la fecha de finalización en la que se puede cambiar la contraseña.
• sudo passwd -S nombreusuario. Permite ver el estado de la cuenta de un determinado usuario.
• sudo passwd -d nombreusuario. Borra la contraseña de un usuario. Con la opción –status ó -S podemos ver la
NP que indica que no tiene password.
• sudo passwd -l nombreusuario. Bloquea una contraseña
sudo userdel nombredeusuario
Permite eliminar un determinado usuario. Realmente borra de /etc/passwd, /etc/shadow y /etc/group todas las
referencias a dicho usuario. Con la opción –r también borrará el directorio personal vinculado a dicho usuario.



https://sio2sio2.github.io/doc-linux/02.conbas/05.seguridad/05a.usuarios.html#consulta
