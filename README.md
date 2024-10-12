# Apache Spark y Kafka - Proyecto de Procesamiento de Datos en Tiempo Real - BIG DATA TAREA-3

## Descripción

Este proyecto implementa un sistema de procesamiento de datos en tiempo real utilizando Apache Kafka y Apache Spark. Se configura un topic en Kafka que simula la llegada de datos, y Spark se utiliza para consumir estos datos y realizar análisis en tiempo real. Los resultados del procesamiento se visualizan en la consola.

### Características

- Generación de datos simulados y envío a un topic de Kafka.
- Consumo de datos en tiempo real utilizando Spark Streaming.
- Análisis y procesamiento de datos para contar eventos y calcular estadísticas.
- Visualización de resultados en la consola.

## Instrucciones para la Ejecución

### 1. Configuración del Entorno

1. **Instalar Java**: Asegúrate de que Java esté instalado. Puedes verificar la instalación ejecutando:
   ```bash
   java -version
#  Generador de Datos generator.py
El script `generator.py` tiene como objetivo simular la llegada de datos en tiempo real al topic de Kafka. A continuación se describe su funcionalidad principal:

1. **Simulación de Datos**: Genera datos aleatorios en un bucle continuo, creando un flujo constante de información que puede ser consumida por aplicaciones de análisis en tiempo real.

2. **Configuración del Productor de Kafka**: Establece una conexión con un broker de Kafka, permitiendo el envío de mensajes a un topic específico.

3. **Generación de Mensajes**:
   - Cada mensaje puede incluir un identificador único y varios atributos aleatorios, como nombres, precios o cantidades, dependiendo de los requisitos del proyecto.
   - Los datos generados representan eventos o registros que pueden ser relevantes para el análisis.

4. **Envío Periódico**: Los mensajes se envían al topic de Kafka a intervalos regulares, simulando una carga de trabajo realista que podría encontrarse en aplicaciones del mundo real.

5. **Flexibilidad**: El script se puede modificar fácilmente para generar diferentes tipos de datos, adaptándose a diversas necesidades de análisis y pruebas.

Este generador es fundamental para probar y validar la implementación de aplicaciones de streaming en Apache Spark y Kafka, proporcionando un flujo constante de datos que se puede consumir y analizar en tiempo real.

## Consumer de Spark consumer_spark.py

El script `consumer_spark.py` se encarga de consumir los datos generados en tiempo real desde un topic de Kafka y realizar procesamiento sobre esos datos. A continuación se describe su funcionalidad principal:

1. **Conexión a Kafka**: Se establece una conexión con el broker de Kafka y se suscribe a un topic específico donde se están enviando los datos generados por el script generador.

2. **Configuración del Streaming Context**: Crea un contexto de streaming de Apache Spark que permite el procesamiento de datos en tiempo real, facilitando la ingestión y análisis de flujos de datos.

3. **Consumo de Datos**:
   - El consumer recibe datos en micro-batches desde el topic de Kafka, lo que permite un procesamiento eficiente y escalable.
   - Los datos son transformados y preparados para el análisis.

4. **Procesamiento de Datos**:
   - Se pueden realizar diversas operaciones sobre los datos consumidos, como conteo de eventos, cálculos estadísticos y agregaciones.
   - Los resultados del procesamiento pueden ser utilizados para generar informes o tomar decisiones informadas en tiempo real.

5. **Visualización en Consola**: Los resultados del análisis se muestran en la consola de Spark, permitiendo observar en tiempo real las métricas calculadas, como el conteo de eventos y otras estadísticas relevantes.

Este consumer es esencial para la aplicación de streaming en el proyecto, permitiendo la transformación y análisis de datos en tiempo real, lo que es crucial para obtener insights inmediatos a partir de la información generada.

##  Archivo de Eliminación de Registros (`delete_records.py`)

El script `delete_records.py` se utiliza para eliminar registros específicos de un topic tarea 3 en Kafka. Su funcionalidad incluye:

1. **Configuración de Kafka**: Se establece una conexión con el broker de Kafka y se define el topic del cual se desea eliminar los registros.

2. **Definición de los Registros a Eliminar**: Se determina qué registros o mensajes deben ser eliminados. Esto puede hacerse especificando claves o criterios específicos para identificar los mensajes en el topic.

3. **Eliminación de Registros**:
   - Utiliza la API de Kafka para enviar solicitudes de eliminación de mensajes basadas en los criterios definidos.
   - Puede incluir la eliminación de registros en función de un rango de offsets, claves específicas o cualquier otro criterio aplicable según la lógica del negocio.

4. **Confirmación de Eliminación**: El script proporciona retroalimentación sobre el éxito o fracaso de las operaciones de eliminación, lo que permite verificar que los registros no deseados han sido efectivamente eliminados del topic.

5. **Uso en Mantenimiento**: Este script es útil para mantener la integridad y relevancia de los datos en el topic, permitiendo la eliminación de información obsoleta o incorrecta.

El script de eliminación de registros es una herramienta fundamental para gestionar los datos en Kafka, asegurando que solo se conserven los mensajes relevantes y útiles para el análisis y procesamiento posterior.
