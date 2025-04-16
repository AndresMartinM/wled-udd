# Proyecto Iluminación WLED

Instructivo sobre la utilización de WLED

### Materiales necesarios

* Esp32 devkit
* Fuente de poder 5v
* Tira led 5v compatible ([listado de tiras compatibles](https://kno.wled.ge/basics/compatible-led-strips/))
* Dispositivo de control (Celular o Computador)

### Materiales opcionales

* Sensor PIR
* Botón
* Modulo micrófono
* Carcasa
* Cables duPont
* Protoboard


## Proceso de Instalación
Primero se debe conectar la placa Esp32 vía USB al computador. En un navegador compatible se abre la página para instalar el código en la placa ([instalador web](https://install.wled.me/)).

Navegador no compatible:

<img title="instalacionMal" alt="página de instalación en un navegador no compatible" src="/img/instalacionMal.png" style="width : 600px;">

Navegador compatible:

<img title="instalacionBien" alt="página de instalación en un navegador compatible" src="/img/instalacionBien.png" width="600px">


Luego se selecciona la versión a instalar, y se presiona el botón ***Install***, tras ello la página solicitará seleccionar el puerto serial en el cuál realizar la instalación, es decir en qué dispositivo conectado al equipo se subirá el programa, por lo mismo se debe saber cual de los puertos es el ocupado por el Esp32, esto se puede averiguar desconectando y conectando el USB, el que desaparezca y aparezca es el correcto.

Se Presiona el botón conectar, tras esto va a aparecer una ventana de carga que dice *Connecting*, y aparecerá la opción ***Install WLED*** y ***Logs & Console***, la primera es para insalar wled en el Esp32, y el segundo para visualizar la información mandada por el Esp32 a travéz del puerto serial. Si se presiona ***Install WLED*** pedirá confirmar la acción, y si se confirma la página comenzará a preparar la instalación.

<div alt="sección de imágenes" style="display: inline-block; align : center;">
<img title="installLog" alt="opciones install wled, log and console" src="/img/installLog.png" height="200px">
<img title="confirm" alt="confirmar instalación" src="/img/confirmInstall.png" height="200px">
<img title="preparando" alt="preparando instalación" src="/img/preparandoInstall.png" height="200px">
<img title="instalando" alt="instalando el software" src="/img/instalando.png" height="200px">
<img title="completa" alt="instalación completa" src="/img/completa.png" height="200px">
</div>  


Luego mostrará el porcentaje de la instalación, se debe esperar en la página que ocurra este proceso, y al final aparece el mensaje de instalación completa; se presiona ***Next*** y a continuación se debe realizar la configuración de red, se selecciona el nombre de la red o se escribe si no aparece, y se ingresa la contraseña.

<div alt="sección de imágenes" style="display: inline-block;">
<img title="seleccionarRed" alt="pestaña de selección de red" src="/img/seleccionarRed.png" height="200px">
<img title="instalado" alt="pestaña tras la instalación" src="/img/instalado.png" height="200px">
<img title="listoParaUsar" alt="listo para usar" src="/img/listoParaUsar.png" height="200px">
</div>


Por último, teniendo instalado el software y configurada la red se puede acceder a la interfaz de WLED, cuyo uso se explica en el **Proceso de Configuración**.
A continuación se explica el armado del dispositivo.

## Proceso de Construcción
Para armar este dispositivo, lo primero que hay que hacer es identificar los pines del Esp32, el pin de entrada de voltaje (VIN - 5v), el pin de salida de voltaje (3V3 - 3.3v), los pines de tierra (GND), y los pines de señal (D2, D3, D4... en adelante); por otro lado hay que identificar los cables de la tira led, que debe contar con: entrada de voltaje (5v), tierra (GND), y señal digital entrada (Din) en la que se debe ver la dirección en la que apunta la flecha para luego realizar la conexión; y en el caso de ser necesaria más corriente para alimentar las tiras led tambien se deben ver las conexiones de la fuente de poder, salidas de voltaje (v+ - 5v) y la tierra (gnd - ⏚) TODO revisar esto cuando tengamos fuentes de poder

La conexión entre la tira led y el Esp32 es mediante el cable de señal que debe conectar la entrada digital (Din) de la tira led con uno de los pines de señal del Esp32 (D2, D3, D4... en adelante) esto luego se debe configurar en la interfaz de wled, 5v y GND de la tira deben ir conectados o al VIN y GND del Esp32 o a lo correspondiente en la fuente de poder.

Con eso ya se puede realizar el proceso de configuración.

Si se quisieran añadir más elementos, como sensores de presencia, botones, u otros sensores se deben realizar lo siguiente, en lo que se revisará el uso de 3 tipos de sensores, en el caso de que se quiera usar un sensor distinto a los que se muestran aquí se recomienda el video de *ResinChem Tech* [*Level Up Your WLED Projects: A Guide to adding Components (no code)*](https://www.youtube.com/watch?v=1Qj1jJAam-8) (en este también estan los que se ven aquí).

Para esta etapa se recomienda usar **Cables *duPont*** y ***Protoboard***, ya que facilitan las conexiones.

### Botón
Se conecta un lado del botón a un pin de señal del Esp32 y el otro a la tierra.
El resto es configurar el funcionamiento de este sensor, desde la interfaz de wled.

### Sensor PIR
Se conecta el 

### Sensor de ruido
TODO


## Proceso de Configuración
### Pantalla Principal
Al ingresar en la interfaz de wled lo primero que aparece en la parte superior se encuentran los siguientes botones:
* Power (para encender y apagar la luz del dispositivo)
* Timer (para encender y apagar el cambio de estado programado)
* Sync (para sincronizar otros dispositivos con este)
* Peek TODO qué hace peek?
* Info (para ver los datos del dispositivo)
* Config (para configurar luces, sensores, comportamientos, etc)

Bajo esto hay un *slider* para asignar el brillo y la sección para escoger el color (***Colors***) que consta de una rueda de color, 2 *sliders*, 10 muestras, y un botón para escoger un color al azar; además está la opción de escoger paletas de color en forma de gradientes.

También está la sección ***Effects***, con más de 100 distintos efectos de luz que se pueden escoger. Cada uno de los cuáles se puede configurar mediante distintos parámetros controlados por *sliders* ubicados en la parte inferior.

La sección ***Segments*** permite configurar distintos comportamientos a secciones de la tira led.

Finalmente está la sección ***Presets***, en la que se pueden guardar configuraciones que se quieran usar en el futuro, ya sea seleccionandolas manualmente o de manera automatizada, cada preset se guarda con un **Nombre** y un **ID**, este último será de mucha utilidad a la hora de asignar comportamientos automatizados. Cada preset se puede editar luego marcando la casilla ***Overwrite with state*** cambiando los parámetros y luego presionando ***Save*** en la pestaña del preset.

### Menú de Configuración
Eso es lo que hay en la pestaña principal, ahora lo recomendable tras conocer la interfaz de control es ir a las configuraciones en **Config**, al presionar el botón se despliega un menú con diferentes opciones:
* Back (para volver a la pestaña principal)
* WiFi Setup (para las opciones de red)
* LED Preferences (para las opciones de las tiras y sus comportamientos)
* 2D Cofiguration (para configurar los LED como panel bidimensional)
* User Interface (para personalizar la interfaz de la app)
* Time & Macros (para configurar el reloj y comportamientos relacionados al tiempo)
* Usermods (para activar y configurar acciones personalizadas, por ejemplo aquí está AudioReactive)
* Security & Updates (para las opciones de seguridad)
<img title="menuWled" alt="menu de configuración" src="/img/menuWled.png" width="400px">

### Configurar Punto de Acceso
Lo primero a hacer en el menú es ir al ***WiFi Setup*** para habilitar un *Access point* que permitirá prescindir de redes WiFi externas, y se podrá llevar el dispositivo a distintos lugares, sin la necesidad de conectarlo a una red. Por el contrario esto hará que el Esp32 genere una red a la que se puede acceder desde el celular o computador.

<img title="redWled" alt="configuración de la red" src="/img/redWled.png" width="600px">

Entonces se entra al menú *WiFi Setup* se desliza hasta la sección ***Configure Access Point***, se escribe un nuevo nombre para la red (reconocible, distinto al de otras redes y otros dispositivos wled), se escribe un acontraseña o se deja vacía para dejar la red abierta, en el canal se deja el 1, y en ***AP opens*** se selecciona ***Always***. Con eso ya se debería poder acceder a la red, la cuál pedirá ingresar, lo que lleva a la interfaz de WLED.

### Configurar Tira LED
Para configurar la o las tiras led que se van a usar hay que ir a ***LED Preferences***, lo primero que aparece es la información general sobre como están ya configurados los LED.

Después está la configuración de las tiras LED, en la que se puede escoger el modelo de tira LED con la que se está trabajando y según eso se despliegan opciones de configuración, en este caso se muestran las opciones de los modelos WS281X que son las siguientes: el orden de color de la señal digital (***Color Order***), el led desde el que va comenzar (***Start***, es automático), y la longitud de la tira contado en cantidad de LEDs (***Length***); también se debe escoger el pin de señal del Esp32 al que se está conectando (**GPIO**), si se quiere invertir o no el orden de los LEDs (***Reversed (rotated 180°)***), cuántos LEDs ignorar o no encender (***Skip first LEDs***), y el último es la opción de refrescar la tira con un apagado (***Off Refresh***).

Tras estas opciones hay un ícono de cruz que sirve para añadir más tiras LED que se conecten a otros pines GPIO del Esp32, esta es una de las formas para añadir mas LED, puesto que también está la opción de conectar las tiras unas a otras (mientras sean del mismo tipo). Bueno, al presionar el botón para añadir más, surge una sección identica a la que se describió anteriormente.

<div alt="sección de imágenes" style="display: inline-block;">
<img title="ledConfig1" alt="opciones de tiras led" src="/img/ledConfig1.png" width="600px">
<img title="ledConfig2" alt="opciones de tiras led" src="/img/ledConfig2.png" height="400px">
<img title="ledConfig3" alt="opciones de tiras led" src="/img/ledConfig3.png" height="400px">
</div>

