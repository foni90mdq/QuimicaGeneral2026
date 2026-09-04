# Anexo – Medidas repetidas, desvío estándar e incertidumbre experimental

Cuando se realiza una medición experimental, el resultado obtenido nunca es completamente exacto. Toda medición presenta cierto grado de variabilidad e incertidumbre asociado tanto al procedimiento experimental como a los instrumentos utilizados.

Una forma sencilla de evaluar parte de esta variabilidad consiste en repetir varias veces la determinación y comparar los resultados obtenidos.

## Ejemplo: determinación de una concentración

Se quiere determinar la concentración de una solución expresada en g/L.

Para ello se toman tres muestras independientes de 10,00 mL de la solución. En cada caso se evapora el solvente y se determina la masa de soluto presente.

Los resultados obtenidos son:

| Determinación | Masa de soluto (g) | Volumen de muestra (mL) |
|---|---:|---:|
| 1 | 0,501 | 10,00 |
| 2 | 0,497 | 10,00 |
| 3 | 0,503 | 10,00 |

La concentración se calcula como:

$$
C=\frac{m}{V}
$$

expresando el volumen en litros.

Para la primera determinación:

$$
C_1=\frac{0,501\ \mathrm{g}}{0,01000\ \mathrm{L}}
=50,1\ \mathrm{g/L}
$$

De manera análoga:

$$
C_2=49,7\ \mathrm{g/L}
$$

$$
C_3=50,3\ \mathrm{g/L}
$$

Por lo tanto, las tres determinaciones experimentales de la concentración son:

$$
50,1;\ 49,7;\ 50,3\ \mathrm{g/L}
$$

La concentración promedio es:

$$
\bar C=\frac{50,1+49,7+50,3}{3}
=50,03\ \mathrm{g/L}
$$

y el desvío estándar de las tres determinaciones es aproximadamente:

$$
s=0,31\ \mathrm{g/L}
$$

El resultado podría informarse, de manera simplificada, como:

$$
C=(50,0\pm0,3)\ \mathrm{g/L}
$$

## ¿Qué representa el desvío estándar?

El desvío estándar describe la **dispersión de las determinaciones repetidas alrededor del valor promedio**.

En el ejemplo anterior, las tres concentraciones no son exactamente iguales. Esto puede deberse a pequeñas variaciones que ocurren de manera diferente en cada repetición, por ejemplo:

- pequeñas diferencias en la lectura de la balanza;
- variaciones en el volumen efectivamente tomado;
- pequeñas pérdidas de muestra durante la manipulación;
- diferencias en el procedimiento entre una determinación y otra;
- variaciones propias de la lectura y resolución de los instrumentos.

Este tipo de variaciones hace que algunas determinaciones resulten ligeramente mayores y otras ligeramente menores. Por esta razón, al repetir el experimento aparecen como una **dispersión de los resultados**, que puede ser evaluada mediante el desvío estándar.

Un desvío estándar pequeño indica que las determinaciones son cercanas entre sí y, por lo tanto, que el procedimiento presenta una buena **precisión o repetibilidad**.

Sin embargo, es importante destacar que el desvío estándar de las medidas repetidas **no representa necesariamente toda la incertidumbre del resultado experimental**.

## Incertidumbres que pueden no observarse en las medidas repetidas

Consideremos nuevamente el ejemplo anterior.

Supongamos que la pipeta utilizada está rotulada como de 10,00 mL, pero debido a un problema de calibración entrega en realidad 9,90 mL.

Si se utiliza la misma pipeta para las tres determinaciones, este problema afectará a todas ellas aproximadamente de la misma manera.

Es posible entonces obtener resultados muy próximos entre sí, por ejemplo:

$$
50,5;\ 50,6;\ 50,5\ \mathrm{g/L}
$$

El desvío estándar sería muy pequeño, por lo que las mediciones serían muy **precisas**.

