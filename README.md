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

“El Sensor de Flujo de Agua YF-S201 Efecto Hall, ideal para medir el flujo de agua por medio de un rotor interno que se activa por efecto Hall adecuado para tuberías estándar (1/2″), el cual envía pulsos por cada rotación ocasionado por el flujo, siendo que cada pulso es de aproximadamente 2,25 mililitros.” (UNIT ELECTRONICS, 2022)

**Especificación y características:**
- Voltaje de funcionamiento: 5 a 18 V DC
- Consumo de corriente: 15 mA a 5 V
- Tipo de salida: 5V TTL
- Trabajo Caudal: de 1 /30 litros / minuto
- Temperatura de funcionamiento: -25°C a 80 °C
- Pulso de flujo: F (Hz) = 7.5* Q – 3 (+/- 10%) Q = L / min
- Medida de rosca: DN15, G1/2″ (BSP), macho.
- Rango de Humedad: 35% -80% de humedad relativa
- Dimensiones: 2.5 “ x 1.4” x 1.4

![](https://electronicamade.com/wp-content/uploads/2020/04/arduino-caudalimetro-esquema.png)

