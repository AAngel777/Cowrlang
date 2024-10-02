
Asciinema
https://asciinema.org/a/oNPkA9j6WGa0zchPVNgK7DMgx

Preguntas 
Fundamentos de Erlang
1. ¿Qué características de Erlang lo hacen adecuado para aplicaciones de alta concurrencia y escalabilidad?

Erlang es ideal para aplicaciones de alta concurrencia y escalabilidad por las siguientes razones:

Modelo de procesos ligeros: Los procesos en Erlang son extremadamente livianos en comparación con los hilos del sistema operativo. Permiten la creación y administración de millones de procesos sin un impacto significativo en el rendimiento.
Concurrencia nativa: Erlang está diseñado para manejar procesos concurrentes y distribuidos de forma eficiente. La comunicación entre procesos se realiza de manera asíncrona mediante el paso de mensajes, lo que minimiza los bloqueos.
Tolerancia a fallos: Erlang permite el desarrollo de sistemas tolerantes a fallos mediante el uso de supervisores, los cuales reinician procesos fallidos sin detener el sistema completo.
Distribución fácil: Permite que sistemas distribuidos se comuniquen de manera transparente, escalando horizontalmente en múltiples nodos.
2. Explica el modelo de actores en Erlang y cómo se aplica en la gestión de procesos concurrentes.

El modelo de actores en Erlang establece que:

Todo en el sistema es un actor (proceso independiente).
Los actores no comparten memoria, lo que evita conflictos por condiciones de carrera.
Se comunican exclusivamente mediante mensajería asíncrona. Cada proceso tiene una bandeja de entrada de mensajes (mailbox) y usa funciones como receive para procesar mensajes.
Esto simplifica la concurrencia, ya que no hay necesidad de mecanismos de sincronización como locks o semáforos. Los procesos se pueden crear y destruir dinámicamente, permitiendo que Erlang administre millones de procesos concurrentes.

Características de Cowboy
3. ¿Cuáles son las principales ventajas de usar Cowboy como servidor HTTP en aplicaciones Erlang?

Las ventajas clave de Cowboy incluyen:

Ligereza y eficiencia: Cowboy es un servidor HTTP minimalista que está diseñado para ser rápido y eficiente, ideal para aplicaciones con requisitos de alto rendimiento.
Soporte de protocolos: Cowboy soporta HTTP, HTTP/2, y WebSockets de manera nativa, lo que lo hace flexible para diferentes tipos de aplicaciones web.
Concurrencia nativa: Como está basado en Erlang, Cowboy hereda su capacidad para manejar miles de conexiones concurrentes de manera eficiente.
Escalabilidad: Puede escalar fácilmente para manejar grandes volúmenes de tráfico, especialmente en aplicaciones distribuidas.
4. Describe cómo Cowboy maneja las conexiones concurrentes de manera eficiente.

Cowboy maneja conexiones concurrentes utilizando procesos Erlang individuales para cada conexión. Cada solicitud HTTP es atendida por un proceso, lo que significa que el servidor puede manejar muchas conexiones de manera simultánea sin bloquear otras solicitudes. Gracias a la gestión liviana de procesos y el modelo de actores de Erlang, esto se hace de manera eficiente sin necesidad de hilos de sistema pesado o multiplexación compleja.

