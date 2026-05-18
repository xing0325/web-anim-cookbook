# G · 视觉系统

> 不是某一个组件的动效，而是整个网站"视觉氛围"的基础设施。字号、字宽、字形、布局变换、异形容器。

## 包含

| 文件 | 说明 |
|---|---|
| `fluid-clamp.html` | 1728 流体 clamp 字号（`clamp()` · 整站字号根据视口呼吸 · 设计稿基准 1728px） |
| `oval-arc-text.html` | 椭圆轨迹大字（`transform-origin` + 字符 `rotate` · 字按弧形排） |
| `gsap-flip.html` | GSAP FLIP 布局变形（First-Last-Invert-Play · 元素飞跃式重新排布） |
| `svg-mask-shape.html` | SVG mask 异形容器（`-webkit-mask-image` · 凹缺切角 · 不规则边界） |
| `variable-font.html` | Variable Font 双轴（`wght` + `wdth` · `font-variation-settings` 平滑调节） |
| `scroll-font-width.html` | 滚动驱动字宽变化（`wdth` 75→125 · scrub · 文字"喘气"） |

## 共同点 / 设计哲学

视觉系统这一类是 cookbook 里"基础设施"层级的东西 —— 它们不是局部装饰，而是**整个网站语言的一部分**。

- `clamp()` 一行解决整站字号响应式，比 `@media` 媒体查询 + 三套字号优雅一万倍
- Variable Font 让 1 个字体文件等于过去 9 个（5 种字重 × 2 种字宽 + 斜体），bundle 一下子小很多
- GSAP FLIP 是布局动画的核武器：你只管"现在元素在哪、之后元素在哪"，FLIP 算出中间的位移自己补帧
- SVG mask 让 `<div>` 不再是矩形，做 ticket 切角、缺口卡片等设计语言

`scroll-font-width` 是 Variable Font + ScrollTrigger 的组合拳：随着滚动，标题文字的宽度从压缩 (`wdth: 75`) 变到展开 (`wdth: 125`)，文字像在呼吸 —— 这种细节是 OFF+BRAND 标志性的"高级网站"质感。
