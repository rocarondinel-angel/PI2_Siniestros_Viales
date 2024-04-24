# SINIESTROS VIALES EN LA CIUDAD AUTÓNOMA DE BUENOS AIRES

## INTRODUCCIÓN

Teniendo como objetivo la generación de información que permita la toma de decisiones de las autoridades locales; a fin de lograr la disminución en la cantidad de víctimas fatales de los siniestros viales, este proyecto nos pone en el papel de Analistas de Datos. Se nos ha proporcionado un conjunto de datos, el cual se encuentra en formato .xlsx, sobre los siniestros viales entre 2016 y 2021, el cual contine dos hojas: hechos y victimas.

Los mínimos entregables del proyecto: informe EDA, mencionar las tecnologías, herramientas, metodologías empleadas, análisis, conclusiones, KPIs y un dashboard interactivo.

## CONTEXTO

En Argentina, cada año mueren cerca de 4.000 personas en siniestros viales. Aunque muchas jurisdicciones han logrado disminuir la cantidad de accidentes de tránsito, esta sigue siendo la principal causa de muertes violentas en el país. Los informes del Sistema Nacional de Información Criminal (SNIC), del Ministerio de Seguridad de la Nación, revelan que entre 2018 y 2022 se registraron 19.630 muertes en siniestros viales en todo el país. Estas cifras equivalen a 11 personas por día que resultaron víctimas fatales por accidentes de tránsito.

## DESCRIPCIÓN DE LOS ARCHIVOS

+ homicidios.xlsx: archivo original, que contiene las dos hojas (hechos y víctimas)
+ Homicidios.csv: archivo generado a partir del dataframe unificado de los datos de las pestañas hechos y victimas, incluidos en el dataset entregado.
+ 1011poblacion.xlsx: archivo que contiene la poblacón de cada comuna desde el año 2015 hasta el año 2022.
+ EDA_ETL.ipynb: archivo en el que se realizo el análisis de datos, incluyendo el proceso de extracción, transformación y carga.
+ PIDA.pbix: archivo que contiene el dashboard interactivo y los KPIs
+ README.md: ncluye un reporte de análisis en base al dashboard y análisis de los KPI sugeridos
archivo en el que se da una presentación del proyecto, las tecnologías, herramientas, metodología empleada, análisis,
reporte de análisis con base en los dashboards, así como el análisis y la funcionalidad de los KPIs sugeridos, y conclusiones.

## TECNOLOGÍAS Y HERRAMIENTAS UTILIZADAS

Se utilizó Python, 
se creó el dashboard en PowerBI, 
se descargó un archivo excel de la pagina web: https://www.indec.gob.ar/indec/web/Nivel4-Tema-2-41-165 (POBLACION DE CABA),
y se importó lo siguiente:
+ import numpy as np -> manipular datos numéricos, cálculos matriciales y estadísticos
+ import pandas as pd -> carga, tratamiento y análisis de datos estructurados
+ from datetime import datetime, time
+ import matplotlib.pyplot as plt -> gráficos estáticos, animados e interactivos
+ import seaborn as sns-> gráficos más atractivos
+ import calendar -> visualización y manipulación de calendarios y fechas
+ import matplotlib.cm as cm -> modulo de matplotlib
+ import folium -> creación de mapas interactivos 
+ from folium.plugins import HeatMap -> visualizaciones de densidad
+ import warnings -> depuración y mejora del código


## METODOLOGIA
### Datos
Se trabajó con las dos secciones: HECHOS y VÍCTIMAS, del archivo homicidios.xlsx, relacionadas por el ID único, utilizando el Diccionario de datos Siniestros viales, el cual proporciona detalles sobre las variables utilizadas.

* **HECHOS**: contiene una variable que es el ID único del hecho y las variables temporales, las espaciales y las referidas a personas.

* **VICTIMAS**: contiene una fila por cada víctima y las características como su edad, sexo, modo de desplazamiento, etc. Se vincula a los HECHOS mediante el ID único del hecho.

### ETL
Proceso de ETL (Extracción, transformacion y carga). Se utilizó Pandas y Visual Studio Code. Eliminando nulos, duplicados, cambiando el tipo de los datos, eliminando columnas y uniendo las tablas en el dataframe df_homicidios2, el cual será cargado al archivo Homicidios.csv

