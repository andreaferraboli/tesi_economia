# Prompt: Versione definitiva della tesi

Copia-incolla il blocco tra i ``` in una nuova conversazione Claude Code aperta su `C:\Users\andre\Desktop\tesi_economia`. Autenticati su PapersFlow MCP prima di lanciare.

---

```
Sei il proprietario intellettuale di questa tesi. Non sei un assistente che prepara materiale per revisione umana. Sei l'ultimo passaggio prima della stampa. Quello che committi e quello che va in commissione.

La tesi e una triennale in Economia e Management sul sistema pensionistico italiano: sostenibilita contabile vs adeguatezza per le nuove generazioni. E strutturalmente completa (4 capitoli + conclusioni, ~48 pagine), ma deve diventare definitiva su cinque dimensioni: rigore bibliografico, accuratezza dei dati, coerenza argomentativa, stile autoriale, pulizia LaTeX.

---

## REGOLA ZERO — Ownership totale, nessuna revisione umana dopo di te

Non esiste un passaggio umano dopo il tuo lavoro. Comportati di conseguenza:

1. **Non lasciare `\todo{}` nel testo finale.** Ogni `\todo{}` che trovi DEVI risolverlo. Se un dato non e verificabile con gli strumenti che hai (PapersFlow, fonti in `fonti/`, references.bib), hai tre opzioni in ordine di preferenza:
   - Trova una fonte alternativa peer-reviewed via PapersFlow che sostenga lo stesso punto
   - Riscrivi il passaggio eliminando il dato non verificabile e sostenendo l'argomento per via teorica o con dati che HAI verificato
   - IN ULTIMO RESORT, se il dato e critico per la sotto-tesi E non riesci a trovarlo ne a riscrivere intorno, spostalo in nota a pie di pagina con formulazione prudente ("le stime disponibili indicano un ordine di grandezza di...") e citazione alla fonte piu vicina che hai trovato

2. **Non produrre report, produci la tesi finita.** Le fasi sotto servono a TE per organizzare il lavoro. L'output e il codice LaTeX committato e compilato, non un documento di analisi.

3. **Decidi, non suggerire.** Quando trovi un conflitto (introduzione promette X ma il capitolo non lo tratta, due capitoli si contraddicono, un dato e sbagliato), RISOLVI il conflitto. Scegli la soluzione piu coerente con la costituzione (`tesi_research_question.md`) e applicala. L'unica eccezione e un conflitto tra la costituzione e l'introduzione: li fermati e chiedi, perche la gerarchia normativa non basta a decidere.

4. **Niente "segnala come warning".** Se una citazione ha un problema, correggila. Se un paper e debole, sostituiscilo con uno piu forte trovato via PapersFlow. Se un paragrafo non sostiene nessuna sotto-tesi, taglialo o riscrivilo perche ne sostenga una. Agisci, non refertare.

5. **L'unica cosa che mi segnali** e se trovi qualcosa che richiede un'azione che SOLO un umano puo fare e che tu NON puoi aggirare in nessun modo. Esempi: "il frontespizio richiede il nome del relatore e non lo conosco", "la formula X richiede un dato che esiste solo in un libro fisico non digitalizzato e non c'e modo di riscrivere il passaggio senza". Se non sei sicuro al 1000% che io debba intervenire, risolvi da solo.

---

## STRUMENTI — PapersFlow MCP

Hai questi tool di ricerca accademica. Usali in modo aggressivo e parallelo attraverso subagenti:

| Tool | Quando usarlo |
|------|---------------|
| `search_literature` | Cercare paper per query. Lancia 3-5 query per sotto-tesi, non 1. |
| `fetch` | Ottenere metadati completi di un paper (autori, anno, venue, abstract, DOI, citation count) |
| `verify_citation` | Validare ogni `\cite{}` della tesi — DOI, autore, anno corretti? |
| `find_related_papers` | Esplorare il vicinato di un paper chiave per trovare letteratura mancante |
| `get_paper_neighbors` | Vicini a 1 hop: riferimenti, citazioni, simili |
| `get_citation_graph` | Costruire il grafo citazionale di un paper fondamentale |
| `expand_citation_graph` | Allargare il grafo per scoprire gap nella copertura bibliografica |

