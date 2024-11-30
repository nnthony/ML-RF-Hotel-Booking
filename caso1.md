# Dataset 1 Hotel Booking
Este data set está disponible de manera pública en Kaggle:
https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand

El data set posee 32 columnas y 119390 filas.

Ha rasgos generales:
- El dataset posee datos de 2 hoteles.
- Probablemente sean hoteles de Europa.
- Es data de la reserva y su programación, además la columna `is_canceled` posee el dato de si esta reserva fue cancelada o no.
### Descripción de las columnas
- ``hotel`` Hotel (H1 = Hotel Resort o H2 = Hotel Ciudad)
- ``is_canceled`` Valor que indica si la reserva fue cancelada (1) o no (0)
- ``lead_time`` Número de días transcurridos entre la fecha de ingreso de la reserva en el PMS y la fecha de llegada
- ``arrival_date_year`` Año de la fecha de llegada
- ``arrival_date_month`` Mes de la fecha de llegada
- ``arrival_date_week_number`` Número de semana del año para la fecha de llegada
- ``arrival_date_day_of_month`` Día de la fecha de llegada
- ``stays_in_weekend_nights`` Número de noches de fin de semana (sábado o domingo) que el huésped se quedó o reservó para quedarse en el hotel
- ``stays_in_week_nights`` Número de noches de semana (lunes a viernes) que el huésped se quedó o reservó para quedarse en el hotel
- ``adults`` Número de adultos
- ``children`` Número de niños
- ``babies`` Número de bebés
- ``meal`` Tipo de comida reservada. Las categorías se presentan en los paquetes estándar de comida de hospitalidad: No definido/SC – sin paquete de comida; BB – Solo desayuno; HB – Media pensión (desayuno y otra comida, generalmente cena); FB – Pensión completa (desayuno, almuerzo y cena)
- ``country`` País de origen. Las categorías se representan en el formato ISO 3155–3:2013
- ``market_segment`` Designación del segmento de mercado. En las categorías, el término “TA” significa “Agentes de viajes” y “TO” significa “Operadores turísticos”
- ``distribution_channel`` Canal de distribución de la reserva. El término “TA” significa “Agentes de viajes” y “TO” significa “Operadores turísticos”
- ``is_repeated_guest`` Valor que indica si el nombre de la reserva es de un huésped repetido (1) o no (0)
- ``previous_cancellations`` Número de reservas anteriores que fueron canceladas por el cliente antes de la reserva actual
- ``previous_bookings_not_canceled`` Número de reservas anteriores que no fueron canceladas por el cliente antes de la reserva actual
- ``reserved_room_type`` Código del tipo de habitación reservada. El código se presenta en lugar de la designación por razones de anonimato.
- ``assigned_room_type`` Código del tipo de habitación asignado a la reserva. A veces, el tipo de habitación asignado difiere del tipo de habitación reservado debido a razones operativas del hotel (por ejemplo, overbooking) o por solicitud del cliente. El código se presenta en lugar de la designación por razones de anonimato.
- ``booking_changes`` Número de cambios/modificaciones realizados a la reserva desde el momento en que se ingresó en el PMS hasta el momento del check-in o la cancelación
- ``deposit_type`` Indicación sobre si el cliente hizo un depósito para garantizar la reserva. Esta variable puede asumir tres categorías: Sin depósito – no se realizó ningún depósito; No reembolsable – se hizo un depósito por el valor del costo total de la estancia; Reembolsable – se hizo un depósito con un valor inferior al costo total de la estancia.
- ``agent`` ID de la agencia de viajes que hizo la reserva
- ``company`` ID de la empresa/entidad que hizo la reserva o responsable del pago de la reserva. El ID se presenta en lugar de la designación por razones de anonimato.
- ``days_in_waiting_list`` Número de días que la reserva estuvo en la lista de espera antes de ser confirmada al cliente
- ``customer_type`` Tipo de reserva, asumiendo una de las cuatro categorías: Contrato - cuando la reserva tiene una asignación o algún otro tipo de contrato asociado; Grupo – cuando la reserva está asociada a un grupo; Transitorio – cuando la reserva no forma parte de un grupo ni de un contrato, y no está asociada a otras reservas transitorias; Transitorio-party – cuando la reserva es transitoria, pero está asociada a al menos otra reserva transitoria
- ``adr`` Tasa diaria promedio definida como la suma de todas las transacciones de alojamiento dividida por el número total de noches de estancia
- ``required_car_parking_spaces`` Número de espacios de estacionamiento para autos requeridos por el cliente
- ``total_of_special_requests`` Número de solicitudes especiales realizadas por el cliente (por ejemplo, cama doble o piso alto)
- ``reservation_status`` Último estado de la reserva, asumiendo una de tres categorías: Cancelada – la reserva fue cancelada por el cliente; Check-Out – el cliente ha hecho el check-in pero ya ha partido; No-Show – el cliente no hizo check-in y no informó al hotel sobre el motivo
- ``reservation_status_date`` Fecha en la que se estableció el último estado. Esta variable puede usarse junto con el estado de la reserva para entender cuándo se canceló la reserva o cuándo el cliente hizo el check-out del hotel


