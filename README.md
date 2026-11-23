# segundo-cerebro-template

Plantilla de "segundo cerebro" en markdown para un asistente personal con Claude Code al que le hablas por Telegram.

Mezcla tres ideas:

- **[LLM Wiki de Karpathy](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f):** fuentes crudas inmutables (`inbox/`), un wiki que escribe y mantiene el LLM (`wiki/`) y un archivo de reglas (`CLAUDE.md`). Ingest, query, lint.
- **[PARA de Tiago Forte](https://buildingasecondbrain.com/para):** `wiki/` se ordena en proyectos, áreas, recursos y archivo, según qué tan accionable es cada cosa.
- **Nota diaria de [OpenClaw](https://openclaw.ai):** `diario/AAAA-MM-DD.md` con lo que se habló y decidió cada día.

```
CLAUDE.md          reglas para el asistente (capturar, ingerir, consultar, lint, git)
perfil.md          quién eres y cómo te gusta que te hablen
inbox/             capturas crudas, nunca se editan
wiki/              proyectos/ areas/ recursos/ archivo/ + index.md + log.md
diario/            una nota por día
```

## Uso

Crea **tu copia privada** (tus notas no deben ir en un repo público):

```bash
gh repo create segundo-cerebro --private --template ignchap27/segundo-cerebro-template --clone
```

Ábrela con Claude Code (`cd segundo-cerebro && claude`) o como vault de Obsidian. El asistente de Telegram que la usa está en [agent-company-kit](https://github.com/ignchap27/agent-company-kit) (agente `asistente`).
