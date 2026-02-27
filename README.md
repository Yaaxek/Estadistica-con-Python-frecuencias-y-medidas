# Análisis Estadístico del Dataset de Domicilios en Colombia - 2018

## 1. Introducción de Datos

El dataset `datos` contiene una muestra de domicilios de Colombia del año 2018, utilizado para investigar características generales de la población, educación, trabajo, entre otros aspectos socioeconómicos.

### Variables Clave:

*   **Ingreso**: Ingresos mensuales (en miles de pesos) del trabajo principal para personas de 10 años o más. (Cuantitativa Continua)
*   **Edad**: Edad del entrevistado en la fecha de referencia en años. (Cuantitativa Discreta - puede considerarse ordinal o continua según el contexto)
*   **Altura**: Altura del entrevistado en metros. (Cuantitativa Continua)
*   **Ciudad**: Código de referencia a 27 ciudades analizadas. (Cualitativa Nominal)
*   **Sexo**: Sexo del entrevistado. (Cualitativa Nominal)
    *   0: Masculino
    *   1: Femenino
*   **Años de Estudio**: Años de estudio del entrevistado. (Cualitativa Ordinal)
    *   1: Sin estudios y menos de 1 año
    *   ... (hasta 16: 15 años o más, 17: No se sabe)
*   **Color**: Color de piel del entrevistado. (Cualitativa Nominal)
    *   0: Indio
    *   2: Blanco
    *   4: Negro
    *   6: Amarillo
    *   8: Moreno
    *   9: Sin declarar

## 2. Distribución de Frecuencias

### Variables Cualitativas:

*   **Sexo**: La distribución de género muestra que hay una mayor proporción de individuos masculinos (69.3%) en comparación con los femeninos (30.7%) en el dataset.
    *   Masculino: 53,250 individuos (69.3%)
    *   Femenino: 23,590 individuos (30.7%)

*   **Color (Cruzado por Sexo)**: Se analizó la frecuencia y proporción de color de piel segmentado por sexo. Por ejemplo, en general, el grupo 'Pardo' es el más frecuente, seguido por 'Blanco'. El análisis detallado por sexo muestra cómo se distribuyen estas categorías en cada grupo.

### Variables Cuantitativas:

*   **Ingreso (Clases Personalizadas)**: Los ingresos se clasificaron en clases basadas en el salario mínimo. La mayor concentración de ingresos se encuentra en la clase 'E' (Hasta 1,576 mil pesos), que representa el 64.75% de la población, seguida por la clase 'D' (De 1,576 a 3,152 mil pesos) con el 21.73%.
    *   E (Hasta 1,576): 49,755 individuos (64.75%)
    *   D (De 1,576 a 3,152): 16,700 individuos (21.73%)
    *   C (De 3,152 a 7,880): 7,599 individuos (9.89%)
    *   B (De 7,880 a 15,760): 2,178 individuos (2.83%)
    *   A (Más de 15,760): 608 individuos (0.79%)

*   **Ingreso (Clases de Amplitud Fija - Regla de Sturges)**: Utilizando la regla de Sturges, se definieron 17 clases para los ingresos. Se observa una alta concentración de individuos en el rango de ingresos más bajo (98.38% en la primera clase), lo que indica una distribución de ingresos fuertemente sesgada hacia los valores más bajos.

## 3. Medidas de Tendencia Central

### Ingreso:
*   **Media**: 2000.38 (aproximadamente 2000 mil pesos)
*   **Mediana**: 1200 mil pesos
*   **Moda**: 788 mil pesos
La relación **Moda (788) < Mediana (1200) < Media (2000)** indica una distribución asimétrica positiva (sesgada a la derecha), con la mayoría de los ingresos concentrados en los valores más bajos.

### Altura:
*   **Media**: 1.70 metros
*   **Mediana**: 1.70 metros
*   **Moda**: Múltiples modas, con valores cercanos a la media y mediana, por ejemplo, 1.57m, 1.67m, 1.68m, 1.69m, 1.71m, 1.75m, 1.78m, 1.80m.
La media, mediana y las modas están muy próximas, lo que sugiere una distribución de altura aproximadamente simétrica, cercana a una distribución normal.

### Años de Estudio:
*   **Media**: 9.47 años
*   **Mediana**: 11 años
*   **Moda**: 12 años
La relación **Moda (12) > Mediana (11) > Media (9)** sugiere una distribución asimétrica negativa (sesgada a la izquierda), indicando que un mayor número de individuos tienen más años de estudio, pero hay una cola de valores más bajos.

## 4. Medidas de Localización

### Cuartiles (Ingreso):
*   **Primer Cuartil (Q1)**: 788 mil pesos (25% de los individuos ganan hasta esta cantidad).
*   **Mediana (Q2)**: 1200 mil pesos (50% de los individuos ganan hasta esta cantidad).
*   **Tercer Cuartil (Q3)**: 2000 mil pesos (75% de los individuos ganan hasta esta cantidad).
El Rango Intercuartílico (IQR) es de 1212 mil pesos, indicando la dispersión del 50% central de los ingresos.

### Box-plot:
*   **Altura**: La distribución de la altura es aproximadamente simétrica, con la mediana cerca del centro de la caja. Se observan algunos valores atípicos tanto en el extremo inferior como superior, lo que indica individuos excepcionalmente bajos o altos. Al segmentar por sexo, se nota una diferencia clara en la mediana y la distribución entre hombres y mujeres, con los hombres presentando generalmente una altura media mayor.

*   **Ingreso**: Para ingresos menores a 10,000 mil pesos, el box-plot revela una fuerte asimetría positiva, con la mayoría de los datos concentrados en el rango inferior. La mediana está significativamente más cerca del primer cuartil, y hay una gran cantidad de valores atípicos en el extremo superior, confirmando el sesgo a la derecha y la presencia de ingresos muy elevados en comparación con la mayoría. Al segmentar por sexo, se pueden observar diferencias en la mediana y dispersión de ingresos, sugiriendo disparidades salariales.

*   **Años de Estudio**: La distribución de años de estudio muestra una concentración significativa alrededor de los 11-12 años, con una asimetría negativa o sesgada a la izquierda. Hay una cola de valores más bajos, y la mediana es alta, lo que indica que una gran parte de la población tiene un nivel de educación decente. Se observan pocos valores atípicos en los extremos. Al segmentar por sexo, se pueden identificar patrones en el nivel educativo alcanzado por hombres y mujeres.

## 5. Medidas de Dispersión

### Notas de María (DataFrame de ejemplo):
*   **Varianza**: 4.57
*   **Desviación Estándar**: 2.14

Estas medidas indican la variabilidad de las notas de María. La varianza, al estar en unidades cuadradas, es menos intuitiva de interpretar que la desviación estándar. La desviación estándar de 2.14 significa que, en promedio, las notas de María se desvían 2.14 unidades de su media (que es de 7.71). Un valor más bajo de desviación estándar indicaría que las notas de María son más consistentes y se agrupan más cerca de la media.