### Campos vacios (Proporción)
````
hotel                              0.000000
is_canceled                        0.000000
lead_time                          0.000000
arrival_date_year                  0.000000
arrival_date_month                 0.000000
arrival_date_week_number           0.000000
arrival_date_day_of_month          0.000000
stays_in_weekend_nights            0.000000
stays_in_week_nights               0.000000
adults                             0.000000
children                           0.003350
babies                             0.000000
meal                               0.000000
country                            0.408744
market_segment                     0.000000
distribution_channel               0.000000
is_repeated_guest                  0.000000
previous_cancellations             0.000000
previous_bookings_not_canceled     0.000000
reserved_room_type                 0.000000
assigned_room_type                 0.000000
booking_changes                    0.000000
deposit_type                       0.000000
agent                             13.686238
company                           94.306893
days_in_waiting_list               0.000000
customer_type                      0.000000
adr                                0.000000
required_car_parking_spaces        0.000000
total_of_special_requests          0.000000
reservation_status                 0.000000
reservation_status_date            0.000000
````
Se realizó las siguientes acciones con las columnas
| Columna  | % Nulos  | Acción                                      |
|----------|----------|---------------------------------------------|
| children | 0.33%    | Completar campos con la mediana.           |
| country  | 40.87%   | Completar campos con 'Unknown'.            |
| agent    | 13.69%   | Completar campos cifra cero 0.             |
| company  | 94.31%   | Eliminar la columna.                       |

## Análisis Exploratorio de Datos
Los datos son de dos hoteles distintos
````
hotel         is_canceled
City Hotel    0              46084
              1              33079
Resort Hotel  0              28927
              1              11120
````
Las reservas de ambos hoteles se concentran en Europa, la particularidad para el City Hotel es que tiene una cantidad considerable de reservas desde Brasil, de igual foma con el Resort Hotel, tiene cantidad considerable de reservas desde China
| hotel        | country | country_name      | count |
|--------------|---------|-------------------|-------|
| **City Hotel**  | PRT     | Portugal          | 10793 |
|              | FRA     | France            | 7069  |
|              | DEU     | Germany           | 5010  |
|              | GBR     | United Kingdom    | 3746  |
|              | ESP     | Spain             | 3278  |
|              | ITA     | Italy             | 2049  |
|              | BEL     | Belgium           | 1479  |
|              | NLD     | Netherlands       | 1258  |
|              | USA     | United States     | 1185  |
|              | BRA     | Brazil            | 1063  |
| **Resort Hotel**| PRT     | Portugal          | 10184 |
|              | GBR     | United Kingdom    | 5922  |
|              | ESP     | Spain             | 3105  |
|              | IRL     | Ireland           | 1734  |
|              | FRA     | France            | 1399  |
|              | DEU     | Germany           | 1057  |
|              | CN      | China             | 614   |
|              | NLD     | Netherlands       | 458   |
|              | Unknown | Unknown           | 419   |
|              | USA     | United States     | 407   |

