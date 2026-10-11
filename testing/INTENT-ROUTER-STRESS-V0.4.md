# Stress test linguistico del router — V0.4

**Data:** 11 ottobre 2026

## Obiettivo

Verificare che il campo libero della web app riconosca il modo in cui studenti reali possono formulare richieste, senza obbligarli a conoscere il menu 1–8 o usare parole tecniche.

Sono state stressate:

1. comprensione / rispiegazione;
2. esercizi / blocchi / errori;
3. preparazione verifica;
4. preparazione interrogazione;
5. organizzazione / poco tempo;
6. memoria / ripasso;
7. autovalutazione;
8. richieste trasversali e router generale.

Sono stati inoltre testati:
- linguaggio colloquiale;
- abbreviazioni da telefono;
- richieste miste;
- sinonimi;
- frasi incomplete;
- parole potenzialmente ambigue;
- falsi positivi concettuali.

## Problemi emersi durante lo stress test

Il primo classificatore era troppo letterale.

Esempi inizialmente non riconosciuti:
- `nn capisco`;
- `non ci capisco una mazza`;
- `sono inchiodato qui`;
- `da qui che faccio?`;
- `domani compito mate`;
- `la prof mi sente domani`;
- `ho solo stasera`;
- `non mi resta niente`;
- `fammi un check finale`.

Sono state aggiunte:
- normalizzazione di accenti e apostrofi;
- normalizzazione di abbreviazioni comuni;
- più sinonimi colloquiali;
- priorità tra intenti misti;
- distinzione tra prova scolastica e controllo di una risposta;
- distinzione tra parola-concetto e azione di studio.

## Falsi positivi corretti

Un problema importante era l'uso di parole che possono essere sia contenuto scolastico sia comandi.

Esempi:
- `Cos'è la memoria RAM?` non deve andare in Ripasso;
- `Che cos'è il test di Turing?` non deve andare in Verifica;
- `Spiegami la tradizione orale` non deve andare in Interrogazione;
- `Spiegami l'organizzazione della cellula` non deve andare in Organizzare lo studio;
- `Cosa vuol dire autovalutazione?` non deve avviare un'autovalutazione.

Il router ora riconosce prima le domande concettuali/definizioni quando non esiste un evento scolastico esplicito.

## Richieste miste

Sono state testate priorità come:

- `ho 20 minuti e non capisco le derivate` → **5 Organizzare lo studio**;
- `ho poco tempo e devo fare 15 esercizi` → **5 Organizzare lo studio**;
- `spiegami i casi più difficili per la verifica` → **3 Preparare una verifica**;
- `voglio approfondire per l'interrogazione` → **4 Preparare un'interrogazione**;
- `sono pronto per la verifica?` → **7 Sapere se sono pronto**;
- `verifica quello che ha detto ChatGPT` → **8 Revisione critica**, non verifica scolastica;
- `verifica la mia soluzione` → **2 Esercizio / controllo del proprio tentativo**.

## Abbreviazioni da telefono

Normalizzazioni aggiunte, tra le altre:

- `nn` → non;
- `sn` → sono;
- `cm` → come;
- `dv` → dove;
- `nnt` → niente;
- `tt` → tutto;
- `qlcs` → qualcosa;
- `2h` → 2 ore;
- `3 gg` → 3 giorni;
- `lun` → lunedì;
- `ven` → venerdì.

Esempi finali corretti:
- `nn c capisco nnt con le derivate` → 1;
- `sn bloccato qui` → 2;
- `test inglese lun` → 3;
- `interrogaz storia domani` → 4;
- `3 gg e 5 capitoli` → 5;
- `nn ricordo nnt` → 6;
- `sn pronto?` → 7;
- `migliora sto prompt` → 8.

## Risultati finali

### Regressione multi-categoria
**97 / 97 PASS**

### Falsi positivi concettuali
**40 / 40 PASS**

### Linguaggio da telefono / abbreviazioni
**55 / 55 PASS**

Totale suite finale verificata: **192 / 192 PASS**.

Durante lo sviluppo sono state inoltre esplorate centinaia di formulazioni aggiuntive in blocchi precedenti, che hanno guidato le correzioni del classificatore.

## Limite importante

Questo non significa che ogni frase italiana possibile verrà sempre classificata perfettamente.

Se una frase non viene riconosciuta con sufficiente sicurezza, il comportamento sicuro è il **flow 8 — Altro**, che contiene il router generale e può interpretare semanticamente la richiesta dentro l'AI.

Quindi un mancato riconoscimento locale non deve bloccare lo studente.

## Principio

**Routing locale quando il segnale è chiaro; fallback intelligente quando non lo è.**

L'obiettivo non è indovinare ogni frase con espressioni regolari, ma ridurre la frizione senza trasformare il router in una fonte di errori.
