# Changelog

## V0.4 — 11 ottobre 2026

### Web app cliccabile

- trasformata la pagina GitHub Pages in una vera interfaccia mobile-first;
- 8 scelte numerate cliccabili;
- supporto anche ai tasti 1–8 da tastiera;
- campo libero per descrivere direttamente il problema;
- nessuna emoticon nell'interfaccia;
- schermata iniziale con Posizionamento, Battlecry e casi A/B del Kit;
- metodo SUPERA visibile sotto le scelte.

### Avvio dell'AI

Dopo la scelta:
- il routing è immediato e locale;
- non viene letto tutto il repository;
- viene costruita un'istruzione autosufficiente con Core minimo + flow specifico;
- un pulsante copia l'istruzione e apre ChatGPT o Gemini;
- disponibile anche la sola copia per usare un'altra AI.

### Privacy tecnica

La web app è statica:
- non contiene chiavi API;
- non richiede un backend SuperoSuperiori;
- il testo inserito resta nel browser finché lo studente non lo incolla volontariamente nella propria AI.


## V0.3 — 11 ottobre 2026

### Avvio rapido

- introdotto il principio **FAST PATH FIRST**;
- la prima schermata non richiede la lettura completa del repository;
- create 8 scelte numerate, utilizzabili anche scrivendo soltanto il numero;
- rimosse emoticon dalla schermata iniziale per mantenere un aspetto professionale;
- l'avviso tecnico sulle impostazioni dell'AI non blocca più l'avvio;
- le scelte 1–7 usano routing deterministico;
- il ragionamento approfondito parte solo quando inizia il problema reale.

### Interfaccia

La schermata iniziale mostra:
- Brand Positioning;
- Battlecry;
- i due casi del Kit: **A — devo sbloccarmi** e **B — voglio approfondire**;
- menu numerato 1–8.

### Architettura

Aggiunti:
- `runtime/FAST-START.md`;
- `runtime/FAST-ROUTER.md`;
- `runtime/CORE-MIN.md`;
- flow dedicati per capire, esercizi, verifiche, interrogazioni, organizzazione, memoria/ripasso, autovalutazione e altro;
- `method/METODO-SUPERA.md`.

Principio: **il metodo può essere ricco; l'esperienza dello studente deve restare semplice.**


## V0.2 — 3 ottobre 2026

### Posizionamento

- **Categoria:** Metodo di studio semplice nell'era dell'AI.
- **Brand Positioning:** Il primo metodo di studio semplice per superare le superiori nell'era dell'AI.
- **Battlecry:** Supera le superiori. Non farti superare dall'AI.
- **Target:** studenti delle scuole superiori italiane.

### Principio progettuale

**Semplificare l'esperienza, non impoverire il metodo.**

Lo studente deve poter descrivere il problema con parole normali. È il tutor a riconoscere automaticamente la situazione e scegliere la parte giusta del metodo.

### Nuovo router delle situazioni

Aggiunto `core/INTENT-ROUTER.md` per coprire operativamente le principali casistiche del Kit, tra cui:

- non capisco;
- mi blocco;
- continuo a sbagliare;
- non ricordo;
- mi annoio;
- esercizi;
- controllo del proprio tentativo;
- verifiche;
- interrogazioni;
- poco tempo;
- approfondimento;
- collegamenti;
- foto e appunti;
- cambio formato;
- verifica dell'AI;
- miglioramento delle richieste;
- chat lunghe;
- richieste grandi;
- uso di più AI;
- verifica finale dell'autonomia.

### Gemini

- Skill `/superosuperiori` validata come bootstrap sperimentale.
- Aggiunta versione canonica in `gemini/SKILL.md`.
- Correzione: una sola domanda per messaggio.
- Il semplice link web/repository non è considerato un bootstrap affidabile per Gemini.

### Documenti aggiornati

- README
- START-HERE
- core/TUTOR-RULES
- MANIFESTO
- GEMINI-START
- docs/index
- gemini/SKILL
- PLATFORM-SUPPORT
- KNOWN-LIMITATIONS

## V0.1 — 3 ottobre 2026

Prima versione pubblica sperimentale.

Includeva:
- README e START-HERE;
- Manifesto;
- modalità Sufficienza e Approfondimento;
- regole scientifiche;
- Kit V1.7 in Markdown e PDF;
- privacy;
- licenza;
- test iniziali ChatGPT/Gemini.
