# 01. Tutkimussuunnitelma ja Deep Research -prompti: Operação Serenata de Amor (*Rosie & Jarbas*)

**Kohde:** Operação Serenata de Amor (Brasilia)  
**Tavoite:** Tuottaa teknisesti, taloudellisesti ja oikeudellisesti tarkka, primaarilähteisiin perustuva syväanalyysi siitä, miten yksi maailman tunnetuimmista *civic tech* -valvontahankkeista rakennettiin, miten se toimi lähdekoodin tasolla, mihin institutionaalisiin ja juridisiin rajoihin se törmäsi ja mitä sen opeista voidaan soveltaa Suomeen.

---

## 1. Tutkimussuunnitelma ja ydinkysymykset

1. **Tausta, rahoitus, hallintomalli ja säädöspohja:**
   * Miten hanke käynnistyi vuonna 2016 (perustajat, *Data Science Brigade*, joukkorahoitus Catarse-alustalla ja kerätyt varat)?
   * Miten ja miksi hanke siirtyi **Open Knowledge Brasil (OKBR)** -järjestön alle, ja miten jatkorahoitus järjestettiin?
   * Mihin Brasilian säädöksiin hanke nojasi (julkisuuslaki *Lei de Acesso à Informação – LAI 12.527/2011*, edustajainhuoneen kulukorvaussääntö *Ato da Mesa nº 43/2009* sekä myöhempi tietosuojalaki *LGPD 13.709/2018*)?
2. **Tekninen arkkitehtuuri, dataputki ja lähdekoodi:**
   * Mitkä olivat viralliset GitHub-repositoriot (`okfn-brasil` / `datasciencebr`: `serenata-de-amor`, `rosie`, `jarbas`, `serenata-toolbox` jne.), lisenssit, ohjelmointikielet ja riippuvuudet?
   * Miten Brasilian edustajainhuoneen (*Câmara dos Deputados*) CEAP-kulukorvausdata haettiin, siivottiin ja rikastettiin ulkoisilla rekistereillä (esim. *Receita Federal* CNPJ-yritysrekisteri ja paikkatietolähteet), ja mikä oli *Jarbas*-sovelluksen rooli?
3. **Analyysimoottori *Rosie* – lähdekooditason todentaminen:**
   * Mitkä konkreettiset luokittelumoduulit (`classifiers`) *Rosien* lähdekoodissa oikeasti ajettiin?
   * Mikä oli yksinkertaisten **determinististen sääntöjen** (hintakatot, kielletyt kululuokat, epäaktiiviset yritykset, maantieteellisesti mahdottomat siirtymät) suhde **tilastolliseen poikkeamatunnistukseen ja koneoppimiseen**?
   * Miten vapaaehtoisten ihmistarkastus (*mutirões*) kytkeytyi algoritmin liputuksiin ennen julkista esittämistä tai kanteluita?
4. **Vaikuttavuussuppilo, väärät positiiviset ja julkisen nimeämisen riskit:**
   * Miten hankkeen luvut jakautuvat koko ketjussa ilman PR-lukujen ja lopputulosten sekoittumista: *(1) analysoidut kuitit → (2) Rosien liputtamat anomaliat → (3) ihmistarkastetut tapaukset → (4) viralliset kantelut (chamados) → (5) todistetusti valtiolle palautetut varat*?
   * Mistä väärät positiiviset (*false positives*) johtuivat, miksi edustajainhuoneen hallintokäytäntö hylkäsi tai jätti perimättä suuren osan ilmoituksista, ja mitä oikeudellisia tai eettisiä riskejä automaattinen Twitter/X-botti (`@RosieDaSerenata`) aiheutti?
5. **Nykytila (2024–2026) ja elinkaaren opit:**
   * Mikä on repositorioiden, *Jarbasin* ja *Rosie*-botin todennettu tila tänä päivänä (tarkat aikaleimat arkistoinnille tai viimeisille päivityksille)?
   * Miksi aktiivinen kehitys hiipui tai painopiste siirtyi muihin OKBR-hankkeisiin (kuten kuntien virallisia lehtiä louhivaan *Querido Diário* -projektiin)?

### Metodologinen rajaus ja työnjako
Kansainvälistä tapausta tutkittaessa empiirinen tiedonhankinta ja kotimainen sovellettavuusanalyysi pidetään tietoisesti erillään:
* **Vaiheet 1–3 (Brasilian empiria ja faktantarkistus):** Alla oleva Deep Research -prompti on rajattu 100-prosenttisesti Brasilian alkuperäislähteisiin, portugalinkieliseen viranomaisaineistoon ja GitHub-lähdekoodiin. Kielimallia ei pyydetä tekemään tässä vaiheessa pinnallista Suomi-vertailua.
* **Vaihe 4 (Sovellettavuus Suomeen, `README.md`):** Kun Brasilian faktapohja on todennettu vaiheessa [`03_faktantarkistus.md`](03_faktantarkistus.md), sovellettavuus Suomeen (julkisten ostolaskujen ja kuittitason datan ero, julkisuuslaki `621/1999`, tietosuojakehikko sekä `@RosieDaSerenata`-tyyppisen automaattisen julkisen liputuksen kunnianloukkaus- ja yksityiselämän suojariskit Suomessa) laaditaan erillisenä asiantuntijasynteesinä loppuraporttiin.

---

## 2. Deep Research -prompti (kopioi ja aja sellaisenaan)

```markdown
You are conducting an exhaustive, primary-source technical, institutional, and civic-tech investigation on **Operação Serenata de Amor** (including **Rosie**, **Jarbas**, and **serenata-toolbox**) in Brazil.

Your output will undergo strict source-hierarchy verification and be published in an open-methodology investigative data journalism repository in Finland. **Code-level accuracy, primary-source citations, multilingual verification, and zero hype-inflation are mandatory.**

### Strict Methodological & Evidence Rules:

1. **Bilingual Search Requirement (`pt-BR` + `en`):**
   - Do NOT rely solely on English tech media. Actively search and verify sources in **Brazilian Portuguese** alongside English using exact institutional, statutory, and project terminology (e.g., *Cota para o Exercício da Atividade Parlamentar – CEAP*, *Ato da Mesa nº 43/2009*, *Lei de Acesso à Informação – LAI 12.527/2011*, *LGPD 13.709/2018*, *Câmara dos Deputados*, *Tribunal de Contas da União – TCU*, *mutirões*, *chamados*, *Data Science Brigade*, *Open Knowledge Brasil – OKBR*, and Brazilian academic venues such as SBC, SciELO, and university repositories).
2. **Primary-Source & Code-Over-Press Hierarchy:**
   - Prioritize: (a) official GitHub source code, commit histories, and documentation (`okfn-brasil` / `datasciencebr`), (b) Catarse crowdfunding records and OKBR official reports/financial disclosures, (c) Brazilian Chamber of Deputies rules and official responses, and (d) peer-reviewed academic papers.
   - When secondary media articles (e.g., Wired, TechCrunch, blogs) claim "AI" capabilities or impact numbers that differ from the actual Python source code or official reports, **trust the source code and primary records**, and explicitly document the discrepancy.
3. **Anti-Echo Verification:**
   - Do not treat multiple news articles repeating the same interview or press release as independent confirmation. Trace every major figure back to its originating document, repository, or institutional record.
4. **Granular Attribution & "As-Of" Timestamps:**
   - Every numerical claim (funding in BRL, receipts analyzed, anomalies flagged, complaints filed, funds actually refunded, contributors, GitHub metrics) MUST state: (a) the exact unit of measurement, (b) the time period covered or "as-of" verification date, and (c) an inline primary URL.
5. **Explicit Non-Verifiability (Zero Extrapolation):**
   - If any figure (such as total cumulative funds refunded to the treasury or current 2025–2026 live infrastructure status) cannot be verified from open primary sources, write explicitly: **"Not verifiable from open primary sources."** Never estimate, interpolate, or round speculative figures into facts.

---

### Required Report Sections:

#### 1. Origin, Governance, Funding & Statutory Basis
- Exact timeline, founders, initial organizational structure (*Data Science Brigade*), and the 2016 **Catarse** crowdfunding campaign (`catarse.me/serenata`): funding target vs. final raised amount in BRL, number of backers, and initial scope.
- Transition to **Open Knowledge Brasil (OKBR)**: exact timing, reasons for institutionalization, subsequent funding streams (grants, recurring crowdfunding, partnerships), and governance model.
- Legal and regulatory foundation in Brazil: how **LAI (Law No. 12.527/2011)** and **Ato da Mesa nº 43/2009** enabled CEAP auditing and citizen complaints, and whether **LGPD (Law No. 13.709/2018)** or Chamber rules later restricted data granularity (such as CNPJ/CPF fields or receipt images).

#### 2. Target Dataset (CEAP), Data Pipeline & "Jarbas"
- Exact structure of the **CEAP** dataset (*Cota para o Exercício da Atividade Parlamentar*): data formats (XML/CSV dumps, APIs, digitized receipt PDFs/images), key fields (subquotas, net/reimbursed values, issue dates, supplier CNPJ/CPF, parliamentary IDs), and data quality flaws.
- External data enrichment: how records were cross-referenced with **Receita Federal** CNPJ registries (company status, opening date, CNAE activity codes), municipal/state tax invoice portals, or commercial place APIs (Google Places, Foursquare, Yelp). Clarify whether OCR/computer vision was actually used in production or if analysis relied primarily on structured metadata.
- **Jarbas**: exact technical stack (backend, database, search, frontend), user-facing purpose, and how journalists/citizens used it to inspect individual receipts.

#### 3. Inside "Rosie": Code-Level Audit of Classifiers
- List all core GitHub repositories (`serenata-de-amor`, `rosie`, `jarbas`, `serenata-toolbox`, `whistleblower` / bot repos) with exact URLs, primary programming languages, open-source licenses, last commit dates, and current archive/maintenance status.
- Inspect and list the **actual classifier modules implemented in `rosie`** (e.g., meal price outliers, travel speed / simultaneous presence anomalies, irregular/inactive CNPJ companies, monthly subquota limits, election-period/campaign expenses, invalid CNPJ/CPF checksums).
- Categorize each implemented classifier strictly into:
  1. **Deterministic rule-based / statutory threshold checks**, vs.
  2. **Statistical outlier / machine learning models** (specify exact algorithms/libraries used, such as `scikit-learn` Isolation Forest, clustering, linear models, or NLP).
- Explain how Rosie combined individual module outputs into suspicion flags/probabilities and how human verification sprints (*mutirões*) filtered outputs.

#### 4. The Accountability Funnel, `@RosieDaSerenata` & False Positives
- Reconstruct the **documented impact funnel** as a structured table and prose analysis, strictly separating each stage so flagged suspicions are never conflated with recovered public money:
  1. Total receipts / BRL volume ingested and analyzed;
  2. Total receipts / BRL volume flagged as suspicious by Rosie;
  3. Cases manually audited and confirmed by humans (*mutirões* / core team);
  4. Formal complaints (*chamados*) submitted to the Chamber of Deputies via LAI;
  5. Official Chamber responses and **documented BRL actually refunded** to the public treasury.
- Institutional bottleneck analysis: why did the Chamber of Deputies reject, shelve, or decline to enforce refunds on many valid flags (e.g., internal procedural rules requiring deputy voluntary return, administrative thresholds)? What role did **TCU** or **MPF** play, if any?
- Public shaming & the Twitter/X bot (`@RosieDaSerenata`): how automated public tagging of deputies worked, why the tone/design changed over time, what caused **false positives** (shared/group meals, clerical typos in Chamber data, outdated CNPJ records, retroactive reimbursements), and whether the project faced defamation threats, legal pushback, harassment, or political retaliation.

#### 5. Current Status (2024–2026), Maintenance Reality & Legacy
- Verify the current operational status (with explicit "as-of" dates) of the GitHub repositories, the public Jarbas web interface, and `@RosieDaSerenata`.
- Explain the structural reasons behind its slowdown, hibernation, or archival (e.g., volunteer burnout, dependency rot, changes in Chamber open-data APIs, Twitter/X API paywalls, funding constraints) and how lessons from Serenata de Amor shaped OKBR's subsequent flagship project, **Querido Diário**.

#### 6. Categorized Primary Source Bibliography
Provide a numbered bibliography grouped into:
1. **Official Source Code & Technical Documentation** (GitHub repos, READMEs, classifier modules);
2. **Institutional, Statutory & Crowdfunding Records** (Câmara dos Deputados norms, LAI/LGPD references, Catarse page, OKBR official reports);
3. **Peer-Reviewed Academic Studies & Theses** (Brazilian and international academic evaluations of Serenata de Amor);
4. **Audited Secondary Sources** (major developer posts by core founders and media reports, noting where secondary claims diverge from primary records).
```

---

## 3. Tutkimusputken seuraavat vaiheet
1. **Raakatutkimus (`02`):** Aja yllä oleva prompti Deep Research -työkalussa ja tallenna sen tuottama raakaraportti sellaisenaan tiedostoon [`02_raakadata_ja_tutkimus.md`](02_raakadata_ja_tutkimus.md).
2. **Faktantarkistus (`03`):** Tarkista raakaraportin keskeiset luvut, koodiväitteet ja vaikuttavuustiedot lähdehierarkian mukaisesti tiedostoon [`03_faktantarkistus.md`](03_faktantarkistus.md).
3. **Julkinen synteesi ja Suomi-sovellettavuus (`README.md`):** Kokoa todennetuista faktoista lopullinen suomenkielinen tutkimusraportti ja laadi siihen erillinen oikeudellis-tekninen sovellettavuusanalyysi Suomen olosuhteisiin tiedostoon [`README.md`](README.md).
