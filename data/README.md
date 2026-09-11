# Datos

## Procedencia

Los datos utilizados en este Trabajo de Fin de Grado fueron descargados originalmente del repositorio **tennis_atp** mantenido por Jeff Sackmann, disponible en el momento en que se obtuvo la base de datos.

Actualmente, el repositorio oficial `JeffSackmann/tennis_atp` ya no se encuentra disponible. Para mantener la trazabilidad del trabajo y permitir la obtención de los archivos necesarios, se utiliza como referencia la siguiente copia archivística de terceros:

[Copia archivística de los datos ATP de Jeff Sackmann](https://github.com/Aneeshers/tennis-sackmann-archive/tree/main/atp)

La copia archivística atribuye los datos originales a **Jeff Sackmann / Tennis Abstract** y conserva también documentación de procedencia del repositorio original.

## Licencia

La copia archivística indica que los datos se redistribuyen bajo la misma licencia atribuida al conjunto original:

**Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0).**

Este repositorio del TFG no redistribuye los archivos de datos originales.

## Archivos utilizados

El pipeline emplea los archivos anuales ATP correspondientes a:

- 2008–2019;
- 2021–2024.

El año 2020 no forma parte del conjunto utilizado en el estudio.

Los años 2008 y 2021 se utilizan exclusivamente como periodos de historial previo (*buffer*). El desarrollo y la validación interna se realizan sobre 2009–2019 y 2022–2023, mientras que 2024 se reserva para la evaluación temporal externa.

## Ubicación esperada

El Notebook 01 espera encontrar los archivos originales en una carpeta con la siguiente estructura relativa:

```text
./tennis_atp-master/
```

Por tanto, para reproducir el pipeline pueden descargarse los CSV anuales necesarios desde la copia archivística y situarse en una carpeta local denominada `tennis_atp-master` junto al entorno de ejecución esperado por el Notebook 01.

## Reproducción

1. Acceda a la copia archivística indicada anteriormente.
2. Obtenga los archivos anuales ATP necesarios.
3. Sitúelos en la carpeta `tennis_atp-master` esperada por el Notebook 01.
4. Ejecute los notebooks siguiendo el orden `01` → `09` indicado en el `README.md` principal.

Los archivos intermedios se generan automáticamente durante la ejecución de los notebooks y tampoco se distribuyen como parte principal del repositorio.
