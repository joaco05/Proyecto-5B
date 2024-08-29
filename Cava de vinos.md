Diseño para una cava de vinos que utiliza una Raspberry Pi Pico W como microcontrolador, junto con un esquema de conexión a una PC.

### *1. Estructura de la Cava:*
   - *Dimensiones:* ==120 cm de alto, 60 cm de ancho y 60 cm de profundidad.==
   - *Material:* Madera tratada con aislamiento térmico interno (En lo posible).
   - *Puerta:* Vidrio templado con sellado hermético (En lo posible).

### [*2. Sistema de Refrigeración con Celda Peltier:*](Driver)
   - *Celda Peltier:* 12V DC, montada con disipadores de calor y ventiladores para enfriamiento.
   - *Controlador PWM:* Regulador de potencia para la celda Peltier, controlado por la Raspberry Pi Pico W.

### [*3. Sensores:*](Acondicionamiento)
   - *Sensor de Temperatura y humedad (Digital):* DHT11, para lectura precisa de la temperatura y humedad.
   - *Sensor de Luz (Analógico):* LDR, conectado a una entrada analógica para medir la intensidad de la luz.
   - *Sensor de alcohol (Analógico)*: MQ3, para detección de botellas mal cerradas.

### [*4. Microcontrolador: Raspberry Pi Pico W*](<Controlador (Raspberry Pi Pico W)>)
   - *[[Puertos GPIO]]:* Conectados a los sensores, la celda Peltier (a través de un módulo PWM) y los ventiladores.

### [*5. Interfaz de Usuario:*](<interfaz de usuario>)
   - *7 segmentos:* Conectada a la Raspberry Pi Pico W para mostrar temperatura.
   - *Botones de Control:* Para ajustar las configuraciones desde la propia cava.
   - *Alarmas:* Visuales y/o sonoras en caso de que la temperatura o la humedad estén fuera de los límites.

### [*6. Flujo de Aire:*](Acondicionamiento)
   - *Ventiladores:* Para distribución del aire frío dentro de la cava y disipación del calor fuera.

### [*7. Suministro de Energía:*](Driver)
   - *Fuente de 12V DC:* Para la celda Peltier, ventiladores y lampara.
   - *Fuente de 5V:* Para la Raspberry Pi Pico W y los sensores.

### [*8. Conexión a PC:*](<Conexión a PC>)
- *Cable USB:* Desde la Raspberry Pi Pico W a la PC para la alimentación, programación, y comunicación (Utilizando un Bridge UART).

### *9. Adicionales:*
- *Humidificador/deshumidificador:* Para control de humedad dentro del sistema.
- Uso portátil con Wi-Fi o RF.
- Sellado hermético y aislamiento.
### *Esquema de Conexión:*

*Raspberry Pi Pico W:*
   - *DHT11:* Conectado a un pin GPIO digital para leer humedad y temperatura.
   - *MQ3:* Conectado a un ADC (convertidor analógico a digital) para leer los valores de alcohol.
   - *LDR:* Conectado a otro pin ADC para la intensidad de luz.
   - *Celda Peltier y Ventiladores:* Conectados a través de un módulo PWM y transistores para el control de velocidad.
   - *Pantalla 7 segmentos:* Conectada a través de GPIO.
   - *Botones:* Conectados a pines GPIO para la interacción con el usuario.



### [*Código para la Raspberry Pi Pico W:*](Código)
El código incluirá:
- *Lectura de Sensores:* Mediante las entradas GPIO y ADC.
- *Control de la Celda Peltier:* A través de un módulo PWM.
- *Envío de Datos a la PC:* Via USB (Bridge UART), con posibilidad de almacenar los datos localmente o en un servidor.
- *Interfaz de Usuario:* Control y monitoreo en la pantalla LCD/OLED (con botonera) y a través de la PC.


