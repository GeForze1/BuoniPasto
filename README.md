# Buoni pasto

Web app per tenere traccia dei buoni pasto: saldo, utilizzi con data e ora, blocchi con scadenza. Pensata per iPhone, funziona anche offline e i dati restano sul dispositivo.

## Funzioni

- **Tasti + e −:** aggiungono o usano un buono con un solo tocco, registrando data e ora (secondi compresi).
- **Saldo iniziale:** si imposta dalle Impostazioni, con quantità ed eventuale scadenza.
- **Valore del buono:** configurabile (di default 8 €). Cambia gli importi mostrati in tutta l'app.
- **Blocchi con scadenza:** ogni blocco di buoni può avere una data di scadenza. Il tasto − usa prima i buoni che scadono per primi. I buoni scaduti non contano nel saldo e vengono segnalati.
- **Modifica:** si possono cambiare la scadenza di un blocco e la data e ora di ogni movimento (✎), o eliminare un movimento (✕).
- **Statistiche:** buoni usati e importo speso nel mese corrente.
- **Copia di sicurezza:** esportazione e importazione dei dati come testo, per salvarli o spostarli su un altro dispositivo.
- **Grafica adattabile:** telefoni piccoli, orizzontale, tablet e computer; tema chiaro e scuro automatico.

## Installazione su iPhone

1. Pubblica il repository con GitHub Pages (Settings → Pages → branch `main`, cartella `/ (root)`).
2. Apri l'indirizzo della pagina in Safari e attendi il caricamento completo.
3. Tocca Condividi → **Aggiungi a Home**.

Dopo la prima apertura con connessione l'app parte anche senza rete. Un aggiornamento si vede alla seconda apertura con connessione.

## Dati e privacy

I dati sono salvati solo nella memoria del browser del dispositivo (`localStorage`): non vengono inviati a nessun server e non c'è alcun tracciamento. Per questo non si sincronizzano tra dispositivi diversi e si perdono se si cancellano i dati di navigazione di Safari. Per spostarli o conservarne una copia usa **Impostazioni → Copia di sicurezza e importazione**.

## Tecnologia

HTML, CSS e JavaScript puri in un unico file, senza librerie né passaggi di compilazione.

| File | Scopo |
| --- | --- |
| `index.html` | Interfaccia e logica dell'app |
| `sw.js` | Service worker: copia locale per l'uso offline |
| `manifest.webmanifest` | Nome e icone per l'installazione sulla Home |
| `icon-180.png`, `icon-512.png` | Icone dell'app |

Per provarla in locale basta servire la cartella con un server statico, per esempio `python3 -m http.server`, e aprire `http://localhost:8000`. Il service worker funziona solo via HTTPS o su `localhost`.
