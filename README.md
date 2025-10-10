**Bienvenida:**

Cuando una persona se quiere introducir en el mundo de la **ciberseguridad** desde el punto de vista **ofensivo**, uno de los principales problemas que suele tener es encontrar la información necesaria para empezar, no por la falta de la misma, sino más bien justo por lo opuesto: *existe un exceso de información que puede provocar frustración por empezar con aspectos demasiado complejos o por no estar estructurada*.

Este repositorio tiene como objetivo que todas aquellas personas que se quieren iniciar en el *"hacking ético"* tengan los recursos necesarios y conozcan la metodología que se debe seguir durante el proceso, se da por hecho que el lector dispone de conocimientos previos de **Informática** y **Redes**, que resultan muy necesarios para este mundo. Por ello, en este  repositorio se parte del supuesto de que el lector sabe manejar con soltura Sistemas Operativos **Linux** y **Windows** y posee unos conocimientos básicos de **Protocolos de Red**, aunque esto no quiere decir que sea imprescindible conocer hasta el mínimo detalle todos los protocolos ni ser un experto administrador de sistemas. Se sobreentiende que la propia inquietud del lector interesado en la ciberseguridad le animará a profundizar en aquellos aspectos en los que detecte que deberá tener mayores conocimientos.

No dudes en volver de vez en cuando para ver nuevos *contenidos* sobre **ciberseguridad**. Este repositorio se irá actualizando progresivamente a medida que avance y adquiera nuevos conocimientos en el mundo del *hacking ético*. Mi objetivo es compartir lo que voy aprendiendo, desde lo mas básico hasta técnicas mas avanzadas.

