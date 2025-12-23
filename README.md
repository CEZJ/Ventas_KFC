# Ventas_KFC
Proyecto de Certificacion Python for Data Analytics

<img width="254" height="269" alt="image" src="https://github.com/user-attachments/assets/c44d0f14-0b40-41a9-9fea-c45541441009" />

“Análisis de Ventas y Optimización de Inventario en KFC con Python”


Comprensión del Negocio

Kentucky Fried Chicken (KFC) es una reconocida cadena de restaurantes de comida rápida especializada en pollo frito. Fundada por Harland D. Sanders, conocido como el Coronel Sanders, la empresa ha experimentado un crecimiento significativo desde sus inicios hasta convertirse en una marca global. 

En 2023, KFC registró ventas globales de aproximadamente 33,865 millones de dólares (Statista, 2024), consolidando su presencia internacional con nuevas aperturas en India y Rumania, y con planes de expansión hacia su país número 150 en 2024 (KFC Global, 2024). En la península ibérica, la franquicia ha crecido con 39 nuevos restaurantes en España y 9 en Portugal, alcanzando un total de 352 locales en la región (Franquicias Hoy, 2023). Además, la empresa ha implementado innovaciones como el KFC Innovations Lab, un proyecto de crowdfunding que permite a los consumidores influir en el desarrollo de nuevos productos y experiencias (Barrixe, 2023).

KFC ingresó al mercado peruano en 1981 y ha expandido su presencia con más de 145 locales en todo el país. Su crecimiento refleja tendencias clave en el consumo de comida rápida y en la evolución del mercado gastronómico peruano (El Comercio, 2022). A través del análisis de datos de ventas, es posible identificar patrones de demanda, preferencias de los clientes y factores estacionales que impactan el desempeño de la marca en distintas ubicaciones.

Planteamiento del problema
Uno de los principales problemas en KFC es la variabilidad en las ventas de productos, lo que puede generar dos situaciones críticas:  
Sobrestock: Exceso de inventario que provoca desperdicio de productos perecederos y aumento de costos operativos.  
Desabastecimiento: Falta de productos clave en momentos de alta demanda, generando pérdidas de ventas y clientes insatisfechos.  
Estas fluctuaciones en las ventas están influenciadas por diversos factores, como la demanda según días y horarios, el impacto de promociones y descuentos, los cambios en precios que afectan las preferencias de los clientes y la popularidad variable de ciertos productos, como gaseosas y combos de pollo. La combinación de estos elementos dificulta la gestión eficiente del inventario, aumentando el riesgo de sobrestock o desabastecimiento.


Objetivo del Negocio
El objetivo principal es optimizar la gestión del inventario y la planificación de ventas en KFC para reducir desperdicios, minimizar desabastecimientos y maximizar la rentabilidad. Esto se logrará mediante el análisis de datos y la predicción de la demanda, mejorando la eficiencia operativa y la satisfacción del cliente. El enfoque se centra en:
Mejorar la eficiencia en el manejo del stock.
Aplicar estrategias de precios y promociones basadas en datos.
Alinear la oferta de productos con las preferencias y comportamientos de los clientes.
Objetivos Analíticos
El propósito de este estudio es analizar las ventas de KFC para:
Identificar patrones de compra y su impacto en el inventario: Detectar cómo las variaciones en la demanda afectan la disponibilidad de productos.
Determinar el efecto de promociones y variaciones de precios en la demanda: Evaluar cómo las campañas de descuentos y cambios de precios influyen en las ventas.
Predecir tendencias de ventas utilizando herramientas estadísticas y visualización de datos: Utilizar modelos predictivos para anticipar la demanda y mejorar la planificación.
Optimizar la planificación del stock: Reducir pérdidas y mejorar la disponibilidad de productos mediante un manejo más eficiente del inventario.

