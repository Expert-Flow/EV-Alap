# Landing oldal — telepítés 3 lépésben

Ez egy önálló, statikus HTML+CSS landing oldal sablon. **Nincs build, nincs npm, nincs framework.** Két fájl: `index.html` + `style.css`. Bárhova feltehető.

A sablonban placeholder tokenek vannak (`{{KAPCSOSZÖVEG}}` formában) — ezeket kell kitöltened. **NEM kell scratchről írnod oldalt**, csak helyettesítsd a placeholdereket az EV-Alap `context/` fájljaiból.

---

## 1. lépés — Töltsd ki a placeholdereket

A `index.html` fájlban kb. **25 placeholder token** van. Mindegyik egyetlen szövegmezőt jelöl. Helyettesítsd őket az EV-Alap `context/` fájljaidból kinyert tartalommal.

| Token | Honnan jön | Példa |
|---|---|---|
| `{{SAJAT_NEVED}}` | `context/en-magam.md` identitás | „Kovács Anna" |
| `{{AJANLAT_NEVE}}` | `context/ajanlat.md` csomag-név | „AI-alapú onboarding rendszer" |
| `{{EYEBROW_SZOVEG}}` | rövid kategória-cimke | „STRATÉGIAI TANÁCSADÁS" |
| `{{HERO_FOSZOVEG}}` | egy mondatos ígéret | „90 napon belül működő AI-asszisztens az ügyfeleidnek." |
| `{{HERO_ALSZOVEG}}` | 1-2 mondat a Q5 (probléma mélysége) alapján | „Te tudod a szakmádat, de már elfáradtál abban hogy minden ügyfél kérdésére te magad válaszolj éjszaka. Ez ezt oldja meg." |
| `{{CTA_SZOVEG}}` | gomb felirat | „Foglalj 15 perces hívást" |
| `{{BIZONYITEK}}` | `context/icp.md` bizonyíték | „Eddig 7 vállalkozónak építettem ilyet — 5 visszajelzés a referenciákban." VAGY „Korai indulás, az első 3 ügyfél kedvezményes árat kap." |
| `{{KINEK_1}}, {{KINEK_2}}, {{KINEK_3}}` | `context/icp.md` „mit próbált már" | „Már próbáltad a [X]-et, de [Y] miatt nem vált be" |
| `{{KARTYA_1_CIM}}` … `{{KARTYA_3_LEIRAS}}` | `context/ajanlat.md` deliverable lebontva 3 részre | pl. „1. Workshop", „2. Beüzemelés", „3. Hangolás" |
| `{{EREDMENY}}` | konkrét, mérhető eredmény | „2 hét után az ügyfeleid 70%-a már nem hív telefonon kérdezni — az AI válaszol nekik." |
| `{{DIFFERENCIATOR_HOSSZU}}` | `context/en-magam.md` differenciátor | „13 év [iparág]-tapasztalat + AI-szakértelem egy emberben. Nem egy ügynökség 5 fős csapata." |
| `{{AR}}` | `context/ajanlat.md` ár | „450.000 Ft" |
| `{{AR_JEGYZET}}` | rövid magyarázat | „egyszeri, 4 hetes projekt, ÁFA-mentes" |
| `{{CTA_BEVEZETO}}` | egy mondat a CTA szakaszban | „15 perces hívás, nincs kötelezettség. Ha nem passzol, mondd ki — szólj egy ismerősnek aki igen." |
| `{{CTA_JEGYZET}}` | apró biztosíték | „Általában 1 napon belül válaszolok." |
| `{{KAPCSOLAT}}` | email link vagy booking URL | `mailto:te@email.hu` vagy `https://cal.com/te/15perc` |
| `{{EMAIL}}` | csak az email | `te@email.hu` |

**Tipp Claude-dal:** ha az EV-Alap repo-dból (kitöltött `context/` fájlokkal) megnyitod a Claude Code-ot és odaadod neki ezt a `index.html`-t, **egy promptban** kitölti a placeholdereket. Erre a `BOVITESEK.md` (EV-AIOS) jövőbeli `/landing-testreszabas` skillje optimalizált — addig manuálisan is megy.

---

## 2. lépés — Nézd meg a böngészőben

A `index.html`-t kattintsd duplán. Megnyílik a böngészőben. Görgess át, **mobil nézetben is** (DevTools → eszköz-toolbar → iPhone). Ha valami furcsa, javítsd a CSS-ben.

A sablon **mobil-first** módon van megírva, 640px az alapvető megtörés-pont.

---

## 3. lépés — Tedd ki Netlify-ra (drag & drop)

A legegyszerűbb deploy módszer kezdő egyéni vállalkozóknak. **Nincs CLI, nincs Git, nincs config.** 3 perc:

1. Menj a [app.netlify.com/drop](https://app.netlify.com/drop) oldalra
2. Húzd rá a teljes `landing-oldal/` mappát a böngészőablakra
3. Vársz 30 másodpercet → kapsz egy `nev-tetszoleges-12345.netlify.app` URL-t

**Ennek a domainnek a megváltoztatása:**
- Bejelentkezés után: Site settings → Change site name → adj egy értelmes nevet pl. `kovacs-anna-onboarding.netlify.app`

**Saját domain (pl. `kovacsanna.hu`) ráhúzása:** Netlify → Domain management → Add custom domain → kövesd az utasításokat. Általában az ingyenes Netlify HTTPS-tanúsítvánnyal együtt 10 percen belül él.

---

## Mit ne csinálj

- **Ne hagyj benne placeholdert** a deploy előtt. Egy `{{...}}` token a végleges oldalon szakmaiatlannak látszik. Tipp: nyomd `Ctrl/Cmd + F` és keress rá: `{{` — ha bármelyik felugrik, az még kitöltetlen.
- **Ne tedd be a Vercel-re** ha még nincs Git-tudásod. A Netlify drag-and-drop kifejezetten Git nélkül is működik. Vercel CLI-t igényelhet.
- **Ne kezdj scratchről írni HTML-t.** Ez a sablon **az EV-Alap kurzus része** — Claude azért nem ír neked nulláról oldalt mert az 4-5x annyi tokenba kerülne. A sablon helyettesítés módszere a token-takarékos.

---

## Mit ad ez az oldal

| Szekció | Mit közöl |
|---|---|
| **Hero** | Az egy mondatos ígéret (Q5+Q2 alapján) |
| **Kinek szól** | Az ICP felismeri magát (Q4+Q5 alapján) |
| **Mit kapsz** | 3 deliverable-kártya (Q2 lebontva) |
| **Eredmény** | Konkrét, mérhető outcome (Q5 inverz) |
| **Miért én** | Differenciátor (Q3) |
| **Csomag** | Ár + kapacitás (Q9) |
| **CTA** | Konkrét cselekvés (Q10 trigger alapján) |

Egy szabályos „one-pager" szerviz-landing. **Nem értékesítési levél, nem long-form sales page** — egyetlen ajánlatot, tisztán.

Ha többre van szükséged (visszajelzések, GYIK, blog), másold ezt a sablont és bővítsd. De az első 6 ügyfélig ez bőven elég.
