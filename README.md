# Proyecto Iluminación WLED

Instructivo sobre la utilización de WLED

### Materiales necesarios

* Esp32 devkit
* Fuente de poder 5v
* Tira led 5v compatible https://kno.wled.ge/basics/compatible-led-strips/
* Dispositivo de control (Celular o Computador)

### Materiales opcionales

* Sensor PIR
* Botón
* Carcasa
* Cables duPont
* Protoboard


## Proceso de Instalación
Primero se debe conectar la placa Esp32 vía USB al computador. En un navegador compatible se abre la página para instalar el código en la placa (https://install.wled.me/).

Navegador no compatible:

<img title="instalacionMal" alt="página de instalación en un navegador no compatible" src="/img/instalacionMal.png" width="600px">

Navegador compatible:

<img title="instalacionBien" alt="página de instalación en un navegador compatible" src="/img/instalacionBien.png" width="600px">

Luego se selecciona la versión a instalar, y se presiona el botón ***Install***, tras ello la página solicitará seleccionar el puerto serial en el cuál realizar la instalación, es decir en qué dispositivo conectado al equipo se subirá el programa, por lo mismo se debe saber cual de los puertos es el ocupado por el Esp32, esto se puede averiguar desconectando y conectando el USB, el que desaparezca y aparezca es el correcto.

Se Presiona el botón conectar, tras esto va a aparecer una ventana de carga que dice *Connecting*, y aparecerá la opción ***Install WLED*** y ***Logs & Console***, la primera es para insalar wled en el Esp32, y el segundo para visualizar la información mandada por el Esp32 a travéz del puerto serial. Si se presiona ***Install WLED*** pedirá confirmar la acción, y si se confirma la página comenzará a preparar la instalación.

<div style="display: inline-block;">
<img title="installLog" alt="opciones install wled, log and console" src="/img/installLog.png" height="200px">
<img title="confirm" alt="confirmar instalación" src="/img/confirmInstall.png" height="200px">
<img title="preparando" alt="preparando instalación" src="/img/preparandoInstall.png" height="200px">
<img title="instalando" alt="instalando el software" src="/img/instalando.png" height="200px">
<img title="completa" alt="instalación completa" src="/img/completa.png" height="200px">
</div>  

Luego mostrará el porcentaje de la instalación, se debe esperar en la página que ocurra este proceso, y al final aparece el mensaje de instalación completa; se presiona ***Next*** y a continuación se debe realizar la configuración de red, se selecciona el nombre de la red o se escribe si no aparece, y se ingresa la contraseña.

<div style="display: inline-block;">
<img title="seleccionarRed" alt="pestaña de selección de red" src="/img/seleccionarRed.png" height="200px">
<img title="instalado" alt="pestaña tras la instalación" src="/img/instalado.png" height="200px">
</div>

Por último, teniendo instalado el software y configurada la red se puede acceder a la interfaz de WLED, cuyo uso se explica en el **Proceso de Configuración**.
A continuación se explica el armado del dispositivo.

## Proceso de Construcción
acá explicar las conexiones del dispositivo

## Proceso de Configuración
acá explicar la configuración de la app
