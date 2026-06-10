# Curso de Digitalizacion en Acuicultura

Material de apoyo para un curso practico sobre analitica de datos aplicada a acuicultura. Este repositorio contiene presentaciones, datos y notebooks de Jupyter pensados para ejecutarse paso a paso en clase o de forma autonoma.

## Contenido

- `bloque3_preprocesamiento.ipynb`: limpieza y preprocesamiento de una serie temporal de oxigeno disuelto.
- `bloque4_analitica_bbdd.ipynb`: carga de datos reales en SQLite, consultas SQL y visualizacion.
- `bloque6_predictivo_chronos.ipynb`: comparativa entre un modelo predictivo clasico y un modelo fundacional Chronos.
- `PVA_AGUA_SP_15_19.xlsx`: dataset base usado en los notebooks con datos reales.
- `calidad_agua.db`: base de datos SQLite generada para el bloque de analitica.
- `bloque*.pptx`: presentaciones de apoyo del curso.

## Que necesitas para ejecutar los notebooks

Para trabajar en local se recomienda:

- Python 3.10, 3.11 o 3.12
- `pip`
- Jupyter Notebook o JupyterLab
- Conexion a internet la primera vez que se use Chronos, porque descarga el modelo

Librerias utilizadas en el material:

- `numpy`
- `pandas`
- `matplotlib`
- `openpyxl`
- `scikit-learn`
- `torch`
- `chronos-forecasting`

`sqlite3` no hace falta instalarlo porque viene incluido con Python.

## Instalacion recomendada en local

### 1. Crear un entorno virtual

En Windows PowerShell:

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

En macOS o Linux:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 2. Instalar dependencias

```bash
pip install jupyter numpy pandas matplotlib openpyxl scikit-learn torch chronos-forecasting
```

Si `torch` diera problemas en algun equipo, se puede instalar siguiendo la guia oficial de PyTorch y despues repetir la instalacion del resto de paquetes.

### 3. Abrir Jupyter

```bash
jupyter notebook
```

o bien:

```bash
jupyter lab
```

Despues abre el notebook que quieras ejecutar.

## Ejecucion en Google Colab

Los notebooks tambien se pueden usar en Google Colab. En ese caso:

- Sube los ficheros del repositorio, o monta Google Drive
- Ejecuta las celdas de instalacion cuando aparezcan
- Asegurate de que el Excel `PVA_AGUA_SP_15_19.xlsx` este disponible en la misma carpeta del notebook

En `bloque6_predictivo_chronos.ipynb`, Chronos puede tardar varios minutos la primera vez porque descarga el modelo preentrenado.

## Orden recomendado para el curso

1. `bloque3_preprocesamiento.ipynb`
2. `bloque4_analitica_bbdd.ipynb`
3. `bloque6_predictivo_chronos.ipynb`

Ese orden sigue una progresion natural:

- primero limpieza y comprension de datos
- despues almacenamiento y consulta
- por ultimo prediccion y comparativa de modelos

## Notas por notebook

### `bloque3_preprocesamiento.ipynb`

- Usa `numpy`, `pandas` y `matplotlib`
- No depende del fichero Excel del repositorio
- Es una buena puerta de entrada para alumnado sin experiencia previa

### `bloque4_analitica_bbdd.ipynb`

- Lee `PVA_AGUA_SP_15_19.xlsx`
- Crea o actualiza `calidad_agua.db`
- Usa SQLite con `sqlite3`, que ya viene con Python

### `bloque6_predictivo_chronos.ipynb`

- Usa `numpy`, `pandas`, `matplotlib`, `scikit-learn`, `torch` y `chronos-forecasting`
- Compara un modelo clasico con Chronos
- Requiere internet la primera vez para descargar el modelo `amazon/chronos-t5-small`
- Si Chronos no puede cargarse, el notebook deja mensajes para ayudar a diagnosticar el problema

## Problemas frecuentes

### Error al leer el Excel

Instala `openpyxl`:

```bash
pip install openpyxl
```

### Jupyter no reconoce el entorno virtual

Instala el kernel del entorno:

```bash
pip install ipykernel
python -m ipykernel install --user --name curso-acuicultura
```

Luego selecciona ese kernel desde Jupyter.

### Chronos falla o no descarga el modelo

Comprueba:

- que `chronos-forecasting` este instalado
- que haya conexion a internet
- que `torch` este correctamente instalado
- que se haya reiniciado el kernel tras una instalacion incompleta

### El notebook da resultados distintos a los de clase

Puede ocurrir por:

- diferencias de version en las librerias
- ejecucion de celdas fuera de orden
- reinicio parcial del kernel

Si pasa, reinicia el kernel y ejecuta todas las celdas desde el principio.

## Recomendaciones para el alumnado

- Ejecuta los notebooks en orden
- Lee primero el texto explicativo de cada bloque
- Si modificas una celda, guarda una copia antes de seguir
- Si una libreria se instala durante el notebook, a veces conviene reiniciar el kernel y volver a ejecutar

## Licencia y uso

Este material esta pensado como recurso docente. Si vas a reutilizarlo en otro curso o proyecto, conviene revisar antes el origen y las condiciones de uso de los datos y de los modelos externos utilizados.
