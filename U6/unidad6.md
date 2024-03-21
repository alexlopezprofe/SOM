# Unidad 6. Introducción a Linux

# Permisos

En Linux, los permisos de archivos y carpetas son un componente importante para gestionar la seguridad y el acceso a la información almacenada en el sistema de archivos de tu equipo. Estos permisos definen quién puede leer, escribir o ejecutar un archivo o directorio y desempeñan un papel fundamental en la protección de la integridad del sistema y la privacidad de los datos.

Puede parecer simple, pero todo puede llegar a tener cierta complejidad a la hora de asignar los permisos en Linux. Todos ellos se pueden aplicar de diferentes formas. Tanto en red, con diferentes usuarios en un servidor, como en loca. Donde varios usuarios pueden manejar un mismo PC, con algunos recursos compartidos entre sí.

* **Lectura (r):** Es el primer permiso que podemos encontrarnos. Este nos da la opción de que un usuario pueda ver el contenido al que quiere acceder.
* **Escritura (w):** Nos da la posibilidad de otorgar poder sobre sobre un archivo. De esta forma podrá ser modificado, al igual que un directorio.
* **Ejecución (x):** Permite a los usuarios ejecutar diferentes parámetros dentro del equipo.
* **Sin permisos (-):** Nos indica que el usuario no tiene ningún tipo de permiso sobre el recurso de red o contenido compartido.

# Niveles de permisos

* **Propietario (user - u):** El propietario es el usuario que creó el archivo o directorio. Este tiene el control total sobre los permisos y puede modificarlos según sus necesidades. Los permisos del propietario afectan directamente al usuario que creó el archivo.
*  **Grupo (group - g):** En Linux, los usuarios se organizan en grupos y un archivo o directorio puede pertenecer a uno de estos grupos. Los permisos asignados al grupo afectan a todos los usuarios que forman parte de ese grupo, permitiéndoles acceder y modificar archivos en conjunto.
*  **Otros (others - o):** Este conjunto de permisos se aplica a cualquier usuario que no sea el propietario ni esté en el grupo especificado. Los permisos otorgados o denegados a otros usuarios aseguran que el sistema permanezca protegido contra accesos no autorizados.
*  **Todos (all - a)):** Si se necesita otorgar permisos a todos
  
La combinación de estas tres categorías o niveles y sus respectivos permisos crea un sistema que permite el control sobre quién puede hacer qué con un archivo o directorio. El uso principal de los permisos en Linux es garantizar la seguridad y la privacidad de los datos, al tiempo que permite la colaboración y el acceso necesario para los usuarios autorizados.

![image](https://github.com/alexlopezprofe/SOM/assets/148449360/dc503d31-38d6-4a21-9840-dd27076bb072)

# Comandos
## ¿Cómo sé qué permisos tienen mis ficheros o directorios?

El comando `ls` Muestra el listado del directorio actual; si le añadimos la opcion `-l`, `ls -l` nos permite listar la información de permisos, usuario, grupo, tamaño, fecha de modificación entre otras características más, del directorio actual.

ls -l 
> 
