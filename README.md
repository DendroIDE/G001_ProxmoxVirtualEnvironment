# Proxmox Virtual Environment

------------

> Proxmox VE es una plataforma de virtualización de código abierto que permite gestionar máquinas virtuales y contenedores de forma centralizada. Ofrece características avanzadas para la creación, gestión y monitorización de entornos de virtualización, incluyendo clusters de servidores y almacenamiento compartido.

La **Guía de Virtual Machines 001 DendroIDE Code** se dedica a la explicación de la instalación y configuración de la plataforma: **Proxmox Virtual Environment 8.1**, utilizando una máquina virtualizada con **Oracle VM VirtualBox** el cual es un software de virtualización para arquitecturas x86/amd64.

## Requisitos mínimos del sistema recomendado por DendroIDE Code.

### Requisitos de Hardware
- **Procesador:**
	* Procesador de novena generación o superior Intel o AMD con 64 bits en la unidad central de proceso.
	* Procesador compatible con la virtualización por hardware (Intel VT-x/AMD-V) para usar KVM.

- **Memoria (RAM):**
	* 8 GB de memoria RAM o superior.

- **Almacenamiento:**
	* Disco duro mecánico o SSD con al menos 128 GB de espacio libre para la instalación del sistema operativo y almacenamiento de datos.
	* Se recomienda un almacenamiento adicional con almenos 256 GB de espacio libre para almacenar imágenes isos, máquinas virtuales, respaldos, templates y datos de contenedores.

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

#### **Paso 1.** Navegar al sitio web oficial de [Proxmox Virtual Environment](https://www.proxmox.com/en/) para proceder a la descarga del software.

![Sitio Oficial de Proxmox Virtual Environment](<src/001. Sitio de descarga oficial Proxmox VE.png>)

#### **Paso 2.** Descargar la imagen ISO que contiene el instalador con la versión de [Proxmox VE 8.1](https://enterprise.proxmox.com/iso/proxmox-ve_8.1-2.iso).

![Descarga de Proxmox VE 8.1 ISO Installer](<src/002. Descarga de la imagen ISO de Proxmox VE 8.1.png>)