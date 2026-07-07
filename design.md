# DESIGN.MD: Valtioneuvoston ja ministeriöiden design system

**Versio:** 2.5.0
**Päivitetty:** 2026-07-07
**Tila:** Luonnos
**Omistaja:** Valtioneuvoston kanslia, verkkoviestintä

Tämä dokumentti on valtioneuvoston ja sen 12 ministeriön yhteinen totuuden lähde (Source of Truth). Se ohjaa tekoälyagentteja, suunnittelijoita ja kehittäjiä yhtenäisen ja saavutettavan lopputuloksen varmistamiseksi.

---

## 1. STRATEGISET TAVOITTEET JA ARVOT

Valtionhallinnon viestinnän on vahvistettava demokratiaa ja avoimuutta. Kaikki toteutukset noudattavat seuraavia periaatteita:

**Saavutettavuus:** Sivustojen on noudatettava kaikilta osin digipalvelulaissa asetettuja WCAG 2.1 A- ja AA-tason kriteerejä. Toteutuksessa huomioidaan myös tulevan WCAG 2.2 -version aiheuttamat täsmennykset.

**Luotettavuus:** Virallinen, rauhallinen ja asiantunteva ilme ilman turhia visuaalisia efektejä.

**Yhtenäisyys:** Yhtenäinen käyttökokemus kaikilla ministeriöiden sivustoilla.

**Käyttäjäkeskeisyys:** Sisällön löydettävyys, käytettävyys ja selkeys.

### 1.1 Äänensävy ja mikrokopio (UX Writing)

**Virallisuus ja selkeys:** Kieli on asiallista, neutraalia ja helposti ymmärrettävää (selkokielen periaatteet). Monimutkaista ja hallinnollista kieltä vältetään, mutta kieli on virallista, eikä esimerkiksi sinuttelevaa.

**Toimintaan ohjaavuus:** Painikkeet ja linkit kertovat selkeästi, mitä niitä klikkaamalla tapahtuu (esim. "Tallenna muutokset").

**Virheilmoitukset:** Syyllistämättömiä ja ratkaisukeskeisiä. Kerrotaan, mikä meni vikaan ja annetaan ohje tilanteen korjaamiseksi. Virheilmoituksissa ei anneta ymmärtää, että käyttäjä on tehnyt virheen, vaan kerrotaan, mitä pitää tehdä toisin.

---

## 2. SAAVUTETTAVUUDEN PERUSPERIAATTEET

Nämä vaatimukset koskevat kaikkia komponentteja ja toteutuksia. Komponenttikohtaiset tarkennukset löytyvät kunkin komponentin omasta osiosta.

### 2.1 WCAG-vaatimukset

Sivustojen on täytettävä digipalvelulain edellyttämät WCAG 2.1 A- ja AA-tason kriteerit. Toteutuksessa huomioidaan myös WCAG 2.2:n tuomat tarkennukset.

### 2.2 Näppäimistökäyttö ja fokus

Kaikki sivuston toiminnot ovat käytettävissä näppäimistöllä. Jokaisella interaktiivisella elementillä on aina selkeä fokus-indikaattori: vähintään 3 px paksu, kontrastisuhde vähintään 3:1 taustaväriin nähden.

| Tila | Kuvaus |
|---|---|
| Hover | Hienovarainen vaste, taustavärin 10 % tummennus |
| Active | Taustavärin 20 % tummennus |
| Disabled | Matala kontrasti (`opacity: 0.4`) ja `not-allowed`-kursori |
| Focus | Vähintään 3 px paksu indikaattori, kontrasti ≥ 3:1 |

### 2.3 Kosketuskohteiden minimikoko

Kaikkien interaktiivisten elementtien minimikoko on 44×44 px (WCAG 2.5.5). Tämä koskee painikkeita, linkkejä, lomake-elementtejä ja navigaatioelementtejä.

### 2.4 Väri ja kontrasti

Tekstin ja taustan kontrastisuhde on vähintään 4.5:1. Väri ei yksin riitä tiedon välittämiseen — jokainen värikoodattu tieto ilmaistaan aina myös tekstillä tai ikonilla.

### 2.5 Animaatiot

Animaatiot ovat hienovaraisia (enintään `0.2s ease-in-out`). `prefers-reduced-motion` -asetusta kunnioitetaan: jos asetus on päällä, animaatioita ei näytetä.

### 2.6 Sivun rakenne ja landmarks

Sivun eri alueet merkitään HTML5-elementeillä (`<nav>`, `<main>`, `<header>`, `<footer>` jne.), jotta näppäimistöllä siirtyminen sivun eri alueille on sujuvaa. Jokaisella navigaatioelementillä on yksilöllinen `aria-label`. Sivun alussa on visuaalisesti piilotettu skip-linkki, joka näkyy fokusoitaessa.

### 2.7 Ruudunlukijalle tarkoitetut tekstit (`sr-only`)

`sr-only`-apuluokkaa käytetään tekstille, joka on tarkoitettu vain ruudunlukijoille. Se piilottaa elementin visuaalisesti mutta säilyttää sen avustavalle teknologialle. Tyypillisiä käyttökohteita ovat ikonipainikkeet, hakukenttien labelit ja tila-ilmoitukset.

`display: none` tai `visibility: hidden` piilottaa elementin myös ruudunlukijoilta — niitä ei käytetä saavutettavuustekstien piilottamiseen.

### 2.8 Automaattisesti avautuvat elementit

Elementit, jotka avautuvat automaattisesti tai vaativat käyttäjän toimintaa — kuten evästebanneri tai palveluilmoitukset — sijoitetaan aina sivun yläreunaan ennen headeria. Ne työntävät sivun muuta sisältöä alaspäin eivätkä asemoidu sisällön päälle. Sivuston käyttö ei saa estyä ennen kuin käyttäjä on vastannut.

---

### 3.1 Väripaletti

Värijärjestelmä perustuu valtioneuvoston viralliseen graafiseen ohjeistukseen.

#### 3.1.1 Päävärit

| Nimi | Hex |
|---|---|
| Valtioneuvoston sininen | `#365ABD` |
| Tumma sininen | `#002F6C` |
| Vaalea sininen | `#00A9E0` |

#### 3.1.2 Tukivärit

Tukiväreillä on pieni rooli toiminnallisuuksien osoittamisessa, infografiikassa ja hanketunnuksissa. Niitä käytetään myös huomionauhan vakavuustasojen värikoodauksessa (ks. osio 13.1).

