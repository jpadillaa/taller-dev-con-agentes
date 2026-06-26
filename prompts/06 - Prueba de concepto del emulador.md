<!--
Este prompt esta pensado para cualquier chatbot, sin embargo, le recomiendo ejecutarlo sobre un agente de IA para codificar 
-->
# Objetivo
Construye el ejemplo más pequeño posible que valide que el núcleo snes9x_libretro funciona desde Python, cargando una ROM y mostrando imagen.

# Contexto
La emulación la realiza snes9x_libretro. En esta etapa no quiero la aplicación completa, solo un prototipo que demuestre que el núcleo se carga y ejecuta una ROM. Estructura del proyecto:

​```text
Proyecto/
├── kernel/
│   └── snes9x_libretro.dylib
├── ROMS/
│   └── SuperMarioKart.sfc
└── poc.py
​```

# Tarea
Escribe `poc.py` para que:
1. Cargue el núcleo desde `kernel/snes9x_libretro.dylib`.
2. Cargue la ROM `ROMS/SuperMarioKart.sfc`.
3. Inicialice el núcleo mediante la API de Libretro.
4. Ejecute el bucle de emulación y muestre el framebuffer en una ventana, de modo que se vea imagen del juego.

No agregues nada más allá de esto.

# Restricciones
- Solo Python.
- Prioriza la simplicidad. Un único script, sin capas, patrones ni arquitectura.
- El único fin es validar la integración del núcleo.

# Dependencias
Libretro entrega video y audio por callbacks, así que se necesita al menos recoger el framebuffer y dibujarlo. Si hacen falta bibliotecas para enlazar con la API de Libretro o para mostrar la imagen, elígelas priorizando la simplicidad, justifica brevemente la elección y lista los comandos de instalación.

# Salida esperada
Entrega el contenido completo de `poc.py` y las instrucciones de instalación. 