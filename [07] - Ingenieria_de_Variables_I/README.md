# [07] - Ingeniería de Variables I

Notebooks prácticos de la sesión **Ingeniería de Variables I** del Máster FP en Data Science
(The Valley). El hilo conductor es un dataset **sintético y reproducible de fraude con tarjeta**
que se genera dentro de cada notebook (no necesitas descargar nada: son autocontenidos para Colab).

> *Las mejores variables ganan a los mejores modelos.*

## Notebooks

| Notebook | Ejercicio (presentación) | Conceptos |
|---|---|---|
| [`E1_Tus_Primeras_Features.ipynb`](%5B01%5D%20-%20Notebooks/E1_Tus_Primeras_Features.ipynb) | **E1 · Tus primeras features** | Tipos de variables, pseudo-numéricas, escalado (Standard/MinMax/Robust), outliers (`log`, winsorizing, Yeo-Johnson), `log_monto`, `monto_ratio`, extracción de fecha, encoding cíclico, binning |
| [`E2_Codifica_como_un_Pro.ipynb`](%5B01%5D%20-%20Notebooks/E2_Codifica_como_un_Pro.ipynb) | **E2 · Codifica como un pro** | Error del label encoding, One-Hot, encoding ordinal, alta cardinalidad, target/mean encoding ingenuo vs **out-of-fold + smoothing**, hashing trick |
| [`E3_Pipeline_Completo.ipynb`](%5B01%5D%20-%20Notebooks/E3_Pipeline_Completo.ipynb) | **E3 · Pipeline completo** | Imputar antes/después del split, `Pipeline` + `ColumnTransformer` (numéricas + categóricas), `TargetEncoder` sin fugas, evaluación en test, cross-validation, scoring en datos nuevos |
| [`E4_Caza_del_Leakage.ipynb`](%5B01%5D%20-%20Notebooks/E4_Caza_del_Leakage.ipynb) | **E4 · Caza del leakage** *(bonus)* | Tres fugas frecuentes (fit antes del split, feature del futuro, fuga temporal) con versión rota y arreglada; los 6 tropiezos clásicos |
| [`E5_Mean_Encoding_Bien_vs_Mal.ipynb`](%5B01%5D%20-%20Notebooks/E5_Mean_Encoding_Bien_vs_Mal.ipynb) | **E5 · Mean encoding: bien vs mal** *(bonus)* | Mean encoding sin smoothing (overfit) vs smoothing manual vs `TargetEncoder` con turnos; comparativa train vs test (AUC) |

Cada notebook incluye un botón **"Open In Colab"** al principio para abrirlo directamente.

## Estructura

```
[07] - Ingenieria_de_Variables_I/
├── README.md
└── [01] - Notebooks/
    ├── E1_Tus_Primeras_Features.ipynb
    ├── E2_Codifica_como_un_Pro.ipynb
    ├── E3_Pipeline_Completo.ipynb
    ├── E4_Caza_del_Leakage.ipynb
    └── E5_Mean_Encoding_Bien_vs_Mal.ipynb
```

## El dataset (fraude con tarjeta)

Se genera con la función `generar_datos_fraude(n, semilla)` incluida en los notebooks. La
probabilidad de fraude depende de variables reales (monto, hora, canal, país y comercio), de
modo que la ingeniería de variables que se practica **tiene señal de verdad** y su efecto se
ve reflejado en las métricas.

| Variable | Tipo | Notas |
|---|---|---|
| `monto` | numérica | Distribución sesgada con outliers (para `log`/winsorizing) |
| `edad`, `canal` | numérica / categórica | Con valores faltantes (para imputación) |
| `pais`, `tipo_tarjeta`, `canal` | categóricas | Baja cardinalidad (One-Hot) |
| `comercio` | categórica | Alta cardinalidad, frecuencias desiguales (target encoding) |
| `codigo_postal` | pseudo-numérica | Parece número, pero no tiene magnitud |
| `fecha` | fecha/hora | Para extraer mes, hora, día de la semana y encoding cíclico |
| `es_fraude` | objetivo (0/1) | ~10 % de fraude |

## Requisitos

- Python 3.8+
- `numpy`, `pandas`, `scikit-learn` (>= 1.3 para `TargetEncoder`), `matplotlib`, `seaborn`

En Google Colab todas las dependencias vienen preinstaladas.
