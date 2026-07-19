# 言出法随 · World Model

**Speak the word, and the world follows.** A single-file interactive art piece where Chinese characters dissolve into thousands of particles and reincarnate as living natural phenomena — rain, dragons, ink wash, beating hearts, and the occasional middle finger.

<p>
  <img src="https://img.shields.io/badge/HTML5-Canvas%202D-E34F26?logo=html5&logoColor=white" alt="HTML5 Canvas">
  <img src="https://img.shields.io/badge/JavaScript-Vanilla-F7DF1E?logo=javascript&logoColor=black" alt="Vanilla JS">
  <img src="https://img.shields.io/badge/Web%20Audio-Generative-8A2BE2?logo=audiomack&logoColor=white" alt="Web Audio">
  <img src="https://img.shields.io/badge/dependencies-0-brightgreen" alt="Zero Dependencies">
  <img src="https://img.shields.io/badge/build-none-blue" alt="No Build">
  <img src="https://img.shields.io/badge/architecture-single--file-orange" alt="Single File">
  <img src="https://img.shields.io/badge/lines-2.1k-informational" alt="2.1k Lines">
  <img src="https://img.shields.io/badge/license-MIT-green" alt="MIT License">
  <img src="https://img.shields.io/badge/PRs-welcome-brightgreen" alt="PRs Welcome">
  <img src="https://img.shields.io/badge/status-actively%20maintained-success" alt="Maintained">
</p>

**English** | [简体中文](README.zh-CN.md)

---

## Overview

Type a Chinese character, press Enter — the glyph is sampled into particles on an offscreen canvas, holds its form for a breath, then *becomes* what it means:

- **雨** falls as rain, **龙** soars as a golden dragon with spring-chain physics
- **墨** turns the entire page into xuan paper, ink bleeding with every stroke
- **心** floods the screen in rouge pink with sixteen floating, beating hearts
- **靠**… let's just say it's very expressive

Everything — rendering, physics, typography sampling, generative audio — lives in **one `index.html`**. No dependencies, no bundler, no framework.

## Features

| | |
|---|---|
| **Glyph-to-particle morphing** | Characters are rasterized offscreen and reborn as particle constellations before every manifestation |
| **20+ elemental laws** | Rain, snow, stars, fire, ocean, thunder, wind, flower, moon, cloud, mountain, sunglow, firefly, ink, dragon, heart, dream, and more |
| **Fusion system** | Combine 2–7 laws for named hybrids — 禅 (moon + ink) paints an ink-moon on rice paper |
| **Living backgrounds** | Ink law recolors the whole UI to rice paper; heart law floods everything rouge pink |
| **Physics showcase** | 48-segment verlet spring-chain dragon, lub-dub heartbeat, buoyant dream bubbles |
| **Generative audio** | Per-law ambient soundscapes synthesized live with the Web Audio API |
| **Cinematic camera** | Idle drift, cast punch, rotational kicks, screen shake, and pointer gravity lensing |
| **Easter eggs** | A danmaku-flooding middle-finger law, hidden character mappings, and 万法归尘 |

## The Laws

| 字 | Law | Manifestation | 字 | Law | Manifestation |
|---|---|---|---|---|---|
| 雨 | rain | 细雨润物 | 山 | mountain | 远山如黛 |
| 雪 | snow | 雪落无声 | 霞 | sunglow | 霞光漫天 |
| 星 | stars | 星河璀璨 | 萤 | firefly | 流萤飞舞 |
| 火 | fire | 烈焰焚空 | 墨 | ink | 墨染江山 |
| 花 | flower | 繁花似锦 | 月 | moon | 明月照彻 |
| 风 | wind | 长风万里 | 冰 | ice | 冰雪之境 |
| 海 | ocean | 沧海横流 | 龙 | dragon | 龙游太虚 |
| 雷 | thunder | 雷霆万钧 | 心 | heart | 怦然心动 |
| 云 | cloud | 云卷云舒 | 梦 | dream | 浮生若梦 |

Plus hidden mappings: 春夏秋冬 (seasons), 禅 (zen ink-moon), 酒 / 诗 / 茶, 剑, 凤, 靠, and the terminal law 万法归尘.

## Fusion & Multi-Laws

- Type multiple characters at once, or switch to **融合** mode and pick chips
- 38 named fusions: 焚天烈焰 (fire+wind), 星月交辉 (stars+moon), 禅心墨月 (ink+moon)…
- 3–7 simultaneous laws escalate: 三才同辉 → 四象汇聚 → 五行轮转 → 六合归一 → 七星连珠

## Technical Highlights

```
index.html   ← everything: ~2,100 lines of HTML/CSS/JS
```

- **Trail-fade rendering** — semi-transparent fullscreen overlays produce motion trails; swapping the overlay color turns trails into ink bleed (rice paper) or blush (rouge mode)
- **Composite choreography** — `lighter` for glow on night backgrounds, `source-over` multiply for pigment on paper, switched per law per layer
- **Glyph sampling** — offscreen canvas renders the character at high weight; opaque pixels become seek-targets for the particle swarm
- **Spring-chain dragon** — a Lissajous-driven head drags 48 verlet segments at fixed spacing; spine bristles, antlers and whiskers ride the chain
- **Parametric heart** — the classic heart curve drives both the particle release formation and the lub-dub beating centerpiece
- **Generative audio** — filtered noise, detuned sine pairs, and saw drones layered per law; thunder crackles and star twinkles on timers

## Quick Start

No build step. Ever.

```bash
# open directly
open index.html

# or serve (recommended, for audio autoplay policies)
python3 -m http.server 8817
# → http://localhost:8817
```

## Controls

| Action | Effect |
|---|---|
| Type a character + Enter | Cast a law |
| Click a chip | Cast from the law dock |
| 融合 mode | Multi-select laws to fuse |
| 音 | Toggle ambient audio |
| 留影 | Capture the canvas |
| Move pointer | Gravity-lens the particle field |
| Scroll to top | Return to the overture |

## Documentation

- English — this file
- [简体中文](README.zh-CN.md)

## License

[MIT](LICENSE) © World Model contributors
