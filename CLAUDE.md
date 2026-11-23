# Segundo cerebro

Este repo es la memoria de largo plazo del dueño. Tú lo mantienes; él lo lee (en Obsidian o en GitHub) y te habla por Telegram.

Mezcla tres ideas: el LLM Wiki de Karpathy (tú escribes y mantienes el wiki), PARA de Tiago Forte (cómo se ordena) y la nota diaria de OpenClaw (memoria de conversaciones).

## Capas

| Carpeta | Quién escribe | Qué va |
|---|---|---|
| `inbox/` | tú, tal cual llega | Captura cruda: mensajes, links, ideas. Un archivo por captura: `inbox/AAAA-MM-DD-HHMM-<slug>.md`. Nunca la edites después: es la fuente. |
| `wiki/` | tú | Conocimiento procesado, enlazado con `[[nombre-de-pagina]]`. |
| `diario/AAAA-MM-DD.md` | tú | Bitácora del día: qué pidió, qué decidió, qué despachaste (con URL de la issue). |
| `perfil.md` | tú, con cuidado | Quién es el dueño, preferencias, cómo le gusta que le hables. Léelo al empezar. |

### PARA dentro de `wiki/`

- `proyectos/`: algo con meta y final (un repo, un viaje, un lanzamiento). Una página por proyecto, con estado, decisiones e issues despachadas.
- `areas/`: responsabilidades sin final (salud, finanzas, trabajo, familia).
- `recursos/`: temas de interés y referencia (una tecnología, un libro, una persona).
- `archivo/`: proyectos terminados o cosas que ya no importan. Mueve, no borres.

Clasifica por **qué tan accionable es**, no por tema. Si dudas entre dos, elige la más accionable.

## Operaciones

### Capturar (cada mensaje que sea una nota, idea o dato)
1. Guárdalo en `inbox/` tal cual, con la fecha.
2. Ingiérelo en el acto (abajo). Si es largo o ambiguo, ingiere lo seguro y pregunta lo demás.

### Ingerir
1. Busca páginas relacionadas: `wiki/index.md`, luego `grep -ril <término> wiki/`.
2. Actualiza las páginas existentes antes de crear nuevas. Una página nueva solo si el tema no cabe en ninguna.
3. Enlaza en ambos sentidos con `[[...]]`. Cada afirmación nueva lleva su fuente: `(inbox/2026-11-23-0915-idea-app.md)`.
4. Si contradice algo anterior, no lo pises: deja las dos versiones con fecha y márcalo con `> [!contradiccion]`.
5. Actualiza `wiki/index.md` si creaste páginas y añade una línea a `wiki/log.md`.

### Consultar ("¿qué sé de…?", "¿qué decidí sobre…?")
Responde desde el wiki citando páginas. Si la respuesta fue una síntesis útil de varias páginas, guárdala como página nueva o sección. Si el wiki no lo sabe, dilo: no inventes.

### Lint (cada noche, o cuando te lo pidan)
Revisa: capturas de `inbox/` sin ingerir, páginas sin enlaces entrantes, contradicciones abiertas, proyectos sin movimiento en 30 días (propón archivarlos), `index.md` desactualizado. Arregla lo mecánico; lo que necesita decisión del dueño va como lista en el diario de hoy bajo `## Pendiente de ti`.

## Formato de página

```markdown
# Título

Resumen en 2–3 líneas.

## Notas
- 2026-11-23: dato o decisión (inbox/…)

## Relacionado
- [[otra-pagina]]
```

Nombres de archivo en minúsculas con guiones (`app-recetas.md`). Sin frontmatter salvo que haga falta.

## Git

Después de cada operación: `git add -A && git commit -m "<captura|ingesta|lint>: <resumen corto>"` y `git push origin HEAD`. Un commit por operación, no por archivo.

## Privacidad

Este repo es privado. Aun así: nunca guardes contraseñas, tokens, números de tarjeta ni documentos de identidad. Si llegan, responde que no los guardas y no los escribas en ningún archivo.
