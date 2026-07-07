# Valtioneuvoston ja ministeriöiden design system

Valtioneuvoston (VN) ja sen 12 ministeriön yhteinen visuaalisen ilmeen suunnittelujärjestelmä verkkoviestintään. Määrittelee värit, typografian, välistykset, komponentit ja saavutettavuusvaatimukset yhtenäisen ja saavutettavan lopputuloksen varmistamiseksi.

**Versio:** 2.6.0 · **Tila:** Luonnos · **Omistaja:** Valtioneuvoston kanslia, verkkoviestintä

## Sivusto

Dokumentaatio julkaistaan GitHub Pagesilla:

👉 **https://tuomopekka.github.io/vn_ui_manual/**

## Rakenne

| Tiedosto | Kuvaus |
|---|---|
| `design.md` | Speksin **totuuden lähde** (source of truth) — kaikki säännöt ja arvot |
| `index.html` | Dokumentaatiosivu, joka esittää speksin visuaalisesti (GitHub Pages) |
| `assets/` | Tyylit (`design-system.css`), fontit ja tunnukset |
| `PRODUCT.md` | Tuotteen käyttäjät, tarkoitus ja periaatteet |
| `CLAUDE.md` | Ohjeet tekoälyavustajalle |

Kun `design.md`:tä muutetaan, `index.html` päivitetään vastaamaan sitä — speksi ja dokumentaatiosivu pidetään synkassa.

## Paikallinen esikatselu

Sivu on staattinen HTML. Sen voi avata suoraan selaimessa (`index.html`) tai käynnistää kevyen paikallisen palvelimen:

```
python3 -m http.server
```

ja avata `http://localhost:8000`.

## Saavutettavuus

Toteutus noudattaa WCAG 2.1 A/AA -tason vaatimuksia (digipalvelulaki). Yksityiskohdat: `design.md` §2.
