# /alap — Brand Discovery Varázsló (EV-Alap belépési skill)

## Leírás

Ez a skill az EV-Alap repo gerincét képezi. **Az EV-AIOS előtti lépés.** Ha még nem tudod biztosan ki vagy, kinek dolgozol, mit adsz el és hogyan beszélsz — itt kezded.

10 kérdés, 4 fázis, ~30-45 perc. A végén egy átemelhető fájl-csomagot kapsz, amit egy az egyben beolvasol az EV-AIOS repo-ba és onnan tudja kit, mit, kinek, hogyan szolgálsz.

Bármikor újrafuttatható egy szerkesztett `alap-intake.md`-ből.

## Mit csinál

- Beolvassa az `alap-intake.md`-t és ellenőrzi, melyik kérdés (Q1-Q10) van kitöltve
- Hiányzó kérdéseket interjú formájában feltesz a felhasználónak (EGYSZERRE EGY)
- A válaszokat visszamenti az `alap-intake.md`-be
- A teljes intake-ből legenerálja a következő fájlokat:
  - `context/en-magam.md` (Q1+Q2+Q3 alapján)
  - `context/icp.md` (Q4+Q5+Q6 alapján)
  - `context/ajanlat.md` (Q9+Q10 alapján)
  - `references/voice.md` (Q7+Q8 alapján — verbatim hangminta + megfigyelt jellemzők)
  - `kimenet/ev-aios-atadas.md` (handoff dokumentum az EV-AIOS Q1-be való átemeléshez)

## Mit NEM csinál

- **Nem ír landing oldalt.** Az a `/landing-testreszabas` skill (sablonok/landing-oldal/).
- **Nem épít automatizálásokat.** Az az EV-AIOS `/fejlesztes` skill.
- **Nem ad audit-pontszámot.** Tisztán brand discovery setup.
- **Nem ír felül kézzel szerkesztett fájlokat figyelmeztetés nélkül.**
- **Nem generál címkéket vagy slogan-t.** A brand discovery az *anyagok* feltárása, nem a marketing-csomagolás. Az utóbbi az EV-AIOS feladata.

## Fázisok

### 1. fázis — Intake ellenőrzés

Olvasd be az `alap-intake.md`-t. Ellenőrizd, melyik Q1-Q10 kérdés van kitöltve és melyik nem (a `[A te válaszod]` vagy `[Minta 1 — verbatim, nyersen]` placeholder = nincs kitöltve).

Ha minden ki van töltve, ugorj a 3. fázisra.

### 2. fázis — Hiányzó kérdések interjúja (4 fázisos struktúra)

Egyenként kérdezd végig a hiányzó kérdéseket, **a fázis-sorrendet betartva**:

1. Q1, Q2, Q3 (TE)
2. Q4, Q5, Q6 (AZ ÜGYFELED)
3. Q7, Q8 (A HANGOD)
4. Q9, Q10 (AZ AJÁNLATOD)

**Egyszerre EGY kérdés.** Várj válaszra. A választ mentsd vissza az `alap-intake.md`-be (str_replace-szel a placeholder helyére).

**Speciális szabályok:**

#### Q1, Q4 — Konkrétság-ellenőrzés
Ha a felhasználó absztrakt választ ad ("sokaknak segítettem", "30-40 éves nők"), kérdezz vissza:
> "Ez túl általános ahhoz hogy értelmes context legyen. Adj egy **konkrét** példát: egy ember, egy nap, egy helyzet. Lehet kitalált, de részletes."

#### Q3, Q6 — „Még nincs" megengedett
Ha kezdő vagy és nincs bizonyítékod, NE erőltesd hogy találjon ki valamit. Inkább kérd:
> "Írd azt hogy 'még nincs, de ezt fogom csinálni' — és írd le a hipotézist. A kezdő hangja autentikusabb mint a kitalált történet."

#### Q7 — Voice-szennyeződés warning (kötelező strict)
HA a felhasználó NEM illeszt be verbatim szöveget, hanem leírja "mit szokott írni", JELEZD:
> "Ez nem egy verbatim minta — ez egy leírás róla. Kérlek illessz be **tényleges, nyers szöveget**: egy emailt, posztot, üzenetet pontosan abban a formában, ahogy elküldted/megírtad. Ne fogalmazd át, ne tisztázd. A nyers, hibákkal együtt jobb, mint a kitisztított."
>
> "Ha most ülsz a Claude-dal és tőle kérdezed, az NEM hangminta. Másold be egy Messengerből, Gmailből, LinkedIn drafból. Verbatim."

A hangminta autentikus KELL legyen, különben a `references/voice.md` használhatatlan lesz az EV-AIOS-ban.

