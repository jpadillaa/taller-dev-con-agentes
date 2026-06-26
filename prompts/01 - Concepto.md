<!--
Este prompt está pensado para en cualquier chatbot, el resultado debe ser un archivo de texto, debe guardarlo en la carpeta docs con el nombre descripcion.md
-->
# Rol
Eres un arquitecto de software experto en Python y en aplicaciones de escritorio nativas para macOS, con experiencia integrando núcleos de emulación de videojuegos.

# Contexto
Quiero construir un emulador de SNES para macOS en Python. El proyecto no implementa la emulación. Se asume un núcleo de emulación maduro y externo, integrable desde Python mediante una API, una biblioteca compartida o un proceso externo. El alcance es toda la capa de aplicación que rodea ese núcleo, es decir, la experiencia completa del usuario.

# Tarea
Diseña la especificación técnica de la arquitectura de la aplicación. Debe servir como punto de partida para iniciar el desarrollo.

# Restricciones
- No describas cómo implementar el núcleo de emulación. Trátalo siempre como un componente externo ya existente.
- Separa con claridad la interfaz gráfica de la lógica de negocio.
- Propón una arquitectura modular, mantenible y extensible, con diseño idiomático en Python.
- Asume una aplicación nativa para macOS con apariencia moderna.

# Análisis previo
Antes de elaborar la arquitectura, delimita qué responsabilidades pertenecen a la aplicación y cuáles son exclusivas del núcleo de emulación. Organiza los módulos priorizando bajo acoplamiento, alta cohesión y facilidad de prueba.

# Manejo de incertidumbre
Cuando una recomendación dependa del núcleo de emulación concreto, indícalo de forma explícita en lugar de asumir una API o un comportamiento específico.

# Formato de salida
Genera un documento estructurado con las siguientes secciones.

## 1. Visión general
Propósito del proyecto, alcance y principios de diseño.

## 2. Objetivos
Requerimientos funcionales, como lista de funcionalidades principales, y requerimientos no funcionales, cubriendo mantenibilidad, modularidad, escalabilidad, rendimiento y experiencia de usuario.

## 3. Arquitectura
Módulos principales y su interacción. Incluye un diagrama conceptual en Mermaid.

## 4. Flujo de funcionamiento
Paso a paso desde que el usuario abre la aplicación hasta que comienza a jugar.

## 5. Módulos principales
Para cada módulo, indica propósito, responsabilidades, entradas, salidas y dependencias.

## 6. Funcionalidades de la interfaz
Arquitectura de biblioteca de juegos, configuración de controles, guardado y carga de partidas, configuración de video, configuración de audio, pantalla completa.

## 7. Tecnologías recomendadas
Justifica las bibliotecas o frameworks para interfaz gráfica, persistencia, configuración, integración con el núcleo y pruebas.