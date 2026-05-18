# C · 导航 & 主题

> 导航栏和页脚的细节动作。这类动效不抢戏，但缺了就显廉价。

## 包含

| 文件 | 说明 |
|---|---|
| `nav-sentinel-theme.html` | 隐形哨兵 div 切 nav 主题（ScrollTrigger `onToggle` · `data-theme` 切色，白底进暗 nav，黑底进亮 nav） |
| `footer-theme.html` | Footer 三色主题（`data-footer-theme="black\|green\|white"` · 页脚根据上一屏自动变色） |

## 共同点 / 设计哲学

"哨兵 div"是这类技术的核心模式：在页面里塞几个**不可见的标记元素**，让 ScrollTrigger 监听它们进出视口的时刻，然后在那一刻切换整个 nav / footer 的 `data-attribute`。CSS 用属性选择器响应变化，完成视觉切换。

好处：**逻辑和视觉解耦**。JS 只管"现在该是什么状态"，CSS 自己处理过渡。换主题色、加新主题、调过渡曲线都不用碰 JS。
