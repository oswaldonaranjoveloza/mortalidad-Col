# Dashboard de Mortalidad en Colombia

Aplicación interactiva desarrollada en Dash + Plotly Graph Objects.


Introducción del proyecto:

El proyecto “Análisis de Mortalidad en Colombia (2019)” es una aplicación web 
interactiva desarrollada en Python 3.13 con Dash, cuyo propósito es visualizar
y analizar de manera dinámica los datos de mortalidad registrados en Colombia 
durante el año 2019.

La aplicación permite explorar tendencias, causas y distribuciones geográficas
de las muertes mediante gráficos y mapas interactivos, facilitando la comprensión 
de patrones demográficos, epidemiológicos y territoriales.


Objetivo:

El objetivo es analizar la mortalidad en Colombia durante el año 2019, identificando:
• Los departamentos con mayor y menor número de fallecimientos.
• Las principales causas de muerte.
• La distribución por sexo y grupo de edad.
• Las tendencias mensuales y los municipios con índices más altos de violencia.

La aplicación busca proveer una herramienta de análisis visual que apoye la toma de 
decisiones en salud pública y la investigación demográfica.


Estructura del proyecto:

Proyecto/
│
├── src/
│   └── app.py                     			# Archivo principal del dashboard Dash
│
├── data/
│   ├── Mortalidad.xlsx            			# Base de datos de muertes no fetales (2019)
│   ├── Divipola.xlsx              			# Tabla de equivalencias de códigos DANE
│   ├── CIE10.xlsx                 			# Códigos y descripciones de causas de muerte
│   └── geoBoundaries-COL-ADM1_simplified.geojson   	# Mapa geográfico de departamentos
│
└── requirements.txt               			# Lista de librerías necesarias

• app.py: Contiene toda la lógica del proyecto (carga, limpieza de datos, generación de gráficos y despliegue Dash).
• data/: Almacena los archivos base (.xlsx y .geojson) utilizados en el análisis.
• requirements.txt: Se usa para instalar las dependencias necesarias del proyecto.


Requisitos: 

Para ejecutar la aplicación, se requieren las siguientes librerías y versiones (compatibles con Python 3.13):

dash==2.17.0
pandas==2.2.2
plotly==5.24.1
geopandas==0.14.4
pyproj==3.6.1
shapely==2.0.4
fiona==1.9.5
gunicorn==23.0.0       # usado en Render

Estas dependencias pueden instalarse fácilmente con:
pip install -r requirements.txt


Despliegue 

El proyecto fue desplegado en la plataforma Render.com siguiendo estos pasos:

1.	Crear un repositorio en GitHub con los archivos del proyecto (src/, data/, requirements.txt).
2.	En Render:
3.	Crear un nuevo servicio Web Service.
4.	Conectar el repositorio de GitHub.
5.	Configurar:
6.	Start command:
7.	gunicorn src.app:server
8.	Runtime: Python 3.13
9.	Build command:
10.	pip install -r requirements.txt
11.	Render instala automáticamente las dependencias y lanza la aplicación en una URL pública, por ejemplo:

https://colombia-mortalidad-2019.onrender.com/


Software:

• Python 3.13 – lenguaje base del proyecto.
• Dash (Plotly) – framework web para dashboards interactivos.
• Pandas / GeoPandas – procesamiento de datos y análisis espacial.
• Plotly Express / Graph Objects – generación de visualizaciones interactivas.
• Render – despliegue del servidor en la nube.
• Visual Studio Code / PyChar / TeXStudio – entornos de desarrollo y documentación.


Instalación:

Para ejecutar la aplicación en tu equipo:

1.	Clonar el repositorio:
2.	git clone https://github.com/tu-usuario/mortalidad-Col.git
3.	cd mortalidad-Col
4.	Crear entorno virtual (opcional pero recomendado):
5.	python -m venv venv
6.	venv\Scripts\activate
7.	Instalar dependencias:
8.	pip install -r requirements.txt
9.	Ejecutar la aplicación:
10.	python src/app.py
11.	Abrir en el navegador:   http://127.0.0.1:8050/


Visualizaciones con explicaciones de los resultados: 

1. Mapa de mortalidad por departamento
Muestra la distribución total de muertes en Colombia en 2019, usando un mapa coroplético.
Hallazgo: Los departamentos con mayor mortalidad son Antioquia, Valle del Cauca y Bogotá D.C., lo que refleja su densidad poblacional.

2. Gráfico de líneas – Muertes por mes
Representa la variación mensual del total de fallecimientos.
Hallazgo: Se observa una tendencia estable con picos en meses como junio y diciembre, posiblemente asociados a factores estacionales o sociales.

3. Top 5 ciudades más violentas (códigos X9)
Filtra las muertes por causas violentas (X9 del CIE10).
Hallazgo: Municipios como Cali y Medellín concentran los mayores casos de homicidios.

4. Top 10 ciudades con menor mortalidad
Presenta las ciudades con menor número de defunciones en porcentaje.
Hallazgo: Refleja la baja mortalidad en municipios rurales de menor densidad poblacional.

5. Tabla – Principales causas de muerte
Lista los 10 códigos CIE10 más frecuentes.
Hallazgo: Predominan enfermedades cardiovasculares, respiratorias y neoplasias.

6. Barras apiladas – Muertes por sexo y departamento
Compara la mortalidad entre hombres y mujeres por departamento.
Hallazgo: Se observa mayor mortalidad masculina, especialmente en causas violentas.

7. Histograma – Distribución por rango de edad
Clasifica los fallecimientos en grupos etarios (0–4, 15–19, 60–84, etc.).
Hallazgo: El grupo de adultos mayores (60–84 años) concentra la mayor proporción de 
muertes, seguido por adultos medios (45–59 años).


Conclusión

La aplicación permite comprender de forma visual y dinámica la mortalidad en Colombia, 
integrando datos geográficos, demográficos y epidemiológicos.

Su diseño modular, despliegue en la nube y uso de herramientas open source la convierten 
en una base sólida para futuros proyectos de análisis de salud pública, predicción o dashboards 
interactivos más avanzados.