Tratamiento de los datos y análisis gráfico
Fuentes de información
Para el análisis de ventas entre las tres sucursales de KFC (Sucursal Norte, Sucursal Centro y Sucursal Sur), se trabajó con un conjunto de 500 registros recolectados como muestra parcial de las operaciones de cada sucursal; estos consisten de registros de ventas del año 2022 al 2024, incluyendo información como fecha de compra, producto y cantidad por cada transacción.

 Tratamiento de Datos y Preparación para el Análisis
La carga y conexión de los datos se llevó a cabo en Google Colab, utilizando diversas librerías especializadas en manipulación y análisis de datos. En particular, pandas fue utilizada para la estructuración y procesamiento de la información, mientras que os permitió la gestión de rutas y directorios. Para la visualización de datos, se emplearon seaborn y matplotlib.pyplot, los cuales facilitaron la representación gráfica de los resultados. Adicionalmente, scipy.stats fue utilizada para realizar análisis estadísticos y detección de posibles anomalías en los datos, mientras que numpy optimizó los cálculos numéricos. Finalmente, para el modelado y la identificación de patrones en la información, se incorporó sklearn.tree, enfocándose en técnicas como los árboles de decisión.

Una vez realizada la carga de datos, se procedió con la limpieza y estandarización. Se eliminaron registros duplicados para evitar inconsistencias en el análisis y se agruparon los datos por producto, consolidando la información de ventas de manera estructurada. Este proceso permitió garantizar que cada producto estuviera representado con datos precisos y sin redundancias.

Variables relevantes
Cantidad: Indicador de la demanda de cada producto y su aceptación en el mercado.
Precio Unitario: Parámetro esencial para validar la coherencia en la facturación de las ventas.
Total Venta: Variable determinante para medir la rentabilidad y el éxito comercial.
Sucursal: Elemento clave para segmentar los datos por ubicación geográfica y analizar tendencias específicas en los distintos puntos de venta.

Análisis de Tipos de Datos y Manipulación
El análisis de las medidas de tendencia central y dispersión permite caracterizar la distribución de las variables Precio Unitario, Cantidad y Total Venta, proporcionando información clave sobre su comportamiento y variabilidad.

El precio unitario presenta un valor medio de 15.26, con una desviación estándar de 7.70, lo que indica una variabilidad moderada en los precios de los productos. Los valores oscilan entre 5.00 y 25.90, con una mediana de 18.30, lo que sugiere una distribución ligeramente sesgada hacia precios más altos.
La variable cantidad tiene una media de 2.51, con un mínimo de 1 y un máximo de 4, lo que indica que la mayoría de las ventas corresponden a pocas unidades por transacción. La desviación estándar es 1.14, reflejando una baja dispersión.
El total de ventas muestra una mayor variabilidad, con una media de 37.99 y una desviación estándar de 27.33. Se observan valores que van desde 5.00 hasta 103.60, con una mediana de 26.70. El rango intercuartílico (IQR) indica que el 50 % central de los datos se encuentra entre 17.80 y 54.90, lo que sugiere la presencia de algunas ventas significativamente altas que incrementan el valor máximo.

El análisis de estas métricas permite comprender la distribución de los datos y establecer criterios para su segmentación y comparación en los siguientes apartados.

Análisis de ventas 
El análisis del promedio de las ventas diarias de la empresa de comida rápida KFC por sucursal y producto permite identificar qué productos poseen una mayor demanda en cada zona, proporcionando información relevante para la toma de decisiones estratégicas.

TABLA N°1: Promedio de ventas por Sucursal y Producto

Fuente: Elaboración propia

Tomando en cuenta los registros históricos de las ventas desde el año 2022 hasta la actualidad, se calculó el promedio de ventas por producto en cada sucursal (Tabla N°1). Los resultados indican que la Sucursal Centro registra los valores más altos en la mayoría de los productos, destacando el Mega Box (S/. 66.00) y el Combo Crispy (S/. 64.85) como los más vendidos, mientras que la Sucursal Sur presenta un comportamiento similar, con el Mega Box (S/. 66.60) y las Alitas BBQ (S/. 46.51) liderando las ventas. En contraste, la Sucursal Norte tiene los promedios más bajos en casi todos los productos, con el Mega Box (S/. 59.98) y el Combo Pollo Clásico (S/. 49.50) como los más demandados. 

