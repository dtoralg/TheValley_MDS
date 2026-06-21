# [01] - Introducción a los modelos no supervisados

Notebooks prácticos de la sesión **Introducción a los modelos no supervisados** del Máster en
Data Science (The Valley). El tema es el **clustering**: agrupar lo parecido cuando **no hay
etiquetas**, midiendo distancias, escalando bien y eligiendo e interpretando los grupos.

> *Sin etiquetas, buscamos estructura en los datos.*

El dataset es **sintético y reproducible** (clientes para segmentar), generado dentro de cada
notebook, así que todo funciona en Colab sin descargar nada.

## Notebooks

| Notebook | Ejercicio (presentación) | Conceptos |
|---|---|---|
| [`E1_Distancias_y_Efectos_de_Escala.ipynb`](%5B01%5D%20-%20Notebooks/E1_Distancias_y_Efectos_de_Escala.ipynb) | **E1 · Distancias y efectos de escala** | Distancias Euclídea, Manhattan y Minkowski; Jaccard y coeficiente simple; por qué escalar es obligatorio |
| [`E2_KMeans_Completo.ipynb`](%5B01%5D%20-%20Notebooks/E2_KMeans_Completo.ipynb) | **E2 · K-Means completo** | K-Means con k-means++, centroides, método del codo (inercia), Silhouette Score, elegir K y describir clusters |
| [`E3_KMedoids_E2E.ipynb`](%5B01%5D%20-%20Notebooks/E3_KMedoids_E2E.ipynb) | **E3 · K-Medoids E2E** | K-Medoids implementado desde cero con el mismo K que K-Means; centroide (promedio) vs medoide (cliente real), cliente representante de cada grupo y robustez a outliers |
| [`E4_Defiende_tu_K.ipynb`](%5B01%5D%20-%20Notebooks/E4_Defiende_tu_K.ipynb) | **E4 · Defiende tu K** *(bonus)* | Elegir K con 3 evidencias (codo/silhouette, interpretabilidad y acción de negocio) y redactar una recomendación |

Cada notebook incluye un botón **"Open In Colab"** al principio para abrirlo directamente.

## Estructura

```
[01] - Intro_No_Supervisados/
├── README.md
└── [01] - Notebooks/
    ├── E1_Distancias_y_Efectos_de_Escala.ipynb
    ├── E2_KMeans_Completo.ipynb
    ├── E3_KMedoids_E2E.ipynb
    └── E4_Defiende_tu_K.ipynb
```

## El dataset

`generar_clientes` crea una base de clientes **sin etiqueta** con variables de negocio
(`gasto_anual`, `num_visitas`, `ticket_medio`, `antiguedad_meses`, `edad`) y varias binarias
(`usa_app`, `tiene_tarjeta_fidelidad`, `compra_online`...). Las variables tienen **escalas muy
distintas** a propósito, para ver por qué hay que escalar antes de agrupar. Por dentro hay 4
perfiles latentes que el clustering debería redescubrir, pero no se exponen como etiqueta.

## Takeaways

1. Sin target, el objetivo es **descubrir estructura**.
2. Clustering = agrupar lo parecido por **distancia**.
3. **Escala antes de agrupar**: la distancia depende de la escala.
4. **K-Means**: centros que se ajustan por iteración; elige K con codo y silhouette.
5. **K-Medoids**: el centro es un dato real. Y recuerda: sin interpretar, no hay valor.

## Requisitos

- Python 3.8+
- `numpy`, `pandas`, `scikit-learn`, `scipy`, `matplotlib`

En Google Colab todas las dependencias vienen preinstaladas.
