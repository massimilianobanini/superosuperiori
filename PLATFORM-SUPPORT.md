# Supporto delle piattaforme — V0.1

SuperoSuperiori è progettato per essere il più possibile indipendente dalla piattaforma AI.

**Progettato per funzionare** non significa **già verificato**.

## Stato dei test

| Piattaforma | Lettura del solo link | Link + problema concreto | Stato V0.1 |
|---|---|---|---|
| ChatGPT | osservato: funziona | osservato: comportamento non ancora stabile prima delle ultime correzioni | sperimentale |
| Gemini | FAIL runtime: ha descritto il repository come vuoto/senza README, anche se il repository reale contiene i file | FAIL runtime: non ha caricato SuperoSuperiori e ha risposto genericamente al problema | non supportato via solo link nella V0.1 |
| Altre AI | non verificato | non verificato | da testare |

## Cosa significa "supportata"

Una piattaforma non viene dichiarata supportata soltanto perché riesce ad aprire GitHub.

Per considerarla supportata deve almeno:

1. capire che il solo link avvia SuperoSuperiori;
2. mostrare l'avviso iniziale;
3. distinguere tra "solo link" e "link + problema";
4. seguire le regole fondamentali del tutor;
5. riuscire a usare i file collegati oppure applicare il fallback minimo di START-HERE.

## Se una piattaforma non apre i file collegati

Il progetto contiene un fallback minimo dentro `START-HERE.md`.

Una piattaforma che legge soltanto il README o START-HERE può comunque fornire una versione ridotta del metodo, ma non va considerata pienamente supportata finché il comportamento non è affidabile.

## Funzioni e nomi cambiano

Nomi dei modelli, modalità veloci o avanzate, limiti, piani e requisiti di età possono cambiare.

Per questo SuperoSuperiori cerca di descrivere il comportamento desiderato senza dipendere da un nome specifico della piattaforma.

## Regola di pubblicazione

Non aggiungere una piattaforma all'elenco delle piattaforme supportate senza una prova reale in chat nuova.


## Esito Gemini del 3 ottobre 2026

### Test 1 — solo link: FAIL

Gemini ha riconosciuto l'URL come repository GitHub pubblico, ma ha dichiarato che il repository risultava vuoto o privo di README e sorgenti.

Questo non corrisponde allo stato reale del repository, che contiene README, START-HERE, core, modalità, Kit e altri file.

Conclusione: in questo test Gemini non ha recuperato correttamente il contenuto corrente del repository.

### Test 2 — link + problema: FAIL

Gemini non ha applicato SuperoSuperiori.

In particolare:
- non ha mostrato l'avviso iniziale;
- non ha seguito il routing del repository;
- ha presunto subito lacune e scenari;
- ha inventato percentuali di probabilità sul risultato;
- ha dato una lezione ampia prima di vedere un esercizio reale;
- ha usato un tono non coerente con il progetto;
- ha fornito regole troppo generali per alcuni casi di disequazioni.

Conclusione: il link GitHub da solo non è al momento un ingresso affidabile per Gemini.

### Conseguenza

Nella V0.1 Gemini non va dichiarato supportato tramite il solo URL del repository.

Un eventuale fallback specifico per Gemini va trattato come percorso separato e testato a parte.
