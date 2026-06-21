# Capitolo 4 -- Sfide strutturali e strategie individuali

Guida allo studio per ripeterlo al Prof. Santoni. Segue il capitolo nell'ordine
esatto. Non e un riassunto: e la traccia di come difendere ogni frase a voce.
Numeri allineati alla versione corrente del `.tex` (retribuzione crescente,
capitalizzazione reale 0,7%, due grafici nuovi).

---

## Introduzione (§4.1 -- "Dal sistema all'individuo")

**"Le riforme percorribili liberano al massimo dieci o quindici punti di tasso di
sostituzione per le platee piu svantaggiate..."**

Il capitolo 3 ha mappato le riforme possibili. Il recupero migliore realisticamente
ottenibile, per i lavoratori piu penalizzati, e di 10-15 punti di tasso di
sostituzione, e solo a tre condizioni: che le riforme vengano davvero implementate,
che il vincolo di bilancio regga, che la produttivita recuperi. Sul fronte
produttivita il dato e impietoso: 0,12% medio annuo nel decennio 2015-2025 (OCPI
2026) contro l'1,04% ipotizzato dalla RGS. La distanza fra le due cifre e il margine
di incertezza di tutta la tesi.

**"Ciò che invece e certo... e che i meccanismi automatici del sistema NDC traducono
la pressione demografica in riduzioni del tasso di sostituzione in modo sistematico
e misurabile."**

Il NDC non aspetta il Parlamento: agisce automaticamente attraverso la
capitalizzazione nozionale (agganciata al PIL nominale, che cresce poco) e i
coefficienti di trasformazione (che scendono con la speranza di vita). "Sistematico
e misurabile" significa: non dipende da una decisione politica futura, e gia nella
formula.

**I due piani dell'analisi.** Piano aggregato (§4.1-4.2 del PDF): "come sta il
sistema?", cioe il rendimento implicito. Piano individuale (§4.3-4.9): "cosa
succedera a me?", cioe i quattro profili e le strategie. La distanza fra i due piani
e la distanza fra sostenibilita del sistema e adeguatezza della persona: il sistema
puo essere sostenibile e io povero, e non e una contraddizione, e il punto centrale
della tesi.

---

## La pressione demografica come vincolo strutturale (§4.2 del PDF)

**L'indice di dipendenza degli anziani sfiora il 62% entro il 2070.** Quasi due
pensionati ogni tre persone in eta da lavoro (MEF-RGS 2025). Qui interessa l'altra
faccia di quel numero: cosa significa, in termini di rendimento, per chi versa oggi.

**Il teorema di Samuelson-Aaron: r_PAYG = n + g_w.** Il rendimento implicito di un
sistema a ripartizione e la somma del tasso di variazione dell'occupazione (n) e
del tasso di crescita del salario reale (g_w). Fonte: Bosi 2018. A voce: in un
sistema a ripartizione i contributi non sono investiti sui mercati, pagano le
pensioni correnti; il "rendimento" e quanto crescono lavoratori e salari. Entrambi
i fattori sono sotto pressione in Italia: occupazione nativa in contrazione
strutturale, migrazione che compensa solo in parte, produttivita ristagnante.

**"Il rendimento implicito del PAYG si colloca, nelle ipotesi prudenziali,
nell'ordine dello 0,5-1,5% reale annuo."** Traduzione di Samuelson-Aaron per
l'Italia. Per confronto: un portafoglio diversificato a prevalente componente
azionaria, su quarant'anni, ha restituito storicamente molto di piu. Il database di
lungo periodo di Dimson, Marsh e Staunton stima per le azioni mondiali circa il 5%
reale annuo dal 1900, con gli Stati Uniti ancora piu alti (DimsonMarshStaunton2025).
La differenza non e teorica: e la misura quantitativa del rischio demografico che
la generazione attuale porta in dote.

---

## La Generazione Z e il mercato del lavoro italiano (§4.3 del PDF)

