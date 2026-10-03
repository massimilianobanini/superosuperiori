# Limiti noti — V0.1

Questo file elenca problemi o limiti già conosciuti. Non sono nascosti: fanno parte del lavoro di miglioramento.

## 1. Il comportamento dipende dalla piattaforma

Due AI possono leggere lo stesso repository e reagire in modo diverso.

Una piattaforma può:
- leggere soltanto il README;
- non seguire i link interni;
- usare una copia temporaneamente non aggiornata;
- interpretare in modo diverso le istruzioni.

Per questo le regole critiche sono ripetute in forma minima tra README e START-HERE.

## 2. Le istruzioni lette da una pagina web possono essere trattate come contenuto non attendibile

Alcune AI, per ragioni di sicurezza, possono leggere una pagina web ma **non eseguire automaticamente le istruzioni trovate dentro quella pagina**.

Questo è un limite importante del requisito "incolla solo il link e parti": non può essere eliminato completamente dal repository.

SuperoSuperiori riduce il problema mettendo le regole essenziali nel README e in START-HERE, ma una piattaforma può comunque scegliere di riassumere il link o chiedere cosa farne.

## 3. L'avvio dal solo link non è garantito su ogni AI

ChatGPT ha già mostrato di poter avviare SuperoSuperiori partendo dal solo link, ma il comportamento con richieste concrete è stato variabile durante i primi test.

Gemini e altre AI non sono ancora validate.

Vedi `PLATFORM-SUPPORT.md`.

## 4. Il PDF V1.7 non è ancora generato dal Markdown canonico

Il PDF presente in `kit/KIT-DI-SOPRAVVIVENZA.pdf` è la versione V1.7 del 30 settembre 2026.

Il Markdown del repository è stato adattato per essere più leggibile dalle AI e non è ancora parte di una pipeline automatica che rigenera il PDF.

Quindi, finché questa pipeline non esiste, PDF e Markdown vanno controllati quando uno dei due cambia.

## 5. Il QR del PDF V1.7 punta ancora al collegamento pubblico precedente

La versione cartacea V1.7 era stata creata prima che GitHub diventasse la fonte pubblica principale.

Il prossimo PDF dovrà puntare al repository ufficiale o a un indirizzo stabile che porti sempre all'ultima versione.

## 6. Le regole di età e le funzioni delle AI cambiano

La tabella del Kit è una fotografia della versione V1.7, non una garanzia futura.

Prima di dire a uno studente che può usare oggi una certa piattaforma, bisogna verificare le regole ufficiali aggiornate.

## 7. Non esiste ancora una validazione completa su tutte le materie

Le regole scientifiche sono più sviluppate perché matematica e fisica richiedono controlli specifici.

Le materie teoriche usano per ora soprattutto le regole generali del tutor e il Kit.

## 8. Il metodo non può garantire un voto

Le modalità "Sufficienza" e "Approfondimento" indicano una priorità di studio.

Non garantiscono un risultato scolastico specifico.

## 9. Il tutor può ancora sbagliare

SuperoSuperiori riduce alcuni errori di utilizzo dell'AI, ma non rende l'AI infallibile.

Libro, appunti, materiale del docente e fonti affidabili restano importanti per i controlli.
