# Investigación: Conceptos Fundamentales de Sistemas de Bases de Datos

## 1. Dato, Información y Base de Datos

En el ámbito de la ciencia de la computación, existe una jerarquía conceptual clara entre dato, información y base de datos:

* **Dato:** Es una representación simbólica (numérica, alfabética, algorítmica) elemental y no estructurada de un atributo o variable, sin contexto ni significado intrínseco por sí mismo (Silberschatz et al., 2020).
* **Información:** Es el conjunto de datos procesados, contextualizados y organizados de manera que adquieren significado, utilidad y valor para la toma de decisiones (Elmasri & Navathe, 2015).
* **Base de Datos:** Es una colección organizada e integrada de datos relacionados lógicamente, diseñada para ser compartida por múltiples usuarios y aplicaciones de forma eficiente y segura (Date, 2004).

### Comparativa de Definiciones Formales

| Autor / Fuente | Definición Formal | Análisis y Énfasis |
| :--- | :--- | :--- |
| **Silberschatz, Korth y Sudarshan (2020)** | *"Una base de datos es una colección de datos interrelacionados y un conjunto de programas para acceder a esos datos."* | Enfatiza el carácter práctico e integrado del sistema completo de almacenamiento y recuperación. |
| **Date (2004)** | *"Una base de datos es una colección de datos persistentes que son utilizados por los sistemas de aplicación de una empresa dada."* | Hace especial hincapié en la **persistencia** de los datos y su orientación operativa al entorno institucional. |
| **Madden / MIT OpenCourseWare (2010)** | *"Un sistema de gestión de bases de datos es un software estructurado diseñado para proporcionar un almacenamiento declarativo, consistente y de alto rendimiento sobre un volumen masivo de datos compartidos."* | Destaca la **consistencia, las garantías ACID y la abstracción declarativa** del acceso a la información. |

---

## 2. Características Principales de una Base de Datos

* **Integración:** La información se centraliza lógicamente, eliminando fronteras entre datos pertenecientes a diferentes áreas de una organización.
* **Persistencia:** Los datos permanecen almacenados de forma permanente en medios no volátiles hasta que son modificados o eliminados explícitamente (Date, 2004).
* **Redundancia Controlada:** Se minimiza la duplicación innecesaria de información mediante técnicas de normalización, manteniendo redundancias estrictamente necesarias para el rendimiento o la integridad (Elmasri & Navathe, 2015).
* **Integridad:** Reglas y restricciones de validación (claves primarias, foráneas, valores únicos) que garantizan que los datos almacenados sean correctos y coherentes.
* **Independencia de Datos:** Capacidad de modificar la estructura física o lógica de almacenamiento sin afectar las aplicaciones que consumen los datos (Silberschatz et al., 2020).
* **Seguridad y Control de Acceso:** Mecanismos de autenticación y autorización que protegen la información confidencial de accesos no autorizados.
* **Concurrencia:** Permite que múltiples usuarios y procesos accedan y modifiquen la base de datos simultáneamente sin generar conflictos ni inconsistencias.
* **Recuperación:** Capacidad del sistema para restaurar el estado consistente de la base de datos ante fallos de hardware, software o cortes de energía mediante registros de transacciones (*logs*).

---

## 3. Archivos Tradicionales frente a Bases de Datos

Antes de los Sistemas Gestores de Bases de Datos (SGBD), el almacenamiento se realizaba mediante **sistemas de archivos del sistema operativo**. Este enfoque tradicional presentó serias limitaciones:

* **Redundancia e Inconsistencia:** Cada aplicación mantenía sus propios archivos, lo que derivaba en datos duplicados en distintos formatos y ubicaciones. La actualización en un archivo no se reflejaba en los demás, generando **inconsistencia** (Silberschatz et al., 2020).
* **Dependencia Programa-Datos:** La estructura de almacenamiento físico estaba codificada directamente dentro de los programas de aplicación. Si el formato del archivo cambiaba, se requería reescribir todo el código fuente del software.
* **Aislamiento de Datos y Dificultad de Acceso:** Extraer nueva información requería programar scripts a medida para cada consulta.

**Origen de los SGBD:** Estas deficiencias impulsaron a investigadores como Edgar F. Codd en IBM y Charles Bachman en ACM a formular el modelo relacional y la arquitectura de gestión centralizada, dando origen a los SGBD modernos para desacoplar el almacenamiento físico de la lógica de negocio (Codd, 1970).

---

## 4. Usuarios de una Base de Datos: Roles, Responsabilidades y Permisos

