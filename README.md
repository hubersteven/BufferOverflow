
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
  
</p>

<h2 align="center">Créditos de autores</h2>

<p>
  
</p>