**"...caratteristiche strutturalmente diverse... non per scelta ma per composizione
del mercato del lavoro."** Generazione Z = nati fra il 1997 e il 2012. La distinzione
"non per scelta" e fondamentale: e un argomento strutturale, non morale.

**NEET 16,1% in Italia nel 2023, secondo peggiore UE dopo la Romania** (Eurostat).
NEET = Not in Education, Employment or Training, 15-29 anni.

**Tempo determinato fra gli under 30: 34,3% nel 2024, sopra la media UE-27 del
31,1%** (Eurostat LFS). Questi numeri non descrivono una transizione generazionale:
descrivono il montante contributivo che verra accumulato, o non accumulato, nei
prossimi quarant'anni.

**"Ogni discontinuita di carriera diventa una riduzione permanente e non
recuperabile del montante."** Nel retributivo la pensione dipendeva dagli ultimi
anni; chi aveva un percorso accidentato recuperava con retribuzioni finali alte. Nel
NDC quello smoothing non esiste: il contributo non versato all'anno t non viene mai
capitalizzato, perche l'anno t e passato.

**"Una pausa di cinque anni a inizio carriera... equivale a perdere i cinque anni di
capitalizzazione piu lunga."** Passaggio controintuitivo da padroneggiare: i
contributi versati prima rendono di piu perche hanno piu anni davanti. Perdere
cinque anni a 27-32 anni significa perdere i fattori (1+g) elevati al numero
massimo di anni. Il costo di un'interruzione precoce e sistematicamente superiore a
quello di un'interruzione tardiva.

**Anzianita contributiva dei trentacinquenni: da 9,6 anni (2002) a 7,8 (2022)**,
quasi un quinto in meno in vent'anni (INPS 2025). Carriere che iniziano piu tardi e
si interrompono piu spesso riducono i contributi versati, mentre la capitalizzazione
resta agganciata al PIL nominale: due canali di compressione simultanei.

---

## Simulazioni: il costo previdenziale delle carriere discontinue (§4.4 del PDF)

**La formula del montante con retribuzione crescente.**
MC_j = c * somma_{t=1}^{T_j} S_t (1+gamma)^(T_j - t), con S_t = S_0 (1+w)^(t-1).

A differenza di un esercizio a retribuzione costante (che sovrastima il rapporto
montante/ultima retribuzione), qui la retribuzione cresce lungo la carriera.

