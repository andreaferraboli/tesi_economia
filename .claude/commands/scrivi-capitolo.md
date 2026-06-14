---
description: Scrive o espande un capitolo della tesi seguendo CLAUDE.md
---

Scrivi o espandi il capitolo: $ARGUMENTS

## Fase 1 — Allineamento (leggi PRIMA di scrivere, in quest'ordine)

1. Verifica di essere sul branch `sviluppo-test-agente`. Se non ci sei, fai
   checkout. Mai lavorare su `main`.
2. `tesi_research_question.md` (LA costituzione, prevale su tutto): fissa in
   testa domanda di ricerca, tesi centrale, le 4 sotto-tesi, le posizioni di
   partenza dell'autore, le obiezioni da affrontare e la lista "Cosa NON
   sostengo".
3. `capitoli_second/00_introduzione.tex`: ricostruisci la funzione del capitolo
   nel disegno complessivo — cosa promette, cosa lo precede, cosa lo segue.
   Se introduzione e costituzione confliggono, FERMATI e segnala il conflitto,
   non risolverlo da solo.
4. `tesi_constraints.md`: prendi il budget di pagine del capitolo (tabella di
   distribuzione, circa 4-7 pagine) e ricorda che la densita argomentativa e
   il vincolo dominante.
5. `CLAUDE.md`: stile accademico, divieti assoluti, struttura per sezione,
   formato LaTeX.
6. Voce autoriale, da leggere insieme:
   - `C:\Users\andre\OneDrive\andrea\database umano\me.txt` (biografia, valori,
     visione, posizioni)
   - `C:\Users\andre\OneDrive\andrea\database umano\tone_of_voice.txt` (registro,
     lessico, strutture frase)
   - `style_patterns.md` (10 pattern strutturali da trasportare nel registro
     accademico + lista nera dei tic da AI)
7. Il file `.tex` del capitolo indicato: rispetta contenuto e fonti gia
   validati. Se e una bozza AI, trattalo come indicatore di CONTENUTO, non di
   stile: si riscrive dalla costituzione e dalle fonti, non si corregge in
   superficie.
8. `git log -- capitoli_second/<file>`: le correzioni passate dell'autore sono
   il segnale piu forte di cosa vuole davvero (vedi `tesi_constraints.md`).
9. Fonti: parti da `fonti/_dossier_fonti.md` (dossier gia pronto con dati,
   posizioni e mappatura su sotto-tesi). Apri i PDF originali in `fonti/` solo
   per verifica puntuale o per un dato che il dossier non copre. Chiediti
   sempre cosa Andrea estrarrebbe da ogni fonte e come la userebbe come leva
   argomentativa.

## Fase 2 — Scrittura

Struttura interna di ogni sezione (da CLAUDE.md):
1. introduzione divulgativa
2. analisi tecnica: formula in `equation`/`align` o inline, variabili definite
   subito, sempre un esempio numerico concreto
3. evidenze empiriche: dati MEF/RGS (Rapporto-2025-n.26) o IMF con `\cite{}`
4. dibattito tra esperti: 3-4 voci (Lavoce, VoxEU, paper in `fonti/`)
   sintetizzate, non parafrasate
5. conclusione critica: tensione lasciata aperta, niente fiocco

Vincoli mentre scrivi:
- Ogni paragrafo sostiene o sfuma una delle 4 sotto-tesi. Se non lo fa, non va
  scritto (test di coerenza della costituzione).
- Non violare la lista "Cosa NON sostengo" della costituzione, anche se una
  fonte la suggerisce.
- Densita, non accumulo: rispetta il budget di pagine, niente paragrafi di
  pura transizione, un dato MEF ben scelto vale piu di cinque generici.
- Dati solo da fonti verificate. Numero non verificato → `\todo{VERIFICA DATO}`.
  Contraddizione tra fonti → `\todo{CONTRADDIZIONE: spiegazione}`. Mai inventare
  numeri.
- Citazioni: `\cite{Chiave}` con chiavi CamelCase `CognomeAnno` come gia in
  `references.bib` (es. `Bosi2018`, `FrancoTommasino2020`, `MEF_RGS2025`). Se la
  fonte non esiste ancora, aggiungi la voce BibTeX in `references.bib` nella
  root, NON in `06_bibliografia.tex` (che fa solo `\bibliography{references}`).
- Stile: ritmo non prevedibile, niente em dash, virgolette tipografiche o
  ellissi Unicode, niente "in conclusione"/"in sintesi", niente "Tuttavia,"/
  "Inoltre," come apertura ricorrente, niente aggettivi gemelli o verbi
  tappabuchi (lista nera in `style_patterns.md`).
- Header del file `.tex`:
  ```
  % Capitolo X — [Titolo]
  % Ultima modifica: <data odierna>
  % Fonti principali usate: [elenco]
  ```

## Fase 3 — Verifica e commit

1. Compila dalla root: `pdflatex second_main.tex`. Se hai aggiunto citazioni:
   `bibtex second_main`, poi due volte `pdflatex second_main` per i riferimenti
   incrociati. Controlla che non ci siano errori e che i `\cite` risolvano
   (nessun `[?]` nel PDF).
2. Test finale prima di committare (CLAUDE.md): Andrea, leggendo questo capitolo
   tra sei mesi, lo riconoscerebbe come suo per sostanza e posizioni, e come
   scritto per una tesi e non per un post? Devono valere entrambi.
3. Committa in italiano: `git add` dei soli file toccati (capitolo + eventuale
   `references.bib`), commit tipo `feat(capN): <descrizione>`.
