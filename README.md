# Influencia de la carga competitiva acumulada en el rendimiento de tenistas profesionales

**Autor:** Diego García Alba  
**Titulación:** Grado en Matemática Aplicada  
**Universidad:** Universidad Loyola Andalucía  
**Curso académico:** 2026–2027  

## Descripción

Este repositorio contiene el código desarrollado para el Trabajo de Fin de Grado **“Influencia de la carga competitiva acumulada en el rendimiento de tenistas profesionales”**.

El objetivo del estudio es analizar si la carga competitiva acumulada externa observable aporta información adicional para predecir el rendimiento de tenistas profesionales. El análisis utiliza datos históricos del circuito ATP en estructura jugador–partido y toma como variable objetivo el porcentaje de juegos ganados.

El pipeline incluye la preparación y validación de los datos, la construcción de variables de carga competitiva, el análisis y selección de predictores, el desarrollo de modelos mediante validación temporal y la evaluación temporal externa reservada para la temporada 2024.

## Fuente de datos

Los datos utilizados fueron descargados originalmente del repositorio **tennis_atp** mantenido por Jeff Sackmann, disponible en el momento de obtención de los datos. Actualmente dicho repositorio oficial ya no se encuentra disponible.

Para mantener la trazabilidad y facilitar la reproducción, se referencia una copia archivística de terceros que conserva los datos ATP de Jeff Sackmann:

`https://github.com/Aneeshers/tennis-sackmann-archive/tree/main/atp`

Los archivos de datos originales e intermedios no se incluyen en este repositorio. La procedencia, los periodos utilizados y la ubicación necesaria para reproducir el pipeline se documentan en `data/README.md`.

## Estructura del repositorio

```text
TFG-tenis-carga-competitiva/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── 01_preparacion_datos_atp.ipynb
├── 02_transformacion_y_preparacion_predictores_tradicionales.ipynb
├── 03_validacion_calidad_datos.ipynb
├── 04_construccion_cargas_acumuladas.ipynb
├── 05_enriquecimiento_cargas_competitivas.ipynb
├── 06_analisis_y_seleccion_variables.ipynb
├── 07_desarrollo_modelos_validacion_temporal.ipynb
├── 08_auditoria_seleccion_temporal.ipynb
├── 09_evaluacion_temporal_externa_2024.ipynb
│
└── data/
    └── README.md
```

## Orden de ejecución

Los notebooks están numerados según el orden recomendado de ejecución:

1. `01_preparacion_datos_atp.ipynb` — Carga y unifica los archivos históricos ATP utilizados en el estudio, homogeneiza su estructura y define los bloques temporales necesarios para las etapas posteriores.
2. `02_transformacion_y_preparacion_predictores_tradicionales.ipynb` — Depura los partidos, transforma los datos a estructura jugador–partido, construye la variable objetivo y prepara y selecciona los predictores tradicionales. También genera el snapshot utilizado posteriormente en la auditoría temporal de la selección.
3. `03_validacion_calidad_datos.ipynb` — Realiza las comprobaciones de integridad, reciprocidad y coherencia temporal del conjunto jugador–partido y aplica la depuración final necesaria antes de construir las cargas competitivas.
4. `04_construccion_cargas_acumuladas.ipynb` — Construye las variables de carga competitiva acumulada en ventanas de 365 y 180 días y durante la temporada, utilizando únicamente información anterior a cada participación.
5. `05_enriquecimiento_cargas_competitivas.ipynb` — Incorpora información de la participación competitiva anterior, separación temporal entre participaciones y medidas de densidad competitiva reciente.
6. `06_analisis_y_seleccion_variables.ipynb` — Analiza asociación, redundancia, estabilidad y colinealidad de los predictores, define las especificaciones Base, Principal y Ampliada y genera las muestras utilizadas en modelización.
7. `07_desarrollo_modelos_validacion_temporal.ipynb` — Compara algoritmos, optimiza hiperparámetros mediante cinco particiones temporales, estudia la aportación de las variables de carga y congela las configuraciones que se utilizarán en la evaluación externa.
8. `08_auditoria_seleccion_temporal.ipynb` — Audita retrospectivamente la estabilidad temporal de las principales decisiones de selección de variables utilizando exclusivamente los periodos de desarrollo.
9. `09_evaluacion_temporal_externa_2024.ipynb` — Ajusta las configuraciones previamente congeladas sobre el conjunto de desarrollo y realiza la evaluación temporal externa de 2024, incluyendo bootstrap, importancia por permutación y comprobaciones complementarias.

## Reproducción básica

1. Obtenga los datos ATP necesarios desde la copia archivística indicada en `data/README.md`.
2. Sitúe los archivos en la estructura esperada por el Notebook 01.
3. Instale las dependencias especificadas en `requirements.txt`.
4. Ejecute los notebooks secuencialmente del `01` al `09`.
5. Para una comprobación reproducible de cada notebook, reinicie el kernel y ejecute todas sus celdas en orden.

Los notebooks generan los archivos intermedios necesarios para las etapas posteriores del pipeline. La temporada 2024 se mantiene separada de las fases de selección y desarrollo y se utiliza únicamente en la evaluación temporal externa.

## Dependencias

La ejecución final del proyecto se realizó con **Python 3.12.5**. Las dependencias directas y sus versiones exactas se recogen en `requirements.txt`.

## Datos y archivos generados

Los archivos intermedios generados durante la ejecución no forman parte de la presentación principal del repositorio. Se producen automáticamente a lo largo del pipeline.

La documentación específica sobre los datos originales y su procedencia se recoge en `data/README.md`.

## Licencias y recursos externos

Las dependencias utilizadas mantienen sus respectivas licencias.

La copia archivística utilizada como referencia atribuye los datos a Jeff Sackmann / Tennis Abstract y los distribuye bajo **Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)**. Este repositorio del TFG no redistribuye los datos originales.

## Memoria del TFG

La metodología, los resultados y su interpretación se desarrollan en la memoria del Trabajo de Fin de Grado. Este repositorio proporciona el código y la documentación necesarios para revisar el pipeline computacional asociado.