**Parametri (tutti dichiarati e giustificati nel testo):**
- c = 0,33 (aliquota dipendente; 0,25 per l'autonomo)
- S_0 = 25.000 euro (retribuzione reale d'ingresso, uguale per tutti: esperimento controllato)
- w = 1,0% reale (le retribuzioni crescono come la produttivita per occupato, media RGS 2025-2070)
- gamma = 0,7% reale (capitalizzazione del montante = crescita del PIL reale RGS; in nominale 2,7% = 0,7 reale + 2 di deflatore)
- coefficiente di trasformazione al 2067 = 5,0% (stima dell'autore, dichiarata in nota: prudente, il valore vigente a 67 anni e 5,608% per il 2025-2026 e scende con la speranza di vita)
- pensionamento a 67 anni nel 2067 per tutti

**Il cuore del problema:** le retribuzioni (1% reale) crescono piu in fretta del
montante (0,7% reale) perche l'occupazione si contrae; il rendimento riconosciuto ai
contributi resta sotto la dinamica salariale, ed e questo che comprime il tasso di
sostituzione.

### I quattro profili (numeri della Tabella 4.1)

- **Profilo A -- Dipendente stabile (40 anni).** MC ≈ 459.300 euro; pensione ≈ 22.965
  euro/anno (1.767/mese); ultima retribuzione ≈ 36.850 euro; **TS lordo 62,3%**, in
  linea col 58,4% che la RGS proietta per il dipendente privato al 2070, e lontano
  dal 90% che la stessa carriera darebbe a retribuzione costante.
- **Profilo B -- Gap di 5 anni iniziali (35 anni).** MC ≈ 404.800; pensione ≈ 20.240
  (1.557/mese); **TS 54,9%**, circa sette punti e mezzo sotto A. Il peso dei cinque
  anni mancanti e amplificato perche cadono all'inizio, dove la capitalizzazione opera
  per il numero massimo di anni.
- **Profilo C -- Dieci anni a regime ridotto, caregiving (40 anni, di cui 10 al
  50%).** MC ≈ 404.400; pensione ≈ 20.220 (1.555/mese); **TS 54,9%**. Esito quasi
  identico a B: dieci anni a meta contribuzione pesano come cinque di assenza piena.
- **Profilo D -- Autonomo sotto-dichiarato (40 anni).** c = 0,25; reddito dichiarato
  75% di quello effettivo (18.750 contro 25.000). MC ≈ 261.000; pensione ≈ 13.050
  (1.004/mese); **TS 35,4%** sul reddito effettivo, quasi ventisette punti sotto A.
  La sotto-dichiarazione e strutturale: evasione IRPEF da lavoro autonomo e impresa
  al 63,9% dell'imposta potenziale nella media 2017-2021 (MEF), stime accademiche di
  circa un terzo di reddito in meno (Albarea 2020). L'imposta evasa oggi e pensione
  mancante domani.

**Il messaggio della tabella:** non conta il livello assoluto ma la **distanza fra i
profili** -- quasi 27 punti separano il dipendente stabile dall'autonomo che
sotto-dichiara, a parita di salario d'ingresso e di dinamica salariale. E questo a
misurare la regressivita.

> Attribuzione (importante in sede d'esame): i quattro profili sono
> **elaborazioni dell'autore** su parametri MEF-RGS 2025/NdA e INPS 2025. Si difende
> il metodo di calcolo, non un dato letto da un report.

---

## La regressivita implicita (§4.4 del PDF -- la sezione "asciugata")

> Nota di revisione: questa sezione e stata mantenuta (e l'architrave fra le
> simulazioni e le conclusioni: traduce i quattro numeri nella tesi centrale) ma
> alleggerita. Il dato Mazzaferro (92,6% / 80 miliardi), che era ripetuto qui, e
> stato tolto perche gia trattato per esteso nel capitolo 3; resta citato la dove
> e sviluppato.

**"La neutralita attuariale e rispettata. Eppure i quattro profili si distribuiscono
su quasi ventisette punti di tasso di sostituzione."** Il paradosso che Franco e
Tommasino chiamano contraddizione fondamentale del NDC: il metodo e formalmente
neutro (ognuno riceve il valore attualizzato di quanto ha versato), eppure produce
40 punti... no, **27 punti** di divario fra A e D. Le discontinuita che generano gli
esiti divergenti non sono distribuite a caso: si concentrano sui lavoratori piu
svantaggiati. Il sistema non discrimina, amplifica le disuguaglianze preesistenti.

**Franco e Tommasino (2020):** il NDC garantisce equita attuariale fra chi ha
carriere omogenee, ma non redistribuisce e non puo farlo per definizione. Non e
un'opinione dell'autore, e il giudizio della letteratura di riferimento.

**Doppio svantaggio:** chi ha carriere discontinue ha pensione pubblica bassa
(primo svantaggio) ed e anche quello con meno capacita di aderire al pilastro
complementare (secondo svantaggio). I due nascono dalla stessa radice: posizione nel
mercato del lavoro.

**Dimensione di genere (il caso piu documentato):** le donne ricorrono al part-time,
spesso non volontario, piu degli uomini, e concentrano su di se i carichi di cura
(INPS 2025). Per le lavoratrici nel regime contributivo puro dopo il 1995 il divario
di genere nel montante atteso e stimato fra **23 e 28%** (MEF-RGS 2025), contro
**16-18%** per le coorti del regime misto. Il NDC, pur non distinguendo per sesso,
amplia il gender pension gap perche non compensa l'asimmetria del lavoro di cura.

**Raitano (2020):** una quota rilevante dei lavoratori interamente nel contributivo
-- soprattutto carriere discontinue e donne -- non accumula contribuzione sufficiente
a una pensione dignitosa. Il rischio non e solo la pensione bassa: e non raggiungere
la soglia minima per il pensionamento anticipato contributivo (tre volte l'assegno
sociale) e restarne esclusi per anni. I Profili B e C sono sopra quella soglia, ma
solo se salario e capitalizzazione reggono; una riduzione del 15-20% del montante li
spingerebbe sotto.

**La correzione costa.** La regressivita non si corregge dall'interno del primo
pilastro senza romperne l'equilibrio: servono trasferimenti espliciti dalla fiscalita
generale (pensione contributiva di garanzia, contribuzione figurativa per cura),
costo gia stimato nel capitolo 3 in 3-5 miliardi annui. Non e una critica alla
proposta: e la sua condizione di realizzabilita, in un paese con debito fra i piu
alti dell'area euro.

---

## Il rischio individuale senza strumenti individuali (§4.5 del PDF)

**"La variabile che separa il 62,3% del Profilo A dal 35,4% del Profilo D non e ne
il salario (uguale) ne gli anni di lavoro (uguali o superiori in D): e la qualita
dell'integrazione nel mercato formale."** Punto culminante della diagnosi. Il NDC non
corregge quella differenza: la amplifica via capitalizzazione composta.

**"Da qui in avanti il capitolo cambia registro e diventa operativo."** Frase-cerniera:
le sezioni seguenti ricostruiscono, strumento per strumento, le mosse del lavoratore,
in ordine di priorita e rendimento atteso.

**"Un lavoratore del Profilo B che aderisce al fondo pensione fin dall'inizio recupera
fino a 7-10 punti di tasso di sostituzione"** (MEF-RGS 2025). E il ponte fra diagnosi
e terapia. Il secondo pilastro non elimina il problema di B ma lo dimezza. E la base
del grafico 4.2 piu avanti.

**Il vincolo che nessuno strumento elimina:** l'accesso dipende dal reddito
disponibile, non dalla competenza finanziaria. Il pilastro complementare e efficiente
per chi ha gia un margine, meno per chi non ce l'ha: proprio i profili B, C e D, con
i TS piu bassi, sono quelli con meno capacita di correggerli.

---

## Il secondo pilastro: TFR, fondi pensione e deducibilita (§4.6 del PDF)

**TFR in azienda:** rivalutazione 1,5% fisso + 75% dell'inflazione ISTAT; rendimento
nominale medio ~2,4% nel decennio 2014-2024 (COVIP 2024). Protegge il nominale, non
accumula ricchezza reale.

**TFR al fondo:** irrevocabile per i nuovi accantonamenti; permette di investire a
tassi di mercato. Vantaggi fiscali: rendimenti tassati al 20% (invece del 26%);
prestazione finale tassata al 15%, ridotta di 0,3% per ogni anno oltre il
quindicesimo fino a un minimo del 9% (Bosi e Guerra 2022). Per chi aderisce giovane:
aliquota finale 9%, meta o meno dell'IRPEF marginale sul lavoro.

**Tre tipologie di fondo (costi che cambiano tutto):**
- Negoziali (chiusi): ISC a 10 anni medio **0,49%** (COVIP 2024); in piu il contributo
  del datore, **0,55-2%** del lordo secondo il CCNL -- trasferimento accessibile solo
  attivando il fondo: ogni mese di ritardo e matching non incassato.
- Aperti (banche/assicurazioni): ISC a 10 anni **1,35%**.
- PIP (prodotti assicurativi): ISC a 10 anni **2,17%**, i meno efficienti su orizzonti
  lunghi, ma i piu venduti per effetto della rete commerciale.

**Deducibilita: massimale 5.164,57 euro/anno.** Risparmio fiscale immediato: 23% ->
1.188 euro/anno; 35% -> 1.807 euro/anno. Plafond che si accumula nei primi cinque
anni fino a 7.746,86 euro nell'anno di utilizzo. Sono soldi gia "persi" come tasse: la
deducibilita li reindirizza all'accumulo.

**Operativita:** modulo TFR2 entro sei mesi dall'assunzione; in assenza di scelta,
silenzio-assenso al negoziale di categoria. Confronto fondi sul comparatore COVIP
(nessun consulente necessario). L'attivazione del contributo del datore richiede una
quota minima a carico: ometterla equivale a rinunciare al matching.

---

## La scelta della linea di investimento (§4.7 del PDF)

**Garantita/obbligazionaria:** nel decennio 2014-2024 meno dell'1% annuo, sotto la
stessa rivalutazione del TFR (2,4%) (COVIP 2024). In termini reali converge verso
zero. La garanzia sul capitale nominale scatta a pensionamento o per uscita anticipata
(decesso, invalidita grave, disoccupazione > 48 mesi): per un venticinquenne sano e
occupato, probabilita bassa. Selezionarla su 40 anni non riduce il rischio: sposta
l'esito atteso verso il basso.

**Dinamica:** benchmark azionario globale ~5% reale annuo (DimsonMarshStaunton2025),
ma e un rendimento lordo di indice; una linea reale non e integralmente azionaria e
sconta l'ISC, quindi ne cattura prudenzialmente una frazione, ~4% reale netto su 40
anni.

**>>> GRAFICO NUOVO -- Figura 4.1 (montante garantita vs dinamica).** Versamento
mensile di 200 euro per 40 anni: allo 0,5% reale (garantita) ~106.000 euro; al 4%
reale netto (dinamica) ~233.000 euro; multiplo di **2,2**. Da dire a voce: "la forbice
si apre lentamente e diventa decisiva solo nell'ultimo terzo dell'orizzonte; e la
ragione per cui la scelta va fatta presto e non corretta tardi". E elaborazione
dell'autore (versamento anticipato capitalizzato mensilmente su 480 mesi).

**Ciclo di vita:** dinamica in accumulo (primi ~25 anni), bilanciata nel decennio
pre-pensionamento, prudente negli ultimi 3-5 anni. Il trasferimento fra linee dentro
il fondo e fiscalmente neutro (fuori dal fondo, vendere e ricomprare genera plusvalenza
al 26%).

**PAC su ETF** per le somme oltre il limite deducibile: ETF azionario globale (MSCI
World o simili) con TER < 0,2%; non deducibile, guadagni al 26%, ma nessun limite di
importo e piena liquidabilita. Sequenza: prima saturare il massimale deducibile del
fondo, poi l'eccedenza sul PAC.

---

## Quattro profili, quattro strategie (§4.8 del PDF)

**>>> GRAFICO NUOVO -- Figura 4.2 (recupero del TS col secondo pilastro).** Per
ciascun profilo, TS solo pubblico vs TS con secondo pilastro ad adesione piena:
A 62,3 -> 70,3; B 54,9 -> 61,9; C 54,9 -> 61,9; D 35,4 -> 39,9. Il recupero (7-8
punti, coerente con MEF-RGS) scende per l'autonomo D, privo di TFR e con minore
capacita contributiva. **Punto chiave da dire a voce:** il grafico mostra il recupero
*potenziale* ad adesione piena, ma la possibilita di realizzarlo dipende dal reddito,
ed e proprio nei profili a TS piu basso che la capacita manca. Il secondo pilastro
recupera per tutti, ma recupera di piu per chi parte meglio: e regressivo anche
l'antidoto. Elaborazione dell'autore su parametri MEF-RGS.

**Profilo A -- dipendente stabile.** Rischio maggiore: l'inerzia. (1) TFR al negoziale
+ contributo datore subito; (2) versare fino a 5.164,57 su linea dinamica; (3) PAC per
l'eccedenza; (4) RITA dai 63 anni con 5 anni di iscrizione, ponte di reddito fino a 67.

**Profilo B -- gap di 5 anni.** Riscatto della laurea agevolato (per chi e privo di
anzianita al 31/12/1995, quindi quasi tutta la Gen Z): 6.123 euro per anno nel 2025
(33% IVS sul minimale 18.555), deducibile, aumento permanente del montante NDC. In
alternativa, posticipare il pensionamento di due anni: a 69 anni il coefficiente
proiettato supera il 5,5% (MEF-RGS 2025) e si capitalizzano due anni in piu.

**Profilo C -- caregiving.** (1) Amministrativa: contribuzione figurativa per
assistenza a familiari con disabilita grave (art. 42 c. 5 D.Lgs. 151/2001, in
attuazione della L. 104/1992), poco usata per scarsa conoscenza. (2) Finanziaria:
fondo aperto, anche 50-100 euro/mese durante il part-time. Il ciclo di vita conta con
forza: un euro versato a trent'anni capitalizza per 36-37 anni, il doppio rispetto
allo stesso euro versato a 52.

**Profilo D -- autonomo sotto-dichiarato.** Problema a monte: dichiarare il reddito
effettivo (la sotto-dichiarazione produce 13.050 invece di 22.965 euro). Poi lo
strumento: no negoziale, ma fondo aperto; il differenziale di costo fondo aperto vs
PIP (1,35% contro 2,17%, ovvero 0,82 punti) su un patrimonio medio di 50.000 euro vale
~410 euro/anno, ~16.400 euro cumulati in valore reale su 40 anni. PAC su ETF per
l'eccedenza e per la variabilita del reddito autonomo.

---

## Sintesi operativa: la checklist (§4.9 del PDF)

Sette mosse in ordine di priorita (rendimento atteso + costo di attivazione):
1. Conferire il TFR al fondo (TFR2 entro 6 mesi; rendimento di mercato vs 2,4% del TFR; tassazione finale 15% -> 9%). Tutti i dipendenti, costo zero.
2. Attivare il contributo del datore (quota minima da CCNL; +0,55-2% del lordo). Dipendenti con negoziale, costo zero.
3. Versamenti volontari deducibili (fino a 5.164,57; risparmio IRPEF 23-43%). Richiede reddito capiente.
4. Linea dinamica in accumulo (~4% reale netto vs <1% garantita). Under 50, orizzonte lungo.
5. Riscatto agevolato della laurea (6.123 euro/anno, deducibile). Carriere con gap + liquidita.
6. PAC su ETF globale (TER < 0,2%, nessun limite). Capacita contributiva residua.
7. RITA (dai 63 anni con 5 di iscrizione; ponte fino a 67). Chi ha una posizione complementare.

**La gerarchia e anche una mappa della disuguaglianza:** le prime due mosse sono
universali (costo zero); dalla terza servono reddito e liquidita, cioe esattamente
cio che manca ai profili B, C e D. E questa asimmetria, non l'assenza di strumenti, la
ragione per cui il secondo pilastro da solo non chiude il problema dell'adeguatezza.

---

## I numeri chiave tradotti a parole (aggiornati)

- **62% al 2070:** indice di dipendenza degli anziani (MEF-RGS 2025).
- **0,5-1,5% reale:** rendimento implicito del PAYG italiano (Samuelson-Aaron).
- **~5% reale:** azioni mondiali dal 1900 (DimsonMarshStaunton2025); ~4% reale netto la linea dinamica.
- **0,12% vs 1,04%:** produttivita 2015-2025 vs ipotesi RGS.
- **16,1%:** NEET 15-29 anni, Italia 2023, secondo peggiore UE.
- **34,3% vs 31,1% UE:** under 30 a tempo determinato, 2024.
- **9,6 -> 7,8 anni:** anzianita contributiva dei 35enni, 2002 -> 2022.
- **62,3 / 54,9 / 54,9 / 35,4%:** i quattro TS lordi (A/B/C/D). Spread A-D ~27 punti, a parita di salario.
- **459.300 / 404.800 / 404.400 / 261.000 euro:** i quattro montanti.
- **5,0% al 2067:** coefficiente di trasformazione usato (estrapolato, dichiarato in nota).
- **23-28% vs 16-18%:** gender pension gap, contributivo puro vs misto.
- **3-5 miliardi/anno:** costo della correzione via fiscalita generale (Raitano 2020 / cap. 3).
- **7-10 punti di TS:** recupero col fondo pensione ad adesione piena (MEF-RGS 2025).
- **ISC 0,49 / 1,35 / 2,17%:** negoziali / aperti / PIP (COVIP 2024).
- **5.164,57 / 7.746,86 euro:** massimale di deducibilita / plafond accumulato.
- **9%:** aliquota minima sulla prestazione finale per iscritti da almeno 35 anni.
- **6.123 euro/anno:** costo del riscatto laurea agevolato 2025.
- **106.000 vs 233.000 euro (Fig. 4.1):** 200 euro/mese su 40 anni allo 0,5% vs 4% reale, multiplo 2,2.
- **~16.400 euro:** risparmio cumulato fondo aperto vs PIP su 40 anni (patrimonio medio 50.000).

---

## La posizione dell'autore (come spiegarla senza farla suonare ideologica)

Cornice liberale-libertaria d'ordine, ma ogni elemento ha un'argomentazione
economica, non un postulato politico.
1. **Responsabilita individuale informata, non obbligo.** L'auto-enrolment funziona
   con educazione finanziaria; l'obbligo puro genera adesione passiva, default sulla
   linea garantita, perdita di rendimento. Il problema dell'inerzia si risolve col
   design, non con la coercizione.
2. **Scetticismo verso i regimi speciali.** Il NDC e formalmente neutro ma
   sostanzialmente regressivo. La PCG e la contribuzione figurativa per cura si
   applicano a categorie definite da svantaggio oggettivo, non da appartenenza
   corporativa.
3. **Educazione finanziaria mai fatta dallo Stato.** Il sistema ha trasferito il
   rischio sull'individuo senza dargli gli strumenti per gestirlo: fallimento di
   policy, non inerzia comportamentale.
4. **Il mercato dei fondi ha problemi reali.** La tesi dice esplicitamente che i PIP
   sono inefficienti e che la rete spinge gli strumenti sbagliati. Difende la
   complementare come categoria, non lo stato attuale dell'offerta.

---

## Possibili domande del professore (risposte pronte)

### Q1. "Non e elitista dire al giovane precario di aprire un fondo pensione?"
La tesi lo riconosce nel paragrafo §4.5. Ma il primo gradino non costa nulla in piu:
il TFR e gia accantonato per legge, spostarlo nel fondo non riduce il reddito
disponibile, lo riposiziona. La deducibilita dei volontari e il secondo gradino. Per
chi resta in precarieta permanente la risposta non e il fondo, e la pensione
contributiva di garanzia del capitolo 3. Le due cose sono complementari.

### Q2. "Perche non rendere l'adesione obbligatoria?"
L'obbligo senza alfabetizzazione concentra tutti sulla linea di default (in Italia la
garantita = rendimento minimo); richiede un'infrastruttura di controllo che non
esiste; l'auto-enrolment con opt-out ottiene gran parte dell'adesione obbligatoria a
una frazione del costo politico. La tesi e favorevole all'auto-enrolment, non
all'obbligo.

### Q3. "I fondi italiani hanno rendimenti competitivi?"
I negoziali si (ISC 0,49%), i PIP no (ISC 2,17%, spesso sotto il TFR su orizzonti
decennali). Il problema non e la categoria "fondi pensione", e l'asset allocation
conservativa: la domanda dei sottoscrittori va sulla garantita. Soluzione: educazione
finanziaria + default life-cycle.

### Q4. "Il TFR in azienda non e un cuscinetto utile in emergenza?"
Il fondo consente anticipazioni fino al 75% per la prima casa, 30% per altre esigenze
dopo 8 anni, 100% per spese sanitarie gravi in qualunque momento. Il TFR in azienda
si liquida solo alla cessazione. Il fondo e piu flessibile, non meno.

### Q5. "La regressivita della complementare non smentisce ST4?"
No. ST4 non dice che la complementare e equa: dice che e necessaria per chi puo
accedervi e che, dato il vincolo politico-temporale, non c'e alternativa scalabile.
Il capitolo distingue adeguatezza media (che la complementare migliora) e adeguatezza
di chi e gia penalizzato (per cui serve l'intervento sistemico del cap. 3). ST3 e ST4
lavorano in parallelo su platee diverse.

### Q6. "Il coefficiente del 5,0% al 2067 non e inventato?"
E un'estrapolazione tendenziale dichiarata in nota: 5,608% (2025) -> ~5,2% (2040,
illustrato nel cap. 2 e nell'introduzione) -> 5,0% (2067), coerente con la dinamica
demografica MEF. E prudenziale: un coefficiente piu basso renderebbe le pensioni
ancora piu basse, ma le proporzioni fra i profili resterebbero identiche. La
conclusione sulla varianza degli esiti non dipende dal livello assoluto.

### Q7. "Perche un dipendente stabile con TS 62,3% dovrebbe aderire al fondo?"
Il 62,3% e lordo e ipotizza una carriera quarantennale piena, che la maggioranza non
realizza; non incassare il contributo del datore e rinunciare a denaro gia previsto
dal contratto; la RITA permette l'uscita anticipata fino a 4 anni prima senza fondo
non esiste. Per A il fondo non serve a sopravvivere, serve a guadagnare flessibilita
e a coprire l'eventualita che la carriera non sia stata piena.

### Q8. "Il decumulo in capitale non espone al rischio di longevita?"
Si, per questo la legge impone almeno il 50% in rendita per chi non rientra nelle
soglie. Il capitale integrale ha senso con bassa speranza di vita attesa, eredi, altre
fonti stabili. Per chi e in salute e senza eredi, la rendita vitalizia e la copertura
naturale contro il rischio di vivere "troppo a lungo". E matching profilo-strumento,
non dogma.

---

## Trappola argomentativa: tenere insieme ST2 e ST4 senza contraddirsi

ST2 dice che il sistema penalizza i nuovi entranti; ST4 dice che il singolo puo
farcela. Tre passaggi che le tengono insieme:
1. La diagnosi di ST2 e sistemica e media (riguarda la coorte, non il singolo). ST4
   lavora sul singolo dentro la distribuzione: chi attiva gli strumenti si sposta
   verso la coda alta, ma la distribuzione resta quella. Una persona puo uscire dal
   problema senza che il problema scompaia.
2. ST3 (riforme) e la risposta corretta al problema sistemico, ma lenta. ST4 e la
   risposta al problema individuale, immediata. Per un venticinquenne del 2025 una
   riforma del 2035 arriva quando meta del danno e gia fatto. L'azione individuale e
   l'unica leva attivabile nel tempo giusto.
3. L'argomento non e "il sistema funziona perche l'individuo rimedia", ma "il sistema
   non funziona, le riforme servono ma non arriveranno in tempo per la Gen Z, quindi
   l'azione individuale informata e una necessita pratica, non una scelta ideologica".
   Lo Stato fissa le regole (NDC, deducibilita, vigilanza COVIP), informa, riserva la
   redistribuzione a chi e oggettivamente escluso (PCG); per tutti gli altri scegliere
   bene e la contropartita della liberta di scegliere.
