# 🎨 Color Trend — Color Wheel Animation

A cinematic 18-second color showcase animation — built with **zero libraries**, just pure HTML, CSS & Canvas API.

---

## 👀 Preview

Here are the two interactive variants I built. Both sync perfectly with video clips, text cards, and background music — timed to the millisecond.

### 1. Template Variant (Classic Orbit)
*The dot orbits around a static color wheel.*
> **[Open `color_wheel_template.html`](./color_wheel_template.html)** to experience it! 👈
> *(Reference: [YouTube url](https://www.youtube.com/results?search_query=color+wheel+trend))*

<div align="center">
  <video src="https://github.com/user-attachments/assets/e616fdf1-cbad-4e5f-8bfc-986e4794a3e0" alt="Color Wheel Animation Preview" width="600">
  <p><i>A cinematic showcase of the "Spinner Variant" built with pure HTML5 Canvas.</i></p>
</div>

---

### 2. Spinner Variant (Cinematic Lock)
*The wheel itself spins while the dot stays fixed at 12 o'clock.*
> **[Open `color_wheel_spinner.html`](./color_wheel_spinner.html)** to experience it! 👈

---

## 🌟 What I Built

Two interactive variants of a color wheel animation that syncs perfectly with video clips, text cards, and background music — all timed to the millisecond.

| Version | How it works |
|---------|-------------|
| `color_wheel_template.html` | Dot orbits around a static wheel |
| `color_wheel_spinner.html` | Wheel itself spins, dot stays fixed |

---

## 🛠️ What I Used

- **HTML5 Canvas** — drew the color wheel + dot from scratch (720 arc segments per frame)
- **`requestAnimationFrame`** — custom 60fps render loop with pause/resume support
- **CSS z-index stacking** — layered videos, overlays, canvas & text perfectly
- **Web Audio API** — background music with smooth fade-out at 18s
- **7× `<video>` elements** — each color gets its own themed clip

---

## 💡 Cool Things I Learned

- **Monotonic angle unwrapping** — to keep the wheel spinning in one direction, I unwrap hue angles past 360° (e.g., orange at 30° becomes 390°) so values never jump backward
- **Canvas renders above CSS overlays** — z-index 12 > z-index 6, so the dot stays visible even when the black overlay is on
- **Browser blocks audio autoplay** — had to build a 3-layer unlock: first frame → click → keydown
- **CSS transition + JS state = flash bug** — a 0.4s opacity transition on clips caused the intro clip to ghost through when the overlay lifted. Fixed by setting `transition: opacity 0s`

---

## 🗂️ File Structure

```
color trend/
├── color_wheel_template.html   ← Dot-orbit variant (main)
├── color_wheel_spinner.html    ← Spinning-wheel variant
├── intro.mp4                   ← 0–7.2s  · B&W portrait
├── blue.mp4                    ← Blue card gap clip
├── pink.mp4                    ← Pink card gap clip
├── orange.mp4                  ← Orange card gap clip
├── yellow.mp4                  ← Yellow card gap clip
├── green.mp4                   ← Green card gap clip
├── white.mp4                   ← White card gap clip
└── Vendredi sur Mer - Écoute chérie.m4a   ← Background audio
```

---

## ⏱️ The 18-Second Timeline

```
ms         Event
────────────────────────────────────────────────────────────
0          BW hold — no wheel visible
200        Wheel pops in at CENTER (full size, instant)
200–3800   Wheel drifts CENTER → RIGHT edge (ease-in-out)
2600       Dot fades in at 4 o'clock (blue hue, 240°)
4000       Intro clip playing — wheel fully right-docked
7200       Hard black cut (50ms)
7400–8200  🎨 "blue / 蓝色的"    — black bg, dot snaps to blue
8200–9200  🌊 Blue clip gap      — blue visual clip
9200–10000 🎨 "Pink / 红色的"   — dot snaps to pink (330°)
10000–11000 🌸 Pink clip gap    — pink drop visual clip
11000–11800 🎨 "orange / 橙子"  — dot snaps to orange (30°)
11800–12800 🌅 Orange clip gap  — wheel slides RIGHT → LEFT
12800–13600 🎨 "yellow / 黄色的"— dot snaps to yellow (57°)
13600–14400 🌻 Yellow clip gap  — yellow paint visual clip
14400–15200 🎨 "green / 绿色的" — dot snaps to green (120°)
15200–16200 🏔️ Green clip gap  — green floating visual clip
16200–17000 🎨 "white / 白色的" — dot snaps to white/cyan (175°)
17000–18000 🏖️ White clip gap  — bright white flow visual + audio fade-out
18000       Animation complete, audio stops
```

---

## 🚀 Run It

1. Drop all `.mp4` + `.m4a` files in the same folder as the HTML
2. Open the HTML files directly in Chrome/Edge
3. Click anywhere if audio doesn't start (browser policy)

---

*Made while learning that browser APIs are way more powerful than I thought 🤯*
#
