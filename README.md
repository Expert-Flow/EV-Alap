# EV-Alap — A Kiindulópontod

A magyar egyéni vállalkozók AI-eszközeinek **első, kötelező lépése**: tisztázd ki vagy, kinek dolgozol, és hogyan beszélsz — még mielőtt bármi mást építenél. Készítette a [Solo Business](https://solobusiness.hu).

Egy ingyenes, MIT-licenszelt sablon. A célja egyetlen kérdés tisztázása:

> **Ki vagy, kinek dolgozol, mit adsz el, és hogyan beszélsz?**

Ha erre a 4 dologra még nincs konkrét, igazi válaszod, a következő AI-eszközöd, landing oldalad és napi munkamódszered homályos marad. Az EV-Alap repo a `/alap` skillen keresztül 10 kérdést tesz fel 4 részben, és a végén egy átemelhető fájl-csomagot ad, amit egy az egyben beolvasol az **EV-AIOS** repo-ba.

---

## Mi az a `/alap` skill?

A `/alap` egy parancs, amit a Claude Code chat ablakába írsz be — a `/` jellel az elején. Ez **egy előre megírt beszélgetést** indít: a Claude végigkérdez 10 kérdésen, te válaszolsz, és a végén legyártja neked a brand-anyagaidat.

Nem kell külön weboldalt megnyitnod, nem kell semmit telepítened az `npm`-en kívül a Claude Code-ot magát. Ha még nincs meg, telepítsd innen: [claude.com/claude-code](https://claude.com/claude-code).

---

## Mikor van rá szükséged

Két jelből látszik:

1. **Nem tudod 30 másodperc alatt elmondani egy idegennek mit adsz el és kinek.** (Vagy elmondod, de a hangod alapján te magad sem hiszed.)
2. **Az ügyfeleid lényegében ismeretlenek számodra.** Nem tudod ki ők, mit próbáltak már, mi a döntési pillanatuk.

Ha bármelyik igaz, az EV-AIOS önmagában nem fog megoldódni — itt kezdj.

---

## Mit kapsz

A `/alap` skill futtatása után 5 fájl áll a rendelkezésedre:

| Fájl | Mi van benne |
|---|---|
| `context/en-magam.md` | Identitás, eredet-történet, mitől vagy más |
| `context/icp.md` | Konkrét ICP-leírás (ki az ideális ügyfeled), már próbált megoldások, bizonyíték |
| `context/ajanlat.md` | Csomag(ok), ár, döntési pillanatok, nyitott kérdések |
| `references/voice.md` | Szó szerinti hangminta + megfigyelt jellemzők |
| `kimenet/ev-aios-atadas.md` | **Az átadás-dokumentum** — mit másolj hova az EV-AIOS-ban |

---

## A 4 rész, 10 kérdés

```
1. rész — Te magad
  Q1 Eredet-történet
  Q2 Mit csinálsz konkrétan
  Q3 Miért nem más

2. rész — Az ügyfeled
  Q4 Konkrét ember
  Q5 A probléma mélysége
  Q6 Bizonyíték

3. rész — A hangod
  Q7 Szó szerinti szöveg (2 minta)
  Q8 Kommunikációs helyzet

4. rész — Az ajánlatod
  Q9 A csomag
  Q10 Döntési pillanat
```

**Idő: 60-90 perc.** Az első kérdés a legnehezebb. Ott akár 10 percig is gondolkodhatsz — ez normális. A többi gyorsabban megy. Szétoszthatod 2-3 napra. A válaszaid automatikusan mentődnek a fájlba.

**Eredmény:** kitöltött `context/`, `references/voice.md`, és a kimenet `ev-aios-atadas.md` átadás-dokumentum.

---

## Quick start

1. **Töltsd le a repo-t.** A GitHub-on kattints a zöld **Code** gombra, majd a **Download ZIP** opcióra. Csomagold ki egy mappába (pl. az Asztalra).

2. **Nyisd meg a Terminált.**
   - Mac-en: nyomd `Cmd + Space`, írd be `Terminal`, Enter.
   - Windows-on: keresd a Start menüben a `Parancssor`-t (vagy PowerShell-t).

3. **Lépj be a letöltött mappába.** Ezt írd be:
   ```
   cd Desktop/EV-Alap
   ```
   (Ha máshova csomagoltad ki, írd át az útvonalat.)

4. **Indítsd a Claude Code-ot.** Ezt írd be:
   ```
   claude
   ```

5. **Indítsd a skillt.** A megnyíló chat ablakba írd be:
   ```
   /alap
   ```

6. **Beszélgetsz a Claude-dal kb. 60-90 percig.** 10 kérdés, szétoszthatod 2-3 alkalomra.

7. **A végén** kapsz egy `kimenet/ev-aios-atadas.md` fájlt. Az lesz a térkép, hogyan menj tovább az EV-AIOS-ra.

Másik út: ha jártas vagy a git-tel, le is **másolhatod magadnak (Fork)** a repo-t a GitHub-on a **Fork** gombbal, vagy **letöltheted a saját gépedre (klónozd)** a `git clone https://github.com/Expert-Flow/EV-Alap` paranccsal.

---

## Mit NE várj ettől a repo-tól

- **NEM** AI operációs rendszer. Az az EV-AIOS.
- **NEM** generál neked landing oldalt. (Külön sablon: `sablonok/landing-oldal/` — egy kitölthető HTML+CSS sablon.)
- **NEM** ír neked tartalmat, posztot, kampányt.
- **NEM** építi meg a 3Ms-t vagy a 3 pillért — ezek az EV-AIOS-ban élnek.
- **NEM** marketing tanácsadó — a márka-feltárás (ki vagy, kinek dolgozol — még a marketing előtt) a *meglévő anyagok* feltárása, nem új csomagolás.

---

## Repo struktúra

```
EV-Alap/
├── README.md                         (ez a fájl)
├── CLAUDE.md                         (márka-feltárás operatori manual)
├── alap-intake.md                    (10 kérdés helyettesítő szöveggel)
├── LICENSE
├── .gitignore
├── .claude/
│   └── skills/
│       └── alap/SKILL.md             (a /alap márka-feltárás skill)
├── context/
│   ├── en-magam.md                   (template, /alap tölti)
│   ├── icp.md                        (template, /alap tölti)
│   └── ajanlat.md                    (template, /alap tölti)
├── references/
│   └── voice.md                      (template, /alap tölti)
├── kimenet/
│   └── ev-aios-atadas.md             (template, /alap tölti — átadás)
└── sablonok/
    └── landing-oldal/                (külön sablon: HTML+CSS landing oldal)
        ├── index.html
        ├── style.css
        └── deploy.md                 (3 lépéses Netlify drag & drop útmutató)
```

---

## Mihez kapcsolódik

Az EV-Alap a márka-feltárás. Ha ez kész, jön az **EV-AIOS** (AI operációs rendszer), majd a **sablonok/landing-oldal/** (statikus landing-oldal). A három repo három különböző problémát old meg — együtt fednek le egy teljes „kezdő egyéni vállalkozó, aki AI-rendszer-tulajdonossá válik" utat.

---

## Claude előfizetés — mire elég a Pro?

A `/alap` skill **alacsony token-igényű** (1-2 session, többnyire szöveges interjú). A **Claude.ai Pro ($20/hó)** bőven elég hozzá. Nem kell Max csomag, nem kell API access.

---

## Licenc

MIT Licenc. Lásd `LICENSE`.

A módszertan (Q1-Q10 felépítése, kevert hang figyelmeztetés, „konkrét személy" módszer) a [Solo Business](https://solobusiness.hu) saját pedagógiai kerete. Szabadon használható és adaptálható, attribúcióval.

<!-- english summary: Hungarian brand-discovery starter kit for Claude Code. Prerequisite to EV-AIOS — clarify who you are, who you serve, and how you talk before booting up the operating system. Built by Solo Business. -->
