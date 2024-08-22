**Objetivo:** Creación de una imagen de Raspbian para la tarjeta de pruebas Raspberry Pi, así como la verificación de comandos e instalación de software necesario para el manejo remoto de la tarjeta.

### **Introducción:** 
Esta práctica se centra en la configuración de una Raspberry Pi como un sistema embebido básico. La Raspberry Pi es una pequeña computadora de placa única (*single-board computer,* SBC) que ha revolucionado el campo de la electrónica y la computación. Al instalar el sistema operativo Raspbian, una distribución de Linux optimizada para la Raspberry Pi, se habilita un entorno de desarrollo versátil.

Un sistema embebido es un sistema informático diseñado para una función específica, a menudo con recursos limitados. La Raspberry Pi se montará con un servidor VNC para permitir el control remoto de un ordenador a través de una interfaz gráfica. Esto significa que podemos acceder y controlar la Raspberry Pi desde otro dispositivo, como un ordenador personal o una tableta, como si estuviéramos sentados frente a ella.

A través de esta práctica, se adquirirán conocimientos básicos en el campo de los sistemas embebidos, lo que sienta las bases para explorar aplicaciones más complejas en el futuro.

El modelo de Raspberry que se utilizará en esta práctica es la Raspberry 5 de 8 GB RAM. El sistema operativo Raspbian se montará en una tarjeta de memoria micro SD XC-I Clase Ultra 3 de 64 GB. Para la montura de la imagen de Raspbian se utilizará el software Raspberry Pi Imager. La imagen instalada será Raspberry Pi OS con escritorio.

### **Desarrollo**
1. Ingresar a [raspberry.com](https://www.raspberrypi.org/)
![[Pasted image 20240821202504.png|Figura 1: Sitio oficial de Raspberry]]
2. Descargar Raspberry Pi Imager para Windows
![[Pasted image 20240821202556.png|Figura 2: Descarga para Windows]]

3. Elegir la versión de Raspberry Pi OS y descargarla
![[Pasted image 20240821203236.png]]
4. Mediante Raspberry Pi Imager generar imagen en tarjeta SD
   ![[Pasted image 20240821203415.png]]
   
5. Una vez creada la imagen, insertar en su Raspberry y encenderla
![[Pasted image 20240821204433.png]]

6. Verificar el correcto funcionamiento
![[Imagen de WhatsApp 2024-08-15 a las 19.51.43_691273a9.jpg]]

7. Ingresar a símbolo de sistema, verificar el funcionamiento de algunos comandos básicos e indicar lo observado:

| Comandos                    | Observaciones                                                          |
| --------------------------- | ---------------------------------------------------------------------- |
| `pinout`                    | ![[Imagen de WhatsApp 2024-08-15 a las 19.52.54_cdf6e8bb.jpg]]         |
| `sudo pwd`                  | ![[Imagen de WhatsApp 2024-08-15 a las 19.53.37_877517c7.jpg]]         |
| `sudo mdkir`                | ![[Imagen de WhatsApp 2024-08-15 a las 19.54.19_cdcc747d.jpg]]         |
| `sudo cat /proc/meminfo`    | ![[Imagen de WhatsApp 2024-08-15 a las 22.08.06_71b0278f.jpg]]<br><br> |
| `sudo cat /proc/partitions` | ![[Imagen de WhatsApp 2024-08-15 a las 22.08.06_0ff1a95a.jpg]]         |
| `sudo cat /proc/cpuinfo`    | ![[Imagen de WhatsApp 2024-08-15 a las 22.08.06_c1d7dadc.jpg]]         |
| `sudo cat /proc/version`    | ![[Imagen de WhatsApp 2024-08-15 a las 22.08.06_c72681d4.jpg]]         |
| `sudo shutdown -r now`      | ![[Imagen de WhatsApp 2024-08-15 a las 22.09.32_f761e75c.jpg]]         |
| `sudo apt-get update`       | ![[Imagen de WhatsApp 2024-08-15 a las 21.43.41_34aa4611.jpg]]         |
| `sudo apt-get upgrade`      | ![[Imagen de WhatsApp 2024-08-15 a las 21.43.41_5d7f3f22.jpg]]         |


8. Ingresar a símbolo de sistema y teclear sudo raspi-config e indicar lo observado
   ![[Imagen de WhatsApp 2024-08-15 a las 21.53.51_63dc6421.jpg]]
   
9. Activar en la configuración de la Raspberry, el servicio de VNC y SSH para continuar con la siguiente parte de la práctica.
   ![[Imagen de WhatsApp 2024-08-15 a las 21.54.47_231203e4.jpg]]
   ![[Imagen de WhatsApp 2024-08-15 a las 21.55.33_ef36193d.jpg]]
   
   
10. Instalar en mi equipo PuTTy y Nmap para determinar la IP de la Raspberry Pi si lo requiere y utilizar nmap -sn 192.168.1.1/24 para escanear la red.
	![[Pasted image 20240821210020.png]]
1. Ingresar a Raspberry Pi mediante PuTTy
![[Pasted image 20240821210106.png]]
![[Pasted image 20240821210119.png]]


11. Instalar VNC Viewer y acceder a la Raspberry Pi mediante el mismo
	a. Instalar o actualizar VNC
		i. sudo apt-get update
		ii. sudo apt-get install realvnc-vnc-server
		![[Imagen de WhatsApp 2024-08-15 a las 21.46.34_d12a4a40.jpg]]
		iii. sudp apt-get install realvnc-vnc-viewer
		![[Imagen de WhatsApp 2024-08-15 a las 21.48.46_d552eef4.jpg]]
	b. Activar el servidor VNC
		i. sudo raspi-config
	c. Instalar VNC en dispositivos externos
		i. https://www.realvnc.com/es/connect/download/viewer/
		![[Imagen de WhatsApp 2024-08-15 a las 22.00.48_73ee7919.jpg]]
![[Pasted image 20240821210213.png]]

12. Anotar observaciones, si es posible conectarse a la Raspberry a través de computadora, celular, Tablet e identificar las diferencias.

**Responda brevemente las siguientes preguntas**
1. ¿Qué aprendí de esta práctica?
2. ¿Para qué me servirá lo aprendido en esta práctica?
3. ¿Qué beneficios tiene el manejo remoto de mi Raspberry Pi?

### Conclusiones

### Fuentes de Consulta