# DeKa tím — prihlasovacia stránka

Jednostránkový web pre QR kód. Človek oskenuje kód, prejde 6 krátkych otázok
a na konci sa dostane k prihláške (Google formulár).

Celá stránka je jeden súbor: `index.html` (žiadny build, žiadne závislosti).

## 1. Nastav odkaz na formulár

V `index.html` úplne hore v `<script>` sú dve premenné:

```js
const FORM_URL   = "https://forms.gle/VLOZ-SEM-ODKAZ";
const EMBED_FORM = true;
```

- `FORM_URL` — odkaz na váš Google formulár (pýtajte si v ňom **Meno, Vek, E-mail**).
  V Google Forms: **Send → odkaz 🔗 → Copy**.
- `EMBED_FORM` — `true` vloží formulár priamo do stránky, `false` nechá len tlačidlo.
  Pre vloženie do stránky použi dlhý odkaz `https://docs.google.com/forms/d/e/.../viewform`
  (Send → `< >` embed). Krátke `forms.gle/...` odkazy sa vkladať do stránky nedajú —
  s nimi nechaj `EMBED_FORM = false`.

Kým je tam predvolený odkaz, na poslednej obrazovke svieti upozornenie pre správcu.
Po nastavení `FORM_URL` zmizne.

## 2. Uprav otázky (voliteľné)

Otázky sú v poli `STEPS` v `index.html`. Každá otázka má `q` (otázka),
`note` (podtitulok, môže byť `null`), `options` (odpovede) a `reply` — krátku
reakciu, ktorá sa ukáže po kliknutí. `layout: "row2"` / `"row3"` dá odpovede
vedľa seba, bez neho sú pod sebou.

## 3. Zverejni

**GitHub Pages (zadarmo):**

```bash
git add -A && git commit -m "DeKa prihlasovacia stránka" && git push
```

Potom v repozitári: **Settings → Pages → Source: Deploy from a branch → main / (root)**.
Stránka bude na `https://<tvoje-meno>.github.io/deka/`.

**Netlify Drop:** presuň priečinok na https://app.netlify.com/drop — do 10 sekúnd máš odkaz.

## 4. QR kód

Keď máš finálnu adresu, vygeneruj QR (napr. https://qr.io alebo priamo v Chrome:
pravý klik na stránke → *Create QR Code for this page*). Na plagát dávaj QR
veľký aspoň 3 × 3 cm a nad neho napíš, čo sa po oskenovaní stane.

> Tip: adresu radšej nemeň potom, čo QR kódy vytlačíš.

## Testovanie lokálne

```bash
open index.html
```
