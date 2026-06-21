# HANDOFF — stato della tesi e come ripartire

Documento per far ripartire il lavoro da un'altra istanza di un agente.
**Leggi prima** `CLAUDE.md` (regole di progetto, stile, gerarchia delle fonti) e
`tesi_research_question.md` (la costituzione: domanda di ricerca, tesi centrale,
quattro sotto-tesi, posizioni, no-go). Poi questo file per lo stato corrente.
Aggiornato: **2026-06-21**.

---

## 0. Regole d'oro (non negoziabili)
- Si lavora **solo sul branch `main`**. Niente branch alternativi, niente rebase autonomi.
- File di compilazione: **`second_main.tex`**. Bibliografia: **`references.bib`** (root).
- Commit in **italiano**, descrittivi. Chiudere il messaggio col trailer
  `Co-Authored-By:` quando committa un agente.
- **Mai inventare numeri**: solo da fonti verificate in `fonti/`. Dove un dato non è
  confermato su fonte primaria si mette `\todo{VERIFICA DATO}`.
- Stile (vedi CLAUDE.md): niente em dash, niente "Tuttavia/Inoltre" a inizio paragrafo,
  niente "in conclusione/in sintesi"; tono critico; contraddizioni lasciate aperte.

## 1. Cos'è il progetto
Tesi triennale di Economia e Management (relatore **Michele Santoni**) su
**adeguatezza pensionistica e autonomia previdenziale**. Tesi centrale: la riforma
del 1995 ha risolto la sostenibilità contabile scaricando il rischio di inadeguatezza
sull'individuo; per chi entra oggi nel lavoro il pubblico da solo non basta, il
pilastro complementare è necessario, le riforme del pubblico restano possibili ma
costose, mentre l'azione individuale è immediata e a costo politico nullo.

Struttura: **4 capitoli di contenuto + conclusioni**.
| Cap | File | Contenuto | Sotto-tesi |
|-----|------|-----------|------------|
| 0 | `00_introduzione.tex` | Domanda di ricerca, paradosso sostenibilità/adeguatezza, esempio lordo/netto | inquadramento |
| 1 | `01_part_fondamenta.tex` | Teoria previdenza, PAYG vs capitalizzazione, meccanica NDC, storia riforme | ST1, ST2 |
| 2 | `02_part_riforme.tex` | Criticità sistema vigente: demografia, Dini/Fornero, deroghe | ST1, ST2 |
| 3 | `03_ndc_adeguatezza.tex` | Riforme strutturali per l'adeguatezza e loro costi | ST3 |
| 4 | `04_sfide_strutturali.tex` | Diagnosi Gen Z + strategie individuali (TFR, fondi, deducibilità) | ST2, ST4 |
| 5 | `05_conclusioni.tex` | Sintesi 4 sotto-tesi, automazione, responsabilità individuale | tutte |
| — | `06_bibliografia.tex` | Fa solo `\bibliography{references}`. **NON è il capitolo 6.** | — |

## 2. Stato git
- Branch `main`, remoto `https://github.com/andreaferraboli/tesi_economia`.
- Ultimo lavoro di contenuto: commit `8a89b75` "revisione: correzioni puntuali
  cap.3-4, citazioni in italiano, grafici pratici cap.4" (+ questo handoff).
- **Compila pulito: 57 pagine**, 0 errori LaTeX, 0 citazioni irrisolte, 0 warning BibTeX.
- File untracked presenti nella working copy ma **NON da committare**: `_chk.*`
  (validazioni), `.firecrawl/` (scratch), `_old_fe2f160/`, `_perllib/`,
  `_latexdiff.cfg`, `second_main_DIFF.{tex,pdf}` (artefatti latexdiff).

## 3. Cosa è stato fatto nella sessione 2026-06-21 (per tema)
1. **Citazioni in italiano alla radice.** Il `.bst` reale è **`plainnat-cognome.bst`**
   (NON `unsrtnat`). Corretto `" and "` → `" e "` in tre funzioni (`format.names`,
   `format.full.names`, `format.lab.names`): ora ogni citazione multi-autore e l'intera
   bibliografia rendono "Beltrametti e Della Valle", "Bosi e Guerra", ecc.
   **Per applicarlo serve rieseguire bibtex** (rigenera `second_main.bbl`).
