# Proxmox Virtual Environment

------------

> Proxmox VE es una plataforma de virtualización de código abierto que permite gestionar máquinas virtuales y contenedores de forma centralizada. Ofrece características avanzadas para la creación, gestión y monitorización de entornos de virtualización, incluyendo clusters de servidores y almacenamiento compartido.

La **Guía de Virtual Machines 001 DendroIDE Code** se dedica a la explicación de la instalación y configuración de la plataforma: **Proxmox Virtual Environment 8.1**, utilizando una máquina virtualizada con **Oracle VM VirtualBox** el cual es un software de virtualización para arquitecturas x86/amd64.

## Requisitos mínimos del sistema recomendado por DendroIDE Code.

### Requisitos de Hardware
- **Procesador:**
	* Procesador de novena generación o superior Intel o AMD con 64 bits en la unidad central de proceso.
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
  Al finalizar la descarga del instalador de Proxmox VE 8.1 contenido en la imagen ISO, procederemos a la creación de la máquina virtual que ejecutará el entorno  de virtualización de servidores de código abierto. Para ello, es necesario abrir el software de Oracle VirtualBox 7.0.

  ![Oracle VirtualBox 7.0](<src/003. Software Oracle VirtualBox 7.0.png>)

* #### **Paso 04.**
  En el menú principal del software Oracle VirtualBox 7.0, seleccionar el submenú **Máquina**, y luego la opción **Nueva**. También funcionaría con el comando **Ctrl + N** en Windows OS, o utilizando la opción secundaria presentada en la pantalla principal definida como **Nueva**.
  
  ![Selección opción - Nueva](<src/004. Creacion de una nueva máquina virtual.png>)

* #### **Paso 05.**
  Asignar el nombre a la máquina virtual, para caso de la guía el nombre será: Proxmox VE 8.1.
  
  ![Nombre de la máquina virtual](<src/005. Asignación del nombre de la máquina virtual.png>)

* #### **Paso 06.**
  Se debe establecer la ubicación de la máquina virtual, ésta puede estar alojada en la ruta predeterminada por el software de Oracle VirtualBox 7.0 o puede ser almacenada en una ubicación predefinida por el usuario, las únicas recomendaciomnes son que primero el almacenamiento sea fijo y que dicho almacenamiento tenga espacio suficiente parael correcto funcionamiento del sistema.

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
  Definido como requisito mínimo de hardware, se establece un valor inicial con al menos 128 GB de espacio libre en un disco duro mecánico o SSD para la instalación del sistema operativo y almacenamiento de datos. Pero, al ser un sistema virtualizado las circunstancias **cambian**. Utilizando Oracle VirtualBox 7.0, se establecerá como parte de estudio un disco duro virtual dinámico con 128.00 GB de almacenamiento.

    > En Oracle VirtualBox 7.0, un disco virtual es un archivo que representa el disco duro de una máquina virtual. Funciona de manera similar a un disco físico en una computadora real, pero está encapsulado dentro de un archivo en el sistema de archivos del host. Este archivo contiene toda la información y datos almacenados dentro de la máquina virtual, incluidos el sistema operativo, las aplicaciones y los archivos del usuario.
    
    > Los discos virtuales en VirtualBox también pueden ser dinámicos o fijos. Los discos dinámicos crecen según sea necesario para almacenar datos, mientras que los discos fijos reservan todo el espacio definido desde el principio, lo que puede ocupar más espacio en el disco físico pero puede ofrecer un mejor rendimiento.

    > *En **resumen**, un disco virtual en Oracle VirtualBox 7.0 es un archivo que simula un disco duro físico y contiene todos los datos de una máquina virtual, permitiendo que la máquina virtual funcione como si estuviera utilizando un hardware físico real.*

  ![Asiganción del tipo y tamaño del disco duro de la máquina virtual](<src/016. Asignación del disco duro.png>)

* #### **Paso 14.**
  Una vez se encuentre asignada la configuración del disco duro virtual de la máquina virtual a utilizar, seleccionar la opción **siguiente**.
  
  ![Confiuración del disco duro virtual](<src/017. Configuración del disco duro virtual.png>)

* #### **Paso 15.**
  Se visualiza un resumen de la máquina virtual en creación. En caso de estar conforme con la configuración realizada y presentada, deberá ser seleccionada la opción **terminar**. Caso contrario, la opción **anterior** permitirá gestionar el cambio de cualquier configuración previa. La opción **cancelar** permite cerrar la pantalla de creación de máquina virtuales y no proceder a realizar cualquier creación o modificación en el sistema.

  ![alt text](<src/018. Resumen de la creación de la máquina virtual.png>)










