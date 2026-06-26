<!--
Este prompt está pensado para en cualquier chatbot, adjunte los archivos de salida de Claude Design o Google Stitch del paso anterior, el resultado debe ser un archivo de texto, debe guardarlo en la carpeta docs con el nombre descripcion_interfaz.md
-->
# Rol
Eres un diseñador senior de UX, arquitecto de interfaces Qt y desarrollador experto en Python y PySide6, especializado en aplicaciones de escritorio modernas y escalables.

# Contexto
Necesito definir completamente la interfaz antes de implementarla. La salida será una especificación funcional y visual que se usará como entrada para agentes de programación como Claude Code, Codex u OpenCode, por lo que debe ser determinística y permitir la implementación directa sin decisiones de diseño abiertas.

# Archivos de referencia
Analiza completamente ambos artefactos adjuntos antes de generar la especificación:
1. Un wireframe que define la distribución visual, organización espacial y jerarquía de la interfaz.
2. Un documento exportado de Google Stitch con la especificación de diseño y el código de una versión web.

Reglas de uso:
- El wireframe es la fuente principal de estructura visual y distribución. Ante cualquier contradicción, prevalece el wireframe.
- El documento de Stitch es la fuente principal de componentes, estados, interacciones y comportamiento funcional.
- Consolida ambos en una especificación única y coherente. No describas los archivos por separado.
- Reinterpreta todos los componentes para una aplicación de escritorio en PySide6. No asumas que la implementación web es reutilizable de forma directa.

# Tarea
Define la interfaz completa: estructura de ventana, regiones, componentes, interacciones, flujos, estados visuales y jerarquía de widgets y contenedores en PySide6. Para cada interacción relevante, identifica widgets, contenedores, relaciones padre-hijo y comportamiento esperado, minimizando ambigüedades.

# Objetivos de diseño
- Simplicidad y claridad visual.
- Baja carga cognitiva.
- Acceso rápido a las funciones principales.
- Experiencia centrada en el juego.
- Apariencia profesional.
- Compatibilidad con macOS y Windows, con soporte HiDPI y Retina.

# Estructura del documento de salida
Genera un único documento Markdown con exactamente las siguientes secciones, cada una con el contenido indicado.

## Visión general
Propósito de la aplicación y descripción de la pantalla única.

## Objetivos UX
Desarrolla los objetivos de diseño aplicados a la interfaz.

## Layout principal
Ventana principal, áreas funcionales, distribución espacial, jerarquía visual y estructura de layouts.

## Jerarquía de componentes
Árbol completo de widgets y contenedores con relaciones padre-hijo.

## Componentes de la interfaz
- Área de juego: ubicación, dimensiones relativas, relación de aspecto y su comportamiento al redimensionar, modos de visualización y comportamiento en pantalla completa.
- Paneles auxiliares: información del juego, configuración, visualización y asignación del control, estados del sistema, apertura y cierre, conexión y desconexión de dispositivos.
- Barra de acciones: acciones principales, agrupación de controles, iconografía recomendada, accesos rápidos y comportamiento de cada acción. Incluye como mínimo cargar juego, guardar partida, cargar partida, salir del juego y pantalla completa.

## Flujos de interacción
Paso a paso para: carga de juego (apertura de ROM, validación, carga, transición al juego), guardado (manual, confirmación, errores), carga de partida (selección, restauración, feedback), pantalla completa (entrada, salida, persistencia de controles) y salida del juego (cierre de sesión, limpieza visual, retorno a la interfaz principal).

## Estados de la interfaz
Define explícitamente: vacío, cargando, ejecutando, pausado, error y pantalla completa.

## Componentes PySide6 recomendados
Por cada componente importante indica widget principal, layouts utilizados, widgets hijos y propósito funcional, con una justificación breve.

## Sistema visual
- Tipografía: familia, tamaños y pesos.
- Espaciados: márgenes externos, separación entre componentes y padding interno.
- Iconografía: estilo, tamaño recomendado y consistencia.
- Colores para tema claro y tema oscuro: fondo principal, paneles, texto, controles y estados.

## Reglas de comportamiento
Redimensionamiento, tamaños mínimos e iniciales recomendados, restricciones de layout, persistencia de configuración, restauración del estado de la ventana y comportamiento ante cambios de resolución.

## Consideraciones multiplataforma
Diferencias y recomendaciones específicas para macOS y Windows.

## Recomendaciones para implementación
Notas finales orientadas al agente de programación.

# Restricciones
- No generes código.
- No generes mockups gráficos.
- No describas el núcleo de emulación, la arquitectura backend ni la lógica interna del emulador.
- Mantén el enfoque exclusivamente en la experiencia de usuario y la estructura de la interfaz.