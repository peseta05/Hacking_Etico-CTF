**Bienvenida**

En primer lugar, es necesario comprender adecuadamente el término Hacking. El término hacker se utilizó desde su origen para definir a aquella persona que estudiaba en profundidad una tecnología, con el fin de conocerla de modo que pudiera modificarla y realizar tareas para las que no estaba pensada originalmente. Esta definición se adoptó en el ámbito informático, pero su significado ha ido variando, de tal manera que, actualmente, se suele utilizar el término hacking para definir el acceso no autorizado a sistemas ajenos con el propósito de ocasionar daños. La Real Academia Española (RAE) reconoce el término hacker (aunque lo redirige a "jáquer") en sus dos acepciones: "pirata informático" y "persona con grandes habilidades en el manejo de computadoras que investiga un sistema informático para avisar de los fallos y desarrollar técnicas de mejora".

**Ethical Hacking**

Para evitar la anterior connotación negativa se inventó este término para definir aquel hacking que no tiene propósitos dañinos, también denominado white hat hacking o hacking ético (afortunadamente, el término "jáquing" no se encuentra en el diccionario de la RAE). Estos términos se utilizan para definir la utilización de técnicas ofensivas para acceder a sistemas con la finalidad de detectar vulnerabilidades y reportarlas para que puedan ser solucionadas.

**Tipos de Hackers**

Es común identificar los distintos tipos de hackers según colores de sombreros. Al hablar del *Ethical Hacking* se introdujo el término *white hat hacking*. Como se puede deducir, un **white hack hacker** es aquel que lleva a cabo acciones de hacking debidamente autorizadas con el propósito de identificar vulnerabilidades.

Por el contrario, un **black hat hacker** es aquel que tiene propósitos maliciosos, cuyos fines consisten en obtener un beneficio personal o económico, o causar daños a una organización o persona.

Entre medias se encontrarían los denominados **grey hat hackers**. Como corresponde al color, hay muchos tonos de gris y bajo esta denominación caben unos cuantos tipos de personas. Por ejemplo, aquí entrarían aquellos que atacan a una organización para, a continuación, ponerse en contacto con ella y ofrecer sus servicios. También podrían entrar en este tipo aquellos que trabajan para un gobierno con el fin de obtener información sobre otros paises.

Diariamente se producen numerosos ciberataques; cuando alguno de ellos es detectado surgen varias preguntas: quién ha sido, cuando entró en los sistemas, qué ha hecho y qué se ha llevado, cuanto tiempo ha estado dentro y cómo consiguió acceder. Es probable que nunca se pueda identificar al atacante, y averiguar lo que ha hecho en el sistema puede requerir un proceso largo y costoso, pero lo que es aún más preocupante para muchas organizaciones es si podrá recuperarse de los daños y recuperar la información perdida. Sin embargo, si la organización hubiera identificado previamente el cómo y el qué, habría podido protegerse de una manera más adecuada y evitar el ataque o, al menos, aprender de sus vulnerabilidades para minimizar los daños.

El objetivo de la ciberseguridad es minimizar los riesgos, reduciendo las vulnerabilidades y bloqueando las amenazas, en un proceso continuo que va desde la detección de las vulnerabilidades hasta el análisis de los ataques recibidos, pasando por la monitorización en tiempo real de lo que sucede en los sistemas.

**Introducción**

Cuando una persona se quiere introducir en el mundo de la **ciberseguridad** desde el punto de vista **ofensivo**, uno de los principales problemas que suele tener es encontrar la información necesaria para empezar, no por la falta de la misma, sino más bien justo por lo opuesto: *existe un exceso de información que puede provocar frustración por empezar con aspectos demasiado complejos o por no estar estructurada*.