#### Q10 — Konkrét trigger-keresés
Ha a válasz általános ("amikor segítségre van szüksége"), kérdezz vissza:
> "Konkrét élethelyzetet keresünk. Mi történik aznap reggel az életében, hogy lecsapja a kávét és azt mondja 'na most kell valaki, aki ebben segít'? 1-3 ilyen triggert sorolj fel."

### 3. fázis — Fájlgenerálás

A teljes intake alapján generáld le az alábbi 5 fájlt. **Minden fájl saját section header struktúrát kap, hogy Claude (és az ügyfél) azonnal lássa mit hol talál.**

#### `context/en-magam.md` — Identitás

Q1 + Q2 + Q3 szintézise. Struktúra:

```markdown
# Én magam

## Eredet-történet
[Q1-ből: a konkrét pillanat, ahogy elmondta — szerkesztett, de NEM átfogalmazott formában. A nyers nyelve maradjon.]

## Mit csinálok konkrétan
[Q2-ből: a deliverable. Pontosan mit kap az ügyfél fizetés után.]

## Differenciátor
[Q3-ból: miért engem. Ha „még nincs", írd be a hipotézist explicit jelzéssel: „Hipotézis: még nem validált."]

## Felismert minták
[A Claude megfigyelései a válaszokban — mondatszerkezet, hangsúlyok, ismétlődő témák. 3-5 pont.]
```

#### `context/icp.md` — Ideális Ügyfél

Q4 + Q5 + Q6 szintézise. Struktúra:

```markdown
# Ideális ügyfél

## Konkrét személy
[Q4 válasza, szerkesztetlenül vagy minimálisan szerkesztve. Ez egy persona-vázlat, nem egy lista.]

## Mit próbált már
[Q5 válasza. Lista formában: mit próbált, mi vált be részben, mi nem vált be.]

## Bizonyíték hogy én tudok segíteni
[Q6 válasza. Ha „még nincs", az is OK — explicit jelölve.]

## Beszédmód-implikációk
[A Claude megfigyelése: hogyan beszéljünk ezzel az emberrel? Tegezés? Iparági szakszó? Direkt vagy lágy? 3-5 pont.]
```

#### `context/ajanlat.md` — Ajánlat

Q9 + Q10 szintézise. Struktúra:

```markdown
# Ajánlat

## A csomag(ok)
[Q9 válasza, strukturált formában:
- Mit adok el (a deliverable)
- Mennyi időbe telik
- Mennyibe kerül
- Kapacitás (egyszerre hány ügyfél)]

## Döntési triggerek
[Q10 válaszai. 1-3 konkrét trigger, ami után az ICP keresni kezd.]

## Felmerülő nyitott kérdések
[Amik a Q9-Q10 alapján nyitottak maradtak — pl. "Kapacitás nincs definiálva", "Ár nincs validálva piacon" — Claude ide jegyzi fel hogy később az EV-AIOS `/fejlesztes` skill ezt felvegye.]
```

#### `references/voice.md` — Hangminta

Q7 verbatim mintái + Q8 helyzeti kontextus. Struktúra:

```markdown
# Hangminta

## Verbatim minták

### Minta 1
[Q7 első mintája — VÁLTOZTATÁS NÉLKÜL másold be. Ha helyesírási hiba van benne, az is maradjon. Az autentikusság fontosabb mint a tisztaság.]

### Minta 2
[Q7 második mintája — ugyanúgy verbatim.]

## Kommunikációs kontextus
[Q8 válasza. Hol, mennyire formálisan, mi a különbség baráti vs ügyfél hangok között.]

## Megfigyelt jellemzők

### Regiszter
[formális/informális/vegyes — konkrét megfigyelésekkel]

### Mondatszerkezet
[rövid pattogó / hosszú lélegzetű / kérdéses / állító — példákkal a Q7-ből]

### Visszatérő szavak és kifejezések
[3-7 szó/kifejezés ami többször előfordul]

### Írásjel- és tördelés-szokások
[bekezdés-hossz, gondolatjel-használat, emoji, felkiáltójel, három-pont]

### Tabuk és sajátosságok
[Mit NEM csinálok soha? Pl. "Soha nem használok 'tehát'-ot", "Sose írok emojit"]

## Mit NE csinálj a hangom utánzásakor
[3-5 explicit tiltás, hogy ne legyen hangelszennyeződés:
- Ne tisztítsd ki a hibákat ha kérlek hogy az én hangomon írj.
- Ne használj LinkedIn-bullshit szavakat („leverage", „synergy").
- Ne adj „motivációs" sortöréseket („Egyszerű.\nVilágos.\nKész.") ha a mintákban nincs ilyen.]
```

#### `kimenet/ev-aios-atadas.md` — Handoff az EV-AIOS-hoz

Ez a **legfontosabb fájl**. Ez az átemelhető package amit a felhasználó egy az egyben beolvas az EV-AIOS repo-ba.

Struktúra:

```markdown
# EV-AIOS Átadás — Mit Másolj Hová

Ez a fájl annak a hídja, amit az EV-Alap brand discovery-ben tisztáztál, és amit az EV-AIOS `ev-intake.md` várja.

A 4 fájl alább **másolható** szöveg blokkokba van helyezve. Egy az egyben másold be őket a megadott fájlokba.

---

## 1. EV-AIOS `ev-intake.md` Q1 előre kitöltve

Az EV-AIOS Q1 ezt kérdezi: „Ki vagy, mit adsz el, kinek?"

Ezt másold be az EV-AIOS `ev-intake.md` Q1 placeholder helyére:

```
[Itt egy 3-bekezdéses szöveg jön, Q1+Q2+Q4 alapján:
- 1. bek: Ki vagyok (Q1 alapján, identitás-fókusszal)
- 2. bek: Mit adok el (Q2+Q9 alapján, deliverable+ár)
- 3. bek: Kinek (Q4 alapján, konkrét persona)]
```

---

## 2. EV-AIOS `ev-intake.md` Q2 — hangminták

Az EV-AIOS Q2 verbatim szövegmintákat kér. Másold be a Q7 mintáit ide:

```
[Q7 1. minta verbatim]
```

```
[Q7 2. minta verbatim]
```

---

## 3. EV-AIOS `context/` mappa előfeltöltése (opcionális, javasolt)

Az EV-AIOS `/bevezetes` skill önmagában is létrehoz `context/` fájlokat. De ha akarod, **ezeket az EV-Alap fájlokat átmásolhatod**, így gazdagabb kontextust kap az AIOS:

| EV-Alap fájl | → | EV-AIOS célhely |
|---|---|---|
| `context/en-magam.md` | → | `context/en-magam.md` (új fájl) |
| `context/icp.md` | → | `context/icp.md` (új fájl) |
| `context/ajanlat.md` | → | `context/ajanlat.md` (új fájl) |
| `references/voice.md` | → | `references/voice.md` (felülír, ha még üres template) |

Ezek után amikor az EV-AIOS `/bevezetes` skillt futtatod, az látni fogja a már létező fájlokat, és NEM ír felül semmit — csak kiegészíti a hiányzókat (Q3 prioritások, Q4-Q7 eszközök).

---

## 4. EV-AIOS következő lépésed

Amint az 1-2-3 pontokat megcsináltad:

1. `cd ev-aios && claude`
2. Töltsd ki az EV-AIOS `ev-intake.md` Q3-Q7-et (90 napos prioritások + eszközök)
3. Futtasd a `/bevezetes`-t
4. A varázsló végigfut és kitölti a `CLAUDE.md`-t a már átemelt anyagok alapján
5. Egy hét használat után: `/attekintes`
6. Két hét használat után: `/fejlesztes`

---

## Mit NE csinálj

- Ne futtasd az EV-AIOS `/bevezetes`-t üres `ev-intake.md`-vel, ha az EV-Alap-ot már elvégezted. Az itteni tartalom a forrás — ott csak a Q3-Q7 maradt nyitva.
- Ne szerkesztsd át az átemelt verbatim hangmintákat. Ha hibák vannak bennük, az autentikus.
- Ne másold át a `kimenet/ev-aios-atadas.md`-t magát — ez a fájl csak instrukció, nem context.
```

**Konfliktuskezelés**: Ha valamelyik fájl már létezik az EV-Alap-ban és tartalmaz tartalmat (nem a default placeholder), KÉRDEZZ a felhasználótól:

> "A `[fájlnév]` már tartalmaz adatot. Felülírjam, egybeolvasszam (a régit megtartva, az újat hozzáadva), vagy hagyjam érintetlenül?"

### 4. fázis — Záró összefoglaló

Írd ki:

1. Melyik 5 fájl jött létre / frissült
2. Az `ev-aios-atadas.md` elérési útja teljes egészében
3. Egy explicit checklist a felhasználónak:
   - [ ] Nyisd meg a `kimenet/ev-aios-atadas.md`-t
   - [ ] Klónozd az EV-AIOS repo-t (ha még nincs meg)
   - [ ] Másold be az 1-2-3 blokkok tartalmát a megadott helyekre
   - [ ] Töltsd ki az EV-AIOS Q3-Q7-et
   - [ ] Futtasd az EV-AIOS `/bevezetes`-t
4. Egy mondatos emlékeztető: "Ha bármi változik (új ICP-tapasztalat, új hangminta, új ajánlat), szerkeszd az `alap-intake.md`-t és futtasd újra a `/alap`-ot."

## Kimenet

Egy kitöltött EV-Alap, készen az EV-AIOS-ba való átemelésre. A felhasználó már **nem fog homályosan elindulni** — az AIOS-a egy konkrét identitásra, konkrét ICP-re, konkrét ajánlatra és autentikus hangra fog épülni.
