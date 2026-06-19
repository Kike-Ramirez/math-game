# Star Wars Math Academy

Juego de práctica de tablas de multiplicar con temática Star Wars. Implementado en un único archivo HTML con CSS y JavaScript vanilla, sin dependencias externas.

## Características principales

- Intro animada estilo "crawl" de Star Wars (omitible)
- Fondo animado de estrellas en canvas
- Selección de tablas del 1 al 10
- 4 modos de juego
- Sistema de combo (hasta x5)
- 3 vidas por partida
- Temporizador visual con barra de color
- Efectos de partículas y puntuación flotante
- Sonidos generados por Web Audio API
- Mensajes motivacionales de personajes Star Wars
- Pausa con tecla `P` o botón
- Atajos de teclado para respuestas
- Marcador local con los 20 mejores resultados (localStorage)
- Informe de batalla al finalizar
- Diseño responsive (móvil y escritorio)

## Modos de juego

| Modo | Tablas | Preguntas | Respuesta |
|---|---|---|---|
| Orden · Escribir | 1 tabla | 10 | Escribir el resultado |
| Orden · Elegir | 1 tabla | 10 | Elegir entre 3 opciones |
| Aleatorio · Escribir | Varias tablas | 20 | Escribir el resultado |
| Aleatorio · Elegir | Varias tablas | 20 | Elegir entre 3 opciones |

En los modos **Orden**, las preguntas van de `tabla × 1` a `tabla × 10` de forma secuencial y solo se puede seleccionar una tabla. En los modos **Aleatorio**, las preguntas se mezclan aleatoriamente entre todas las tablas seleccionadas.

## Sistema de puntuación

```
Puntos por respuesta = (100 + bono_tiempo) × combo
  bono_tiempo = (tiempo_restante / tiempo_máximo) × 60  [máx. 60 pts]
  combo       = 1–5 (aumenta cada 3 aciertos consecutivos)
```

- Respuesta incorrecta: −15 puntos
- Tiempo agotado: −15 puntos y se cuenta como error
- El combo se reinicia a ×1 en cada fallo

### Tiempo por pregunta

- Modos **Elegir**: 8 segundos
- Modos **Escribir**: 12 segundos

La barra de temporizador cambia de color según el tiempo restante: verde → dorado → rojo.

## Pantallas

### Intro
Crawl de texto animado (estilo Star Wars). Se salta automáticamente a los 20 segundos o con el botón **SALTAR INTRO**.

### Menú
- **Pestaña MISIÓN**: configura tablas y modo de juego, botón para iniciar.
- **Pestaña HOLOCRONES**: leaderboard con los 10 mejores resultados y opción de borrar todo.

### Partida (HUD)
| Indicador | Descripción |
|---|---|
| PUNTOS | Puntuación acumulada |
| COMBO | Multiplicador activo (x1–x5) |
| VIDAS | 3 vidas representadas con ❤️/🖤 |
| TIEMPO | Segundos restantes para responder |

### Resultados
- Puntuación final
- Badge de nuevo récord (si procede)
- Cita Star Wars según el porcentaje de aciertos (≥95% perfecto, ≥75% excelente, ≥50% bien, <50% mejorable)
- Estadísticas: correctas, errores, racha máxima
- Informe de batalla completo con cada pregunta y respuesta dada

## Atajos de teclado

| Tecla | Acción |
|---|---|
| `1` / `2` / `3` | Seleccionar opción en modos Elegir |
| `Enter` | Confirmar respuesta en modos Escribir |
| `P` | Pausar / Reanudar |
| `Esc` | Abrir diálogo de abandono |

## Tecnología

- HTML5 / CSS3 / JavaScript ES6+ (sin frameworks)
- **Canvas API** — fondo de estrellas animadas
- **Web Audio API** — efectos de sonido generados por síntesis (osciladores)
- **localStorage** — persistencia del historial de puntuaciones
- Fuentes: [Orbitron](https://fonts.google.com/specimen/Orbitron) y [Exo 2](https://fonts.google.com/specimen/Exo+2) via Google Fonts

## Uso

Abre `index.html` directamente en el navegador. No requiere servidor ni instalación.