Este repositorio tiene como objetivo que todas aquellas personas que se quieren iniciar en el *"hacking ético"*comprendan los conceptos, las herramientas, tengan los recursos necesarios y conozcan la metodología que se debe seguir durante el proceso, se da por hecho que el lector dispone de conocimientos previos de **Informática** y **Redes**, que resultan muy necesarios para este mundo. Por ello, en este  repositorio se parte del supuesto de que el lector sabe manejar con soltura Sistemas Operativos [**Linux**](https://unhackeretico-notes.blogspot.com/2025/06/sistemas-operativos-linux.html) y [**Windows**](https://unhackeretico-notes.blogspot.com/2025/06/sistemas-operativos-windows.html) y posee unos conocimientos básicos de [**Protocolos de Red**](https://unhackeretico-notes.blogspot.com/2025/06/funcionamiento-del-protocolo-tcpip.html), aunque esto no quiere decir que sea imprescindible conocer hasta el mínimo detalle todos los protocolos ni ser un experto administrador de sistemas. Se sobreentiende que la propia inquietud del lector interesado en la ciberseguridad le animará a profundizar en aquellos aspectos en los que detecte que deberá tener mayores conocimientos.

Con un lenguaje instructivo se introduce al lector de forma secuencial en esta disciplina donde la teoría esta acompañada de numerosos ejemplos prácticos, realizados sobre laboratorios controlados (CTF) que el propio lector puede crear. Para ello el repsositorio se estructura de la siguiente forma:

- Definiciones, conceptos y tipos de análisis.
- Técnicas de reconocimiento y herramientas útiles para el mismo.
- Fase de enumeración y técnicas de obtención de información.
- Explotación de sistemas y obtención de acceso utilizando la información conseguida en la fase de enumeración.
- Obtención de información del equipo y de la red interna para tomar el control total del sistema.
- Test de la seguridad de las redes WIFI.

Con este repositorio aprenderás a descubrir vulnerabilidades atacando sistemas antes de que lo hagan los ciberdelincuentes. 

Antes de continuar explorando el contenido de este repositorio, te invito a leer el [**Descargo de Responsabilidad**](https://github.com/peseta05/Hacking_Etico-CTF/blob/main/Descargo%20de%20Responsabilidad.md). Es importante entender que todo lo compartido en este repositorio tiene fines educativos y está orientado al uso responsable del conocimiento en Ciberseguridad.

**Perfil de un buen hacker o ciberinvestigador**

Los conocimientos que debe adquirir un hacker se sustentan sobre una base sólida de conocimientos básicos y avanzados del funcionamiento de los sistemas informáticos. Esto incluye materia o áreas como:

- **Arquitectura de computadoras y lenguaje ensamblador:** Constituye la base del funcionamiento de los elementos hardware y software de los sistemas informáticos.
- **Redes de ordenadores y protocolos de red:** Esto incluye las diferentes arquitecturas de red, los tipos de redes (cableadas, inalámbricas, fibra óptica...), los dispositivos que intervienen en las redes de comunicaciones, la capa de protocolos TCP/IP y OSI y los protocolos de encaminamiento.
- **Administración de sistemas operativos:** Instalar y configurar sistemas operativos, tanto Windows como GNU/Linux, que incluyen elementos como políticas de seguridad, permisos y roles de usuarios y grupos, administración de servicios (DHCP, DNS, FTP, HTTP, SSH...), administración de dominios, gestión de cuotas, configuración de reglas de cortafuegos, etc...
Gestión y administración de bases de datos: Conocer los diferentes lenguajes de modelado de datos (SQL y noSQL), diferentes sistemas gestores de bases de datos (relacionales, orientados a objetos), su estructura y comandos de administración.
- **Lenguajes de programación:** Es un área muy amplia que va desde lenguajes de bajo nivel (C, C++, Go, Rust), hasta lenguajes orientados a objetos (Java, C#), programación orientada a aplicaciones móviles (Android, iOS), tecnologías web (Javascript, Jakarta EE framework, PHP, ASP, NodeJS), lenguajes de scripting (Python, Bash, PowerShell). La lista no es exhaustiva y puede ser que uno de los lenguajes o tecnologías encaje en más de una categoría.
- **Criptografía:** Serán útiles los conocimientos desde dos perspectivas, los fundamentos matemáticos detrás de los algoritmos criptográficos y la aplicación práctica de técnicas criptográficas.

**Acceso a la Ciberseguridad a través de FP**

La Formación Profesional se ha convertido en una de las mejores opciones para acceder al sector con garantías de empleabilidad. Gracias a la colaboración entre instituciones educativas, administraciones públicas y empresas privadas, se han desarrollado programas formativos alineados con las necesidades del mercado, combinando formación teórica con prácticas en entornos laborales reales.

En España, para desarrollar una carrera en ciberseguridad, es fundamental contar con una base sólida en informática a través de estudios reglados como un ciclo formativo de Formación Profesional (FP), y combinarlo con formación autodidacta y práctica especializada.

El itinerario académico oficial más habitual comienza con la FP, donde existen varias opciones:

- **El Ciclo Formativo de Grado Medio como [Sistemas Microinformáticos y Redes (SMR)](https://www.todofp.es/que-estudiar/familias-profesionales/informatica-comunicaciones/sistemas-microniformaticos-redes.html):** Este ciclo es accesible sin necesidad de bachillerato y proporciona las bases de la informática general, aunque con un enfoque más básico.
- **Los Ciclos Formativos de Grado Superior como [Administración de Sistemas Informáticos en Red (ASIR)](https://www.todofp.es/que-estudiar/familias-profesionales/informatica-comunicaciones/admin-sist-informaticos-red.html), [Desarrollo de Aplicaciones Multiplataforma (DAM)](https://www.todofp.es/que-estudiar/familias-profesionales/informatica-comunicaciones/des-aplicaciones-multiplataforma.html) y [Desarrollo de Aplicaciones Web (DAW)](https://www.todofp.es/que-estudiar/familias-profesionales/informatica-comunicaciones/des-aplicaciones-web.html):** Siendo el Ciclo Formativo de Grado Superior de Administración de Sistemas Informaticos en Red (ASIR) especialmente recomendado porque, aunque no tiene un enfoque específico en ciberseguridad, abarca los fundamentos esenciales: **Redes**, **Sistemas Operativos** (*Linux* y *Windows*), **Bases de Datos**, **Hardware**, y **Administración de Servicios**. Estos conocimientos son imprescindibles para entender los entornos que se deben proteger y gestionar en ciberseguridad.

El ciclo oficial es solo una base. Es fundamental complementar la formación con aprendizaje autodidacta y cursos específicos:

- [**Especialización de Ciberseguridad en Entornos de las Tecnologías de la Información (CETI)**](https://www.todofp.es/que-estudiar/familias-profesionales/informatica-comunicaciones/ce-ciberseguridad-entornos-tecnologias-informacion.html): Es un curso de especialización dirigido a titulados de ciclos formativos superiores de Informática (tales como los mencionados anteriormente), también conocido como el "*Máster de la FP*", es ideal para quienes buscan una formación sólida, practica y orientada al mundo laboral. Si quieres trabajar en ciberseguridad, como *Experto en Ciberseguridad*, *Auditor de Ciberseguridad*, *Consultor de Ciberseguridad*, *Analista Forense Informatico*/*Perito Judicial* (Según el Artículo *340* de la [*Ley de Enjuiciamiento Civil*](https://www.boe.es/buscar/act.php?id=BOE-A-2000-323#a340)) y *Hacker Ético* esta es tu titulación. Esta especialidad tiene un plan de formación como:
    - **Análisis Forense Informático**: Técnicas para recopilar, preservar y analizar evidencia digital tras un incidente, buscando causas y culpables, con validez legal.
    - **Bastionado de Redes y Sistemas**: Fortalecimiento de sistemas y redes eliminando servicios innecesarios, configuraciones por defecto y aplicando parches para reducir la superficie de ataque.
    - **Hacking Ético**: Simulación de ataques maliciosos por profesionales (hackers éticos) para encontrar y corregir vulnerabilidades antes que atacantes reales, de forma legal.
    - **Incidentes de Ciberseguridad**: Gestión de eventos que comprometen la confidencialidad, integridad o disponibilidad de sistemas (ataques, malware, etc.), desde la detección hasta la recuperación.
    - **Normativa de Ciberseguridad**: Conjunto de leyes, regulaciones y estándares que obligan a cumplir buenas prácticas para proteger la información y sistemas.
    - **Puesta en Producción Segura**: Proceso para asegurar que nuevos sistemas o aplicaciones se implementen siguiendo las mejores prácticas de seguridad desde el diseño, evitando introducir vulnerabilidades.
- **Cursos online especializados en Ciberseguridad**: En el mundo hispanohablante destaca **Marcelo Vázquez**, alias **S4vitar**, quien cada dia en su canal de [Twitch](https://www.twitch.tv/s4vitaar) realiza directos explicando técnicas de hacking o explotando alguna maquina. Ha trabajado como Pentester en empresas de ciberseguridad como *Eleven Paths*, *OneCyber* y *EnigmaSec*, actualmente dirige su propia empresa de ciberseguridad *QUBIT TECHNOLOGIES* desde la que ofrece auditorias y formación especializada a empresas. En abril de 2023 lanzo el curso *Introducción al hacking ético* en su academia online [Hack4u](https://hack4u.io/cursos/) con mas de 50 horas de contenido, tambien ofrece una [hoja de ruta](https://docs.google.com/spreadsheets/u/0/d/1dzvaGlT_0xnT-PGO27Z_4prHgA8PHIpErmoWdlUrSoA/htmlview?usp=gmail&pli=1) dinámica para profesionales y principiantes que buscan formación práctica y teórica.
- [**Certificaciones reconocidas internacionalmente**](https://unhackeretico-notes.blogspot.com/p/certificaciones-de-ciberseguridad.html): Pueden ser muy útiles, aunque no imprescindibles de inicio.
- [**Práctica con laboratorios de Hacking Ético**](https://unhackeretico-notes.blogspot.com/2025/06/creacion-de-un-laboratorio.html): Retos CTF (*Capture The Flag*) y plataformas de simulación de ataques y defensa.

**Acceso a la Ciberseguridad a través de la Universidad**

La vía universitaria está orientada a quienes buscan una formación multidisciplinar más teórica y profunda, con proyección a puestos de trabajo de mayor responsabilidad o investigación.

Para acceder a estudios universitarios es necesario disponer de un título de Bachillerato y superar la evaluación pertinente (*EBAU*), o disponer de un título de FP superior, o de acceso universitario para mayores de 25 años.

Se puede cursar un grado universitario específicamente en ciberseguridad o en ingeniería informática / telecomunicaciones. Los grados dedicados en exclusiva a ciberseguridad incluyen contenidos como criptografía, protección de infraestructuras, análisis de malware, derecho y gestión de riesgos digitales.

Finalizado el grado, es posible especializarse aún más mediante másteres oficiales o cursos de postgrado, permitiendo acceder tanto a empleos técnicos avanzados como a labores de dirección, investigación y consultoría estratégica.

**Conclusión entre FP y Universidad**

Ambas rutas "*FP* y *Universidad*" conducen a competencias profesionales que responden a la alta demanda de la ciberseguridad en España. La FP destacada por su orientación práctica y rápida incorporación al mundo laboral, mientras que la universidad ofrece una base conceptual sólida y mayores posibilidades de progresión hacia puestos de mayor especialización o investigación. Elegir uno u otro camino dependerá del perfil, objetivos y preferencias de cada estudiante, sabiendo que ambos son altamente valorados por las empresas del entorno digital.

El INCIBE, pone a tu disposición tres [catálogos formativos](https://www.incibe.es/incibe/formacion/catalogos-formacion-ciberseguridad) que te ayudarán a elegir la mejor opción para especializarte en ciberseguridad y acceder a un mercado laboral en pleno auge.

Si está empezando en el *hacking ético* como me imagino, mi consejo es que no se obsesione con esto, el aprendizaje es largo y lleva su tiempo adquirir los conocimientos suficientes. Tómese su tiempo para ganar experiencia.

**Mantenerse bien informado**

El mundo de la tecnología avanza a pasos agigantados, por lo que en un corto periodo de tiempo se suceden numerosas novedades. Lo mismo sucede en ciberseguridad; por tanto, es preciso mantenerse al día de todo lo que ocurre. Una forma de hacerlo es a través de blogs especializados, de los que se recomiendan los siguientes:

- [**Una al día**](https://unaaldia.hispasec.com/): La iniciativa de Hispasec nació hace más de 24 años y desde entonces no faltan a su cita diaria con una publicación relacionada con la seguridad informática.
- [**Un informático en el lado del mal**](https://www.elladodelmal.com/): El blog personal de Chema Alonso que es un referente en el mundo de la ciberseguridad.
- [**Flu Proyect**](https://www.flu-project.com/): Sitio web de Pablo González y Juan Antonio Calles donde encontrar noticias y artículos de investigaciones. Además, en él publican otros autores del panorama nacional.
- [**Hackplayer**](https://www.hackplayers.com/): Otro sitio web de referencia en castellano donde las publicaciones son frecuentes y hay un gran número de colaboradores.
- [**The hacker Way**](https://thehackerway.es/): Sitio web de Daniel Echeverri, alias Adastra, con numerosas publicaciones de gran calidad técnica.
- [**Hacking Articles**](https://www.hackingarticles.in/): Sitio en ingles, con publicaciones continuas de diferentes categorías, soluciones a retos CTF, utilización de herramientas, técnicas de hacking, red teaming, etc....
- [**Google Project Zero**](https://googleprojectzero.blogspot.com/): El blog del equipo de Google encargado de descubrimientos de vulnerabilidades zero day. Sus publicaciones suelen ser explicaciones técnicas de sus descubrimientos.
- [**Ars Technica**](https://arstechnica.com/information-technology/): La sección de tecnología es un lugar de referencia para mantenerse al día de las últimas novedades.

Las conferencias de seguridad que se organizan cada año son un punto de encuentro de hackers e investigadores que comparten sus nuevos descubrimientos, realizan talleres y demostraciones prácticas, sirven para formarse y mantenerse actualizados. Como no siempre es posible asistir a las charlas, algunas de ellas se publican libremente para consulta de todo el mundo y, en determinados casos, se emiten en directo en plataformas de streaming. Destacan las siguiente conferencias, dos de carácter internacional y el resto en España o Latinoamérica:

- [**BlackHat**](https://blackhat.com/): Una de las conferencias de referencia a nivel mundial donde se reúnen los mejores hackers del globo. Se realizan varios eventos anuales (BlackHat Asia, BlackHat USA, BlackHat Europe, etc...).
- [**DEFCON**](https://defcon.org/): Esta conferencia que se realiza en Las Vegas cada año es uno de los principales eventos de hacking del planeta.
- [**RootedCON**](https://rootedcon.com/): Posiblemente la conferencia de seguridad más importante del país que se celebra desde 2010.
- [**Navaja Negra**](https://www.navajanegra.com/2025/): Otra conferencia referente en España. Se viene celebrando desde 2012 en Albacete y se organiza por la Escuela Superior de Ingeniería Informática y la UCLM.
- [**DragonJar**](https://www.dragonjarcon.org/): Esta conferencia de seguridad se organiza en Colombia y ofrece acceso online y gratuito
- [**H-CON**](https://www.h-c0n.com/p/home.html): Conferencia de ciberseguridad organizada por la gente de Hackplayers.
- [**No cON Name**](https://www.noconname.org/): Una de las conferencias más antiguas de España, surgió en 1999 en las Islas Baleares como asociación si ánimo de lucro.
- [**Congreso C1b3rWall**](https://c1b3rwall.policia.es/congreso): Su primera edición tuvo lugar en 2019 y tras el parón obligado por la pandemia volvió a celebrarse en 2022. Se lleva a cabo en la sede de la Escuela Nacional de Policía en Ávila a finales de junio.
- [**Jornadas STIC del CCN-CERT**](https://jornadas.ccn-cert.cni.es/es/?format=html): Jornadas organizadas por el Centro Cristológico Nacional desde 2007 y que reúne a responsables de seguridad de las Administraciones públicas, empresas y experto en ciberseguridad. En la web de las diferentes ediciones se pueden encontrar los videos y materiales de las charlas que se han llevado a cabo.

**Recursos Útiles**

Si quieres empezar ahora, [aquí](https://unhackeretico-notes.blogspot.com/p/recursos.html) tienes una lista de recursos utiles de ciberseguridad.

**Distribuciones para Pentesting**

Para llevar a cabo las labores de *pentesting* se necesita un buen arsenal de herramientas, que se pueden instalar manualmente en el sistema operativo cuando se vayan necesitando o se puede emplear algunas de las distribuciones específicamente creadas para esta tarea. La segunda opción es la mas recomendable y la más empleada ya que facilita enormemente el trabajo y ahorra una gran cantidad de tiempo. Entre las distribuciones disponibles destacan las siguientes:

- **[Kali Linux](https://www.kali.org/):** Distribución de seguridad basada en Debian desarrollada por la empresa *Offensive Security*. Dispone de numerosas opciones de instalación. Tambien dispone de un enorme repositorio de paquetes donde se incluyen nuevas herramientas con cada nueva versión, Lo que facilita la instalación automatizada de estas.
- **[ParrotOS](https://parrotsec.org/):** Distribucion de seguridad basada en Debian. En 2022 comenzó una alianza con HackTheBox para mejorar su desarrollo e incluirla en la plataforma a través de la web.
- [**TailsOS**](https://tails.net/index.es.html): Acrónimo de "*The Amnesic Incognito Live System*" es una distribución de Linux basada en Debian que se ejecuta desde una unidad USB o un DVD. Su objetivo principal es proporcionar a los usuarios una forma segura y anónima de utilizar Internet, minimizando las huellas digitales dejadas en el proceso. Las características clave son:
    - **Privacidad y Anonimato**: Tails canaliza todo el tráfico a través de la red Tor, lo que garantiza el anonimato al ocultar la ubicación y la identidad del usuario.
    - **Modo Amnésico**: Tails no almacena ninguna información de sesión después de apagar el sistema. Esto significa que no deja rastro en el dispositivo que estás utilizando, proporcionando un nivel adicional de seguridad.
    - **Herramientas de Criptografía**: Tails viene con herramientas de cifrado integradas, como GnuPG, que permite a los usuarios cifrar y firmar digitalmente sus correos electrónicos y documentos.
    - **Navegación Segura**: La combinación de Tor Browser y la configuración de seguridad predeterminada garantiza una experiencia de navegación segura y privada.
    - **Uso Temporal de Hardware**: Tails está diseñado para ser utilizado en cualquier computadora sin dejar rastros en el hardware. Esto permite a los usuarios llevar su entorno seguro a donde vayan.
- **[BlackArch](https://blackarch.org/):** Distribución de seguridad basada en Arch Linux con mas de 2800 herramientas en sus repositorios.
- **[CommandoVM](https://github.com/mandiant/commando-vm):** Es un conjunto de herramientas para convertir el sistemas operativo Windows en una distribución de seguridad ofensiva. Creada por la empresa "*Mandiant*".

Puedes acceder al blog para ver los contenidos haciendo click [**aquí**](https://unhackeretico-notes.blogspot.com/).

No dudes en volver de vez en cuando para ver nuevos *contenidos* sobre **ciberseguridad**. Este repositorio y el blog se irán actualizando progresivamente a medida que avance y adquiera nuevos conocimientos en el mundo del *hacking ético*. Mi objetivo es compartir lo que voy aprendiendo, desde lo mas básico hasta técnicas mas avanzadas.

**¡Llevemos el aprendizaje más allá del repositorio!**

Si te apasiona el pentesting y quieres un espacio para resolver dudas en tiempo real, compartir herramientas y conectar con otros entusiastas del sector, súmate a nuestro grupo de [Telegram](https://t.me/+jTwMaut-z2NjMGQ0).
