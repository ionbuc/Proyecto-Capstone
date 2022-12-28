# Proyecto IoT

Sistema de video vigilancia y monitoreo de servicios básicos.

## Introducción.
Este proyecto es la entrega final en el *"Diplomado Curso de IoT de Samsung Innovation Campus"* de la plataforma [Código IoT](https://edu.codigoiot.com/ "Código IoT"). Se desarrolló un sistema enfocado al hogar que contendrá un monitoreo de video vigilancia mediante la ESP32CAM, además contará con un registro de consumo de agua para avisar al usuario si está realizando un consumo excesivo y por último esta aplicación nos emitirá una alerta auditiva y un mensaje en WhatsApp en caso de que se detecte una fuga de gas dentro de la vivienda.

## Desarrollo.

**En el proyecto se utilizó el siguiente hardware:**
- Módulo ESP32CAM
- Módulo ESP3 WROOM 32
- Sensor de caudal YF-S201
- Sensor de calidad de aire MQ135

**Y el siguiente Software:**
- IDE de Arduino
- Node red
- Grafana
- Mysql
- Broker Mosquitto

#### **ESP32CAM:**
*"ESP32-CAM es una tarjeta de desarrollo que está basada en el microcontrolador ESP32-S, además de incorporar interfaz de programación MicroUSB con el Driver CH340. Esta tarjeta incorpora una cámara OV2640 que permite hacer streaming de video, tomar fotos y realizar pequeñas aplicaciones de reconocimiento facial y como todo ESP32 cuenta con Bluetooth y WiFi. La ESP32-CAM CH340 es ideal para proyectos de videovigilancia, transmitir imágenes ya sea de tu robot móvil o como sensor para un sistema de visión por computadora básico."(UNIT ELECTRONICS, 2022)*

![](https://scontent.fmex27-1.fna.fbcdn.net/v/t39.30808-6/322620556_845670449848200_1766737508608148737_n.jpg?_nc_cat=111&ccb=1-7&_nc_sid=730e14&_nc_ohc=M1g3VuAwAhQAX8OrRks&_nc_ht=scontent.fmex27-1.fna&oh=00_AfDohcq0TIc2zHVhcT-rxCqwergy7-cHihGJraS3XfN6hA&oe=63AFF664)

#### **Sensor de caudal YF-S201.**

*“El Sensor de Flujo de Agua YF-S201 Efecto Hall, ideal para medir el flujo de agua por medio de un rotor interno que se activa por efecto Hall adecuado para tuberías estándar (1/2″), el cual envía pulsos por cada rotación ocasionado por el flujo, siendo que cada pulso es de aproximadamente 2,25 mililitros.” (UNIT ELECTRONICS, 2022)*

**Especificación y características:** 

- Voltaje de funcionamiento: 5 a 18 V DC
- Consumo de corriente: 15 mA a 5 V
- Tipo de salida: 5V TTL
- Trabajo Caudal: de 1 /30 litros / minuto
- Temperatura de funcionamiento: -25°C a 80 °C
- Pulso de flujo: F (Hz) = 7.5* Q – 3 (+/- 10%) Q = L / min*
- Medida de rosca: DN15, G1/2″ (BSP), macho.
- Rango de Humedad: 35% -80% de humedad relativa
- Dimensiones: 2.5 “ x 1.4” x 1.4

![](https://electronicamade.com/wp-content/uploads/2020/04/arduino-caudalimetro-esquema.png)

[Explicación del funcionamiento (video)](https://youtu.be/8Os665VJvwY "Explicación del funcionamiento (video)")

#### **Sensor detector de calidad de aire MQ 135.**
“El MQ-135 Detector de Calidad de Aire es un sensor electroquímico que varía su resistencia al estar contacto con gases como Amoniaco, Alcohol, Benceno, Humo y Dióxido de carbono en el aire, el módulo contiene un circuito electrónico que funciona como interfaz permitiendo realizar la conexión con alguna tarjeta de desarrollo y cuenta con una salida analógica y otra digital.
El Módulo MQ-135 es es ideal para detectar la calidad de aire pues permite la detección de gases nocivos en un rango máximo de 10-1000 ppm (partes por millón). Se utiliza en equipos de control de calidad de aire en casas, edificios, oficinas y en las industrias que manejan este tipo de gases.” (UNIT ELECTRONICS, 2022)

![](https://www.waveshare.com/w/fkbk/swtumb.php?f=MQ-135-Gas-Sensor_l.jpg&width=300)

[Explicación del funcionamiento MQ135 (video)](https://youtu.be/uMnx8sM3n98 "Explicación del funcionamiento MQ135 (video)")

**Diagrama de conexiones.**

En el siguiente diagrama se muestra las conexiones necesarias para obtener las lecturas de los dos sensores y enviarlas por medio del protocolo MQTT al servidor Node red y procesar los datos, almacenándolos en una base de datos y mostrándolos en un Flow.

![](https://scontent.fmex27-1.fna.fbcdn.net/v/t39.30808-6/322468120_700141891459810_4420626460333194085_n.jpg?stp=dst-jpg_s600x600&_nc_cat=104&ccb=1-7&_nc_sid=730e14&_nc_ohc=VdFl9iIrLjoAX_YFeQ6&_nc_oc=AQndvn0yV1NMe--Lg_c7dO7Ya-nYUZziJHVOejYv5Cp1G_5KchHju8a3OQPCb2sTYlcuFdIfGkQgY-pav6szVrN9&_nc_ht=scontent.fmex27-1.fna&oh=00_AfCe1yFKSr9S58GNEt5IFEPEcA3diJwCZitPsgklPndg2A&oe=63B17E66)

**Resultados en Node red.**

![](https://scontent.fmex27-1.fna.fbcdn.net/v/t39.30808-6/322113998_1339695213534422_4898545840929984890_n.jpg?_nc_cat=108&ccb=1-7&_nc_sid=730e14&_nc_ohc=9VghdV-tDf4AX_RC9ii&_nc_ht=scontent.fmex27-1.fna&oh=00_AfDkXqBakVfvIiT80Dbxjeu1Qd1NAr3DDb43LMUoDrop9g&oe=63AFD165)