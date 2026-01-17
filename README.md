**Descargo de Responsabilidad**

El contenido publicado en este repositorio tiene como único objetivo la **divulgación educativa y ética** de conocimientos relacionados con la *ciberseguridad*, *hacking ético* y *protección digital*.

Toda la información publicada está destinada a promover *buenas prácticas de seguridad informática*, ayudar a usuarios y profesionales a **proteger sus sistemas**, y **no debe utilizarse para actividades ilegales** o **no autorizadas**.  

**El autor de este repositorio no se hace responsable del mal uso de los contenidos aquí compartidos**. *Se recuerda que el acceso no autorizado a sistemas informáticos está penado por la ley*.

En *España*, el [**Código Penal**](https://www.boe.es/buscar/act.php?id=BOE-A-1995-25444) establece los supuestos en los que un hacker podría estar cometiendo un delito. Son de interés los artículos comprendidos *entre el 197 y el 201*, *especialmente el 197bis y el 197ter*, que se incorporan al código penal en el año 2015:

- **Artículo 197bis**.
    - **1.** "*El que por cualquier medio o procedimiento, vulnerando las medidas de seguridad establecidas para impedirlo, y sin estar debidamente autorizado, acceda o facilite a otro el acceso al conjunto o una parte de un sistema de información o se mantenga en él en contra de la voluntad de quien tenga el legítimo derecho a excluirlo, será castigado con pena de prisión de seis meses a dos años*".
    - **2.** "*El que mediante la utilización de artificios o instrumentos técnicos, y sin estar debidamente autorizado, intercepte transmisiones no públicas de datos informáticos que se produzcan desde, hacia o dentro de un sistema de información, incluidas las emisiones electromagnéticas de los mismos, será castigado con una pena de prisión de tres meses a dos años o multa de tres a doce meses*".
- **Artículo 197ter.** "*Será castigado con una pena de prisión de seis meses a dos años o multa de tres a dieciocho meses el que, sin estar debidamente autorizado, produzca, adquiera para su uso, importe o, de cualquier modo, facilite a terceros, con la intención de facilitar la comisión de alguno de los delitos a que se refieren los apartados 1 y 2 del artículo 197 o el artículo 197 bis:*
  
  - *un programa informático, concebido o adaptado principalmente para cometer dichos delitos; o*
  - *una contraseña de ordenador, un código de acceso o datos similares que permitan acceder a la totalidad o a una parte de un sistema de información*".

Por tanto, de lo anterior se deduce que es totalmente imprescindible tener la autorización correspondiente por medio de un contrato en donde se establezca claramente el propósito y ámbito de la actividad. En caso de que se realice una investigación sobre un sistema informático sin tener dicha autorización, aunque no se haga un uso malintencionado de la información y reporten las vulnerabilidades encontradas, se podría ser denunciado.

Este repositorio rechaza cualquier actividad que vulnere la privacidad, la integridad de los sistemas o la confidencialidad de la información.

El Hacking Ético consiste en la identificación y análisis de vulnerabilidades en sistemas únicamente con autorización previa y expresa del propietario del sistema. Todas las técnicas, herramientas y metodologías descritas en este repositorio deben utilizarse de forma legal, ética, y responsable, respetando en todo momento la legislación vigente y los derechos de terceros.

Antes de poner en practica cualquier técnica aquí descrita, asegúrate de contar con:

- Permiso explicito por escrito del propietario del sistema.
- Conocimiento de la leyes y normativas aplicables en tu país.
- Un objetivo legítimo relacionado con la mejora de la seguridad.

Al usar este repositorio, el usuario acepta liberar al autor y editor de cualquier y toda responsabilidad por cualquier daño, pérdida o perjuicio que pueda resultar del uso de este blog o de cualquiera de las informaciones contenidas en el mismo.

El autor no promueve, avala ni se responsabiliza del uso indebido, ilegal o malintencionado de la información aquí presentada. Cualquier acción realizada por el lector basada en los contenidos de este sitio es responsabilidad exclusiva del propio lector.

Al continuar navegando y leyendo este repositorio, aceptas este descargo de responsabilidad y te comprometes a utilizar la información de manera ética, legal y profesional.

Si tu interés es formarte en Hacking Ético, te recomiendo hacerlo a través de laboratorios controlados, entornos de prueba (CTF), programas de bug bounty o certificaciones reconocidas en ciberseguridad.

**Utiliza siempre el conocimiento con responsabilidad**. La mejor defensa comienza con la educación.

**Bienvenida**

El término hacker se utilizó desde su origen para definir a aquella persona que estudiaba en profundidad una tecnología, con el fin de conocerla de modo que pudiera modificarla y realizar tareas para las que no estaba pensada originalmente. Esta definición se adoptó en el ámbito informático, pero su significado ha ido variando, de tal manera que, actualmente, se suele utilizar el término hacking para definir el acceso no autorizado a sistemas ajenos con el propósito de ocasionar daños. La RAE reconoce el término hacker (aunque lo redirige a "jáquer") en sus dos acepciones: "pirata informático" y "persona con grandes habilidades en el manejo de computadoras que investiga un sistema informático para avisar de los fallos y desarrollar técnicas de mejora".

**Ethical Hacking**

Para evitar la anterior connotación negativa se inventó este término para definir aquel hacking que no tiene propósitos dañinos, también denominado white hat hacking o hacking ético (afortunadamente, el término "jáquing" no se encuentra en el diccionario de la RAE). Estos términos se utilizan para definir la utilización de técnicas ofensivas para acceder a sistemas con la finalidad de detectar vulnerabilidades y reportarlas para que puedan ser solucionadas.

Diariamente se producen numerosos ciberataques; cuando alguno de ellos es detectado surgen varias preguntas: quién ha sido, cuando entró en los sistemas, qué ha hecho y qué se ha llevado, cuanto tiempo ha estado dentro y cómo consiguió acceder. Es probable que nunca se pueda identificar al atacante, y averiguar lo que ha hecho en el sistema puede requerir un proceso largo y costoso, pero lo que es aún más preocupante para muchas organizaciones es si podrá recuperarse de los daños y recuperar la información perdida. Sin embargo, si la organización hubiera identificado previamente el cómo y el qué, habría podido protegerse de una manera más adecuada y evitar el ataque o, al menos, aprender de sus vulnerabilidades para minimizar los daños.

El objetivo de la ciberseguridad es minimizar los riesgos, reduciendo las vulnerabilidades y bloqueando las amenazas, en un proceso continuo que va desde la detección de las vulnerabilidades hasta el análisis de los ataques recibidos, pasando por la monitorización en tiempo real de lo que sucede en los sistemas.

**Introducción**

Cuando una persona se quiere introducir en el mundo de la **ciberseguridad** desde el punto de vista **ofensivo**, uno de los principales problemas que suele tener es encontrar la información necesaria para empezar, no por la falta de la misma, sino más bien justo por lo opuesto: *existe un exceso de información que puede provocar frustración por empezar con aspectos demasiado complejos o por no estar estructurada*.

Este repositorio tiene como objetivo que todas aquellas personas que se quieren iniciar en el *"hacking ético"* tengan los recursos necesarios y conozcan la metodología que se debe seguir durante el proceso, se da por hecho que el lector dispone de conocimientos previos de **Informática** y **Redes**, que resultan muy necesarios para este mundo. Por ello, en este  repositorio se parte del supuesto de que el lector sabe manejar con soltura Sistemas Operativos [**Linux**](https://unhackeretico-notes.blogspot.com/2025/06/sistemas-operativos-linux.html) y [**Windows**](https://unhackeretico-notes.blogspot.com/2025/06/sistemas-operativos-windows.html) y posee unos conocimientos básicos de [**Protocolos de Red**](https://unhackeretico-notes.blogspot.com/2025/06/funcionamiento-del-protocolo-tcpip.html), aunque esto no quiere decir que sea imprescindible conocer hasta el mínimo detalle todos los protocolos ni ser un experto administrador de sistemas. Se sobreentiende que la propia inquietud del lector interesado en la ciberseguridad le animará a profundizar en aquellos aspectos en los que detecte que deberá tener mayores conocimientos.

Puedes acceder al blog para ver los contenidos haciendo click [**aquí**](https://unhackeretico-notes.blogspot.com/).

No dudes en volver de vez en cuando para ver nuevos *contenidos* sobre **ciberseguridad**. Este blog se irá actualizando progresivamente a medida que avance y adquiera nuevos conocimientos en el mundo del *hacking ético*. Mi objetivo es compartir lo que voy aprendiendo, desde lo mas básico hasta técnicas mas avanzadas.

**Perfil de un buen hacker o ciberinvestigador**

Los conocimientos que debe adquirir un hacker se sustentan sobre una base sólida de conocimientos básicos y avanzados del funcionamiento de los sistemas informáticos. Esto incluye materia o áreas como:

- **Arquitectura de computadoras y lenguaje ensamblador:** Constituye la base del funcionamiento de los elementos hardware y software de los sistemas informáticos.
- **Redes de ordenadores y protocolos de red:** Esto incluye las diferentes arquitecturas de red, los tipos de redes (cableadas, inalámbricas, fibra óptica...), los dispositivos que intervienen en las redes de comunicaciones, la capa de protocolos TCP/IP y OSI y los protocolos de encaminamiento.
- **Administración de sistemas operativos:** Instalar y configurar sistemas operativos, tanto Windows como GNU/Linux, que incluyen elementos como políticas de seguridad, permisos y roles de usuarios y grupos, administración de servicios (DHCP, DNS, FTP, HTTP, SSH...), administración de dominios, gestión de cuotas, configuración de reglas de cortafuegos, etc...
Gestión y administración de bases de datos: Conocer los diferentes lenguajes de modelado de datos (SQL y noSQL), diferentes sistemas gestores de bases de datos (relacionales, orientados a objetos), su estructura y comandos de administración.
- **Lenguajes de programación:** es un área muy amplia que va desde lenguajes de bajo nivel (C, C++, Go, Rust), hasta lenguajes orientados a objetos (Java, C#), programación orientada a aplicaciones móviles (Android, iOS), tecnologías web (Javascript, Jakarta EE framework, PHP, ASP, NodeJS), lenguajes de scripting (Python, Bash, PowerShell). La lista no es exhaustiva y puede ser que uno de los lenguajes o tecnologías encaje en más de una categoría.
- **Criptografía:** Serán útiles los conocimientos desde dos perspectivas, los fundamentos matemáticos detrás de los algoritmos criptográficos y la aplicación práctica de técnicas criptográficas.

**Acceso a la Ciberseguridad a través de FP**

En España, para desarrollar una carrera en ciberseguridad, es fundamental contar con una base sólida en informática a través de estudios reglados como un ciclo formativo de Formación Profesional (FP), y combinarlo con formación autodidacta y práctica especializada.

El itinerario académico oficial más habitual comienza con la FP, donde existen varias opciones:

- **El Ciclo Formativo de Grado Medio como Sistemas Microinformáticos y Redes (SMR):** Este ciclo es accesible sin necesidad de bachillerato y proporciona las bases de la informática general, aunque con un enfoque más básico.
- **Los Ciclos Formativos de Grado Superior como Administración de Sistemas Informáticos en Red (ASIR), Desarrollo de Aplicaciones Multiplataforma (DAM) y Desarrollo de Aplicaciones Web (DAW):** Siendo el Ciclo Formativo de Grado Superior de Administración de Sistemas Informaticos en Red (ASIR) especialmente recomendado porque, aunque no tiene un enfoque específico en ciberseguridad, abarca los fundamentos esenciales: Redes, Sistemas (Linux y Windows), Bases de Datos, Hardware, y Administración de Servicios. Estos conocimientos son imprescindibles para entender los entornos que se deben proteger y gestionar en ciberseguridad.
El ciclo oficial es solo una base. Es fundamental complementar la formación con aprendizaje autodidacta y cursos específicos:

Cursos online especializados en Ciberseguridad.
Práctica con laboratorios de Hacking Ético, retos CTF (*Capture The Flag*) y plataformas de simulación de ataques y defensa.
Certificaciones reconocidas internacionalmente pueden ser muy útiles, aunque no imprescindibles de inicio.

**Acceso a la Ciberseguridad a través de la Universidad**

La vía universitaria está orientada a quienes buscan una formación multidisciplinar más teórica y profunda, con proyección a puestos de trabajo de mayor responsabilidad o investigación.

Para acceder a estudios universitarios es necesario disponer de un título de Bachillerato y superar la evaluación pertinente (*EBAU*), o disponer de un título de FP superior, o de acceso universitario para mayores de 25 años.

Se puede cursar un grado universitario específicamente en ciberseguridad o en ingeniería informática / telecomunicaciones. Los grados dedicados en exclusiva a ciberseguridad incluyen contenidos como criptografía, protección de infraestructuras, análisis de malware, derecho y gestión de riesgos digitales.

Finalizado el grado, es posible especializarse aún más mediante másteres oficiales o cursos de postgrado, permitiendo acceder tanto a empleos técnicos avanzados como a labores de dirección, investigación y consultoría estratégica.

**Conclusión entre FP y Universidad**

Ambas rutas "*FP* y *Universidad*" conducen a competencias profesionales que responden a la alta demanda de la ciberseguridad en España. La FP destacada por su orientación práctica y rápida incorporación al mundo laboral, mientras que la universidad ofrece una base conceptual sólida y mayores posibilidades de progresión hacia puestos de mayor especialización o investigación. Elegir uno u otro camino dependerá del perfil, objetivos y preferencias de cada estudiante, sabiendo que ambos son altamente valorados por las empresas del entorno digital.

**Certificaciones mas relevantes en el Ámbito de la Seguridad Ofensiva**

Algunas de las certificaciones más relevantes en el ámbito de la seguridad ofensiva son:

- **CEH (EC Council Certified Etihical Hacker):** Es una de las certificaciones más extendidad y demandadas, pero suele ser muy criticada por su bajo contenido práctico, aunque esto ha cambiado a partir de la version 12 (CEHv12).
- **Pentest+:** Certificado de CompTIA (The Computing Techology Industry Association) con un nivel intermedio. A diferencia de otras certificaciones, esta incluye elementos de todas las fases de un test de intrusión.
- **eJPT (eLearnSecurity Junior Penetration tester):** Esta certificación está enfocada a expertos de IT que comienzan en el area del pentesting; por tanto, es una certificación de nivel básico.
- **eCPPT (eLearnSecurity Certified Professional Penetration Tester):** Certificación de nivel avanzado sobre test de intrusión.
- **HTB CPTS (HackTheBox Certified Penetration Testing Specialist):** Certificación altamente práctica que evalúa las habilidades de pruebas de penetración de los candidatos, es una certificación creada por la plataforma HackThebox.
- **PNPT (TCM Security Practical Network Penetration Tester):** Certificación práctica de pruebas de penetración creada por la empresa TCM Security.
- **OSCP (Offensive Security Certified Professional):** Esta certificación posiblemente sea la más temida y codiciada en el sector por su nivel de dificultad; tambien es una de las que más inversión económica precisa para realizarla. Su lema "*Try Harder*", anima a aquellos que no han conseguido su objetivo a seguir intentándolo y nunca tirar la toalla.
- [**Especialización de Ciberseguridad en Entornos de las Tecnologías de la Información (CETI)**](https://www.todofp.es/que-estudiar/familias-profesionales/informatica-comunicaciones/ce-ciberseguridad-entornos-tecnologias-informacion.html): Es un curso de especialización dirigido a titulados de  ciclos formativos superiores de Informática, es ideal para quienes buscan una formación sólida, practica y orientada al mundo laboral. Si quieres trabajar en ciberseguridad, como *Experto en Ciberseguridad*, *Auditor de Ciberseguridad*, *Consultor de Ciberseguridad*, *Perito Judicial* (Según los Art *340* y *457* de la [*Ley de Enjuiciamiento Civil*](https://www.boe.es/buscar/act.php?id=BOE-A-2000-323)) y *Hacker Ético* esta es tu titulación. Esta especialidad tiene un plan de formación como:
    - **Análisis Forense Informático**: Técnicas para recopilar, preservar y analizar evidencia digital tras un incidente, buscando causas y culpables, con validez legal.
    - **Bastionado de Redes y Sistemas**: Fortalecimiento de sistemas y redes eliminando servicios innecesarios, configuraciones por defecto y aplicando parches para reducir la superficie de ataque.
    - **Hacking Ético**: Simulación de ataques maliciosos por profesionales (hackers éticos) para encontrar y corregir vulnerabilidades antes que atacantes reales, de forma legal.
    - **Incidentes de Ciberseguridad**: Gestión de eventos que comprometen la confidencialidad, integridad o disponibilidad de sistemas (ataques, malware, etc.), desde la detección hasta la recuperación.
    - **Normativa de Ciberseguridad**: Conjunto de leyes, regulaciones y estándares que obligan a cumplir buenas prácticas para proteger la información y sistemas.
    - **Puesta en Producción Segura**: Proceso para asegurar que nuevos sistemas o aplicaciones se implementen siguiendo las mejores prácticas de seguridad desde el diseño, evitando introducir vulnerabilidades.

Si está empezando en el *hacking ético* como me imagino, mi consejo es que no se obsesione con esto, el aprendizaje es largo y lleva su tiempo adquirir los conocimientos suficientes. Tómese su tiempo para ganar experiencia.

**Recomendaciones de libros para iniciarse en el Hacking Ético**

Tanto si estas empezando o quieres reforzar tus conocimientos en el mundo del hacking ético, una de las mejores formas de aprender es a través de libros bien estructurados y con contenidos alineados a la realidad del sector, Quiero recomendarte tres fuentes excelentes para formarte de manera solida son las editoriales 

- [**Paraninfo**](https://www.paraninfo.es/).
- [**RA-MA**](https://www.ra-ma.es/).
- [**0xWORD**](https://0xword.com/).

Estas editoriales ofrecen libros muy completos sobre *ciberseguridad*, *hacking ético*, *pentesting*, y *fundamentos de redes*. Están orientados tanto a estudiantes de formación profesional como a autodidactas, e incluso a profesionales que quieren actualizarse.

¿Por que los recomiendo?
- Están escritos por expertos del sector.
- Tienen un enfoque práctico.
- A menudo se adaptan a certificaciones oficiales (como CompTIA, LPI o Cisco).
- Incluyen laboratorios, ejercicios y ejemplos reales.

Algunos títulos recomendados son:
- [**Hacking Ético - RA-MA**](https://www.ra-ma.es/libro/hacking-etico_139070/).
- [**Hacking Ético - Paraninfo**](https://www.paraninfo.es/catalogo/9788428362672/hacking-etico).
- [**The Art of Pentesting**](https://0xword.com/es/libros/236-the-art-of-pentesting.html).

La lectura técnica es clave para desarrollar una base sólida. Así que si estás aprendiendo o ya estas en camino, te animo a que explores estos libros. Yo mismo los utilizo como parte de mi formación y los considero un gran apoyo.

**¡Recuerda!** *El conocimiento es tu mejor herramienta*.

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

- [**Hacktricks**](https://book.hacktricks.wiki/es/index.html): Recurso fundamental que debe estar en los marcadores, sitio de referencia de pentesters y expertos en ciberseguridad, recopila técnicas de explotación, detección de vulnerabilidades, escalada de privilegios, fallos de configuración, bastionado de servicios y un largo etcétera.
- [**Hacktricks Cloud**](https://cloud.hacktricks.wiki/es/index.html): Lo mismo que la anterior pero orientada a técnicas de pentesting en servicios en la nube.
- [**PortSwigger**](https://portswigger.net/web-security/all-materials): academia gratuita en el que se explican las vulnerabilidades tipo web más comunes. Además, dispone de varios laboratorios con ejercicios de distintos niveles para practicar con algunas de ellas.
- [**RevShells**](https://www.revshells.com/): Página muy recomendable sobre las distintas técnicas en el lanzamiento de diferentes tipos de *shells*; También existe la posibilidad de usarlo a través de la terminal con la ayuda de la herramienta escrita en python [revshell](https://github.com/esp0xdeadbeef/revshell).
- [**PayloadsAllTheThings**](https://swisskyrepo.github.io/PayloadsAllTheThings/)): Es una lista de cargas útiles y métodos de omisión para la seguridad de aplicaciones web.
- [**InternalAllTheThings**](https://swisskyrepo.github.io/InternalAllTheThings/): Hojas de trucos para Active Directory y pruebas de penetración internas.
- [**HardwareAllTheThings**](https://swisskyrepo.github.io/HardwareAllTheThings/): Es una colección de valiosas cargas útiles y técnicas de evasión diseñadas para la seguridad de hardware e IoT.
- [**FlipperZero**](https://docs.flipper.net/zero): Documentación oficial de este dispositivo multifunción de hacking portátil diseñado para pruebas de seguridad. Tiene forma de un pequeño gadget con pantalla, botones y una interfaz sencilla, ideal para auditar sistemas físicos, controles de acceso, dispositivos IoT y redes inalámbricas. Permite clonar y emular tarjetas RFID/NFC, capturar señales de radiofrecuencia (Sub-1 GHz), controlar dispositivos por infrarrojos, ejecutar ataques BadUSB simulando un teclado, y comunicarse con hardware mediante GPIO.
- [**GTFOBins**](https://gtfobins.github.io/): Pagina muy recomendable de binarios de Unix que pueden usarse para eludir las restricciones de seguridad locales en sistemas mal configurados; También existe la posibilidad de usarlo a través de la terminal con la ayuda de la herramienta escrita en python [GTFOBins-cli](https://github.com/7Rocky/gtfobins-cli).
- [**GTFOArgs**](https://gtfoargs.github.io/): Pagina muy recomendable siendo lo mismo que el anterior pero para casos donde solo puedes inyectar argumentos en un comando.
- [**LOLBAS**](https://lolbas-project.github.io/): Pagina muy recomendable en la que se describe como se pueden aprovechar las herramientas presentes por defecto en Windows para obtener información local de este.
- [**Nishang**](https://github.com/samratashok/nishang): Es un conjunto de scripts de PowerShell diseñados para pruebas de penetración y operaciones de hacking ético en entornos Windows.
- [**APKMirror**](https://www.apkmirror.com/): Es un repositorio en línea muy conocido donde los usuarios de Android pueden descargar archivos de aplicaciones (APK) directamente, sirviendo como una alternativa a la Google Play Store para obtener versiones específicas, versiones anteriores, o apps no disponibles en su región.
- [**VirusTotal**](https://www.virustotal.com/gui/home/upload): Es una plataforma gratuita de ciberseguridad que analiza archivos, URLs, direcciones IP y dominios sospechosos utilizando múltiples motores antivirus y de inteligencia de amenazas para detectar malware y otros peligros, permitiendo a usuarios y organizaciones identificar amenazas ocultas y compartir información de forma colaborativa con la comunidad de seguridad.
- [**NameCHK**](https://namechk.com/): Es una herramienta que permite comprobar si un nombre de usuario está disponible en más de 150 servicios online. De Este modo, se puede saber los servicios que utiliza un usuario en concreto, ya que habitualmente la gente mantiene dicho nombre para todos los servicios que utiliza. Además, disponen de una API que permite automatizar las consultas.
- [**Tineye**](https://tineye.com/): Es un servicio que, partiendo de una imagen, indica en que sitios web aparece. Es similar a la búsqueda por imágenes que incorpora Google Imágenes.
- [**Hashes**](https://hashes.com/): Es una excelente herramienta para el mundo del hacking ético, orientada al crackeo y descifrado de hashes, entre todas las funcionalidades destacan el descifrado de hashes online, se pueden subir archivos grandes y comprobar múltiples hashes, identificación del tipo de hash, comparte diccionarios y recursos útiles para el crackeo, etc...
- [**CrackStation**](https://crackstation.net/): Es un servicio online que nos permite crackear hashes de contraseñas. Utiliza un diccionario con más de 190GB, y más de 1.5 billones de contraseñas.
- [**CyberChef**](https://gchq.github.io/CyberChef/): Es una herramienta de ciberseguridad de código abierto desarrollada por el servicio de inteligencia del Reino Unido que permite a los usuarios manipular y analizar datos de manera sencilla y visual, actuando como una "navaja suiza" para tareas como cifrado, decodificación, compresión y conversiones de formato. Su interfaz web permite realizar estas operaciones, como decodificar datos en Base64, cifrar mensajes o analizar diferentes tipos de archivos, directamente en el navegador web.
- [**HaveIBeenPwned**](https://haveibeenpwned.com/): Es un sitio web que permite a los usuarios de Internet comprobar si sus datos personales se han visto comprometidos por violaciones de datos. El servicio recopila y analiza cientos de ficheros de bases de datos que contienen información sobre miles de millones de cuentas filtradas, y permite a los usuarios buscar su propia información introduciendo su nombre de usuario o dirección de correo electrónico.
- [**Whatcms**](https://whatcms.org/): Es una herramienta poderosa que ayuda a determinar el CMS de un sitio web dado.
- [**Linuxcert**](http://linuxcert.ir/): Es una pagina web pensada para quienes desean aprender linux desde cero o prepararse para las certificaciones oficiales del linux Professional Institute (LPI).
- [**Devdocs**](https://devdocs.io/): Es un navegador de documentación gratuito, de código abierto y optimizado para desarrolladores, que consolida la documentación de múltiples lenguajes de programación, librerías, frameworks y herramientas en una interfaz unificada, rápida y con capacidad de búsqueda instantánea.

**Distribuciones para Pentesting**

Para llevar a cabo las labores de *pentesting* se necesita un buen arsenal de herramientas, que se pueden instalar manualmente en el sistema operativo cuando se vayan necesitando o se puede emplear algunas de las distribuciones específicamente creadas para esta tarea. La segunda opción es la mas recomendable y la más empleada ya que facilita enormemente el trabajo y ahorra una gran cantidad de tiempo. Entre las distribuciones disponibles destacan las siguientes:

- **[Kali Linux](https://www.kali.org/):** Distribución de seguridad basada en Debian desarrollada por la empresa *Offensive Security*. Dispone de numerosas opciones de instalación. Tambien dispone de un enorme repositorio de paquetes donde se incluyen nuevas herramientas con cada nueva versión, Lo que facilita la instalación automatizada de estas.
- **[ParrotOS](https://parrotsec.org/):** Distribucion de seguridad basada en Debian. En 2022 comenzó una alianza con HackTheBox para mejorar su desarrollo e incluirla en la plataforma a través de la web.
- **[BlackArch](https://blackarch.org/):** Distribución de seguridad basada en Arch Linux con mas de 2800 herramientas en sus repositorios.
- **[CommandoVM](https://github.com/mandiant/commando-vm):** Es un conjunto de herramientas para convertir el sistemas operativo Windows en una distribución de seguridad ofensiva. Creada por la empresa "*Mandiant*".

**Creación de un laboratorio**

A la hora de practicar las acciones de pentesting es necesario disponer de un laboratorio con distintos equipos, de modo que se disponga de distintos Sistemas Operativos y aplicaciones con vulnerabilidades diferentes. Dado que montar un laboratorio con equipos físicos seria muy costoso y dificil de mantener, es bastante habitual optar por la virtualización, puesto que con unos recursos más limitados se puede disponer de equipos suficientes para practicar, con la ventaja añadida de que si se dañan se pueden revertir al estado inicial sin tener que reinstalarlos desde cero.

Existen plataformas que ponen a disposición del público entornos virtuales en los que practicar. Esta seria la mejor opción de cara a practicar, dado que suelen ir notando las Máquinas Virtuales con cierta regularidad y, además, algunas de ellas proporcionan laboratorios que simulan redes, de modo que se puede utilizar un equipo vulnerado para pivotar y acceder a la red interna hasta lograr tomar el control de todos los equipos. Como inconveniente principal, estos entornos son generalmente de pago, salvo pases temporales o laboratorios reducidos, por lo que hay que habrá que considerar si el presupuesto permite optar por esta opción.

Las posibilidades son múltiples: se pueden utilizar Máquinas Virtuales independientes descargadas de internet o crear Máquinas Virtuales propias, utilizando aplicaciones y/o configuraciones vulnerables; se puede crear un laboratorio con varios equipos en una misma red para practicar los movimientos laterales o, incluso, crear un dominio Windows con su controlador de dominio y diferentes servidores y clientes. La limitación en este caso viene dada por el procesador y por la cantidad de memoria disponible en el equipo utilizado, aparte de por el presupuesto disponible para las licencias de Windows, si se opta por esta opción.

**Repositorios de CTF Challenges & Writeups**

Para practicar y mejorar nuestras habilidades disponemos de multitud de entornos de pruebas que simulan escenarios reales y que han sido diseñados para ser explotados.

Los retos de captura la bandera o **Capture The Flag** (*CTF*) consisten en la obtención de un código oculto (*flag*) en el reto, que solo es accesible para aquellos que descubren la vulnerabilidad o el punto débil del reto. En este tipo de retos prima el resultado sobre el proceso, por lo que no hay que dar explicaciones de cómo se ha logrado resolver. Basta con obtener la bandera para demostrar que se tienen las habilidades que llevan a su resolución. Para evitar que puedan hacer trampas existen códigos de conductas que se deben respetar. El más importante es no hacer pública la solución a un reto, denominado *writeup* o *walkthrough*, hasta que el reto deje de estar activo.

Existen numerosas plataformas de internet donde se puede practicar todo este tipo de retos, algunos de ellos son:

- [**Atenea**](https://atenea.ccn-cert.cni.es/home): Plataforma creada por el CCN-CERT que tiene numerosos retos en distintas categorías. Además se pueden consultar todos los retos d años pasados. Tiene una sección "*Academia*" donde se explican conceptos teóricos y prácticos de las distintas disciplinas.
- [**Academia Hacker**](https://www.incibe.es/ed2026/talento-hacker/academia-hacker): Creada reciente por el INCIBE, dispone de una sección de retos descargables organizados en diferentes niveles de dificultad. Además, ofrece el solucionario (*writeup*) de todos ellos. Las academia ofrece la posibilidad de inscribirse en talleres temáticos que se convocan a lo largo del año y también organiza una competición CTF para descubrir talento y seleccionar al equipo nacional que forma parte de las competiciones de hacking que se organizan a nivel europeo y mundial.
- [**PicoCTF**](https://picoctf.org/): Es una plataforma de retos creada por la Universidad Carnegie Mellon. Realiza una competición anual orientada a estudiantes de secundaria y educación superior, con retos realmente exigentes. En su web también ofrece una sección con recursos de aprendizaje. En la plataforma de retos se encuentran accesibles todos los retos de las competiciones realizadas desde 2019 por lo que es un buen lugar para entrenar y poner en práctica nuestra habilidades.
- [**CTF Time**](https://ctftime.org/): Es la web de referencia para buscar eventos CTF que se van a realizar en el futuro o que ya se han realizado. Incluye clasificaciones de equipos y enlaces a las soluciones de los retos ya realizados en los CTF.

Por otro lado, existen plataformas orientadas principalmente a la resolución de máquinas, pero pueden incluir otro tipos de retos. Las mas relevantes son:

- [**HackTheBox**](https://www.hackthebox.com/): Esta empresa fundada en 2017 por James Hooker, Haris Pylarinos y Aris Zikopoulos, tiene más de dos millones de usuarios y es el referente de este tipo de plataformas, ya que la dificultad y grado de profesionalidad de sus máquinas en un aspecto a destacar. Dispone de un conjunto de unas 20 máquinas cativas de dificultades *easy*, *medium*, *hard* e *insane*, cuya resolución otorga puntos al usuario que en función del numero y nivel de máquinas vulneradas a adquiere un ranking (*rank*). Cualquier usuario registrado puede enfrentarse a estas máquinas que tras un cierto tiempo se retiran por otras nuevas.
- [**TryHackMe**](https://tryhackme.com/): Esta plataforma ofrece laboratorios de aprendizaje, llamados *room*, con una serie de tareas guiadas que explican el proceso paso a paso para aprender nuevos conceptos, manejar una herramienta, explotar un servicio o una máquina completa, etc..., Por lo que es un lugar excelente para aprender y practicar. Además, existen otros laboratorios de tipo CTF que consisten en máquinas vulnerables donde no se ofrece ninguna pista para obtener las banderas, donde es posible poner a prueba nuestro nivel. También dispone de redes de máquinas (*networks*). Existen aboratorios de acceso gratuito y otros solo accesibles mediante suscripción.
- [**VulnHub**](https://www.vulnhub.com/): Es un repositorio de máquinas virtuales vulnerables creadas por la comunidad de acceso gratuito. Hay más de 700 laboratorios para descargar, normalmente en formato *OVA* (*VirtualBox*). Actualmente, el proyecto está promocionado por la empresa Offensive Security.
- [**HackMyVM**](https://hackmyvm.eu/): Otro repositorio de máquinas virtuales vulnerables libres que se ha creado recientemente. Existe la opción de destacar las imágenes de forma anónima o registrarse en la plataforma para enviar las banderas obtenidas y registrar nuestro progreso. Hay más de 200 máquinas con tres niveles de dificultad: *fácil*, *media* y *difícil*.
- [**Proving Grounds**](https://www.offsec.com/products/proving-grounds/): Plataforma creada por la empresa Offensive Security con dos versiones, **Play** (*gratuita*) y **Practice** (de *pago*). PG Play es una plataforma online que incluye las maquina de la plataforma VulnHub con tres horas diarias de acceso, mientras que PG Practice no tiene limitación de tiempo, incluye máquinas con SO Windows y máquinas especiales creadas por los expertos de la empresa.
- [**TheHackersLabs**](https://thehackerslabs.com/).
- [**Vulnyx**](https://vulnyx.com/).
- [**DockerLabs**](https://dockerlabs.es/#/).
- [**BugBountyLabs**](https://bugbountylabs.com/).

Es posible encontrar otras VM virtuales fuera de estas paginas, algunas de las cuales han sido desarrolladas por los creadores de la herramienta **Metasploit**. Por la cantidad de vulnerabilidades que presenta, a efectos didácticos y de asimilación de conceptos y metodología es interesante utilizar [Metasploitable2](https://sourceforge.net/projects/metasploitable/), teniendo en cuenta que muchas de sus vulnerabilidades son muy antiguas y no se van a encontrar en entornos reales a día de hoy.

Otra VM vulnerable interesante es [Metasploitable3](https://github.com/rapid7/metasploitable3), puesto que es una de las pocas que tienen una versión con el sistema operativo **Windows**.

**Damn Vulnerable Web App (DVWA)** es una aplicación virtual vulnerable a los ciberataques web más conocidos y utilizados por hackers. El propósito de esta aplicación es entender cómo funcionan estos ataques y, además, aprender a identificar fallos de seguridad en otros sitios web. No obstante, [DVWA](https://github.com/digininja/DVWA) es un entorno legal y seguro, en donde puedes practicar estas técnicas todo lo que desees.

Una vez configurado el laboratorio con la Máquina Virtual atacante y las Máquinas Virtuales vulnerables se puede comenzar a practicar. **¡¡¡Happy Hacking!!!**.

**Plataformas de Recompensas (Bug Bounty)**

Un programa de recompensas (Bug Bounty) es un mecanismo por el que grandes empresas, fabricantes, etc..., pagan una cantidad económica a un hacker por reportar vulnerabilidades en sus sistemas o en su software. Es una forma de incentivar la búsqueda y descubrimiento de vulnerabilidades de manera ética para que sean reportadas antes de que caigan en malas manos.

El programa de recompensas puede estar abierto para que participe cualquier persona o puede ser privado, de modo que la empresa elige a las personas que pueden participar en él. Normalmente, las empresas que comienzan un programa de recompensas lo hacen de forma privada, y con el paso del tiempo y conforme van adquiriendo experiencia y confianza lo hacen público.

Los sitios web de las empresas suelen tener un lugar para informar sobre sus programas de recompensas. El **RFC 91156** aceptado en 2022 por el IETF establece el fichero **security.txt** como la forma recomendada para informar a los investigadores de seguridad cómo reportar los fallos de seguridad que encuentren. Este fichero se puede situar en la raíz del dominio o en la carpeta **/.well-known/**. Si no existe el fichero, no significa que esa empresa no disponga de un programa de recompensas, ya que no es algo obligatorio.

Las empresas suelen gestionar sus programas de recompensas a través de las plataformas intermediarias que existen. Las mas conocidas son:

- [**Bugcrowd**](https://www.bugcrowd.com/bug-bounty-list/): Una de las plataformas principales a nivel global donde están los programas de recompensas de las mayores empresas.
- [**HackerOne**](https://www.hackerone.com/bug-bounty-programs): Similar a la anterior, es una de las plataformas de recompensas más importantes con una lista de programas públicos muy extensa.
- [**Intigriti**](https://www.intigriti.com/): Plataforma de recompensas de ámbito europeo cuya sede se encuentra en Bélgica. Financiada con fondos de la Unión Europea, también dispone de programas para evaluar la seguridad de las herramientas de la Comisión y otros organismos europeos.
- [**Immunefi**](https://immunefi.com/): Esta plataforma de recompensas está enfocada a la protección de activos digitales y proyectos DeFi (Decentralized Finance) como monederos de criptomonedas o **smart contracts**, la conocida como Web3. Las cuantías que se pagan como recompensas son elevadas ya que un fallo de seguridad en esos sistemas puede llevar a la pérdida de grandes sumas de dinero.

**CTF Challenges & Writeups**

Este repositorio contiene mis soluciones, scripts y notas relacionadas con retos de *CTF* (Capture The Flag). El objetivo es practicar y mejorar habilidades en *Ciberseguridad*, *Hacking Ético* y *Pentesting*.

Mis soluciones *CTF* (Capture The Flag):
- [x] [Máquina Shop (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/07/maquina-shop-vulnyx.html) - Easy.
- [x] [Máquina Basic (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/08/maquina-basic-vulnyx.html) - Low.
- [x] [Máquina Experience (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/08/maquina-experience-vulnyx.html) - Low.
- [x] [Máquina Infected (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/08/maquina-infected-vulnyx.html) - Low.
- [x] [Máquina Mux (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/08/maquina-mux-vulnyx.html) - Low.
- [x] [Máquina Wicca (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/08/maquina-wicca-vulnyx.html) - Low.
- [x] [Máquina Zero (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/09/maquina-zero-vulnyx.html) - Low.
- [x] [Máquina Blogger (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/09/maquina-blogger-vulnyx.html) - Low.
- [x] [Máquina Diff3r3ntS3c (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/09/maquina-diff3r3nts3c-vulnyx.html) - Low.
- [x] [Máquina Eternal (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/09/maquina-eternal-vulnyx.html) - Low.
- [x] [Máquina Build (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/10/maquina-build-vulnyx.html) - Low.
- [x] [Máquina Agent (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/10/maquina-agent-vulnyx.html) - Low.
- [x] [Máquina Exec (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/10/maquina-exec-vulnyx.html) - Low.
- [x] [Máquina HackingStation (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/10/maquina-hackingstation-vulnyx.html) - Low.
- [x] [Máquina Look (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/11/maquina-look-vulnyx.html)- Low.
- [x] [Máquina Share (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/11/maquina-share-vulnyx.html) - Low
- [x] [Máquina Plot (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/11/maquina-plot-vulnyx.html) - Low
- [x] [Máquina Noob (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/11/maquina-noob-vulnyx.html) - Low
- [x] [Máquina Lower (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/11/maquina-lower-vulnyx.html) - Low.
- [x] [Máquina Lower2 (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/12/maquina-lower2-vulnyx.html)- Low.
- [x] [Máquina Deploy (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/12/maquina-deploy-vulnyx.html) - Low.
- [x] [Máquina Lower3 (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/12/maquina-lower3-vulnyx.html) - Low.
- [x] [Máquina Lower4 (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/12/maquina-lower4-vulnyx.html) - Low.
- [x] [Máquina Lower5 (Vulnyx)](https://unhackeretico-notes.blogspot.com/2026/01/maquina-lower5-vulnyx.html) - Low.
- [x] [Máquina Lower6 (Vulnyx)](https://unhackeretico-notes.blogspot.com/2026/01/maquina-lower6-vulnyx.html) - Low.
- [x] [Máquina Lower7 (Vulnyx)](https://unhackeretico-notes.blogspot.com/2026/01/maquina-lower7-vulnyx.html) - Low.
- Máquina Loweb (Vulnyx) - Low.
