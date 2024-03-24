# Unidad 6. Introducción a Linux

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
+  **/etc**: Almacena archivos de configuración del sistema. Aquí se encuentran archivos de configuración para diversos servicios y aplicaciones.
+  **/var**: Contiene datos variables, como archivos de registro (logs), correos electrónicos y otros datos que pueden cambiar con el tiempo.
+  **/bin y /usr/bin**: Contienen programas ejecutables (binarios) accesibles para todos los usuarios del sistema.
+  **/sbin y /usr/sbin**: Almacenan programas ejecutables de administración del sistema, generalmente reservados para usuarios con privilegios de administrador (root).
+  **/tmp**: Es un directorio temporal utilizado por aplicaciones para almacenar archivos temporales. El contenido de esta carpeta se borra cuando se reinicia el sistema.


# Indicador de tipo de ficheros

El comando `ls` Muestra el listado del directorio actual; si le añadimos la opcion `-l`, `ls -l` nos permite listar la información de tipo de archivo, de permisos, usuario, grupo, tamaño, fecha de modificación entre otras características más, del directorio actual.

```bash
ls -l 
> 
```

![image](https://github.com/alexlopezprofe/SOM/assets/148449360/4800ce34-370a-438e-804a-267d7d6817e4)

![image](https://github.com/alexlopezprofe/SOM/assets/148449360/13979e26-3499-4f2b-bf62-8565b4d5919e)

## Tipos de ficheros:

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



# Permisos de archivos

En Linux, los permisos de archivos y carpetas son un componente importante para gestionar la seguridad y el acceso a la información almacenada en el sistema de archivos de tu equipo. Estos permisos definen quién puede leer, escribir o ejecutar un archivo o directorio y desempeñan un papel fundamental en la protección de la integridad del sistema y la privacidad de los datos.

Puede parecer simple, pero todo puede llegar a tener cierta complejidad a la hora de asignar los permisos en Linux. Todos ellos se pueden aplicar de diferentes formas. Tanto en red, con diferentes usuarios en un servidor, como en loca. Donde varios usuarios pueden manejar un mismo PC, con algunos recursos compartidos entre sí.

* **Lectura (r):** Es el primer permiso que podemos encontrarnos. Este nos da la opción de que un usuario pueda ver el contenido al que quiere acceder.
* **Escritura (w):** Nos da la posibilidad de otorgar poder sobre sobre un archivo. De esta forma podrá ser modificado, al igual que un directorio.
* **Ejecución (x):** Permite a los usuarios ejecutar diferentes parámetros dentro del equipo.
* **Sin permisos (-):** Nos indica que el usuario no tiene ningún tipo de permiso sobre el recurso de red o contenido compartido.

# Niveles de permisos

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


# Cambio de permisos

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


## Ejemplos notación simbólica:

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

## Ejemplos notación octal:

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

## Recursividad

Si cambiamos los permisos a un directorio y deseamos que estos permisos tengan efecto sobre todos sus subdirectorios y archivos
sólo deberemos añadir la opción `–R`. 

```bash
$ chmod a=rw DIRECTORIO –R
```

