# [[Unike267](https://github.com/Unike267)] DOCUMENTACIÓN TÉCNICA
---
---

- **Asignatura**: Electrónica de potencia
- **Tema**: Protecciones. (Anexo)
- **Curso**: 3º 
- **Autor**: Unai S.

---
---

# ANEXO 2: Protecciones

## Índice:

- Objetivo
- Tipos de protecciones

---

### Objetivo:

El objetivo es claro, proteger a los interruptores electrónicos de potencia. 
Las amenazas ante las que tomamos medidas protectoras provienen de dos índoles:

- *Eléctricas*, principalmente distinguimos cuatro tipos:
    + **Sobretensión** 
    + **Sobrecorriente**
        + Estas dos amenazas provienen de la red. Provocan un **aumento** en la magnitud eléctrica que atraviesa los dispositivos acoplados, la cual **supera** el valor característico máximo admitido. 
        Están relacionadas con el incremento sobre un límite dado.
    + **dv/dt**
    + **di/dt**
        + Son amenazas causadas por variaciones **rápidas** de las magnitudes eléctricas que atraviesan los dispositivos. Están relacionadas con la **velocidad** a la que varían, no tiene porqué superar un límite característico dado.
- *Térmicas*, están relacionadas con la potencia. Toman gran relevancia cuando manejamos tensiones o corrientes altas. A diferencia de las eléctricas, no son de carácter repentino.


### Tipos de protecciones

- Ante amenazas *eléctricas*, el tipo de protección utilizada dependerá de la autonomía de los dispositivos. 
    + **Protecciones estáticas:** Se implementan en interruptores no autónomos, es decir, guiados por red (diodos y tiristores). Este tipo de protecciones están respaldadas por dispositivos electrónicos, tales como:
        + [Varistores](https://es.wikipedia.org/wiki/Varistor "info sobre varistores") para proteger de sobretensiones.
        + [Fusibles](https://es.wikipedia.org/wiki/Fusible "info sobre fusibles") para proteger de sobrecorrientes.
        + [Filtro RC](https://es.wikipedia.org/wiki/Circuito_RC "info sobre circuito RC") para proteger de dv/dt.
        + [Bobinas](https://es.wikipedia.org/wiki/Inductor "info sobre bobinas") para proteger de di/dt.
        + **Nota:** se deben dimensionar correctamente las particularidades de los diferentes dispositivos para asegurar un correcto funcionamiento de la instalación.

    + **Protecciones dinámicas:** Se implementan en interruptores autónomos (MOSFET, IGBT, GTO). 
    Este tipo de protección actúa directamente sobre el dispositivo, es decir, lo apaga cuando surge una amenaza eléctrica que lo pueda averiar. Sin embargo, requiere de sensores que monitoricen el estado de la red en cada momento.

En la siguiente imagen se muestra un tiristor dotado de todas las protecciones estáticas:
![Tiristor protegido](https://raw.githubusercontent.com/Unike267/Photos/master/UNI-Photos/potencia/picture1.png)

- Ante amenazas *térmicas*, el tipo de interruptor es indiferente. Se solventan empleando dispositivos fiscos, tales como: 
    + [Disipadores](https://es.wikipedia.org/wiki/Disipador "info sobre disipadores"), con el fin de radiar la energía calorífica extra, producida por los componentes.
    + Ventiladores, con el fin de refrigerar los componentes.

El diseño de este tipo de protecciones se rige por una máxima: **la potencia generada debe ser igual a la potencia disipada.** 
[Información extra sobre la disipación térmica](http://rabfis15.uco.es/transistoresweb/Tutorial_General/disipacionTermica.html)