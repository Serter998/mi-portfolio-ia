# Proyecto Portfolio 1: Análisis de Datos Meteorológicos con NumPy

## 📋 Descripción del Proyecto

Análisis exhaustivo de datos meteorológicos sintéticos de 5 estaciones españolas utilizando técnicas avanzadas de NumPy. Este proyecto forma parte del Módulo de Programación de IA del Máster en Inteligencia Artificial y Big Data.

**Contexto**: El análisis de datos meteorológicos es fundamental para la predicción climática, gestión de recursos energéticos y planificación urbana. Este proyecto simula el procesamiento de mediciones horarias de múltiples variables atmosféricas durante un mes completo en estaciones distribuidas geográficamente.

## 🎯 Objetivos

- Dominar operaciones avanzadas con arrays multidimensionales de NumPy
- Aplicar técnicas de indexing, slicing y broadcasting en datos reales
- Implementar análisis estadísticos e identificación de patrones meteorológicos
- Desarrollar habilidades de manipulación eficiente de datos sin bucles explícitos

## 📊 Dataset

**Fuente**: Generación sintética con seed fijada (reproducible)

**Dimensiones**: (5, 30, 24, 6) → 21.600 mediciones totales

**Variables principales**:
- `Temperatura`: Medición en °C con variación diurna sinusoidal
- `Humedad`: Porcentaje de humedad relativa (30-100%)
- `Presión`: Presión atmosférica en hPa (~1013)
- `Viento`: Velocidad del viento en km/h
- `Precipitación`: Acumulación horaria en mm
- `Radiación`: Radiación solar en W/m² (0-800)

**Estaciones**: Madrid, Barcelona, Valencia, Sevilla, Bilbao

## 🔧 Tecnologías Utilizadas

- **Python 3.x**
- **NumPy**: Manipulación de arrays multidimensionales y operaciones vectorizadas
- **Entorno virtual**: Gestión aislada de dependencias

## 📁 Estructura del Proyecto
```
01-numpy-analisis/
├── datos-meteo/
│   ├── dataset_meteorologico.py    # Generación de datos sintéticos
│   └── datos_meteorologicos.npy    # Dataset serializado
├── analisis_meteorologico.py       # Script principal de análisis
└── README.md
```

## 🔍 Análisis Implementados

### Fase 1: Verificación y Extracción
- **01. Verificación de estructura**: Validación de dimensiones y tipos de datos
- **02. Series temporales**: Extracción de temperatura de una estación en un día específico
- **03. Comparativa entre estaciones**: Análisis transversal a una hora determinada
- **04. Bloques de datos**: Extracción de datos de primera semana de una estación

### Fase 2: Estadística Descriptiva
- **05. Temperatura media por estación**: Identificación de estaciones extremas (más cálida/fría)
- **06. Perfil horario medio**: Patrón térmico diario típico
- **07. Variabilidad climática**: Desviación estándar por estación
- **08. Extremos meteorológicos**: Localización de temperatura máxima y mínima absoluta

### Fase 3: Análisis Avanzados
- **09. Detección de heladas**: Identificación de mediciones < 0°C y porcentaje
- **10. Días de lluvia significativa**: Detección de días con precipitación > 10mm
- **11. Condiciones de confort**: Análisis de habitabilidad (temp 18-24°C, humedad 40-60%, viento <20km/h)
- **12. Normalización Min-Max**: Escalado de variables al rango [0,1]
- **13. Anomalías térmicas**: Desviaciones respecto a media por estación
- **14. Correlaciones**: Matriz de correlación de Pearson entre variables
- **15. Potencial energético solar**: Ranking de estaciones por radiación acumulada

## 🛠️ Técnicas de NumPy Aplicadas

- **Indexing avanzado**: Slicing multidimensional y extracción de subarrays
- **Broadcasting**: Operaciones entre arrays de shapes diferentes
- **Reducción de ejes**: `mean()`, `sum()`, `std()` con parámetro `axis`
- **Máscaras booleanas**: Filtrado con operadores `&`, `|`
- **np.where()**: Localización de elementos que cumplen condiciones
- **np.unravel_index()**: Conversión de índices planos a coordenadas multidimensionales
- **np.corrcoef()**: Cálculo de matriz de correlación
- **np.argsort()**: Generación de rankings

## 🚀 Instalación y Uso

### Requisitos
```bash
Python 3.8+
numpy>=1.24.0
```

### Instalación
```bash
# Clonar repositorio
cd mi-portfolio-ia/01-numpy-analisis

# Crear entorno virtual
python -m venv .venv
source .venv/bin/activate  # Linux/Mac
.venv\Scripts\activate     # Windows

# Instalar dependencias
pip install numpy
```

### Ejecución
```bash
# Generar dataset
python datos-meteo/dataset_meteorologico.py

# Ejecutar análisis
python analisis_meteorologico.py
```

## 📈 Resultados Principales

- **Patrón diurno**: Temperatura máxima entre 14-15h, mínima a las 6h
- **Correlación temp-humedad**: -0.7 (negativa, coherente con física atmosférica)
- **Porcentaje de heladas**: ~X% de mediciones con temperatura < 0°C
- **Condiciones de confort**: ~X% de mediciones cumplen criterios simultáneos
- **Potencial solar**: Estación con mayor radiación acumulada identificada

## 📝 Notas

- Seed fijada (`np.random.seed(42)`) para reproducibilidad
- Datos sintéticos sin inercia temporal real
- Formato `.npy` para serialización eficiente de arrays NumPy

## 👨‍💻 Autor

**Sergio**  
Máster en Inteligencia Artificial y Big Data  
Grado Superior en Desarrollo de Aplicaciones Multiplataforma

---

*Proyecto académico - Programación de IA y Sistemas de Machine Learning*