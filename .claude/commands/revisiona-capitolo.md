---
description: Revisione critica completa di un capitolo - coerenza con la costituzione e le sotto-tesi, densita, integrita di dati e citazioni, struttura e voce
---

Revisiona il capitolo: $ARGUMENTS

Questa skill fa la revisione di SOSTANZA e RIGORE. Per il solo riallineamento
stilistico di superficie (em dash, tic, ritmo) c'e `/rileggi-stile`: questa la
include come ultima dimensione, ma il suo focus e contenuto, coerenza con la
tesi e verificabilita dei dati. Non e una riscrittura: e un audit con report e
correzioni proposte.

## Fase 1 — Contesto (leggi prima di giudicare)

1. Verifica di essere sul branch `sviluppo-test-agente`.
2. `tesi_research_question.md` (costituzione): le 4 sotto-tesi, le posizioni di
   partenza, le obiezioni da affrontare, la lista "Cosa NON sostengo".
3. `capitoli_second/00_introduzione.tex`: la funzione assegnata al capitolo e i
   suoi confini con i capitoli vicini.
4. `tesi_constraints.md`: il budget di pagine del capitolo e il principio di
   densita argomentativa.
5. `style_patterns.md` e `CLAUDE.md`: i 10 pattern di voce, la lista nera
   anti-tells e i divieti assoluti.
6. `fonti/_dossier_fonti.md`: la base per verificare che i dati e le posizioni
   citati nel capitolo siano davvero nelle fonti. Apri i PDF in `fonti/` solo
   se serve un riscontro che il dossier non copre.
7. Il file `.tex` del capitolo da revisionare, integralmente.

## Fase 2 — Audit

Per ogni problema assegna una gravita:
- **BLOCCANTE**: rompe la tesi, viola un no-go, o presenta come fatto un dato
  non verificabile o falso.
- **FORTE**: indebolisce l'argomento o lascia scoperta un'obiezione.
- **MINORE**: rifinitura di stile o forma.

Dimensioni da controllare:

1. **Coerenza con la costituzione.** Per ogni sezione: quale delle 4 sotto-tesi
   sostiene o sfuma? Se una sezione non ne sostiene nessuna → segnala. Il
   capitolo viola la lista "Cosa NON sostengo"? → BLOCCANTE.
2. **Funzione nel disegno.** Il capitolo fa cio che `00_introduzione.tex` gli
   assegna? Sconfina nel territorio di un altro capitolo o ripete cose gia
   dette altrove?
3. **Obiezioni.** Le obiezioni della costituzione pertinenti a questo capitolo
   sono affrontate, o consapevolmente rimandate? Se ignorate in silenzio →
   FORTE.
4. **Densita e budget.** Stima le pagine rispetto al target di
   `tesi_constraints.md`. Segnala i paragrafi di pura transizione o descrittivi
   che non producono un'affermazione: vanno tagliati o densificati.
5. **Struttura della sezione.** Ogni sezione tecnica segue lo schema
   divulgativa → tecnica (formula + esempio numerico) → evidenze → dibattito →
   conclusione critica? Manca l'esempio numerico dopo una formula? La
   conclusione aggiunge qualcosa che l'introduzione non sapeva, o e circolare?
6. **Integrita dei dati.** Ogni numero nel capitolo e tracciabile a una fonte
   (dossier o PDF)? Un numero presentato come fatto ma senza riscontro →
   BLOCCANTE o `\todo{VERIFICA DATO}`. Contraddizioni con altre fonti non
   segnalate → `\todo{CONTRADDIZIONE: ...}`.
7. **Integrita delle citazioni.** Ogni `\cite{Chiave}` esiste in
   `references.bib`? Le chiavi sono nel formato CamelCase `CognomeAnno`? Ci sono
   citazioni che riassumono autori ("Bosi sostiene X, Artoni afferma Y") invece
   di sostenere una posizione? Quelle vanno riformulate (vietate da
   `tesi_constraints.md`).
8. **Voce e anti-tells.** Applica i criteri di `/rileggi-stile`: niente em dash,
   virgolette tipografiche o ellissi Unicode, niente "in conclusione"/"in
   sintesi", niente "Tuttavia,"/"Inoltre," come tic, niente aggettivi gemelli,
   verbi tappabuchi o frasi-annuncio. Ritmo non prevedibile, tono critico.
   Riconosci i 10 pattern autentici di `style_patterns.md` o e prosa neutra da
   AI?
9. **Test di coerenza per paragrafo** (costituzione). Sui paragrafi chiave: il
   lettore alla fine sa qualcosa che prima non sapeva? Andrea ci si riconosce
   per sostanza e posizioni?

## Fase 3 — Report e correzione

1. Produci un report sintetico raggruppato per gravita (BLOCCANTE → FORTE →
   MINORE). Ogni voce: riferimento a riga o sezione, problema, correzione
   proposta. A questo punto NON hai ancora toccato il file.
2. Mostra un diff sintetico delle modifiche che applicheresti.
3. Applica solo dopo conferma dell'autore. I `\todo{}` per dati da verificare
   restano nel sorgente: non li "risolvi" inventando un numero.
4. Se hai modificato il testo, ricompila (`pdflatex second_main.tex`; se hai
   toccato citazioni anche `bibtex second_main` + due `pdflatex`) e committa con
   messaggio `revisione(capN): <descrizione>`.
