# Calcolatore RAL → Netto (prototipo)

Prototipo che stima il **netto annuale e mensile** e le **trattenute** a partire da una **RAL** (Retribuzione Annua Lorda), per un caso semplice e standard:

- impiegato a tempo indeterminato, full time, anno intero lavorato
- residenza e sede di lavoro a Milano (Regione Lombardia)
- nessuna agevolazione, carico di famiglia o altro reddito

## Come si usa

Apri [`index.html`](./index.html) in un browser (nessuna installazione richiesta, tutto è HTML/CSS/JS vanilla in un unico file), inserisci una RAL e premi **Calcola**.

## Logica di calcolo

Il calcolo segue, in ordine:

1. **Contributi INPS** a carico del lavoratore (9,19% sulla RAL).
2. **Quota esente cuneo fiscale** per redditi ≤ 20.000€ (7,1% / 5,3% / 4,8% a seconda della fascia), che riduce l'imponibile IRPEF.
3. **IRPEF lorda** sugli scaglioni 2026 (23% / 33% / 43%).
4. **Detrazioni da lavoro dipendente** (formula D.Lgs. 216/2023) e **ulteriore detrazione cuneo fiscale** (1.000€ tra 20.000€ e 32.000€, decrescente fino a 40.000€).
5. **Trattamento integrativo** ("ex bonus Renzi", fino a 1.200€/anno per redditi ≤ 28.000€, semplificato).
6. **Addizionale regionale Lombardia** (a scaglioni, 1,23%–1,73%) e **addizionale comunale Milano** (0,80% flat, esente sotto 23.000€).

Tutte le semplificazioni e ipotesi (RAL su 13 mensilità, nessun elemento variabile, netto mensile calcolato come media annua ÷ 13, ecc.) sono elencate nel pannello "Ipotesi, semplificazioni e fonti" della pagina stessa.

⚠️ Prototipo a scopo dimostrativo — non costituisce consulenza fiscale né sostituisce un cedolino ufficiale.
