# bank-marketing-dataops

## Descripcion del Proyecto

Este proyecto implementa un pipeline completo de DataOps para el dataset 
"Bank Marketing" del caso de estudio N°2. El objetivo es procesar y 
preparar los datos para un modelo de Machine Learning que prediga la 
probabilidad de que un cliente suscriba un deposito a plazo.

## Estructura del Proyecto

bank-marketing-dataops/
├── data/
│ ├── raw/ # Datos originales (sin modificar)
│ ├── processed/ # Datos procesados (limpios y transformados)
│ └── reports/ # Reportes de validacion
├── src/
│ ├── ingest.py # Etapa 1: Ingesta de datos
│ ├── clean_transform.py # Etapa 2: Limpieza y transformacion
│ ├── validate.py # Etapa 3: Validacion estructural y semantica
│ └── load.py # Etapa 4: Carga a base de datos
├── logs/ # Archivos de log de cada etapa
├── requirements.txt # Dependencias del proyecto
└── README.md # Este archivo


## Requisitos

- Python 3.8 o superior
- Dependencias listadas en requirements.txt

## Instalacion

```bash
pip install -r requirements.txt

los scripts deben ejecutarse en el siguiente orden;

1.  python src/ingest.py
2.  python src/clean_transform.py
3.  python src/validate.py
4.  python src/load.py

Descripcion de las Etapas

1. Ingesta (ingest.py)
Copia el archivo CSV desde data/raw/ a data/processed/ y registra
informacion basica del dataset.

2. Limpieza y Transformacion (clean_transform.py)
Reemplaza valores 'unknown' por la moda de cada columna

Convierte variables binarias (yes/no) a numericas (1/0)

Aplica One-Hot Encoding a variables categoricas

Escala variables numericas usando StandardScaler

3. Validacion (validate.py)
Verifica valores nulos en columnas criticas

Valida rangos de valores (edad, pdays, campaign)

Genera reporte de errores y advertencias

4. Carga a Base de Datos (load.py)
Conecta a base de datos SQLite

Crea tabla con estructura dinamica

Inserta datos con manejo de errores por fila

Genera reporte de carga

