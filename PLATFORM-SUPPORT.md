# Supporto delle piattaforme — V0.4

SuperoSuperiori è progettato per essere il più possibile indipendente dalla singola AI.

**Progettato per funzionare** non significa **già verificato in ogni modalità e su ogni piattaforma**.

Questa pagina distingue ciò che è stato realmente osservato da ciò che è soltanto previsto dal progetto.

---

## Ingresso consigliato per gli studenti

L'ingresso consigliato è la web app:

https://massimilianobanini.github.io/superosuperiori/

La web app non chiede all'AI di leggere tutto GitHub.

Lo studente:
1. sceglie uno dei percorsi 1–8 oppure scrive direttamente il problema;
2. SuperoSuperiori seleziona localmente il flow;
3. viene generata un'istruzione autosufficiente e breve;
4. l'istruzione viene copiata;
5. si apre ChatGPT o Gemini;
6. lo studente incolla e invia.

Questo percorso riduce la dipendenza dalla capacità dell'AI di leggere repository o pagine web.

---

## Stato attuale

| Piattaforma / ingresso | Stato | Note |
|---|---|---|
| Web app → ChatGPT | **da validare manualmente su dispositivo reale** | routing e copia/apertura superano lo stress test tecnico; resta da verificare il comportamento reale della chat |
| Web app → Gemini | **da validare manualmente su dispositivo reale** | routing e copia/apertura superano lo stress test tecnico; resta da verificare il comportamento reale della chat |
| ChatGPT → solo link GitHub | **sperimentale** | in test precedenti ha mostrato di poter avviare il progetto, ma il comportamento non è stato sempre stabile |
| Gemini → solo link GitHub | **non affidabile** | nei test non ha applicato correttamente SuperoSuperiori |
| Gemini Skill `/superosuperiori` | **validata sperimentalmente** | dopo la correzione ha rispettato lingua, routing, niente esercizi inventati e una sola domanda ad alto valore |
| Altre AI | **non verificate** | da testare |

---

## ChatGPT

### Solo link GitHub

Nei test iniziali ChatGPT ha mostrato di poter leggere il repository e avviare SuperoSuperiori.

Tuttavia il comportamento con richieste concrete è stato variabile prima delle successive correzioni.

Per questo il solo link GitHub resta un ingresso **sperimentale**, non quello consigliato agli studenti.

### Web app

La web app elimina la necessità di far leggere il repository a ChatGPT.

Lo stress test V0.4 ha verificato:
- routing 1–8;
- classificazione del testo libero;
- generazione del prompt;
- copia;
- apertura di ChatGPT;
- assenza di caricamento dell'intero repository.

Resta da validare manualmente:
- clipboard reale;
- apertura su browser mobile;
- qualità della prima risposta del modello.

---

## Gemini

### Solo link GitHub: non affidabile

Nei test del 3 ottobre 2026 Gemini:
- non ha recuperato correttamente il contenuto del repository;
- non ha applicato il metodo;
- ha saltato il routing;
- ha fatto assunzioni non richieste;
- ha fornito risposte non coerenti con le regole del progetto.

Conclusione:

**il solo link GitHub non è un ingresso affidabile per Gemini.**

### Pagina web letta direttamente da Gemini

In un test precedente Gemini è riuscito a leggere la pagina pubblica ma l'ha trattata come contenuto da riassumere invece di eseguire automaticamente le istruzioni.

Per questo una normale pagina web non va considerata da sola un comando affidabile per l'AI.

### Skill Gemini `/superosuperiori`

La Skill è stata testata in runtime.

Dopo la correzione "una sola domanda per messaggio", il retest ha prodotto:

- risposta in italiano;
- nessun menu quando il problema era già dichiarato;
- nessun esercizio inventato;
- nessuna diagnosi arbitraria dei prerequisiti;
- una sola domanda ad alto valore;
- richiesta di partire da un esercizio reale.

Conclusione:

**la Skill Gemini è validata sperimentalmente come percorso dedicato.**

Versione canonica:

[gemini/SKILL.md](gemini/SKILL.md)

### Web app → Gemini

La V0.4 usa un meccanismo diverso dal vecchio "Gemini legge la pagina".

La pagina costruisce prima un'istruzione autosufficiente, la copia e apre Gemini.

Il comportamento tecnico della web app ha superato lo stress test, ma il flusso completo va ancora verificato manualmente su dispositivo reale.

---

## Fallback Gemini

Il file:

[GEMINI-START.md](GEMINI-START.md)

resta come riferimento tecnico e base autosufficiente.

Non è l'ingresso consigliato per uno studente quando sono disponibili:
- web app;
- Skill Gemini.

---

## Cosa significa "supportata"

Una piattaforma o un percorso non viene dichiarato supportato soltanto perché riesce ad aprire un link.

Per considerarlo realmente supportato bisogna verificare almeno:

1. avvio corretto;
2. lingua italiana;
3. routing coerente con la richiesta;
4. una sola domanda alla volta quando serve;
5. assenza di diagnosi arbitrarie;
6. uso corretto del materiale dello studente;
7. comportamento coerente con il flow scelto;
8. continuità della sessione;
9. funzionamento su un dispositivo reale.

---

## Funzioni e regole cambiano

Nomi dei modelli, funzioni, piani, requisiti di età e limiti possono cambiare.

SuperoSuperiori cerca quindi di definire il **comportamento desiderato** senza dipendere troppo dal nome di uno specifico modello.

Prima di dichiarare una piattaforma supportata o compatibile con una certa fascia di età, serve una verifica aggiornata.

---

## Regola di pubblicazione

Non aggiungere una piattaforma all'elenco delle piattaforme supportate senza una prova reale.

Distinguere sempre:

- **progettato per funzionare**;
- **stress test tecnico superato**;
- **test runtime superato**;
- **validato su dispositivo reale**.
