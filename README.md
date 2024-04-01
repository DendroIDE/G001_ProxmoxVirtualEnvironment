# Proxmox Virtual Environment (Graphical o GUI basada en web)

------------

> Proxmox VE es una plataforma de virtualización de código abierto que permite gestionar máquinas virtuales y contenedores de forma centralizada. Ofrece características avanzadas para la creación, gestión y monitorización de entornos de virtualización, incluyendo clusters de servidores y almacenamiento compartido.

La **Guía de Virtual Machines 001 DendroIDE Code** se dedica a la explicación de la instalación y configuración de la plataforma: **Proxmox Virtual Environment 8.1**, utilizando una máquina virtualizada con **Oracle VM VirtualBox** el cual es un software de virtualización para arquitecturas x86/amd64.

## Requisitos mínimos del sistema recomendado por DendroIDE Code.

### Requisitos de Hardware
- **Procesador:**
	* Procesador de novena generación o superior Intel o AMD con 64 bits en la unidad central de proceso.
	* Procesador con mínimo cuatro unidades centrales y núcleos de procesamiento que pueden ejecutar hasta cuatro procesos de manera simultánea o superior.
	* Procesador con mínimo cuatro unidades centrales y núcleos de procesamiento que pueden ejecutar hasta cuatro procesos de manera simultánea o superior.
	* Procesador compatible con la virtualización por hardware (Intel VT-x/AMD-V) para usar KVM.

- **Memoria (RAM):**
	* 8 GB de memoria RAM o superior.

- **Almacenamiento:**
	* Disco duro mecánico o SSD con al menos 128 GB de espacio libre para la instalación del sistema operativo y almacenamiento de datos.
	* Se recomienda un almacenamiento adicional con almenos 256 GB de espacio libre para almacenar imagenes isos, máquinas virtuales, respaldos, templates y datos de contenedores.

- **Red:**
	* Se requiere una o más tarjetas de red Ethernet compatibles con la infraestructura del servidor a implementar
	* Se recomienda una conexión de red estable y de alta velocidad para un rendimiento óptimo..

### Requisitos de Software
- **Sistema Operativo:** 
	* Proxmox VE 8.1 es un sistema operativo basado en Debian, por lo que no se requiere un sistema operativo previamente instalado.

- **Hypervisor:** 
	* Proxmox VE utiliza KVM (Kernel-based Virtual Machine) como hipervisor para la virtualización de máquinas.

- **Navegador Web:** 
	* Se recomienda tener un navegador web moderno y compatible (como Google Chrome, Mozilla Firefox, o Microsoft Edge) para acceder a la interfaz de administración basada en web.

#### Antes de comenzar
------------
> - Recuerda que la instalación de Proxmox se realizará en un entorno virtualizado utilizando Oracle VM Virtual Box 7.0.
> - Es importante verificar la compatibilidad del hardware, especialmente en lo que respecta a los controladores de red y almacenamiento, para garantizar un funcionamiento correcto.
> - Se recomienda revisar la documentación oficial de Proxmox VE para obtener información detallada sobre los requisitos del sistema y la compatibilidad del hardware.

### Proceso de instalación de Proxmox Virtual Environment utilizando Oracle VM VirtualBox 7.0