* **Diseñador de la Base de Datos:**
  * *Responsabilidad:* Identificar los datos que se deben almacenar, elegir las estructuras adecuadas, definir relaciones y aplicar normas de normalización.
  * *Permisos:* Altos privilegios en etapas de desarrollo; permisos de creación de esquemas (`CREATE`, `ALTER`).
* **Administrador de la Base de Datos (DBA):**
  * *Responsabilidad:* Garantizar la disponibilidad, rendimiento, respaldos, afinamiento (*tuning*) y seguridad global del sistema.
  * *Permisos:* Permisos administrativos totales (`SUPERUSER`, `GRANT`, `REVOKE`, gestión de almacenamiento físico).
* **Programador de Aplicaciones:**
  * *Responsabilidad:* Desarrollar la lógica de aplicaciones que interactúan con la base de datos mediante comandos DML o APIs.
  * *Permisos:* Accesos restringidos en entornos de producción (lectura/escritura en tablas específicas a través de vistas o procedimientos almacenados).
* **Usuario Final:**
  * *Responsabilidad:* Consumir la información o ingresar datos mediante interfaces de usuario (formularios, dashboards).
  * *Permisos:* Mínimos privilegios indispensables (generalmente definidos dentro de la capa del software de aplicación).

---

## 5. Ciclo de Vida de una Base de Datos

El desarrollo de un sistema de bases de datos sigue una metodología por etapas estructuradas (Elmasri & Navathe, 2015):

1. **Planificación y Definición del Sistema:**
   * *Descripción:* Identificación de metas, alcance, recursos y límites del sistema.
   * *Entregable:* Documento de especificación de requerimientos y estudio de factibilidad.
2. **Análisis de Requerimientos:**
   * *Descripción:* Recopilación de las necesidades de información de los usuarios clave de la organización.
   * *Entregable:* Documento formal de requisitos de datos e interacciones.
3. **Diseño de la Base de Datos:**
   * *Descripción:* Creación del modelo conceptual, lógico (normalizado) y físico (optimizado para un SGBD específico).
   * *Entregable:* Diagramas Entidad-Relación (DER), esquema relacional y diccionario de datos.
4. **Selección del SGBD (si aplica):**
   * *Descripción:* Evaluación técnica y económica del motor de base de datos más conveniente.
   * *Entregable:* Reporte de evaluación técnico-económica y contrato/licencia del SGBD.
5. **Implementación y Carga de Datos:**
   * *Descripción:* Creación de las estructuras físicas (`CREATE TABLE`) y migración/poblado de datos iniciales.
   * *Entregable:* Scripts SQL de despliegue y base de datos inicial operada.
6. **Pruebas y Validación:**
   * *Descripción:* Verificación de la integridad, seguridad, rendimiento y corrección de las consultas.
   * *Entregable:* Reporte de pruebas de estrés, rendimiento y aceptación de usuario.
7. **Operación y Mantenimiento:**
   * *Descripción:* Monitoreo continuo, respaldos, parches de seguridad y ajustes de rendimiento en producción.
   * *Entregable:* Bitácoras de mantenimiento y planes de recuperación ante desastres (DRP).

---

## 6. Sistema Gestor de Bases de Datos (SGBD)

Un **SGBD** (o DBMS por sus siglas en inglés) es el paquete de software que actúa como interfaz entre la base de datos física, los usuarios y las aplicaciones.

### Módulos Componentes
* **Gestor de Almacenamiento:** Módulo encargado de la interfaz entre los datos de bajo nivel almacenados en disco y las aplicaciones.
* **Procesador de Consultas:** Traduce, optimiza y ejecuta instrucciones escritas en lenguajes de alto nivel (como SQL) en operaciones de bajo nivel.
* **Gestor de Transacciones:** Garantiza que las operaciones cumplan las propiedades ACID (Atomicidad, Consistencia, Aislamiento y Durabilidad).

### Clasificación de Lenguajes SQL

* **DDL (Data Definition Language):** Define y modifica la estructura de los objetos de la base de datos.
  * *Comandos:* `CREATE`, `ALTER`, `DROP`, `TRUNCATE`.
* **DML (Data Manipulation Language):** Permite a los usuarios manipular o consultar los datos almacenados.
  * *Comandos:* `SELECT`, `INSERT`, `UPDATE`, `DELETE`.
* **DCL (Data Control Language):** Administra permisos y derechos de acceso sobre los objetos.
  * *Comandos:* `GRANT`, `REVOKE`.
* **Control de Transacciones (TCL):** Gestiona los cambios realizados por las sentencias DML para asegurar consistencia.
  * *Comandos:* `COMMIT`, `ROLLBACK`, `SAVEPOINT`.

