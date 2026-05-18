# C · 导航 & 主题

> 导航栏和页脚的细节动作。这类动效不抢戏，但缺了就显廉价。

## 包含

| 文件 | 说明 |
|---|---|
| `nav-sentinel-theme.html` | 隐形哨兵 div 切 nav 主题（ScrollTrigger `onToggle` · `data-theme` 切色，白底进暗 nav，黑底进亮 nav） |
| `footer-theme.html` | Footer 三色主题（`data-footer-theme="black\|green\|white"` · 页脚根据上一屏自动变色） |
| `sticky-nav-shrink.html` | Sticky nav 滚动时缩小（scroll position 阈值 · class toggle 切紧凑态） |
| `hamburger-morph.html` | Hamburger 转 close（3 横线 `rotate` + 中线 opacity 0 · 合成 X） |
| `theme-switcher.html` | 主题切换器 dark/light/system（3 态 toggle · `prefers-color-scheme` · CSS 变量平滑色变） |
| `dot-navigator.html` | 侧边 dot navigator（`IntersectionObserver` 高亮当前 section · 点击锚跳） |

## 共同点 / 设计哲学

"哨兵 div"是这类技术的核心模式：在页面里塞几个**不可见的标记元素**，让 ScrollTrigger 监听它们进出视口的时刻，然后在那一刻切换整个 nav / footer 的 `data-attribute`。CSS 用属性选择器响应变化，完成视觉切换。

好处：**逻辑和视觉解耦**。JS 只管"现在该是什么状态"，CSS 自己处理过渡。换主题色、加新主题、调过渡曲线都不用碰 JS。

`sticky-nav-shrink` 和 `dot-navigator` 是同一种思想的两种界面表达：前者用 nav 自身的"高度变化"暗示"你已经滚走了"，后者用一列圆点 + `IntersectionObserver` 把整个页面的"章节地图"画出来。

`hamburger-morph` 和 `theme-switcher` 都是**单一按钮多态**的练习：3 根横线变 X、3 态主题切换。共同的细节是过渡曲线要选对 —— hamburger 用 `cubic-bezier` 的弹簧感，theme 切换则要给整个文档加 `transition: background-color, color`，让色变像呼吸而不是闪屏。