### EDA
Luego de que los datos han sido tratados, se procede a realizar el Proceso de EDA (Análisis Exploratorio de los datos) para identificar las posibles relaciones o patrones que sean relevantes para la toma de decisiones. Realizando medidas de tendencia central y de dispersión, definiendo algunos otros tipos de datos, utilizando visualizaciones apropiadas para el análisis univariado, bivariado, verificando las posibles relaciones que pudiesen existir entre las variables, eligiendo que hacer ante la presencia de outliers (que no tienen que ser errores necesariamente).

###  DASHBOARD
Una vez realizado el Análisis Exploratorio, se utiliza el archivo Homicidios.csv para trabajar en la herramienta PowerBi, donde se creará el archivo PIDA.pbix (el Dashboard, tablero de control). Alineando los elementos, eligiendo técnicas de diseño adecuadas, eligiendo las gráficas correspondientes a cada tipo de variable, mostrando una visión general de los datos, etc.

### KPIs (Indicadores Clave de Rendimiento)
Con el fin de definir los KPIs (Indicadores Clave de Rendimiento) en el dashboard, se utiliza el archivo excel de la pagina web: https://www.indec.gob.ar/indec/web/Nivel4-Tema-2-41-165 (POBLACION DE CABA). Utilizando las visualizaciones de medidor para cada uno de ellos, utilizando las tarjetas para visualizar su valor

## ANÁLISIS

El análisis que se llevó a cabo nos indica que existen ciertas relaciones entre las variables temporales, las espaciales y las relacionadas con las personas.  Acerca del análisis, se podría dividir en 3 grupos: Análisis temporal, Análisis espacial y Análisis relacionado con las personas.

### Análisis Temporal:
Se manifiesta un patrón de aumento en la cantidad de siniestros viales hasta antes del inicio de la pandemia, tendencia que volvió a manifestarse para el año 2021. Los meses que tienen una mayor cantidad de víctimas fatales son diciembre, noviembre y agosto, siendo la mayor cantidad de victimas fatales en diciembre. Se observa una disminución de la cantidad de siniestros viales para el fin de mes, los días que tiene una mayor cantidad de siniestros viales son alrededor de los días 15 al 20. De sábado a lunes hay la mayor cantidad de siniestros viales, siendo la menor cantidad de estos los días jueves. Hay una franja horaria que resulta contener una gran cantidad de siniestros viales, y esta es, entre las 5 horas y las 9 horas, con una tendencia ascendente hasta las 7 horas.

### Análisis Espacial:
Los siniestros se producen mayormente en los cruces, lo cual es un patrón que se repite. Los accidentes en las avenidas también son comunes en todas las comunas de la Ciudad Autónoma de Buenos Aires, con la mayoría de las víctimas perdiendo la vida en estos lugares

### Análisis Relacionado con las Personas
La mayor cantidad de víctimas tienen el rol de conductor, seguido por el de peatón. Los acusados son en su mayoría conductores de auto, pasajeros y cargas. La distribución de las edades de las víctimas fatales esta sesgada positivamente y la mayor cantidad de siniestros viales han ocurrido a víctimas entre los 20 años y un poco mas de 40 años. Cerca de la mitad de las víctimas son conductores, principalmente de motocicletas, y la responsabilidad del accidente recae principalmente en vehículos como automóviles, colectivos y camiones.

Este análisis proporciona una perspectiva de los patrones temporales, factores espaciales y el perfil de las personas, relacionados con los siniestros, lo que puede ser fundamental para generar información que permita a las autoridades locales tomar medidas correspondientes.


## KPIs: INDICADORES CLAVE DE RENDIMIENTO

En función del análisis previo, se establecieron tres KPIs para medir y evaluar el progreso en relación con el objetivo estratégico establecido. 

KPIs propuestos:

+ **1) Reducir en un 10% la tasa de homicidios en siniestros viales de los últimos seis meses, en CABA, en comparación con la tasa de homicidios en siniestros viales del semestre anterior**

