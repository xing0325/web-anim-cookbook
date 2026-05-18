# D · 微动效合集（40 个）

> 整个 cookbook 体量最大的一类。微动效就是那些"用户没意识到，但去掉就觉得网页廉价"的小动作。按交互对象分成 4 个子组。

## 子组

| 子组 | 数量 | 主题 |
|---|---|---|
| [buttons](./buttons/README.md) | 10 | 按钮的所有 hover / click / 状态切换 |
| [links](./links/README.md) | 10 | 链接和文本本身的 hover / 描线 / 翻转 |
| [forms](./forms/README.md) | 10 | 表单控件（checkbox / radio / slider / input）的细节 |
| [feedback](./feedback/README.md) | 10 | 反馈状态（modal / toast / tooltip / skeleton / cursor） |

## 共同点 / 设计哲学

微动效的两条铁律：

1. **不超过 300ms**。超过用户就会觉得卡。除非是 modal / drawer 这种"大件"，可以到 400-500ms。
2. **必有 easing**，不允许 `linear`。`ease-out` 是默认选择，`cubic-bezier` 自己调最好。

40 个 demo 里，反复出现的技术点是：
- `transform` 优先于 `top/left`（GPU 加速）
- `opacity` 配合 `transform` 做淡入淡出
- `:hover` 状态的 `transition` 写在元素上，`:active` 状态的 `transition` 可以更短
- `pointer-events: none` 用来让动效层不挡交互
- `aria-*` 属性也参与状态切换，不只是 class

这些看着简单，但 40 个组合起来，就是一个网站"高级"和"廉价"的分水岭。