Puedes acceder a la web para ver los contenidos haciendo click [aquí](https://unhackeretico-notes.blogspot.com/).

**Perfil de un buen hacker o ciberinvestigador**

Los conocimientos que debe adquirir un hacker se sustentan sobre una base sólida de conocimientos básicos y avanzados del funcionamiento de los sistemas informáticos. Esto incluye materia o áreas como:

- **Arquitectura de computadoras y lenguaje ensamblador:** Constituye la base del funcionamiento de los elementos hardware y software de los sistemas informáticos.
- **Redes de ordenadores y protocolos de red:** Esto incluye las diferentes arquitecturas de red, los tipos de redes (cableadas, inalámbricas, fibra óptica...), los dispositivos que intervienen en las redes de comunicaciones, la capa de protocolos TCP/IP y OSI y los protocolos de encaminamiento.
- **Administración de sistemas operativos:** Instalar y configurar sistemas operativos, tanto Windows como GNU/Linux, que incluyen elementos como políticas de seguridad, permisos y roles de usuarios y grupos, administración de servicios (DHCP, DNS, FTP, HTTP, SSH...), administración de dominios, gestión de cuotas, configuración de reglas de cortafuegos, etc...
Gestión y administración de bases de datos: Conocer los diferentes lenguajes de modelado de datos (SQL y noSQL), diferentes sistemas gestores de bases de datos (relacionales, orientados a objetos), su estructura y comandos de administración.
- **Lenguajes de programación:** es un área muy amplia que va desde lenguajes de bajo nivel (C, C++, Go, Rust), hasta lenguajes orientados a objetos (Java, C#), programación orientada a aplicaciones móviles (Android, iOS), tecnologías web (Javascript, Jakarta EE framework, PHP, ASP, NodeJS), lenguajes de scripting (Python, Bash, PowerShell). La lista no es exhaustiva y puede ser que uno de los lenguajes o tecnologías encaje en más de una categoría.
- **Criptografía:** Serán útiles los conocimientos desde dos perspectivas, los fundamentos matemáticos detrás de los algoritmos criptográficos y la aplicación práctica de técnicas criptográficas.

**Certificaciones mas relevantes en el Ámbito de la Seguridad Ofensiva:**

- **CEH (EC Council Certified Etihical Hacker):** Es una de las certificaciones más extendidad y demandadas, pero suele ser muy criticada por su bajo contenido práctico, aunque esto ha cambiado a partir de la version 12 (CEHv12).
- **Pentest+:** Certificado de CompTIA (The Computing Techology Industry Association) con un nivel intermedio. A diferencia de otras certificaciones, esta incluye elementos de todas las fases de un test de intrusión.
- **eJPT (eLearnSecurity Junior Penetration tester):** Esta certificación está enfocada a expertos de IT que comienzan en el area del pentesting; por tanto, es una certificación de nivel básico.
- **eCPPT (eLearnSecurity Certified Professional Penetration Tester):** Certificación de nivel avanzado sobre test de intrusión.
- **HTB CPTS (HackTheBox Certified Penetration Testing Specialist):** Certificación altamente práctica que evalúa las habilidades de pruebas de penetración de los candidatos, es una certificación creada por la plataforma HackThebox.
- **PNPT (TCM Security Practical Network Penetration Tester):** Certificación práctica de pruebas de penetración creada por la empresa TCM Security.
- **OSCP (Offensive Security Certified Professional):** Esta certificación posiblemente sea la más temida y codiciada en el sector por su nivel de dificultad; tambien es una de las que más inversión económica precisa para realizarla. Su lema "*Try Harder*", anima a aquellos que no han conseguido su objetivo a seguir intentándolo y nunca tirar la toalla.
- [Especialización de Ciberseguridad en Entornos de las Tecnologías de la Información (CETI)](https://www.todofp.es/que-estudiar/familias-profesionales/informatica-comunicaciones/ce-ciberseguridad-entornos-tecnologias-informacion.html): Es un curso de especialización dirigido a titulados de ciclos superiores de Informática, es ideal para quienes buscan una formación sólida, practica y orientada al mundo laboral. Esta especialidad profundiza en áreas como:
    - Seguridad de Redes y Sistemas.
    - Análisis Forense.
    - Hacking Ético y pruebas de penetración.
    - Criptografía.
    - Gestión de incidentes.
    - Normativas y cumplimiento (como el ENS y el RGPD).

Si está empezando en el *hacking ético* como me imagino, mi consejo es que no se obsesione con esto, el aprendizaje es largo y lleva su tiempo adquirir los conocimientos suficientes. Tómese su tiempo para ganar experiencia.

**Distribuciones para Pentesting:**

- **[Kali Linux](https://www.kali.org/):** Distribución de seguridad basada en Debian desarrollada por la empresa *Offensive Security*. Dispone de numerosas opciones de instalación. Tambien dispone de un enorme repositorio de paquetes donde se incluyen nuevas herramientas con cada nueva versión, Lo que facilita la instalación automatizada de estas.
- **[ParrotOS](https://parrotsec.org/):** Distribucion de seguridad basada en Debian. En 2022 comenzó una alianza con HackTheBox para mejorar su desarrollo e incluirla en la plataforma a través de la web.
- **[BlackArch](https://blackarch.org/):** Distribución de seguridad basada en Arch Linux con mas de 2800 herramientas en sus repositorios.
- **[CommandoVM](https://github.com/mandiant/commando-vm):** Es un conjunto de herramientas para convertir el sistemas operativo Windows en una distribución de seguridad ofensiva. Creada por la empresa "*Mandiant*".

**Recursos Utiles:**

A continuación os dejo unos links utiles. 

- [Hacktricks](https://book.hacktricks.wiki/es/index.html): página muy recomendable que recopila técnicas de explotación, detección de vulnerabilidades, escalada de privilegios, fallos de configuración, bastionado de servicios y un largo etcétera.
- [Hacktricks Cloud](https://cloud.hacktricks.wiki/es/index.html): página muy recomendable orientada a técnicas de pentesting en servicios en la nube.
- [PortSwigger](https://portswigger.net/web-security/all-materials): academia gratuita en el que se explican las vulnerabilidades tipo web más comunes. Además, dispone de varios laboratorios con ejercicios de distintos niveles para practicar con algunas de ellas.
- [RevShells](https://www.revshells.com/): página muy recomendable sobre las distintas técnicas en el lanzamiento de *shells reversas* de diferentes tipos.
- [PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings): página muy recomendable sobre las distintas técnicas en el lanzamiento de *shells reversas* de diferentes tipos, explorar otros metodos y aplicar opciones avanzadas.
- [GTFOBins](https://gtfobins.github.io/): pagina muy recomendable de binarios de Unix que pueden usarse para eludir las restricciones de seguridad locales en sistemas mal configurados.
- [LOLBAS](https://lolbas-project.github.io/): pagina muy recomendable en la que se describe como se pueden aprovechar las herramientas presentes por defecto en Windows para obtener información local de este.
- [CrackStation](https://crackstation.net/): Es un servicio online que nos permite crackear hashes de contraseñas. Utiliza un diccionario con más de 190GB, y más de 1.5 billones de contraseñas.

**Repositorios de CTF Challenges & Writeups:**
- [TheHackersLabs](https://thehackerslabs.com/).
- [Vulnyx](https://vulnyx.com/).
- [VulnHub](https://www.vulnhub.com/).
- [DockerLabs](https://dockerlabs.es/#/).
- [BugBountyLabs](https://bugbountylabs.com/).

**CTF Challenges & Writeups:**

Este repositorio Contiene mis soluciones, scripts y notas relacionadas con retos de *CTF* (Capture The Flag). El objetivo es practicar y mejorar habilidades en *Ciberseguridad*, *Hacking Ético* y *Pentesting*.

Mis soluciones *CTF* (Capture The Flag):
- [x] [Máquina shop (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/07/maquina-shop-vulnyx.html) - Easy.
- [x] [Máquina Basic (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/08/maquina-basic-vulnyx.html) - Low.
- [x] [Máquina Experience (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/08/maquina-experience-vulnyx.html) - Low.
- [x] [Máquina Infected (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/08/maquina-infected-vulnyx.html) - Low.
- [x] [Máquina Mux (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/08/maquina-mux-vulnyx.html) - Low.
- [x] [Máquina Wicca (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/08/maquina-wicca-vulnyx.html) - Low.
- [x] [Máquina Zero (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/09/maquina-zero-vulnyx.html) - Low.
- [x] [Máquina blogger (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/09/maquina-blogger-vulnyx.html) - Low.
- [x] [Máquina Diff3r3ntS3c (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/09/maquina-diff3r3nts3c-vulnyx.html) - Low.
- [x] [Máquina Eternal (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/09/maquina-eternal-vulnyx.html) - Low.
- [x] [Máquina Build (Vulnyx)](https://unhackeretico-notes.blogspot.com/2025/10/maquina-build-vulnyx.html) - Low.
- Máquina Agent (Vulnyx) - Low.

**Descargo de Responsabilidad:**

Este repositorio tiene como único objetivo la **divulgación educativa y ética** de conocimientos relacionados con la *ciberseguridad*, *hacking ético* y *protección digital*.

Toda la información publicada está destinada a promover *buenas prácticas de seguridad informática*, ayudar a usuarios y profesionales a **proteger sus sistemas**, y **no debe utilizarse para actividades ilegales** o **no autorizadas**.  

**El autor de este repositorio no se hace responsable del mal uso de los contenidos aquí compartidos**. *Se recuerda que el acceso no autorizado a sistemas informáticos está penado por la ley*.

En *España*, el **código penal** establece los supuestos en los que un hacker podría estar cometiendo un delito. Son de interés los artículos comprendidos *entre el 197 y el 201*, *especialmente el 197bis y el 197ter*, que se incorporan al código penal en el año 2015:

- **Artículo 197bis.1.** "*El que por cualquier medio o procedimiento, vulnerando las medidas de seguridad establecidas para impedirlo, y sin estar debidamente autorizado, acceda o facilite a otro el acceso al conjunto o una parte de un sistema de información o se mantenga en él en contra de la voluntad de quien tenga el legítimo derecho a excluirlo, será castigado con pena de prisión de seis meses a dos años*".
- **Articulo 197bis.2.** "*El que mediante la utilización de artificios o instrumentos técnicos, y sin estar debidamente autorizado, intercepte transmisiones no públicas de datos informáticos que se produzcan desde, hacia o dentro de un sistema de información, incluidas las emisiones electromagnéticas de los mismos, será castigado con una pena de prisión de tres meses a dos años o multa de tres a doce meses*".
- **Artículo 197ter.** "*Será castigado con una pena de prisión de seis meses a dos años o multa de tres a dieciocho meses el que, sin estar debidamente autorizado, produzca, adquiera para su uso, importe o, de cualquier modo, facilite a terceros, con la intención de facilitar la comisión de alguno de los delitos a que se refieren los apartados 1 y 2 del artículo 197 o el artículo 197 bis:*
  
  - *un programa informático, concebido o adaptado principalmente para cometer dichos delitos; o*
  - *una contraseña de ordenador, un código de acceso o datos similares que permitan acceder a la totalidad o a una parte de un sistema de información*".

Por tanto, de lo anterior se deduce que es totalmente imprescindible tener la autorización correspondiente por medio de un contrato en donde se establezca claramente el propósito y ámbito de la actividad. En caso de que se realice una investigación sobre un sistema informático sin tener dicha autorización, aunque no se haga un uso malintencionado de la información y reporten las vulnerabilidades encontradas, se podría ser denunciado.

**Utiliza siempre el conocimiento con responsabilidad**. La mejor defensa comienza con la educación.