Evolución de las ventas

El gráfico N°1 muestra la evolución de ventas mensuales por sucursal evidenciando la tendencia y variabilidad de las ventas totales mensuales en las tres zonas desde enero de 2022 hasta enero de 2025. Todas las sucursales presentan una alta volatilidad, con fluctuaciones pronunciadas a lo largo del tiempo. Sin embargo, hay diferencias en los niveles de ventas promedio (Ver Anexo N°1). 
GRÁFICO N°1: Evolución de las ventas totales mensuales por sucursal












Fuente: Elaboración propia

La Sucursal Centro presenta el mayor promedio de ventas mensuales, con S/. 213.04, lo que indica que es la zona con mayor demanda. En contraste, la Sucursal Norte tiene el menor promedio, con S/. 155.51, reflejando un menor volumen de ventas en comparación con las otras zonas, mientras que la Sucursal Sur se mantiene en un nivel intermedio con S/. 159.03. Aunque las tres sucursales experimentan picos y caídas similares, se puede notar que la Sucursal Centro suele mantenerse en valores más elevados y estables en comparación con la Norte y la Sur.

Ventas por producto
El diagrama (Gráfico N°2) de  distribución de ventas por producto muestra que los productos con mayor participación en las ventas totales son el Sundae de Chocolate (16.4%), seguido del Combo Pollo Clásico (15.6%) y la Bebida Mediana (15.0%), esto indica que hay una fuerte preferencia por estos tres productos. En cambio, el Combo Crispy (11.0%) es el de menor participación, representando la menor proporción dentro del total de ventas. Otros productos como el Mega Box (14.2%), las Alitas BBQ (14.8%) y las Papas Fritas Grandes (13.0%) mantienen una participación similar. Esta información permite identificar los productos más demandados y orientar estrategias para reforzar su disponibilidad y promoción.

Gráfico N°2: Porcentaje de las ventas totales históricas por producto 

Fuente: Elaboración propia
Ventas por zona
Gráfico N°3: Ventas totales históricas por Sucursal 

El histograma de Total de Ventas por Sucursal (Gráfico N°3) muestra la distribución de la cantidad de ventas en distintos rangos de valores, diferenciando cada sucursal mediante colores. Se observa que la mayoría de las ventas se concentran en rangos bajos, especialmente entre 10 y 30 unidades, donde las tres sucursales presentan la mayor frecuencia. La Sucursal Centro domina en casi todos los intervalos, lo que indica que tiene un mayor volumen de ventas en comparación con las demás. La Sucursal Norte y la Sucursal Sur tienen una participación menor y más equilibrada entre sí. A medida que el total de ventas aumenta, la frecuencia disminuye, lo que sugiere que hay menos días con ventas muy altas.

Machine Learning para Pronóstico 
Se implementó un árbol de decisión de regresión con el objetivo de predecir el total de ventas de bebidas medianas en función de la cantidad vendida. El modelo fue entrenado con una profundidad máxima de 3 niveles, permitiendo realizar divisiones basadas en los valores de cantidad.

Interpretación del Árbol de Decisión (Gráfico N°4)
El árbol de decisión segmenta los datos en distintos niveles con base en la variable cantidad. Los principales hallazgos son los siguientes:
El nodo raíz divide los datos en Cantidad ≤ 2.5 y Cantidad > 2.5.
Si la cantidad es menor o igual a 2.5, el total de ventas promedio es 12.667.
Si la cantidad es mayor a 2.5, el total de ventas promedio es 17.368.
En el grupo con Cantidad ≤ 2.5, se genera una segunda división en Cantidad ≤ 1.5.
Si la cantidad es ≤ 1.5, el total de ventas promedio es 7.838.
Si la cantidad está entre 1.5 y 2.5, el total de ventas promedio es 10.0.
En el grupo con Cantidad > 2.5, se genera otra división en Cantidad ≤ 3.5.
Si la cantidad es ≤ 3.5, el total de ventas promedio es 15.0.
Si la cantidad es > 3.5, el total de ventas promedio es 20.0.

