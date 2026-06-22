---
description: Rilegge un capitolo e lo riallinea allo stile descritto in CLAUDE.md
---

Rileggi il file: $ARGUMENTS

## Passaggio 1 — Coerenza con `CLAUDE.md` e la voce dell'autore
Verifica e correggi rispetto a `CLAUDE.md`:
1. Niente em dash, ellissi Unicode, virgolette tipografiche
2. Niente "in conclusione", "in sintesi", "e importante sottolineare"
3. Niente apertura di paragrafo con "Tuttavia," o "Inoltre," ripetitivi
4. Ritmo: alternare frasi brevi e lunghe senza pattern prevedibile
5. Tono critico, non neutro: l'autore prende posizione
6. Termini tecnici usati naturalmente, non spiegati come dizionario
7. Citazioni `\cite{}` corrette e presenti in `references.bib` (chiavi CamelCase `CognomeAnno`)
8. Coerenza con la funzione del capitolo come definita in
   `capitoli_second/00_introduzione.tex`

## Passaggio 2 — Secondo giro anti-AI con la skill `humanizer`
Leggi e applica anche la skill **`humanizer`** in
`.claude/skills/humanizer/SKILL.md` (se compare nella lista skill puoi invocarla
con lo strumento Skill; altrimenti leggi direttamente quel file e usane il
catalogo di pattern). Serve come secondo passaggio per stanare i segni residui di
scrittura generata da AI: gonfiamento del significato, linguaggio promozionale,
analisi superficiali in "-ing"/gerundio, attribuzioni vaghe, regola del tre,
parallelismi negativi ("non solo... ma..."), variazione elegante (sinonimi a
rotazione), false gamme ("da X a Y"), copule mascherate, filler e hedging,
"punchline" costruite a effetto, segnaletica ("vediamo ora...") e formule da
aforisma.

**Regole di adattamento (obbligatorie, prevalgono sul default della skill):**
- Il testo e una **tesi accademica in italiano**: adatta gli esempi della skill
  (pensati per l'inglese) all'italiano e ignora le regole puramente
  anglofone non pertinenti (es. title case, curly quotes inglesi, copula
  "is/are", coppie con trattino tipo "data-driven").
- **NON applicare** la sezione "PERSONALITY AND SOUL" della skill: niente
  iniezione di opinioni in prima persona, battute o tono colloquiale. Per un
  testo accademico il registro neutro e argomentato e gia la voce umana corretta.
  La skill stessa lo dice: per testo tecnico/accademico "neutral and plain is the
  correct human voice".
- La **voce dell'autore prevale** sulle preferenze generiche della skill. Tienila
  agganciata a `style_patterns.md`, a `C:\Users\andre\OneDrive\andrea\database
  umano\me.txt` e `...\tone_of_voice.txt`. Dove la skill spinge verso una prosa
  generica, vince lo stile dell'autore.
- Preserva i tecnicismi previdenziali (neutralita attuariale, montante, NDC, tasso
  di sostituzione, ecc.) e i numeri/citazioni: non "semplificarli" via.

## Output
Mostra prima un diff sintetico delle modifiche proposte (indicando per le piu
rilevanti quale pattern AI risolvono).
Applica solo dopo conferma. Committa con messaggio "style: riallineamento [file]".
