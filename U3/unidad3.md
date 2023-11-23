# Unidad 3. Introducción a Windows 

# Concepto de virtualización y máquinas virtuales

La **virtualización** es una tecnología que permite la creación de entornos virtuales o simulados dentro de un sistema informático físico. Este concepto se utiliza para optimizar recursos, mejorar la eficiencia y facilitar la administración de sistemas. El objetivo de la virtualización es la creación de **máquinas virtuales** (VM, por sus siglas en inglés).

Las máquinas virtuales son instancias virtuales de sistemas operativos que se ejecutan sobre un equipo **host** o anfitrion. Un **hipervisor**, conocido también como monitor de máquinas virtuales, es un proceso que crea y ejecuta máquinas virtuales. Un hipervisor permite que un ordenador host preste soporte a varias máquinas virtuales invitadas mediante el uso compartido virtual de sus recursos, como la memoria y el procesamiento.

En general, hay dos tipos de hipervisores.

- Los hipervisores de tipo 1, denominados «hipervisores **bare metal**», se ejecutan directamente en el hardware del host.
- Los hipervisores de tipo 2, denominados «alojados», se ejecutan como una capa de software sobre un sistema operativo, como otros programas informáticos. 

Mientras que podemos referirnos a las máquinas virtuales como huéspedes o sistemas invitados (**guest**).

