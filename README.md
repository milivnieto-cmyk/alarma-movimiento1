# alarma-movimiento1
Sistema de Alarma por Movimiento con Arduino

Repositorio oficial del proyecto de sensor de alarma por movimiento. Desarrollado con Arduino, sensor PIR y buzzer de 5V.

Historia de Usuario

Título: Detección de movimiento y emisión de alerta sonora

Como: Usuario del sistema de seguridad

Quiero: Que el sistema detecte movimientos dentro de su rango usando el sensor PIR y active un buzzer de 5V

Para: Recibir una alerta acústica inmediata cuando se detecte una presencia no autorizada en el área monitoreada

Criterios de Aceptación:

El sensor PIR debe detectar movimiento y enviar la señal a la placa Arduino.

El buzzer de 5V debe emitir un sonido fuerte al detectar presencia.

La alarma sonora debe permanecer encendida mientras se mantenga la detección de movimiento.

El sistema debe regresar automáticamente al estado de reposo para quedar listo ante una nueva detección.

Requerimientos Funcionales

RF1 - Detección de movimiento: El sistema debe capturar la presencia de movimiento en su área de cobertura mediante el sensor PIR.

RF2 - Activación de alarma sonora: El sistema debe activar el buzzer de 5V emitiendo un tono de 1000 Hz en el instante en que el sensor PIR detecte movimiento.

RF3 - Silenciado automático: El sistema debe desactivar el sonido del buzzer inmediatamente cuando el sensor PIR deje de detectar movimiento.

RF4 - Lectura de señales digitales: La placa Arduino debe procesar e interpretar de manera continua el estado lógico (HIGH/LOW) enviado por el pin de salida del sensor PIR.

RF5 - Restablecimiento automático: El sistema debe retornar al estado de vigilancia activa (espera) tras finalizar la alerta, quedando listo para una nueva lectura.

Requerimientos No Funcionales

RNF1 - Tiempo de respuesta (Latencia): El tiempo transcurrido entre la detección física por el sensor PIR y el encendido del buzzer no debe superar 1 segundo.

RNF2 - Estabilidad en las conexiones: El circuito debe usar cables macho-hembra y macho-macho en correcto estado para asegurar la conductividad y evitar falsas alarmas o desconexiones.

RNF3 - Consumo energético: El sistema completo debe funcionar eficientemente alimentado con 5V mediante el puerto USB de la placa Arduino.

RNF4 - Legibilidad del software: El código escrito en C++ para Arduino debe incluir comentarios explicativos y una estructura clara para facilitar futuras modificaciones.

RNF5 - Fiabilidad operativa: Los componentes del sistema deben funcionar de forma continua sin fallas térmicas o eléctricas en condiciones normales de aula.