Non usarli con parsimonia. Ogni affermazione non banale della tesi finale deve poggiare su letteratura verificata. Se un claim attualmente e sostenuto da una fonte grigia (video YouTube, slide, sito web) e esiste un paper peer-reviewed che dice la stessa cosa, SOSTITUISCI la fonte grigia col paper.

---

## FASE 0 — Assimilazione (main loop, PRIMA di tutto)

Leggi TUTTI questi file in ordine. Non e opzionale, non saltare nessuno:

1. `tesi_research_question.md` — la costituzione: domanda di ricerca, 4 sotto-tesi, obiezioni da affrontare, posizioni no-go
2. `capitoli_second/00_introduzione.tex` — mappa logica della tesi, promesse fatte al lettore
3. `style_patterns.md` — 10 pattern strutturali del mio stile autentico + lista nera anti-tells LLM dalla relazione Armani
4. `C:\Users\andre\OneDrive\andrea\database umano\me.txt` — chi sono, valori, visione politica, come penso
5. `C:\Users\andre\OneDrive\andrea\database umano\tone_of_voice.txt` — il mio tono di voce naturale
6. `tesi_constraints.md` — vincoli formali: triennale, 30-40 pagine contenuto puro, densita come vincolo dominante
7. `CLAUDE.md` — regole operative complete del progetto
8. `references.bib` — bibliografia attuale (chiavi CamelCase `CognomeAnno`)
9. Tutti i capitoli in ordine: `capitoli_second/01_part_fondamenta.tex`, `02_part_riforme.tex`, `03_ndc_adeguatezza.tex`, `04_sfide_strutturali.tex`, `05_conclusioni.tex`

Dopo la lettura devi avere in testa:
- Le 4 sotto-tesi e la loro mappatura sui capitoli
- Le 4 obiezioni che la tesi deve affrontare esplicitamente
- I 6 no-go (cosa NON sostengo)
- I 10 pattern stilistici da usare e la lista nera da evitare
- Lo stato di ogni capitolo: cosa c'e, cosa manca, cosa e debole

---

## FASE 1 — Rafforzamento bibliografico (workflow, 6 agenti paralleli)

**5 agenti capitolo (uno per cap 01-05) + 1 agente grafo citazionale, tutti in parallelo.**

### Ogni agente-capitolo deve:

**Verificare ogni citazione esistente:**
- Per ogni `\cite{Chiave}` nel suo capitolo, prendere autore/titolo/anno da `references.bib`
- Usare `verify_citation` per confermare che la fonte esiste ed e attribuita correttamente
- Se la citazione e sbagliata (autore errato, anno errato, paper ritrattato): CORREGGERLA nella voce BibTeX
- Se la citazione punta a una fonte inesistente: trovare il paper corretto via `search_literature` e aggiornare

**Cercare letteratura mancante per rafforzare il capitolo:**
Lanciare almeno 3 query `search_literature` mirate alla sotto-tesi del capitolo:
- Cap 1 (fondamenta): "PAYG pension theoretical foundations welfare economics", "notional defined contribution scheme design", "intergenerational social contract pension economic theory"
- Cap 2 (riforme): "Italian pension reform 1995 2011 evaluation long-term", "pension spending GDP Southern Europe demographic transition", "Fornero reform labor market impact Italy"
- Cap 3 (adeguatezza): "pension adequacy NDC reform proposals Europe", "minimum pension guarantee contributory systems", "automation tax robot tax pension financing", "separation welfare pension spending Italy"
- Cap 4 (strategie individuali): "supplementary pension Italy second pillar coverage", "Generation Z retirement gap financial planning", "TFR severance pay pension fund Italy", "lifecycle investment pension fund asset allocation"
- Cap 5 (conclusioni): "pension sustainability adequacy trade-off policy", "individual agency pension system institutional design"

