<!--
Esto es en la terminal, no requiere IA
-->

Ejecute el comando en la raíz de su proyecto para inicializar el entorno

Bash

```
python3 -m venv .venv
```

## Activación del entorno virtual

Utilice el comando correspondiente a su sistema operativo

**macOS y Linux**

Bash

```
source .venv/bin/activate
```

**Windows**

PowerShell

```
.\.venv\Scripts\Activate.ps1
```

## Generación de dependencias

Exporte los paquetes instalados al archivo de texto con el siguiente comando

Bash

```
pip freeze > requirements.txt
```