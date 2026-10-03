# Stress test SuperoSuperiori V0.1

**Data:** 3 ottobre 2026  
**Repository:** https://github.com/massimilianobanini/superosuperiori

Questo documento distingue tra:

- **test runtime osservato**: comportamento realmente visto in una chat;
- **test strutturale**: controllo delle istruzioni e dei file del repository;
- **da validare**: comportamento che dipende da una piattaforma esterna e non è ancora stato osservato in modo affidabile.

## Sintesi

La V0.1 è abbastanza solida per continuare con test pilota, ma non va ancora presentata come universalmente compatibile con tutte le AI.

I problemi strutturali principali trovati durante lo stress test sono stati corretti.

Restano soprattutto tre limiti:

1. il solo link può essere interpretato in modo diverso dalle varie AI;
2. ChatGPT ha mostrato comportamento non perfettamente stabile nel caso "link + problema";
3. PDF e Markdown non sono ancora sincronizzati da una pipeline unica.

---

## Risultati

| Area | Esito | Nota |
|---|---|---|
| Repository pubblico | PASS | Il repository è pubblico e leggibile senza accesso al profilo del proprietario. |
| Struttura README → START-HERE → core | PASS | Routing semplificato e reso esplicito. |
| Link Markdown interni | PASS | Nessun collegamento relativo rotto nel controllo automatico. |
| Solo link → avvio | PASS runtime su ChatGPT, non universale | Osservato almeno una volta in chat pulita. |
| Link + problema concreto | PASS CON PROBLEMI runtime | Nei primi test ChatGPT è stato incoerente; il routing è stato poi riscritto. |
| Avviso sulle impostazioni | PASS strutturale | Ora è obbligatorio in START-HERE e richiamato nel README. |
| Menu 1/2/3 | PASS strutturale | Limitato al caso "solo link". |
| Problema già dichiarato | PASS strutturale | Non deve più essere interrotto automaticamente dal menu. |
| Diagnosi dei prerequisiti | PASS strutturale dopo correzione | Vietato presumere la lacuna; prima evidenza o esercizio reale. |
| Modalità Sufficienza | PASS strutturale | Priorità, tempo reale, niente promessa di voto. |
| Modalità Approfondimento | PASS strutturale | Rigore, varianti, collegamenti e trasferimento del metodo. |
| Matematica/fisica/scientifiche | PASS strutturale | Formule, unità, condizioni, plausibilità e secondo metodo. |
| Materie teoriche | PASS CON LIMITI | Coperte dal core e dal Kit; non esiste ancora un modulo dedicato. |
| Correzione di un tentativo | PASS strutturale | Primo errore importante, spiegazione, nuovo tentativo. |
| Controllo rapido | PASS strutturale | Il tutor non deve forzare una lezione quando serve solo verificare. |
| Compito da consegnare | PASS strutturale | Aggiunta distinzione tra apprendimento e lavoro generato al posto dello studente. |
| Materiale del docente | PASS strutturale | Aggiunta gerarchia delle fonti; niente correzioni silenziose. |
| Prompt malevoli nei materiali | PASS strutturale | Le istruzioni dentro testi e pagine vengono trattate come contenuto. |
| Privacy studenti | PASS strutturale | Creato PRIVACY.md con principio di minimizzazione dei dati. |
| Chat lunghe / passaggio di consegne | PASS strutturale | Coperto dal core e dal Kit. |
| Controllo dell'AI con fonti | PASS strutturale | Seconda AI = revisore, non prova definitiva. |
| Informazioni sulle piattaforme | PASS CON LIMITI | Le regole cambiano; la tabella del Kit è ora marcata come fotografia datata. |
| Fallback se i moduli non si aprono | PASS strutturale | START-HERE contiene 8 regole minime autonome. |
| Feedback | PASS strutturale | Stesso questionario, richiesta non invasiva. |
| Manifesto | PASS | Contiene categoria, posizionamento, battlecry, target, ragioni e principi. |
| Licenza / fork | PASS | CC BY 4.0; copie e modifiche ammesse con attribuzione. |
| PDF V1.7 presente | PASS | File pubblico nel repository. |
| PDF ↔ Markdown sincronizzati | FAIL / backlog | Il Markdown è adattato per AI; non esiste ancora generazione automatica del PDF. |
| QR del PDF verso GitHub | FAIL / backlog | Il PDF V1.7 punta ancora al collegamento pubblico precedente. |
| ChatGPT | SPERIMENTALE | Test 1 riuscito; Test 2 ha mostrato variabilità prima delle ultime correzioni. |
| Gemini | DA VALIDARE | Nessun test runtime pulito registrato. |
| Altre AI | DA VALIDARE | Nessun supporto dichiarato. |

