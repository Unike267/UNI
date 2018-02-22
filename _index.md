# [[Unike267](https://github.com/Unike267)] DOCUMENTACI�N T�CNICA
---
---

- **Asignatura**: Electr�nica de potencia
- **Tema**: Introducci�n
- **Curso**: 3� 
- **Autor**: Unai S.

---
---

# INTRODUCCI�N a la electr�nica de potencia.

## �ndice:
- El porqu�.
- Objetivo, c�mo lo consigue y con qu�.
- Etapas
- Disposici�n de los convertidores y tipos.
- Efectos.

---
### El porqu�.
La electr�nica de potencia surge por la necesidad imperiosa de controlar la corriente alterna. Tiene tres grandes aplicaciones:
- Fuentes de alimentaci�n.
- Calentamiento por inducci�n
- **Control de motores de corriente alterna**

Esta �ltima es "la guinda del pastel" de la electr�nica de potencia y es la aplicaci�n en la que se centrar� toda la asignatura.

### Objetivo, c�mo lo consigue y con qu�.

- **Objetivo:** Control y conversi�n de la energ�a en formato el�ctrico.
- **C�mo lo consigue:** Modifica el camino que deben seguir los electrones, utilizando la **conmutaci�n**.
- **Con qu�:** Con los dispositivos electr�nicos de potencia, estos son **los interruptores de potencia.** Existen dos tipos:
    + **Guiados por red:** La red el�ctrica los sincroniza. Principalmente:
        * Diodo: La red controla tanto su encendido como su apagado.
        * Tiristor: Nosotros controlamos su encendido, pero la red lo apaga.
    + **Aut�nomos:** NO se sincronizan con la red, es decir, nosotros controlamos su encendido y su apagado. Principalmente:
        * MOSFET: Tipo de FET (Transistores controlados por tensi�n).
        * IGBT: H�brido entre un BJT y un FET tipo MOSFET.
        * GTO: Es un tipo de tiristor en el que tambi�n se controla su apagado. 

### Etapas.

La electr�nica de potencia consta de dos etapas, etapa de control y etapa de potencia, **aisladas el�ctricamente** entre s�.
- **Etapa de control**: Es la etapa encargada del control, definiendo control como **la decisi�n sobre el CU�NDO encender o apagar los interruptores de potencia**.
Parece una tonter�a, pero regulando el cu�ndo, obtenemos el control sobre las formas de onda que llegan a nuestras cargas. Es decir, obtenemos el control sobre **la velocidad que llega a nuestros motores el�ctricos.**
Las decisiones sobre el cu�ndo las toma un algoritmo implementado en un microcontrolador.
Trabaja a bajo voltaje entre 3.3 V y 5 V.

- **Etapa de potencia**: Es la etapa en la que, obedeciendo las decisiones del control, lleva a cabo de manera f�sica las conmutaciones. 
Trabaja al voltaje de la red.

### Disposici�n de los convertidores y tipos.

**Todos** los convertidores electr�nicos de potencia tienen la misma disposici�n, la cual se puede resumir en cuatro bloques:
- **Bloque de potencia:** es el bloque encargado de gestionar la electricidad que toma de la red, obedeciendo las �rdenes del bloque de control. Seg�n la operaci�n de conversi�n que queramos hacer estar� formado por unos convertidores u otros. 
- **Bloque acondicionador (driver):** es el bloque encargado de enlazar la etapa de potencia y la de control. Est� formada por circuitos denominados driver�s, los cuales cumplen una doble funci�n: 
    + Aportar la energ�a necesaria al interruptor para ejecutar correctamente su encendido y bloqueo. 
    + Proporcionar aislamiento galv�nico entre el bloque de potencia y el de control.
- **Bloque de instrumentaci�n:** es el bloque encargado de captar, con ayuda de sensores, las variables susceptibles de control o visualizaci�n.
- **Bloque de control:** es el bloque encargado de enviar las instrucciones, procedentes del algoritmo de control, al resto de bloques. Est� formado por un microcontrolador, el cual suele dotarse de una interface gr�fica para facilitar la intervenci�n humana.

Los 4 **tipos** de convertidores son:
- **Rectificadores (AC/DC):** convierten la energ�a alterna en continua.
- **Inversores (DC/AC):** convierten la energ�a continua en alterna.
- **Choppers (DC/DC):** convierten la energ�a continua en otra con diferente tensi�n.
- **Cicloconversores (AC/AC):** convierten la energ�a alterna en otra variando tanto la amplitud como la frecuencia del voltaje de salida.

### Efectos.

El principal efecto negativo introducido por la electr�nica de potencia es la distorsi�n arm�nica a causa del comportamiento conmutado de los interruptores electr�nicos que conforman el convertidor. 
Los desarrollos en serie de Fourier nos van a facilitar el estudio energ�tico de los efectos que causen las perturbaciones generadas por nuestro convertidor. 





