<!--  Claude Code ya lee archivos, analiza el contexto, planifica y edita el proyecto por su cuenta. Por eso no enumera esos pasos como instrucciones, ya que repetir el comportamiento por defecto del agente no añade dirección y solo alarga el prompt. Lo que sí se declara de forma explícita es aquello que se aparta de ese comportamiento o que el agente no puede inferir: trabajar de modo autónomo sin pedir confirmaciones, documentar al final las decisiones tomadas ante ambigüedades, y los límites duros del trabajo. Las restricciones se separan del procedimiento porque un agente las trata como fronteras del problema y no como un paso más de la secuencia. El alcance se lista de forma cerrada para acotar qué construir y evitar que el agente extienda el trabajo hacia la lógica del emulador, que aquí queda fuera. La estructura general va de lo general a lo concreto, objetivo, procedimiento, restricciones y alcance, de modo que el agente fije primero la meta y los límites antes de entrar al detalle de los entregables. -->
# Objetivo
Implementa la interfaz gráfica especificada en `docs/descripcion_interfaz.md` con Python y PySide6. El resultado debe ser una representación funcional, ejecutable y fiel a la especificación.

# Procedimiento
Lee la especificación completa y planifica antes de escribir código. Luego implementa de forma autónoma, editando los archivos del proyecto directamente y sin pedir confirmaciones intermedias. Si encuentras inconsistencias o ambigüedades, toma la decisión más razonable, continúa, y documenta esas decisiones al finalizar.

# Restricciones
- No implementes la lógica del emulador. La arquitectura debe quedar preparada para integrar el núcleo de emulación más adelante.
- Usa datos simulados y mock services donde sea necesario para demostrar la experiencia completa.

# Alcance
Implementa únicamente la capa de interfaz:
- Ventana principal
- Área de visualización del juego
- Panel lateral
- Barra inferior de acciones
- Menús y toolbars
- Diálogos necesarios
- Temas visuales claro y oscuro
- Navegación y estados de la interfaz
- Componentes reutilizables
- Mock services para las acciones