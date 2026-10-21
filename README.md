# alarma-movimiento1
# Proyecto: Sistema de Alarma por Movimiento con Arduino

# Integrantes
* Nieto Milagros
* Prinzi Candelaria
* Osler Gonzalo


# 1. Historia de Usuario
* **Título:** Detección de movimiento y emisión de alerta acústica
* **Como:** Usuario del sistema de seguridad.
* **Quiero:** Que el sistema detecte el movimiento mediante un sensor PIR y active un buzzer de 5V.
* **Para:** Recibir una alerta sonora inmediata ante la presencia no autorizada en un espacio monitoreado.

**Criterios de Aceptación:**
* El sensor PIR debe enviar una señal digital a la placa Arduino al detectar presencia.
* El buzzer de 5V debe sonar inmediatamente tras la lectura del movimiento.
* La alerta sonora debe permanecer encendida mientras se detecte movimiento.
* El sistema debe volver automáticamente al estado de reposo una vez finalizado el movimiento.

---

## 2. Requerimientos Funcionales
1. **Detección de movimiento:** El sistema debe detectar la presencia de movimiento en el área de cobertura utilizando el sensor PIR conectado a la placa Arduino.
2. **Activación de alerta sonora:** El sistema debe emitir una señal acústica a través del buzzer de 5V de forma inmediata al detectarse movimiento.
3. **Temporización de la alarma:** El buzzer debe mantenerse activo con tono intermitente o continuo durante el intervalo de detección.
4. **Procesamiento de señales:** La placa Arduino debe leer y procesar correctamente el estado digital enviado por el pin de datos del sensor PIR.
5. **Reinicio de estado:** El sistema debe volver a su estado de reposo (vigilancia) una vez finalizado el movimiento, quedando listo para detectar nuevas presencias.

---

## 3. Requerimientos No Funcionales
1. **Tiempo de respuesta:** El tiempo transcurrido entre la detección física del movimiento y la activación del buzzer debe ser menor a un segundo.
2. **Estabilidad de conexiones:** Los cables macho-hembra-macho deben asegurar una transmisión eléctrica firme y estable para evitar falsos positivos.
3. **Eficiencia energética:** El circuito completo debe operar con un bajo consumo de energía, apto para alimentación USB o fuente de 5V estándar.
4. **Mantenibilidad del código:** El programa en Arduino debe estar debidamente estructurado para facilitar su lectura y futuras modificaciones.
5. **Confiabilidad:** Los componentes físicos deben operar de manera continua bajo condiciones normales de temperatura ambiente.

---

## 4. Diagrama de Flujo
* **Inicio**
* **Configuración:** Configurar pines del Arduino (Pin 2: Entrada / Pin 8: Salida).
* **Lectura:** Leer estado del Sensor PIR Pin Digital.
* **Evaluación:** ¿Se detectó movimiento? (¿Estado == ALTO?)
  * **Sí:** Activar Buzzer Pin 8 HIGH (usando tono).
  * **No:** Apagar Buzzer Pin 8 LOW.
* **Espera:** Espera corta (100ms).
* **Bucle:** Volver a evaluar estado.

---

## 5. Código Fuente (Arduino / Wokwi)

```cpp
const int sensorPIR = 2;
const int buzzer = 8;

void setup() {
  pinMode(sensorPIR, INPUT);
  pinMode(buzzer, OUTPUT);
}

void loop() {
  int movimiento = digitalRead(sensorPIR);

  if (movimiento == HIGH) {
    tone(buzzer, 1000);
  } else {
    noTone(buzzer);
  }
}
