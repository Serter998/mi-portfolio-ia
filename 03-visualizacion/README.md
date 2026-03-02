# Ejercicios de Visualización de Datos con Python

Este repositorio contiene dos ejercicios integradores de análisis y visualización de datos utilizando las librerías matplotlib, pandas, numpy y seaborn.

## 📊 Contenido

### 1. Observatorio Turístico - Análisis con Matplotlib
**Dataset:** 3.000 reservas turísticas en España (2024)

**Tecnologías:** NumPy, Pandas, Matplotlib

**Ejercicios incluidos:**
- **Ejercicio 0:** Generación del dataset con arrays NumPy
- **Ejercicio 1:** Exploración inicial con Pandas (head, info, describe, value_counts)
- **Ejercicio 2:** Limpieza de datos (duplicados, nulos, imputación con mediana)
- **Ejercicio 3:** Feature engineering temporal (extracción de mes, trimestre, temporadas)
- **Ejercicio 4:** Filtrado booleano avanzado (segmentación de mercado)
- **Ejercicio 5:** Agrupaciones y agregaciones (groupby, pivot_table, rankings)
- **Ejercicio 6:** Gráfico de líneas - Evolución de ocupación mensual
- **Ejercicio 7:** Scatter plot con línea de tendencia (precio vs ocupación)
- **Ejercicio 8:** Dashboard final 2x2 (barras, pie, heatmap, boxplot)

**Variables del dataset:**
- Comunidades autónomas (Andalucía, Cataluña, C. Valenciana, Madrid, Baleares, Canarias, País Vasco, Galicia)
- Tipos de alojamiento (Hotel, Apartamento, Hostal, Rural)
- Origen turista (Nacional, UE, Internacional)
- Métricas: noches, precio_noche, ocupación_pct, valoración, ingreso_total

---

### 2. EDA Hotelera - Análisis con Seaborn
**Dataset:** 1.200 encuestas de satisfacción - Hotel Costa Brava

**Tecnologías:** NumPy, Pandas, Matplotlib, Seaborn

**Ejercicios incluidos:**
- **Ejercicio 0:** Configuración de Seaborn (temas, contextos, exploración inicial)
- **Ejercicio 1:** Distribuciones univariantes (histplot, kdeplot por segmento)
- **Ejercicio 2:** Comparaciones categóricas (boxplot, violinplot con split)
- **Ejercicio 3:** Relaciones bivariantes (scatterplot multidimensional, regplot)
- **Ejercicio 4:** Análisis por segmentos con facetas (catplot con col_wrap)
- **Ejercicio 5:** Mapa de calor de correlaciones (heatmap con máscara triangular)
- **Ejercicio 6:** Exploración multivariante (pairplot con hue por NPS)
- **Ejercicio 7:** Dashboard ejecutivo 2x2 profesional

**Variables del dataset:**
- Mes (Ene-Dic)
- Tipo de cliente (Familiar, Pareja, Negocio, Solo)
- Canal de reserva (Web, Booking, Agencia, Directo)
- Métricas: satisfacción (1-10), precio, noches (1-7), edad (18-80)
- NPS (Promotor, Pasivo, Detractor)
- Repetidor (binario)

---

## 🛠️ Requisitos
```bash
pip install numpy pandas matplotlib seaborn --break-system-packages
```

**Versiones recomendadas:**
- Python 3.8+
- NumPy 1.24+
- Pandas 2.0+
- Matplotlib 3.7+
- Seaborn 0.12+

---

## 📁 Estructura del Proyecto
```
.
├── observatorio_turistico.ipynb    # Ejercicios Matplotlib
├── seaborn_eda_hotelera.ipynb     # Ejercicios Seaborn
└── README.md                       # Este archivo
```

---

## 🚀 Uso

### Observatorio Turístico (Matplotlib)
```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

# El dataset se genera sintéticamente con NumPy
# Ejecuta las celdas secuencialmente desde el Ejercicio 0
```

### EDA Hotelera (Seaborn)
```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Configuración inicial
sns.set_theme(style='whitegrid')
sns.set_context('notebook', font_scale=1.1)

# El dataset se genera sintéticamente
# Ejecuta las celdas secuencialmente desde el Ejercicio 0
```

---

## 📈 Conceptos Clave Aprendidos

