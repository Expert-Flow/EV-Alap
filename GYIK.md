# GYIK — Gyakori kérdések és hibaelhárítás

Ha elakadsz, itt keresd a választ először. A kérdések abban a sorrendben vannak, ahogy egy kezdő általában találkozik velük.

---

## Hol tartok? — Az út két lépése

```
1. EV-Alap          →   ez itt: tisztázod ki vagy, kinek, mit adsz el
   (ez a repó)          10 kérdés, 4 fázis, kb. 60-90 perc
        │
        ▼  a kész fájlokat átmásolod
        │
2. EV-AIOS          →   az AI operációs rendszered, ami erre épül
   (külön repó)         /bevezetes, majd hetente /attekintes + /fejlesztes
```

Az EV-Alap egyszeri. A végén kapsz egy fájl-csomagot, amit egy az egyben beolvasol az EV-AIOS-ba.

---

## A leggyakoribb aggodalom

### Még nincs ügyfelem. Akkor van értelme ennek?

Igen — sőt, pont neked szól. Az interjú a „még nincs" válaszokra is épít. Ahol nincs valódi tapasztalatod, ott becslést, tervet vagy feltételezést írj — ez is érték. A feltevés jelölve épp olyan hasznos, mint a tény. Senkit nem szűr ki, hogy kezdő.

### Nincs kész ajánlatom / nem tudom pontosan mit adok el

Ez normális ezen a ponton. Írd le, amit MA gondolsz — akár „még nincs véglegesítve, de ezt tervezem". A skill ebből is dolgozik. Az ajánlat az interjú közben tisztul.

### Mennyire részletes válasz az elég?

Egy-két bekezdés kérdésenként bőven elég. Konkrét legyen, ne tökéletes. Az első kérdés a legnehezebb — ott akár 10 percig is gondolkodhatsz, ez rendben van. A többi gyorsabban megy.

---

## A hangminta (Q7)

### Mi az a „kevert hang"?

Amikor a Claude-dal beszélgetés közben gépelsz be egy szöveget, az nem a te igazi hangod — keveredik az AI-éval. A `references/voice.md` ettől pontatlan lesz. Ezért kérünk **szó szerinti** mintát: egy valódi emailt, posztot, üzenetet, amit korábban te írtál.

### Nincs olyan szövegem, amit korábban írtam. Mit tegyek?

Két út: (1) keress egy régebbi emailt vagy üzenetet a postafiókodban — bármit, ami úgy hangzik, ahogy te beszélsz. (2) Ha tényleg nincs, írj le most egy rövid üzenetet úgy, ahogy egy ügyfélnek írnál — és az lesz a minta. A lényeg: a saját szavaiddal, ne átfogalmazva.

---

## Telepítés és indulás

### Mi az a terminál, és hogyan nyitom meg?

Szövegalapú felület, ahol parancsokkal beszélsz a géppel.
- **Mac:** `Cmd + Space`, írd be: `Terminal`, Enter.
- **Windows:** Start menü, írd be: `Parancssor`, Enter.

### A `claude` parancs „command not found" hibát ad

A Claude Code még nincs telepítve. Telepítsd innen: [claude.com/claude-code](https://claude.com/claude-code), majd zárd be és nyisd újra a terminált.

### A `cd ~/Desktop/EV-Alap` nem találja a mappát

Nézd meg a Finderben/Fájlkezelőben, hova csomagoltad ki, és írd át az útvonalat. Ha a mappa neve más (pl. `EV-Alap-main`), írd azt.

---

## Az eredmény és az átadás

### Mit kapok a végén?

Öt fájlt: `context/en-magam.md`, `icp.md`, `ajanlat.md`, `references/voice.md`, és a `kimenet/ev-aios-atadas.md` átadó-dokumentumot.

### Hogyan viszem át az EV-AIOS-ba?

A `kimenet/ev-aios-atadas.md` lépésről lépésre elmondja: melyik fájlt hova másold az EV-AIOS repóban, és mit futtass utána. Nyisd meg azt a fájlt a végén.

### Használhatom az EV-Alap-ot önállóan, EV-AIOS nélkül?

Igen. A kész `context/` fájlok és a `voice.md` önmagukban is értékes brand-dokumentumok — landing oldalhoz, ügyfél-kommunikációhoz. Az EV-AIOS a folytatás, nem kötelező azonnal.

---

## A landing oldal sablon

### Hogyan töltöm ki a `sablonok/landing-oldal/`-t?

A `sablonok/landing-oldal/deploy.md` tartalmaz egy táblázatot: melyik `{{...}}` helyettesítő honnan jön. A legegyszerűbb: nyisd meg a Claude Code-ban az `index.html`-t és a `context/` fájljaidat, és kérd meg, hogy töltse ki a helyettesítőket a brand-adataidból.

---

## Általános

### Feltölthetem a kitöltött repót GitHubra?

Csak ha **privát**. A kitöltött `alap-intake.md` és a `context/` fájlok a személyes és üzleti adataidat tartalmazzák — publikus repóba ne kerüljenek.

### Még nem találom a választ

Nézd meg a [glosszáriumot](glosszarium.md), vagy írd meg a Claude-nak a problémát a saját szavaiddal.