Se ha definido la tasa de homicidios en siniestros viales como el número de víctimas fatales en accidentes de tránsito por cada 100,000 habitantes en un área geográfica durante un período de tiempo específico. Su fórmula es: (Número de homicidios en siniestros viales / Población total) * 100,000


Población Total = 3038836, tomada del archivo de la Fuente:INDEC

La tasa de hommicidios que se requiere, se obtiene con la siguiente fórmula DAX:

k1_Tasa Homicidios_Semestre1 = 
DIVIDE(
    CALCULATE([TOTAL SINIESTROS], 'Homicidios'[Sem]=1 && Homicidios[AÑO]=2021),
    3078836
) * 100000

-> La variación porcentual de la tasa de homicidios ha sido una disminución del 24%, y comparado con la reducción del 10 % que se planteó; se puede decir que se alcanzó el KPI.

- **2) Reducir en un 7% la cantidad de accidentes mortales de motociclistas en el último año, en CABA, respecto al año anterior**

Se define la cantidad de accidentes mortales de motociclistas en siniestros viales como el número absoluto de accidentes fatales en los que estuvieron involucradas víctimas que viajaban en moto en un determinado periodo temporal. Su fórmula para medir la evolución de los accidentes mortales con víctimas en moto es: (Número de accidentes mortales con víctimas en moto en el año anterior - Número de accidentes mortales con víctimas en moto en el año actual) / (Número de accidentes mortales con víctimas en moto en el año anterior) * 100

La cantidad de accidentes que se requiere, se obtiene con la siguiente fórmula DAX:

k2_Registros_MOTO_2021 = 
COUNTROWS(
    FILTER(
        'Homicidios',
        'Homicidios'[VICTIMA] = "MOTO" &&
        Homicidios[AÑO] = 2021 ||
        'Homicidios'[ACUSADO] = "MOTO" &&
        Homicidios[AÑO] = 2021
    )
)

-> La variación porcentual de la cantidad de accidentes mortales de motociclistas en el último año respecto al año anterior, ha sido un aumento del 30%, y comparado con la reducción del 7 % que se planteó; se puede decir que no se logró el KPI.


- **3) Reducir en un 5% la cantidad de accidentes mortales en los que el acusado era un conductor de auto; en el último año, en CABA, respecto al año anterior**

La cantidad de accidentes que se requiere, se obtiene con la siguiente fórmula DAX:

k3 Registros_2021_ACUSADOauto = 
COUNTROWS(
    FILTER(
        'Homicidios',
        'Homicidios'[ACUSADO] = "AUTO" &&
        Homicidios[AÑO] = 2021 
    )
)

-> La variación porcentual de la cantidad de accidentes mortales en los que el acusado era un conductor de auto, en el último año, respecto al año anterior, ha sido un aumento del 15%, y comparado con la reducción del 5 % que se planteo; se debe decir que no se satisfizo el KPI.


## CONCLUSIONES

Se concluye a partir del análisis de los datos:

Que hay una franja horaria que resulta contener una gran cantidad de siniestros viales, y esta es, entre las 5 horas y las 9 horas, con una tendencia ascendente hasta las 7 horas. Entre las 15 horas y las 18 horas, hay también una tendencia a aumentar la cantidad de siniestros viales.

Hay una tendencia al aumento en la cantidad de siniestros, en el mes de diciembre; y también, se vió una disminucion en la cantidad de estos durante la pandemia.

Las víctimas son en su mayoría de sexo masculino, y el rol que desempeñaban era el de conductores de motocicletas o peatones. La mayor cantidad de siniestros viales han ocurrido con víctimas entre los 20 años y un poco más de 40 años. También, que la menor cantidad de víctimas, en edad adulta, se ubica alrededor de los 65 años.

Los acusados son en su mayoría conductores de auto, pasajeros y cargas. En cuanto al lugar donde se producen los siniestros, las avenidas han sido los espacios de mayor cantidad de ocurrencia de estos. 

Por lo tanto, es requerida una mejora en el control de la seguridad vial de las avenidas; además, se sugiere la realización de campañas dirigidas a conductores de autos y motocicletas; y también, a pasajeros. En especial a quienes se encuentren en el rango etario de 20 a 40 años de sexo masculino. Se recomienda que se siga promoviendo la obtención de datos de siniestros viales para mejorar los estudios de estos.