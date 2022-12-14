# ESP32CAM-MQTT-Basic-Rams-s
Comunicación del ESP32CAM con MQTT broker local

## Configurar el MQTT

![](https://github.com/RamsesOrtiz36/ESP32CAM-MQTT-Basic-Rams-s/blob/main/Configuraci%C3%B3n%20MQTT/Configuraci%C3%B3n%20mqtt%20original%20a%20modificar%20con%20sudo%20gedit.png)

Para configurar el servicio de broker MQTT (Mosquitto) ocupabos el archivo de configuración:
+ Ir a la ubicado en **/usr/share/doc/mosquitto/examples/mosquitto.conf.exampl**.
+ Abrimos la carpeta en una terminal nueva. 
+ Abrir el documento con permiso de administrador o root.

      sudo gedit mosquitto.conf
      
+ Descomentar la linea: **allow_anonymous = true** (quitando el simbolo # al inicio de la linea).
+ Modificar la linea: **listener 1883 0.0.0.0** de la sección extra listener, descomentadola y agregando el puerto 0.0.0.0
+ Usar el **Guardar como** para guardarlo en **/etc/mosquitto/conf.d/**.

![](https://github.com/RamsesOrtiz36/ESP32CAM-MQTT-Basic-Rams-s/blob/main/Configuraci%C3%B3n%20MQTT/Guardar%20archivo%20mqtt%20reconfigurado.png)

## Comprobar el funcionmiento del servicio MQTT

Comprobamos el estado del servicio desde terminal con el comando:

      systemctl status mosquitto
      
Detenemos el servicio con el comando:

      systemctl stop mosquitto

Reiniciamo es servicio con el comando:

      systemctl start mosquitto
      
![](https://github.com/RamsesOrtiz36/ESP32CAM-MQTT-Basic-Rams-s/blob/main/Configuraci%C3%B3n%20MQTT/reconfigurar%20mosquitto.png)

## Uso de MQTT esn ESP32CAM
Este servicio se emplea para enviar y ver mensajes por el protocolo de MQTT por internet.

La ESP32CAM ocupa una biblioteca para facilitar la subscripción y publicación de mensajes por internet empleando el puerto 1883.
Usando la biblioteca **PubSubClient**.

En el IDE de Arduino vamos a Herramientas- Administrador de bibliotecas (o mal traducido librerias)- **buscar PubSubClient de Nick O'Leary**

![](https://github.com/RamsesOrtiz36/ESP32CAM-MQTT-Basic-Rams-s/blob/main/Configuraci%C3%B3n%20MQTT/ESP32CAM%20MQTT%20Biblioteca.png)