| Nimi | Hex |
|---|---|
| Tumma vihreä | `#00713A` |
| Vaalea vihreä | `#76B82A` |
| Turkoosi | `#00A79F` |
| Sininen | `#2699D6` |
| Purppura | `#8C4091` |
| Pinkki | `#D90066` |
| Punainen | `#E63312` |
| Oranssi | `#F18700` |

#### 3.1.3 Taustavärit

| Nimi | Hex | Käyttö |
|---|---|---|
| Viileä harmaa | `#5D626A` | Metatekstit, disabled-tila, reunaviivat |
| Lämmin harmaa | `#9B9183` | Toissijaiset taustat |

#### 3.1.4 Ministeriöiden dynaamiset värit

Kukin ministeriö käyttää omaa aksenttiväriään, joka ohjataan CSS-muuttujilla. Värit perustuvat ministeriöiden graafisiin ohjeistoihin — ne on tarkistettava ohjeistoista ennen lopullista tuotantokäyttöä.

| Ministeriö | `--ministry-color` | `--ministry-color-light` | `--ministry-color-lighter` | `--ministry-color-dark` | `--ministry-color-darker` |
|---|---|---|---|---|---|
| Valtioneuvoston kanslia | `#002F6C` | `#E8EEF7` | `#F3F7FC` | `#001B42` | `#000A1A` |
| Ulkoministeriö | `#003399` | `#E6EBFA` | `#F3F6FD` | `#001F5A` | `#000D2B` |
| Oikeusministeriö | `#00305A` | `#E6EDF4` | `#F3F6FA` | `#001B36` | `#000A1A` |
| Sisäministeriö | `#8B1A1A` | `#F5E8E8` | `#FBF3F3` | `#5A1010` | `#2A0808` |
| Puolustusministeriö | `#1B3A6B` | `#E8EDF5` | `#F3F6FA` | `#0F2447` | `#050E1A` |
| Valtiovarainministeriö | `#003580` | `#E8F0FA` | `#F3F7FD` | `#002350` | `#000E28` |
| Opetus- ja kulttuuriministeriö | `#005EB8` | `#E8F0FA` | `#F3F7FD` | `#003D7A` | `#001A39` |
| Maa- ja metsätalousministeriö | `#006B3C` | `#E6F2EC` | `#F3F9F6` | `#004A26` | `#001F11` |
| Liikenne- ja viestintäministeriö | `#0072C6` | `#E6F1FB` | `#F3F8FD` | `#004A85` | `#001D3A` |
| Työ- ja elinkeinoministeriö | `#0058A0` | `#E6EFF8` | `#F3F7FC` | `#003A68` | `#001A33` |
| Sosiaali- ja terveysministeriö | `#006B4D` | `#E6F2EE` | `#F3F9F6` | `#004A35` | `#002019` |
| Ympäristöministeriö | `#00703C` | `#E6F2EC` | `#F3F9F6` | `#004A26` | `#001F11` |

> **Värien saavutettavuus:** Kaikki `--ministry-color`-värit on valittu niin, että valkoinen teksti (`#FFFFFF`) niiden päällä täyttää WCAG AA -vaatimuksen (≥ 4.5:1). Saavutettavuus tarkistetaan aina lopullisessa toteutuksessa.

> **Värien käytettävyys:** Käyttöliittymien virhe- ja varoitusvärien on erotuttava riittävän selvästi sivuston muista väreistä. Virhe- ja varoitusvärit ovat kaikilla sivustoilla samat.

### 3.2 Typografia ja tekstihierarkia

**Fonttiperheet:** Noto Sans (leipäteksti, käyttöliittymä), Noto Sans Extra Condensed (otsikot) ja Noto Sans Light (metatiedot tms.).

**Otsikkofontin tekninen toteutus:** Noto Sans on variable font, jonka leveyttä ohjataan `wdth`-akselilla. Extra condensed -leveys saadaan arvolla `wdth: 62.5`, joka vastaa CSS-arvoa `font-stretch: extra-condensed`. Google Fonts -import: `family=Noto+Sans:wdth,wght@62.5,700`.

**Rivivälit:** Leipätekstissä aina vähintään 1.5. Otsikoissa tiiviimpi 1.2.

**Yksiköt:** Koodissa käytetään suhteellisia rem-yksiköitä (perustuen 16 px kokoon).

**Saavutettavuus:** Tekstin on oltava skaalattavissa 200 % asti selaimen asetuksissa, niin ettei se estä sisällön lukemista tai sivuston käyttöä (ks. osio 2.1).

#### Tekstityypit

| Tyyppi | Fontti | Desktop | Mobiili | Käyttö |
|---|---|---|---|---|
| H1 | Noto Sans Extra Condensed Bold 700 | 40px / 2.5rem | 32px / 2rem | Sivun pääotsikko |
| H2 | Noto Sans Extra Condensed Bold 700 | 32px / 2rem | 28px / 1.75rem | Pääväliotsikot |
| H3 | Noto Sans Extra Condensed Bold 700 | 24px / 1.5rem | 20px / 1.25rem | Korttien ja osioiden otsikot |
| H4 | Noto Sans Extra Condensed Bold 700 | 20px / 1.25rem | 18px / 1.125rem | Pienet otsikot |
| Ingressi | Noto Sans Regular 400 | 20px / 1.25rem | 20px / 1.25rem | Johdantoteksti |
| Leipäteksti | Noto Sans Regular 400 | 16px / 1rem | 16px / 1rem | Ensisijainen lukuteksti |
| Pieni teksti | Noto Sans Regular 400 | 14px / 0.875rem | 14px / 0.875rem | Päivämäärät, kuvatekstit |
| UI-teksti | Noto Sans Bold 700 | 16px / 1rem | 16px / 1rem | Navigaatio, painikkeet |
| Mikroteksti | Noto Sans Regular 400 | 12px / 0.75rem | 12px / 0.75rem | Tagit, sisältötyyppitunnisteet, tiiviit metatiedot |
| Koodi | Monospace (esim. Courier New) | 14px / 0.875rem | 14px / 0.875rem | Näytettävät koodinpätkät, väri- ja tokenarvot |

#### Pystyvälistykset

Välistykset noudattavat 8 px -pohjaista järjestelmää (ks. osio 3.3). Otsikon yläpuolinen väli on suurempi kuin alapuolinen — otsikko sitoutuu visuaalisesti alla olevaan sisältöön.

