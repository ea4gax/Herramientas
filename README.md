Herramientas Orange pi Zero:

Como Actualizar Firmware del walkie.txt:
1 - Primero tenemos que actualizar la carpeta md380tools. Abrimos la ventana de carpetas (pulsado icono que tenemos a la derecha del icono del terminar), escribimos en la parte de arriba /home/pi.
2 - Nos fijamos en la carpeta md380tools, damos un click sobre él, con el botón derecho desplegamos un submenú, pulsamos  sobre la opción open in terminal, se nos abrirá una consola con la ruta que nos interesa.
3 - Escribimos el comando git pull, (Si nos diera fallos al después de escribir git pull, le metemos el comando make clean, nos hará una limpieza, luego seguimos con git pull), dejamos que acabe, escribimos el comando make, dejamos que finalice.
Ya tenemos actualizada la carpeta md380tools, esto se hace para que nos baje la última versión de firmware.
4 - El siguiente paso es pasar ese firmware al walkie. Conectaremos el cable, seguidamente hay que ponerlo en modo programaciÃ³n de la siguiente manera, con el wakie apagado pulsamos a la vez las teclas ptt y botÃ³n de arriba y encendemos el wakie, veremos que el led de arriba parpadeará de rojo a verde.
5 - Ahora vamos de nuevo a la consola que hemos dejado abierta (recordemos que tenemos que esta en la ruta /home/pi/md380tools, escribiremos los siguientes comando según sea nuestra walkie CON o SIN gps.
    make flash // Walkie SIN gps
    make flash_S13 //Walkie CON gps 
Tardará unos minutos, si todo ha ido bien el mismo walkie se reiniciará solo.
El sigue paso sería actualizar la base de datos con el cable conectado y el walkie encendido normal, abriremos el icono "Actualizar base de datos", se abrirá una consola y se empezará actualizar, cuando termine se cerrará la ventada sola.
Ahora tenemos que coger el walkie nos iremos a la carpeta md380tools que la tendremos en el menú Utilities y nos vamos al menú 4 "Show Calls" y marcamos la opción TA & UserDB.
Actualizar carpeta MMDVMHost.txt:
1 - En primer lugar abrimos una consola (icono primero de la izquierda de abajo del escritorio, el que tiene forma de monitor).
2-  Entramos a la carpeta MMDVMHost, con el siguiente comando cd /home/pi/MMDVMHost.
3 - Escribimos los siguientes comandos con este orden, primero make clean, pulsamos enter, dejamos que acabe, escribimos git pull, pulsamos enter, dejamos que termine y por Ãºltimo escribimos make, este último nos compilará la nueva versión, dejamos que termine, (tardará unos minutos).
4 - Cerramos la ventana y ya podemos abrir nuestro MMDVMHost desde el icono del escritorio.
Programar STM:
- Añadida Herramienta para programar el STM, situada en la carpeta MMDVM_HS, ruta: /home/pi/MMDVM_HS_ACMO/AMA0.
Seguir el manual mmdvm_pizero.pdf, páginas  9  y 10. Sólo será necesario conectar el conversor USB to TTL a los pines de la placa "SERIAL AUR" de la siguiente manera:
  TXD --- RXD
  RXD --- TXD
  GND --- GND
  +5  --- VCC (Hay opciÃ³n a 3v3)
FORMA AUTOMATICA:
Lo primero hay que cambiar el jumper pegado al botón RESET  de posición, por defecto está en posición 0, lo cambiaremos a posición 1, seguidamente pulsaremos el botón RESET.
A continuación ejecutaremos el icono según vayamos a utilizar nuestro hotspot, AMA0 si vamos a utilizar los gpio y el ACMO si lo vamos a utilizar conectado a un USB. Podremos editar el fichero config.h si fuera necesario.
FORMA MANUAL:
Abrimos una consola, (en remoto o el local) escribiremos cd /home/pi/ MMDVM_HS_AMAO/,  o cd /home/pi/ MMDVM_HS_ACM0, según lo deseemos programar, pulsamos el botón RESET y escribimos el comando sudo make serial devser=/dev/ttyS1, ttyS1 es el puerto que se usa si tenemos el STM soldado en la placa, si no nos funcionara, (sin tener ningún dispositivo conectado al puerto usb), probaremos con el puerto ttyUSB0, si lo tenemos ocupado usaremos el ttyUSB1, si nos queremos asegurar que puertos tenemos activos, podemos usar el comando ls /dev.
Programar Nextion:
Podemos programar la nextion por dos puertos diferentes, recordemos que los cables tx rx irán cruzados.
Si tenemos conectada la nextion por el puerto S2, directamente pulsaremos el icono que pone por "S2", se abrirá un terminal y empezará a meter el fichero correspondiente tft, esperamos que termine, la ventana se cerrará sola.
Si queremos programar la nextion por el puerto USB necesitaremos un conversor usb-ttl, lo conectaremos y pulsaremos el icono que hace referencia "por USB0".
Como actualizar bluedv.txt:Nos bajamos la nueva versión de la siguiente página: http://software.pa7lim.nl/BlueDV/BETA/Linux/.
subimos el fichero zip mediante nuestro ftp server a /home/pi.
Abrimos una consola en remoto y nos conectamos mediante ssh y entraremos al directorio /home/pi (comando: cd /home/pi)
Ponemos el siguiente comando en consola: sudo unzip BlueDV-Linux-09349-BETA.zip -d /usr/local/bluedv, (el nombre del zip puede variar según la versión).
Nos preguntará si queremos sustituir todo el contenido de la carpeta, escribimos la palabra A (all). Y ya tenemos actualizado nuestro Bluedv.
Herramientas de sistema:
- Actualizar linux: Ejecutamos el icono haciendo doble click sobre el, se nos abrirá una consola y se bajará los últimos paquetes, cuando termine se cerrará la ventana automáticamente.
Podemos actualizar nuestro sistema haciendo doble click en el icono Software Updater.
- Como actualizar BlueDV for linux: Hay que seguir los pasos que nos muestra el manual. Actualmente está puesta la versión 1.0.0.9388, soporta AMBE3000.
- Configurar wifi: Haciendo doble click sobre el icono, se nos abrirá la ventana de configuración.
- Centro de software de Lubuntu: Nos podremos bajar multitud de aplicaciones fácilmente.
- Vaciar papelera: Vaciado de papelera automáticamente, (se cerrará la ventana sola).
- Cambiar contraseña root, pi y vnc server: Podemos cambiar la contraseña de pi, root y vnc server, abriendo el icono correspondiente.
- Posibilidad de conectarse un sistema bluetooch.
- Añadido icono para instalar paquetes llamado Synactic
