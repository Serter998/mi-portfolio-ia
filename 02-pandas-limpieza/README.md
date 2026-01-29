# Proyecto Portfolio 2: Limpieza y Exploración de Datos - Dataset Titanic

## 📋 Descripción del Proyecto

Análisis exhaustivo del dataset histórico del Titanic para identificar factores que influyeron en la supervivencia de los pasajeros. Este proyecto forma parte del Módulo de Programación de IA del Máster en Inteligencia Artificial y Big Data.

**Contexto**: El 15 de abril de 1912, el RMS Titanic se hundió tras chocar con un iceberg. De los 2.224 pasajeros y tripulantes a bordo, más de 1.500 perdieron la vida. Este análisis sirve para desarrollar modelos de riesgo y políticas de evacuación basadas en datos históricos.

## 🎯 Objetivos

- Realizar limpieza y preparación de datos siguiendo estándares de la industria
- Detectar y gestionar valores faltantes, inconsistencias y duplicados
- Identificar patrones de supervivencia según variables demográficas y socioeconómicas
- Crear un pipeline de transformación reutilizable para modelado predictivo

## 📊 Dataset

**Fuente**: [Kaggle - Titanic Dataset](https://raw.githubusercontent.com/datasciencedojo/datasets/master/titanic.csv)

**Dimensiones**: 891 filas × 12 columnas

**Variables principales**:
- `Survived`: Variable objetivo (0=No, 1=Sí)
- `Pclass`: Clase del billete (1=Primera, 2=Segunda, 3=Tercera)
- `Sex`: Sexo del pasajero
- `Age`: Edad en años (~20% missing)
- `Fare`: Tarifa pagada en libras
- `Embarked`: Puerto de embarque (C/Q/S)
- `Cabin`: Número de cabina (~77% missing)

## 🔧 Tecnologías Utilizadas

- **Python 3.x**
- **Pandas**: Manipulación y análisis de datos
- **NumPy**: Operaciones numéricas
- **Jupyter Notebook**: Entorno de desarrollo interactivo

## 📁 Estructura del Proyecto
```
proyecto-titanic/
│
├── titanic_analysis.ipynb    # Notebook principal con análisis completo
├── README.md                  # Documentación del proyecto
└── requirements.txt           # Dependencias (opcional)
```

## 🚀 Ejecución del Proyecto

1. **Clonar/descargar el repositorio**

2. **Instalar dependencias**:
```bash
pip install pandas numpy jupyter
```

3. **Ejecutar el notebook**:
```bash
jupyter notebook titanic_analysis.ipynb
```

## 📈 Metodología

### Bloque 1: Exploración Inicial
- Inspección dimensional y tipos de datos
- Estadísticas descriptivas
- Distribución de variables categóricas

### Bloque 2: Diagnóstico de Calidad
- Mapa de valores faltantes
- Análisis de la variable `Cabin` (77% missing)
- Detección de duplicados
- Validación de consistencia y detección de outliers

### Bloque 3: Tratamiento de Valores Faltantes
- **Age**: Imputación estratificada por título (Mr, Mrs, Miss, Master) usando mediana
- **Cabin**: Creación de variable binaria `HasCabin` (77% missing imposibilita imputación)
- **Embarked**: Imputación basada en análisis de pasajeros similares (clase + tarifa)

### Bloque 4: Análisis Exploratorio de Supervivencia
- Supervivencia por sexo (validación principio "mujeres y niños primero")
- Supervivencia por clase socioeconómica
- Análisis multivariado (sexo × clase)
- Segmentación por grupos etarios
- Efecto del tamaño familiar

### Bloque 5: Pipeline de Limpieza
Función reutilizable `limpiar_titanic(df)` que aplica todas las transformaciones:
- Extracción de título del nombre
- Imputación de Age por título
- Creación de HasCabin
- Imputación de Embarked
- Creación de FamilySize y AgeGroup
- Eliminación de columnas innecesarias

## 🔍 Hallazgos Principales

### 1. Supervivencia por Sexo
- **Mujeres**: ~74% de supervivencia
- **Hombres**: ~19% de supervivencia
- **Conclusión**: Confirma el protocolo "mujeres y niños primero"

### 2. Supervivencia por Clase
- **1ª clase**: 63% de supervivencia
- **2ª clase**: 47% de supervivencia
- **3ª clase**: 24% de supervivencia
- **Conclusión**: Disparidad socioeconómica (3x más probabilidad en 1ª vs 3ª)

### 3. Análisis Cruzado Sexo-Clase
- Una mujer de 3ª clase tenía más probabilidades de sobrevivir que un hombre de 1ª clase
- El sexo fue un factor más determinante que la clase socioeconómica

### 4. Efecto de la Edad
- **Niños (0-12)**: Mayor tasa de supervivencia
- **Mayores (60+)**: Menor tasa de supervivencia
- **Conclusión**: Los niños recibieron prioridad en la evacuación

### 5. Efecto del Tamaño Familiar
- **Familias pequeñas (2-4)**: Mayor supervivencia
- **Personas solas**: Supervivencia intermedia
- **Familias grandes (5+)**: Menor supervivencia
- **Hipótesis**: Familias pequeñas facilitan coordinación; familias grandes dificultan evacuación

## 📊 Decisiones Técnicas Clave

### Imputación de Age
**Estrategia**: Mediana por título (Mr, Mrs, Miss, Master)

**Justificación**:
- Robustez a outliers
- Distribución con sesgo (no simétrica)
- Diferentes títulos tienen rangos etarios muy distintos (Master ~4 años, Mr ~30 años)

### Gestión de Cabin
**Estrategia**: Variable binaria `HasCabin` (no imputación)

**Justificación**:
- 77% de valores faltantes imposibilita imputación confiable
- La presencia/ausencia de registro puede ser predictor de clase social
- Conserva información útil sin especular datos

### Detección de Outliers
**Método**: IQR (Interquartile Range) con umbral Q3 + 3×IQR

**Aplicación**: Tarifas extremas detectadas (máx: 512.33 vs media: 32.20)

## 💡 Competencias Desarrolladas

✅ Carga y exploración de datos con Pandas  
✅ Diagnóstico de calidad (missing, outliers, duplicados)  
✅ Estrategias de imputación avanzadas (stratified imputation)  
✅ Operaciones groupby, transform, crosstab  
✅ Creación de pipelines reutilizables  
✅ Análisis exploratorio y visualización de patrones  

## 📝 Autor

**Sergio**  
Máster en Inteligencia Artificial y Big Data  
Fecha de realización: 21-27 de enero de 2026

## 📚 Referencias

- [Kaggle Titanic Competition](https://www.kaggle.com/c/titanic)
- [Pandas Documentation](https://pandas.pydata.org/docs/)
- Organización Marítima Internacional (OMI) - Regulaciones SOLAS

---

*Este proyecto demuestra la aplicación práctica de técnicas de preparación de datos siguiendo estándares industriales, replicando el flujo de trabajo típico donde el 80% del tiempo de ML se dedica a limpieza y exploración.*