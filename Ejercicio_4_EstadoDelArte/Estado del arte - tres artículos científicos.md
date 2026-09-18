Artículo 1: Bases de datos vectoriales e Inteligencia Artificial

**Cita en formato APA (7.ª edición):** Li, G., & Chao, Z. (2024). *Vector database management techniques and systems*. Proceedings of the ACM SIGMOD International Conference on Management of Data, 2024, 4325–4330. doi.org

**Problema que aborda:** El crecimiento exponencial de los modelos de lenguaje a gran escala (LLMs) y la IA generativa ha creado la necesidad urgente de almacenar y consultar de manera eficiente colecciones masivas de embeddings vectoriales de alta dimensionalidad, una tarea en la que los sistemas relacionales tradicionales fallan debido a problemas de escalabilidad y latencia en búsquedas de vecinos más cercanos (ANN).

**Método o propuesta:** Los autores presentan un análisis técnico integral de las estructuras de indexación basadas en grafos, cuantificación y árboles empleadas en los sistemas de gestión de bases de datos vectoriales modernos (VDBMS), evaluando las optimizaciones de hardware y algoritmos de recuperación híbrida.

**Resultado principal:** Se demuestra que la integración de índices de grafos de proximidad con filtrado de metadatos estructurados reduce la latencia de consulta en más del 40% en comparación con métodos tradicionales de búsqueda lineal, garantizando una alta precisión en sistemas de generación aumentada por recuperación (RAG).

**Relación con la Unidad Temática I:** Se vincula directamente con la evolución de los modelos de datos, extendiendo el paradigma clásico hacia estructuras complejas de tipo vectorial diseñadas para datos no estructurados en entornos analíticos modernos.

**Aporte al proyecto de curso:** (Completar según tu proyecto. Ejemplo: Aporta una base conceptual sólida para justificar por qué nuestro sistema requerirá un almacenamiento indexado mediante embeddings si decidimos incorporar un módulo de búsqueda semántica en la aplicación).


Artículo 2: Procesamiento Híbrido Transaccional/Analítico (HTAP)

**Cita en formato APA (7.ª edición):** Li, G., & Zhang, C. (2025). Hybrid transactional/analytical processing databases: A comprehensive tutorial. IEEE International Conference on Data Engineering (ICDE), 2025, 1205–1212. doi.org

**Problema que aborda:** Tradicionalmente, las empresas separan sus datos en sistemas transaccionales (OLTP) y analíticos (OLAP), lo que genera retrasos críticos por procesos de extracción, transformación y carga (ETL), impidiendo la toma de decisiones en tiempo real sobre flujos de datos operativos vivos.

**Método o propuesta:** Se propone un marco de diseño para bases de datos HTAP que unifica el almacenamiento en memoria utilizando formatos de almacenamiento híbridos (por filas y columnas simultáneamente) respaldados por mecanismos avanzados de control de concurrencia y aislamiento de recursos.

**Resultado principal:** El enfoque integrado elimina por completo la necesidad de canalizaciones ETL externas, manteniendo un rendimiento transaccional óptimo sin que las consultas analíticas pesadas degraden el rendimiento operativo global de la base de datos.

**Relación con la Unidad Temática I:** Se relaciona con las arquitecturas de los Sistemas de Gestión de Bases de Datos (SGBD) y la consistencia de los datos, redefiniendo las fronteras tradicionales entre el almacenamiento orientado a la eficiencia transaccional y el procesamiento analítico.

**Aporte al proyecto de curso:** (Completar según tu proyecto. Ejemplo: Nos ayuda a diseñar la arquitectura del backend para procesar los pedidos de los usuarios y generar reportes financieros inmediatos en la misma plataforma sin duplicar la infraestructura).