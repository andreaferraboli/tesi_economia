---
description: Produce un dossier analitico professionale di tutte le fonti in fonti/
---

Argomento opzionale per filtrare le fonti: $ARGUMENTS
Se vuoto, processa tutte le fonti in `fonti/`.

## Obiettivo
Produrre `fonti/_dossier_fonti.md`: un dossier di ricerca strutturato, utile
come base di lavoro per la scrittura dei capitoli. Non un indice generico,
non un riassunto da Wikipedia. Un documento che permetta all'autore di
sapere, per ogni fonte, quali dati puo citare e quali posizioni puo
sostenere o contestare.

## Procedura

1. Leggi `tesi_research_question.md` per avere a mente le 4 sotto-tesi
2. Leggi `capitoli_second/00_introduzione.tex` per la mappa dei capitoli
3. Per ogni file in `fonti/`, leggi il contenuto completo
   - PDF: usa Read con il parametro pages se il PDF e grande, leggi tutto
   - .txt e .md: leggi integralmente
4. Per ogni fonte produci una scheda secondo lo schema sotto
5. Salva il dossier in `fonti/_dossier_fonti.md`

## Schema obbligatorio per ogni fonte

Ogni fonte deve avere una scheda con TUTTI questi campi. Se un campo non e
applicabile, scrivi esplicitamente "n/a" con motivo, non saltare il campo.

```markdown
### [Numero progressivo]. [Titolo file in `fonti/`]

**Tipo:** paper accademico / report istituzionale / articolo di opinione /
  manuale didattico / trascrizione / altro
**Autore/i:** nome cognome (se istituzione: nome ente)
**Anno:** YYYY
**Editore / rivista / istituzione:** ...
**Pagine totali:** N
**Lingua:** italiano / inglese
**Affidabilita come fonte:**
  - dato istituzionale (citabile come fatto)
  - peer-reviewed (citabile come evidenza)
  - opinione qualificata (citabile come posizione)
  - materiale didattico (citabile come sintesi)
  - solo ispirazione narrativa (NON citabile in bibliografia)

**Tesi centrale dell'autore (1-3 righe):**
Cosa l'autore sostiene, in forma assertiva. Non "la fonte parla di X",
ma "Bosi sostiene che il NDC ha risolto la sostenibilita ma...".

**Posizioni dell'autore degne di citazione critica:**
Elenco di 3-8 affermazioni esplicite dell'autore che esprimono UN GIUDIZIO,
una valutazione, una raccomandazione, una critica. Sono le frasi che diventano
il nucleo critico della tesi. Per ognuna:
  - Citazione testuale o parafrasi fedele (con virgolette se testuale)
  - Pagina o sezione di riferimento
  - Posizione che esprime (favorevole/contraria a cosa, quale meccanismo
    sostiene, quale obiezione muove)
  - Rapporto con le posizioni dell'autore della tesi: allineata / parzialmente
    allineata / da contestare / utile come contraddittorio

**Dati numerici estratti (per uso diretto nella tesi):**
Tabella di tutti i dati numerici significativi presenti nella fonte.
Formato:
  | Dato | Valore | Unita | Anno riferimento | Pagina | Possibile uso in tesi |
Esempi di dati da estrarre sempre quando presenti:
  - tassi di sostituzione (lordo, netto, per categoria)
  - eta pensionabile (di vecchiaia, anticipata, per categoria)
  - speranza di vita e coefficienti di trasformazione
  - aliquote contributive (lavoratore, datore, totale)
  - spesa pensionistica in % di PIL (storico e proiezioni)
  - numero pensionati per categoria
  - importo medio pensione (lordo, netto, per categoria)
  - rendimenti netti di fondi pensione (negoziali, aperti, PIP)
  - costi di gestione (ISC) dei fondi pensione
  - patrimonio fondi pensione, adesioni
  - tassazione contributi, rendimenti, prestazioni
  - dati demografici (natalita, immigrazione, popolazione attiva)
Non lasciare dati fuori. Se un dato e nella fonte, va nella tabella.

**Concetti tecnici definiti o discussi:**
Lista dei termini tecnici che la fonte definisce o usa in modo distintivo
(es: "neutralita attuariale secondo Bosi 2024, pag. 42"). Utile per
costruire il glossario operativo.

**Metodologia (per paper):**
Se e un paper accademico: dataset usato, periodo, tecnica econometrica
o modello, eventuali limitazioni dichiarate dall'autore.

**Mappatura su sotto-tesi della tesi:**
Per ognuna delle 4 sotto-tesi (ST1 sostenibilita, ST2 inadeguatezza per
nuovi entranti, ST3 riforme possibili e costi, ST4 strategie individuali):
  - Pertinente: si/no
  - Come supporta o contesta la sotto-tesi
  - Quale capitolo specifico potrebbe usarla

**Capitoli della tesi in cui usarla:**
Mappa numerica sui 9 capitoli, con peso (primario / secondario / accessorio).

**Citazione BibTeX gia pronta:**
```bibtex
@article{autore_anno,
  author = {...},
  title = {...},
  journal = {...},
  year = {...},
  pages = {...},
  url = {...}
}
```
Usa il tipo BibTeX corretto: @article, @book, @techreport, @misc, @incollection.

**Note critiche dell'analista:**
3-5 righe in cui l'agente segnala:
  - eventuali bias dichiarati o impliciti della fonte
  - punti su cui la fonte e debole o poco aggiornata
  - dove la fonte e particolarmente forte e va citata come riferimento
  - se la fonte e in conflitto con altre fonti del dossier (e quali)
```

