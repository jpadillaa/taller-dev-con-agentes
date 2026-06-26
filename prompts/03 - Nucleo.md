<!--
Este prompt está pensado para en cualquier chatbot
-->
# Rol
Eres un experto en núcleos de emulación de SNES y conoces sus características técnicas, licencias, estado de mantenimiento y opciones de integración.

# Contexto
Desarrollo una aplicación de escritorio en Python que actúa como capa superior de un emulador de SNES. La aplicación no implementa la emulación, usa un núcleo existente. Necesito elegir el núcleo más adecuado antes de empezar, porque esa decisión condiciona la arquitectura y la estrategia de integración.

# Verificación de datos
Esta comparación depende de información que cambia con el tiempo, como versiones, actividad del repositorio y estado de mantenimiento. Si dispones de acceso a la web, verifica estos datos en fuentes oficiales antes de responder. Si no dispones de acceso, indícalo de forma explícita, señala qué afirmaciones provienen de tu conocimiento interno y podrían estar desactualizadas, y recomienda qué conviene reverificar.

# Tarea
Revisa y compara los principales núcleos de emulación de SNES que cumplan estos requisitos:
- Gratuitos.
- De código abierto cuando sea posible.
- Disponibles para macOS y Windows.
- Activos o razonablemente mantenidos.
- Integrables desde una aplicación en Python.

Presenta varias alternativas relevantes, no solo el núcleo más conocido.

# Ficha por núcleo
Para cada uno describe nombre, sitio oficial, repositorio oficial, rendimiento, facilidad de integración con Python, forma de integración recomendada (biblioteca compartida, API, proceso externo, Libretro u otra), ventajas, desventajas y casos de uso recomendados.

# Tabla comparativa
Incluye al menos estos criterios, un núcleo por columna: licencia, rendimiento, facilidad de integración, documentación, compatibilidad con macOS, compatibilidad con Windows e integración con Python.

# Recomendación técnica
1. Clasifica los núcleos del más al menos recomendable para este proyecto, justificando cada posición.
2. Indica cuál elegirías para una aplicación moderna en Python.
3. Describe cómo propondrías integrarlo en la arquitectura del proyecto.