![image](https://github.com/alexlopezprofe/SOM/assets/148449360/00359333-8520-429d-a21d-5b0e2964e305)

# Otros tipos de virtualización

## Emulación

El software de virtualización emula por completo el juego de instrucciones de un hardware que suele ser distinto del anfitrión.

El emulador recibe las instrucciones máquina de la arquitectura emulada y las traduce a las de la arquitectura del anfitrión para ejecutarlas . Una vez obtenida la respuesta, la traduce para el software invitado. Suele emularse, incluso, el funcionamiento del hardware específico de la arquitectura. 

La consecuencia de todo este proceso es una pérdida de rendimiento muy considerable, por lo que no suele utilizarse en entornos de producción. Sin embargo, sí que resultan muy útiles en entornos de desarrollo para plataformas diferentes de la que estemos usando. Un ejemplo de esto es cuando se escriben programas para dispositivos móviles en ordenadores de escritorio.

> Algunos emuladores de Android para Windows son: Android Studio, BlueStacks, LDPlayer, Genymotion, etc.
> 
>También podemos encontrar emuladores de iPhone para Windows o Mac, como Xcode, Xamarin, Appetize.io (basado en la web), etc.
>
>Incluso podemos usar emuladores para volver a disfrutar de juegos para antiguas plataformas. Por ejemplo, para emular una GameBoy podemos usar BGB, GB Enhanced+ o RetroArch en Windows, o Mednafen en GNU/Linux, etc.

## Contenedores

La virtualización a nivel de sistema operativo, también llamada virtualización basada en contenedores, es un método de virtualización en el que, sobre el núcleo del sistema operativo, se ejecuta una capa de virtualización que permite que existan múltiples instancias aisladas de espacios de usuario, en lugar de solo uno.

![image](https://github.com/alexlopezprofe/SOM/assets/148449360/ae961523-5748-4e2f-8c61-780289416f9e)

* **Docker.** Docker es el entorno en tiempo de ejecución de contenedores más popular y ampliamente utilizado. Docker Hub es un gigantesco repositorio público de aplicaciones populares de software en contenedores. Los contenedores en Docker Hub se pueden descargar e implementar al instante en un entorno en tiempo de ejecución de Docker local.

## Virtualización en la nube

Se trata de ofrecer capacidad de cálculo, bases de datos y otros tipos de almacenamiento, aplicaciones y otros recursos, a través de Internet, a cambio de un determinado coste. En el contexto de las máquinas virtuales, esto significa que un proveedor de cloud computing puede ofrecernos sus propios recursos hardware para almacenar nuestras propias máquinas virtuales y acceder a ellas desde cualquier parte del planeta.

![image](https://github.com/alexlopezprofe/SOM/assets/148449360/8165f445-a304-4e11-82a4-0fcf4cfe4f85)

Esto permite olvidarnos de los requisitos que tienen los servidores de virtualización locales, como el mantenimiento, la reparación de averías, refrigeración, gastos de electricidad, seguridad física, etc.

Además dispondremos de flexibilidad a la hora de decidir el equipamiento. Es decir, contratamos la potencia a medida que la necesitamos, pudiendo aumentarla y disminuirla según los requerimientos.

Incluso podemos implementar modelos híbridos, donde una parte de la infraestructura de la empresa se encuentre virtualizada en la nube y otra, normalmente la más crítica, se implemente de forma local, para evitar eventuales problemas de falta de conexión.

**Ventajas:**

- Flexibilidad, porque podemos elegir casi cualquier aspecto de la implementación: sistema operativo, sistema gestor de bases de datos y casi cualquier otro servicio que necesitemos.
- Rentabilidad, porque se paga únicamente por lo que consume.
- Agilidad, porque se reduce el tiempo necesario para que los recursos estén disponibles. En el mundo físico, podríamos tardar semanas en recibir el hardware adecuado e instalarlo y configurarlo correctamente. Usando cloud computing podemos reducirlo a minutos.
- Elasticidad, porque podremos ampliar o reducir los recursos utilizados en función de nuestras necesidades puntuales.
- Seguridad, porque se trata de grandes centros de datos que se encuentran altamente protegidos ante posibles ataques físicos y lógicos.

**Inconvenientes:**

- Coste, porque aunque pagamos únicamente por lo que consumimos, estamos pagando constantemente. Un servidor local se paga una vez y se utiliza de forma indefinida. Es decir, este aspecto puede ser una ventaja o un inconveniente, dependiendo de las características particulares de la inversión.
- Velocidad de transferencia, sobre todo, cuando necesitamos transferir grandes cantidades de datos. La velocidad de una conexión a Internet no puede igualar, al menos de momento, a una conexión local.
Una variante de esto es que no dispongamos de una conexión a Internet suficientemente rápida para usar estos servicios. No todas las zonas geográficas tienen la misma calidad de servicio.
- Dependencia de la conexión. Si tenemos nuestros servidores en la nube y un día falla la conexión a Internet, habremos perdido la posibilidad de usarlos.
  
 ## Herramientas de virtualización

 ### Oracle VM VirtualBox
 
![image](https://github.com/alexlopezprofe/SOM/assets/148449360/ecf92147-9e91-4440-adcd-b864f8ec576f)

Software de virtualización multiplataforma de **código abierto** que permite ejecutar múltiples sistemas operativos en un solo dispositivo.

### VMware Workstation Player

VMware Workstation Player es una herramienta para ejecutar máquinas virtuales en un equipo con Windows o Linux. Las organizaciones utilizan Workstation Player para ofrecer escritorios corporativos gestionados, mientras que los estudiantes y profesores lo utilizan para aprendizaje y formación. La versión gratuita está disponible para uso personal y doméstico, y que no sea comercial. 

### VMware Workstation Pro

VMware Workstation Pro es una línea de productos de Hipervisor de escritorio que permiten a los usuarios ejecutar máquinas virtuales, contenedores y clústeres de Kubernetes.

![image](https://github.com/alexlopezprofe/SOM/assets/148449360/a42a4139-3b86-4e6a-a3cd-9c2d833bd723)

[Comparación VMware Workstation Player VS VMware Workstation Pro](https://www.vmware.com/es/products/workstation-player.html)


# Bibliografía

- https://somebooks.es/capitulo-7-configuracion-de-maquinas-virtuales/6/
- https://www.vmware.com/
- https://www.virtualbox.org/