## Output finale: indici sintetici a fine dossier

Dopo le schede individuali, aggiungi tre tavole di sintesi che permettano
all'autore di orientarsi rapidamente.

### Indice 1: fonti per sotto-tesi

| Sotto-tesi | Fonti primarie | Fonti secondarie |
|---|---|---|
| ST1 sostenibilita | ... | ... |
| ST2 inadeguatezza | ... | ... |
| ST3 riforme | ... | ... |
| ST4 strategie | ... | ... |

### Indice 2: fonti per capitolo

| Capitolo | Fonti da citare in priorita | Fonti da consultare |
|---|---|---|
| 0 Introduzione | ... | ... |
| 1 Fondamenta | ... | ... |
| ... | ... | ... |

### Indice 3: tabella consolidata dei dati numerici chiave

I dati piu importanti (spesa/PIL, tassi di sostituzione, aliquote, eta
pensionabile, coefficienti di trasformazione) consolidati in un'unica tabella
trasversale alle fonti, con valori comparativi quando diverse fonti riportano
lo stesso dato in modo diverso. Questa tabella e la "miniera" per la tesi.

| Variabile | Valore | Anno | Fonte | Note |
|---|---|---|---|---|

### Indice 4: contraddizioni e disaccordi tra fonti

Sezione critica: dove le fonti si contraddicono, su quali punti, e quale
posizione l'autore puo prendere coerentemente con la tesi centrale.

## Vincoli operativi

- **Non saltare dati**: se sono nella fonte, sono nel dossier
- **Citazioni testuali importanti vanno virgolettate** con pagina precisa
- **Non parafrasare quando l'autore prende posizione**: cita testualmente
  le frasi di giudizio, sono il materiale critico
- **Trascrizioni video**: trattale come opinione qualificata se l'autore
  e identificabile e competente, altrimenti come ispirazione narrativa.
  Vanno citate come `@misc{cognome_anno_video, ...}` con URL se noto,
  oppure non citate in bibliografia ma usate solo come stimolo
- **PDF lunghi**: se >20 pagine, leggi a blocchi e ricostruisci la scheda
  in modo cumulativo, non parziale
- **`libro.md`**: trattalo come manuale di riferimento, estrai capitoli
  rilevanti come sotto-fonti se ha struttura interna
- Non scrivere "sembra che", "potrebbe", "forse" — i campi vanno compilati
  con quello che la fonte effettivamente dice
- Se una fonte non aggiunge nulla al dossier, dillo esplicitamente nella
  scheda invece di gonfiarla
- Il dossier finale deve permettere di scrivere un capitolo della tesi
  SENZA dover riaprire le fonti originali, salvo per verifiche puntuali

## Verifica finale prima di salvare

1. Tutte le fonti in `fonti/` hanno una scheda completa?
2. Tutte le schede hanno dati numerici dove la fonte li conteneva?
3. Tutte le schede hanno citazioni testuali delle posizioni di giudizio?
4. I 4 indici di sintesi sono presenti e popolati?
5. La tabella consolidata dei dati ha tutte le variabili chiave?
6. Le contraddizioni tra fonti sono nominate esplicitamente?

Solo dopo aver verificato, salva `fonti/_dossier_fonti.md` e committa con
`docs: dossier analitico delle fonti per la tesi`.