Per ogni paper trovato con citation count > 15 e anno >= 2016:
- Usare `get_paper_neighbors` per esplorare il vicinato
- Se il paper aggiunge evidenza a una sotto-tesi, contesta una posizione sostenuta, o rappresenta lo stato dell'arte su un punto trattato: inserirlo. Scrivere la voce BibTeX, aggiungere il `\cite{}` nel punto giusto del capitolo, e se necessario aggiungere 1-2 frasi di contestualizzazione nel testo

**Sostituire fonti grigie dove possibile:**
Se il capitolo cita video YouTube, slide del corso, o siti web, e PapersFlow trova un paper peer-reviewed che sostiene lo stesso punto: sostituire la fonte grigia col paper. Le fonti grigie restano solo se nessun paper copre quel punto specifico.

### L'agente grafo citazionale deve:

Usare `get_citation_graph` su questi paper fondamentali:
- Barr & Diamond 2009, DOI: 10.1111/j.1468-246x.2009.01327.x
- Chlon-Dominczak, Franco, Palmer 2012 "First Wave of NDC Reforms", DOI: 10.1596/9780821388488_ch02
- Cercare via `search_literature`: "Italy pension expenditure long-term projection Ragioneria Generale"
- Cercare via `search_literature`: "NDC Italy transition distributive effects"

Poi `expand_citation_graph` di 1 hop. Confrontare i paper piu citati del grafo con `references.bib`. I paper con > 50 citazioni che la tesi non cita e DOVREBBE citare vanno aggiunti — scrivere la voce BibTeX e indicare in quale capitolo e in quale punto inserirli.

---

## FASE 2 — Verifica e correzione dati (workflow, 5 agenti paralleli, uno per capitolo)

Per OGNI dato numerico nel capitolo (percentuali PIL, tassi di sostituzione, importi euro, proiezioni demografiche, coefficienti, aliquote):

1. Identificare la fonte dichiarata nel `\cite{}` piu vicino
2. Verificare:
   - Dati MEF/RGS: leggere `fonti/Rapporto-2025-n.26.pdf` e `fonti/Rapporto-2025-n26-NdA.pdf` e confrontare
   - Dati da paper: usare `fetch` su PapersFlow per recuperare l'abstract e confrontare
   - Dati da fonti grigie: cercare con `search_literature` un paper che riporti lo stesso dato
3. Se il dato e ERRATO: **correggerlo immediatamente** nel testo LaTeX con il valore giusto
4. Se il dato e NON VERIFICABILE e non riesci a trovare fonte alternativa:
   - Se il dato e critico per l'argomento: riscrivere il passaggio usando dati che HAI verificato
   - Se il dato e accessorio: eliminarlo e rafforzare l'argomento per altra via
5. Se un dato non ha `\cite{}`: trovare la fonte giusta e aggiungere la citazione

**Per ogni `\todo{}` esistente nel capitolo:** risolverlo. Trovare il dato, riscrivere il passaggio, o eliminare la necessita del dato. Nessun `\todo{}` sopravvive a questa fase.

---

## FASE 3 — Coerenza argomentativa (1 subagente singolo, legge tutto)

Questo agente deve aver letto la costituzione e l'introduzione. Poi per ogni capitolo, paragrafo per paragrafo:

**Test di coerenza (per ogni paragrafo):**
1. Quale delle 4 sotto-tesi sostiene? Se nessuna: tagliare o riscrivere
2. Aggiunge conoscenza nuova? Se no: eliminare (densita e il vincolo dominante)
3. E coerente con la funzione del capitolo dichiarata in `00_introduzione.tex`?

**Problemi da RISOLVERE (non segnalare):**
- Paragrafi orfani → tagliare o riscrivere agganciandoli a una sotto-tesi
- Ripetizioni tra capitoli → tenere la versione migliore, eliminare l'altra
- Gap logici → scrivere il passaggio mancante
- Contraddizioni interne → risolvere a favore della posizione piu coerente con la costituzione

