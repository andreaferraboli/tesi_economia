# HANDOFF — stato della tesi e come ripartire

Documento per far ripartire il lavoro da un'altra istanza di Claude Code (altro PC).
Leggi **prima** `CLAUDE.md` (regole di progetto, stile, gerarchia delle fonti) e
`tesi_research_question.md` (costituzione). Poi questo file per lo stato corrente.

## 1. Cos'è il progetto
Tesi triennale di Economia e Management su adeguatezza pensionistica e autonomia
previdenziale. Documento LaTeX multi-file. File di compilazione: `second_main.tex`.
Capitoli in `capitoli_second/`, fonti in `fonti/`, bibliografia in `references.bib`.
Si lavora **solo sul branch `main`**. Commit in italiano.

## 2. Ultimo stato git
- Ultimo commit pushato: `4952c3c` — "revisione: cap.4 pratico, calibrazione NDC su
  dati MEF, debito implicito e bibliografia cognome-nome".
- Tutto pushato su `origin/main` (https://github.com/andreaferraboli/tesi_economia).
- Working tree pulito al momento dell'handoff (a parte questo file).

## 3. Cosa è stato fatto in questa sessione (per tema)
1. **Citazioni in stile economista.** `natbib` passato a `[authoryear,round,sort]`;
   `\let\cite\citep` (così `\cite` è parentetico "(Autore, anno)"). In prosa dove
   l'autore è nominato si usa `\citet`/`\citeyearpar`; **dentro parentesi manuali si usa
   `\citealp`** per evitare le doppie tonde. Bibliografia: stile **locale**
   `plainnat-cognome.bst` (copia di plainnat con nome stampato "Cognome, Nome").
   Link hyperref tutti neri e cliccabili (`citecolor=black, urlcolor=black`).
2. **Correzioni dal colloquio col relatore** (trascrizione discussa con l'utente):
   - Esempi di tasso di sostituzione riformulati come **illustrativi** del divario
     lordo/netto; eliminata l'ipotesi fuorviante.
   - Tabella delle "sei leve" (cap. 3): corretta la riga **debito pubblico** (non
     peggiora Sp/PIL nel breve), aggiunta spiegazione del meccanismo (numeratore vs
     base/PIL, orizzonti temporali, problema redistributivo dell'immigrazione).
   - Marchionne (cap. 3): esplicitato il **doppio onere** della transizione che la sua
     proposta sottostima; qualificata la fonte (Moneta e Credito).
3. **Valore di `g` corretto + simulazione cap. 4 riscritta con salario crescente.**
   La capitalizzazione NDC è agganciata al PIL nominale, non a 1,5%. Vedi §4 e §5.
4. **Debito implicito (cap. 3).** Paragrafo riscritto con Franco-Marino-Zotteri (2004)
   e Altiparmakov (2011): debito pensionistico implicito = valore attuale delle
   promesse al netto dei contributi futuri; **dibattito** sul fatto che NON vada
   sommato al debito convenzionale (dipende dal tasso di sconto). Nuove voci in
   `references.bib`: `FrancoMarinoZotteri2004`, `Altiparmakov2011`.
5. **Cap. 4 reso pratico ("consulenza").** Smussato il ponte vago prima delle sezioni
   operative; aggiunta §4.10 **"Sintesi operativa"** con checklist delle mosse in
   ordine di priorità (`tab:checklist`). Mantenuta la tesi critica sull'accesso
   diseguale. Scelta concordata: categorie + criteri, **niente nomi commerciali**.
6. **`fonti_da_scaricare.md`** creato: lista mirata di fonti da scaricare (vedi §6).

## 4. Dati MEF già verificati (estratti da `fonti/Rapporto-2025-n.26.pdf` con pdftotext)
Usare questi, NON re-inventare:
- Produttività per occupato (reale): **media 1,0%** (2025-2070), picco 1,5% (~2042),
  1,2% al 2070. Le **retribuzioni crescono in media come la produttività**.
- PIL reale: **media 0,7%** annuo. Deflatore/inflazione: **2%** → **PIL nominale ~2,7%**.
- Tassi di sostituzione, dipendente privato, ipotesi base:
  - lordo: **73,6% (2010) → 58,4% (2070)**;
  - netto 2070: **64,1%** sola obbligatoria, **74,2%** con complementare;
  - autonomi netto 2070: 66,9% obbligatoria, 84,3% con complementare.
- Parametri della simulazione cap. 4 (in termini reali): retribuzione d'ingresso
  S0 = 25.000, crescita reale w = 1,0%, capitalizzazione reale γ = 0,7%, c = 0,33
  (0,25 autonomo), coefficiente δ = 5,0%, 40 anni. Risultati TS lordo:
  **A 62,3% · B 54,9% · C 54,9% · D 35,4%** (montanti ~459k/405k/404k/261k euro reali).
- COVIP (da verificare col PDF, vedi §6): ISC negoziali ~0,49%, aperti ~1,72%,
  PIP ~2,61%; TFR ~2,4%.

## 5. Fonti già in `fonti/` (NON richiederle all'utente)
MEF Rapporto n.26 + NdA; Gronchi e Bevilacqua-Gronchi (Lavoce); OCPI ("Pensioni, la
spesa continua a salire"); **Marchionne** ("Guarda_Una_proposta_di_riforma..." =
articolo Moneta e Credito); Franco-Tommasino (s10272-020-0874-4); Mazzaferro
("div_class_title_the_transition_to_ndc..."); Altiparmakov **2022** (WP_208); slide
del corso; trascrizioni video; `libro.md`. Le fonti si leggono col testo pieno via
`pdftotext` (Git Bash), non solo abstract.

## 6. Prossimo passo concreto (in attesa dell'utente)
L'utente scaricherà le fonti elencate in **`fonti_da_scaricare.md`** dentro `fonti/`.
Priorità 1,2,4,5 sono sufficienti a chiudere le verifiche aperte:
- **Franco-Marino-Zotteri 2004** e **Altiparmakov 2011** → verificare/approfondire il
  paragrafo sul debito implicito (cap. 3): finora basato su abstract + WebSearch.
- **COVIP Relazione 2024** → verificare i costi ISC e il 2,4% TFR della checklist (cap. 4).
- **OECD Pensions at a Glance 2023** → verificare tassi di sostituzione intl e rendimenti 4-6%.
Quando l'utente dice che i PDF sono in `fonti/`, leggerli interi e aggiornare il testo.

## 7. Note operative / gotchas
- **MCP papersflow**: restituisce SOLO abstract + metadati, non il full text. Per il
  testo pieno servono i PDF in `fonti/`.
- **Compilazione** (Windows/MiKTeX): dalla root del progetto. In PowerShell usare
  `Push-Location "C:\...\tesi_economia"` prima di `pdflatex`, altrimenti "file not found".
  Sequenza: `pdflatex` → `bibtex second_main` → `pdflatex` ×2. Il PDF esce 55 pagine.
- **Commit message**: scriverlo in un file e usare `git commit -F file` (gli here-string
  con virgolette si rompono in PowerShell 5.1). Chiudere con il trailer Co-Authored-By.
- **Stile** (da CLAUDE.md): niente em dash, niente "Tuttavia/Inoltre" a inizio paragrafo,
  niente "in conclusione"; `\euro{}` per l'euro; mai inventare numeri (solo fonti in `fonti/`).
- **Citazioni**: `\citep` di default; `\citet` se autore in prosa; `\citeyearpar` per
  solo anno; `\citealp` dentro parentesi manuali.

## 8. Mappa file
- `second_main.tex` — compilazione + preambolo (natbib, hyperref, alias \cite).
- `capitoli_second/00_introduzione.tex` — struttura tesi + esempio lordo/netto.
- `capitoli_second/03_ndc_adeguatezza.tex` — sei leve, debito implicito, Marchionne/carve-out.
- `capitoli_second/04_sfide_strutturali.tex` — simulazioni Gen-Z, secondo pilastro, §4.10 checklist.
- `capitoli_second/05_conclusioni.tex`, `06_bibliografia.tex`.
- `references.bib` — bibliografia (autori istituzionali in acronimo: MEF-RGS, OCPI, CeRP...).
- `plainnat-cognome.bst` — stile bibliografico locale (cognome per primo).
- `fonti_da_scaricare.md` — fonti da reperire.