**Origen de visitas al City Hotel**
![image](graph\M1\1country.png)
**Origen de visitas al Resort Hotel**
![image](graph\M1\1country-.png)

### Tipo de habitaciones reservadas
Existe una considerable superioridad en la demanda de habitaciones de tipo A, el segundo tipo, con amplia diferencia con el primero es el tipo D, seguido del tipo E.
![image](graph\M1\1.png)
### ADR y Tipo de Habitacion
Las tasas diarias promedio para el Resort Hotel (en azul) tienden a ser más altas que las del City Hotel (en anaranjado) para la mayoría de los tipos de habitaciones. Sin embargo, hay variaciones dependiendo del tipo específico de habitación.
![image](graph\M1\2.png)


La dispersión y la presencia de valores atípicos varían entre los tipos de habitaciones y los tipos de hoteles, sugiriendo diversidad en la demanda y el precio.

Todos los valores atípicos, indicados por puntos individuales fuera de los límites, representan precios ADR inusualmente altos o bajos en comparación con la mayoría de las noches de estancia para ese tipo de habitación.

### Reserva por tipo de habitación en los años
Este gráfico es un histograma que muestra la cantidad de reservas por tipo de habitación reservada, desglosado por año de llegada (2015, 2016 y 2017).
![image](graph\M1\3.png)
Este desglose proporciona una visión de cómo las reservas han evolucionado anualmente para cada tipo de habitación.
- El tipo de habitación A es claramente el más popular durante todos los años, con un número significativamente mayor de reservas en comparación con los otros tipos de habitaciones. Este patrón se mantiene constante en los tres años observados.
- Hay una ligera variabilidad en las reservas para el tipo de habitación A entre los años, pero sigue siendo dominante.
- Los otros tipos de habitaciones (B, C, D, etc.) tienen un número mucho menor de reservas, con algunas variaciones año tras año. En particular, se observa un aumento pequeño en las reservas de algunos tipos de habitaciones en 2016 y 2017 en comparación con 2015.
### Reserva por meses durante los años
Este gráfico es un histograma que presenta la cantidad de reservas por mes de llegada, desglosado por año de llegada
![image](graph\M1\4.png)
- Se observa que para algunos meses no hay datos para todos los años. Por ejemplo, falta información para 2015 en Enero, Marzo, Noviembre y Diciembre, lo que indica que los datos no están completos para todos los meses de cada año en el conjunto de datos.
- Los meses de verano (Junio, Julio, Agosto) muestran un volumen más alto de reservas, lo cual es común en la industria hotelera ya que coincide con las vacaciones de verano en muchas regiones.
- Las reservas son bastante constantes en algunos meses del año, lo que podría indicar una temporada constante de demanda, mientras que picos en algunos meses indican períodos de alta demanda.
La ausencia de datos en algunos meses para ciertos años sugiere que el conjunto de datos no es completo para 2015, 2016 y 2017. Esto podría limitar los resultados y obliga a considerar otros factores diferentes a los años.
### Reserva por meses de los hoteles
Este gráfico es un conjunto de histogramas que muestra la cantidad de reservas por mes y año diferenciado por tipo de hotel: City Hotel y Resort Hotel. 
![image](graph\M1\5.png)
- City Hotel presenta un patrón consistente durante todo el año, con reservas relativamente uniformes, aunque con ciertas fluctuaciones.
- Los meses de otoño e invierno (desde septiembre hasta diciembre) tienden a mostrar un volumen ligeramente más alto de reservas en comparación con meses anteriores, especialmente en 2016 y 2017.
- El número de reservas para Resort Hotel es generalmente menor que para City Hotel, probablemente debido a la naturaleza estacional y al segmento de mercado diferente del resort.
- Las reservas en City Hotel son consistentemente altas durante más meses del año, lo cual es indicativo de una demanda más constante durante todo el año.
Resort Hotel experimenta picos de demanda durante el verano, posiblemente reflejando su función como destino vacacional.
### Reservas por mes
Este gráfico es una gráfica de líneas que muestra la cantidad de llegadas por mes, proporcionando una visión clara de la evolución de las llegadas a lo largo del tiempo. 
![image](graph\M1\6.png)
Al no contar con datos completos para todos los meses de cada año (2015, 2016, y 2017), algunas tendencias pueden estar sesgadas. Por ejemplo, si no hay datos para ciertos meses en algunos años, la media de llegadas durante esos meses estará subestimada o mal representada.
- La representación de un patrón estacional basado en un conjunto de datos incompletos podría no reflejar con precisión la realidad. Las fluctuaciones observadas podrían, de hecho, ser un artefacto de los datos faltantes, en lugar de una tendencia estacional genuina.
- Al combinar datos incompletos de múltiples años, se pierde la capacidad de realizar un análisis comparativo de las tendencias de llegadas entre los años. Esto puede ocultar cambios significativos de tendencia o anomalías que podrían haber ocurrido en un año específico.