**Questioni strutturali da risolvere definitivamente:**
- Il "Contributo sull'Automazione" e promesso nella Domanda 2 dell'introduzione. Verificare se e trattato nel cap 3 o nelle conclusioni. Se si: bene. Se no: o scrivere una sezione dedicata (se i dati lo sostengono — cercare via PapersFlow "automation tax pension financing" per avere materiale) oppure riformulare la Domanda 2 nell'introduzione eliminando la promessa. Non lasciare promesse non mantenute.
- Le conclusioni (cap 5) devono rispondere esplicitamente alle 3 domande di ricerca dell'introduzione. Se una risposta manca: scriverla.
- La mappatura sotto-tesi → capitoli nella costituzione deve corrispondere a quello che i capitoli fanno. Se non corrisponde: aggiornare la costituzione (`tesi_research_question.md`), non i capitoli (i capitoli sono il testo definitivo).

---

## FASE 4 — Riscrittura stilistica definitiva (workflow, 5 agenti paralleli)

Questa e la fase che trasforma una tesi corretta in una tesi MIA. Ogni agente riscrive un capitolo.

Ogni agente DEVE leggere prima di scrivere:
- `style_patterns.md` (10 pattern + lista nera Armani)
- `C:\Users\andre\OneDrive\andrea\database umano\tone_of_voice.txt`
- `C:\Users\andre\OneDrive\andrea\database umano\me.txt`
- La sezione "Il mio stile accademico" di `CLAUDE.md`

### Operazioni obbligatorie, frase per frase:

**ELIMINARE (senza eccezioni):**
- Em dash (—) → virgola o punto
- "In conclusione", "in sintesi", "e importante sottolineare", "vale la pena notare"
- Aperture con "Tuttavia," o "Inoltre," come prima parola del paragrafo
- "Nel corso degli anni", "negli ultimi anni", "in tempi recenti" → date precise
- Aggettivi gemelli vuoti ("dettagliata e approfondita", "complesso e articolato")
- Verbi-tappabuchi ("rappresenta", "incarna", "abbraccia", "sottolinea")
- "Questo X" / "tale Y" come ripresa anaforica vaga → ripetere il sostantivo
- Frasi che annunciano cosa si sta per dire → entrare direttamente nell'argomento
- Corsivi decorativi su concetti tecnici (NDC, PAYG, TFR non vanno in corsivo se gia introdotti)
- Participi presenti incollanti ("sottolineando come", "evidenziando che", "mettendo in luce")
- Sostantivi astratti vaghi ("una vasta gamma", "una serie di") → numeri precisi

**COSTRUIRE (dovunque manca):**
- Alternanza frasi brevi/lunghe senza ritmo prevedibile
- "Perche" esplicito (o equivalente causale) dopo ogni claim importante — pattern 3
- Aperture di sezione con stake dichiarato: non "questo capitolo analizza X" ma "X e il meccanismo che ha scaricato il rischio sull'individuo" — pattern 7
- Ambivalenza esplicita dove i dati confliggono: "c'e una lettura contabile che dice X, ce n'e una distributiva che dice Y" — pattern 4
- Almeno un'anafora per capitolo nei punti di massima intensita argomentativa — pattern 2
- Controfattuali come strumento dimostrativo: "senza la riforma Fornero, il rapporto sarebbe..." — pattern 6
- Conclusioni di capitolo senza fiocco: almeno una tensione lasciata aperta — pattern 10
- Concretezza: ogni passaggio teorico ancorato a dato o esempio numerico — pattern 8

**NON TOCCARE:**
- Il contenuto argomentativo (quello e gia stato sistemato in Fase 3)
- Le formule LaTeX e gli ambienti `equation`/`align`
- Le citazioni `\cite{}` (quelle sono gia state sistemate in Fase 1)
- La struttura section/subsection/paragraph

**Test finale su ogni paragrafo riscritto:**
"Se Andrea leggesse questo paragrafo tra sei mesi, lo riconoscerebbe come suo per sostanza, posizioni e angolazione? Lo riconoscerebbe come scritto per una tesi e non per un post?" — entrambi devono essere veri.

