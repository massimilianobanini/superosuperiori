# SuperoSuperiori — Protocollo di test V0.1

Obiettivo: verificare se SuperoSuperiori funziona davvero quando uno studente usa soltanto il link del repository, senza dover capire la struttura interna.

Repository ufficiale:

https://github.com/massimilianobanini/superosuperiori

## Regola generale del test

Ogni prova importante va fatta in una **chat nuova**, senza contesto precedente.

Non anticipare alla AI come dovrebbe comportarsi, tranne quando il test lo richiede.

Annota:
- piattaforma usata;
- modello o modalità scelta;
- data;
- prompt esatto inviato;
- risposta ottenuta;
- cosa ha funzionato;
- cosa non ha funzionato;
- eventuali errori o passaggi inutili.

---

## Test 1 — Solo link

Apri una nuova chat.

Incolla soltanto:

https://github.com/massimilianobanini/superosuperiori

Non scrivere altro.

### Risultato atteso

La AI deve:

1. capire che il link avvia SuperoSuperiori;
2. leggere il repository o almeno README + START-HERE;
3. partire senza aspettare "Iniziamo" o "Aiutami";
4. mostrare una volta l'avviso sulle impostazioni della AI;
5. proporre:
   - 1 — Voglio arrivare alla sufficienza
   - 2 — Voglio approfondire / puntare a voti alti
   - 3 — Altre informazioni

### Errore grave

- la AI si limita a riassumere GitHub;
- chiede "cosa vuoi che faccia con questo link?";
- non riesce a leggere il repository;
- non propone il menu iniziale.

---

## Test 2 — Link + problema reale

Nuova chat.

Scrivi:

https://github.com/massimilianobanini/superosuperiori

Ho una verifica di matematica giovedì e non capisco le disequazioni.

### Risultato atteso

La AI non deve obbligare lo studente a scegliere prima 1/2/3.

Deve:
- capire che il problema è già stato dichiarato;
- applicare le regole generali;
- caricare anche il modulo scientifico;
- chiedere solo le informazioni davvero utili;
- preferire una domanda alla volta;
- capire se lo studente punta alla sufficienza o vuole approfondire, solo se non è già evidente.

---

## Test 3 — Modalità Sufficienza

Nuova chat.

Incolla il link.

Quando compare il menu, rispondi:

1

Poi scrivi:

Ho un'interrogazione domani. Ho 45 minuti e devo studiare 4 capitoli.

### Risultato atteso

La AI deve:
- riconoscere che il tempo è insufficiente per fare tutto bene;
- non costruire un piano irrealistico;
- separare almeno mentalmente:
  - indispensabile;
  - importante;
  - approfondimento;
- concentrarsi sulle priorità;
- non promettere un 6.

---

## Test 4 — Modalità Approfondimento

Nuova chat.

Incolla il link.

Rispondi:

2

Poi scrivi:

Sto studiando la seconda legge di Newton. So usare F = ma, ma voglio capire bene quando si può usare e quando no.

### Risultato atteso

La AI deve:
- non limitarsi a dare una definizione;
- spiegare il significato;
- chiarire le condizioni;
- mostrare casi o varianti;
- fare almeno un controllo o una domanda che verifichi comprensione;
- evitare testo lungo solo per sembrare più approfondita.

---

## Test 5 — Studente bloccato in matematica

Nuova chat.

Incolla il link.

Poi scrivi:

Continuo a sbagliare le disequazioni fratte.

### Risultato atteso

La AI non deve partire subito con una lezione completa.

Deve cercare di capire se il problema dipende da:
- segni;
- frazioni;
- equazioni;
- condizioni di esistenza;
- studio del segno;
- altro prerequisito.

Deve verificare, non assumere.

---

## Test 6 — Tentativo dello studente

Nuova chat.

Incolla il link.

Poi invia un esercizio già svolto, meglio se con un errore intenzionale.

Scrivi:

Questo è il mio tentativo. Dove sbaglio?

### Risultato atteso

La AI deve:

1. indicare prima ciò che è corretto;
2. trovare il primo errore importante;
3. spiegare perché è un errore;
4. farti riprovare;
5. non riscrivere subito tutta la soluzione se non serve.

---

## Test 7 — Controllo anti-risposta automatica

Nuova chat.

Incolla il link.

Poi scrivi:

Fammi questo esercizio e dammi solo la risposta finale.

### Risultato atteso

La AI deve adattarsi al contesto.

Non deve rifiutare in modo rigido.

Dovrebbe capire se:
- vuoi imparare;
- vuoi controllare;
- sei bloccato;
- vuoi solo verificare un risultato.

Se serve, può dare anche la soluzione o il risultato, ma deve evitare di trasformare il tutor in una macchina che fa sempre tutto al posto dello studente.

---

## Test 8 — Altre informazioni

Nuova chat.

Incolla il link.

Rispondi:

3

### Risultato atteso

La AI deve proporre in modo semplice:
- cos'è SuperoSuperiori;
- Manifesto;
- metodo;
- Kit;
- feedback.

Non deve mostrare struttura tecnica inutile del repository.

---

## Piattaforme da testare

Prima fase:

1. ChatGPT
2. Gemini

Seconda fase, solo dopo:

3. altre AI capaci di leggere GitHub o pagine web

Non dichiarare una piattaforma come supportata finché non supera almeno il Test 1 e il Test 2 in modo affidabile.

---

## Esito del test

Per ogni piattaforma usa una classificazione semplice:

- **PASS** — comportamento corretto;
- **PASS CON PROBLEMI** — funziona, ma con attriti;
- **FAIL** — non parte o non segue il metodo.

Annota sempre il motivo.

---

## Principio

Il test più importante è questo:

**Uno studente che non sa nulla della struttura del progetto deve poter incollare un solo link e iniziare a studiare.**
