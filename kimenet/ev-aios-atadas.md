# EV-AIOS Átadás — Mit Másolj Hová

> **Gratulálok, az EV-Alap kész!** Most átlépsz az EV-AIOS-ra. Ez a fájl a térképed — kövesd lépésről lépésre.

> *Ez egy template fájl. A `/alap` skill futtatása után a helyettesítő szövegek (üres helyek a sablonban) helyére az interjú alapján szintetizált tartalom kerül.*
>
> *Ez a fájl a híd az EV-Alap (márka-feltárás) és az EV-AIOS (AI operációs rendszer) között. Az itteni 4 blokkot egy az egyben másolod át az EV-AIOS repo megfelelő helyeire.*

---

## 1. EV-AIOS `ev-intake.md` Q1 — előre kitöltve

Az EV-AIOS Q1 ezt kérdezi: **"Ki vagy, mit adsz el, kinek?"**

Másold be az alábbi szöveget az EV-AIOS `ev-intake.md` Q1 helyettesítő szöveg helyére (a `[A te válaszod]` blokk helyére):

```
[3 bekezdéses szintézis a /alap Q1, Q2, Q4, Q9 alapján:

1. bek — Ki vagyok:
Az eredet-történetből (Q1) és identitásból (Q3) sűrítve. 2-3 mondat.

2. bek — Mit adok el:
Mit kap az ügyfél (Q2) és a csomag (Q9) konkrétan. 2-4 mondat.
Tartalmazza: mit kap az ügyfél fizetés után, körülbelüli ár, formátum.

3. bek — Kinek:
A konkrét persona (Q4) tömörítve. 2-3 mondat.
Tartalmazza: ki ő, milyen életszakaszban, mi a legfontosabb fájdalompontja.]
```

> **A `/alap` skill futtatása után itt egy valódi 3-bekezdéses szöveget látsz, amit egy az egyben másolsz az EV-AIOS-ba. Ha most helyettesítő szöveget látsz, futtasd újra a `/alap`-ot.**

---

## 2. EV-AIOS `ev-intake.md` Q2 — szó szerinti hangminták

Az EV-AIOS Q2 szó szerinti szövegmintákat kér. A Q7-ben már megadtad ezeket — másold át változtatás nélkül.

**Minta 1:**

```
[/alap Q7 első mintája, szerkesztetlenül]
```

**Minta 2:**

```
[/alap Q7 második mintája, szerkesztetlenül]
```

---

## 3. EV-AIOS `context/` mappa előfeltöltése (opcionális, de erősen javasolt)

Az EV-AIOS `/bevezetes` skill önmagában is létrehoz `context/` fájlokat (vallalkozas.md, szemelyes.md, prioritasok.md). De ha az EV-Alap-ban már megcsináltad a márka-feltárást, **gazdagabb kontextust adsz az AIOS-nak**, ha az itteni fájlokat is átemeled.

**Másold át ezeket a fájlokat ugyanazon a néven az EV-AIOS-ba:**

1. `context/en-magam.md` (új fájl lesz)
2. `context/icp.md` (új fájl lesz)
3. `context/ajanlat.md` (új fájl lesz)
4. `references/voice.md` (ha az EV-AIOS-ban még üres template, írd felül — ha már tartalom van benne, először egyezz meg magaddal hogy melyik a maradó)

### A egyszerű út (alapból ezt ajánljuk)

1. **Nyisd meg a Findert.**
2. **Másold ki a fájlokat innen:** `EV-Alap/context/en-magam.md`, `icp.md`, `ajanlat.md` és `EV-Alap/references/voice.md`
3. **Tedd ide:** az EV-AIOS mappa `context/` és `references/` almappáiba.

(Cmd+C, menj át a másik mappába, Cmd+V. A `voice.md`-nél kérdezni fog, hogy felülírja-e — válaszolj IGEN.)

### Az automatikus út (csak ha tudsz parancssort kezelni)

Ha jártas vagy a Terminálban, ezzel egy lépésben átmegy minden fájl:

```bash
cp context/en-magam.md ../EV-AIOS/context/
cp context/icp.md ../EV-AIOS/context/
cp context/ajanlat.md ../EV-AIOS/context/
cp references/voice.md ../EV-AIOS/references/
```

*(Ez feltételezi hogy az EV-AIOS mappa az EV-Alap testvér-mappájában van — pl. mindkettő az Asztalon.)*

Ezek után amikor az EV-AIOS `/bevezetes` skillt futtatod, az látni fogja a már létező fájlokat, és **a konfliktuskezelési szabálya szerint** rákérdez mielőtt bármit felülír.

---

## 4. EV-AIOS következő lépésed — checklist

Amint az 1-2-3 pontokat megcsináltad:

- [ ] `cd EV-AIOS && claude` (vagy nyisd meg VS Code-ban + Claude Code-dal)
- [ ] Töltsd ki az EV-AIOS `ev-intake.md` **Q3-Q7-et** (90 napos prioritások + eszközök) — ezekre a `/alap` nem kérdezett rá, mert ezek operációs információk, nem brand-identitás
- [ ] Futtasd a `/bevezetes`-t
- [ ] A varázsló végigfut, kitölti a `CLAUDE.md`-t, és felhasználja az átemelt anyagokat
- [ ] Egy hét használat után: `/attekintes` (7. nap)
- [ ] Két hét használat után: `/fejlesztes` (14. nap)

---

## Mit NE csinálj

- **Ne futtasd az EV-AIOS `/bevezetes`-t üres `ev-intake.md`-vel**, ha az EV-Alap-ot már elvégezted. Az itteni tartalom a forrás — ott csak a Q3-Q7 maradt nyitva.
- **Ne szerkesztsd át az átemelt szó szerinti hangmintákat.** Ha hibák vannak bennük, az igazi.
- **Ne másold át magát ezt a fájlt** (`ev-aios-atadas.md`) az EV-AIOS-ba — ez csak instrukció, nem context.
- **Ne kombináld a két repo-t egybe.** Az EV-Alap és az EV-AIOS különálló célokat szolgál. Az EV-Alap statikus referencia maradhat — ha a brand-ed változik, ide térsz vissza és újrafuttatod a `/alap`-ot.

---

## Ha valami már megváltozott a brand-eden

A brand-ed nem fix. Ha:
- új ICP-tapasztalat ér (egy ügyfél olyat mondott, amitől megváltozott a kép)
- új ajánlatot teszteltél (és bevált / nem vált be)
- a hangod változott (komolyodott / könnyebb lett)

Térj vissza ide, szerkeszd az `alap-intake.md`-t, és futtasd újra a `/alap`-ot. A frissített `kimenet/ev-aios-atadas.md` újra megmondja mit hová másolj.

---

*Forrás: a `/alap` skill futás kimenete. Kapcsolódó fájlok: `context/en-magam.md`, `context/icp.md`, `context/ajanlat.md`, `references/voice.md`.*
