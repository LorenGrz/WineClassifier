# Wine Classifier

Clasificador de tipo de vino usando características químicas del dataset **Wine Quality**.

El proyecto forma parte de un trabajo práctico de Matemática III. La idea inicial era predecir la calidad del vino, pero durante el análisis exploratorio se observó que la variable `quality` no presentaba una relación lineal suficientemente fuerte con las características disponibles. Por ese motivo, el enfoque se reformuló hacia un problema de clasificación binaria: predecir si un vino es **blanco** o **tinto**.

## Objetivo

Entrenar y evaluar modelos capaces de clasificar el tipo de vino (`white` o `red`) a partir de variables físico-químicas del dataset.

La variable objetivo es:

- `type = 1`: vino blanco.
- `type = 0`: vino tinto.

## Dataset

El dataset utilizado es `WineQuality.csv`, incluido en este repositorio.

Fuente original: [Wine Quality Dataset en Kaggle](https://www.kaggle.com/datasets/rajyellow46/wine-quality)

El archivo contiene **6.497 registros** y las siguientes columnas:

- `type`
- `fixed acidity`
- `volatile acidity`
- `citric acid`
- `residual sugar`
- `chlorides`
- `free sulfur dioxide`
- `total sulfur dioxide`
- `density`
- `pH`
- `sulphates`
- `alcohol`
- `quality`

## Enfoque del trabajo

El notebook desarrolla el proyecto en estas etapas:

1. Carga e inspección inicial del dataset.
2. Limpieza de datos.
3. Codificación de la variable `type`.
4. Selección y normalización de variables predictoras.
5. Análisis exploratorio y matriz de correlación.
6. Entrenamiento de una red neuronal implementada manualmente con NumPy.
7. Evaluación de precisión en entrenamiento y prueba.
8. Experimentación con tasa de aprendizaje e iteraciones.
9. Comparación con una red neuronal de `scikit-learn`.
10. Pruebas de predicción sobre ejemplos aleatorios.

## Variables utilizadas

Las variables seleccionadas para entrenar el modelo son:

```python
features = [
    "fixed acidity",
    "volatile acidity",
    "chlorides",
    "free sulfur dioxide",
    "total sulfur dioxide",
    "density",
    "pH",
    "sulphates",
]
```

Estas variables fueron elegidas porque aportan información útil para distinguir entre vino blanco y tinto dentro del dataset.

## Estructura del repositorio

```text
.
├── ConsignasTP.pdf          # Consigna original del trabajo práctico
├── Img/
│   └── Realidad.jpg         # Imagen usada en el README original
├── README.md                # Documentación del proyecto
├── TP_LORENZO_v2.ipynb      # Notebook principal del análisis y modelo
├── WineQuality.csv          # Dataset local
└── requirements.txt         # Dependencias necesarias
```

## Instalación

Crear un entorno virtual:

```bash
python -m venv .venv
source .venv/bin/activate
```

Instalar dependencias:

```bash
pip install -r requirements.txt
```

## Ejecución

Abrir Jupyter:

```bash
jupyter notebook
```

Luego ejecutar:

```text
TP_LORENZO_v2.ipynb
```

También se puede abrir el notebook desde VS Code, Cursor, JupyterLab o cualquier editor compatible con `.ipynb`.

## Modelos implementados

### Red neuronal manual

El notebook implementa una red neuronal simple desde cero usando NumPy:

- capa de entrada con las variables seleccionadas;
- capa oculta de 4 neuronas;
- activación ReLU en la capa oculta;
- activación logística en la salida;
- entrenamiento mediante descenso de gradiente estocástico;
- evaluación por accuracy.

### Red neuronal con scikit-learn

También se entrena un `MLPClassifier` de `scikit-learn` para comparar el enfoque manual con una implementación de librería.

## Resultado esperado

El trabajo muestra que el tipo de vino puede clasificarse con buena precisión usando variables físico-químicas. También permite comparar la implementación manual de una red neuronal con una herramienta estándar de machine learning.

## Notas

- La predicción de `quality` fue descartada como objetivo principal porque no mostraba una correlación lineal clara con las variables disponibles.
- El dataset está desbalanceado: hay más vinos blancos que tintos. Por eso, la accuracy debe interpretarse con cuidado.
- Para mejorar el proyecto en futuras versiones, convendría agregar matriz de confusión, precision, recall, F1-score y validación cruzada.
