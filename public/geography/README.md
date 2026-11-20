# Geografia pubblica

La cartografia pubblica dell'edizione Marche comprende:

- `atlas_region.geojson`: confine regionale ISTAT 2026 (codice 11);
- `atlas_provinces.geojson`: 5 province ISTAT 2026: Pesaro e Urbino (PU 041), Ancona (AN 042), Macerata (MC 043), Ascoli Piceno (AP 044) e Fermo (FM 109);
- `atlas_municipalities.geojson`: 225 comuni ISTAT al 1/1/2026.

I file sono letti in UTF-8 dal DBF ISTAT.

Gli studi della letteratura curata stanno in layer distinti sotto `public/data/`. Le strutture nominate sono geocodificate tramite OSM Nominatim (vedi `raw/nominatim/NOTE.md`). Gli studi con città o province nominate usano i poligoni ISTAT corrispondenti; gli studi regionali usano il contorno regionale. Nessuna RSA, azienda agricola, canile, macello, depuratore non nominato o struttura non nominata è localizzata.