| Elementti | Väli yläpuolella | Väli alapuolella |
|---|---|---|
| H1 | 0 (sivun ensimmäinen elementti) | 24px / `--space-m` |
| H2 | 48px / `--space-xl` | 16px / `--space-s` |
| H3 | 32px / `--space-l` | 8px / `--space-xs` |
| H4 | 24px / `--space-m` | 8px / `--space-xs` |
| Ingressi | 0 (seuraa aina H1:tä) | 32px / `--space-l` |
| Leipäteksti | 0 | 16px / `--space-s` kappaleiden välillä |
| Pieni teksti | 8px / `--space-xs` | 0 |

### 3.3 Välistykset

Suunnittelussa käytetään 8 px -pohjaista järjestelmää:

| Nimi | Arvo | CSS-muuttuja |
|---|---|---|
| xs | 8px | `--space-xs` |
| s | 16px | `--space-s` |
| m | 24px | `--space-m` |
| l | 32px | `--space-l` |
| xl | 48px | `--space-xl` |
| 2xl | 64px | `--space-2xl` |

### 3.4 Kulmaviiste

Kaikissa elementeissä käytetään kevyttä kulmaviistettä yhtenäisen ja pehmeän ilmeen varmistamiseksi. Oletusarvo on `border-radius: 5px`. Tätä käytetään painikkeissa, korteissa, lomake-elementeissä, tageissa, huomionauhassa ja muissa vastaavissa elementeissä.

---

### 4.1 Breakpointit

Sivustot noudattavat Mobile First -periaatetta: tyylimääritykset kirjoitetaan ensin pienimmälle näytölle ja skaalataan ylöspäin `min-width`-mediakyselyillä.

| Nimi | Arvo | Tyypilliset laitteet |
|---|---|---|
| s | 0–479px | Puhelimet |
| m | 480–767px | Tabletit |
| l | 768–1439px | Kannettavat |
| xl | 1440px– | Pöytäkoneet |

### 4.2 Grid-järjestelmä

| Ominaisuus | s | m | l | xl |
|---|---|---|---|---|
| Sarakkeiden määrä | 4 | 8 | 12 | 12 |
| Gutter | 16px | 24px | 24px | 32px |
| Marginaali | 24px | 32px | 32px | auto |
| Maksimileveys | 100% | 100% | 100% | 1280px |

### 4.3 Käyttöperiaatteet

- Maksimileveys on **1280 px** — sisältöalue ei kasva tätä leveämmäksi xl-näytöillä. Taustakuvat, väripalkit ja bannerit voivat ulottua koko näytön leveyteen.
- Leipäteksti näytetään koko sisältöpalstan levyisenä (maksimileveyteen 1280 px saakka). Erillistä tekstirivin merkkileveyden rajausta ei käytetä.
- Gridin alasarakkeistus tapahtuu aina täysinä sarakeyksiköinä (esim. 8+4, 4+4+4, 3+9).

---

## 5. HEADER JA FOOTER

### 5.1 Header (ylätunniste)

Header on yksinkertainen ja pelkistetty — siinä näytetään valtioneuvoston/ministeriön logo vasemmalla ja toimintopainikkeet oikealla. Ministeriökohtainen väri näkyy headerin taustavärissä.

**Headerin rakenne:**
- Taustaväri: ministeriökohtainen
- Vasemmalla: ministeriön virallinen tunnus (SVG), linkitettynä etusivulle
- Oikealla: kielivalikko (FI / SV / EN) + hakuikoni + hampurilainen / megamenu-painike

**Logo:**
- Aina linkki etusivulle: `aria-label="[Ministeriön nimi] – etusivu"`
- SVG-muodossa skaalautuvuuden varmistamiseksi

**Kiinnittyminen:**
- Header kiinnitetty sivun yläreunaan (`position: sticky; top: 0`)
- Kiinnitetyn headerin tausta täysin peittävä

**Kielivalikko:**
- Tekstipainikkeet FI / SV / EN, liputtomina
- Aktiivinen kieli korostetaan visuaalisesti
- Puuttuva kieliversio piilotetaan tai esitetään epäaktiivisena

**Megamenu:**
- Avautuu "Valikko"-painikkeesta headerin oikeasta reunasta
- Megamenu peittää sivun sisällön kokonaan — se on käytännössä koko näytön levyinen paneeli, joka laskeutuu headerin alle
- Sisältö järjestetään selkeisiin ryhmiin, esim. ministeriön päänavigaation rakennetta noudattaen
- Megamenun tausta on tumma (ministeriökohtainen väri tai `--color-dark`), teksti valkoinen — tämä erottaa sen visuaalisesti sivun muusta sisällöstä
- Sulkeutuu "Sulje"-painikkeesta, Escape-näppäimellä sekä fokuksen siirtyessä megamenun ulkopuolelle

### 5.2 Footer (alatunniste)

Footer koostuu kolmesta osasta:

**Lisäfooter (valinnainen):** Parantaa tiedon löydettävyyttä. Voidaan käyttää esim. tärkeiden tai suosittujen sisältöjen nostamiseen.

**Lakisääteinen pääfooter:** 3–4 palstaa leveillä näytöillä, pino mobiililla.
- Pakolliset sisällöt: organisaation nimi ja logo, yhteystiedot, linkit saavutettavuusselosteeseen, tietosuojaselosteeseen, evästekäytäntöihin ja vastaaviin pakollisiin sisältöihin.

**Copyright-footer:**
- Copyright-merkintä (automaattisesti päivittyvä vuosi) ja linkki esim. sivukarttaan.

---

## 6. NAVIGAATIO

Navigaatio rakentuu kolmesta erillisestä tasosta: ministeriövalikosta, päänavigaatiosta ja apunavigaatiosta.

### 6.1 Ministeriövalikko

Kaikilla sivustoilla identtinen elementti, joka mahdollistaa sujuvan siirtymisen ministeriöiden välillä. Ylläpidetään keskitetysti — muutokset päivittyvät automaattisesti kaikille sivustoille.

- Sijoitetaan sivun alkuun, esimerkiksi headerin yläpuolelle, selkeästi päänavigaatiosta erotettuna
- Esitetään kompaktina "Valtioneuvosto ja ministeriöt" -painikkeena, joka avaa esim. flyout-valikon
- Valikko avautuu klikkauksella tai fokuksella (ei hover-only)
- Sulkeutuu Escape-näppäimellä sekä fokuksen siirtyessä valikon ulkopuolelle
- Käyttää aina valtioneuvoston sinistä (`#365ABD`), ei ministeriökohtaista `--ministry-color`-arvoa

### 6.2 Päänavigaatio

