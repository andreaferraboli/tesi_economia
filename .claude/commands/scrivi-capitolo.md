---
description: Scrive o espande un capitolo della tesi seguendo CLAUDE.md
---

Scrivi il capitolo: $ARGUMENTS

Procedura obbligatoria:
1. Verifica di essere sul branch `sviluppo-test-agente` (altrimenti fai checkout)
2. Leggi `CLAUDE.md` per stile, divieti e workflow
3. Leggi `capitoli_second/00_introduzione.tex` per capire la funzione del capitolo
   nel disegno complessivo della tesi
4. Leggi `C:\Users\andre\OneDrive\andrea\database umano\me.txt` e
   `C:\Users\andre\OneDrive\andrea\database umano\tone_of_voice.txt`
   per ricalibrare voce, valori, posizioni di partenza e angolazione interpretativa
5. Leggi il file `.tex` del capitolo indicato per rispettare quanto gia scritto
6. Identifica le fonti pertinenti in `fonti/` e leggile (PDF inclusi) chiedendoti
   cosa Andrea estrarrebbe da ciascuna e come la userebbe nell'argomentazione
6. Scrivi rispettando:
   - struttura: introduzione divulgativa → analisi tecnica → evidenze empiriche
     → dibattito esperti → conclusione critica
   - stile: ritmo non prevedibile, niente em dash, niente "in conclusione",
     niente "tuttavia" come tic
   - dati: solo da fonti verificate, altrimenti `\todo{VERIFICA DATO}`
   - citazioni: `\cite{autore_anno}` con aggiornamento di `06_bibliografia.tex`
7. Compila con `pdflatex second_main.tex` per verificare che non ci siano errori
8. Committa con messaggio descrittivo in italiano
