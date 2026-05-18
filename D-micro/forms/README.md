# D · forms（10 个表单控件微动效）

> 表单是用户最讨厌的环节。让控件动起来、对用户的输入有反应，能显著降低弃填率。

## 包含

| 文件 | 说明 |
|---|---|
| `checkbox-draw.html` | Checkbox 描边变实 + 对勾绘制（`stroke-dashoffset` · 双 path 协同） |
| `toggle-spring.html` | Toggle 反弹滑块（`cubic-bezier` spring · 基于原生 checkbox） |
| `radio-ripple.html` | Radio 涟漪选中（`::before` `scale 0→1` spring · 替换原生圆点） |
| `slider-floating-label.html` | Slider 浮动 label + 手柄缩放（`input[type=range]` · `:active` `scale`） |
| `dual-range-slider.html` | Dual handle range slider（双 `input range` 叠加 · min/max 互锁） |
| `floating-label-input.html` | Floating label · 焦点上浮（`:placeholder-shown` + `transform`） |
| `live-validation.html` | 实时校验 + 错误抖动（`input` event · regex · shake `@keyframes`） |
| `autocomplete-stagger.html` | Autocomplete 下拉 stagger 进入（filter + `animation-delay` 依次出现） |
| `magic-line-tabs.html` | 多按钮 magic line underline（`getBoundingClientRect` · 一根线跨按钮平滑滑动） |
| `chip-toggle.html` | Pill / chip 选中态（click toggle · `scale 1.05` 微弹） |

## 共同点 / 设计哲学

表单微动效的铁律：**不要替换原生控件，只装饰它**。

- 原生 `<input type="checkbox">` 隐藏（不要 `display:none`，会丢失键盘焦点；用 `opacity:0` + `position:absolute`）
- 用 `<label>` 包裹原生控件 + 自定义视觉
- 用 `:checked`、`:placeholder-shown`、`:focus`、`:invalid` 这些**伪类驱动 CSS**
- JS 只在需要"读值"或"做校验"的时候介入

这样做的好处：**完全保留无障碍**（screen reader、键盘 Tab、表单 submit 都正常）+ **几乎零 JS**（性能好、bundle 小）。

`magic-line-tabs` 是这一组里唯一一个必须用 JS 的，因为要测量 DOM 几何。但即便如此，也只在 click 时调一次 `getBoundingClientRect`，CSS `transition` 自己完成动效。