Sivustokohtainen, heijastaa ministeriön sisältörakennetta. Tukee enintään kahta näkyvää tasoa (sivustohierarkian tasot 2 ja 3 — taso 1 on sivuston päätaso, eli käytännössä etusivu). Syvempiä tasoja hallitaan apunavigaatiolla.

- Päänavigaation kohtien määrä suositellaan rajattavaksi 5–7 kohteeseen — liian monta kohtaa heikentää luettavuutta ja käytettävyyttä
- Aktiivinen navigaatiokohta korostetaan `--ministry-color`-muuttujalla sekä visuaalisella indikaattorilla, esim. alareunaan sijoitetulla värillisellä viivalla
- Dropdown avautuu klikkauksella tai fokuksella — ei pelkällä hoverilla
- Dropdownin tausta on valkoinen, ja se erotetaan päänavigaatiosta selkeällä varjolla tai reunaviivalla
- Aktiivinen dropdown-kohta korostetaan samoin kuin päänavigaation aktiivinen kohta

### 6.3 Apunavigaatio

Esittää käyttäjän kulloinkin selaaman osion sisäisen hierarkian.

- Apunavigaatio näytetään esim. sivupalkkina leveillä näytöillä
- Mobiilissa apunavigaatio näytetään esim. taittuvana elementtinä sisältöalueen yläosassa

### 6.4 Murupolku

Murupolku esitetään aina sivun sisältöosion yläpuolella.

### 6.5 Mobiilinavigaatio

- Hampurilaispainike tai vastaava headerin reunassa, vähintään 44×44 px (ks. osio 2.3)
- Valikon sisältö järjestyksessä: ministeriövalikko → kielivalikko → päänavigaatio

### 6.6 Navigaation saavutettavuusvaatimukset

| Vaatimus | Toteutus |
|---|---|
| Näppäimistökäyttö | Tab, Enter, Space, nuolinäppäimet, Escape |
| Aktiivinen kohta | `aria-current="page"` + visuaalinen korostus |
| Dropdown-tila | `aria-expanded="true/false"` |
| Fokus-indikaattori | Vähintään 3 px, kontrasti ≥ 3:1 (ks. osio 2.2) |
| Landmark | `<nav>` + yksilöllinen `aria-label` jokaiselle navigaatioelementille |
| Skip-linkki | "Siirry sisältöön" ennen navigaatiota, näkyy fokusoitaessa (ks. osio 2.6) |
| Focus trap | Mobiilivalikon ollessa auki fokus ei karkaa valikon ulkopuolelle |
| Escape | Sulkee avoimen valikon ja palauttaa fokuksen avaavaan painikkeeseen |

---

## 7. PAINIKKEET JA LINKIT

### 7.1 Painikkeet

Painikkeet käynnistävät toiminnon. Ne eivät koskaan ole navigointilinkkejä.

| Tyyppi | Käyttö | Kuvaus |
|---|---|---|
| Primary | Sivun tärkein toiminto, yksi kerrallaan | `background: var(--ministry-color)` |
| Secondary | Toissijainen toiminto primary:n rinnalla | Läpinäkyvä tausta, `--ministry-color`-reunaviiva |
| Ghost | Vähemmän tärkeät toiminnot | Ei reunaviivaa, alleviivattu teksti |
| Destructive | Peruuttamattomat toiminnot | `background: #E63312` |

**Koot:**

| Koko | Padding | Käyttö |
|---|---|---|
| lg | 16px 32px | Hero-alueet, selkeät CTA:t |
| md | 12px 24px | Lomakkeet, yleiset toiminnot |
| sm | 8px 16px | Tiheät käyttöliittymät |

Minimikorkeus kaikissa kooissa: **44 px** (ks. osio 2.3).

### 7.2 Linkit

**Leipätekstilinkki:** `--ministry-color`, alleviivaus aina näkyvissä.

**Ulkoinen linkki:** Merkitään ikonilla ja ilmoitetaan ruudunlukijoille `(avautuu uuteen välilehteen)` — ruudunlukijoille tehty ilmoitus ei kuitenkaan kopioidu, kun tekstiä kopioidaan esim. selaimesta tekstidokumentteihin.

**Latauslinkki:** Tiedostotyyppi ja koko ilmoitetaan käyttäjälle.

**CTA-linkki:** Linkki tyylitelty painiketyylisesti, johtaa sivulle. Semanttisesti `<a>`, ei `<button>`.

---

## 8. LOMAKE-ELEMENTIT

### 8.1 Yleiset periaatteet

- Jokainen kenttä merkitty näkyvällä `<label>`-elementillä — placeholder ei korvaa labelia
- Pakolliset kentät: asteriski \* visuaalisesti + `aria-required="true"` ohjelmallisesti
- Toisiinsa liittyvät kentät ryhmitellään `<fieldset>` + `<legend>`-elementeillä
- Kaikki lomakkeet tietoturvatestataan ennen käyttöönottoa. Testaus kattaa vähintään XSS- (cross-site scripting), CSRF- (cross-site request forgery) ja SQL-injektiohaavoittuvuudet.

### 8.2 Lomake-elementit

**Tekstikenttä:** Reunaviiva 2 px, fokuksessa korostetaan `--ministry-color`-muuttujalla. Virhetilassa reunaviivan väri muuttuu virheväriksi (`#E63312`).

**Textarea:** `resize: vertical`, minimikorkeus 120 px.

**Select:** Natiivi `<select>` ensisijaisesti. Mukautettu sallittu vain täysimääräisellä ARIA-tuella.

**Checkbox ja Radio:** `accent-color: var(--ministry-color)`, minimikoko 24×24 px, ryhmitellään `<fieldset>` + `<legend>`.

### 8.3 Virheilmoitukset

Virheilmoitus esitetään kentän alla välittömästi. Useista virheistä kootaan yhteenveto lomakkeen yläosaan, joka saa fokuksen lähetyksen jälkeen.

---

## 9. KORTIT JA NOSTOT

### 9.1 Yleiset periaatteet

- Nostojen otsikkolinkki on ainoa klikkausalue — ei koko kortin kattavaa linkkiä
- Kuvat toimivat kuvituksena: `alt=""` kun kuva ei välitä informaatiota
- Nostot toimivat ilman kuvaa — kuvan puuttuminen ei riko asettelua

### 9.2 Kortin esitystavat

| Tapa | Rakenne | Käyttö |
|---|---|---|
| Ruudukko | 3 → 2 → 1 saraketta | Etusivut, koontisivut |
| Lista | Kuva vasemmalla, teksti oikealla | Tiedotelistaukset |
| Nosto (featured) | Koko leveys, kuva 50 % | Tärkein uutinen etusivulla |

