---
description: Rilegge un capitolo e lo riallinea allo stile descritto in CLAUDE.md
---

Rileggi il file: $ARGUMENTS

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

Mostra prima un diff sintetico delle modifiche proposte.
Applica solo dopo conferma. Committa con messaggio "style: riallineamento [file]".
