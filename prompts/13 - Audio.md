<!--
Este prompt está pensado para Claude Code 
-->
# Objetivo
Implementa soporte completo de audio para la emulación, conectando la generación de muestras del núcleo con un sistema de reproducción adecuado para una aplicación PySide6.

# Procedimiento
Primero analiza la arquitectura actual e identifica cómo y dónde genera el núcleo de emulación las muestras de audio. Sobre ese flujo existente, implementa la reproducción. Reutiliza los componentes que ya existan y evita dependencias innecesarias.

# Requisitos de la integración
- Reproduce el audio del juego en tiempo real.
- Mantén una sincronización razonable entre audio y video.
- No bloquees la interfaz gráfica.
- Maneja correctamente buffers y latencia.
- Detén y libera los recursos al cerrar o reiniciar la emulación.
- Intégrate con los estados actuales de ejecución, pausa y salida del juego.