### Matplotlib
- Generación de arrays con `np.random` (uniform, normal, choice)
- Operaciones vectorizadas (`np.clip`, `np.round`)
- Exploración con Pandas (`head()`, `info()`, `describe()`, `value_counts()`)
- Limpieza de datos (`duplicated()`, `isnull()`, `fillna()`, `drop_duplicates()`)
- Feature engineering temporal (`.dt.month`, `.dt.quarter`, `.dt.dayofweek`)
- Filtrado booleano con operadores `&`, `|`, `~`
- Agrupaciones (`groupby()`, `pivot_table()`, `sort_values()`, `nlargest()`)
- Subplots con `plt.subplots()`
- Gráficos: líneas, scatter, barras horizontales, pie, heatmap, boxplot
- Líneas de tendencia con `np.polyfit()`

### Seaborn
- Configuración de temas (`set_theme()`, `set_context()`)
- Distribuciones (`histplot`, `kdeplot` con `hue` y `fill`)
- Comparaciones (`boxplot`, `violinplot` con `split`)
- Relaciones (`scatterplot` con `size`, `regplot` con intervalos de confianza)
- Facetas automáticas (`catplot` con `col` y `col_wrap`)
- Correlaciones (`heatmap` con máscaras triangulares)
- Exploración multivariante (`pairplot` con `corner=True`)
- Dashboards profesionales (múltiples visualizaciones en grids)
- Paletas de colores personalizadas
- `sns.despine()` para gráficos limpios

---

## 💡 Técnicas Destacadas

### Observatorio Turístico
- **Inyección controlada de nulos** para practicar limpieza de datos
- **Duplicados intencionales** (3% del dataset)
- **Clasificación de temporadas** con `np.select()`
- **Filtrado complejo** para análisis de segmentos (lujo, económico, islas)
- **Rankings dinámicos** con `sort_values()` y `nlargest()`
- **Visualización de evolución temporal** con múltiples series
- **Anotaciones en scatter plots** para destacar valores extremos

### EDA Hotelera
- **Violinplot con split** para comparar Promotores vs Detractores
- **Máscara triangular** en heatmaps para evitar redundancia
- **Pairplot con corner** para matriz compacta
- **Paletas personalizadas** según categoría NPS (verde/amarillo/rojo)
- **Pivot tables** para análisis cruzado tipo_cliente × canal
- **Regresión lineal** con intervalos de confianza
- **FacetGrid automático** con `catplot` para análisis por segmentos

---

## 📊 Visualizaciones Generadas

### Matplotlib (8 gráficos)
1. Gráfico de líneas - Evolución mensual de ocupación (top 4 CCAA)
2. Scatter plot - Precio vs ocupación con tendencia lineal
3. Dashboard 2x2:
   - Barras horizontales: ingreso medio por tipo
   - Pie chart: origen del turista
   - Heatmap: ocupación por CCAA y trimestre
   - Boxplot: valoraciones top 4 comunidades

### Seaborn (15+ gráficos)
1. Histograma + KDE de satisfacción general
2. KDE por tipo de cliente
3. Boxplot por tipo de cliente
4. Violinplot split Promotores/Detractores por canal
5. Scatterplot multidimensional precio vs satisfacción
6. Regplot con intervalo de confianza
7. Catplot con facetas (4 paneles)
8. Heatmap de correlaciones con máscara
9. Pairplot 4x4 variables coloreado por NPS
10. Dashboard final 2x2 ejecutivo

---

## 🎯 Objetivos de Aprendizaje

- ✅ Generación sintética de datasets realistas con NumPy
- ✅ Limpieza y preparación de datos con Pandas
- ✅ Feature engineering y transformaciones temporales
- ✅ Análisis exploratorio de datos (EDA)
- ✅ Visualización efectiva con Matplotlib y Seaborn
- ✅ Creación de dashboards profesionales
- ✅ Interpretación de correlaciones y tendencias
- ✅ Segmentación y análisis por cohortes
- ✅ Comunicación visual de insights

---

## 📝 Notas

- Ambos datasets son **sintéticos** generados con `np.random.seed(42)` para reproducibilidad
- Los ejercicios están diseñados para ser completados **secuencialmente**
- Cada ejercicio construye sobre los anteriores
- Se incluyen soluciones comentadas para referencia
- Backend configurado: `matplotlib.use('Agg')` para entornos sin interfaz gráfica

---

## 👨‍💻 Autor

Sergio - Estudiante de Máster en IA y Big Data

---

## 📚 Referencias

- [Documentación NumPy](https://numpy.org/doc/)
- [Documentación Pandas](https://pandas.pydata.org/docs/)
- [Documentación Matplotlib](https://matplotlib.org/stable/contents.html)
- [Documentación Seaborn](https://seaborn.pydata.org/)
- [Kobalto Cursos](https://kobalto.com)