# Emulador de SNES para macOS en Python

Esta colección reúne los prompts utilizados a lo largo del ciclo de vida del proyecto, desde el diseño conceptual hasta la integración del núcleo de emulación. Cada prompt está optimizado para un destino concreto y documentado con su propósito, su modo de ejecución y los supuestos que asume.

El proyecto construye la capa de aplicación de un emulador de Super Nintendo para macOS en Python con PySide6. No implementa la emulación. Usa un núcleo externo, snes9x_libretro, integrado desde Python.
## Principios de diseño de los prompts
La colección sigue un conjunto de criterios transversales. Conviene leerlos antes de usar o adaptar cualquier prompt.

1. **Optimizar según el destino.** Para un agente de codificación se recorta todo lo que el agente ya hace por sí mismo, como leer archivos, analizar y editar. Para un prompt portable que debe rendir en cualquier herramienta se conserva el andamiaje de salida, porque es lo que hace que un modelo fuerte y uno débil produzcan el mismo resultado. Lo que se elimina nunca es la estructura, sino la redundancia.
2. **Eliminar redundancia, conservar la carga útil.** Las listas de requisitos, los mapeos y las tablas son carga útil verificable y se mantienen enteros. Las repeticiones de una misma instrucción en varias secciones se consolidan en un solo lugar.
3. **Los prompts sobre código existente requieren el código en contexto.** Si se ejecutan en un chat en lugar de un agente con acceso al proyecto, hay que pegar el contenido actual del archivo afectado.
    
## Índice de prompts
La tabla resume la colección. El orden refleja el flujo lógico de construcción, no el orden iterativo en que se redactaron.

| Fase                | Prompt                     | Destino              | Modo                 | Entregable                  |
| ------------------- | -------------------------- | -------------------- | -------------------- | --------------------------- |
| Arquitectura        | Diseño de arquitectura     | Agnóstico            | Razonamiento         | Documento técnico           |
| Arquitectura        | Artefacto web de contexto  | Render HTML          | Razonamiento         | Página de una sola vista    |
| Selección de núcleo | Comparación de núcleos     | Con verificación web | Investigación        | Comparativa y recomendación |
| Selección de núcleo | Descarga de binarios       | Con verificación web | Localización         | URLs oficiales              |
| Validación          | Demo mínimo POC            | Agente o chat        | Autónomo             | `poc.py` inicial            |
| Validación          | Primer hito jugable        | Agente o chat        | Autónomo             | `poc.py` jugable            |
| Interfaz            | Diseño UI en Stitch        | Google Stitch        | Diseño visual        | Mockup de interfaz          |
| Interfaz            | Especificación de interfaz | Agnóstico            | Razonamiento         | `descripcion_interfaz.md`   |
| Interfaz            | Implementación PySide6     | Claude Code          | Autónomo             | Aplicación de interfaz      |
| Integración         | Integración del núcleo     | Claude Code          | Puerta de aprobación | Emulador funcional          |
| Integración         | Soporte de audio           | Claude Code          | Autónomo             | Audio integrado             |

## Detalle por fase

### Fase 1. Arquitectura

**Diseño de arquitectura.** Define la arquitectura completa de la aplicación asumiendo un núcleo de emulación externo. Es agnóstico de herramienta porque solo pide razonamiento y un documento de texto estructurado. Su salida alimenta los prompts de interfaz e integración.

**Artefacto web de contexto.** Toma como insumo la especificación de arquitectura y produce una página de una sola vista para que un desarrollador entre en contexto en menos de dos minutos. Requiere una herramienta capaz de renderizar HTML. En entornos sin render se obtiene el código HTML como texto, igualmente válido.

### Fase 2. Selección del núcleo

**Comparación de núcleos.** Revisa y compara los principales núcleos de emulación de SNES viables desde Python. Depende de datos que cambian con el tiempo, por lo que incluye un bloque de verificación que obliga a comprobar en la web o a declarar la incertidumbre. La salida debe tratarse como una lista de candidatos a confirmar, no como un veredicto cerrado.

**Descarga de binarios.** Localiza los binarios oficiales de snes9x_libretro para Windows y macOS. Es el prompt más sensible a seguridad de la colección, porque una URL incorrecta es un vector de riesgo. Define qué cuenta como fuente oficial y exige verificación. La respuesta siempre debe confirmarse a mano antes de descargar nada.

### Fase 3. Validación con prototipo

**Demo mínimo POC.** Construye el `poc.py` más pequeño posible que valide que el núcleo se carga, abre una ROM y muestra imagen. El criterio de éxito es visual, ya que mostrar el framebuffer es lo que distingue un demo que valida de uno que solo carga la librería. El entregable es el mismo tanto si lo ejecuta un agente como si lo corre el usuario.

**Primer hito jugable.** Continúa sobre el mismo `poc.py` para lograr render continuo y control por teclado. Incluye el mapeo de teclas y corrige un punto técnico clave, la velocidad debe ser la nativa que reporta el núcleo, cercana a 60 fps, no 30, que ralentizaría el juego.

### Fase 4. Interfaz

**Diseño UI en Stitch.** Genera el mockup visual del emulador en Google Stitch a partir de un wireframe. Se limita a especificación visual y de composición, sin flujos funcionales ni métricas de producto, que Stitch no puede representar.

**Especificación de interfaz.** Consolida el wireframe y la salida de Stitch en un documento determinista que sirve como entrada para agentes de programación. Conserva flujos, estados y comportamiento, porque aquí sí son la carga útil. Produce `descripcion_interfaz.md`.

**Implementación PySide6.** Implementa la interfaz descrita en `descripcion_interfaz.md` en modo autónomo, sin lógica de emulación y dejando la arquitectura preparada para integrarla después. Usa datos simulados y mock services.

### Fase 5. Integración

**Integración del núcleo.** Conecta la lógica de `poc.py` con la interfaz ya implementada. Opera con puerta de aprobación, primero propone la estrategia de integración y se detiene, luego implementa tras el visto bueno. El control humano se ubica en el punto de máxima incertidumbre, antes de tocar el código.

**Soporte de audio.** Añade reproducción de audio en tiempo real, sincronizada con el video, sin bloquear la interfaz y respetando los estados de ejecución, pausa y salida. Vuelve al modo autónomo porque es una ampliación acotada y de menor riesgo que la integración del núcleo.

## Convenciones

- Los prompts portables evitan nombrar frameworks concretos para no atarse a un entorno.
- Los prompts para agentes declaran de forma explícita solo aquello que se aparta del comportamiento por defecto del agente.
- Los prompts con datos del mundo real incluyen siempre una cláusula de verificación.
- Cada prompt sobre código existente indica el archivo sobre el que trabaja.