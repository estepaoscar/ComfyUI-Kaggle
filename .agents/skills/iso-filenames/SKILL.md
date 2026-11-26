---
name: iso-filenames
description: Aplica la convención de nombres de archivo ISO AAAA-MM-DD_Descripción_Versión a todo archivo que se cree en este proyecto.
---

# Convención ISO de nombres de archivo

Todo archivo que se cree, genere o renombre debe usar el formato `AAAA-MM-DD_Descripción_Versión.ext`.

- `AAAA-MM-DD`: fecha en orden ISO (año-mes-día).
- `Descripción`: texto descriptivo en minúsculas, palabras separadas con guiones bajos.
- `Versión`: número entero, arranca en `v1` y sube `v2`, `v3`, ...
- Separador entre partes: guion bajo `_`. Sin espacios ni otros guiones.
- La versión es SIEMPRE un entero. Prohibido: letras (`vA`), nombres (`vFinal`), la palabra `version`, y puntos (`v1.3`).
- Para versionar un archivo ya existente: incrementa el entero sin añadir sufijos.
- Aplícala a cualquier archivo con fecha/versión: scripts, respaldos, reportes, etc. En caso de duda, aplícala.