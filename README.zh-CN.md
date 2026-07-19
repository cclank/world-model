# 言出法随 · 世界模型

**一字既出，世界重构。** 单文件交互艺术作品：输入一个汉字，它便化作万千粒子，而后涅槃为其所指的天地现象——雨落、龙游、墨染、心动，偶尔也竖个中指。

<p>
  <img src="https://img.shields.io/badge/HTML5-Canvas%202D-E34F26?logo=html5&logoColor=white" alt="HTML5 Canvas">
  <img src="https://img.shields.io/badge/JavaScript-原生-F7DF1E?logo=javascript&logoColor=black" alt="原生 JS">
  <img src="https://img.shields.io/badge/Web%20Audio-生成式-8A2BE2?logo=audiomack&logoColor=white" alt="Web Audio">
  <img src="https://img.shields.io/badge/依赖-0-brightgreen" alt="零依赖">
  <img src="https://img.shields.io/badge/构建-无-blue" alt="零构建">
  <img src="https://img.shields.io/badge/架构-单文件-orange" alt="单文件">
  <img src="https://img.shields.io/badge/行数-2.1k-informational" alt="2.1k 行">
  <img src="https://img.shields.io/badge/许可-MIT-green" alt="MIT 许可">
  <img src="https://img.shields.io/badge/PRs-欢迎-brightgreen" alt="欢迎 PR">
  <img src="https://img.shields.io/badge/状态-积极维护-success" alt="积极维护">
</p>

[English](README.md) | **简体中文**

---

## 概览

输入一个汉字，回车——字形先在离屏画布上被采样为粒子，凝聚成形，屏息一瞬，而后**化作它所指之物**：

- **雨** 落成细雨，**龙** 以弹簧链物理游于太虚
- **墨** 令整个页面化作宣纸，每一笔拖尾都是墨韵
- **心** 将满屏染作胭脂粉，十六颗心各自搏动
- **靠**……情绪非常饱满

渲染、物理、字形采样、生成式音频——**全部栖身于一个 `index.html`**。零依赖、零打包、零框架。

## 特性

| | |
|---|---|
| **字形粒子化** | 每次施法，汉字先在离屏画布光栅化，化作粒子星座，再演化为现象 |
| **二十余道法则** | 雨、雪、星、火、海、雷、风、花、月、云、山、霞、萤、墨、龙、心、梦…… |
| **融合体系** | 2–7 法任意融合，皆有专属法名——「禅」（月+墨）在宣纸上画一轮墨月 |
| **活背景** | 墨法令全站反色为宣纸；心法令一切浸作胭脂粉 |
| **物理秀场** | 48 节 verlet 弹簧链游龙、lub-dub 双跳心搏、浮游梦泡 |
| **生成式音频** | 每道法则一套 Web Audio 实时合成的环境音景 |
| **电影运镜** | 待机漂移、施法推镜、旋转冲击、震屏、指针引力透镜 |
| **彩蛋** | 弹幕刷屏的中指法则、隐藏字映射、万法归尘 |

## 法则一览

| 字 | 法则 | 现象 | 字 | 法则 | 现象 |
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

另有隐藏映射：春夏秋冬四时、禅（墨月）、酒 / 诗 / 茶、剑、凤、靠，以及终焉法则「万法归尘」。

## 融合与多法

- 一次输入多字，或切换 **融合** 模式点选法则
- 38 种具名融合：焚天烈焰（火+风）、星月交辉（星+月）、禅心墨月（墨+月）……
- 3–7 法同施依次升格：三才同辉 → 四象汇聚 → 五行轮转 → 六合归一 → 七星连珠

## 技术亮点

```
index.html   ← 一切：约 2,100 行 HTML/CSS/JS
```

- **拖尾渲染** —— 每帧半透明全屏覆膜产生运动拖尾；更换覆膜色，拖尾即成宣纸墨痕或胭脂红晕
- **合成编舞** —— 暗夜用 `lighter` 提亮发光，纸面用 `source-over` 正片叠底，按法则逐层切换
- **字形采样** —— 离屏画布以粗重字重渲染汉字，不透明像素即粒子群的 seek 目标
- **弹簧链游龙** —— 利萨茹驱动的龙首拖曳 48 节定距 verlet 链节，脊鬃、龙角、飘须皆随链而动
- **参数心形** —— 经典心形参数方程同时驱动施法粒子阵列与 lub-dub 搏动主心
- **生成式音频** —— 滤波噪声、失谐正弦对、锯齿低鸣按法则层叠；雷有噼啪、星有闪烁，皆生于定时器

## 快速开始

永远不需要构建。

```bash
# 直接打开
open index.html

# 或起本地服务（推荐，规避音频自动播放限制）
python3 -m http.server 8817
# → http://localhost:8817
```

## 操作

| 操作 | 效果 |
|---|---|
| 输入汉字 + 回车 | 施放法则 |
| 点击法则 chip | 从法则坞施放 |
| 融合模式 | 多选法则融合 |
| 音 | 开关环境音 |
| 留影 | 截取画布 |
| 移动指针 | 引力透镜扰动粒子场 |
| 滚回顶部 | 回到序章 |

## 文档语言

- [English](README.md)
- 简体中文 —— 本文件

## 许可

[MIT](LICENSE) © World Model contributors