Para abordar este problema, sería ideal segmentar los datos según los años disponibles y, en primer lugar, verifica la integridad de los datos antes de realizar la sumatoria.
## Procesamiento de Datos
### Verificacion de correlacion
**Mapa de Calor**
![image](graph\M1\7.png)
`**Correlaciones Fuertes:**

- ``is_canceled`` y ``lead_time``: Hay una correlación positiva significativa (0.30) entre la tasa de cancelación y el tiempo de anticipación (lead time). Esto sugiere que las reservas realizadas con mucho tiempo de antelación son más propensas a ser canceladas.
- ``stay_in_weekend_nights`` y ``stays_in_week_nights``: Estas variables están altamente correlacionadas (0.53), lo que es esperable ya que ambas representan la duración total de la estancia, aunque medidas de diferentes formas (fines de semana y días de semana).

**Correlaciones Negativas:**

- ``is_canceled`` y ``booking_changes``: Hay una correlación negativa leve (-0.23), lo que indica que cuando se realizan cambios en la reserva, es menos probable que la reserva se cancele. Esto podría indicar decisiones más firmes o ajustes en lugar de cancelaciones.
- ``required_car_parking_spaces`` y ``is_canceled``: Existe una correlación negativa ligera (-0.20) con las cancelaciones, sugiriendo que cuando se necesita estacionamiento, hay menos cancelaciones, tal vez porque se trata de visitas más planificadas.

**Otras Correlaciones:**

- ``adr`` (Average Daily Rate) parece tener correlaciones débiles con muchas variables, lo que indica cierta independencia del precio diario respecto a las otras medidas de comportamiento de los usuarios.
- ``total_of_special_requests``: Se correlaciona positivamente con la cantidad de adultos (0.14) y niños (0.10), indicando que grupos más grandes tienden a hacer más solicitudes especiales.

Al interpretar estas correlaciones, se pueden identificar patrones de comportamiento y relaciones que pueden ser útiles para comprender la dinámica del negocio

## Modelos de Machine Learning

### ML Random Forest
Este modelo tiene como base los Árboles de Decisión, un random forest se construye a partir de múltiples árboles de decisión. Un árbol de decisión es un modelo de predicción que divide iterativamente los datos en subconjuntos basados en una serie de preguntas formuladas a partir de las variables predictoras.

Para la clasificación, cada árbol "vota" por una clase y la clase con más votos es la predicción final del modelo.

Este modelo Random Forest fue diseñado para realizar tareas de clasificación mediante el uso del lenguaje de programación Python y bibliotecas esenciales como pandas, numpy, y scikit-learn. El objetivo principal de este modelo es predecir la variable ``is_canceled``, que indica si una reserva de hotel ha sido cancelada.

**scikit-learn**

Es una biblioteca de aprendizaje automático en Python que ofrece herramientas simples y eficientes para minería de datos y análisis de datos.

Las funciones clave usadas en este caso incluyen:
- ``train_test_split``: Para dividir el conjunto de datos en entrenamiento y prueba.
- ``RandomForestClassifier``: Para crear y ajustar el modelo de Random Forest.
- ``LabelEncoder``: Para convertir columnas categóricas en valores numéricos, facilitando su uso en el modelo.
- ``accuracy_score`` y ``classification_report``: Para evaluar el rendimiento del modelo.

#### Procedimiento del modelo
- División de los Datos: l conjunto de datos se divide en conjuntos de entrenamiento y prueba utilizando ``train_test_split``. El 80% de los datos se utiliza para entrenar el modelo, y el 20% restante para evaluar su rendimiento.
- Entrenamiento del Modelo: Se instancia ``RandomForestClassifier`` con 150 estimadores y un estado aleatorio para reproducibilidad. El modelo se ajusta a los datos de entrenamiento para aprender patrones y realizar predicciones.
- Evaluación del modelo:
  - Se hacen predicciones sobre el conjunto de prueba.
  - La precisión del modelo se calcula utilizando ``accuracy_score``.
  - Se genera un informe de clasificación con métricas detalladas como precisión, exhaustividad y F1-score mediante ``classification_report``.

#### Resultados del modelo Random Forest
**Métricas del Reporte de Clasificación**

Precisión Global (Accuracy):

La precisión del modelo es del 86.5%. Esto significa que, en promedio, el modelo fue capaz de hacer predicciones correctas el 86.5% del tiempo en el conjunto de prueba.

Desempeño por Clase:

| Clase                     | Métrica       | Valor | Descripción                                                                                   |
|---------------------------|---------------|-------|-----------------------------------------------------------------------------------------------|
| **Clase 0 (No se canceló)** | Precisión    | 0.87  | El 87% de las reservas predichas como no canceladas efectivamente no se cancelaron.           |
|                           | Exhaustividad | 0.93  | De todas las reservas que realmente no se cancelaron, el modelo detectó correctamente el 93%. |
|                           | F1-Score      | 0.90  | Media armónica de la precisión y el recall, sugiriendo un buen equilibrio entre ambos.        |
| **Clase 1 (Cancelada)**    | Precisión    | 0.86  | El 86% de las reservas predichas como canceladas efectivamente fueron canceladas.             |
|                           | Exhaustividad | 0.76  | De todas las reservas que realmente fueron canceladas, el modelo detectó correctamente el 76%.|
|                           | F1-Score      | 0.81  | Indica un menor equilibrio entre precisión y recall en comparación con la clase 0.            |


Promedios de Mets específicas (Macro y Weighted Averages):

- Macro Avg: Calcula la media de precisión, recall, y F1-score sin tener en cuenta el balance o desbalance entre clases. Aquí, las puntuaciones son 0.86 para precisión, 0.84 para recall y 0.85 para F1, indicando que en promedio las métricas por clase son bastante buenas.

- Weighted Avg: Estos son promedios ponderados por el número de instancias presentes en cada clase. Precisamente, la precisión ponderada es más alta (0.87), lo que refleja una distribución de datos sesgada hacia la clase 0 (que tiene más instancias).

El modelo de Random Forest se desempeña bien, especialmente para predecir las reservas que no se cancelaron (Clase 0), tal como se indica por el alto recall de 0.93.

Sin embargo, aunque la precisión para la clase de cancelaciones es decente (0.86), el recall es más bajo para esta clase, lo que significa que el modelo puede no detectar algunas cancelaciones correctamente.

Dada la precisión global del 86.5%, el modelo es adecuado para tareas de predicción.

### ML XG Boost
XGBoost (Extreme Gradient Boosting) es una potente biblioteca de aprendizaje automático optimizada para velocidad y rendimiento. Se basa en la técnica de boosting de gradiente para resolver problemas tanto de clasificación como de regresión. 

Es conocido por su capacidad para manejar complejidades de datos y estructuras del modelo, y por proporcionar resultados de alta precisión.
 
**Características clave**
- Boosting de Gradiente: Combina múltiples modelos base (habitualmente árboles de decisión) para mejorar la precisión del modelo a través de un enfoque secuencial, donde se corrige el error del modelo previo.
- Regularización: Integra métodos de regularización como L1 (Lasso) y L2 (Ridge), lo cual ayuda a prevenir el problema de sobreajuste y a mejorar la capacidad de generalización.
- Eficiente y Escalable: Optimizado para velocidad, su implementación es eficiente al utilizar optimizaciones de hardware y algoritmos de aprendizaje paralelo.
- Flexibilidad: Compatible con clasificación, regresión, ranking de usuarios y problemas más complejos en aprendizaje automático.

**XGBoost Library y scikit-learn**
- ``XGBClassifier``: Utilizado para tareas de clasificación con XGBoost. La configuración utiliza ``gbtree`` como el potenciador (booster) y configura distintos hiperparámetros como ``n_estimators`` y ``max_depth`` para ajustar el modelo.
- ``accuracy_score`` y ``classification_report``: Para evaluar el rendimiento, ayudando a extraer métricas como precisión, recall, F1-score y exactitud global.
- La lógica de preprocesamiento del conjunto de datos y su división en conjuntos de entrenamiento y prueba es paralela a la usada en el modelo de Random Forest

#### Procedimiento del modelo
- El uso de ``XGBClassifier`` implica definir parámetros clave:
  - ``booster = 'gbtree'``: Utiliza árboles de decisión como base del modelo.
  - ``n_estimators = 300``: Especifica el número de árboles en el modelo.
  - ``max_depth = 5``: Establece la máxima profundidad de cada árbol, controlando su complejidad.
  - ``random_state=3``: Asegura la reproducibilidad de los resultados.
- Entrenamiento:
El modelo es ajustado usando los datos de entrenamiento (``X_train``, ``y_train``), aprendiendo a optimizar la predicción de cancelaciones.
- Predicción y Evaluación: Predicciones en el conjunto de prueba (``X_test``) para evaluar la precisión de las predicciones con ``accuracy_score``.
``classification_report`` proporciona un análisis detallado del rendimiento, con métricas de precisión, exhaustividad y F1-score.

**Resultados del modelo XG Boost**
- Precisión Global (Accuracy):

El modelo XGBoost alcanzó una precisión del 84.35%. Esto indica que el modelo predijo correctamente el 84.35% de las observaciones en el conjunto de prueba.
- Desempeño por Clase:

  Clase 0 (Reservas no canceladas):
Precisión: 0.84, lo que significa que el 84% de las predicciones de reservas como no canceladas fueron correctas.
Exhaustividad (Recall): 0.92, indicando que el modelo detectó el 92% de las reservas realmente no canceladas.
F1-Score: 0.88, mostrando un buen equilibrio entre precisión y exhaustividad.

  Clase 1 (Reservas canceladas):
  - Precisión: 0.84, con el 84% de las reservas predichas como canceladas siendo correctas.
  - Exhaustividad (Recall): 0.71, indicando que el modelo identificó el 71% de las reservas que realmente fueron canceladas.
  - F1-Score: 0.77, lo que refleja que hay espacio para mejorar el balance de precisión y recall.
- Promedios de Mets específicas (Macro y Weighted Averages):

  - Macro Avg: Proporciones de 0.84 para precisión, 0.82 para recall, y 0.83 para F1-Score.

  - Weighted Avg: Resultados de 0.84 en precisión, recall, y F1-Score ponderado por el número de instancias.

## Comparación del Modelo Random Forest y XG Boost
1. Precisión General:

El Random Forest logró una precisión del 86.5%, superior al 84.35% de XGBoost, sugiriendo que Random Forest tiene una ligera ventaja en precisión global.

2. Clase 0 (No canceladas):

Ambos modelos tienen desempeños similares en precisión para esta clase, pero Random Forest tuvo un F1-Score más alto (0.90) comparado con XGBoost (0.88).

3. Clase 1 (Canceladas):

Random Forest muestra un mejor recall para la clase de cancelaciones (0.76) frente a XGBoost (0.71), lo cual indica que Random Forest es superior en identificar cancelaciones.

4. Promedios:

En general, Random Forest ha mostrado mejores resultados en ambos macro y weighted averages, lo que indica un rendimiento más consistente en las dos clases.