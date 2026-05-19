# Landing oldal — élesbe rakás 3 lépésben

Ez egy önálló, statikus HTML+CSS landing oldal sablon. **Nincs build, nincs npm, nincs framework.** Két fájl: `index.html` + `style.css`. Bárhova feltehető.

A sablonban placeholder (helyettesítő) szövegek vannak, kapcsos zárójellel jelölve (pl. `{{HERO_FOSZOVEG}}`). Ezeket kell kitöltened. **Nem kell nulláról oldalt írnod**, csak helyettesítsd ezeket az EV-Alap `context/` fájljaidból.

---

## 1. lépés — Töltsd ki a helyettesítő szövegeket

Az `index.html` fájlban kb. **25 helyettesítő szöveg** van. Mindegyik egyetlen szövegmezőt jelöl.

| Helyettesítő | Honnan jön — mit jelent | Példa |
|---|---|---|
| `{{SAJAT_NEVED}}` | a saját neved (`context/en-magam.md`) | „Kovács Anna" |
| `{{AJANLAT_NEVE}}` | a csomag neve (`context/ajanlat.md`) | „AI-alapú onboarding rendszer" |
| `{{EYEBROW_SZOVEG}}` | a főcím fölötti kis vékony kategória-szöveg (pl. „STRATÉGIAI TANÁCSADÁS") — max 28 karakter | „STRATÉGIAI TANÁCSADÁS" |
| `{{HERO_FOSZOVEG}}` | a legnagyobb, fő ígéret-mondat — egy mondat, 5-12 szó | „90 napon belül működő AI-asszisztens az ügyfeleidnek." |
| `{{HERO_ALSZOVEG}}` | 1-2 mondat a probléma mélységéről (Q5) | „Te tudod a szakmádat, de elfáradtál, hogy minden ügyfél kérdésére éjszaka te válaszolj." |
| `{{CTA_SZOVEG}}` | a fő gomb felirata — rövid cselekvés | „Foglalj 15 perces hívást" |
| `{{BIZONYITEK}}` | bizonyíték a hero alatt (`context/icp.md`) | „Eddig 7 vállalkozónak építettem ilyet." |
| `{{KINEK_1}}`, `{{KINEK_2}}`, `{{KINEK_3}}` | 3 db „mit próbált már" mondat az ICP-ből | „Már próbáltad a [X]-et, de [Y] miatt nem vált be" |
| `{{KARTYA_1_CIM}}` … `{{KARTYA_3_LEIRAS}}` | a csomag 3 darab szállítható eleme (`context/ajanlat.md`) | „1. Workshop", „2. Beüzemelés", „3. Hangolás" |
| `{{EREDMENY}}` | konkrét, mérhető eredmény | „2 hét után az ügyfeleid 70%-a már nem hív telefonon — az AI válaszol." |
| `{{DIFFERENCIATOR_HOSSZU}}` | mi különböztet meg téged (`context/en-magam.md`) | „13 év iparági tapasztalat + AI-szakértelem egy emberben." |
| `{{AR}}` | a csomag ára | „450.000 Ft" |
| `{{AR_JEGYZET}}` | rövid kiegészítés az ár alá | „egyszeri, 4 hetes projekt, ÁFA-mentes" |
| `{{CTA_BEVEZETO}}` | egy mondat a fő gomb fölött a sötét szakaszban | „15 perces hívás, nincs kötelezettség." |
| `{{CTA_JEGYZET}}` | apró biztosíték a gomb alá | „Általában 1 napon belül válaszolok." |
| `{{KAPCSOLAT}}` | a fő gomb hivatkozása — email-link vagy időpontfoglaló cím | `mailto:te@email.hu` vagy `https://cal.com/te/15perc` |
| `{{EMAIL}}` | csak az email-címed (a láblécben jelenik meg) | `te@email.hu` |

**Tipp Claude-dal:** ha megnyitod a kitöltött EV-Alap mappádat a Claude Code-ban, és odaadod neki ezt az `index.html`-t, egyetlen kéréssel kitölti az összes helyettesítőt.

---

## 2. lépés — Nézd meg a böngészőben

Kattints duplán az `index.html` fájlra. Megnyílik a böngészőben. Görgess át rajta, és nézd meg telefon-méretben is.

**Hogyan nézed meg telefon-méretben:** kattints jobbgombbal az oldalon, válaszd a **Vizsgálat** (Inspect) menüpontot. A megnyíló panel tetején kattints a kis telefon-ikonra. Ezzel telefonra szűkül a nézet.

A sablon először mobilra van tervezve. 640 képpontnál vált át asztali nézetre — ez egy átkapcsolási méret, ami alatt a telefonos verzió fut, fölötte a nagyobb.

---

## 3. lépés — Tedd ki a netre (Netlify, fogd és vidd)

A legegyszerűbb módszer kezdő egyéni vállalkozóknak. **Nincs parancssor (terminál), nincs Git, nincs beállítás.** 3 perc:

1. Menj a [app.netlify.com/drop](https://app.netlify.com/drop) címre.
2. A Finderben (Mac) vagy Intézőben (Windows) **kattints egyszer a `landing-oldal` mappára** — kijelölöd, de NEM nyitod meg. Most húzd át a böngészőben megnyitott Netlify Drop területre. Egyetlen mozdulattal — ne a fájlokat egyenként húzd.
3. Várj 30 másodpercet — kapsz egy `valami-12345.netlify.app` címet.

**Az oldal címének átírása értelmesebbre:**
A Netlify vezérlőpultján kattints a saját oldalad nevére. A bal oldali menüben keresd: **Site configuration** (Oldal beállítások), majd **Change site name** (Oldal nevének módosítása). Írj be egy értelmes nevet. Csak kisbetű, szám és kötőjel — ékezetet ne tegyél bele. Mentés.

**Saját domain (pl. `kovacsanna.hu`) ráhúzása:**
A Netlify-on belül: **Domain management**, majd **Add custom domain**. A Netlify ad neked egy `CNAME` rekordot vagy `A` rekordot — ezt a domain-szolgáltatódnál (Nethely, Rackhost, Domain Direct stb.) a DNS-kezelő felületen kell beírnod. Ha nem találod a DNS-kezelőt, hívd a szolgáltató ügyfélszolgálatát — kérd, hogy „egy CNAME rekordot szeretnék beállítani a Netlify-hoz". 10 perces telefonhívás. Pár óra múlva él, és a Netlify automatikusan ad biztonságos kapcsolatot (zöld lakat-ikon a böngészőben — HTTPS).

---

## Ha nem szimpatikus a Netlify

Két másik út, ugyanúgy díjmentes:

- **Cloudflare Pages** — `pages.cloudflare.com`, ugyanúgy fogd-és-vidd, mappát feltöltesz. Európai szerverek, GDPR-barátabb.
- **GitHub Pages** — ha tudsz Git-et: hozz létre egy GitHub repo-t, töltsd fel a 3 fájlt, kapcsold be a Pages-t a Settings-ben. (Kezdőnek nehezebb.)

---

## Mit ne csinálj

- **Ne hagyj benne helyettesítő szöveget** a feltöltés előtt. Mielőtt felteszed: nyomd meg `Ctrl/Cmd + F`-et, keress rá erre: `{{`. Ha 0 találatot mutat, mehet. Ha találatot mutat, ott még helyettesítő szöveg maradt.
- **`{{KAPCSOLAT}}` biztonság:** a `{{KAPCSOLAT}}` helyettesítőbe **csak** `mailto:te@email.hu` vagy `https://` kezdetű hivatkozást írj. Semmiképp ne `javascript:` kezdetű címet — az biztonsági lyuk (XSS).
- **Ne tegyél képet `alt` szöveg nélkül.** Ha logót vagy fotót adsz hozzá: `<img src="logo.png" alt="Kovács Anna logója">`. Dekoratív (csak díszítő) képnél írj üres `alt=""`-t — a látássérültek olvasóprogramja akkor átugorja.
- **macOS-en takarítsd a `.DS_Store` fájlokat.** macOS-en a `.DS_Store` rejtett fájlok bekerülhetnek a mappádba. Mielőtt felteszed Netlify-ra: nyomd meg a `Cmd + Shift + .` billentyűkombinációt (megjelennek a rejtett fájlok), majd kattints jobbgombbal a `.DS_Store` fájlokra, és válaszd az „Áthelyezés a Kukába" lehetőséget.
- **Vercel csak ha tényleg akarod.** A Vercel kicsit több előkészületet igényel kezdőként. A Netlify Drop a leggyorsabb belépő — ha mégis Vercel-t szeretnél, a [vercel.com/new](https://vercel.com/new) is enged feltöltést, csak körülményesebb.
- **Ne kezdj nulláról HTML-t írni.** Ez a sablon az EV-Alap kurzus része — a helyettesítős módszer 4-5x kevesebb energiát igényel, mint az új oldal.

---

## Mit ad ez az oldal

| Szekció | Mit közöl |
|---|---|
| **Hero** | Az egy mondatos ígéret (Q5+Q2 alapján) |
| **Kinek szól** | Az ICP felismeri magát (Q4+Q5 alapján) |
| **Mit kapsz** | 3 szállítható elem (Q2 lebontva) |
| **Eredmény** | Konkrét, mérhető eredmény (Q5 inverz) |
| **Miért én** | Differenciátor (Q3) |
| **Csomag** | Ár + kapacitás (Q9) |
| **CTA** | Konkrét cselekvés (Q10 trigger alapján) |

Egy szabályos egyoldalas szerviz-landing. **Nem értékesítési levél, nem hosszú sales page** — egyetlen ajánlatot, tisztán.

Ha többre van szükséged (visszajelzések, GYIK, blog), másold ezt a sablont és bővítsd. De az első 6 ügyfélig ez bőven elég.
