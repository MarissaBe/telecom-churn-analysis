# telecom-churn-analysis
Análisis de abandono de clientes de telecomunicaciones utilizando Python y machine learning.
Análisis de abandono de clientes de telecomunicaciones

Descripción del proyecto

Este proyecto analiza el comportamiento de clientes de una empresa de telecomunicaciones con el objetivo de identificar patrones asociados al abandono de clientes (churn).
El análisis busca apoyar la toma de decisiones de la empresa y estimar el nivel histórico de abandono que podría presentarse en un siguiente ciclo bajo condiciones similares.

Problema de negocio

La pérdida de clientes representa un desafío importante para las empresas de telecomunicaciones.
El objetivo del proyecto es analizar los datos disponibles para responder principalmente:
•	¿Qué características presentan los clientes que abandonan?
•	¿Existen diferencias claras entre clientes activos y clientes que abandonan?
•	¿Es posible identificar clientes con mayor probabilidad de abandono?
•	¿Cuál es la tasa histórica de abandono y qué referencia puede ofrecer para un siguiente ciclo?

Datos utilizados

El proyecto utiliza tres archivos:
•	customer_info.csv: información demográfica, contractual y económica de los clientes.
•	usage_data.csv: comportamiento mensual de uso durante 2023.
•	churn_labels.csv: estado de abandono de cada cliente.

Tamaño de los datos

Después de la limpieza:
•	10.000 clientes.
•	120.000 registros mensuales de uso.
•	12 registros mensuales por cliente.
•	786 clientes que abandonaron.
•	9.214 clientes que permanecieron activos.

Limpieza y preparación de los datos

Durante el proceso de limpieza se realizaron, entre otras, las siguientes tareas:
•	Eliminación de registros duplicados.
•	Eliminación de clientes duplicados.
•	Tratamiento de valores faltantes.
•	Corrección de valores negativos en MonthlyCharges.
•	Conversión de fechas.
•	Integración de la información de clientes, uso y abandono.
•	Creación de la variable TenureYears para representar la antigüedad del cliente.
•	Conversión de variables categóricas a variables numéricas para los modelos.

Distribución del abandono

La distribución encontrada fue:
•	Clientes activos: 9.214 (92,14%).
•	Clientes que abandonaron: 786 (7,86%).
La tasa histórica de abandono fue de 7,86%.

Análisis exploratorio

Se analizaron diferentes características de los clientes:
•	Tipo de contrato.
•	Región.
•	Edad.
•	Antigüedad.
•	Minutos de llamadas.
•	Consumo de datos.
•	Cantidad de SMS.
•	Quejas.

Los resultados muestran diferencias pequeñas entre los clientes activos y los clientes que abandonaron.
Por ejemplo, la tasa de abandono según contrato fue:

•	Monthly: 7,56%.
•	Prepaid: 7,67%.
•	Yearly: 8,82%.

Las diferencias no son suficientemente grandes para considerar que un tipo de contrato explique por sí solo el abandono.
Modelos predictivos

Se construyeron dos modelos sencillos de clasificación:
•	Regresión logística.
•	Random Forest.

Los modelos permitieron obtener probabilidades de abandono para los clientes.
Sin embargo, los resultados mostraron una capacidad limitada para diferenciar claramente entre clientes que abandonan y clientes que permanecen.
Por esta razón, no se recomienda utilizar las variables disponibles para asignar un nivel de riesgo individual de abandono con alta confianza.

Comportamiento durante los últimos meses

El análisis temporal mostró un cambio importante durante los últimos tres meses de 2023.

Antes de octubre:
•	Promedio de llamadas: 498,65 minutos.
•	Consumo de datos: 10,00 GB.

Últimos tres meses:
•	Promedio de llamadas: 473,65 minutos.
•	Consumo de datos: 9,58 GB.

Esto representa aproximadamente:
•	5,0% menos minutos de llamadas.
•	4,2% menos consumo de datos.

El número de SMS y las quejas se mantuvieron prácticamente estables.
Este cambio representa un comportamiento que debería ser monitoreado por la empresa, aunque los datos disponibles no permiten afirmar que sea la causa del abandono.

Referencia para el próximo ciclo
La tasa histórica de abandono fue de 7,86%.
Si las condiciones del negocio se mantienen similares, esta tasa puede utilizarse como referencia para estimar el posible nivel de abandono de un siguiente ciclo.
Por ejemplo, para una base de 10.000 clientes:
10.000 × 7,86% ≈ 786 clientes
Esto no representa una predicción individual de qué clientes abandonarán, sino una estimación basada en el comportamiento histórico.

Dashboards

El proyecto incluye tres dashboards:

Dashboard 1 - Overview
Presenta:
•	Total de clientes.
•	Clientes activos.
•	Clientes que abandonaron.
•	Tasa histórica de abandono.
•	Abandono según tipo de contrato.

Dashboard 2 - Customer Details
Presenta información específica relacionada con:
•	Región.
•	Edad.
•	Tipo de contrato.
•	Comportamiento de uso.
•	Comparación entre clientes activos y clientes que abandonaron.

Dashboard 3 - Timeline & Next Cycle
Presenta:
•	Evolución mensual del uso durante 2023.
•	Cambio observado durante los últimos tres meses.
•	Referencia histórica de abandono para un posible siguiente ciclo.

Conclusiones
El análisis muestra que el abandono de clientes no está explicado por una característica individual claramente diferenciadora.
Las variables demográficas, contractuales, de uso, antigüedad y quejas presentan diferencias pequeñas entre clientes activos y clientes que abandonaron.
Los modelos predictivos construidos también mostraron una capacidad limitada para distinguir de manera confiable entre ambos grupos.
Por lo tanto, con los datos disponibles, la empresa no puede identificar con suficiente precisión quién será el próximo cliente que abandone.
Sin embargo, sí puede utilizar la tasa histórica de 7,86% como referencia para estimar el nivel de abandono esperado bajo condiciones similares.
En una base de 10.000 clientes, esto representa aproximadamente 786 posibles abandonos por ciclo.

Recomendaciones
Para mejorar futuras predicciones, sería recomendable incorporar información adicional y más reciente sobre los clientes, por ejemplo:
•	Cambios recientes en el consumo.
•	Cambios de plan.
•	Fallas del servicio.
•	Llamadas al servicio al cliente.
•	Retrasos en pagos.
•	Cancelaciones o modificaciones de servicios.
•	Nivel de satisfacción.
•	Interacciones recientes con la empresa.

También sería recomendable disponer de etiquetas de abandono asociadas a períodos específicos para poder construir una predicción temporal más precisa del siguiente ciclo de facturación.

Limitaciones
El conjunto de datos disponible contiene una etiqueta de abandono por cliente y registros de uso correspondientes a 2023.
Por esta razón, el análisis permite estudiar patrones históricos y construir una referencia de abandono, pero no demuestra completamente una predicción temporal individual del siguiente ciclo de facturación.
Para lograr una predicción más precisa sería necesario contar con información histórica organizada por períodos y conocer el abandono posterior a cada período.

Herramientas utilizadas
•	Python.
•	Pandas.
•	Matplotlib.
•	Scikit-learn.
•	Google Colab.
•	GitHub.

Estructura del proyecto
telecom-churn-analysis/
│
├── Telecom_Churn_Analysis.ipynb
├── README.txt
│
├── dashboards/
│   ├── dashboard_overview.png
│   ├── dashboard_detail.png
│   └── dashboard_timeline.png
│
└── data/
    ├── usage_data.csv
    ├── customer_info.csv
    └── churn_labels.csv

