# AGENTS.md

## Proyecto
Clon de Asteroids en JS vainilla + Canvas HTML5. Sin package.json, sin dependencias, sin bundler. Toda la lógica del juego está en un solo archivo, `game.js`, cargado por `index.html` como script plano (no como módulo ES).

## Comandos
- Ejecutar: `npx serve .` o abrir `index.html` directamente en el navegador.
- No existe tooling de build, test, lint ni typecheck. No inventes `npm test` ni similares. Verifica los cambios cargando la página en el navegador.

## Notas de arquitectura
- El canvas es fijo de 800x600: las constantes `W`/`H` de `game.js` deben mantenerse sincronizadas con los atributos `width`/`height` de `index.html`.
- `game.js` es un solo archivo plano con globals de nivel superior y clases; mantenlo así en lugar de introducir módulos.
- Máquina de estados del juego: `state` es `'playing' | 'dead' | 'gameover'`; Espacio reinicia desde gameover.
- El mundo se envuelve toroidalmente mediante `wrap()`; las constantes de ajuste (radios, velocidades, puntos, propulsión, fricción, tiempos de recarga) están definidas junto a la clase que las usa.

## Convenciones
- Los comentarios del código y los textos de la interfaz del juego están en español ("NIVEL", "PUNTAJE", comentarios separadores de sección). Respeta esto al editar.

## Trampas
- README.md anuncia power-ups y un tipo de asteroide "estrella fugaz" que NO están implementados. Confía en `game.js` antes que en las afirmaciones de funcionalidades del README.
