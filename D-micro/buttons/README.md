# D · buttons（10 个按钮微动效）

> 按钮是网页上点击量最高的元素。让用户每次点都"爽一下"，留存就不一样。

## 包含

| 文件 | 说明 |
|---|---|
| `rive-button-4pack.html` | hover 4 件套（rotate / invert / scale / shake，一个 Rive 文件四种用法） |
| `magnetic-button.html` | 磁力按钮 magnetic（鼠标 200px 内开始被吸过去 · `lerp 0.18` 平滑跟手） |
| `hold-to-transition.html` | Hold-to-transition（按住 0.6s 才触发 · 进度环可视化 · 防误触） |
| `ripple-button.html` | 按钮 ripple 涟漪（从点击位置 · `scale 0→4` + `opacity 1→0`） |
| `bg-slide-button.html` | 按钮背景从一侧滑入（`::before` `translateX` · 纯 CSS · 零 JS） |
| `arrow-follow-button.html` | 按钮内箭头跟随光标方向（`atan2` 计算角度 · `rotate`） |
| `inset-shadow-button.html` | 按钮按下 inset shadow 内陷（`:active` · 拟物质感） |
| `loading-button.html` | 按钮 loading 态（文字替换为 spinner · CSS `rotate` 无限循环） |
| `success-button.html` | 按钮 success 态（click → ✓ 替换 + 反色 · 2s 后自动复位） |
| `disabled-button.html` | 按钮 disabled 平滑过渡（`opacity` + `filter: saturate()` 渐变到失能） |

## 共同点 / 设计哲学

按钮微动效要分清三个状态：**hover / active / 异步状态（loading / success / disabled）**。

- **hover** 是"我准备点了"的预告，应该最克制（200ms 内、变化最小）
- **active** 是"我正在点"的反馈，应该最即时（≤100ms、有触感如 inset shadow）
- **异步状态**是"操作结果"，应该最明显（500ms+、可以放肆一点）

10 个 demo 覆盖了这三个状态的常用花活，可以自由组合 —— 比如 `magnetic-button` 当 hover、`ripple-button` 当 active、`loading-button` 当异步态，组成一个完整的按钮组件。