2. **Raitano2020 e Marchionne2004** passati da `\citeyearpar` a `\citet` (forma
   classica "Raitano (2020)", non solo l'anno tra parentesi).
3. **Introduzione**: nota a piè sul razionale dell'1,04% di produttività (ipotesi
   armonizzate dell'Ageing Working Group UE); giustificazione del tasso nozionale 1,5%
   dell'esempio (valore prudenziale/illustrativo che isola solo il divario lordo/netto).
4. **§3.2** ("le sei leve"): paragrafo riscritto in **periodi lunghi** (preferenza
   autore: niente frasi spezzate).
5. **§3.2 "tre vie d'uscita"** (indicizzazione): **attribuite esplicitamente** a
   Bevilacqua-Gronchi (verificato sull'articolo "Pensioni: come perequarle").
6. **§3.6** rinominata da "Il costo del non riformare" a **"Il costo di sospendere gli
   adeguamenti automatici"** (titolo più fedele, senza spinta implicita a riformare).
7. **Leva automazione**: il **dettaglio** sta ora in **cap. 3 §3.7** (Acemoglu×2,
   Bacchiocchi ~8 mld, Thuemmel, Furgase, Hotte + la tensione produttività); le
   **conclusioni** ("La domanda che il sistema non ha ancora fatto") sono ora una
   **sintesi** (CasasTorres, Kaplin, Carbonara restano citati lì).
8. **§4.4 (regressività)**: tenuta ma **asciugata** (rimosso il doppione Mazzaferro,
   che resta in §3.6).
9. **Grafici cap. 4** (nuovi, `pgfplots` aggiunto al preambolo):
   - **Fig. 4.1** (§4.7): curve di accumulo garantita 0,5% vs dinamica 4% reale,
     200 €/mese × 40 anni → ~106k vs ~233k. Coordinate calcolate (versamento mensile
     anticipato) per coincidere col testo.
   - **Fig. 4.2** (§4.8): recupero del tasso di sostituzione per profilo col secondo
     pilastro (A 62,3→70,3; B/C 54,9→61,9; D 35,4→39,9). **Ancorato al +7-8 pt di
     MEF_RGS2025**, D più basso (no TFR). Mostra anche che l'antidoto è regressivo.
10. **Spiegazioni**: `04_sfide_e_strategie.md` riscritta da zero (era fuori sync con
    numeri vecchi); `03_riforme_strutturali.md` patchata. **Nuovi**:
    `03_riforme_per_le_medie.md`, `04_strategie_per_le_medie.md`.

## 4. Convenzioni citazioni (importante)
- Preambolo: `\usepackage[authoryear,round,sort]{natbib}` + `\let\cite\citep`.
- `\cite{}` / `\citep{}` → parentetico "(Autore, anno)".
- `\citet{}` → "Autore (anno)", quando l'autore è nominato nella prosa.
- `\citeyearpar{}` → "(anno)" soltanto (usare con parsimonia; preferito `\citet`).
- `\citealp{}` → dentro parentesi manuali, per evitare le doppie tonde.
- Chiavi `CognomeAnno` in CamelCase. Autori istituzionali in acronimo (MEF_RGS, OCPI…).
- **Il join degli autori è "e"** grazie a `plainnat-cognome.bst` (modificato). Se
  ricompare "and", è perché qualcuno ha ripristinato il `.bst` o non ha rifatto bibtex.

## 5. Dati MEF/fonti già verificati (USARE questi, non re-inventare)
- Produttività per occupato reale: media **1,0%** (2025-2070); l'**1,04%** citato è
  l'ipotesi AWG UE; produttività effettiva 2015-2025 = **0,12%** (OCPI).
- PIL reale medio **0,7%**, deflatore **2%** → **PIL nominale ~2,7%** (= capitalizzazione NDC).
- TS lordo dipendente privato: **73,6% (2010) → 58,4% (2070)**; netto 2070 64,1%
  (sola obbligatoria), risale verso il 66% con complementare.
- Indice dipendenza anziani: **37,8% (2024) → 62,3% (2070)**.
- Picco spesa/PIL **17,1%** (2042-43), rientro a **14,0%** nel 2070.
- Blocco automatismi (controfattuale RGS): solo requisiti **+36 pp**, solo coefficienti
  **+22 pp**, entrambi **+58 pp** di debito/PIL al 2070.
- **Simulazione cap. 4** (reale): S0 = 25.000, w = 1,0%, γ = 0,7%, c = 0,33 (0,25
  autonomo), coefficiente 2067 = **5,0%** (estrapolazione dell'autore, dichiarata in
  nota), 40 anni. TS lordo: **A 62,3% · B 54,9% · C 54,9% · D 35,4%**; montanti
  ~459k/405k/404k/261k €. Spread A-D ≈ 27 punti.
- COVIP: ISC a 10 anni negoziali **0,49%**, aperti **1,35%**, PIP **2,17%**; TFR ~2,4%.
- Altiparmakov (WP_208/22): differenziale fondi-PAYG **−0,6** (media dei differenziali
  per-paese sui dati non arrotondati, NON 2,7−2,2 sugli arrotondati). Non "correggerlo".

## 6. Fatti non ovvi / trappole da non regredire
- **Due 1,5% diversi**: l'1,5% dell'esempio introduttivo è il tasso nozionale
  illustrativo; l'1,5% di Bevilacqua-Gronchi è lo sconto sull'indicizzazione al PIL.
  Non confonderli.
- **`fonti/wp_118.pdf` = Beltrametti-Della Valle 2011** (debito implicito), NON Altiparmakov.
- Coefficiente 2067 = 5,0% è un'**estrapolazione** dichiarata in nota (il MEF non lo
  pubblica a quella data). Prudenziale: un valore più basso abbasserebbe le pensioni
  simulate ma le proporzioni fra profili restano.
- La leva automazione **non** è nella matrice operativa di §3.7 (è di ordine diverso:
  agisce sul denominatore della base contributiva). Dettaglio in §3.7, sintesi nelle conclusioni.
- §4.4 (regressività) è l'**architrave** fra simulazioni e conclusioni (ST2/Domanda 3):
  non rimuoverla.
- Numerazione sezioni: i **commenti** dentro i `.tex` (`% --- §4.7 ...`) sono sfasati
  di uno rispetto alla numerazione del PDF (il primo paragrafo di capitolo non ha
  `\section`). Fidarsi della numerazione del PDF.

## 7. Compilazione (Windows / MiKTeX)
- Dalla **root** del progetto. Sequenza completa:
  `pdflatex second_main` → `bibtex second_main` → `pdflatex` → `pdflatex`.
  Il giro `bibtex` è necessario per applicare la correzione "and→e".
- **Gotcha lock**: se `second_main.pdf` è aperto nel visualizzatore, pdflatex dà
  "I can't write on file second_main.pdf". Chiudere il viewer. Per validare senza
  chiudere: `pdflatex -jobname=_chk second_main.tex` (+ `bibtex _chk` + 2 pdflatex),
  poi controllare `_chk.log` e rendere le pagine con `pdftoppm -png -r 70 -f N -l M _chk.pdf out`.
- In PowerShell 5.1 gli here-string con virgolette si rompono: per i commit usare
  `git commit -F file` o un heredoc da Git Bash.
- `pgfplots` richiede una distro TeX recente (MiKTeX la installa al volo); compat=1.18.

## 8. Spiegazioni (cartella `spiegazioni/`)
Materiale di studio per il colloquio con Santoni, **non** parte della tesi compilata.
- `00_…` → `05_conclusioni.md`: guide allo studio per capitolo (come difendere ogni
  frase). **Quando cambi i numeri o la struttura di un capitolo, aggiorna la relativa
  guida**: la 04 era gravemente fuori sync prima del 2026-06-21 (aveva g=1,5% e i
  vecchi TS), ora è allineata.
- `03_riforme_per_le_medie.md`, `04_strategie_per_le_medie.md`: spiegazioni dei
  capitoli 3 e 4 "per un ragazzo delle medie" (linguaggio semplice, metafore).
- `domande_prof.md`, `riassunto_colloquio.md`, `vocabolario.md`,
  `vocabolario_difficile.md`: supporto al colloquio.

## 9. Identità autoriale (per scrivere "come l'autore")
Leggere prima di scrivere: `C:\Users\andre\OneDrive\andrea\database umano\me.txt`,
`...\tone_of_voice.txt`, e `style_patterns.md` (root). Posizioni di partenza:
liberale-libertaria d'ordine, neutralità attuariale come giustizia, scetticismo verso
regimi speciali e pensioni anticipate generalizzate, secondo pilastro come complemento
necessario, no patrimoniale, no obbligo di adesione, no ritorno al retributivo.

## 10. Lavori aperti / possibili prossimi passi
- `\todo` residui (dati da confermare su fonte primaria): cap. 1 deficit 1970-73;
  cap. 3 stima recupero assegno di accompagnamento e 30-40 mld separazione
  previdenza/assistenza; cap. 4 alcuni calcoli propri (riscatto, contribuzione figurativa).
- Se l'autore chiede più "consulenza" nel cap. 4: si possono aggiungere altri due
  grafici già progettati ma non realizzati (istogramma TS per profilo; valore di 1 €
  versato per età). pgfplots è già nel preambolo.
- Verificare i costi ISC e il 2,4% TFR su `fonti/relazione_per_lanno_2024.pdf` (COVIP)
  e i tassi internazionali su OECD Pensions at a Glance se servisse.

## 11. Mappa file rapida
- `second_main.tex` — compilazione + preambolo (natbib, hyperref, **pgfplots**, alias `\cite`).
- `capitoli_second/0X_*.tex` — i capitoli (vedi tabella §1).
- `references.bib` — bibliografia. `plainnat-cognome.bst` — stile (cognome per primo, join "e").
- `tesi_research_question.md` — costituzione. `CLAUDE.md` — regole e stile. `style_patterns.md` — pattern di stile.
- `tesi_constraints.md` — vincoli formali (30-40 pagine di contenuto, 4-7 per capitolo).
- `fonti/` — biblioteca PDF (leggere col testo pieno: tool Read sui PDF, o `pdftotext`).
- `spiegazioni/` — guide allo studio (vedi §8).