### 9.3 Hankekortin tilamerkintä

Hankkeen tila ilmaistaan sekä tekstillä että värikoodilla — väri ei ole ainoa tapa välittää tilatietoa (ks. osio 2.4). Tilavärit ovat: aktiivinen (tumma vihreä `#00713A`), suunnitteilla (sininen `#2699D6`) ja päättynyt (viileä harmaa `#5D626A`). Tila esitetään pienen värillisen pisteen ja tekstin yhdistelmänä.

### 9.4 Sivutuskomponentti (Pagination)

Sivutusta käytetään tiedotelistauksissa, hakutuloksissa ja hankelistauksissa, kun sisältöä on enemmän kuin yhdelle sivulle mahtuu.

**Saavutettavuus** (ks. osio 2):
- `<nav>` + yksilöllinen `aria-label` (viittaa listaukseen, esim. "Tiedotteiden sivutus")
- Aktiivinen sivu: `aria-current="page"`
- Jokaiselle sivunumerolle `aria-label`, joka kertoo sivunumeron selkeästi
- Pisteet (`…`) merkitään `aria-hidden="true"` — ne eivät välitä toiminnallista tietoa

### 9.5 Tagi ja sisältötyyppitunniste (Tag / Badge)

Tageja käytetään sisältötyypin (Tiedote, Uutinen, Puhe...) ja hankkeen tilan (Käynnissä, Suunnitteilla, Päättynyt...) ilmaisemiseen esim. korteissa, listauksissa ja hankenäkymissä.

**Käyttöperiaatteet:**
- Sisältötyyppitunniste käyttää aina `--ministry-color`- ja `--ministry-color-light`-muuttujia, joten väri vaihtuu automaattisesti ministeriöittäin
- Hankkeen tilatagi käyttää neutraalia taustaväriä ja värillistä pistettä — väripiste ei yksin riitä, tila kerrotaan aina myös tekstinä (ks. osio 2.4)
- Tageja ei käytetä interaktiivisina elementteinä (ei linkkejä, ei painikkeita) ellei sille ole selkeää toiminnallista tarvetta

---

## 10. ACCORDION JA TAULUKOT

### 10.1 Accordion

- Trigger on aina `<button>`, ei `<div>` tai `<a>`
- Suljetussa tilassa käytetään `hidden`-attribuuttia — ei `display: none` pysyvästi (hakukoneet indeksoivat sisällön)
- Animaatio enintään `0.2s ease-in-out` (ks. osio 2.5)
- Ikonin rotaatio avautuessa: `transform: rotate(180deg)`

### 10.2 Taulukot

- `role="region"` + `tabindex="0"` mahdollistaa vierittyvän taulukon näppäimistökäytön
- `<caption>` pakollinen kaikissa taulukoissa
- `scope="col"` sarakkeotsikoissa, `scope="row"` riviotsikoissa
- Excel-tuonnissa `scope`- ja `caption`-merkinnät lisätään automaattisesti tai ohjataan sisällöntuottajaa

---

## 11. IKONOGRAFIA

### 11.1 Käyttöliittymäikonit

**Kirjasto:** Google Material Symbols (Apache 2.0).

**Tyyli:** Outlined tai filled — valitaan projektin alussa ja pidetään yhtenäisenä läpi sivuston.

| Konteksti | Koko |
|---|---|
| Pienoisikoni | 16×16 px |
| Perusikoni | 20×20 px |
| Medianikoni | 24×24 px |
| Suuri ikoni | 32×32 px |

### 11.2 Ikonien saavutettavuus

Koristeelliset ikonit ja klikattavat ikonit erotetaan kooditasolla. Koristeelliselle ikonikuville asetetaan `aria-hidden="true"` ja `focusable="false"`. Klikattavilla ikonipainikkeilla, joilla ei ole näkyvää tekstiä, käytetään `sr-only`-tekstiä tai `aria-label`-attribuuttia (ks. osio 2.7).

### 11.3 Kuvittavat piktogrammit

- Vapaaehtoisia, täydentävät tekstisisältöä
- Elementtien on toimittava myös ilman piktogrammia — väripinta fallbackina
- Tyyli vastaa käyttöliittymäikoneja: sama viivan paksuus ja optinen koko

### 11.4 Kielletyt käytännöt

- Väri ei ole ainoa tapa erottaa ikonien merkityksiä (ks. osio 2.4)

---

## 12. VALOKUVAT JA MEDIA

### 12.1 Käyttöperiaatteet

- Valokuvan käyttö ei ole pakollista — lähtökohtaisesti jokainen elementti toimii ilman kuvaa
- Kuviin ei suunnitella filttereitä tai gradientteja — muokkaustyyli on luonnollinen ja valoisa
- Kuvitusgrafiikkoja ei käytetä tiedotekuvana

### 12.2 Kuvasuhteet

| Käyttökohde | Kuvasuhde |
|---|---|
| Tiedote- ja uutiskortti | 16:9 |
| Nostokortti (featured) | 16:9 tai 3:2 |
| Kolumni / kasvokuva | 1:1 |
| Hero-alue | 21:9 tai 16:9 |

### 12.3 Kuvateksti ja kuvalähde

Kuvateksti on valinnainen, mutta suositeltava aina kun kuva tarvitsee kontekstia tai selitystä. Kuvaaja merkitään aina, kun se on tiedossa. Kuvaaja merkitään muodossa "Kuva: Etunimi Sukunimi / Organisaatio". Kuvateksti ja kuvaaja esitetään kuvan alapuolella pienemmällä tekstikoolla (pieni teksti, ks. osio 3.2) viileän harmaan (`#5D626A`) värisenä.

### 12.4 Alt-tekstit

| Kuvatyyppi | Alt-teksti |
|---|---|
| Informatiivinen | Kuvaa kuvan keskeisen sisällön |
| Kuvituskuva | `alt=""` — tyhjä |
| Kasvokuva | Henkilön nimi ja titteli |
| Infografiikka | Kuvaa data sanallisesti tai linkitä tekstitaulukkoon |

### 12.5 Tekninen optimointi

- Formaatti: Päätetään toteutusvaiheessa
- `loading="lazy"` listauksen kuville, `loading="eager"` hero-kuville

### 12.6 Videot

- Tekstitys (CC) pakollinen kaikille puhutuille videoille (WCAG 1.2.2)
- Automaattinen toisto äänellä kielletty
- Facade-tekniikka: esikatselukuva ensin, upotus ladataan käyttäjän klikatessa

### 12.7 Karuselli