Cada nodo hoja muestra valores de squared_error = 0.0, lo que indica que dentro de cada grupo la variabilidad es mínima y el modelo ha segmentado los datos de manera precisa en términos de cantidad vendida.
Gráfico N°4: Predicción de las ventas de las Bebidas Medianas












Clustering de Sucursales
El gráfico muestra la segmentación de sucursales según sus ventas totales y la cantidad de productos vendidos, usando K-Means. Cada color representa un grupo con características similares.
Interpretación:
Sucursales de alto rendimiento: Mayor cantidad de ventas.
Sucursales intermedias: Ventas y cantidades equilibradas.
Sucursales de bajo rendimiento: Menores ventas y productos vendidos.











Distribución Normal
La forma de la curva sugiere que las ventas siguen una distribución normal, lo que permite aplicar modelos estadísticos.
La media ayuda a entender el comportamiento general de las ventas en todas las sucursales.
Este análisis es útil para predecir tendencias de ventas, detectar anomalías y mejorar la toma de decisiones comerciales.

Prueba de Hipotesis
Se realiza una prueba t para una muestra con el objetivo de determinar si la media de ventas del producto "Mega Box" es significativamente diferente de 5000.
Interpretación de los Resultados:
Se obtiene un estadístico t muy bajo y un p-valor de 0.0000.
Como el p-valor es menor a 0.05, se rechaza la hipótesis nula.
Esto indica que la media de ventas de "Mega Box" es significativamente diferente de 5000.

Interpretación de resultados
Conclusiones del análisis

Variabilidad en las ventas: Las ventas mensuales de las tres sucursales de KFC fluctúan mucho. La Sucursal Central tuvo las ventas mensuales promedio más altas, seguida por la Sucursal Sur, y la Sucursal Norte tuvo las ventas mensuales promedio más bajas.
Productos más vendidos: Los artículos más populares son la Mega Box y el Crispy Combo en el Departamento Central, mientras que la Mega Box y las Alitas BBQ son particularmente populares en el Departamento Sur. En la ubicación norte, los artículos más populares son la Mega Box y el Combo Pollo Clásico.
Preferencias de los Clientes: El Sundae de Chocolate, el Combo Pollo Clásico y la Bebida Mediana son los productos con mayores ventas totales, lo que demuestra que la gente prefiere fuertemente estos productos.
El modelo de predicción con árboles de decisión permitió identificar la relación entre la cantidad vendida y el total de ventas, proporcionando una herramienta útil para anticipar la demanda y mejorar la gestión de inventario. Sin embargo, la alta dispersión de datos sugiere que factores externos, como la estacionalidad y las campañas de marketing, también influyen en las ventas.

Recomendaciones para la empresa

Optimización de inventarios: Implementar un sistema de gestión de inventarios basado en la demanda histórica y tendencias identificadas para reducir excedentes y faltantes de inventario.
Estrategia promocional: Centrarse en promociones y descuentos en productos populares, como la Mega Box y el Combo Pollo Clásico , para aumentar las ventas y la satisfacción del cliente.
Segmentación de Mercado y Expansión de Sucursales: Identificar nuevas zonas de alto tráfico con potencial de crecimiento para futuras aperturas y ajustar la oferta de productos en cada sucursal según las preferencias locales para mejorar la rentabilidad.
Ajustes en la oferta de productos: Considerar los cambios en la demanda en las sucursales y ajustar la oferta de productos de cada sucursal para satisfacer mejor las preferencias locales.
Análisis continuo de datos: Continuamente usar herramientas estadísticas y de visualización de datos para predecir las tendencias de ventas y ajustar las estrategias comerciales en consecuencia.
