# 2° Parcial Sistema de Procesamiento de datos

## Alumno:
- Tobías Fabricio Escobar

### División:
1-D

## Proyecto: Sistema de incendio con Arduino 
![2°Parcial - SPD - Escobar Tobías Fabricio](https://github.com/TobiasEscobar/2-Parcial-SPD/assets/98720272/63c48d0c-43a0-45fa-9ba1-4346f9ea79f0)

## :robot: Link al proyecto 
[Proyecto-Parcial](https://www.tinkercad.com/things/b8WFet90oc3-segundo-parcial-spd-1-d-escobar-tobias-fabricio/editel)

# Documentación del Código

## Bibliotecas utilizadas
- Servo.h
- IRremote.h
- LiquidCrystal.h

## Variables y constantes
- `SENSOR_IR`: Pin utilizado para el sensor de infrarrojos.
- `BOTON_APAGADO_ENCENDIDO`: Valor hexadecimal del botón de apagado/encendido del control remoto.
- `VERANO`, `OTONIO`, `INVIERNO`, `PRIMAVERA`: Valores hexadecimales para diferentes botones del control remoto.
- `botonPrendido`: Variable booleana que indica si el botón de apagado/encendido está presionado.
- `SENSOR_TEMPERATURA`: Pin utilizado para el sensor de temperatura.
- `lecturaDelSensor`: Variable para almacenar la lectura del sensor de temperatura.
- `temperatura`: Variable para almacenar la temperatura.
- `lcd`: Objeto para controlar el display LCD.
- `texto`: Arreglo de caracteres para almacenar el texto a mostrar en el LCD.
- `myServo`: Objeto para controlar el servo motor.
- `LED_VERDE`, `LED_ROJO`: Pines utilizados para los LEDs.

## Funciones

### `setup()`
- Configura el pin del sensor de infrarrojos como entrada.
- Inicializa el display LCD con 16 columnas y 2 filas.
- Inicializa el servo motor.
- Configura los pines de los LEDs como salidas.

### `loop()`
- Verifica si se ha recibido una señal del control remoto.
- Actualiza el estado del botón de apagado/encendido.
- Si el botón está activado, se muestra la temperatura y la información del clima en el display LCD.
- Si el botón está desactivado, se apaga el display y los LEDs.

### `obtenerTemperatura()`
- Realiza la lectura del sensor de temperatura.
- Mapea el valor leído a un rango de -40 a 125 grados Celsius.
- Devuelve la temperatura obtenida.

### `detectarBotonApagadoEncendido(float botonPresionado)`
- Verifica si se ha presionado el botón de apagado/encendido.
- Actualiza el estado del botón prendido/apagado.
- Borra el contenido del display LCD.
- Reanuda la recepción de señales del control remoto.

### `informarClima(float botonPresionado)`
- Verifica qué botón de clima ha sido presionado.
- Asigna el texto correspondiente a la estación seleccionada.
- Llama a la función `detectarIncendio()` con la temperatura máxima correspondiente a la estación.

### `prender_servo()`
- Mueve el servo motor a la posición 0 grados.
- Espera 1 segundo.
- Mueve el servo motor a la posición 180 grados.
- Espera 1 segundo.

### `detectarIncendio(int maximaTemperatura)`
- Verifica si la temperatura actual es mayor a la máxima temperatura permitida.
- Si se detecta un incendio, muestra un mensaje de advertencia en el display LCD, mueve el servo motor y enciende el LED rojo.
- Si no se detecta un incendio, muestra el texto correspondiente a la estación y la temperatura actual en el display LCD, y enciende el LED verde.

### `prenderDisplay()`
- Enciende la visualización del display LCD.

### `apagarDisplay()`
- Apaga la visualización del display LCD.

## Diagrama esquemático: 
![diagrama-esquematico](https://github.com/TobiasEscobar/2-Parcial-SPD/assets/98720272/d3edba7a-87f4-4c04-a674-bf063d00ed77)
