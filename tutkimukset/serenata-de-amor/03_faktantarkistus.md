# 03. Faktantarkistus ja lähdeauditointi: Operação Serenata de Amor

> **Toimituksellinen periaate:** Ennen lopullisen synteesin ([`README.md`](README.md)) kirjoittamista jokainen raakaraportin ([`02_raakadata_ja_tutkimus.md`](02_raakadata_ja_tutkimus.md)) keskeinen luku, tekninen väite, säädösviite ja vaikuttavuustieto todennetaan alla olevan lähdehierarkian mukaisesti.  
> **Tarkistuspäivämäärä:** 14.11.2026

---

## 1. Tarkistusmenetelmä

1. **Lähdehierarkia väitetyypeittäin:**
   * **Algoritmit ja arkkitehtuuri:** Vahvistetaan virallisista GitHub-repositorioista (`okfn-brasil/serenata-de-amor`, `rosie`, `jarbas`, `serenata-toolbox`, `whistleblower`) ja vertaisarvioidusta teknisestä kirjallisuudesta.
   * **Rahoitus ja hallintomalli:** Vahvistetaan Catarse-joukkorahoitussivulta sekä Open Knowledge Brasilin (OKBR) virallisista julkaisuista.
   * **Säädöspohja:** Vahvistetaan Brasilian virallisista säädöksistä (*Ato da Mesa nº 43/2009*, *LAI 12.527/2011*, *LGPD 13.709/2018*) ja edustajainhuoneen (*Câmara dos Deputados*) teknisestä dokumentaatiosta.
   * **Vaikuttavuusluvut:** Erotetaan toisistaan *(1) analysoidut kuitit → (2) Rosien liputukset → (3) ihmistarkastetut → (4) viralliset kantelut → (5) palautetut varat*.
2. **Kehäviittaussuoja:** Toissijaisia uutisartikkeleita (esim. EL PAÍS, Wired) ei hyväksytä riippumattomaksi vahvistukseksi koodi- tai euromääräväitteille.
3. **Päätösluokitus:**
   * `VAHVISTETTU` – Todennettu primaarilähteestä ja riippumattomasta vertailulähteestä oikeassa asiayhteydessä.
   * `TÄSMENNETTY` – Luku tai väite pitää paikkansa, mutta sen mittayksikkö, ajankohta tai määritelmä vaati tarkennuksen.
   * `RISTIRIITAINEN` – Lähteiden välillä on materiaalinen ero (esim. yksikkömuutos retrospektiivissa vs. aikalaisraportissa); ristiriita dokumentoidaan avoimesti.
   * `EI TODENNETTAVISSA` – Väitettä ei voida varmentaa avoimista primaarilähteistä; ei esitetä varmana faktana loppuraportissa.

---

## 2. Faktantarkistusmatriisi

| # | Tarkistettava väite / tieto | Mittakohde & ajankohta | Primaarilähde (koodi / viranomainen / raportti) | Riippumaton vertailulähde | Tila | Toimitukselliset huomiot |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Ensimmäinen joukkorahoitus Catarse-alustalla: **R$ 80 424,00** (tavoite R$ 61 280,00 = **131 %**), **1 296 tukijaa** | Kampanja 7.9.–7.11.2016 | `catarse.com.br/serenata` | UFMA-opinnäyte / Wikipedia-viitteistetty Catarse-data | `VAHVISTETTU` | Käytetään tarkkoja lukuja, ei pyöristettyä "noin 80 000". |
| 2 | Hankkeen alkuperäinen käynnistyminen ja siirtyminen OKBR:n alle | Alkuvuosi 2016 (repo), OKBR-ohjelma perustettu 2018 | `okfn-brasil/serenata-de-amor` README & OKBR *Ciência de Dados para Inovação Cívica* | OKBR projektisivu (`ok.org.br/projetos/serenata-de-amor/`) | `TÄSMENNETTY` | OKBR:n sivu merkitsee "2015–Atualmente", mutta repo-historia alkaa alkuvuodesta 2016; tarkkaa juridista luovutuspäivää ei löydy. |
| 3 | Säädöspohja: **Ato da Mesa nº 43/2009** (CEAP) ja **LAI 12.527/2011** (tietopyynnöt) | Voimassa 2009 / 2011 alkaen | `camara.leg.br` & `planalto.gov.br` | Edustajainhuoneen CEAP-avoimen datan opas & akateeminen oikeuskirjallisuus | `VAHVISTETTU` | Mahdollistivat sekä avoimen datan (XML/JSON/CSV vuodesta 2008) että kansalaisten tietopyynnöt (*chamados*). |
| 4 | LGPD (13.709/2018) olisi pakottanut poistamaan CNPJ/CPF-tiedot CEAP-datasta | 2018–2026 | `dadosabertos.camara.leg.br` CEAP-skeema & haku | *Ato da Mesa nº 152/2020* ja CEAP-skeemadokumentaatio | `RISTIRIITAINEN` | Retrospektiivisissa keskusteluissa esitetty väite ei saa tukea: toimittajan `txtCNPJCPF` ja kuitit ovat yhä saatavilla CEAP-rajapinnoissa. |
| 5 | **Rosie** ei ollut yhtenäinen "yleinen tekoäly" tai Isolation Forest -malli, vaan hybridi seulontajärjestelmä | Lähdekoodin keskeiset luokittelijat | `okfn-brasil/serenata-de-amor` (`rosie/README.md`, luokittelijat) | ALAIC / akateeminen koodianalyysi & Irio Musskopfin tekniset kuvaukset | `TÄSMENNETTY` | 5/6 ydinluokittelijasta deterministisiä sääntö-/rekisteritarkistuksia; `MealPriceOutlierClassifier` käytti ohjaamatonta **k-means**-klusterointia (`scikit-learn`). Isolation Forestille ei löydy koodinäyttöä. |
| 6 | **Jarbas**-arkkitehtuuri: Django, Gunicorn, PostgreSQL, Celery, RabbitMQ, Elm | Pääsovelluksen historiallinen pino | `okfn-brasil/jarbas` (`docker-compose.yml`, API-docs) | `serenata.ai` & kehitysdokumentaatio | `VAHVISTETTU` | Haku toteutettu PostgreSQL:n omalla tekstihaulla (ei Elasticsearchilla). Pinottu vanhoihin riippuvuuksiin (Python 3.5, Node 8). |
| 7 | OCR (Google Cloud Vision) rooli tuotannossa | Kuittitekstin käsittely | GitHub-issuet & Jarbas API (`receipt_text`) | `rosie/README.md` | `TÄSMENNETTY` | OCR:ää kokeiltiin ja tekstiä indeksoitiin Jarbasiin, mutta Rosien ydinluokittelijat toimivat rakenteisella CEAP- ja CNPJ-datalla. |
| 8 | Analysoidut ja liputetut korvaukset: **> 3 milj. kuittia**, **> 17 700 epäilyä** (5 v) / aikalaiskuva **8 276 epäilyä, 735 parlamentaarikkoa, R$ 3,6 milj.** | Retrospektiivi (5 v) vs. aikalaisnäkymä | `ok.org.br/projetos/serenata-de-amor/` & `serenata.ai/en/explore/` | Wikipedia / OKBR-lähteet | `TÄSMENNETTY` | Luvut koskevat eri aikajaksoja; *Explore*-sivu on päiväämätön varhaisempi tilannekuva. Erotetaan tiukasti palautetuista rahoista. |
| 9 | Tammikuun 2017 tarkastussprintti (*mutirão*): **629 lähetettyä tapausta**, **216 edustajaa**, **R$ 378 844,05** kyseenalaistettu | Tammikuu 2017 | Projektin aikalaisraportti | Akateeminen jälleenrakennus (587 pyyntöä / 971 kulukorvausta / 849 auditoitua) | `RISTIRIITAINEN` | Yksiköissä on eroja (629 tapausta vs. 587 tietopyyntöä / 971 kuittia); yksi *chamado* saattoi niputtaa useita kuitteja. |
| 10 | Todistetusti palautettu summa: **R$ 50 569,18** | Raportti #015 / OKBR retrospektiivi | Projektiraportti #015 & `ok.org.br` | OKBR-vuosisivu | `RISTIRIITAINEN` | Aikalaisraportti: **134 liittovaltion edustajaa** palautti ateriamenoja. Nykyinen OKBR-sivu: **134 peruutettua korvausta**. Summa sama, yksikkö vaihtunut; edustajainhuoneen erillistä kuittitason koontilistaa ei löydetty. |
| 11 | Yli **80 %** tietopyynnöistä sai vakiovastauksen tai siirrettiin yksittäisen edustajan vastuulle | Jatkoraportointi | Projektin seurantaraportti & oikeustieteellinen analyysi | — | `VAHVISTETTU` | Selittää suppilon kaventumisen: järjestelmässä ei ollut automaattista takaisinperintämekanismia. |
| 12 | `@RosieDaSerenata`-botin rajoittaminen Twitterissä helmikuussa 2019 (`#DesbloqueiaRosie`) | Helmikuu 2019 | Vertaisarvioitu SciELO-tutkimus (2026) | `whistleblower` / `serenata-de-amor` dokumentaatio | `TÄSMENNETTY` | Tapahtuma todennettu akateemisessa lähteessä; tarkkaa Twitterin sisäistä rikkomuspykälää ei ole julkisesti saatavilla. |
| 13 | Nykytila 14.11.2026: erillisrepot arkistoitu 2018, päärepo päivitetty viimeksi 31.1.2024, `serenata-toolbox` 8.1.2020; kehityspaino siirtynyt **Querido Diário** -hankkeeseen | 14.11.2026 | GitHub-metatiedot (`okfn-brasil/*`) & päärepon README | OKBR:n uudempi hankeportfolio | `VAHVISTETTU` | `jarbas.serenata.ai` ja `@RosieDaSerenata` reaaliaikaista pystyssäoloa 14.11.2026 ei voitu todentaa avoimesta status-rajapinnasta. |
| 14 | Väite: *TCU* tai *MPF* olisi virallisesti validoinut Rosien koko epäilyjoukon / vapaaehtoisten uupumus tai X:n 2023 maksullinen API syynä hidastumiseen | 2016–2026 | Avoimet primaari- ja akateemiset lähteet | — | `EI TODENNETTAVISSA` | Rajataan pois varmoina syinä loppuraportista. |

---

## 3. Oikaistut myytit ja yleiset väärinkäsitykset

1. **Myytti: "Tekoälybotti löysi ja palautti miljoonia euroja/realeja korruptiorahoja."**  
   *Totuus:* Rosie seuloi yli 3 miljoonaa korvausta ja liputti > 17 700 epäilyä (varhaisessa vaiheessa R$ 3,6 milj. edestä), mutta ihmisten lähettämistä 629 kantelusta (R$ 378 844,05) dokumentoitu tosiasiallinen palautus oli **R$ 50 569,18**. Kyseessä oli hallinnollinen läpinäkyvyys- ja korjausmekanismi, ei rikostuomioistuin.
2. **Myytti: "Rosie oli syväoppiva / yleinen tekoäly."**  
   *Totuus:* Valtaosa ydintarkistuksista oli deterministisiä sääntöjä (hintakatot, CNPJ-tarkistussummat, yrityksen rekisteritila, mahdottomat matka-ajat). Ainoa hyvin dokumentoitu tilastollinen koneoppimiskomponentti oli ateriahintojen `MealPriceOutlierClassifier` (k-means-klusterointi).
3. **Myytti: "Kaikki liputukset olivat rikoksia."**  
   *Totuus:* Väärät positiiviset kuuluivat seulonnan luonteeseen (ryhmäateriat yhdellä kuitilla, sihteerien kirjausvirheet, vanhentunut CNPJ-data, sallitut takautuvat tilitykset). Siksi järjestelmä rakennettiin ihmistarkastuksen (*mutirões* + Jarbas) ympärille.

---

## 4. Tarkistamattomat / avoimeksi jääneet tiedot

* Edustajainhuoneen oma, kuittitasolla täsmäytetty kokonaispalautustaulukko, joka vahvistaisi R$ 50 569,18 kertymän riippumattomasti projektin omasta raportoinnista.
* `jarbas.serenata.ai`-palvelun ja `@RosieDaSerenata`-tilin tarkka operatiivinen tila päivämäärällä 14.11.2026.
* Tarkka yksittäisten Python-luokittelijoiden tuotantoonottokomitti (pl. Whistleblowerin siirto Jarbasiin kommitissa `37dc9a6`).
* Vapaaehtoisuupumuksen tai X:n vuoden 2023 jälkeisen API-hinnoittelun suora dokumentoitu osuus projektin hidastumiseen.
