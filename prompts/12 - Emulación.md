<!--
Este prompt está pensado para Claude Code en una fase de integración, no de
construcción desde cero. Por eso fija con claridad qué es definitivo y qué es
fuente: la interfaz ya existe y no se rediseña, y `@poc.py` aporta la lógica de
emulación que debe conectarse a esa interfaz. Declarar ambos roles evita que el
agente reinterprete o reescriba la capa visual que ya costó construir. A
diferencia del prompt de implementación, aquí no se trabaja de modo autónomo,
sino con una puerta de aprobación: el agente primero analiza la arquitectura y
propone una estrategia de integración, se detiene, y solo implementa tras el
visto bueno. Ese alto explícito es la instrucción que más se aparta del
comportamiento por defecto del agente, que tiende a seguir de largo hacia la
edición, así que se aísla como un paso numerado en lugar de quedar diluido en
prosa. La integración sobre código existente conlleva más riesgo que la creación
de archivos nuevos, y por eso el control humano se ubica en el punto de máxima
incertidumbre, antes de tocar el código, no después.
-->
# Objetivo
Integra la lógica de emulación de `@poc.py` dentro de la interfaz y la arquitectura ya implementadas, para convertir la aplicación en un emulador funcional completo.

# Fuentes
- `@poc.py` es la fuente de la lógica de emulación: carga de ROMs, ejecución, controles y gestión de estados.
- La interfaz actual es definitiva. Conéctala a esa lógica sin rediseñarla, conservando su estructura visual y su experiencia de usuario. Cablea todos los controles y acciones a la funcionalidad correspondiente.

# Procedimiento
1. Analiza la arquitectura actual del proyecto y `@poc.py`, y propón una estrategia de integración. Detente aquí y espera aprobación.
2. Una vez aprobada, implementa los cambios y documenta brevemente las decisiones técnicas relevantes.