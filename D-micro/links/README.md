# D · links（10 个链接 / 文本微动效）

> 链接和文本的 hover 动效。这一组里很多是 OFF+BRAND 风格签名 —— 字符级操作 + Rive 状态机 + SVG 路径动效。

## 包含

| 文件 | 说明 |
|---|---|
| `char-hover-flip.html` | 字符级 hover 翻页（上下两层字符，依次翻面 · 纯 CSS stagger） |
| `rive-state-machine.html` | Rive 状态机切赛道（hover 切 SVG path · 利用 Rive 编辑器预设状态） |
| `underline-draw.html` | 下划线从左到右画出（`::after` `scaleX 0→1` · `transform-origin: left`） |
| `cube-flip-link.html` | 链接整词翻面 cube flip（3D `rotateX` · `backface-visibility: hidden`） |
| `typewriter.html` | Typewriter 打字机（`setInterval` 逐字 · cursor 闪烁 · 写完自动循环） |
| `scramble-text.html` | Glitch / Scramble（字符随机替换 24 帧 · 终态显示原文 · 经典 hacker 效果） |
| `char-shake.html` | 字符 hover 随机抖动（每个字独立 random `rotate` + `translate`） |
| `read-more.html` | Read more 展开 / 折叠（`grid-template-rows 0fr↔1fr` · 无需 max-height hack） |
| `wavy-underline.html` | 波浪下划线（SVG mask · `background-position` 横向流动） |
| `svg-icon-draw.html` | SVG icon hover 描线（`stroke-dasharray` + `stroke-dashoffset` 描出图标） |

## 共同点 / 设计哲学

链接动效有两个流派：

1. **CSS 派**（`underline-draw` / `cube-flip` / `read-more` / `wavy-underline`）：纯 CSS 实现，性能最好，但花样有限。
2. **JS 派**（`typewriter` / `scramble-text` / `char-shake` / `char-hover-flip`）：JS 控制每个字符或每一帧，花样无限，但要小心性能。

**字符级操作**是这一组的核心技术 —— 用 JS 或 GSAP SplitText 把整段文字拆成 `<span>` 包裹的单个字符，然后对每个字符施加独立动效。stagger 延迟可以让整段动效产生"波"的感觉。

`grid-template-rows: 0fr ↔ 1fr` 是 `read-more` 的现代解法，比 `max-height` 黑魔法干净得多 —— 这条技巧本身就值得记住。