* #### **Paso 01.**
  Navegar al sitio web oficial de [Proxmox Virtual Environment](https://www.proxmox.com/en/) para proceder a la descarga del software.
  
  ![Sitio Oficial de Proxmox Virtual Environment](<src/001. Sitio de descarga oficial Proxmox VE.png>)

* #### **Paso 02.**
  Descargar la imagen ISO que contiene el instalador con la versión de [Proxmox VE 8.1](https://enterprise.proxmox.com/iso/proxmox-ve_8.1-2.iso).
  
  ![Descarga de Proxmox VE 8.1 ISO Installer](<src/002. Descarga de la imagen ISO de Proxmox VE 8.1.png>)

* #### **Paso 03.**
  Al finalizar la descarga del instalador de Proxmox VE 8.1 contenido en la imagen ISO, procederemos a la creación de la máquina virtual que ejecutará el entorno  de virtualización de servidores de código abierto. Para ello, es necesario abrir el software de Oracle VM VirtualBox 7.0.

  ![Oracle VM VirtualBox 7.0](<src/003. Software Oracle Virtual Box 7.0.png>)

* #### **Paso 04.**
  En el menú principal del software Oracle VM VirtualBox 7.0, seleccionar el submenú **Máquina**, y luego la opción **Nueva**. También funcionaría con el comando **Ctrl + N** en Windows OS, o utilizando la opción secundaria presentada en la pantalla principal definida como **Nueva**.
  
  ![Selección opción - Nueva](<src/004. Creacion de una nueva máquina virtual.png>)

* #### **Paso 05.**
  Asignar el nombre a la máquina virtual, para caso de la guía el nombre será: Proxmox VE 8.1.
  
  ![Nombre de la máquina virtual](<src/005. Asignación del nombre de la máquina virtual.png>)

* #### **Paso 06.**
  Se debe establecer la ubicación de la máquina virtual, ésta puede estar alojada en la ruta predeterminada por el software de Oracle VM VirtualBox 7.0 o puede ser almacenada en una ubicación predefinida por el usuario, las únicas recomendaciomnes son que primero el almacenamiento sea fijo y que dicho almacenamiento tenga espacio suficiente parael correcto funcionamiento del sistema.

  ![Establecer la ubicación de la máquina virtual - Paso 1](<src/006. Establecer la ubicacion de la máquina virtual.png>)

  ![Establecer la ubicación de la máquina virtual - Paso 2](<src/007. Establecer la ubicacion de la máquina virtual.png>)

* #### **Paso 07.**
  Navegar hasta la ubicación de la imagen ISO de Proxmox VE 8.1 descargada y seleccionarla.

  ![Seleccionar imagen ISO de Proxmox VE 8.1 - Parte 1](<src/008. Selección de la imagen ISO de Proxmox VE 8.1.png>)

  ![Seleccionar imagen ISO de Proxmox VE 8.1 - Parte 2](<src/009. Selección de la imagen ISO de Proxmox VE 8.1.png>)
  
* #### **Paso 08.**
  Proxmox Virtual Environment (VE) está basado en Debian GNU/Linux. Debian es una distribución de Linux estable y popular que ha servido como base para numerosos proyectos y derivados. Proxmox VE toma la robustez y estabilidad de Debian y la combina con herramientas de virtualización y administración, como KVM (Kernel-based Virtual Machine) y OpenVZ, para ofrecer una plataforma de virtualización completa y poderosa. Por lo tanto, seleccionamos el tipo y versión del sistema operativo.
  
  ![Elección del tipo de sistema operativo.](<src/010 Elección del tipo de sistema operativo.png>)
  
  ![Elección de la version del tipo de sistema operativo.](<src/011 Elección de la versión del sistema operativo.png>)
  
* #### **Paso 09.**
  Una vez se encuentre asignada la configuración del nombre y sistema operativo de la máquina virtual a utilizar, seleccionar la opción **siguiente**.

  ![Configuración del nombre y sistema operativo de la máquina virtual](<src/012. Configuración del nombre y sistema operativo de la máquina virtual.png>)
  
* #### **Paso 10.**
  Definido como requisito mínimo de hardware, se establece un valor inicial de 8 GB por parte de la memoria ram. En la guía, como parte de estúdio serán definidas 16 GB de memoria ram.

  ![Asignación de 16 GB de memoria ram](<src/013. Asignación de memoria RAM.png>)
  
* #### **Paso 11.**
  Definido como requisito mínimo de hardware, se establece un valor inicial de cuatro unidades centrales de procesamiento. En la guía, como parte de estúdio serán definidas 6 Unidades de CPUs.

  ![Asignación de unidades centrales y núcleos de procesamiento](<src/014. Asignación de unidades centrales y núcleos de procesamiento.png>)
  
* #### **Paso 12.**  
  Una vez se encuentre asignada la configuración del hardware de la máquina virtual a utilizar, seleccionar la opción **siguiente**.
  
  ![Configuración del Hardware de la máquina virtual](<src/015. Configuración del Hardware de la máquina virtual.png>)
  
* #### **Paso 13.**  
  Definido como requisito mínimo de hardware, se establece un valor inicial con al menos 128 GB de espacio libre en un disco duro mecánico o SSD para la instalación del sistema operativo y almacenamiento de datos. Pero, al ser un sistema virtualizado las circunstancias **cambian**. Utilizando Oracle VM VirtualBox 7.0, se establecerá como parte de estudio un disco duro virtual dinámico con 128.00 GB de almacenamiento.

    > En Oracle VM VirtualBox 7.0, un disco virtual es un archivo que representa el disco duro de una máquina virtual. Funciona de manera similar a un disco físico en una computadora real, pero está encapsulado dentro de un archivo en el sistema de archivos del host. Este archivo contiene toda la información y datos almacenados dentro de la máquina virtual, incluidos el sistema operativo, las aplicaciones y los archivos del usuario.
    
    > Los discos virtuales en VirtualBox también pueden ser dinámicos o fijos. Los discos dinámicos crecen según sea necesario para almacenar datos, mientras que los discos fijos reservan todo el espacio definido desde el principio, lo que puede ocupar más espacio en el disco físico pero puede ofrecer un mejor rendimiento.

    > *En **resumen**, un disco virtual en Oracle VM VirtualBox 7.0 es un archivo que simula un disco duro físico y contiene todos los datos de una máquina virtual, permitiendo que la máquina virtual funcione como si estuviera utilizando un hardware físico real.*
    
  ![Asiganción del tipo y tamaño del disco duro de la máquina virtual](<src/016. Asignación del disco duro.png>)
  
* #### **Paso 14.**
  Una vez se encuentre asignada la configuración del disco duro virtual de la máquina virtual a utilizar, seleccionar la opción **siguiente**.
  
  ![Confiuración del disco duro virtual](<src/017. Configuración del disco duro virtual.png>)
  
* #### **Paso 15.**
  Se visualiza un resumen de la máquina virtual en creación. En caso de estar conforme con la configuración realizada y presentada, deberá ser seleccionada la opción **terminar**. Caso contrario, la opción **anterior** permitirá gestionar el cambio de cualquier configuración previa. La opción **cancelar** permite cerrar la pantalla de creación de máquina virtuales y no proceder a realizar cualquier creación o modificación en el sistema.

  ![alt text](<src/018. Resumen de la creación de la máquina virtual.png>)
  
* #### **Paso 16.**
  En el software de Oracle VM VirtualBox 7.0, se visualiza la máquina virtual creada. A continuación, se procede con la configuración avanzada de la máquina virtual que alojará el sistema de Proxmox VE 8.1.

  ![Visualización de la máquina virtual creada](<src/019. Visualización de la máquina virtual creada.png>)

* #### **Paso 17.**
  Seleccionar la máquina virtual creada con el nombre **Proxmox VE 8.1** o *con el nombre que haya sido asignado*, y luego seleccionar la opción de **configuración**, en donde se visualiza la pantalla de configuración con todos los detalles de la máquina virtual creada.

  ![Configuración de la máquina virtual](<src/020. Configuracion de la máquina virtual.png>)

  ![Pantalla de configuración de la máquina virtual](<src/021. Pantalla de configuración de la máquina virtual.png>)

* #### **Paso 18.**
  Se deberá configurar la **red** de la máquina virtual, para ello hay que seleccionar la opción **Red** en la configuración de la máquina virtual.

  ![Configuración de red de la máquina virtual - Parte 1](<src/022. Opción de configuración de red.png>)

  ![Configuración de red de la máquina virtual - Parte 2](<src/023. Pantalla de configuración de la red de la máquina virtual.png>)

* #### **Paso 19.**
  Es recomendable que se configure en tipo adaptador puente, debido a que en VirtualBox esa configuración de red permite que la máquina virtual se comunique directamente con la red física a la que está conectado el host. Esto significa que la máquina virtual obtiene una dirección IP directamente de la red física y puede interactuar con otros dispositivos en esa red como si fuera una máquina física. Para lo cual hay que seleccionar del menú de opciones en **Conectado a:** y escoger la opción de **Adaptador puente**.

  ![Configuración de red en tipo adaptador puente.](<src/024. Configuración de red en tipo adaptador puente.png>)

* #### **Paso 20.**
  Al seleccionar la opción de **adaptador puente**, de manera automática se seleccionará el nombre de la tarjeta de red que la máquina virtual utilizará para comunicarse directamente con la red física a la que se conecta el host o máquina nativa.

  ![Selección del adaptador de red de la máquina virtual.](<src/025. Selección nombre de adaptador de red.png>)

* #### **Paso 21.**
  Una vez se encuentre asignada la configuración de red de la máquina virtual a utilizar, seleccionar la opción **aceptar** y el cuadro de diálogo se cerrará automáticamente.

  ![Configuración de red de la máquina virtual.](<src/026. Configuración de red de la máquina virtual.png>)

* #### **Paso 22.**
  Se presenta la pantalla incial del software Oracle VM VirtualBox 7.0, por lo tanto la configuración de la máquina virtual a finalizado. Para continuar con la instalación del sistema operativo hay que **marcar** e iniciar la máquina virtual establecida seleccionando la opción **iniciar**.

  ![Inicio de la máquina virtual](<src/027. Iniciar la máquina virtual de manera rápida.png>)

  De igual manera, la máquina virtual puede ser iniciada al ser **marcada** y luego seleccionar en la barra de herramientas del software Oracle VM VirtualBox 7.0 la opción **máquina** y escoger en la cinta de opciones **inicar** y finalmente seleccionar **inicio normal**.

  ![Incio de la máquina virtual](<src/028. Iniciar la máquina virtual desde las opciones de la barra de herramientas.png>)

* #### **Paso 23.**
  Aparece la pantalla de bienvenida a Proxmox Virtual Environment 8.1 y comenzará el consumo de recursos configurados de la máquina fisica nativa.

  ![Bienvenida a Proxmox VE 8.1](<src/030. Bienvenida a Proxmox VE 8.1.png>)

* #### **Paso 24.**
  Es conveniente ocultar las notificaciones en el momento de la instalación y uso de Proxmox VE 8.1.
  
  ![alt text](<src/031. Ocultar notificaciones del software Oracle VM VirtualBox 7.0.png>)

* #### **Paso 25.**
  Si al pulsar con un clic en la pantalla de bienvenida a Proxmox Virtual Environment 8.1, y aparece un cuadro de diálogo detallando la información de Oracle VM VirtualBox 7.0 describiendo el uso del mouse, es recomendable marcar la opción **no mostrar este mensaje de nuevo**, y posteriormente seleccionar la opción **capturar**.

  ![Opción de capturar el mouse en Oracle VM VirtualBox 7.0](<src/032. Información de capturar mouse en VirtualBox.png>)

  ![Seleccionar opción de capturar mouse Oracle VM VirtualBox 7.0](<src/033. Seleccionar opción de capturar mouse Oracle VM VirtualBox 7.0.png>)

* #### **Paso 26.**
  La captura de mouse en Oracle VM VirtualBox 7.0, es una característica que te permite "atrapar" o "capturar" el control del mouse dentro de la ventana de la máquina virtual. Cuando se activa la captura del mouse, el cursor del mouse se "encarcela" dentro de la ventana de la máquina virtual, lo que significa que no puede salir de esa ventana a menos que desactives la función de captura.

  > Para activar la captura de mouse en VirtualBox, generalmente solo necesitas hacer clic dentro de la ventana de la máquina virtual. **Además, puedes presionar la tecla derecha Ctrl en tu teclado para activar o desactivar la captura de mouse manualmente.**
  
  ![Tecla para desactivar la captura del mouse](<src/034. Desactivar captura de mouse.png>)

* #### **Paso 27.**
  La ventana de ejecución de la máquina virtual dentro del software Oracle VM VirtualBox 7.0 podría verse afectada en tamaño, por lo tanto se visualiza una barra de desplazamiento (*scrollbar*) que permite deslizar la visualización de la interfaz gráfica de la máquina virtual.
  
  ![Inicio de instalación de Proxmox VE 8.1](<src/035. Inicio de instalación de Proxmox VE 8.1.png>)

  ![Barra de desplazamiento en la interfaz de la ventana de virtualización de Proxmox VE 8.1](<src/036. Deslizamiento scrollbar de la máquina virtual.png>)

* #### **Paso 28.**
  Para iniciar con la instalación de Proxmox VE 8.1, se deberá seleccionar la opción de **Install Proxmox VE (Graphical)**, debido al uso de la guía y a que la interfaz gráfica proporciona un entorno fácil de usar con interacciones de apuntar y hacer clic. Es adecuada para los usuarios que prefieren la navegación visual y se sienten menos cómodos con la línea de comandos.

  ![Instalación de Proxmox VE 8.1 (Graphical)](<src/037. Instalación de Proxmox VE 8.1 (Graphical).png>)

* #### **Paso 29.**
  Proxmox VE 8.1 lanzará automática una serie de comandos hasta aparecer una nueva pantalla de instalación, mientras se realiza la ejecución en la terminal de la máquina virtual es recomendable ocultar las notificaciones de Oracle VM VirtualBox 7.0.

  ![Comandos inciales pre instalación.](<src/038. Ejecución de comandos inciales en Proxmox VE 8.1.png>)

* #### **Paso 30.**
  Aparecerá en pantalla un cuadro de diálogo mostrando la advertencia **no support for hardware-accelerated KVM virtualization detected.** Lo que quiere decir que, al intentar instalar Proxmox en Oracle VM VirtualBox 7.0 no se puede utilizar la virtualización asistida por hardware (KVM) necesaria para ejecutar Proxmox VE 8.1 de manera eficiente. Proxmox VE 8.1 es un hipervisor que utiliza KVM como una de sus tecnologías de virtualización subyacentes. Esto puede deberse a que Oracle VM VirtualBox 7.0 no es compatible con la virtualización KVM en sí misma, ya que utiliza su propia tecnología de virtualización. Por lo tanto, intentar ejecutar Proxmox VE 8.1 dentro de Oracle VM VirtualBox 7.0 puede no ser la mejor opción, ya que Proxmox VE 8.1 está diseñado para ser un hipervisor de nivel de servidor y Oracle VM VirtualBox 7.0 es más adecuado para entornos de escritorio y desarrollo.

  Sin embargo, esta advertencia no necesariamente es maligna. Para continuar se debería seleccionar **Ok**

  ![Advertencia KVM](<src/039. Advertencia KVM.png>)

* #### **Paso 31.**
  En pantalla se visualiza el **acuerdo de licencia para usuario final**, en resumen se define quién tiene el derecho de usar el software, cuántas instancias se pueden desplegar y cómo se puede utilizar. Para continuar se deberá desplazar hacia la parte final de la ventana y luego pulsar **I agree**.

  ![Acuerdo de licencia para el usuario final - Proxmox VE 8.1.](<src/040. Acuerdo de licencia para el usuario final - Proxmox VE 8.1.png>)

  ![Acuerdo de licencia para el usuario final - Proxmox VE 8.1.(<src/041. Acuerdo de licencia para el usuario final.png>)
  
  ![Aceptar el acuerdo de licencia para el usuario final - Proxmox VE 8.1.](<src/042. Aceptar el acuerdo de licencia para el usuario final - Proxmox VE 8.1.png>)
  
* #### **Paso 32.**
  Se debe especificar el disco duro destino de la instalación de Proxmox VE 8.1 en la máquina virtual creada. Anteriormente, en la configuración del hardware se estableció el tamaño del hard disk en 128 GB. Como solo fue creado un disco duro etonces solo se visualizará un disco de almacenamiento en la lista.

  ![Selección del disco duro.](<src/043. Selección del disco duro destino de la instalación.png>)

  ![Selección del disco duro.](<src/044. Selección del disco duro destino de la instalación.png>)

  ![Target Hard Disk.](<src/045. Target Hard Disk.png>)

* #### **Paso 33.**
  Una vez se determine el disco duro destino de la instalación de Proxmox VE 8.1, seleccionar la opción **next**.

  ![Selección target Hard Disk.](<src/046. Selección disco duro de instalación Proxmox VE.png>)

* #### **Paso 34.**
  El instalador de Proxmox VE 8.1 solicita seleccionar la ubicación y la zona horaria para la configuración del sistema.

  ![Localización y zona horaria - Deplazamiento](<src/047. Localización y zona horaria - Deplazamiento.png>)
  
  ![Localización y zona horaria](<src/047. Localización y zona horaria.png>)

* #### **Paso 35.**
  Especificar la ubicación geográfica del servidor o de la máquina virtual. Esto puede hacerse a través de una lista de países o regiones disponibles. La ubicación seleccionada se utiliza para configurar adecuadamente la configuración regional, como el formato de fecha, hora y moneda.

  ![Especificar la ubicación geográfica.](<src/048. Especificar la ubicación geográfica del servidor.png>)

  En caso de la guía y a la ubicación geográfica a la que pertenece la organización DendroIDE Code, se establecerá con el **country** de **Ecuador**.
  *(Escibir el nombre del país necesario.)*

  ![Especificar la ubicación de la máquina virtual.](<src/049. Especificar el país en la ubicación de la máquina virtual.png>)

* #### **Paso 36.**
  Después de seleccionar la ubicación, se establece automáticamente una zona horaria correspondiente a la ubicación. Es fundamental asegurarse de escoger la zona horaria correcta debido a que el sistema mostrará la hora establecida y aplicará los ajustes de horario de verano e invierno arbitrareamente.

  ![Especificar la zona horaria de la máquina virtual.](<src/050. Especificar la zona horaria de la máquina virtual.png>)

  ![Seleccionar la zona horaria de la máquina virtual.](<src/051. Seleccionar la zona horaria de la máquina virtual.png>)

* #### **Paso 37.**
  Una vez seleccionadas la ubicación y la zona horaria, el sistema utilizará esta información para configurar la hora del sistema y otros ajustes relacionados con la localización geográfica.
  Ahora deberá seleccionar el diseño del teclado lo cual, garantiza que las teclas produzcan los caracteres correctos cuando se presionan, lo que es crucial para la entrada de texto precisa y eficiente, especialmente durante la configuración inicial del sistema operativo.

  ![Diseño del teclado de la máquina virtual.](<src/052. Diseño del teclado de la máquina virtual.png>)

* #### **Paso 38.**
  Determinar el diseño del teclado que se utiliza.

  *"U.S. English (USA)"* se refiere al diseño de teclado estándar utilizado en Estados Unidos.

  ![Diseño de teclado - English USA](<src/053 Diseño de teclado - English USA.png>)

  *"United Kingdom (UK)"* se refiere al diseño de teclado estándar utilizado en el Reino Unido.

  ![Diseño de teclado - United Kingdom](<src/054. Diseño de teclado - United Kingdom.png>)

  *"Spanish (ES)"* se refiere al diseño de teclado estándar utilizado en lenguaje español (contiene la letra ñ).  

  ![Diseño de teclado - Spanish](<src/055. Diseño de teclado - Español.png>)

* #### **Paso 39.**
  Una vez identificado el diseño de teclado que se utilizará para la enrada de texto en la máquina virtual, se deberá seleccionar la opción correcta.

  ![Seleccionar el diseño de teclado.](<src/056. Seleccionar el diseño de teclado.png>)

* #### **Paso 40.**
  Una vez se determina la ubicación, la zona horaria y el diseño de teclado destinado a la instalación de Proxmox VE 8.1, se deberá seleccionar la opción **next**.

  ![Ubicación y zona horaria de la máquina virtual.](<src/057. Configuración de la ubicación y la zona horaria.png>)

* #### **Paso 41.**
  Establecer una contraseña de administración y proporcionar una dirección de correo electrónico.

  ![Contraseña del administrador y correo electrónico](<src/058. Contraseña del administrador y correo electrónico.png>)

  ![Contraseña del administrador y correo electrónico](<src/059. Contraseña del administrador y correo electrónico.png>)

* #### **Paso 42.**
  Se deberá establecer una **contraseña** para la cuenta de administrador, posteriormente debe ser **confirmada**. Esta contraseña es necesaria para acceder a la interfaz web de administración de Proxmox y para realizar tareas administrativas. Es importante elegir una contraseña segura y recordarla correctamente, ya que será necesaria para acceder a la interfaz de administración en el futuro.

  ![Contraseña de administración.](<src/060. Contraseña del administrador.png>)

* #### **Paso 43.**
  Se deberá proporcionar una dirección de correo electrónico. La dirección de correo electrónico puede ser utilizada para recibir notificaciones del sistema, como alertas de eventos importantes o actualizaciones de Proxmox. Proporcionar una dirección de correo electrónico válida y accesible es útil para estar informado sobre el estado y el funcionamiento de la instancia de Proxmox VE.

  ![Correo electrónico para administración del sistema.](<src/061. Correo electrónico del administrador del sistema.png>)

* #### **Paso 44.**
  Es importante tener en cuenta que la contraseña de administración y la dirección de correo electrónico asociada con la cuenta de administrador son elementos clave para administrar y mantener la instancia de Proxmox VE 8.1. Es recomendable elegir una contraseña segura y mantener la dirección de correo electrónico actualizada para recibir notificaciones importantes del sistema.

  Si las contraseñas coinciden y el correo electrónico asignado es correcto se deberá seleccionar la opción **next**.

  ![Configuración de la contraseña de administración y el correo electrónico](<src/062. Configuración de la contraseña de administración y el correo electrónico.png>)

* #### **Paso 45.**
   El próximo paso es configurar la interfaz de red de la máquina virtual.
   
   ![Management Network Configuration](<src/063. Management Network Configuration.png>)

   ![Management Network Configuration](<src/064. Management Network Configuration.png>)

* #### **Paso 46.**
 Durante la instalación de Proxmox VE 8.1, se derberá configurar la interfaz de red. Asegurarse de seleccionar la interfaz que se desea utilizar para la gestión de la red. Por lo general, esto será una interfaz Ethernet, como enp0s3 que es seleccionada automáticamente en caso de seguir con la guía.



* #### **Paso 47.**

* #### **Paso 48.**


  








  

  











Recomendaciones:
Se recomienda instalar Proxmox VE 8.1 utlizando hardware físico o en una plataforma de virtualización que admita la virtualización KVM, como VMware ESXi, KVM/QEMU en sistemas Linux o incluso Hyper-V en Windows Server. De esta manera, podrá ser aprovechado al máximo las capacidades de virtualización de Proxmox y ejecutar contenedores, y máquinas virtuales de manera eficiente.













