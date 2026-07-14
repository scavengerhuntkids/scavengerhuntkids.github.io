# AGENTS.md

Ez a repó a **Scavenger Hunt Kids** nyilvános weboldala (GitHub Pages → `scavengerhuntkids.github.io`).
Minden fájl itt **publikus és élőben kiszolgálódik**.

## ⛔ Kontaktadat — kemény szabály

**A felhasználó privát Gmail címe SOHA nem kerülhet be semmilyen fájlba.**

A brand nyilvános kapcsolattartó címe kizárólag:

```
scavanger.hunt.kids@proton.me
```

Ez érvényes a weboldal minden oldalára, a privacy policyra, az impresszumra, a meta tagekre és a commit-üzenetekre is.

**Kötelező ellenőrzés commit előtt:**

```bash
grep -rni "gmail" . --exclude-dir=.git
```

Ha egy meglévő fájlban benne van, azt **javítani kell**, nem továbbmásolni. A git `user.email` a privát cím — ne emeld át kontaktadatként az oldal tartalmába.

## Az oldal szerkezete

- `/` — főoldal: mi a termék, városlista
- `/<város>/` — ingyenes sétaútvonal + térkép; a fizetős PDF Etsy-linkkel (SEO belépőpont, ez hozza a forgalmat)
- `/privacy-policy/` — adatvédelmi tájékoztató (a Pinterest developer app ezt hivatkozza)
- `/assets/` — közös CSS és webre optimalizált JPEG képek

## Konvenciók

- Minden oldal `<head>`-jébe kell a Pinterest domain-claim tag:
  `<meta name="p:domain_verify" content="43fcb5acb87e953c11ab34fe5e778655"/>`
- Képek: max ~1200px széles, JPEG q82 (a forrás PNG-k a `scavanger_hunt` repóban 0,5–2 MB-osak, azokat NE töltsd fel nyersen).
- A városoldal **nem árulhatja el a rejtvények megfejtését** — az a fizetős PDF tartalma. Az oldal az útvonalat és a „mit keress" tippeket adja ingyen.
- Nincs build lépés: sima statikus HTML + CSS.