### Clasificación de los SGBD
* **Por Modelo de Datos:** Relacionales (RDBMS), NoSQL (Documentales, Clave-Valor, Orientados a Grafos, Columnares), Orientados a Objetos, Multidimensionales.
* **Por Arquitectura de Despliegue:** Centralizados, Distribuidos, En la Nube (DBaaS).

---

## 7. Sistema de Base de Datos: Arquitecturas e Independencia

### Arquitectura de Tres Niveles (ANSI/SPARC)

La arquitectura ANSI/SPARC define tres niveles de abstracción para lograr la separación entre aplicaciones e información física:

1. **Nivel Externo (Vistas):** Define cómo ven los datos los distintos usuarios finales (vistas personalizadas).
2. **Nivel Conceptual (Esquema Lógico):** Describe qué datos están almacenados y qué relaciones existen entre ellos para toda la organización.
3. **Nivel Interno (Esquema Físico):** Describe cómo se almacenan físicamente los datos en los discos (estructuras de archivos, índices, bloques).  


### Tipos de Independencia de Datos
* **Independencia Física de Datos:** Capacidad de modificar el esquema interno (ej. crear un índice o cambiar discos) sin alterar el esquema conceptual ni las aplicaciones.
* **Independencia Lógica de Datos:** Capacidad de modificar el esquema conceptual (ej. añadir un atributo) sin necesidad de reestructurar las vistas externas ni los programas de aplicación existentes.

### Arquitecturas de Sistemas de Bases de Datos
* **Centralizada:** El SGBD, la base de datos y la interfaz se ejecutan en una sola máquina física de gran rendimiento.
* **Cliente-Servidor:**
  * *2 Capas:* El cliente ejecuta la interfaz de usuario y la lógica de negocio, comunicándose directamente con el servidor de base de datos vía SQL.
  * *3 Capas (o N-Capas):* Un servidor web/aplicaciones procesa la lógica de negocio, desacoplando completamente al cliente ligero del servidor de base de datos.

---

## 8. Modelos de Datos

Un **modelo de datos** es una colección de conceptos abstractos utilizados para describir la estructura, relaciones, restricciones semánticas y operaciones sobre los datos. Su importancia radica en que proporciona un lenguaje común entre desarrolladores y usuarios finales para garantizar el correcto diseño conceptual de un sistema.

### Clasificación según Nivel de Abstracción
1. **Modelos Conceptuales (Alto Nivel):** Expresan los requerimientos de la organización de forma abstracta e independiente de la tecnología (ej. Modelo Entidad-Relación).
2. **Modelos Lógicos (Nivel Medio):** Representan las estructuras de datos de forma que un SGBD específico pueda interpretarlas, abstrayendo aún los detalles de hardware (ej. Modelo Relacional).
3. **Modelos Físicos (Bajo Nivel):** Describen los detalles técnicos de almacenamiento en disco, direccionamiento e índices.

### Clasificación según la Estructura
* **Modelo Jerárquico:** Organiza los datos en una estructura tipo árbol donde un nodo padre puede tener varios nodos hijos.
* **Modelo en Red:** Permite estructuras de grafos donde un nodo hijo puede tener múltiples nodos padres.
* **Modelo Relacional:** Organiza los datos en tablas bidimensionales (relaciones) compuestas por filas (tuplas) y columnas (atributos).
* **Modelos NoSQL (No Relacionales):** Flexibles y orientados a alta disponibilidad y escalabilidad horizontal (Documentos JSON, Clave-Valor, Grafos, Columnas Anchas).

---

## Referencias Bibliográficas (Formato APA 7.ª Edición)

* Codd, E. F. (1970). A relational model of data for large shared data banks. *Communications of the ACM*, 13(6), 377–387. https://doi.org/10.1145/362384.362685
* Date, C. J. (2004). *An introduction to database systems* (8th ed.). Pearson Addison-Wesley.
* Elmasri, R., & Navathe, S. B. (2015). *Fundamentals of database systems* (7th ed.). Pearson.
* Hellerstein, J. M., Stonebraker, M., & Hamilton, J. (2007). Architecture of a database system. *Foundations and Trends in Databases*, 1(2), 141–259. https://doi.org/10.1561/1900000002
* Madden, S. (2010). *6.830 Database Systems: Course Introduction and Overview*. MIT OpenCourseWare, Massachusetts Institute of Technology. https://ocw.mit.edu
* Silberschatz, A., Korth, H. F., & Sudarshan, S. (2020). *Database system concepts* (7th ed.). McGraw-Hill Education.