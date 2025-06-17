# Spanish Paragraph Simplification Benchmark – 5K (SPSB-5K)

Este documento describe la estructura, estadísticas y uso del corpus **SPSB-5K**, un banco de 5 000 pares de párrafos en español diseñado para entrenar y evaluar modelos de simplificación y complicación de texto.

---

## 1. Descripción general del corpus

* **Nombre:** Spanish Paragraph Simplification Benchmark – 5K (SPSB-5K).
* **Tamaño:** 5 000 pares de párrafos.
* **Origen de los textos:**

  * Adaptaciones en español de Newsela ES y FIRST.
  * Dominios científicos, históricos, técnicos, culturales y sociales.
  * Textos de dominio público: Wikipedia, Vikidia, Don Quijote, La Odisea, El Principito, etc.
* **Objetivo:**

  * Entrenamiento y evaluación de modelos automáticos de scoring de simplicidad relativa.
  * Conjunto de prueba para métricas como SARI, BERTScore, INFLESZ, LIX, BLEU, etc.

---

## 2. Estructura del archivo CSV

* **Formato:** CSV UTF-8.
* **Filas:** 5 000 registros más la fila de encabezado.
* **Columnas:**

  1. `original` (string): párrafo fuente (36 – 180 palabras).
  2. `simplificado` (string): párrafo reescrito (20 – 240 palabras).
  3. `calidad` (float): puntuación en rango –1.0 … +1.0.

---

## 3. Estadísticas descriptivas

| Métrica               | Original    | Simplificado |
| --------------------- | ----------- | ------------ |
| Caracteres (min–máx)  | 212 – 1 293 | 139 – 1 707  |
| Media de caracteres   | 752.4       | 479.2        |
| Mediana de caracteres | 767         | 250          |
| Palabras (min–máx)    | 36 – 180    | 20 – 240     |
| Media de palabras     | 105.0       | 69.95        |
| Mediana de palabras   | 106         | 42           |

---

## 4. Distribución de la puntuación de calidad

* **Media:** 0.3425
* **Mediana:** 0.555
* **Desviación estándar:** 0.5760
* **Mínimo:** –1.0
* **Máximo:** +1.0

| Rango        | Conteo | % respecto al total |
| ------------ | ------ | ------------------- |
| > 0 (simpl.) | 3 753  | 75.1 %              |
| < 0 (comp.)  | 1 230  | 24.6 %              |
| = 0          | 17     | 0.3 %               |

---

## 5. Tipología y duplicados

* **Duplicados exactos:** 13 (0.26 %).
* **Mismos originales con variantes:** 456 pares (9.12 %).

**Dominios cubiertos:** ciencia, salud, economía, historia, arte, tecnología, literatura, educación, entre otros.

---

## 6. Criterios de construcción y anotación

1. **Selección de textos:**

   * Inspirados en Newsela ES, FIRST y dominio público.
   * Temas variados para robustez semántica.
2. **Reescritura:**

   * Simplificaciones automáticas + revisión humana en muestras.
   * Complicaciones léxicas y sintácticas intencionales para casos negativos.
3. **Valoración de calidad:**

   * Escala –1.0 a +1.0 según claridad y complejidad.
   * Puntuaciones simuladas con criterios humanos y métricas automáticas.

---

## 7. Implicaciones de uso

* **Entrenamiento supervisado:** para predictores de calidad de simplificación.
* **Benchmark de métricas:** comparar SARI, BERTScore, INFLESZ, LIX, BLEU.
* **Evaluación de robustez:** tanto en simplificación como en complicación de textos.

---

*Este README acompaña al archivo `Corpus_SPSB-5K.csv` para su uso en proyectos de simplificación de texto en español.*
