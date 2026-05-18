# E · 数据驱动

> 让数字动起来。倒计时、计数器、CMS 切换 —— 这类动效的关键是"数字本身的变化"成为视觉焦点。

## 包含

| 文件 | 说明 |
|---|---|
| `flip-countdown.html` | 倒计时翻页数字（`yPercent` flip · 每秒更新 · 老式机场显示牌质感） |
| `cms-calendar.html` | CMS 日历切换（24 站字段绑定 · prev/next 按钮 · 字段更新带动效） |
| `scroll-counter.html` | 滚动数字计数器（ScrollTrigger once · GSAP `snap` · `power2.out` 减速到目标值） |

## 共同点 / 设计哲学

数据驱动动效有一个反直觉的细节：**数字变化要快，但要"看得清"**。

- `flip-countdown` 用翻牌动效，每张牌只翻一次，节奏清晰
- `scroll-counter` 从 0 跳到目标值（比如 24 站），用 `power2.out` 缓动 —— 最后几个数字会"减速进入"，让用户能读到终值
- `cms-calendar` 字段切换时，旧数字向上滑出 + 新数字从下滑入，方向暗示"翻到下一站"

通用技巧：**用 `font-variant-numeric: tabular-nums`**。等宽数字让数字变化时位置不抖，是这类动效的隐藏前提。
