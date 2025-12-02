---
mindmap-plugin: basic
---

# TEMA 3 - Almacenamiento

## Factores a valorar
- ➥Confidencialidad
	- ➜Políticas de acceso
	- ➜Evitar robo de datos
	- ➜Cifrar datos
- ➥Rendimiento
	- ➜Tipo de medio almacenamiento
	- ➜Cercanía del medio de almacenamiento
	- ➜Redundancia de discos
- ➥Integridad
	- ➜Mantenimiento del hardware
	- ➜Monitorización de discos
	- ➜Redundancia de discos
	- ➜Copias de seguridad
	- ➜Recuperación de datos
- ➥Accesibilidad
	- ➜Arquitecturas de almacenamiento
- ➥Disponibilidad
	- ➜Redundancia de discos

## Políticas de almacenamiento
- ● Indica la estrategia de gestión de la información e incluyen:
	- ○ Un análisis exhaustivo de los datos, cuáles requieren ser preservados, por cuánto tiempo, y cuál es su valor para la organización. Además, debe determinarse su grado de confidencialidad para definir qué empleados tendrán acceso a ellos.
	- ○ La determinación de la estrategia de almacenamiento, en función del análisis anterior. Los requisitos de rendimiento, accesibilidad y disponibilidad que se pretende cumplir, y las tecnologías disponibles de almacenamiento, tanto en lo referente a soportes físicos como a arquitecturas de almacenamiento.
	- ○ La gestión de los dispositivos de almacenamiento, que incluye su mantenimiento, su monitorización y su eliminación segura cuando acaban su vida útil o fallan, así cómo cuál es el uso adecuado de cada tipo de dispositivo por parte de los empleados de la organización, reflejado en las políticas de uso para cada tipo de dispositivo.
	- ○ La definición de la política de copias de respaldo.
	- ○ Un plan de contingencias que establezca qué debe hacerse ante fugas de información, pérdida de datos y otras incidencias relacionadas.

## Confidencialidad
- ● La confidencialidad es importante para guardar el secreto empresarial y la privacidad de los datos personales, por ello es fundamental clasificar la información según su grado de confidencialidad.
- ● Información confidencial: información especialmente sensible para la organización o bien que contiene datos de carácter personal especialmente sensibles:
	- ○ Debe identificarse como tal.
	- ○ Debe definirse estrictos controles de acceso.
	- ○ Si es preciso sacar la información de las instalaciones, debe cifrarse.
	- ○ Debe cumplir las exigencias del RGPD.
- ● Información interna: que es información propia de la organización accesible a todos sus empleados como la política de seguridad o el directorio de personal, para cuyo tratamiento:
	- ○ Debe identificarse como tal.
	- ○ Debe ser accesible a todo el personal.
	- ○ Salvo indicación contraria de la dirección, no debe difundirse fuera de la organización.
- ● Información pública: que es información que general la empresa para su difusión universal, por lo que no está sujeta a restricción alguna. Tal es el caso de la página web o los catálogos de productos. No recibe ningún tratamiento especial.

## Fundamentos teoricos
- ● Cifrar un archivo puntual con openssl/GPG es útil si se quiere portar un archivo pero impracticable si lo que se pretende es almacenar archivos en disco.
- ● Solución: cuatro estrategias:
	- ○ El cifrado por hardware, esto es, implementado en el propio dispositivo, que se llama Self-Encrypting drive.
	- ○ El cifrado de dispositivos de bloques (p.e. una partición)
	- ○ El cifrado usando el propio sistema de archivos, si es que éste lo soporta. ext4 soporta cifrado desde la versión 4.1 del kernel de Linux.
	- ○ El cifrado del contenido de parte de un sistema de archivos, que, junto a FUSE, es la aproximación que usa software como:
		- ■ encfs, que ha sido el software más usado, pero que es actualmente desaconsejable por sus problemas de seguridad.
		- ■ cryfs, que tiene la limitación de no permitir aún el cambio en la contraseña de cifrado.
		- ■ gocryptfs, que será el que utilicemos por no tener la limitación anterior.

## Cifrado de datos
- ● A diferencia del tema de criptografía, aquí se exige que las operaciones de cifrado y descifrado se hagan de manera transparente, esto es, sin que el usuario tenga que utilizar las herramientas criptográficas cada que vez que desee guardar o leer un fichero.

## Eliminación de datos
- ● La eliminación efectiva de los datos es fundamental cuando hemos almacenado datos sensibles en un dispositivo y lo sustituimos por otro. Antes de empezar, sin embargo, tengamos presentes dos cosas: