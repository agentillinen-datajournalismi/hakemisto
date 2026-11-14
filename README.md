# Agentillinen Datajournalismi – Hakemisto

> **Linkkejä agentillisen datajournalismin työkaluihin, toteutuksiin ja tutkimuksiin Suomessa ja kansainvälisesti.**

Tämä hakemisto kokoaa yhteen avoimia työkaluja, MCP-palvelimia (Model Context Protocol), tiedonkeruuskriptejä, tutkimuksia sekä julkisen datan lähteitä tutkivan datajournalismin tueksi.

---

## 1. Periaatteet

1. **Vain viralliset ja todennettavat lähteet:** Työkalujen ja tutkimusten tulee kytkeytyä tarkistettaviin alkuperäisdokumentteihin (diaarinumerot, Y-tunnukset, taulutunnukset, suorat viranomaislinkit).
2. **Ei julkisia henkilörekistereitä (GDPR & Tietosuojalaki 27 §):** Tässä hakemistossa ja sen linkittämissä avoimissa työkaluissa jaetaan *menetelmiä ja koodia* – ei valmiita yksilöityjä henkilötietokantoja.
3. **Puolueettomuus:** Algoritmit käsittelevät kaikkia toimijoita ja päätöksentekijöitä samoilla matemaattisilla säännöillä.

---

## 2. Suomalaiset työkalut & toteutukset

| Työkalu / Hanke | Kuvaus | Tekijä(t) | Linkki |
| :--- | :--- | :--- | :--- |
| *(Lisää oma työkalusi)* | *(Esim. hallituspositioiden ja vallan keskittymisen tutka / "hillotolppahaku")* | *(Tekijän nimi / yritys)* | *(URL / GitHub)* |
| *(Lisää oma työkalusi)* | *(Pöytäkirja-, hankinta- tai ostolaskuskanneri)* | *(Tekijän nimi / yritys)* | *(URL / GitHub)* |

---

## 3. Keskeiset suomalaiset datalähteet & rajapinnat

* **Valtioneuvoston Hankeikkuna:** Säädösvalmisteluhankkeet ja työryhmät ([api.hankeikkuna.fi](https://api.hankeikkuna.fi))
* **Avoimuusrekisteri (VTV):** Eduskuntaan ja ministeriöihin kohdistuva lobbaus ([avoimuusrekisteri.fi](https://avoimuusrekisteri.fi/))
* **Hilma & Hansel:** Julkiset hankinnat, suorahankinnat ja pienhankinnat ([hankintailmoitukset.fi](https://www.hankintailmoitukset.fi/))
* **Tutkihankintoja.fi & Avoindata.fi:** Valtion ja kuntien ostolaskut rivitasolla ([tutkihankintoja.fi](https://www.tutkihankintoja.fi/), [avoindata.fi](https://www.avoindata.fi/))
* **Tutkiavustuksia.fi & Tutkihallintoa.fi:** Valtionavustukset ja julkisen hallinnon taloustiedot ([tutkihallintoa.fi](https://www.tutkihallintoa.fi/))
* **PRH / YTJ:** Yritysten ja yhdistysten perustiedot sekä tilinpäätökset ([avoindata.prh.fi](https://avoindata.prh.fi/))
* **VTV Vaalirahoitusvalvonta:** Ehdokkaiden ja puolueiden rahoitusilmoitukset ([vaalirahoitusvalvonta.fi](https://www.vaalirahoitusvalvonta.fi/))

---

## 4. Avoimet menetelmät & tutkimukset (Open Methodology)

> Tämä hakemisto kokoaa suorat linkit tekijöiden omissa repositorioissa julkaisemiin avoimiin menetelmiin ja esikuvatutkimuksiin.

### A. Menetelmäkuvaukset ja case-analyysit (Case Studies)
* **[Arkistoharavointi ja sukupolvihyppy vieraskielisissä aineistoissa](https://github.com/pnurmela/datajournalismi-tutkimukset/blob/main/menetelmat/case-arkistoharavointi-ja-sukupolvihaku.md)** *(Tekijä: Pekka Nurmela)*:
  * Kuvaus siitä, miten vieraalla kielellä laadittu 60 000 taltion historiallinen valvonta-arkisto (ÁBTL) otetaan haltuun systemaattisella agentillisella haulla.
  * Hyödyntää 1950-luvun yleisimpiä suku- ja etunimiä sekä sukupolvihyppyä vuoden 1920 suomalaisten äitien etunimiin (`anyja_neve`).
  * Sisältää eettisen tiedonkeruun periaatteet, kohinanpoistologiikan sekä avoimet nimisanastot ilman yksilöityjä henkilötietoja (*Zero-PII*).

### B. Kansainväliset esikuvat
* **[Operação Serenata de Amor (*Rosie & Jarbas*)](https://github.com/pnurmela/datajournalismi-tutkimukset/blob/main/tutkimukset/serenata-de-amor/README.md)** *(Tekijä: Pekka Nurmela)*: Brasilialainen avoimen lähdekoodin hybridi poikkeamaseulonta- ja kansalaisvalvontajärjestelmä kansanedustajien kulukorvausten tarkastamiseen *(Osa 1/3: faktantarkistettu tutkimusraportti & sovellettavuus Suomeen)*.
* **[Querido Diário (*Open Knowledge Brasil*)](https://github.com/pnurmela/datajournalismi-tutkimukset/blob/main/tutkimukset/querido-diario/01_suunnitelma_ja_prompt.md)** *(Tekijä: Pekka Nurmela)*: Kuntien virallisten PDF-päätöslehtien automaattinen muuntaminen avoimeksi dataksi *(suunnitelma & prompti valmiina – Osa 2/3)*.
* **[CruzaGrafos, Brasil.IO & Minha Receita (*ABRAJI & OKBR*)](https://github.com/pnurmela/datajournalismi-tutkimukset/blob/main/tutkimukset/cruzagrafos/01_suunnitelma_ja_prompt.md)** *(Tekijä: Pekka Nurmela)*: Poliitikkojen, yritysten, vaalirahoituksen ja julkisten sopimusten verkostograafi *(suunnitelma & prompti valmiina – Osa 3/3)*.

---

## 5. Miten lisään työkalun tai tutkimuksen?

1. Tee **Pull Request** tähän `README.md`-tiedostoon tai avaa **Issue** linkin ja lyhyen kuvauksen kera.
2. Yhteisön matalan kynnyksen keskusteluryhmä toimii kutsulla WhatsAppissa (*Agentillinen Datajournalismi FI*).
