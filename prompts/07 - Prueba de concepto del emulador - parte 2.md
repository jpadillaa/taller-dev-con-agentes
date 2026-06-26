<!--
Este prompt esta pensado para cualquier chatbot, sin embargo, le recomiendo ejecutarlo sobre un agente de IA para codificar 
-->
# Estado actual
El POC en `poc.py` ya carga `snes9x_libretro.dylib`, carga la ROM `SuperMarioKart.sfc`, inicializa el núcleo y abre una ventana con pygame. El núcleo imprime `Map_HiROMMap`, así que la ROM está siendo reconocida. Quiero continuar sobre este mismo código, no generar un proyecto nuevo.

# Objetivo
Alcanzar el primer hito funcional: ver el juego en pantalla, refrescarlo de forma continua y controlarlo con el teclado. No agregues funcionalidades más allá de esto.

# Análisis previo
Antes de modificar, analiza el estado actual del POC e identifica exactamente qué falta para que un núcleo Libretro renderice y sea jugable, en concreto la recogida del framebuffer por callback, el bucle de frames y el envío de entradas mediante `retro_set_input_state`.

# Tarea
Modifica únicamente el código existente para completar la integración. El resultado debe:
1. Ejecutar el juego de forma continua.
2. Mostrar los frames en pantalla.
3. Correr a la velocidad nativa que el núcleo reporta en `retro_get_system_av_info`, que para SNES es cercana a 60 fps. No fijes 30 fps como objetivo, ya que ralentizaría el juego.
4. Capturar eventos de teclado y pasarlos al núcleo.

# Mapeo de teclado
Implementa este mapeo de forma que sea fácil de modificar después, por ejemplo como una estructura de datos editable y no con condicionales dispersos.

| SNES | Teclado |
|------|---------|
| ↑ | Flecha arriba |
| ↓ | Flecha abajo |
| ← | Flecha izquierda |
| → | Flecha derecha |
| A | X |
| B | Z |
| X | S |
| Y | A |
| L | Q |
| R | W |
| Start | Enter |
| Select | Shift derecho |

# Restricciones
- No cambies la arquitectura actual ni reescribas el proyecto.
- Trabaja sobre `poc.py`.

# Resultado esperado
Super Mario Kart se ve en pantalla y se controla con el teclado definido, a velocidad correcta.