- Ei automaattista pyöritystä (ks. osio 2.1)
- Edellinen/seuraava-painikkeet aina näkyvissä
- Aktiivinen slide: `aria-current="true"` + visuaalinen indikaattori

---

## 13. HUOMIONAUHA, VIRHEILMOITUKSET JA VIRHESIVUT

### 13.1 Huomionauha

| Taso | Taustaväri | Reunaväri |
|---|---|---|
| Tiedotus (info) | `#E8F0FB` | `#2699D6` |
| Varoitus (warning) | `#FFF3CD` | `#F18700` |
| Virhe (error) | `#FDECEA` | `#E63312` |
| Onnistuminen (success) | `#E6F4EC` | `#00713A` |

- Vakavuustaso ilmaistaan aina sekä värin, ikonin että tekstin avulla (ks. osio 2.4)
- Kiireellisissä viesteissä käytetään `role="alert"`, muissa `role="status"` (ks. osio 2)
- Huomionauha ei näy eikä varaa tilaa ilman aktiivista viestiä
- Voidaan ajastaa tai näyttää/piilottaa manuaalisesti

### 13.2 Virhesivut

| Koodi | Nimi | Kuvaus |
|---|---|---|
| 400 | Bad Request | Virheellinen osoite tai parametri |
| 403 | Forbidden | Ei oikeutta sisältöön |
| 404 | Not Found | Sivu poistettu tai osoite muuttunut |
| 500 | Internal Server Error | Odottamaton palvelinvirhe |
| 503 | Service Unavailable | Tilapäinen huoltokatko |

Jokainen virhesivu sisältää: virhekoodin ja -nimen (H1), selkeän kuvauksen, toimintaohjeet sekä linkit etusivulle ja hakuun.

### 13.3 Huoltotila (Maintenance mode)

Teknisesti erillinen WordPress-kokonaisuudesta — toimii myös palvelinvirheen sattuessa. Toteutetaan staattisena HTML-tiedostona palvelinympäristön tasolla.

---

## 14. HAKUTOIMINTO

### 14.1 Rakenne

Kolme toisiaan täydentävää tasoa: headerissa sijaitseva pikahakulomake, hakutulossivun täysi haku sekä kohdennetut erityishaut.

### 14.2 Pikahakulomake

Pikahakulomake sijaitsee headerissa ja on käytettävissä kaikilla sivuilla. Se koostuu tekstikentästä ja hakupainikkeesta. Lomake tukee autocomplete-ehdotuksia, jotka avautuvat käyttäjän kirjoittaessa.

**Autocomplete-näppäimistökäyttö:** ↓/↑ liikkuu ehdotusten välillä, Enter valitsee, Escape sulkee listan.

### 14.3 Hakutulossivun rakenne

Hakutulossivulla esitetään haun tulokset suodatus- ja järjestelymahdollisuuksien kera. Tulosmäärä ilmoitetaan selkeästi hakukentän yhteydessä ja päivittyy suodatinmuutosten yhteydessä. Hakusana korostetaan tuloksissa `<mark>`-elementillä. Sivutus toteutetaan osion 9.4 periaatteiden mukaisesti.

### 14.4 Kohdennetut haut

**Tiedotehaku:** Suodattimet: aikaväli, ministeriö, aiheluokka, sisältötyyppi.

**Hankehaku:** Kohdistuu Hankeikkuna-rajapintaan. Suodattimet: hankkeen tila, ministeriö, tyyppi, aikaväli.

**Yhteystietohaku:** Hakee Elisa OC -integraatiosta nimellä, tehtävänimikkeellä tai organisaatiolla.

### 14.5 Ei tuloksia -tila

Esitetään selkeä viesti, kirjoitusasukehotus, kehotus lyhentää hakusanaa sekä linkki valtioneuvoston laajaan hakuun.

### 14.6 Valtioneuvoston laajuinen haku

Valtioneuvosto.fi tarjoaa koko sivustoperheen kattavan haun. Tulokset ryhmitellään ministeriöittäin, duplikaatit tunnistetaan automaattisesti.

---

## 15. SISÄLTÖLISTAUKSET

Listaussivut ovat valtioneuvoston sivustoperheen keskeisimpiä näkymiä. Niillä esitetään tiedotteet, uutiset, puheet, kolumnit, tapahtumat ja hankkeet yhtenäisellä rakenteella.

### 15.1 Sisältötyypit ja niiden erityispiirteet

| Sisältötyyppi | Tagi | Päivämäärä-kenttä | Ministeriösuodatin | Muut suodattimet |
|---|---|---|---|---|
| Tiedote | Tiedote | Julkaisupäivä | Kyllä | Aiheluokka |
| Uutinen | Uutinen | Julkaisupäivä | Kyllä | Aiheluokka |
| Puhe | Puhe | Puhumispäivä | Kyllä | Puhuja (ministeri) |
| Kolumni | Kolumni | Julkaisupäivä | Kyllä | Kirjoittaja |
| Tapahtuma | Tapahtuma | Tapahtuma-aika | Kyllä | Tapahtumatyyppi |
| Hanke | Tilatagi | Hankkeen aloituspäivä | Kyllä | Tila, tyyppi, aikaväli |

### 15.2 Listaussivun rakenne

Listaussivu koostuu kolmesta vyöhykkeestä: sivun otsikkoalue, suodatin- ja järjestelypalkki sekä tulosalue.

### 15.3 Suodatin- ja järjestelypalkki

Suodattimet ja järjestely esitetään yhdellä rivillä sisältöalueen yläreunassa. Mobiililla suodattimet kokoontuvat "Suodata"-painikkeen taakse.

**Aktiiviset suodattimet (applied filters):** Kun suodatin on aktiivinen, se näytetään suodatinpalkin alapuolella poistettavina tageina.

### 15.4 Tulosalue ja korttiruudukko

Tulokset esitetään oletuksena listanäkymässä. Listanäkymässä kortti on vaakasuuntainen: kuva (jos on) vasemmalla, teksti oikealla.

### 15.5 Tyhjä tila (ei tuloksia)

Kun suodattimet eivät tuota tuloksia, näytetään selkeä viesti — ei tyhjää sivua.

### 15.6 Ladataan lisää vs. sivutus

Listauksissa käytetään joko perinteistä sivutusta tai "Lataa lisää" -painiketta. Valinta tehdään sisältötyypin ja sivuston vaatimusten mukaan:

| Tapa | Milloin | Huom. |
|---|---|---|
| Sivutus (pagination) | Tiedotteet, uutiset, hankehaku | Tukee kirjanmerkkejä ja URL:n jakamista |
| Lataa lisää -painike | Etusivun nostot, tapahtumakalenteri | Lisää tuloksia olemassa olevien perään |

