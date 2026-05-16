# EV-Alap — A Kiindulópontod

> *Hungarian brand-discovery starter kit for Claude Code. Az EV-AIOS előfeltétele: kié vagy, kinek, és hogyan beszélsz — mielőtt az operációs rendszert beindítanád. Készítette a [Solo Business](https://solobusiness.hu).*

Egy ingyenes, MIT-licenszelt sablon. A célja egyetlen kérdés tisztázása:

> **Ki vagy, kinek dolgozol, mit adsz el, és hogyan beszélsz?**

Ha erre a 4 dologra még nincs konkrét, autentikus válaszod, a következő AI-eszközöd, landing oldalad és napi munkamódszered homályos marad. Az EV-Alap repo a `/alap` skillen keresztül 10 kérdést tesz fel 4 fázisban, és a végén egy átemelhető fájl-csomagot ad, amit egy az egyben beolvasol az **EV-AIOS** repo-ba.

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
| `context/en-magam.md` | Identitás, eredet-történet, differenciátor |
| `context/icp.md` | Konkrét ICP-leírás, már próbált megoldások, bizonyíték |
| `context/ajanlat.md` | Csomag(ok), ár, döntési triggerek, nyitott kérdések |
| `references/voice.md` | Verbatim hangminta + megfigyelt jellemzők |
| `kimenet/ev-aios-atadas.md` | **A handoff dokumentum** — mit másolj hová az EV-AIOS-ban |

---

## A 4 fázis, 10 kérdés

```
FÁZIS 1 — TE
  Q1 Eredet-történet
  Q2 Mit csinálsz konkrétan
  Q3 Miért nem más

FÁZIS 2 — AZ ÜGYFELED
  Q4 Konkrét ember
  Q5 A probléma mélysége
  Q6 Bizonyíték

FÁZIS 3 — A HANGOD
  Q7 Verbatim szöveg (2 minta)
  Q8 Kommunikációs helyzet

FÁZIS 4 — AZ AJÁNLATOD
  Q9 A csomag
  Q10 Döntési pillanat
```

**Idő:** 30-45 perc. **Output:** kitöltött `context/`, `references/voice.md`, és a kimenet `ev-aios-atadas.md` handoff.

---

## Quick start

1. **Klónozd** vagy fork-old ezt a repo-t.
2. **Nyisd meg Claude Code-ban**: `cd EV-Alap && claude`
3. **Töltsd ki az `alap-intake.md`-t** (10 kérdés). Vagy futtasd a `/alap`-ot üresen, és interaktívan végigkérdezi.
4. **A `/alap` lefut.** 5 fájl jön létre.
5. **Nyisd meg a `kimenet/ev-aios-atadas.md`-t.** Ez egy explicit checklist.
6. **Klónozd az [EV-AIOS](https://github.com/attilanagy23/EV-AIOS) repot** (ha még nincs).
7. **Másold át a fájlokat** ahogy a `ev-aios-atadas.md` mondja.
8. **Folytasd az EV-AIOS `/bevezetes`-sel.**

---

## Mit NE várj ettől a repo-tól

- **NEM** AI operációs rendszer. Az az EV-AIOS.
- **NEM** generál neked landing oldalt. (Külön sablon: `sablonok/landing-oldal/` — egy kitölthető HTML+CSS sablon.)
- **NEM** ír neked tartalmat, posztot, kampányt.
- **NEM** építi meg a 3Ms-t vagy a 3 pillért — ezek az EV-AIOS-ban élnek.
- **NEM** marketing tanácsadó — a brand discovery a *meglévő anyagok* feltárása, nem új csomagolás.

---

## Repo struktúra

```
EV-Alap/
├── README.md                         ← ez a fájl
├── CLAUDE.md                         ← brand discovery operatori manual (minimális)
├── alap-intake.md                    ← 10 kérdés placeholderekkel
├── LICENSE
├── .gitignore
├── .claude/
│   └── skills/
│       └── alap/SKILL.md             ← a /alap brand discovery skill
├── context/
│   ├── en-magam.md                   ← (template, /alap tölti)
│   ├── icp.md                        ← (template, /alap tölti)
│   └── ajanlat.md                    ← (template, /alap tölti)
├── references/
│   └── voice.md                      ← (template, /alap tölti)
├── kimenet/
│   └── ev-aios-atadas.md             ← (template, /alap tölti — handoff)
└── sablonok/
    └── landing-oldal/                ← külön sablon: HTML+CSS landing oldal
        ├── index.html
        ├── style.css
        └── deploy.md                 ← 3 lépéses Netlify drag & drop útmutató
```

---

## Mihez kapcsolódik

```
EV-Alap (brand discovery)
   ↓
EV-AIOS (AI operációs rendszer)
   ↓
sablonok/landing-oldal/ (statikus landing-deploy)
```

A három repo három különböző problémát old meg — együtt fednek le egy teljes „kezdő egyéni vállalkozó → AI-rendszer-tulajdonos" utat.

---

## Claude előfizetés — mire elég a Pro?

A `/alap` skill **alacsony token-igényű** (1-2 session, többnyire szöveges interjú). A **Claude.ai Pro ($20/hó)** bőven elég hozzá. Nem kell Max csomag, nem kell API access.

---

## Licenc

MIT Licenc. Lásd `LICENSE`.

A módszertan (Q1-Q10 felépítése, voice-szennyeződés warning, „konkrét személy" módszer) a [Solo Business](https://solobusiness.hu) saját pedagógiai kerete. Szabadon használható és adaptálható, attribúcióval.
