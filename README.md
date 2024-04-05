El siguiente trabajo tiene como objetivo aplicar los conceptos y técnicas análisis exploratorio y descriptivo de un conjunto de datos reales de un Call center, con la finalidad de poder
proponer mejoras en:
* Eficiencia operativa, proponiendo mejoras operativas.
* Mejorar la satisfacción del cliente, cumpliendo los SLA comprometidos.
* Brindar una herramienta para la gestión y la toma de decisiones a los managers del Call Center.




Respuesta de voz generada por computadora con información sobre las cuentas de los clientes (a través del dispositivo VRU = Voice Response Unit (unidad de respuesta de voz). Una unidad de respuesta de voz (VRU) es un sistema de contestador telefónico automático que posee un hardware y software que permite a la persona que llama navegar a través de una serie de mensajes pregrabados y utilizar un menú de opciones mediante los botones de un teléfono o el reconocimiento de voz.)

1) linea_vru - 6 dígitos
Cada llamada telefónica entrante es ruteada a través del VRU. Hay 6 VRUs etiquetados desde  AA01 a AA06. Cada VRU tiene varias líneas etiquetadas de 1 a 16. Hay un total de 65 líneas. Cada llamada es asignada a un número de VRU y a un número de línea.

2) IdLLamada - 5 dígitos
A cada llamada telefónica entrante se le asigna un “call id”. Aunque son diferentes, los identificadores no son necesariamente consecutivos por estar asignado a diferentes VRUs.

3) IDCliente - 0 a 12 dígitos
Es la identificación del cliente. Es única por cliente; si el ID es cero, es porque el sistema no pudo identificar a la persona que realiza la llamada (por ejemplo para el caso de los prospectos no se identifican).

4) Prioridad - 1 digito
Hay dos tipos de prioridades: (Alta-)prioridad y Regular:
• 0 y 1 indican clientes no identificados o clientes regulares (los detallaremos más adelante)
• 2 indica clientes de Alta Prioridad.
• Los clientes son servidos en orden según el “Tiempo en Cola” ("Time in Queue").
• A los clientes de Alta Prioridad se les asigna un tiempo de espera de 1.5 minutos al comienzo de su llamada (esto les permite avanzar en la posición de la cola de llamadas). También están exentos de pagar un fee mensual, que los clientes regulares deben pagar.
• No se ha informado a los clientes sobre la existencia de prioridades.
• Hasta Agosto de 1996, todos los clientes tenían la misma prioridad: 0. Las prioridades 1 y 2 fueron incorporadas el 1° de Agosto de 1996. Todavía hay clientes con prioridad 0, pero son tratados como si fueran de prioridad 1. (se definió que los clientes con prioridad 0 corresponden a clientes de prioridad 1 que no realizaron Upgrade a Alta Prioridad (prioridad 2).

• Debido a un error en el sistema, el cliente I.D. no fue registrado para aquellos que no esperaron en la cola, Por lo tanto, su prioridad es 0.

5) Tipo_de_Servicio - 2 digits
Hay 6 tipos diferentes de servicio:
• PS - Actividad Regular
• PE - Actividad Regular en inglés
• IN - Actividad / Consulta por internet
• NE - Actividad por Acciones (stock exchange)
• NW - Cliente potencial (prospecto) solicitando información
• TT – clientes que dejan un mensaje pidiendo al banco que le devuelvan su llamado pero que cuando el sistema automático devuelve el llamado, el agente pasó a estado “ocupado”, dejando al cliente en espera en la cola.

6) Fecha - 6 dígitos
año-mes-día

7) Entrada_vru - 6 dígitos
Hora en que la llamada telefónica ingresa al call center. Más específicamente, cada cliente que llama debe identificarse primero lo que se realiza proporcionando a la VRU la ID del cliente. Por lo tanto, esta es la hora en que la llamada ingresa a la VRU.

8) Salida_vru - 6 dígitos
Hora de salida de la VRU: 
    1. A la cola
    2. O directamente para recibir el servicio.
    3. O para dejar el Sistema (abandono).

9) Espera_en_vru - 1 a 3 dígitos
Tiempo (en segundos) de espera en la VRU (calculada como vru_time= exit_time – entry_time) .
10) q_start - 6 dígitos
Hora en la que se une a la cola. (la llamada queda “en espera”). Este valor es 00:00:00, para clientes que llegan a ponerse en la cola (abandonan cuando están en la VRU).

10) Entrada_cola - 6 dígitos
Hora en la que se une a la cola. (la llamada queda “en espera”). Este valor es 00:00:00, para clientes que llegan a ponerse en la cola (abandonan cuando están en la VRU).

11) Salida_cola - 6 digits
Tiempo (en segundos) en salir de la cola: ya sea porque recibe el servicio o por qué abandona el llamado.

12) Espera_en_cola - 1 to 3 digits
Tiempo de espera en la cola (calculado por q_time = q_exit – q_start)


13) Resultado - 4,5 o 7 digitos
Hay tres posibles salidas por cada llamada:
1. AGENT: se dio servicio
2. HANG: se cortó la llamada y no se dió servicio
3. PHANTOM: una llamada en la que virtualmente se ignora lo que sucedió(afortu- nadamente son pocas llamadas en esta situación).

14) Inicio_servicio - 6 digitos
Hora de comienzo del servicio por un agente.

15) Salida_servicio - 6 digitos
Hora del servicio del servicio por un agente.

16) Duracion_servicio - 1 to 3 digitos
Duración del servicio en segundos (calculada como ser_time = ser_exit – ser_start)

17) Server - text
Nombre del cliente que atendió la llamada. Este campo es NO_SERVER, si el servicio no fue provisto.
