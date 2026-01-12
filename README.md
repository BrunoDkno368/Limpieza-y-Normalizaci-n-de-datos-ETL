# Proyecto ETL – Limpieza, Normalización y Validación de Datos con Python

## 📌 Descripción general

Este repositorio documenta un proyecto completo de **ETL (Extract, Transform, Load)** aplicado a un dataset con **datos sucios, inconsistentes y no estructurados**, simulando un escenario real de trabajo en **Análisis de Datos / Data Analytics**.

El objetivo principal es demostrar competencias técnicas en:

* Procesos ETL con Python
* Limpieza y calidad de datos (Data Cleaning & Data Quality)
* Normalización y estandarización de información
* Aplicación de reglas de negocio
* Preparación de datos para análisis, reporting o carga en bases de datos

Este tipo de procesos es habitual en entornos de **Business Intelligence, Data Analytics, Data Engineering Junior** y proyectos de analítica aplicada.

---

## 🛠️ Tecnologías y herramientas

* **Python 3**
* **Pandas** (manipulación y transformación de datos)
* **NumPy** (operaciones numéricas)
* **Google Colab** (entorno de desarrollo)
* **CSV** como fuente de datos

**Palabras clave:** ETL, Data Cleaning, Data Wrangling, Pandas, Python, Data Quality, Data Analytics, Business Intelligence

---

## 📂 Estructura del dataset

Dataset original con información de clientes y compras.

Columnas:

* `id`
* `nombre`
* `edad`
* `fecha_registro`
* `monto_compra`
* `provincia`

Dimensiones iniciales:

* **Filas:** 11
* **Columnas:** 6

---

## 🔄 Proceso ETL

### 1️⃣ Extract (Extracción de datos)

* Lectura del archivo CSV utilizando Pandas.
* Creación de una copia del DataFrame original para preservar la fuente de datos.
* Inspección inicial de dimensiones, tipos de datos y valores únicos.

**Objetivo:** garantizar trazabilidad y evitar modificaciones sobre los datos crudos.

---

### 2️⃣ Transform (Transformación y limpieza de datos)

Esta es la fase central del proyecto, donde se aplican múltiples técnicas de **Data Cleaning**.

---

### 🔹 Limpieza y normalización de columnas de texto

**Columnas trabajadas:** `nombre`, `provincia`

Problemas detectados:

* Espacios innecesarios
* Diferencias de mayúsculas/minúsculas
* Valores nulos o vacíos
* Errores tipográficos
* Uso de símbolos especiales
* Inconsistencias semánticas

Acciones aplicadas:

* Conversión a tipo string
* Eliminación de espacios al inicio y final
* Normalización de capitalización
* Reemplazo de valores nulos por `Sin datos`
* Limpieza de caracteres no alfabéticos
* Corrección manual de valores inconsistentes

Ejemplos:

* `Ju@n` → `Juan`
* `Mar ia` → `María`
* `Tucuman` → `Tucumán`
* `Bs As` → `Buenos Aires`

**Conceptos clave:** Text Normalization, Data Standardization, Data Consistency

---

### 🔹 Limpieza de la columna `edad`

Problemas detectados:

* Valores no numéricos (`treinta`)
* Edades negativas
* Edades fuera de rango (`200`)
* Valores nulos

Reglas de negocio aplicadas:

* Edad válida entre **0 y 120 años**

Transformaciones realizadas:

* Conversión a numérico con control de errores
* Reemplazo de valores inválidos por `NaN`
* Imputación de valores faltantes mediante la **media**
* Conversión final a entero

**Conceptos clave:** Data Validation, Outlier Detection, Missing Values Imputation

---

### 🔹 Limpieza de la columna `monto_compra`

Problemas detectados:

* Formatos numéricos mixtos (`1.200,30`, `1500.5`)
* Valores negativos
* Valores extremadamente altos
* Celdas vacías o con espacios

Reglas de negocio aplicadas:

* No se permiten montos negativos
* Montos mayores a **90.000** se consideran atípicos

Transformaciones realizadas:

* Normalización de separadores decimales
* Conversión a tipo numérico
* Detección y eliminación de outliers
* Imputación de valores faltantes con la media redondeada

**Conceptos clave:** Numeric Parsing, Outliers, Business Rules, Data Quality

---

### 🔹 Limpieza de la columna `fecha_registro`

Problemas detectados:

* Múltiples formatos de fecha
* Fechas inválidas
* Fechas con texto en español
* Fechas con componente horario

Transformaciones realizadas:

* Conversión inicial a texto
* Traducción de meses del español al inglés
* Unificación de separadores
* Corrección manual de casos puntuales
* Conversión final a tipo `datetime`

**Conceptos clave:** Date Parsing, Time Series Preparation, Data Standardization

---

### 3️⃣ Load (Carga de datos)

* Eliminación de columnas auxiliares
* Consolidación del DataFrame final
* Dataset listo para:

  * Análisis exploratorio (EDA)
  * Visualización
  * Reporting
  * Carga en bases de datos

---

## ✅ Resultado final

El dataset resultante:

* Presenta **consistencia semántica y estructural**
* Tiene **tipos de datos correctos**
* Cumple reglas básicas de negocio
* Está preparado para análisis y toma de decisiones

---

## 🎯 Objetivos del proyecto

* Simular un proceso ETL real
* Aplicar buenas prácticas de limpieza de datos
* Demostrar pensamiento analítico
* Fortalecer un portfolio profesional en Data Analytics

---

## 🚀 Mejoras futuras

* Automatización del pipeline ETL
* Validaciones con tests de calidad de datos
* Análisis exploratorio de datos (EDA)
* Visualizaciones
* Persistencia en base de datos (SQL)

---

## 👤 Autor

**Bruno Argañaraz**
Analista de Datos
Tucumán, Argentina
LinkedIn: [https://www.linkedin.com/in/bruno-arga%C3%B1araz-726a4a199/](https://www.linkedin.com/in/bruno-arga%C3%B1araz-726a4a199/)

---
