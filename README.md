# 🎡 Spin The Gay Wheel

A fun, minimalist, single-page spin-the-wheel game. Add your friends' names, spin the colorful wheel, and watch the entire page transform into a pink & girlish celebration for the lucky winner!

Built with **vanilla HTML, Tailwind CSS (CDN), and JavaScript** — no build tools, no frameworks, no dependencies to install.

---

## ✨ Features

- **Add / Remove Participants** — type a name and press Enter/click Add, or use the quick-add buttons. Remove individual names with ✕, or clear everything.
- **Colorful Spinning Wheel** — drawn on a canvas with smooth easing animation (6 full rotations + random accurate result every time).
- **Pink Gay Theme Takeover** — as soon as a winner is announced:
  - Whole page background turns pink (#fff0f6)
  - All panels, buttons, inputs, badges switch to pink palette
  - 50 heart/sparkle/rainbow emojis float up from the bottom
  - 30 sparkle emojis twinkle all over the screen
  - Winner name wiggles with rainbow 🏳️‍🌈 trophy
- **One Click Reset** — ↩️ Reset Theme button returns everything to minimal light mode instantly.
- **Responsive** — wheel auto-fits on mobile.
- **SEO Ready** — full meta tags, Open Graph + Twitter cards, JSON-LD, inline SVG favicon.
- **No Server Needed** — just open `index.html` in any modern browser.

---

## 🚀 How to Run

1. Clone or download this folder.
2. Double-click **`index.html`** to open it in your browser.
3. Done! 🎉

> If you want to serve over HTTP (e.g. for mobile testing on LAN), you can use any static server.

---

## 🎮 How to Play

1. **Add names** — either type into the input box (Enter to add) or click the preset chips (Rahul, Aman, Vikram, Sahil, Rohan, Karan).
2. **Add at least 2 names** — the wheel requires a minimum of 2 participants.
3. **Hit SPIN 🎯** in the center of the wheel.
4. **Wait for the result** — the wheel slows down and lands on the winner.
5. **Enjoy the gay theme!** 💕 The whole page turns pink, hearts float, sparkles sparkle.
6. **↩️ Reset Theme** to go back to minimal light mode and spin again.

---

## 📁 Project Structure

```
FindTheGay/
├── index.html     # Single-file app (HTML + Tailwind via CDN + inline JS)
└── README.md      # This file
```

Everything — structure, styles, logic, favicon, meta tags, structured data — lives inside the single `index.html` file for maximum portability.

---

## 🛠️ Technical Stack

| Layer | Tech |
|---|---|
| Markup | HTML5 (semantic) |
| Styles | Tailwind CSS 3 via `<script>` CDN + small inline `<style>` block |
| Logic | Vanilla JavaScript (ES2020) — no frameworks, no libraries |
| Wheel Rendering | HTML5 `<canvas>` 2D context |
| Animations | CSS `@keyframes` + `requestAnimationFrame` for spin |
| Icons / Emojis | Native Unicode emojis (rendered by OS/browser fonts) |
| Favicon | Inline SVG (no extra file) |
| OG / Twitter Image | Remote text-to-image URL (auto-generated preview) |

---

## 🎨 Theme Breakdown

### Light (Default)
- Page: `#fafafa` (soft white)
- Accent: Indigo `#6366f1`
- Panels: White `bg-white` + 1px `slate-200` border
- Canvas wheel: Indigo outer ring with 12-color segments

### Gay (After Win)
- Page: `#fff0f6` (pink-50)
- Accent: Gay pink `#ec2c69`
- Panels: White + 2px pink-200 border
- Canvas wheel: Pink outer ring with 12-tone pink/purple pastel segments

---

## 🧠 Spin Logic (Accurate & Fair)

Winner is selected **before** animation starts via `Math.floor(Math.random() * names.length)`. The final wheel rotation is then calculated so the exact winning segment lands precisely under the fixed red pointer at the top — no cheating, no guesswork, always visually accurate.

```
segAngle      = 2π / N
winnerMid     = winnerIndex * segAngle + segAngle/2
targetAngle   = -π/2  -  winnerMid        (so midpoint points up)
finalAngle    = current + 6*2π + delta    (6 full spins + offset to winner)
Easing        = easeOutCubic over 5.2 s
```

---

## 🔍 SEO / Meta Tags Included

Inside `<head>` of [index.html](file:///c:/Users/Sahil%20Jangra/Desktop/DeskTop/yt%20portfolios/FindTheGay/index.html):

- ✅ `<title>`, description, 15+ keywords, author, robots, language, rating, distribution, theme-color, canonical
- ✅ Open Graph: og:type/url/title/description/**og:image** (1200×630), image width/height/alt, site_name, locale
- ✅ Twitter: summary_large_image full card
- ✅ JSON-LD: Schema.org `WebApplication` with offers (free), aggregateRating, keywords
- ✅ 3 favicon links: `icon`, `shortcut icon`, `apple-touch-icon` — all inline SVG (pink wheel + heart design)

---

## 🛡️ Notes on Behavior

- Duplicate names are automatically rejected with a brief red ring flash.
- `< 2` names triggers a red-bordered warning instead of spinning.
- Clear All shows a native `confirm()` dialog to prevent accidental wipe.
- Winner display still renders emojis (🏳️‍🌈 💅 ✨) even in the result block — all gradient text effects were *intentionally removed* in v2 to guarantee emoji visibility without needing selection.

---

## 📜 License

Do whatever you want with it. Made for fun, not for profit. 🐸☕

---

**Made with 💜 & lots of chaos**
