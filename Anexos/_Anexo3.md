# [[Unike267](https://github.com/Unike267)] DOCUMENTACIÓN TÉCNICA
---
---

- **Asignatura**: Electrónica de potencia
- **Tema**: Series de Fourier. (Anexo)
- **Curso**: 3º 
- **Autor**: Unai S.

---
---

# ANEXO 3: Series de Fourier

## Índice:

- Contexto
- Series de Fourier, la solución.
- Explicación

---

### Contexto:

Ante la condición abstracta propia de la corriente eléctrica conviene poseer **herramientas** que nos faciliten su estudio, comprensión y control.
Durante años la corriente alterna ha sido generada de forma continua y lineal. Este hecho ha permitido modelizarla mediante ondas sinusoidales.
- Este enfoque relaciona el aumento de caudal de un flujo de **electrones** en una dirección con el aumento positivo de una onda senoidal en unos ejes cartesianos, así como su disminución y posterior cambio de dirección. 
Proyectando dicha onda conseguimos un radio vector para cada instante de tiempo, el cual dota de modulo, dirección y sentido a las magnitudes eléctricas asociadas, es decir, esta mudanza de la realidad al ámbito matemático permite predecir el valor de la tensión y de la corriente que tomará la señal eléctrica alterna en cada unidad de tiempo, además, de ciertos valores característicos de interés.

Implementar la modulación de señales alternas mediante el uso de la conmutación provoca una no linealidad en las señales generadas. Es decir, el modelo sinusoidal tan fácil de tratar **deja de ser válido**. 
Sumado a este hecho, la conmutación provoca efectos indeseados que afectan a la potencia del conjunto, llamados armónicos, los cuales carecen de utilidad práctica pero absorben potencia. 

### Series de Fourier, la solución:

El análisis matemático mediante series de Fourier es una potente herramienta, que permite transformar cualquier topología de señal **periódica** en una componente continua y una serie infinita de ondas sinusoidales. Este hecho mata dos pájaros de un tiro:
+ Por un lado nos permite regresar al marco de las ondas sinusoidales, tomando el primer armónico de la señal generada como nuestra única señal eficaz. 
    + Nota: La frecuencia de la señal generada coincide con la del 1º armónico.
+ Por otro lado nos permite contabilizar los armónicos provocados, pudiendo así hacer un cálculo real de la potencia consumida.
    + Nota: El triángulo de potencias tan común en teoría de circuitos, se transforma en un cuadrángulo de potencias, como el que muestra la siguiente imagen:
    
![Cuadrángulo](https://raw.githubusercontent.com/Unike267/Photos/master/UNI-Photos/potencia/Cuadrangulo.png)

Donde las magnitudes con subíndice 1 se refieren a las del primer armónico, la nueva potencia que añade el resto de armónicos es la de distorsión (D) y el consumo que nos cobrará la compañía eléctrica será el debido a la potencia aparente total consumida (S).

### Explicación:
Antes de empezar debemos saber que:
+ Para que resulte más cómodo la formulación posterior, llamamos 2p al periodo (T) de la señal periódica que vallamos a tratar, es decir, T=2p. De tal manera que si T es 2π, 2p será igualmente 2π y p será π.
+ Debemos tener presentes los conceptos de [paridad de una función](https://es.wikipedia.org/wiki/Paridad_de_una_funci%C3%B3n "IMPORTANTE DIFERENCIAR ENTRE PAR E IMPAR"), ya que si la función es par o impar, se simplifica el cálculo y **nos ahorramos utilizar la forma general.**
+ Las serie está formada por 3 valores que hemos de calcular. Uno correspondiente a la componente continua a0 y otros dos ak y bk correspondientes a la serie infinita de senos y cosenos.
+ Primero calculamos los valores nombrados y seguidamente construimos la serie con ellos.

A la hora de realizar este último punto, diferenciamos dos casos:

+ *Funciones periódicas de periodo 2p=2π.*
    + **General:** La forma general de la serie será del tipo:
![General_2p=2pi](https://raw.githubusercontent.com/Unike267/Photos/master/UNI-Photos/potencia/General_2pi%3D2pi.PNG)
Cuyos valores a0, ak y bk se calculan aplicando:
![General_2p=2pi_Valores](https://raw.githubusercontent.com/Unike267/Photos/master/UNI-Photos/potencia/General_2pi%3D2pi_Valores.PNG)
    + **Función par:** Si la función es par se simplifica a:
![Par_2p=2pi](https://raw.githubusercontent.com/Unike267/Photos/master/UNI-Photos/potencia/Par_2pi%3D2pi.PNG)
    + **Función impar:** Si la función es impar se simplifica a:
![Par_2p=2pi_Valores](https://raw.githubusercontent.com/Unike267/Photos/master/UNI-Photos/potencia/Impar_2pi%3D2pi_Valores.PNG)
![Par_2pi=2pi](https://raw.githubusercontent.com/Unike267/Photos/master/UNI-Photos/potencia/Impar_2pi%3D2pi.PNG)
+ *Funciones periódicas de periodo 2p≠2π.*
    + **General:** La forma general de la serie será del tipo:
![General_2pNO=2pi](https://raw.githubusercontent.com/Unike267/Photos/master/UNI-Photos/potencia/General_2piNO%3D2pi.PNG)
Cuyos valores a0, ak y bk se calculan aplicando:
![General_2pNO=2pi_Valores](https://raw.githubusercontent.com/Unike267/Photos/master/UNI-Photos/potencia/General_2piNO%3D2pi_Valores.PNG)
    + **Función par:** Si la función es par se simplifica a:
![Par_2pNO=2pi_Valores](https://raw.githubusercontent.com/Unike267/Photos/master/UNI-Photos/potencia/Par_2piNO%3D2pi.PNG)
    + **Función impar:** Si la función es impar se simplifica a:
![Impar_2pNO=2pi](https://raw.githubusercontent.com/Unike267/Photos/master/UNI-Photos/potencia/Impar_2piNO%3D2pi.PNG)

Nota: Los resultados de ak y bk quedarán en función del parámetro k, el cual se sustituirá en la serie por un número natural, comenzando con el uno (k=1, 1º armónico) y avanzando sucesivamente en orden, alargamos la serie tantas veces como nos interese. 