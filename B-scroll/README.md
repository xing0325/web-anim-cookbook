# B · 滚动驱动

> 滚动是网页最长的交互。把滚轮的每一格 px 都用上，你的页面就比别人多了一个维度的表达力。这是整个 cookbook 里"含技术量"最高的一类。

## 包含

| 文件 | 说明 |
|---|---|
| `scroll-3d-helmet.html` | scrub · 滚动驱动 3D 头盔旋转（ScrollTrigger + CSS 3D · 滚轮即旋转角度） |
| `horizontal-pin.html` | 横向 pin 滚动（一屏纵向滚 = 多屏横向走 · GSAP `pin` + `translateX`） |
| `velocity-marquee.html` | 速度敏感 marquee（往下滚越快，跑马灯字越急；反向也反向） |
| `scroll-color.html` | 滚动驱动色彩补间（hex 解析 + RGB 线性插值 · 头盔色随滚动渐变） |
| `scroll-svg-draw.html` | Rive scrub · SVG path 描线（`stroke-dashoffset` 跟随滚轮，画出整条路径） |
| `section-progress.html` | 章节滚动进度条（`transform: scaleX` · scrub · 顶部细线指示当前章节进度） |
| `css-dual-marquee.html` | CSS 双向无限 marquee（`@keyframes` infinite · 零 JS · 两行反向叠加） |
| `parallax-layers.html` | 视差多层背景 parallax（3 层 · `translateY` 不同速度 · ScrollTrigger scrub） |
| `mask-reveal.html` | 圆形 Mask reveal 扩散下一屏（`clip-path: circle()` · scrub 圆扩散展开下一屏） |
| `stack-cards.html` | Stack cards 堆叠揭示（`position: sticky` 叠纸效果 · 卡片按顺序覆盖） |
| `scroll-snap.html` | scroll-snap 章节强制对齐（`scroll-snap-type: y mandatory` · 零 JS 章节吸附） |

## 共同点 / 设计哲学

滚动驱动动效的关键词是 **scrub**：把动效的"时间轴"绑定到滚动位置，而不是 wall-clock 时间。这意味着：

- 用户**完全控制**动效进度（往回滚也往回播）
- 动效成为页面信息的一部分，而不只是装饰
- 性能上比 `requestAnimationFrame` 自己监听 scroll 事件更稳（ScrollTrigger 内部用 `IntersectionObserver` + 节流）

`velocity-marquee` 和 `scroll-color` 是这类技术的"极致玩法"：把滚动**速度**和**位置**同时榨出来，做出别的网站做不到的细节。

`parallax-layers` / `mask-reveal` / `stack-cards` 是滚动叙事的"语法糖"：视差给页面纵深，mask 让章节切换变成视觉爆点，sticky 堆叠让卡片像扑克一张张盖上去。而 `scroll-snap` 走的是另一条路 —— 完全 CSS，零 JS，靠浏览器原生 API 实现章节强制对齐，是最便宜也最稳的"全屏分页"方案。
