# Detección, conteo y segmentación de ejemplares arbóreos individuales (ITD) en entornos reales mediante imágenes de UAV y Deep Learning

**Maestría en Ciencia de Datos — Universidad de Montevideo**

**Autoras:** Verónica Cuadro y Sabrina Sellanes  
**Tutor:** César Reyes  
**Año:** 2026

## Descripción del proyecto

Este repositorio contiene los notebooks desarrollados en el marco del trabajo final de la Maestría en Ciencia de Datos de la Universidad de Montevideo.

La investigación aborda la detección, segmentación y conteo automatizado de árboles de *Eucalyptus grandis* en plantaciones forestales comerciales de Uruguay, mediante modelos de visión por computadora y aprendizaje profundo (*Deep Learning*) aplicados a imágenes aéreas obtenidas con vehículos aéreos no tripulados (UAV).

El propósito es evaluar el desempeño de diferentes arquitecturas para la identificación individual de árboles y analizar su potencial como herramientas de apoyo a los procesos de inventario forestal.

## Objetivo

Evaluar y comparar diferentes modelos de visión por computadora para la detección y el conteo individual de árboles de *Eucalyptus grandis*, utilizando imágenes aéreas de alta resolución y censos terrestres georreferenciados como referencia para validar los resultados.

## Áreas de estudio

La investigación comprende tres establecimientos forestales de Uruguay:

| Predio | Superficie | Año de plantación |
|---|---:|---:|
| Cerro Alegre | 19,01 ha | 1997 |
| Las Taperas | 58,89 ha | 1998 |
| Rocha | 37,41 ha | 2000 |

Cerro Alegre se utilizó como predio principal para el desarrollo y la experimentación, mientras que Las Taperas y Rocha permitieron evaluar el comportamiento de los modelos seleccionados en otros entornos.

## Modelos evaluados

Se exploraron diferentes arquitecturas de detección y segmentación de objetos:

- **DeepForest:** detección de copas arbóreas mediante cajas delimitadoras.
- **TreeFormer/TreePoint:** identificación y conteo de árboles mediante predicciones puntuales.
- **Mask R-CNN:** detección y segmentación de instancias individuales.
- **YOLO11-seg:** segmentación de instancias mediante redes de la familia YOLO.
- **SAM 3:** segmentación de objetos mediante indicaciones conceptuales.

Los modelos **DeepForest** y **Mask R-CNN** fueron seleccionados para las evaluaciones externas en Las Taperas y Rocha, representando respectivamente los enfoques de detección y segmentación de instancias.

## Metodología

El trabajo se desarrolló mediante las siguientes etapas:

1. Recopilación y análisis exploratorio de imágenes UAV y censos forestales.
2. Preparación de ortomosaicos y procesamiento de información geoespacial.
3. Generación de anotaciones de copas arbóreas mediante QGIS.
4. Implementación y evaluación de modelos de Deep Learning.
5. Comparación de predicciones con censos terrestres georreferenciados.
6. Análisis del desempeño de los modelos en diferentes plantaciones forestales.

La evaluación consideró métricas de precisión, recall, F1-score y error porcentual de conteo, además de los verdaderos positivos (TP), falsos positivos (FP) y falsos negativos (FN).

## Principales resultados

Los experimentos permitieron observar diferencias en el desempeño de los modelos según las condiciones de cada establecimiento.

DeepForest obtuvo valores de F1 censal de 0,879 en Cerro Alegre, 0,877 en Las Taperas y 0,836 en Rocha.

Mask R-CNN registró valores de F1 censal de 0,733, 0,658 y 0,758, respectivamente.

Uno de los principales hallazgos fue que una estimación agregada cercana al censo no garantiza una correcta identificación individual de los árboles, debido a la posible compensación entre falsas detecciones y omisiones.

Asimismo, se identificaron desafíos relacionados con la superposición de copas, las diferencias radiométricas entre imágenes y la capacidad de generalización de los modelos.

## Herramientas utilizadas

- **Python:** procesamiento de datos e implementación de modelos.
- **Google Colab:** desarrollo y ejecución de notebooks.
- **QGIS:** procesamiento geoespacial y generación de anotaciones.
- **Google Drive:** almacenamiento y organización de los datos utilizados durante la investigación.
- **GitHub:** publicación y control de versiones del código.

## Organización del repositorio

```text
MCD-VeronicaCuadro-SabrinaSellanes/
│
├── Experimentación/
│   └── Notebooks de experimentación para Cerro Alegre.
│
├── Evaluación otros predios/
│   └── Notebooks de evaluación de DeepForest y Mask R-CNN para Las taperas y Rocha.
│
└── README.md
```

## Disponibilidad de los datos

Los datos originales utilizados en esta investigación son propiedad de **Compañía Forestal Uruguaya S.A. (COFUSA)** e incluyen imágenes aéreas UAV, información geoespacial y censos forestales.

Estos datos fueron utilizados exclusivamente con fines académicos y de investigación. Su publicación o distribución requiere la correspondiente autorización de su titular.

