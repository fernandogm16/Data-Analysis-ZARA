# Data-Analysis-ZARA
Repositorio para proyecto de pregrado de la UEES en Data analysis que incluye un análisis completo de un dataset de la compañía textil ZARA
Este proyecto es un análisis integral de Minería de Datos (Data Mining) aplicado a un catálogo real de la marca de ropa Zara. El objetivo principal es extraer inteligencia de negocios, descubrir patrones de compra ocultos en diferentes perfiles de consumidores y desarrollar un modelo predictivo capaz de anticipar si una prenda será un éxito en ventas (Bestseller) basado en sus características fundamentales (precio, sección, temporada y promociones).

El sistema se ejecuta en un único script maestro en Python que carga los datos, los limpia heurísticamente y aplica cuatro ramas principales de la ciencia de datos, generando 10 visualizaciones analíticas (2D y 3D) y entregando conclusiones automatizadas en la consola.

Técnicas de Machine Learning Implementadas
El código fue diseñado implementando las siguientes metodologías centrales de la Minería de Datos:

Detección de Anomalías (Outliers) - Isolation Forest: Se identifican prendas estadísticamente atípicas (piezas de lujo de alto costo) que rompen la distribución normal del catálogo para entender cómo la marca emplea ciertos productos como anclaje de prestigio.

Segmentación (Clustering) - K-Means 2D y 3D: El catálogo es agrupado algorítmicamente en cuatro ecosistemas distintos (ej. básicos masivos frente a premium de bajo movimiento) integrando una métrica tridimensional de ingresos brutos.

Reglas de Asociación - Algoritmo Apriori: Búsqueda de patrones condicionales lógicos (Si ocurre A -> Entonces ocurre B). Permite descubrir el grado de elasticidad precio-demanda y la dependencia a promociones comparando distintas secciones del catálogo.

Clasificación Predictiva - Árbol de Decisión: Entrenamiento de un modelo supervisado para clasificar productos en "Ventas Altas" o "Ventas Bajas". Incluye un análisis de importancia de variables (Feature Importance) y una Matriz de Confusión para evaluar el desempeño y precisión del modelo.

Hallazgos y Conclusiones Principales
A través del análisis automatizado, logramos descubrir la estrategia de "Catálogo Híbrido" implementada por la marca:

El Motor de Liquidez: Las prendas de la sección masculina, de precio bajo y atemporales, generan ventas masivas continuas sin depender de estrategias de promoción, constituyendo la base de flujo de caja.
Sensibilidad Femenina al Precio: Las ventas de volumen en la sección femenina están drásticamente ligadas a las promociones. Este consumidor muestra una alta respuesta y dependencia a las ofertas para movilizar grandes volúmenes.
El Sesgo de la Temporada: La indumentaria estacional de precio alto presenta el mayor riesgo de estancamiento. Estadísticamente, solo se convierte en un éxito comercial si es impulsada por una estrategia de promoción activa.
Requisitos e Instalación
El entorno de ejecución está optimizado para detectar dinámicamente si se opera de forma local (PC / GitHub) o a través de instancias de Google Colab.

Opción 1: Ejecución Local
Asegúrese de contar con un entorno Python configurado y ejecute el siguiente comando en su terminal para instalar las dependencias necesarias:

bash


pip install pandas numpy matplotlib seaborn scikit-learn mlxtend
Posteriormente, inicie el script:

bash


python analisis_zara.py
El sistema solicitará que introduzca mediante la consola la ruta absoluta de su archivo original.

Opción 2: Ejecución en Google Colab
Copie el código del script maestro en una nueva celda de ejecución de Colab.
Ejecute la celda.
La interfaz desplegará automáticamente un botón interactivo para cargar su archivo directamente. No requiere instalación manual de dependencias.
Estructura de los Datos Requeridos
El script incluye una función de limpieza avanzada de monedas, espacios y delimitadores europeos/americanos. Acepta formatos .csv y .xlsx, requiriendo contar al menos con las siguientes columnas (el sistema es insensible a mayúsculas/minúsculas):

Price: Precio nominal de la prenda.
Sales Volume: Cantidad de unidades vendidas.
Promotion: Estatus de descuento (Ej. Yes/No).
Seasonal: Indicador de temporalidad de la prenda.
Section: División departamental (Ej. Hombre, Mujer).
