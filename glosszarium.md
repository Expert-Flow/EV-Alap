# Glosszárium

Rövid magyarázat minden fogalomhoz, ami a sablonban előfordul. Ha egy szót nem értesz, itt keresd.

---

## A rendszer

**EV-Alap** — ez a sablon. Egy 10 kérdéses, 4 fázisos brand-discovery interjú: tisztázza, ki vagy, kinek dolgozol, hogyan beszélsz, mit adsz el.

**EV-AIOS** — a folytatás. Az EV-Alap tiszta alapjára épít egy működő AI operációs rendszert. Külön repó.

**brand-tisztaság** — amikor egy mondatban, magabiztosan meg tudod mondani, ki vagy, kinek dolgozol és mit adsz el. Az EV-Alap célja ennek elérése.

**skill** — egy konkrét, vezetett munkafolyamat a Claude Code-ban. Perjellel hívod: `/alap`.

**fázis** — az interjú négy szakasza: TE, ÜGYFÉL, HANG, AJÁNLAT.

---

## Technikai fogalmak

**terminál** — szövegalapú felület, ahol parancsokkal beszélsz a géppel.

**repó** (repository) — egy projekt-mappa, általában GitHubon tárolva.

**klónozás** — egy GitHub-repó letöltése a saját gépedre.

**Claude Code** — a parancssori AI-eszköz, amiben a sablon fut.

**helyettesítő** (placeholder) — a `{{...}}` jelölés a landing sablonban. A saját szövegedet írod a helyére.

**landing oldal** — egyetlen, fókuszált weboldal, ami egy ajánlatot mutat be.

**deploy** — egy kész oldal kitétele az internetre, hogy bárki elérje.

---

## Az interjú fogalmai

**ICP** — ideális ügyfél-profil: a konkrét személy, akinek dolgozol. Nem demográfia, hanem egy felismerhető ember egy konkrét helyzetben.

**eredet-történet** — egy konkrét pillanat, amikor segítettél valakinek abban, amit most el akarsz adni. Ebből derül ki, hogy a szakmád igazi.

**szó szerinti minta** (verbatim) — egy valódi szöveg, amit te írtál (email, poszt, üzenet), átfogalmazás nélkül. Ebből tanulja meg a rendszer a hangodat.

**kevert hang** — amikor AI-jal beszélgetés közben gépelt szöveget adsz mintának. Ez pontatlan, mert keveredik az AI hangjával — kerüld.

**döntési pillanat** — az a konkrét élethelyzet, ami után az ügyfél azt mondja: „most kell valaki, aki ebben segít".

**differenciátor** — ami megkülönböztet a versenytársaktól. Miért téged válasszanak, és ne mást.

---

## A kimenet

**context/** — a mappa, ahova a rólad és a vállalkozásodról szóló kész fájlok kerülnek: `en-magam.md`, `icp.md`, `ajanlat.md`.

**voice.md** — a `references/` mappában: a megfigyelt hangod és a szó szerinti mintáid.

**átadó-dokumentum** — a `kimenet/ev-aios-atadas.md`: lépésről lépésre elmondja, hogyan viszed át a kész fájlokat az EV-AIOS-ba.
