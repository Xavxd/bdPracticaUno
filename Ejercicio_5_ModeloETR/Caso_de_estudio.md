# Caso de Estudio: Sistema de Base de Datos para "StreamVerse"

## 1. Identificación del Problema
La plataforma ficticia de streaming **StreamVerse** enfrenta fallas críticas en el seguimiento de usuarios, la gestión de suscripciones y el control de la reproducción de contenido debido al uso de archivos aislados e ineficientes. 

Para solucionar esto, se requiere el diseño de una **base de datos relacional** que permita gestionar de forma óptima:
* Usuarios y perfiles
* Planes de suscripción y pagos
* Catálogo multimedia (películas, series y episodios)
* Historial de reproducción en tiempo real

---

## 2. Descripción de la Problemática y Entrevista Simulada

### Descripción
StreamVerse necesita organizar su operación central con urgencia para cumplir con los siguientes objetivos de negocio:
* Validar qué usuarios tienen un pago activo.
* Controlar los límites de perfiles permitidos por cada cuenta.
* Recomendar contenido personalizado según el historial del usuario.
* Generar reportes analíticos de consumo para la toma de decisiones.

### Entrevista con el Cliente (CEO de StreamVerse)
* **Consultor:** ¿Qué información clave necesita almacenar el sistema?
  * **Cliente:** Necesitamos registrar a los usuarios con su correo y contraseña, sus planes de pago (Básico, Estándar, Premium), los perfiles asociados a cada cuenta y el catálogo de películas y series con sus episodios, géneros y actores. También queremos guardar qué contenido ve cada perfil y en qué minuto se quedó.
* **Consultor:** ¿Con qué frecuencia se consulta esta información?
  * **Cliente:** El catálogo y el historial se consultan en tiempo real miles de veces por segundo. La validación de pagos y planes se realiza en cada inicio de sesión o al intentar reproducir contenido.
* **Consultor:** ¿Qué reportes o métricas requieren para la toma de decisiones?
  * **Cliente:** Queremos reportes de los contenidos más vistos del mes por género, ingresos mensuales por tipo de suscripción y tasa de retención de usuarios.

---

## 3. Documentación de Requerimientos

### Lista de Datos a Guardar (Entidades y Atributos)

#### Gestión de Accesos y Cuenta
* **Usuario:** ID, correo electrónico, contraseña (hash), fecha de registro.
* **Perfil:** ID, nombre, edad, clasificación (infantil/adulto).

#### Planes y Facturación
* **Suscripción:** ID, nombre del plan (Básico, Estándar, Premium), precio, límite de perfiles, duración.
* **Pago:** ID, fecha, monto, método de pago, estado (completado, pendiente, fallido).

#### Catálogo Multimedia
* **Contenido (General):** ID, título, descripción, año de estreno, clasificación por edad.
* **Película:** (Hereda de Contenido) Duración.
* **Serie:** (Hereda de Contenido) Temporadas totales.
* **Episodio:** ID, título, número de temporada, número de episodio, duración.
* **Género:** ID, nombre del género.
* **Actor:** ID, nombre completo.

#### Actividad
* **Historial de Reproducción:** ID, fecha/hora, minuto de pausa, completado (sí/no).

### Requerimientos Funcionales del Sistema
1. **Autenticación:** Permitir el registro seguro y el inicio de sesión de los usuarios.
2. **Control de Suscripciones:** Asociar un plan de suscripción activo y vigente a cada usuario.
3. **Multiperfil:** Crear y limitar múltiples perfiles bajo una misma cuenta de usuario según las reglas de su plan.
4. **Navegación:** Buscar y filtrar el catálogo multimedia por género, tipo de contenido (película/serie) y clasificación.
5. **Progreso de Carga:** Guardar el estado exacto de la reproducción por perfil para permitir la reanudación del contenido más tarde.
6. **Módulo Analítico:** Generar reportes automatizados de consumo de contenidos, métricas de retención e ingresos mensuales financieros.
