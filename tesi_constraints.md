# Vincoli formali della tesi

## Inquadramento istituzionale
- **Tipo**: Tesi di laurea triennale
- **Corso**: Economia e Management
- **Universita**: Unimi (logo presente in `images/`) — da confermare
- **Relatore**: ancora da specificare
- **Lingua**: italiano

## Vincolo di lunghezza
- **Contenuto puro dei capitoli: 30-40 pagine totali**
- NON sono 30-40 pagine per capitolo: e il totale di tutto il corpo della tesi
- Esclusi: frontespizio, indice, bibliografia, eventuali appendici, ringraziamenti
- Significa che ogni capitolo della mappatura attuale deve stare in
  **circa 4-7 pagine di contenuto** (variando per peso argomentativo)

## Implicazioni di stile derivate dal vincolo di lunghezza

La densita e il vincolo dominante. Concretamente:

1. **Ogni paragrafo deve produrre o sostenere un'affermazione**.
   Niente paragrafi di transizione, niente paragrafi descrittivi che ripetono
   cosa si sta per dire.
2. **Niente storia generale del sistema pensionistico**.
   Il Capitolo 2 (riforme) non e un riassunto cronologico: e una selezione
   delle riforme che hanno prodotto la condizione attuale, lette dalla
   prospettiva della tesi centrale.
3. **Le formule vanno usate solo dove producono argomento**.
   Mostrare la formula del montante NDC ha senso se serve a dimostrare la
   sotto-tesi 2 (carriere discontinue → montante basso). Non se decora.
4. **I dati vanno scelti, non accumulati**.
   Un dato MEF ben scelto vale 5 dati generici. Per ogni dato chiediti:
   sostiene quale sotto-tesi?
5. **Le citazioni sostengono o sfumano una posizione, non riassumono autori**.
   Niente "Bosi (2024) sostiene che... Artoni (2003) afferma che... Lavoce
   nota che...": e un compito di liceo. Va invece costruita la tua posizione
   appoggiandoti agli autori dove serve.

## Distribuzione di pagine indicativa (su 35 pagine totali)

| Capitolo | Pagine target | Densita argomentativa |
|---|---|---|
| 0 Introduzione | 2-3 | massima: domanda di ricerca, tesi centrale, mappa |
| 1 Fondamenta | 3-4 | concetti minimi necessari |
| 2 Riforme | 3-4 | selezione mirata, non cronologia |
| 3 NDC e adeguatezza | 5-6 | **cuore tecnico** |
| 4 Sfide strutturali | 3-4 | demografia, mercato del lavoro |
| 5 Parte lavoratore | 5-6 | **cuore operativo, step-by-step** |
| 6 Secondo pilastro | 4-5 | matematica fondo pensione, TFR |
| 7 Patrimonio integrato | 3-4 | estensione ETF/PIC/PAC |
| 8 Conclusioni | 2 | sintesi tesi centrale |
| **Totale** | **30-38** | |

Questa distribuzione e indicativa. Va validata contro `00_introduzione.tex`
e ricalibrata se l'introduzione assegna pesi diversi.

## Status dei capitoli esistenti

I file `.tex` gia presenti in `capitoli_second/` sono **bozze generate da AI
sotto spunti e correzioni dell'autore**. Conseguenze operative:

- **Non sono affidabili come reference di stile**: probabilmente contengono
  tic LLM da bandire (vedi sezione anti-tells nel CLAUDE.md)
- **Sono affidabili come indicatori di contenuto**: cosa l'autore voleva
  trattare in ogni capitolo, quali fonti pensava di usare, quali argomenti
  ha gia validato
- **Vanno riscritti, non corretti superficialmente**. Una rilettura di
  superficie lascia in piedi la struttura AI sottostante. Meglio rifare un
  capitolo da zero, partendo dalla costituzione (`tesi_research_question.md`)
  e dalle fonti
- **Il git log dei file esistenti contiene segnale**: le correzioni passate
  dell'autore sono il piu forte indicatore di cosa lui voleva davvero. Vale
  la pena scorrerle prima di riscrivere un capitolo
