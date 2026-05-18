# D · feedback（10 个反馈状态微动效）

> 系统对用户操作的反馈：弹窗、通知、提示、加载、空状态、错误。这些时刻动效得当，用户就觉得"这个产品有人在做"。

## 包含

| 文件 | 说明 |
|---|---|
| `modal-blur.html` | Modal 弹窗 + backdrop blur（`backdrop-filter: blur` · `scale 0.92→1` 入场） |
| `modal-shake.html` | Modal 摇晃强调拒绝（click-outside detect · shake 0.4s · "不能关"的强反馈） |
| `toast-stack.html` | Toast 通知滑入 + auto-dismiss（动态 DOM · 堆叠多条 · 3s 自动消失） |
| `tooltip-delay.html` | Tooltip hover delay + 定位（600ms delay 防误触 · `position: fixed`） |
| `tooltip-edge-flip.html` | Tooltip 智能边界反转（viewport edge detect · 靠右就向左弹） |
| `skeleton-wave.html` | Skeleton loader · wave 闪烁（`linear-gradient` 平移 · 假装在加载） |
| `empty-state.html` | Empty state · 插画 + 引导（SVG + 标题 + 副标题 + CTA 四件套） |
| `notification-badge.html` | Notification badge 弹出（`scale` spring · 数字 flip 切换） |
| `cursor-spring.html` | Cursor 弹簧延迟跟随（`lerp 0.15` · 半拍跟手的高级感） |
| `heart-particles.html` | Like + 粒子飞溅（Web Animations API · 8 个粒子四散） |

## 共同点 / 设计哲学

反馈动效要分清"**好消息**"和"**坏消息**"的动效语法：

- 好消息（success / 收到通知）：**spring**、**scale 放大**、**飞溅** —— 释放型
- 坏消息（错误 / 拒绝 / 加载中）：**shake**、**pulse**、**dim** —— 焦虑型
- 中性（信息 / tooltip / skeleton）：**slide**、**fade**、**linear-gradient wave** —— 低存在感

`modal-shake` 是个经典例子：用户点 backdrop 想关弹窗，但这个弹窗"不让关"（比如有未保存内容），不能弹另一个二级弹窗（会更烦），只能让弹窗自己**摇一下表示拒绝** —— 这是"动效作为 UI 语言"的最佳示范。

`cursor-spring` 单独说一下：自定义光标如果是 `lerp 1`（即时跟随），用户感觉不到；`lerp 0.15` 慢半拍，反而让光标"有重量"，这种"不完美"才是高级感的来源。
