**Qué es un contenedor y en qué se diferencia de una máquina virtual, en términos de arranque, tamaño y aislamiento.**



Un contenedor es una unidad estándar de software que empaqueta el código de una aplicación junto con todas sus dependencias (librerías, configuraciones y binarios) para asegurar que se ejecute de manera rápida y confiable en cualquier entorno informático. A diferencia de las soluciones tradicionales, los contenedores realizan una virtualización a nivel del sistema operativo (OS) compartiendo el núcleo (kernel) del host, en lugar de simular hardware físico.



Defina: imagen, contenedor, volumen y puerto publicado.

•	Imagen: Es una plantilla inmutable de solo lectura que funciona como el plano de diseño básico. Contiene las instrucciones exactas y archivos necesarios para dar vida a un contenedor.

•	Contenedor: Es la instancia ejecutable, viva y en tiempo real de una imagen. Añade una capa de lectura y escritura por encima de la imagen original.

•	Volumen: Mecanismo de almacenamiento persistente administrado por el motor de contenedores que extrae y resguarda los datos fuera de la estructura volátil del contenedor.

•	Puerto publicado: Configuración de red que mapea o enlaza un puerto del contenedor hacia un puerto físico del host, permitiendo la comunicación con el exterior.



**Importancia del Volumen y Riesgos de Omisión**



Los contenedores son efímeros y no persistentes por naturaleza. Cuando un contenedor genera datos (como transacciones o registros de bases de datos), la información se almacena en una capa superior de escritura temporal propia del contenedor.

Si no se declara un volumen, la consecuencia exacta es la destrucción permanente e irrecuperable de los datos en el momento en que el contenedor se detiene y se elimina (docker rm). Declarar un volumen es indispensable para separar el ciclo de vida de los datos del ciclo de vida de la aplicación.



**Citas bibliográficas**



What is a Container? (2025). Retrieved from https://www.docker.com/resources/what-container/



Containers vs. VMs: Why not both? (2026). Retrieved from https://www.redhat.com/en/topics/containers/containers-vs-vms



Docker Inc. (2026). Volumes. Retrieved from https://docs.docker.com/engine/storage/volumes/