# [[Unike267](https://github.com/Unike267)] DOCUMENTACIÓN TÉCNICA
---
---

- **Asignatura**: Electrónica de potencia
- **Tema**: Tipos de interruptores. (Anexo)
- **Curso**: 3º 
- **Autor**: Unai S.

---
---

# ANEXO 1: Tipos de interruptores

## Índice:

- Objetivo
- Recordatorio
- En profundidad

---

### Objetivo:

El objetivo principal de los interruptores de potencia es hacer de **intermediario físico** entre el control y la red, materializando las conmutaciones que dan lugar a la modulación de las señales. Simplemente controlando el cuándo de esta sencilla acción, **la conmutación**, conseguimos todos los objetivos de la electrónica de potencia.

---

### Recordatorio (fuente : [index.md](https://github.com/Unike267/UNI/blob/potencia/_index.md "_index.md")):

Recordamos que existen dos tipos de interruptores de potencia:
+ **Guiados por red:** La red eléctrica los sincroniza. Principalmente:
    * Diodo: La red controla tanto su encendido como su apagado.
    * Tiristor: Nosotros controlamos su encendido, pero la red lo apaga.
+ **Autónomos:** NO se sincronizan con la red, es decir, nosotros controlamos su encendido y su apagado. Principalmente:
    * MOSFET: Tipo de FET (Transistores controlados por tensión).
    * IGBT: Híbrido entre un BJT y un FET tipo MOSFET.
    * GTO: Es un tipo de tiristor en el que también se controla su apagado. 

---

### En profundidad:

##### Guiados por red:

- **Diodo:** Es el dispositivo electrónico de potencia más simple. Formado por la unión de dos materiales, tipo P (portadores de huecos/ánodo) y tipo N (portadores de electrones/cátodo), solo permite la circulación de electricidad si se polariza directamente (tensión ánodo > tensión cátodo), es decir, convierte la línea donde esté aplicado en **unidireccional.** 
Al ser guiados íntegramente por la red, por sí solos, tan solo permiten la construcción de convertidores **NO controlados**.
No obstante, asociados con tiristores dan lugar a los convertidores **semicontrolados.**
- **Tiristor:** Es un diodo provisto de un terminal extra, llamado *gate*. Este hecho permite cierto control sobre el dispositivo:
    + Para **iniciar la conducción** se deben cumplir tres condiciones:
        - Dos ajenas a nuestro control:
            - Debe estar polarizado directamente.
            - La corriente principal A-K que lo atraviesa debe tener un valor igual o superior a un  valor característico llamado *Il* (corriente de enganche) **antes de que termine el impulso por la puerta.**
        - Y una controlada por nosotros:
            - Debe estar sometido a un tren de impulso entre los terminales de puerta y cátodo. Los valores de tensión (Vgk) y corriente (Igk) de impulso están comprendidos generalmente entre 5 % 7.5 voltios y 100 % 200 mili amperios. 
    + Nota: Se utiliza un [tren de impulso](https://sites.google.com/site/telecouco/laboritorio-caracteristicas "Info sobre tren de impulso"), en vez de uno solo, para asegurar que el tiristor cumpla la segunda condición. 
    + Para **bloquearlo** se debe cumplir que:
        + La corriente principal A-K que lo atraviesa sea menor que un valor característico llamado *Ih* (corriente de mantenimiento). Este hecho es ajeno a nuestro control, depende exclusivamente de la red. 
    + Concluimos que el terminal gate solo tiene el poder de encender el dispositivo, es decir, una vez iniciada la conducción los impulsos en puerta serán en vano. También hemos de tener en cuenta que **antes** de dar el tren de impulso deben cumplirse las otras dos condiciones, en caso contrario, el interruptor no se inmutará de nuestras acciones. 

##### Autónomos:

- **MOSFET:** Es un transistor controlado por tensiones aplicadas entre sus terminales *gate* y *source*. Nos permite gobernar tanto su encendido como su bloqueo. Sus características más importantes, dentro de la electrónica de potencia, son:
    + Su conmutación es muy rápida, en el orden de los MHz. 
    + No soportan tensiones elevadas entre los terminales conectados a la red. (< 1000 V)
- **IGBT:** Es un transistor híbrido, mezcla de un BJT y un MOSFET. Al igual que el anterior, se controla por tensiones aplicadas entre sus terminales *gate* y *emitter*, de unos 15 V. Sus características más importantes son:
    + Conmutan más lentamente que los MOSFET, con frecuencias máximas de unos 100 kHZ.
    + Soportan más tensión que los anteriores, con valores límite de unos 6000 V.
- **GTO:** Es un tiristor dotado de control sobre su apagado. Las 3 condiciones que deben cumplir, tanto para el encendido como para el apagado, son las mencionadas en el caso del tiristor. El encendido se produce igual que en los tiristores, mientras que el apagado se produce emitiendo un tren de impulso **negativo** entre la puerta y el cátodo. 