### 15.7 Saavutettavuusvaatimukset listauksissa

| Vaatimus | Toteutus |
|---|---|
| Listauksen semantiikka | `<ol>` (järjestetty) tai `<ul>` (järjestämätön) + `aria-label` |
| Tulosmäärän ilmoitus | `aria-live="polite"` + `aria-atomic="true"` suodatinmuutoksen yhteydessä |
| Suodattimet | `<form role="search">` tai `role="search"` -ryhmittely |
| Aktiiviset suodattimet | Jokainen poistopainike nimeää suodattimen: `aria-label="Poista suodatin: X"` |
| Lataa lisää | Painike saa fokuksen ja ilmoittaa latauksen tuloksen |
| Kortin linkki | Yksiselitteinen linkkiteksti — otsikko riittää; vältä "Lue lisää" ilman kontekstia |

---

## 16. MONIKIELISYYS

Sivuston kieli ja yksittäisen sisältöelementin kieli on erotettava toisistaan sekä käyttäjäkokemuksen että saavutettavuuden kannalta. Avustavat teknologiat (ruudunlukijat) käyttävät `lang`-attribuuttia valitakseen oikean ääntämissäännöstön.

**Sivuston peruskieli** määritellään `<html>`-elementissä erikseen suomen-, ruotsin- ja englanninkielisille versioille (`lang="fi"`, `lang="sv"`, `lang="en"`).

**Vieraskielinen sisältö** sivun sisällä merkitään `lang`-attribuutilla asianomaisen elementin tasolla.

**RTL-kielet** (arabia, heprea) vaativat lisäksi `dir="rtl"`-attribuutin asianomaiselle elementille. Globaalia `dir`-attribuuttia ei muuteta, ellei koko sivusto ole RTL-kielistä.

**Kielivalikon toteutus:** Kielivalikossa linkit osoittavat saman sivun eri kieliversioihin. Kieliversioiden välinen linkitys toteutetaan `hreflang`-attribuuteilla `<head>`-osiossa.

---

## 17. TEKNINEN ARKKITEHTUURI

**Nimeäminen:** Noudatetaan BEM-metodologiaa (esim. `card__title--active`).

**Kansiorakenne:** Erotellaan tyylimuuttujat, saavutettavuus, asettelu ja komponentit omiin tiedostoihinsa.

**Alusta:** WordPress Multisite -arkkitehtuuri, jossa kaikki sivustot jakavat saman teeman.

**Väriteemat:** Rakennetaan dynaamisiksi globaalien CSS-muuttujien varaan, jotta ministeriökohtainen värinvaihto tapahtuu automaattisesti. CSS-muuttujien nimet ja oletusarvot on määritelty osiossa 3.

---

## 18. EVÄSTEBANNERI

Evästebanneri näytetään sivuston yläosassa ennen muuta sisältöä. Se työntää sivun sisältöä alaspäin — se ei asemoidu sisällön päälle eikä estä sivuston lukemista (ks. osio 2.8).

Evästeitä ei tallenneta ennen kuin käyttäjä on tehnyt aktiivisen valinnan.

**Rakenne ja toiminta:**
- Bannerissa on kaksi painiketta: "Hyväksy evästeet" ja "Hylkää evästeet"
- Bannerissa on linkki evästekäytäntöihin
- Banneri sulkeutuu kumman tahansa painikkeen painamisen jälkeen
- Käyttäjän valinta tallennetaan, eikä banneria näytetä uudelleen saman istunnon aikana

**Sisältövaatimukset:**
- Kerrotaan selkeästi, miksi evästeitä kerätään
- Kerrotaan, mitä haittaa evästeiden hylkäämisestä voi olla (esim. tiettyjen toimintojen rajoittuminen)
- Kieli on ystävällistä ja selkeää — ei juridista kapulakieltä

**Saavutettavuus** (ks. osio 2):
- Banneri ei estä näppäimistökäyttöä eikä ruudunlukijaa
- Painikkeiden minimikoko 44×44 px

---

## 19. TULOSTUSTYYLI

Tulostusversio optimoidaan automaattisesti selaimen tulostustyylillä (`@media print`). Erillistä tulostuspainiketta ei tarvita.

**Piilotetaan tulostuksessa:**
- Header ja footer
- Navigaatio
- Evästebanneri
- Hakutoiminto
- Sivutuskomponentti
- Painikkeet, jotka eivät liity sisältöön

**Tulostuksessa näytetään:**
- Sivun otsikko
- Julkaisupäivä ja sisältötyyppi
- Leipäteksti, otsikot ja kuvat
- Ulkoisten linkkien URL-osoitteet tekstinä linkin perässä
- Ministeriön nimi ja sivuston osoite sivun alaosassa

**Typografia ja asettelu:**
- Fonttikoko vähintään 12 pt
- Rivinväli vähintään 1.5
- Musta teksti valkoisella taustalla — ministeriövärejä ei käytetä
- Yksisarakkeinen asettelu
- Sivunumero ja tulostuspäivämäärä automaattisesti sivun alaosaan

---

## 20. VERSIOINTI JA MUUTOSHISTORIA

### 20.1 Dokumentin omistajuus

**Omistaja:** Valtioneuvoston kanslia, verkkoviestintä
**Säilytyspaikka:** Versionhallinta (Git), projektin repositorio
**Tiedostomuoto:** Markdown (`.md`)

### 20.2 Versiointikäytäntö

Dokumentti noudattaa semanttista versiointia (semver: `MAJOR.MINOR.PATCH`):

| Tyyppi | Milloin |
|---|---|
| MAJOR | Taaksepäin yhteensopimaton muutos |
| MINOR | Uusi ominaisuus, ei riko olemassa olevaa |
| PATCH | Korjaus tai täsmennys |

### 20.3 Muutosprosessi

1. Muutosehdotus kirjataan tehtävänhallintajärjestelmään
2. Valtioneuvoston kanslia arvioi vaikutukset
3. MINOR ja MAJOR edellyttävät tilaajan hyväksynnän
4. Muutos kirjataan muutoshistoriaan ja versionumero päivitetään
5. Tekniselle toteuttajalle tiedotetaan ennen voimaantuloa

### 20.4 Muutoshistoria

