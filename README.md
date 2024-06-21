# README

## Machine Learning No Supervisado - Ejercicios y Datos

Bienvenido al repositorio de ejercicios y datos para la clase de Machine Learning No Supervisado. Este repositorio contiene materiales diseñados para enseñar y practicar técnicas de aprendizaje no supervisado. A continuación, se detallan las instrucciones para configurar el entorno, una descripción de los contenidos del repositorio y guías para la ejecución de los ejercicios.

## Contenido

Este repositorio incluye:

- **Datasets:** Conjuntos de datos utilizados en los ejercicios.
- **Notebooks:** Jupyter Notebooks con ejercicios y ejemplos prácticos.
- **Scripts:** Scripts en Python para preprocesamiento y análisis de datos.
- **Documentación:** Material de apoyo y recursos adicionales.

## Estructura del Repositorio

```
machine-learning-no-supervisado/
│
├── data/
│   ├── dataset1.csv
│   ├── dataset2.csv
│   └── ...
│
├── notebooks/
│   ├── 01-introduccion.ipynb
│   ├── 02-clustering.ipynb
│   ├── 03-pca.ipynb
│   ├── 04-deteccion-anomalias.ipynb
│   └── ...
│
├── scripts/
│   ├── preprocessing.py
│   ├── clustering.py
│   ├── pca.py
│   ├── anomaly_detection.py
│   └── ...
│
├── docs/
│   ├── syllabus.pdf
│   ├── referencias.md
│   └── ...
│
├── .gitignore
├── LICENSE
└── README.md
```

## Requisitos

Para ejecutar los ejercicios y ejemplos, asegúrate de tener instalado lo siguiente:

- **Python 3.7+**
- **Jupyter Notebook**
- **Librerías de Python:**
  - numpy
  - pandas
  - scikit-learn
  - matplotlib
  - seaborn

Puedes instalar las librerías necesarias utilizando el archivo `requirements.txt` incluido en el repositorio:

```bash
pip install -r requirements.txt
```

## Configuración del Entorno

1. **Clonar el Repositorio:**

```bash
git clone https://github.com/tu-usuario/machine-learning-no-supervisado.git
cd machine-learning-no-supervisado
```

2. **Crear un Entorno Virtual:**

```bash
python -m venv venv
source venv/bin/activate  # En Windows usa `venv\Scripts\activate`
```

3. **Instalar Dependencias:**

```bash
pip install -r requirements.txt
```

## Ejecución de Ejercicios

### 1. Notebooks

Para trabajar con los notebooks, inicia Jupyter Notebook:

```bash
jupyter notebook
```

Navega a la carpeta `notebooks` y selecciona el notebook que deseas ejecutar.

### 2. Scripts

Los scripts en la carpeta `scripts` pueden ejecutarse directamente desde la línea de comandos. Por ejemplo:

```bash
python scripts/clustering.py
```

## Contribuciones

Si deseas contribuir a este repositorio, por favor sigue los siguientes pasos:

1. Haz un fork del repositorio.
2. Crea una nueva rama (`git checkout -b feature/nueva-funcionalidad`).
3. Realiza tus cambios y haz commit (`git commit -m 'Añadir nueva funcionalidad'`).
4. Sube tus cambios (`git push origin feature/nueva-funcionalidad`).
5. Abre un Pull Request.

## Licencia

Este proyecto está bajo la licencia MIT. Para más detalles, consulta el archivo [LICENSE](LICENSE).

## Contacto

Para cualquier pregunta o sugerencia, por favor contacta a [tu-nombre](mailto:tu-email@ejemplo.com).

¡Gracias por tu interés en aprender Machine Learning No Supervisado con nosotros!