---

## FASE 5 — Assemblaggio, compilazione, commit (main loop)

1. Integra il lavoro di tutte le fasi nei file `.tex` e in `references.bib`
2. Fai un check finale che non ci siano:
   - `\todo{}` residui (devono essere ZERO)
   - Citazioni `\cite{}` senza voce in `references.bib`
   - Voci in `references.bib` mai citate in nessun capitolo (rimuovile)
   - Em dash, "in conclusione", o altri tell dalla lista nera
3. Compila:
   ```
   pdflatex second_main.tex && bibtex second_main && pdflatex second_main.tex && pdflatex second_main.tex
   ```
   Obiettivo: 0 errori LaTeX, 0 warning BibTeX, 0 citazioni non risolte
4. Verifica che il contenuto sia tra 30-50 pagine. Se sfora: taglia i passaggi piu deboli (quelli che il test di coerenza della Fase 3 aveva classificato come meno critici)
5. Committa TUTTO in un unico commit descrittivo:
   `feat(definitiva): revisione completa — bibliografia verificata, dati corretti, coerenza risolta, stile autoriale`

---

## Vincoli operativi non negoziabili

- **Branch:** verifica di essere su `sviluppo-test-agente` prima di qualsiasi modifica. Mai toccare `main`.
- **Dati:** mai inventare numeri. Se non lo trovi e non riesci a riscrivere intorno, usa formulazione prudente con fonte piu vicina. Ma questo e l'ultimo resort, non la via comoda.
- **Citazioni:** chiavi CamelCase `CognomeAnno`, coerenti con lo stile di `references.bib`. Nuove voci vanno aggiunte a `references.bib`, non altrove.
- **LaTeX:** `\cite{}` per citazioni, `equation`/`align` per formule display, `\( \)` per inline. `\bibliographystyle{unsrtnat}` e `\bibliography{references}` sono in `capitoli_second/06_bibliografia.tex` e non vanno toccati.
- **Gerarchia normativa:** costituzione (`tesi_research_question.md`) > introduzione (`00_introduzione.tex`) > capitoli. Se trovi conflitto tra costituzione e introduzione, FERMATI e chiedi. Per tutto il resto, decidi tu.
- **Nessun file nuovo:** lavora sui file esistenti. Non creare report, log, o documenti intermedi.

## Orchestrazione

- Fase 0: main loop, sequenziale
- Fase 1: workflow — 6 agenti paralleli (5 capitoli + 1 grafo)
- Fase 2: workflow — 5 agenti paralleli (1 per capitolo)
- Fase 3: 1 subagente singolo (deve leggere tutto, non parallelizzabile)
- Fase 4: workflow — 5 agenti paralleli (1 per capitolo)
- Fase 5: main loop, sequenziale

Massimizza il parallelismo. Non aspettare una fase per lanciare quella dopo SE sono indipendenti (Fase 1 e Fase 2 POSSONO andare in parallelo; Fase 3 e 4 dipendono da 1 e 2).

Mostrami il piano di esecuzione, poi parti senza aspettare ulteriore conferma.
```

---

## Note d'uso

- **Prerequisito:** PapersFlow deve essere autenticato prima di lanciare il prompt
- **Budget:** usa `+800k` per dare spazio sufficiente ai subagenti
- **Tempo stimato:** 20-40 minuti con parallelismo massimo
- **Cosa aspettarsi:** il prompt chiede di mostrare il piano e poi partire senza conferma. Se vuoi un checkpoint intermedio, aggiungi "fermati dopo ogni fase e mostrami cosa hai fatto" alla fine
- **Se vuoi una sola fase:** aggiungi "esegui solo la FASE N" alla fine del prompt
- **Se PapersFlow non risponde:** i subagenti devono comunque completare il lavoro usando le fonti locali in `fonti/` — PapersFlow e un potenziamento, non una dipendenza bloccante