```
## [2.5.0] – 2026-07-07
### Lisätty
- Osio 3.2: Tekstityypit-taulukkoon lisätty Mikroteksti (12px) ja Koodi (monospace) — aiemmin toteutuksessa käytössä, mutta puuttuivat speksistä
- Osio 3.3: Lisätty puuttunut osio-otsikko "Välistykset" (aiemmin siihen viitattiin ilman että osiota oli olemassa) sekä tokenit xl (48px) ja 2xl (64px)
### Muutettu
- Osio 3.2: Korjattu H2:n ylävälin merkintä muotoon `--space-xl` (48px) — aiempi "3 × --space-xs" olisi ollut 24px
- Osio 4.3: Leipätekstin merkkileveysrajaus poistettu; teksti näytetään koko sisältöpalstan levyisenä

## [2.4.0] – 2026-05-08
### Muutettu
- Osio 3.2: Otsikkofontti vaihdettu Noto Sans Condensed → Noto Sans Extra Condensed (`font-stretch: extra-condensed`, `wdth: 62.5`)
- Osio 3.2: Lisätty tekninen toteutusohje Google Fonts variable font -importista

## [2.3.0] – 2026-05-07
### Lisätty
- Osio 3.2: Pystyvälistykset-taulukko tekstityyppien yhteyteen

## [2.2.0] – 2026-05-07
### Lisätty
- Osio 2.8: Automaattisesti avautuvat elementit
- Osio 3.4: Kulmaviiste (border-radius)
### Muutettu
- Osio 18: Evästebanneri — lisätty viittaus osioon 2.8

## [2.1.0] – 2026-05-06
### Lisätty
- Osio 18: Evästebanneri
- Osio 19: Tulostustyyli
- Osio 6.6: Navigaation saavutettavuusvaatimukset palautettu
### Muutettu
- Osio 5.1: Megamenun kuvaus laajennettu
- Osio 6.2: Päänavigaation kuvaus laajennettu
- Osio 8.1: Lomakkeiden tietoturvavaatimukset tarkennettu (XSS, CSRF, SQL-injektio)
- Osio 9.3: Hankekortin tilavärit kuvattu sanallisesti, CSS-esimerkki poistettu
- Osio 12.3: Kuvatekstin ja kuvaajan ohjeistus tarkennettu
- Osio 20: Versiointi siirretty viimeiseksi osioksi (20)

## [2.0.0] – 2026-05-06
### Muutettu
- Dokumentin rakenne uusittu kokonaan: osiot järjestetty uudelleen loogisempaan järjestykseen
- Uusi osio 2: Saavutettavuuden perusperiaatteet — koottu hajallaan olleista saavutettavuusmaininnoista
- Osio 1: "Sukunäköisyys" muutettu "Yhtenäisyydeksi"
- Osio 3: Nimi muutettu "Design-tokeneiksi", animaatiot siirretty osioon 2
- Osio 4: Grid — koodiesimerkki poistettu, tiedot löytyvät taulukoista
- Osio 6: Navigaatio — numerointi korjattu, järjestys selkeytetty, kielivalikko siirretty osioon 5
- Osio 9: Nimi muutettu "Kortit ja nostoksi"
- Osio 16: Monikielisyys nostettu omaksi päätason osiokseen, koodiesimerkit poistettu
- Osio 17: Tekninen arkkitehtuuri — koodiesimerkki poistettu
- Saavutettavuusviittaukset yhtenäistetty: komponenteissa mainitaan arvo + viittaus osioon 2

## [1.3.0] – 2026-05-05
### Muutettu
- UX Writing: Tarkennettu virallisuusperiaatetta — kieli ei ole sinuttelevaa
- UX Writing: Virheilmoituksiin lisätty selventävä lause käyttäjäsyyttelyttömyydestä
- Typografia: Fonttiperheisiin lisätty Noto Sans Light (metatiedot)

## [1.2.0] – 2026-04-30
### Lisätty
- Osio 18 (alkuperäisessä rakenteessa, nykyisin osio 15): Sisältölistaukset

## [1.1.0] – 2026-04-30
### Muutettu
- Ministeriövärit laajennettu 5-portaiseen skaalaan
- Grid-maksimileveys päivitetty 1440 px → 1280 px
- Header-rakenne yksinkertaistettu

## [1.0.0] – 2026-04-28
### Lisätty
- Kaikki alkuperäiset osiot (1–17)
```

Tulevat merkinnät noudattavat [Keep a Changelog](https://keepachangelog.com/fi/1.0.0/) -formaattia.

### 20.5 Ministeriökohtaiset poikkeamat

Poikkeamat dokumentoidaan erillisiin ministeriökohtaisiin liitteisiin (`design-[lyhenne].md`), ei tähän yhteiseen dokumenttiin. Jokainen poikkeama edellyttää tilaajan hyväksynnän.

### 20.6 Dokumentin käyttö tekoälyagenttien kanssa

- Dokumentti annetaan agentille kokonaisuudessaan kontekstiksi ennen suunnittelutehtäviä
- Agentin tuottamat ehdotukset tarkistetaan aina ihmisarvioijalla
- Agentin havaitsemia ristiriitoja tai puutteita käsitellään muutosehdotuksina

### 20.7 Liitteet ja viiteaineistot

| Aineisto | Sijainti |
|---|---|
| Valtioneuvoston graafinen ohjeistus | Valtioneuvoston intranet |
| Ministeriöiden graafiset ohjeistukset | [kuvapankki.valtioneuvosto.fi](https://kuvapankki.valtioneuvosto.fi/l/Bkqvhc9HfxMw) |
| Valtioneuvoston väripaletti (.ase) | [kuvapankki.valtioneuvosto.fi](https://kuvapankki.valtioneuvosto.fi/l/TbsHFRtckkqf) |
| Valokuvien tyylikirja | [kuvapankki.valtioneuvosto.fi](https://kuvapankki.valtioneuvosto.fi/l/bncwhWR_f9-s) |
| Noto Sans | [fonts.google.com/noto/specimen/Noto+Sans](https://fonts.google.com/noto/specimen/Noto+Sans) |
| Google Material Symbols | [fonts.google.com/icons](https://fonts.google.com/icons) |
| WCAG 2.1 | [w3.org/TR/WCAG21](https://www.w3.org/TR/WCAG21/) |
| WCAG 2.2 | [w3.org/TR/WCAG22](https://www.w3.org/TR/WCAG22/) |
| WAI-ARIA Authoring Practices | [w3.org/WAI/ARIA/apg](https://www.w3.org/WAI/ARIA/apg/) |
| Vaatimusmäärittely | Projektin dokumentaatiokansio |
| Visuaaliset ilmeet -koonti | Projektin dokumentaatiokansio |
