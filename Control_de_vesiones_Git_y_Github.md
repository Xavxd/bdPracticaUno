# Control de versiones con Git y GitHub

## ¿Qué es el control de versiones?

El control de versiones es un sistema que permite registrar y administrar los
cambios realizados en los archivos de un proyecto. Permite conservar un
historial, saber quién hizo cada cambio y cuándo lo hizo, comparar versiones y
recuperar una versión anterior cuando sea necesario.

## ¿Qué problema resuelve?

Sin control de versiones, los equipos pueden perder trabajo, sobrescribir los
cambios de otras personas o crear archivos como `proyecto-final`,
`proyecto-final-2` y `proyecto-final-definitivo`. El control de versiones
resuelve estos problemas porque:

- conserva un historial confiable de los cambios;
- permite que varias personas trabajen en el mismo proyecto;
- evita que el trabajo de un integrante sobrescriba el de otro;
- permite experimentar de forma segura mediante ramas independientes; y
- facilita revisar, combinar o deshacer cambios.

## Diferencia entre Git y GitHub

**Git** es un sistema distribuido de control de versiones que se ejecuta en
una computadora. Registra los cambios de un proyecto y ofrece comandos como
`commit`, `branch`, `merge`, `pull` y `push`. Git puede utilizarse sin conexión
a internet.

**GitHub** es una plataforma en línea que aloja repositorios de Git. Añade
funciones de colaboración como repositorios remotos, solicitudes de cambios,
revisiones de código, seguimiento de problemas, permisos y comprobaciones
automáticas.

En resumen, Git es la herramienta de control de versiones y GitHub es un
servicio que aloja proyectos Git y facilita la colaboración entre equipos.

## Conceptos importantes

### Repositorio

Un **repositorio**, o **repo**, es un proyecto administrado por Git. Contiene
los archivos del proyecto y el directorio oculto `.git`, donde se almacenan el
historial, las ramas y la configuración del proyecto. Un repositorio puede
existir de forma local, remota o en ambas.

### Commit

Un **commit** es una captura guardada de los cambios realizados en un
repositorio. Cada commit tiene un identificador, un autor, una fecha y un
mensaje que describe el cambio. Los commits deben representar unidades
pequeñas y lógicas de trabajo para que sean fáciles de entender y revisar.

Ejemplo:

```bash
git add login.js
git commit -m "Agregar validación de inicio de sesión"
```

### Branch o rama

Una **rama** es una línea independiente de desarrollo. Permite trabajar en una
funcionalidad, corrección o experimento sin modificar la rama principal
estable. Las ramas pueden crearse, compartirse y eliminarse según sea
necesario.

### Merge o fusión

Un **merge**, también llamado **fusión**, combina los cambios de una rama con
otra. Por ejemplo, después de revisar una funcionalidad, su rama puede
fusionarse con `main`. Git puede realizar la fusión automáticamente cuando los
cambios no se superponen.

### Conflicto de merge

Un **conflicto de merge** ocurre cuando Git no puede combinar los cambios de
forma segura. Normalmente sucede cuando dos ramas modifican las mismas líneas
o partes cercanas de un archivo de maneras diferentes. El desarrollador debe
revisar el archivo, elegir o reescribir el contenido correcto, eliminar las
marcas de conflicto y guardar la solución en un nuevo commit.

Las marcas de conflicto normalmente tienen esta forma:

```text
&lt;&lt;&lt;&lt;&lt;&lt;&lt; rama-actual
contenido de una rama
= = = = = = =
contenido de la otra rama
&gt;&gt;&gt;&gt;&gt;&gt;&gt; rama-funcionalidad
```

Los conflictos no son errores de Git: indican que se necesita una decisión
humana.

### Pull request

Un **pull request** (PR), o **solicitud de cambios**, es una petición para
fusionar los cambios de una rama con otra, normalmente de una rama de
funcionalidad hacia `main`. En GitHub, el pull request muestra los archivos
modificados y permite que el equipo discuta la implementación, revise el
código, ejecute comprobaciones automáticas y apruebe o rechace los cambios
antes de fusionarlos.

### `.gitignore`

El archivo **`.gitignore`** contiene una lista de archivos y directorios que
Git no debe controlar. Se utiliza normalmente para archivos generados,
dependencias, resultados de compilación, archivos del sistema, configuraciones
locales y secretos.

Ejemplo:

```gitignore
node_modules/
dist/
.env
```

Ignorar un archivo evita que se agregue accidentalmente, pero no elimina un
archivo que Git ya está controlando.

### README

Un **README** es un archivo de documentación, normalmente llamado
`README.md`, que presenta un proyecto. Generalmente explica qué hace el
proyecto, cómo instalarlo y ejecutarlo, cómo utilizarlo y dónde encontrar más
información. Un buen README ayuda a los nuevos colaboradores a comprender
rápidamente el repositorio.

## Flujo de trabajo utilizando ramas

Un flujo de trabajo común para un equipo es el siguiente:

1. Comenzar desde una rama `main` actualizada.
2. Crear una rama descriptiva para el trabajo, por ejemplo
   `feature/registro-usuarios` o `fix/fecha-invalida`.
3. Realizar los cambios en esa rama.
4. Guardar el trabajo en commits pequeños y descriptivos.
5. Subir la rama a GitHub.
6. Abrir un pull request con destino a `main`.
7. Permitir que se ejecuten las comprobaciones automáticas y que otros
   desarrolladores revisen los cambios.
8. Resolver las observaciones y los conflictos de merge, si existen.
9. Fusionar el pull request aprobado con `main`.
10. Eliminar la rama terminada cuando ya no sea necesaria.

Este flujo mantiene estable la rama `main` mientras se desarrolla el trabajo y
crea un registro claro de por qué se realizó cada cambio.

## ¿Por qué se revisa el código en parejas antes de fusionarlo?

Antes de fusionar el código, normalmente se revisa en parejas o al menos por
otro desarrollador para obtener una segunda opinión objetiva. La revisión por
pares ayuda a:

- encontrar errores y casos especiales que el autor pudo pasar por alto;
- comprobar que el código cumple los estándares del proyecto;
- mejorar la seguridad, el rendimiento y la facilidad de mantenimiento;
- confirmar que las pruebas y la documentación son suficientes;
- compartir conocimientos entre los integrantes del equipo; y
- evitar que código incompleto o sin revisar llegue a `main`.

La revisión no consiste únicamente en encontrar errores. También ayuda a
mejorar el diseño y crea una responsabilidad compartida sobre la calidad del
proyecto. Las pruebas y comprobaciones automáticas son útiles, pero la
revisión humana sigue siendo importante porque permite evaluar la intención,
la legibilidad y el impacto del código a largo plazo.