# Marche One Health AMR Atlas

Edizione regionale `marche_amr_atlas`, pubblicata da Codex Vitae ETS sulla stessa
base delle edizioni Umbria e Toscana.

## Stato

La letteratura pubblicata con collegamento territoriale esplicito alle Marche
è concentrata su Ancona (AOU delle Marche - Ospedali Riuniti, presidio di
Torrette). Ne restano 23 inclusi (20 novembre 2026): 10 a scala regionale,
10 di struttura, 2 sui comuni e 1 sulla provincia (fiume Chienti, Macerata e
Fermo).

Tre strutture nominate, georiferite con Nominatim (© OpenStreetMap
contributors, ODbL):

- AOU delle Marche, Ospedali Riuniti (presidio di Torrette, Ancona): 8 studi;
- Ospedale San Salvatore di Pesaro: 1 studio;
- Ospedale Principe di Piemonte di Senigallia: 1 studio.

Per gli studi che citano l'ospedale regionale o universitario di Ancona il
segnaposto è il presidio di Torrette. Due studi che nominano due strutture
(Santa Croce di Fano e INRCA di Ancona; Ospedali Riuniti e Engles Profili di
Fabriano) sono sui poligoni comunali, non su un punto. Uno studio che tocca
più province conta in ciascuna: Ancona 11, Pesaro e Urbino 2, Macerata 1,
Fermo 1, Ascoli Piceno 0.

L'edizione pubblica AR-ISS 2024 (copertura 83,6%, nessuna rete regionale,
CC BY 4.0) e AIFA Open Data 2024, antibatterici J01 (CC BY 4.0). Non è stato
trovato un rapporto ISTISAN o ISS regionale sulle Marche.

Sei layer (AMR umana, veterinaria, alimentare, ambientale, fauna selvatica,
contorno regionale):

- AMR umana: 5 elementi, 12 studi (3 punti ospedalieri; comuni di Fano e Ancona, e di Ancona e Fabriano);
- AMR veterinaria: 1 elemento (regione), 1 studio;
- AMR alimentare: 1 elemento (regione), 5 studi;
- AMR ambientale: 2 elementi, 3 studi (regione; province di Macerata e Fermo, fiume Chienti);
- AMR nella fauna selvatica: nessun elemento;
- studi a scala regionale: 1 elemento, 2 studi umani.

I layer vuoti e le aree senza segnaposto sono nessuna evidenza pubblicata,
non resistenza zero. Ogni popup cita lo studio e il DOI (o il record PubMed
se il DOI non è assegnato) e ricorda che il segnaposto è il luogo dello
studio, non una prevalenza.

Confini ISTAT 2026 (225 comuni, 5 province, regione 11), letti in UTF-8.
Regione Marche, ARS Marche, AOU delle Marche, INRCA, AST, ARPA Marche, IZSUM
e il PDF OsMed sono esclusi: vedi `metadata/EXCLUDED_SOURCES.md`.

Il conteggio in homepage e in pubblicazioni legge
`public/data/literature-catalog.json` (23).

## Pagine

Sorgente su `main`. Il sito statico è pubblicato dal branch `gh-pages`
(GitHub Pages, cartella `/`). Nessun file `CNAME`. Analitica: GoatCounter
`https://atlanteamr.goatcounter.com/count`, come le edizioni Umbria e Toscana.

## Build locale

```bash
python3 -m http.server 8000
```

Aprire `http://localhost:8000/`.

Per rigenerare i dati pubblici servono gli input in `raw/` e, per i confini,
l'archivio ISTAT indicato in `metadata/SNAPSHOTS.tsv`. I DBF ISTAT si leggono
in UTF-8:

```bash
pip install -r requirements-geodata.txt
python3 scripts/build_istat_geography.py --source-root <Limiti01012026_g> --output-root public/geography
python3 scripts/build_literature_catalog.py
python3 scripts/build_study_evidence_layers.py
```

## Directory

- `public/`: dati e asset approvati per il sito;
- `metadata/`: fonti, snapshot, ambito pubblico e fonti escluse;
- `raw/`: curatela, esummary e risposte Nominatim;
- `scripts/`: ricostruzione del catalogo e dei layer;
- `private/`: nessun dato riservato in questa edizione.
