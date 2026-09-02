---
description: Crea un git worktree en .worktrees/ con el nombre derivado del argumento.
---

Recibes el argumento: "$ARGUMENTS"

Sigue estos pasos al pie de la letra, sin hacer nada más:

1. Si el argumento está vacío, pregunta al usuario por el nombre deseado y detente ahí. No ejecutes ningún comando todavía.
2. Deriva el nombre del worktree slugificando el argumento:
   - Convierte a minúsculas.
   - Elimina acentos y caracteres especiales (conserva solo letras, números y guiones).
   - Reemplaza cada espacio (o secuencia de espacios) por un solo guion `-`.
   - Colapsa guiones repetidos y recorta guiones al inicio/final.
   - Ejemplo: "Fix Collision bug!" → `fix-collision-bug`.
3. Ejecuta EXACTAMENTE este comando (una sola invocación, con el nombre slugificado):

   git worktree add .worktrees/<nombre-slugificado>

Restricciones estrictas:

- NO hagas `cd`, NO cambies de directorio de trabajo.
- NO crees ramas, NO modifiques archivos, NO ejecutes ningún otro comando git ni de otro tipo.
- NO intentes entrar al worktree ni instalar nada en él.
- Si el comando falla (por ejemplo, si el worktree o la rama ya existen), muestra el error de git tal cual y detente; no intentes corregirlo ni reintentar con variantes.
4. Al terminar con éxito, responde únicamente con la ruta del worktree creado.
