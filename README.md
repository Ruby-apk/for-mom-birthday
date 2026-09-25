# 🎉 Happy Birthday to an Amazing Mother — Website

A warm, colorful, single-page birthday website for your friend's Mom, celebrating
**27 September 2026**. It works offline, can be installed to a phone home screen,
and is packed with little interactive surprises.

Live preview: https://sites.super.myninja.ai/60a4d474-e047-4435-bc2f-24186be8129c/38770d5e/index.html

---

## ✨ What's inside

- **Live countdown** to 27 Sept 2026 that automatically flips into a "birthday mode"
  celebration (count-up + confetti + lanterns) once the day arrives.
- **Envelope letter** — a heartfelt message that opens in a modal.
- **Three wish cards** and **three floating "notes" orbs**, each revealing a note.
- **Cake with candles** — tap/blow to snuff the candles and reveal a wish.
- **Scratch-off secret** — swipe to uncover a hidden message.
- **Voice note** — a short "Happy Birthday" melody you can play.
- **Background music** toggle (generated with the Web Audio API).
- **Confetti & floating lanterns**, scroll-reveal animations, and a keepsake list.
- **Share** button (Web Share API / WhatsApp) and **install-to-home-screen** prompt.
- **Offline support** via a service worker (PWA).

---

## 📸 How to swap her photos (very important)

The site uses these images — replace any of them (keep the **same filenames**) to update:

| File | Used for | Best size / shape |
|------|----------|-------------------|
| `photos/mom-1.jpg` | Hero portrait — **first** photo in the auto-rotating slideshow | Portrait (e.g. 1000 × 1500 px) |
| `photos/mom-2.jpg` | Hero portrait — **second** photo in the slideshow (rotates with the first) | Portrait (e.g. 1000 × 1500 px) |
| `photos/letter.jpg` | The photo inside the letter for Mom | Portrait / square |
| `photos/flowers.jpg` | The floral still-life in the "Words from the heart" (children's messages) section | Portrait (e.g. 1000 × 1500 px) |

Steps:
1. Rename your photo to the matching filename above.
2. Drop it into the `photos/` folder, overwriting the current one.
3. Re-deploy / refresh — done!

> Tip: Keep files under ~500 KB each for fast loading. Any JPG works.
> The hero slideshow automatically cross-fades between `mom-1.jpg` and `mom-2.jpg` every few seconds.

---

## 🎂 Other things you can personalize

Open **`script.js`** and edit the `CONFIG` block at the very top:

```js
var CONFIG = {
  name: 'Mom',                                  // her name / nickname
  birthday: new Date(2026, 8, 27, 0, 0, 0, 0),  // 27 Sept 2026 (month is 0-indexed: 8 = September)
  whatsapp: '2347078456163',                    // number for the WhatsApp wish button
  waIntro: 'Hi! I just saw the birthday site for Mom — it\'s beautiful. Here\'s my message for her: '
};
```

- **Change the name** → update `name`.
- **Change the date** → update the `Date(...)` (year, month−1, day).
- **Change the WhatsApp number** → update `whatsapp` (country code + number, no `+`).

To edit the **written words** (hero line, wishes, letter, notes, thank-you),
open **`index.html`** and look for the section comments like
`<!-- WISHES -->`, `<!-- LETTER -->`, `<!-- NOTES -->`, `<!-- THANKS -->`.

---

## 🚀 How to publish / host it

It's a plain static site — no build step. Any static host works:

- **Netlify / Vercel:** drag the `site/` folder onto their dashboard.
- **GitHub Pages:** push the `site/` folder to a repo and enable Pages.
- **Any web host:** upload the folder contents as-is.

The service worker (`sw.js`) and `manifest.webmanifest` must be served over
**HTTPS** for the install/offline features to work (they already do on the live URL).

---

## 📁 File overview

```
site/
├─ index.html            ← all page content & text
├─ styles.css            ← the warm burgundy / rose / gold design
├─ script.js             ← countdown, modals, candles, scratch, music, PWA (edit CONFIG here)
├─ sw.js                 ← offline service worker
├─ manifest.webmanifest  ← app name / icons / theme
├─ voice-note.mp3        ← the birthday melody
├─ photos/
│   ├─ mom-1.jpg         ← ⭐ hero slideshow photo 1
│   ├─ mom-2.jpg         ← ⭐ hero slideshow photo 2 (auto-rotates with photo 1)
│   ├─ letter.jpg        ← ⭐ photo inside the letter
│   └─ flowers.jpg       ← floral still-life (Save-the-date section)
└─ icons/                ← app icons (favicon, home-screen)
```

---

Made with love. 💛