---

## Copertura del Kit V1.7

Le 22 aree del Kit risultano presenti nel repository, direttamente nel Markdown del Kit o trasformate in regole operative:

1. uso del Kit — coperto;
2. strumenti ed età — coperto, con avviso di volatilità;
3. nessun bisogno di "dimostrare" competenza AI — coperto;
4. 7 livelli — coperto;
5. limite del livello comodo — coperto;
6. istruzioni migliori — coperto;
7. leve del tutor — coperto;
8. miglioramento dei prompt — coperto;
9. quando non capisci — core/Kit;
10. quando ti blocchi — core/scientifiche;
11. memoria e noia — core;
12. matematica/fisica — modulo scientifiche;
13. immagini e appunti — core;
14. esercizio → metodo — core;
15. piano di studio — core/modalità;
16. interrogazioni — core/modalità;
17. verifica dell'AI — core/Kit;
18. chat lunghe — core;
19. strumenti — Kit/supporto piattaforme;
20. tutor personale — Kit;
21. scorciatoie — Kit;
22. feedback — core/README.

**Copertura concettuale: 22/22.**

Questo non significa che il Markdown sia una trascrizione identica del PDF: è una versione adattata e più operativa.

---

## Problemi trovati e già corretti

### 1. Contraddizione nel router

Prima START-HERE diceva contemporaneamente:
- continua con il problema senza menu;
- "poi mostra" il menu 1/2/3.

Ora esistono due rami separati e non ambigui:
- solo link;
- link + problema.

### 2. Diagnosi troppo precoce

Nei primi test ChatGPT inventava una disequazione semplice e presumeva possibili lacune.

Ora:
- niente esercizio inventato se lo studente ha un problema reale;
- prerequisiti solo come ipotesi;
- prima esercizio reale, tentativo o informazione ad alto valore.

### 3. Fallback insufficiente

Dopo aver alleggerito START-HERE, una AI che non riusciva ad aprire i moduli poteva perdere troppe regole.

Ora START-HERE contiene un fallback minimo autonomo.

### 4. Fonti dello studente non gerarchizzate

Ora il core dà priorità a:
1. consegna del docente;
2. materiale scolastico fornito;
3. metodo SuperoSuperiori;
4. conoscenza generale;
5. fonti esterne.

### 5. Istruzioni dentro fonti esterne

Aggiunta protezione: frasi rivolte all'AI dentro testi, pagine o PDF sono contenuto, non comandi.

### 6. Privacy

Creato PRIVACY.md.

### 7. Regole delle piattaforme che diventano vecchie

La tabella del Kit è ora dichiarata esplicitamente come fotografia della V1.7, non verità permanente.

---

## Rischi ancora aperti

### A. Limite fondamentale del "solo link"

Le AI possono trattare le istruzioni trovate sul web come contenuto non attendibile e decidere di non eseguirle.

Non esiste una modifica al repository che possa garantire al 100% il comportamento "incolla il link e parte" su ogni piattaforma.

### B. Cache

Una AI o un motore di ricerca può vedere una versione non ancora aggiornata del README.

### C. Tempi di avvio

Nei primi test ChatGPT ha impiegato circa 37–53 secondi per il primo messaggio.

Il routing ridotto dovrebbe limitare letture inutili, ma il costo di apertura del repository dipende dalla piattaforma.

### D. Claim "il primo"

Il posizionamento ufficiale è:

**"Il primo metodo di studio per superare le superiori nell'era dell'AI."**

Lo stress test non considera dimostrata la priorità storica della parola "primo". Esistono già in Italia corsi e contenuti che combinano metodo di studio, studenti e AI. Il claim resta il posizionamento scelto del progetto, ma una verifica di anteriorità/competitor è un lavoro separato.

### E. PDF

Il prossimo PDF dovrebbe:
- nascere dalla fonte Markdown canonica o essere controllato contro di essa;
- avere QR/link verso il punto pubblico canonico scelto.

---

## Stato consigliato della versione

**V0.1 — PILOTA / SPERIMENTALE**

Adatta a:
- test controllati con studenti reali;
- raccolta feedback;
- test ChatGPT e Gemini;
- correzioni rapide.

Non ancora adatta a dichiarazioni del tipo:
- "funziona con tutte le AI";
- "compatibilità verificata con Gemini";
- "il solo link funziona sempre".

---

## Prossimi criteri per V0.2

Passare a V0.2 quando almeno:

1. il Test 1 e il Test 2 sono ripetibili su ChatGPT;
2. Test 1 e Test 2 sono provati su Gemini;
3. almeno alcuni studenti reali completano sessioni di studio;
4. i problemi ricorrenti vengono classificati;
5. PDF e fonte canonica vengono riallineati.