Sin embargo, todas podrían estar desplazadas respecto del valor verdadero debido al error de calibración de la pipeta.

Este tipo de error, que afecta de manera similar a todas las determinaciones, se denomina generalmente **error sistemático**.

Algunos ejemplos son:

- una balanza incorrectamente calibrada;
- una pipeta que entrega sistemáticamente un volumen diferente del indicado;
- un matraz aforado cuyo volumen real difiere del nominal;
- un procedimiento que produce siempre una pequeña pérdida de muestra;
- un método de medición que produce sistemáticamente valores mayores o menores que el valor real.

Como estas fuentes afectan de manera semejante a todas las repeticiones, **repetir la medición no necesariamente permite detectarlas**.

Por este motivo, un conjunto de resultados puede presentar un desvío estándar muy pequeño y, sin embargo, no encontrarse cerca del valor verdadero.

## Precisión y exactitud

Es importante distinguir dos conceptos:

**Precisión:** indica qué tan próximos están entre sí los resultados de medidas repetidas.

**Exactitud:** indica qué tan próximo se encuentra el resultado experimental al valor verdadero o de referencia.

Por ejemplo:

### Caso A

$$
50,0;\ 50,1;\ 49,9\ \mathrm{g/L}
$$

Las mediciones están muy próximas entre sí: presentan buena precisión.

### Caso B

$$
48,0;\ 48,1;\ 47,9\ \mathrm{g/L}
$$

Estas mediciones también presentan muy buena precisión, porque están muy próximas entre sí.

Sin embargo, si el valor verdadero de la concentración fuera 50,0 g/L, los resultados del caso B serían poco exactos.

Por lo tanto:

> **Una alta precisión no garantiza necesariamente una alta exactitud.**

## ¿Qué incertidumbre estamos evaluando entonces?

Cuando calculamos el promedio y el desvío estándar de varias determinaciones, estamos evaluando principalmente la **variabilidad observada al repetir el procedimiento experimental**.

Esta variabilidad incluye muchas fuentes aleatorias que cambian entre una repetición y otra.

Sin embargo, existen otras fuentes de incertidumbre que pueden ser comunes a todas las determinaciones y que, por lo tanto, no aparecen necesariamente reflejadas en el desvío estándar.

De manera simplificada podemos pensar en dos contribuciones:

### Variabilidad observada experimentalmente

Es la que puede detectarse al repetir la medición y observar la dispersión de los resultados.

Se evalúa, por ejemplo, mediante el desvío estándar.

### Incertidumbres asociadas a instrumentos y procedimientos

Provienen de factores como la resolución, tolerancia o calibración de una balanza, pipeta, bureta o matraz aforado.

Algunas de estas incertidumbres pueden contribuir a la dispersión entre medidas, pero otras pueden afectar de manera semejante a todas las determinaciones y no ser evidentes a partir del desvío estándar.

En un tratamiento metrológico más completo, ambas contribuciones pueden considerarse conjuntamente mediante procedimientos de **propagación y combinación de incertidumbres**.

Ese tratamiento excede el objetivo de este curso. Sin embargo, es importante comprender que:

> **El desvío estándar de medidas repetidas describe la precisión del procedimiento, pero no debe interpretarse automáticamente como la incertidumbre total de la medición.**

## Idea principal

Al realizar varias determinaciones experimentales es conveniente:

1. calcular el resultado correspondiente a cada determinación;
2. calcular el valor promedio;
3. calcular el desvío estándar;
4. informar el resultado teniendo en cuenta las cifras significativas y la dispersión observada.

Por ejemplo:

$$
C=(50,0\pm0,3)\ \mathrm{g/L}
$$

Este valor informa tanto el valor central obtenido como la variabilidad observada entre las determinaciones.

Sin embargo, siempre debe recordarse que pueden existir otras fuentes de incertidumbre, especialmente errores sistemáticos o incertidumbres comunes a todas las mediciones, que no necesariamente se manifiestan en el desvío estándar.
