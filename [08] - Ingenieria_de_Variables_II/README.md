# [08] - Ingeniería de Variables II

Notebooks prácticos de la sesión **Ingeniería de Variables II** del Máster en Data Science
(The Valley). El tema central es la **reducción de dimensionalidad**: cuando tienes muchísimas
columnas, ¿cómo te quedas con la información que de verdad importa? La herramienta principal es
**PCA** (y **TruncatedSVD** para texto/datos dispersos).

> *Más columnas no significa mejor modelo.*

Los datasets son **sintéticos y reproducibles**, generados dentro de cada notebook, así que
todo funciona en Colab sin descargar nada.

## Notebooks

| Notebook | Ejercicio (presentación) | Conceptos |
|---|---|---|
| [`E1_PCA_en_10_lineas.ipynb`](%5B01%5D%20-%20Notebooks/E1_PCA_en_10_lineas.ipynb) | **E1 · PCA en 10 líneas** | Escalar antes de PCA, varianza explicada, scree plot, varianza acumulada, elegir nº de componentes, error de no escalar |
| [`E2_Reduce_y_Modela.ipynb`](%5B01%5D%20-%20Notebooks/E2_Reduce_y_Modela.ipynb) | **E2 · Reduce y modela** | Pipeline escalar -> PCA -> LogisticRegression vs sin PCA; comparar AUC, nº de columnas y tiempo |
| [`E3_Visualiza_en_2D_con_PCA.ipynb`](%5B01%5D%20-%20Notebooks/E3_Visualiza_en_2D_con_PCA.ipynb) | **E3 · Visualiza en 2D con PCA** | Proyectar a 2 componentes, scatter, ver grupos, conexión con clustering |
| [`E4_Caza_la_Fuga_de_PCA.ipynb`](%5B01%5D%20-%20Notebooks/E4_Caza_la_Fuga_de_PCA.ipynb) | **E4 · Caza la fuga de PCA** *(bonus)* | Fuga del PCA (no supervisado, pequeña) vs fuga de una selección por el target (enorme); regla de oro del Pipeline |
| [`E5_Texto_Sparse_con_TruncatedSVD.ipynb`](%5B01%5D%20-%20Notebooks/E5_Texto_Sparse_con_TruncatedSVD.ipynb) | **E5 · Texto sparse con TruncatedSVD** *(bonus)* | TF-IDF (miles de columnas dispersas), TruncatedSVD a 50 componentes, comparar columnas, tiempo y AUC |

## Estructura

```
[08] - Ingenieria_de_Variables_II/
├── README.md
└── [01] - Notebooks/
    ├── E1_PCA_en_10_lineas.ipynb
    ├── E2_Reduce_y_Modela.ipynb
    ├── E3_Visualiza_en_2D_con_PCA.ipynb
    ├── E4_Caza_la_Fuga_de_PCA.ipynb
    └── E5_Texto_Sparse_con_TruncatedSVD.ipynb
```

## Los datasets

- **E1-E4** usan `generar_datos_anchos`: un dataset "ancho" (muchas columnas tipo sensor) cuya
  información real vive en unas pocas dimensiones latentes, con columnas correlacionadas y
  escalas muy distintas. Perfecto para ver cómo PCA recupera la estructura.
- **E5** usa `generar_resenas`: reseñas sintéticas en español (positivas/negativas) para
  vectorizar con TF-IDF y reducir con TruncatedSVD.

## Takeaways

1. Más columnas no es más información (maldición de la dimensionalidad: sparsity, ruido, coste).
2. Reducir = **seleccionar** (un subconjunto) o **extraer** (combinar, como PCA).
3. **Escala siempre antes de PCA** y mira la **varianza explicada**.
4. PCA dentro del **Pipeline**, con el `fit` solo en train. Cero fugas.
5. Para texto/datos dispersos, **TruncatedSVD** en lugar de PCA.

## Requisitos

- Python 3.8+
- `numpy`, `pandas`, `scikit-learn`, `matplotlib`

En Google Colab todas las dependencias vienen preinstaladas.
