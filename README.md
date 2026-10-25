# contenido-cerebro

El "cerebro" de mi contenido: voz de marca, prompts y calendario.
Make lee estos archivos en cada ejecución, así que **si cambio algo aquí, cambian todos los copys** sin tocar ningún escenario.

## Qué hay en cada carpeta

| Carpeta | Para qué sirve | Quién lo lee |
|---|---|---|
| `marca/` | Cómo hablo, a quién le hablo y de qué temas | Todos los prompts (se inyecta como contexto) |
| `prompts/` | Instrucciones para la IA: hooks, copys y títulos por red | Escenario 03 · Copys IA |
| `calendario/` | Qué sale, cuándo y en qué red | Escenarios 03 y 05 |

## Cómo lo usa Make

1. El módulo **GitHub → Get a file content** lee, por ejemplo, `prompts/hooks.md` de la rama `main`.
2. Se reemplazan las variables `{{entre_llaves}}` con los datos del clip (transcripción, tema, lugar…).
3. El texto final se manda al módulo de IA.

### Variables que aceptan los prompts

| Variable | Qué es | De dónde sale |
|---|---|---|
| `{{voz}}` | Contenido de `marca/voz-y-tono.md` | GitHub |
| `{{avatar}}` | Contenido de `marca/avatar.md` | GitHub |
| `{{pilar}}` | Pilar de contenido del clip | Calendario |
| `{{transcripcion}}` | Lo que digo en el vídeo | Edición (Whisper) |
| `{{contexto}}` | Nota rápida que escribo al subir el clip (lugar, qué pasó) | Formulario o nombre del archivo |
| `{{hook}}` | Hook elegido | Paso de hooks |
| `{{hashtags}}` | Set de hashtags del pilar | `prompts/hashtags.json` |

## Reglas

- Edito los `.md` directamente en GitHub (botón del lápiz) o desde el móvil con la app de GitHub.
- No cambies el nombre de los archivos ni de las variables: los escenarios los buscan por nombre.
- Antes de cambiar un prompt importante en plena temporada, haz una prueba con un clip viejo.
