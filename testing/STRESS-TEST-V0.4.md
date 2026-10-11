# Stress test SuperoSuperiori V0.4

**Data:** 11 ottobre 2026  
**Obiettivo:** verificare l'interfaccia web, il routing rapido 1–8, il campo libero, la generazione delle istruzioni per ChatGPT/Gemini, la coerenza dei flow e il deploy GitHub Pages prima del test manuale su dispositivo reale.

## Esito

**PASS CON CORREZIONI APPLICATE**

Dopo le correzioni emerse durante lo stress test, la suite finale non presenta errori noti nei controlli automatizzabili eseguiti.

## Controlli finali

### 1. Struttura web e routing — 20/20 PASS

Verificati:
- sintassi JavaScript valida;
- HTML collegato correttamente a CSS e JavaScript;
- viewport mobile;
- regole responsive;
- nessuna emoticon nella schermata;
- Brand Positioning;
- Battlecry;
- casi A/B;
- Metodo SUPERA;
- presenza e coerenza dei percorsi 1–8 tra HTML, JavaScript e FAST-ROUTER;
- pulsanti ChatGPT, Gemini e copia;
- scorciatoie 1–8;
- classificazione del testo libero;
- regola una domanda per messaggio;
- assenza di caricamento del Kit/repository completo nel runtime web.

### 2. Comportamento simulato dell'interfaccia — 20/20 PASS

Verificati:
- click sui pulsanti 1–8;
- apertura del dialogo corretto;
- titolo corretto per ogni flow;
- hash corretto;
- chiusura corretta;
- classificazione di richieste libere per verifica, autovalutazione, interrogazione, esercizio, organizzazione, memoria, comprensione e altro;
- copia + apertura ChatGPT;
- copia + apertura Gemini;
- copia senza apertura di una piattaforma.

### 3. Contenuto dei prompt — 24/24 PASS

Per ciascuno degli 8 flow verificati:
- presenza del Core minimo;
- presenza della regola di una sola domanda per messaggio;
- presenza delle istruzioni specifiche del flow;
- lunghezza contenuta.

Lunghezza indicativa delle istruzioni generate: circa **1.350–1.800 caratteri** a seconda del flow, prima dell'eventuale testo dello studente.

### 4. Navigazione da tastiera e chiusura — 4/4 PASS

Verificati:
- tasto numerico 3 → Preparare una verifica;
- Escape → chiude il dialogo;
- Ctrl/Cmd + Invio nel campo libero → continua;
- click sullo sfondo → chiude il dialogo.

### 5. Collegamenti interni principali — 31/31 PASS

Controllati 31 link relativi nei principali documenti runtime e di progetto:
- README;
- START-HERE;
- FAST-START;
- FAST-ROUTER;
- MANIFESTO;
- METODO-SUPERA.

Nessun collegamento relativo rotto rilevato.

### 6. Leggerezza e privacy tecnica — PASS

Web app statica:
- HTML ~6,5k caratteri;
- CSS ~6,4k;
- JavaScript ~11,7k;
- totale indicativo ~24,6k caratteri;
- nessun font esterno;
- nessuna chiamata backend/fetch;
- nessuna chiave API;
- nessuna dipendenza esterna necessaria al caricamento della schermata.

Questo riduce il tempo e la frizione della fase iniziale.

### 7. GitHub Pages — PASS

Ultimo deploy verificato dopo le correzioni:
- workflow: `pages build and deployment`;
- stato: completato;
- esito: successo;
- commit deployato: `acb10c128eaecb1ccba446118e8bf85bd7acf7f7`.

## Difetti trovati e corretti

### 1. Testo libero sempre instradato su “Altro”

Prima:
- qualunque testo scritto nel campo libero usava il flow 8.

Correzione:
- aggiunto classificatore locale rapido;
- richieste chiaramente riconoscibili vengono instradate direttamente al flow corretto senza chiedere all'AI di leggere GitHub.

Esempi verificati:
- “Ho una verifica di fisica venerdì” → 3;
- “Voglio sapere se sono pronto per la verifica” → 7;
- “Domani ho un'interrogazione di storia” → 4;
- “Sono bloccato su questo esercizio” → 2;
- “Non ricordo le date...” → 6;
- “Non capisco le disequazioni” → 1.

### 2. Rischio di due domande nello stesso messaggio

Trovato nei flow esercizio/verifica.

Correzione:
- rafforzata la regola nel Core minimo e nei prompt web;
- verifica: prima chiede la data, poi eventualmente gli argomenti;
- esercizio: prima chiede esercizio/foto, poi il punto di blocco solo se serve.

### 3. Classificatore troppo largo sulla parola “problema”

Prima:
- “Ho un problema diverso con la scuola” veniva erroneamente interpretato come esercizio.

Correzione:
- “problema” da solo non determina più il flow 2;
- il flow esercizio viene scelto solo con segnali più specifici.

Retest: PASS.

## Cosa resta da verificare manualmente

Questi punti dipendono da browser, dispositivo o comportamento reale dell'AI e non possono essere considerati definitivamente validati dal solo test statico/simulato:

1. clipboard reale su Chrome Android;
2. clipboard reale su Safari iPhone/iPad;
3. comportamento del popup/apertura nuova scheda sui diversi browser;
4. effettiva velocità percepita dal caricamento alla prima domanda;
5. qualità reale della prima risposta ChatGPT per flow 1–8;
6. qualità reale della prima risposta Gemini per flow 1–8;
7. leggibilità visiva su telefoni piccoli;
8. eventuali differenze dovute a account, impostazioni o versioni delle AI.

## Verdetto

La **V0.4 è pronta per il test manuale del proprietario e successivamente per un piccolo pilot con studenti reali**.

Non sono emersi altri blocchi tecnici noti dopo le correzioni automatiche.

Il prossimo test non deve modificare subito il progetto: prima raccogliere i problemi osservati su dispositivo reale e poi fare una patch unica.
