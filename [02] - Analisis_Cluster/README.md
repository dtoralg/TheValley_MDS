# [02] - Análisis cluster

Notebooks prácticos de la sesión **Análisis cluster** del Máster en Data Science (The Valley).
Consolidamos **K-Means** y sumamos dos métodos nuevos, **clustering jerárquico** y **DBSCAN**,
y cerramos con el **profiling** (convertir grupos en perfiles de negocio accionables).

> No hay un único clustering: cada método asume una forma distinta de grupo.

Siempre que es posible usamos **datasets reales** (Mall Customers, Iris, Wine), más educativos
que los sintéticos. Solo en DBSCAN generamos datos a propósito (las "lunas"), porque es la forma
ideal para ver su ventaja.

## Notebooks de esta sesión

| Notebook | Ejercicio (presentación) | Dataset | Conceptos |
|---|---|---|---|
| [`E1_KMeans_K_Optimo_Mall.ipynb`](%5B01%5D%20-%20Notebooks/E1_KMeans_K_Optimo_Mall.ipynb) | **E1 · Repaso aplicado: K óptimo** | Mall Customers | Escalado, k-means++, método del codo y Silhouette (K=2..6), elegir y justificar K |
| [`E2_Dendrograma_y_Corte_Iris.ipynb`](%5B01%5D%20-%20Notebooks/E2_Dendrograma_y_Corte_Iris.ipynb) | **E2 · Dendrograma y corte** | Iris | Clustering jerárquico, linkage 'ward', dendrograma, cortes en 2/3/4 grupos |
| [`E3_DBSCAN_vs_KMeans_Moons.ipynb`](%5B01%5D%20-%20Notebooks/E3_DBSCAN_vs_KMeans_Moons.ipynb) | **E3 · DBSCAN vs K-Means en Moons** | make_moons | Densidad, `eps` y `min_samples`, puntos de ruido, formas no compactas |
| [`E4_Profiling_de_Clusters_Mall.ipynb`](%5B01%5D%20-%20Notebooks/E4_Profiling_de_Clusters_Mall.ipynb) | **E4 · Perfila y nombra tus clusters** | Mall Customers | Perfil medio, índice vs media global, variables discriminantes, nombre + acción |
| [`E5_Caso_End_to_End_Wine.ipynb`](%5B01%5D%20-%20Notebooks/E5_Caso_End_to_End_Wine.ipynb) | **E5 · Caso end-to-end** *(bonus)* | Wine | Comparar K-Means/jerárquico/DBSCAN, elegir, perfilar y recomendar |

Cada notebook incluye un botón **"Open In Colab"** al principio.

## Estructura

```
[02] - Analisis_Cluster/
├── README.md
├── [00] - Data/
└── [01] - Notebooks/
    ├── E1_KMeans_K_Optimo_Mall.ipynb        (sesión actual)
    ├── E2_Dendrograma_y_Corte_Iris.ipynb    (sesión actual)
    ├── E3_DBSCAN_vs_KMeans_Moons.ipynb      (sesión actual)
    ├── E4_Profiling_de_Clusters_Mall.ipynb  (sesión actual)
    ├── E5_Caso_End_to_End_Wine.ipynb        (sesión actual)
    └── ... (notebooks de versiones anteriores: Bank, Jerárquico IRIS, DBSCAN, K-Means IRIS, comparación MALL)
```

## Los datasets

- **Mall Customers** (E1, E4): 200 clientes reales (edad, ingresos, spending score). Clásico de
  segmentación. Se descarga desde una URL pública.
- **Iris** (E2): 150 flores de 3 especies, ideal para un dendrograma claro (sklearn).
- **make_moons** (E3): dos lunas entrelazadas; el caso donde K-Means falla y DBSCAN brilla.
- **Wine** (E5): 178 vinos con 13 propiedades químicas y 3 cultivos reales (sklearn).

## Takeaways

1. **K-Means**: rápido para grupos compactos; hay que elegir K (codo + silhouette).
2. **Jerárquico**: dendrograma y corte interpretable, sin fijar K de antemano.
3. **DBSCAN**: densidad, ruido y formas irregulares; muy sensible a `eps`.
4. Las métricas orientan, pero el **profiling** explica y da valor de negocio.
5. El entregable final es una **decisión accionable**, no la tabla.

## Requisitos

- Python 3.8+
- `numpy`, `pandas`, `scikit-learn`, `scipy`, `matplotlib`

En Google Colab todas las dependencias vienen preinstaladas.
