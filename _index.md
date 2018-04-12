# [[Unike267](https://github.com/Unike267)] DOCUMENTACIÓN TÉCNICA
---
---

- **Asignatura**: Electrónica de potencia
- **Tema**: Introducción
- **Curso**: 3º 
- **Autor**: Unai S.

---
---

# INTRODUCCIÓN a la electrónica de potencia.

## Índice:
- El porqué.
- Objetivo, cómo lo consigue y con qué.
- Etapas
- Disposición de los convertidores y tipos.
- Efectos.

---
### El porqué.
La electrónica de potencia surge por la necesidad imperiosa de controlar la corriente alterna. Tiene multitud de aplicaciones, algunas de ellas son:

- Fuentes de alimentación.
- Calentamiento por inducción
- **Control de motores de corriente alterna**
- **Soporte a energías renovables**

Estas dos última son "la guinda del pastel" de la electrónica de potencia y son las aplicaciones en las que se centrará toda la asignatura.

### Objetivo, cómo lo consigue y con qué.

- **Objetivo:** Control y conversión de la energía en formato eléctrico.
- **Cómo lo consigue:** Modifica el camino que deben seguir los electrones, utilizando la **conmutación**.
- **Con qué:** Con los dispositivos electrónicos de potencia, estos son **los interruptores de potencia.** Existen dos tipos:
    + **Guiados por red:** La red eléctrica los sincroniza. Principalmente:
        * Diodo: La red controla tanto su encendido como su apagado.
        * Tiristor: Nosotros controlamos su encendido, pero la red lo apaga.
    + **Autónomos:** NO se sincronizan con la red, es decir, nosotros controlamos su encendido y su apagado. Principalmente:
        * MOSFET: Tipo de FET (Transistores controlados por tensión).
        * IGBT: Híbrido entre un BJT y un FET tipo MOSFET.
        * GTO: Es un tipo de tiristor en el que también se controla su apagado. 

### Etapas.

La electrónica de potencia consta de dos etapas, etapa de control y etapa de potencia, **aisladas eléctricamente** entre sí.
- **Etapa de control**: Es la etapa encargada del control, definiendo control como **la decisión sobre el CUÁNDO encender o apagar los interruptores de potencia**.
Parece una tontería, pero regulando el cuándo, obtenemos el control sobre las formas de onda que llegan a nuestras cargas. Variando estas formas de onda, con la adecuada modulación, conseguiremos control absoluto sobre nuestros motores electricos, tanto en velocidad como en par.
Las decisiones sobre el cuándo las toma un algoritmo implementado en un microcontrolador.
Trabaja a bajo voltaje entre 3.3 V y 5 V.

- **Etapa de potencia**: Es la etapa que, obedeciendo las decisiones del control, lleva a cabo de manera física las conmutaciones. 
Trabaja al voltaje de la red.

### Disposición de los convertidores y tipos.

**Todos** los convertidores electrónicos de potencia tienen la misma disposición, la cual se puede resumir en cuatro bloques:
- **Bloque de potencia:** es el bloque encargado de gestionar la electricidad que toma de la red, obedeciendo las órdenes del bloque de control. Según la operación de conversión que queramos hacer estará formado por unos convertidores u otros. 
- **Bloque acondicionador (driver):** es el bloque encargado de enlazar la etapa de potencia y la de control. Está formada por circuitos denominados driver´s, los cuales cumplen una doble función: 
    + Aportar la energía necesaria al interruptor para ejecutar correctamente su encendido y bloqueo. 
    + Proporcionar aislamiento galvánico entre el bloque de potencia y el de control.
- **Bloque de instrumentación:** es el bloque encargado de captar, con ayuda de sensores, las variables susceptibles de control o visualización.
- **Bloque de control:** es el bloque encargado de enviar las instrucciones, procedentes del algoritmo de control, al resto de bloques. Está formado por un microcontrolador, el cual suele dotarse de una interface gráfica para facilitar la intervención humana.

Los 4 **tipos** de convertidores son:
- **Rectificadores (AC/DC):** convierten la energía alterna en continua.
- **Inversores (DC/AC):** convierten la energía continua en alterna.
- **Choppers (DC/DC):** convierten la energía continua en otra con diferente tensión.
- **Cicloconversores (AC/AC):** convierten la energía alterna en otra variando tanto la amplitud como la frecuencia del voltaje de salida.

### Efectos.

El principal efecto negativo introducido por la electrónica de potencia es la distorsión armónica a causa del comportamiento conmutado de los interruptores electrónicos que conforman el convertidor. 
Los desarrollos en serie de Fourier nos van a facilitar el estudio energético de los efectos que causen las perturbaciones generadas por nuestro convertidor. 





