# Tutorial – Tratamiento de datos de una titulación con jamovi

## ¿Qué es jamovi?

[jamovi](https://www.jamovi.org/) es un programa gratuito y de código abierto para análisis estadístico. Está diseñado para ser fácil de usar y presenta una interfaz similar a una hoja de cálculo, por lo que permite realizar análisis estadísticos y gráficos sin necesidad de escribir código.

Internamente, jamovi utiliza el lenguaje estadístico **R**, pero para las actividades de este curso utilizaremos principalmente su interfaz gráfica.

Existen dos formas principales de utilizar jamovi:

### jamovi Desktop

La versión **Desktop** se instala en la computadora y es completamente gratuita. Está disponible para Windows, macOS y Linux.

Puede descargarse desde:

**[https://www.jamovi.org/download.html](https://www.jamovi.org/download.html)**

Una vez instalado, puede utilizarse sin conexión a Internet para trabajar con los datos y realizar los análisis. Los archivos, datos y resultados permanecen en la computadora del usuario.

Para realizar las actividades de esta guía, esta es la opción recomendada si dispone de una computadora en la que pueda instalar programas.

### jamovi Cloud

También existe una versión online llamada **jamovi Cloud**, que funciona directamente desde un navegador y no requiere instalar ningún programa.

Puede accederse desde:

**[https://cloud.jamovi.org/](https://cloud.jamovi.org/)**

La versión Cloud ofrece un acceso gratuito para realizar análisis básicos y utiliza esencialmente la misma interfaz que la versión Desktop. Puede resultar especialmente útil si se trabaja desde una computadora en la que no se pueden instalar programas, un Chromebook, una tablet o una computadora compartida.

La versión gratuita de jamovi Cloud puede presentar algunas limitaciones relacionadas con la duración de las sesiones o los recursos disponibles. Para los análisis sencillos que realizaremos en este curso estas limitaciones no deberían ser importantes.

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

Por lo tanto:

$$
n_{\mathrm{HCl}}=n_{\mathrm{NaOH}}
$$

Recordando que:

$$
n=C\,V
$$

se puede escribir:

$$C_{\mathrm{HCl}}V_{\mathrm{HCl}}=C_{\mathrm{NaOH}}V_{\mathrm{NaOH}}$$

y despejando la concentración desconocida:

$$C_{\mathrm{HCl}}=\frac{C_{\mathrm{NaOH}}V_{\mathrm{NaOH}}}{V_{\mathrm{HCl}}}$$

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

Para ello puede seleccionar el encabezado de la columna y comprobar el tipo de variable.

La columna `Determinacion` simplemente identifica cada experimento.

---

# 3. Crear una variable calculada

Queremos calcular una concentración de HCl para **cada titulación realizada**.

Sabemos que:

$$C_{\mathrm{NaOH}}=0,1000\ \mathrm{mol/L}$$

y:

$$V_{\mathrm{HCl}}=10,00\ \mathrm{mL}$$

Por lo tanto:

$$C_{\mathrm{HCl}}=\frac{0,1000\times V_{\mathrm{NaOH}}}{10,00}$$

Como ambos volúmenes están expresados en mL, las unidades de volumen se cancelan.

En jamovi, agregue una nueva columna y seleccione la opción para crear una **Computed Variable** o variable calculada.

Nombre la nueva variable:

```text
C_HCl
