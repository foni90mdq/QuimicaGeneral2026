# Tutorial – Tratamiento de datos de una titulación con jamovi

## ¿Qué es jamovi?

[jamovi](https://www.jamovi.org/) es un programa gratuito y de código abierto para análisis estadístico. Está diseñado para ser fácil de usar y presenta una interfaz similar a una hoja de cálculo, por lo que permite realizar análisis estadísticos y gráficos sin necesidad de escribir código.

Internamente, jamovi utiliza el lenguaje estadístico **R**, pero para las actividades de este curso utilizaremos principalmente su interfaz gráfica.

Existen dos formas principales de utilizar jamovi:

### jamovi Desktop

La versión **Desktop** se instala en la computadora y es gratuita. Está disponible para Windows, macOS y Linux.

Puede descargarse desde:

[https://www.jamovi.org/download.html](https://www.jamovi.org/download.html)

Una vez instalado, puede utilizarse sin conexión a Internet para trabajar con los datos y realizar los análisis.

Para realizar las actividades de esta guía, esta es la opción recomendada si dispone de una computadora en la que pueda instalar programas.

### jamovi Cloud

También existe una versión online llamada **jamovi Cloud**, que funciona directamente desde un navegador y no requiere instalar ningún programa.

Puede accederse desde:

[https://cloud.jamovi.org/](https://cloud.jamovi.org/)

La versión Cloud utiliza una interfaz muy similar a la versión Desktop y resulta útil cuando se trabaja desde una computadora en la que no se pueden instalar programas, un Chromebook, una tablet o una computadora compartida.

> **Recomendación:** si es posible, utilice **jamovi Desktop**. Si no desea o no puede instalar programas, puede realizar la actividad utilizando **jamovi Cloud**.

Las instrucciones que se muestran a continuación son prácticamente iguales en ambas versiones.

---

# Objetivo de la actividad

En esta actividad se utilizará jamovi para analizar los resultados de varias determinaciones experimentales de una concentración.

El objetivo es aprender a:

- organizar datos experimentales;
- calcular una magnitud a partir de cada medición;
- calcular el promedio;
- calcular el desvío estándar;
- representar gráficamente los resultados;
- interpretar la variabilidad entre mediciones;
- informar adecuadamente un resultado experimental.

---

# Problema

Se quiere determinar la concentración de una solución de **HCl** mediante titulación con una solución de **NaOH 0,1000 mol/L**.

Para cada determinación se toman **10,00 mL de HCl** y se titulan hasta alcanzar el punto de equivalencia.

Los volúmenes de NaOH utilizados fueron:

| Determinación | Volumen de NaOH (mL) |
|---:|---:|
| 1 | 9,92 |
| 2 | 10,08 |
| 3 | 10,01 |
| 4 | 9,96 |
| 5 | 10,05 |

---

# 1. Planteo químico

Antes de utilizar jamovi:

1. escriba la ecuación química correspondiente a la reacción entre HCl y NaOH;
2. balancee la ecuación;
3. determine la relación estequiométrica entre los moles de HCl y NaOH en el punto de equivalencia.

En este caso, de la ecuación balanceada se obtiene una relación 1:1 entre ambos reactivos.

Por lo tanto, en el punto de equivalencia:

$$
n_{HCl} = n_{NaOH}
$$

Recordando que:

$$
n = C \cdot V
$$

se puede escribir:

$$
C_{HCl} V_{HCl} = C_{NaOH} V_{NaOH}
$$

y despejando la concentración desconocida:

$$
C_{HCl} = \frac{C_{NaOH} V_{NaOH}}{V_{HCl}}
$$

---

# 2. Ingreso de los datos en jamovi

Abra jamovi Desktop o jamovi Cloud.

Al iniciar el programa aparecerá una hoja de cálculo.

En jamovi:

- cada **fila** representa una observación o determinación experimental;
- cada **columna** representa una variable.

Vamos a utilizar inicialmente dos columnas:

| Determinacion | V_NaOH_mL |
|---:|---:|
| 1 | 9,92 |
| 2 | 10,08 |
| 3 | 10,01 |
| 4 | 9,96 |
| 5 | 10,05 |

Puede escribir los datos directamente en la hoja de cálculo o copiarlos y pegarlos desde otra planilla.

## Tipo de variable

Verifique que `V_NaOH_mL` esté definida como una variable numérica continua.

La columna `Determinacion` simplemente identifica cada experimento.

---

# 3. Crear una variable calculada

Queremos calcular una concentración de HCl para **cada titulación realizada**.

Sabemos que la concentración de NaOH es:

$$
C_{NaOH} = 0,1000\ mol/L
$$

y que el volumen de HCl utilizado en cada titulación es:

$$
V_{HCl} = 10,00\ mL
$$

Por lo tanto:

$$
C_{HCl} = \frac{0,1000 \cdot V_{NaOH}}{10,00}
$$

Como ambos volúmenes están expresados en mL, las unidades de volumen se cancelan en el cociente.

En jamovi:

1. agregue una nueva columna;
2. seleccione la opción para crear una **Computed Variable**;
3. nombre la nueva variable `C_HCl`;
4. ingrese la siguiente expresión:

```text
0.1000 * V_NaOH_mL / 10.00
```

jamovi calculará automáticamente la concentración correspondiente a cada fila.

Debería obtener aproximadamente:

| Determinación | V NaOH (mL) | C HCl (mol/L) |
|---:|---:|---:|
| 1 | 9,92 | 0,0992 |
| 2 | 10,08 | 0,1008 |
| 3 | 10,01 | 0,1001 |
| 4 | 9,96 | 0,0996 |
| 5 | 10,05 | 0,1005 |

Observe que **cada titulación genera una determinación independiente de la concentración**.

No calcularemos primero el volumen promedio para realizar una única determinación. Primero obtendremos una concentración para cada experimento y luego analizaremos la variabilidad entre esas concentraciones.

---

# 4. Calcular promedio y desvío estándar

Seleccione:

**Analyses → Exploration → Descriptives**

Agregue la variable `C_HCl` a las variables que se desea analizar.

Dentro de las opciones de estadísticas descriptivas seleccione:

- **Mean** o promedio;
- **Std. deviation** o desvío estándar;
- **Minimum**;
- **Maximum**.

jamovi calculará automáticamente estos valores.

Para los datos del ejemplo se obtiene aproximadamente:

$$
\bar{C} = 0,10004\ mol/L
$$

y:

$$
s = 0,00064\ mol/L
$$

Teniendo en cuenta una cantidad adecuada de cifras significativas, el resultado puede informarse como:

$$
C_{HCl} = (0,1000 \pm 0,0006)\ mol/L
$$

El primer valor representa el **promedio de las determinaciones** y el valor después del símbolo $\pm$ corresponde al **desvío estándar**.

---

# 5. ¿Qué significa el desvío estándar?

Las concentraciones obtenidas en las distintas titulaciones no son exactamente iguales.

Esta variabilidad puede deberse a pequeñas diferencias entre una determinación y otra, por ejemplo:

- pequeñas diferencias en la lectura de la bureta;
- diferencias al identificar el punto final;
- variaciones en el tamaño de la última gota agregada;
- pequeñas diferencias en la manipulación experimental.

El **desvío estándar** permite cuantificar qué tan dispersos están los resultados alrededor del valor promedio.

Un desvío estándar pequeño indica que las determinaciones son próximas entre sí y, por lo tanto, que el procedimiento presenta una buena **precisión o repetibilidad**.

Sin embargo:

> **Un desvío estándar pequeño no garantiza necesariamente que el resultado sea exacto.**

Por ejemplo, suponga que la concentración real de la solución utilizada como titulante no fuera exactamente 0,1000 mol/L.

En ese caso, todas las concentraciones calculadas de HCl podrían resultar desplazadas en la misma dirección.

Como el mismo error afectaría a todas las determinaciones de forma similar, las concentraciones podrían seguir siendo muy próximas entre sí y presentar un desvío estándar pequeño.

Por lo tanto, el desvío estándar describe principalmente la **variabilidad observada entre las determinaciones repetidas**, pero no necesariamente representa toda la incertidumbre del experimento.

Algunas fuentes de incertidumbre instrumental pueden contribuir a la dispersión entre las mediciones. Otras, especialmente aquellas que afectan a todas las determinaciones de manera similar, pueden no ser evidentes a partir del desvío estándar.

---

# 6. Precisión y exactitud

Es importante distinguir entre **precisión** y **exactitud**.

La **precisión** indica qué tan próximos se encuentran entre sí los resultados obtenidos al repetir una medición.

La **exactitud** indica qué tan próximo se encuentra el resultado experimental al valor verdadero o de referencia.

Por ejemplo, considere las siguientes determinaciones:

### Grupo A

$$
0,0999;\ 0,1000;\ 0,1001\ mol/L
$$

### Grupo B

$$
0,0949;\ 0,0950;\ 0,0951\ mol/L
$$

Ambos grupos presentan una dispersión muy pequeña y, por lo tanto, una buena precisión.

Sin embargo, si la concentración verdadera fuera 0,1000 mol/L, el grupo A sería además exacto, mientras que el grupo B sería preciso pero poco exacto.

Por lo tanto:

> **Una alta precisión no garantiza necesariamente una alta exactitud.**

---

# 7. Representación gráfica de los resultados

Dentro del mismo análisis de **Descriptives**, busque la sección correspondiente a gráficos o **Plots**.

Seleccione una representación que permita observar la distribución de los valores de `C_HCl`.

Para conjuntos pequeños de datos resulta especialmente útil una representación en la que puedan observarse las determinaciones individuales.

También pueden explorarse:

- histogramas;
- box plots;
- gráficos de distribución.

Observe:

- qué tan próximos se encuentran los resultados;
- si algún valor parece alejarse del resto;
- dónde se encuentra aproximadamente el valor promedio;
- qué relación existe entre la dispersión observada y el valor del desvío estándar.

---

# 8. Interpretación del resultado

A partir de las cinco titulaciones se obtuvo:

$$
C_{HCl} = (0,1000 \pm 0,0006)\ mol/L
$$

Esto significa que el valor promedio obtenido experimentalmente fue 0,1000 mol/L y que las distintas determinaciones presentaron una dispersión caracterizada por un desvío estándar de aproximadamente 0,0006 mol/L.

Este resultado permite evaluar la **repetibilidad del procedimiento experimental**.

Sin embargo, el valor después del símbolo $\pm$ no debe interpretarse automáticamente como la incertidumbre total de la concentración.

Por ejemplo, pueden existir fuentes de incertidumbre asociadas a:

- la calibración de la bureta;
- la calibración de la pipeta;
- la concentración real de la solución de NaOH;
- el método utilizado para identificar el punto final;
- otros posibles errores sistemáticos.

Si estas fuentes afectan de manera similar a todas las determinaciones, pueden no aumentar significativamente el desvío estándar.

Un tratamiento completo de todas estas contribuciones requiere un análisis más detallado de las incertidumbres experimentales y su propagación, que excede los objetivos de esta actividad.

---

# 9. Preguntas para analizar

1. ¿Por qué se calcula una concentración para cada titulación en lugar de utilizar únicamente el volumen promedio?

2. ¿Qué representa el promedio de las concentraciones obtenidas?

3. ¿Qué información aporta el desvío estándar?

4. Si las cinco concentraciones obtenidas fueran exactamente iguales, ¿qué valor tendría el desvío estándar?

5. ¿Un desvío estándar pequeño garantiza que el resultado experimental sea exacto? Justifique.

6. Suponga que la bureta utilizada presenta un error de calibración que afecta de manera similar a todas las titulaciones. ¿Esperaría necesariamente observar este problema como un aumento del desvío estándar? Explique.

7. ¿Cuál es la diferencia entre **precisión** y **exactitud**?

8. Si se repitiera la titulación un mayor número de veces, ¿qué información adicional podría obtenerse acerca de la variabilidad del procedimiento experimental?

---

# 10. Idea principal

El procedimiento seguido en esta actividad puede resumirse de la siguiente manera:

1. realizar varias determinaciones experimentales;
2. calcular la concentración correspondiente a cada una;
3. calcular el promedio de las concentraciones;
4. calcular el desvío estándar;
5. representar los resultados gráficamente;
6. informar el resultado teniendo en cuenta tanto el valor promedio como la dispersión observada.

En este ejemplo:

$$
V_1 \rightarrow C_1
$$

$$
V_2 \rightarrow C_2
$$

$$
V_3 \rightarrow C_3
$$

$$
V_4 \rightarrow C_4
$$

$$
V_5 \rightarrow C_5
$$

y finalmente:

$$
C_1,\ C_2,\ C_3,\ C_4,\ C_5
\rightarrow
\bar{C}\ \text{y}\ s
$$

De esta manera, las distintas titulaciones son tratadas como **determinaciones experimentales independientes** y la dispersión entre ellas se utiliza para evaluar la precisión del procedimiento.
