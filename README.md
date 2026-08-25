# Calcolatore RAL → Netto (prototipo)

🔗 **Demo live:** https://temporary-sonic-sable-tnvydin.vercel.app

Prototipo che stima il **netto annuale e mensile** e le **trattenute** a partire da una **RAL** (Retribuzione Annua Lorda), per un caso semplice e standard:

- impiegato a tempo indeterminato, full time, anno intero lavorato
- residenza e sede di lavoro a Milano (Regione Lombardia)
- nessuna agevolazione particolare o altro reddito oltre alla RAL

## Come si usa

Apri [`index.html`](./index.html) in un browser (nessuna installazione richiesta, tutto è HTML/CSS/JS vanilla in un unico file). Inserisci:

- **RAL** (retribuzione annua lorda totale)
- **Mensilità** (12 / 13 / 14, per il netto mensile medio)
- **Coniuge a carico** (sì/no)
- **Numero di altri familiari a carico** (es. genitori conviventi)

e premi **Calcola**.

## Logica di calcolo

Il calcolo segue, in ordine:

1. **Contributi INPS** a carico del lavoratore (9,19% sulla RAL).
2. **Quota esente cuneo fiscale** per redditi ≤ 20.000€ (7,1% / 5,3% / 4,8% a seconda della fascia), che riduce l'imponibile IRPEF.
3. **IRPEF lorda** sugli scaglioni 2026 (23% / 33% / 43%).
4. **Detrazioni da lavoro dipendente** (formula D.Lgs. 216/2023), **ulteriore detrazione cuneo fiscale** (1.000€ tra 20.000€ e 32.000€, decrescente fino a 40.000€), **detrazione coniuge a carico** e **detrazione altri familiari a carico** (art. 12 TUIR), se applicabili.
5. **Trattamento integrativo** ("ex bonus Renzi", fino a 1.200€/anno per redditi ≤ 28.000€, semplificato).
6. **Addizionale regionale Lombardia** (a scaglioni, 1,23%–1,73%) e **addizionale comunale Milano** (0,80% flat, esente sotto 23.000€).

I figli a carico non sono modellati come input: dal 2022 la relativa detrazione IRPEF per gli under 21 è stata sostituita dall'Assegno Unico Universale, erogato dall'INPS fuori busta paga.

Tutte le semplificazioni e ipotesi sono elencate nel pannello "Ipotesi, semplificazioni e fonti" della pagina stessa.

⚠️ Prototipo a scopo dimostrativo — non costituisce consulenza fiscale né sostituisce un cedolino ufficiale.
