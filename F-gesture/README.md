# F · 手势 & 光标

> 把鼠标和触摸当成"创意输入"，而不仅仅是"点击工具"。这一类的 demo 最有"作品集网站"气质。

## 包含

| 文件 | 说明 |
|---|---|
| `tap-to-lock.html` | tap to lock 模态手势（`touch-action` 切换 · 锁住整页滚动 · 移动端常见） |
| `cursor-reveal.html` | 自定义光标 + 区域 reveal（`clip-path: circle()` · 光标位置揭开下层图） |
| `blend-cursor.html` | 菜单图片 blend-mode cursor（`mix-blend-mode` · 鼠标位置 radial-gradient 当遮罩） |
| `swipe-cards.html` | Swipe 滑动识别（统一 touch / mouse · 80px 阈值判定方向 · Tinder 卡牌典型） |
| `drag-sort.html` | 列表拖拽排序（HTML5 `drag` / `drop` API · 数组重排 · 占位高亮） |
| `drop-upload.html` | Drag-drop 文件上传区（`dragenter` 高亮 · `drop` 读 `FileList` · 通用上传模式） |
| `3d-tilt-card.html` | 卡片 3D tilt 鼠标跟随（`mousemove` 算偏移 → `rotateX/Y` · `perspective` 立体感） |

## 共同点 / 设计哲学

光标动效的两个高级玩法都在这里：

1. **clip-path circle**（`cursor-reveal`）：上层图盖住下层图，但在光标位置开一个圆形孔，露出下层。鼠标动孔就跟着动 —— "撕开一层"的感觉。
2. **mix-blend-mode + radial-gradient**（`blend-cursor`）：用一个跟随鼠标的径向渐变层做"灯光"，配合 `mix-blend-mode: difference` 或 `multiply`，让光标范围内的图片颜色反转或加深。

这两种技巧都**不需要真的换图**，只需要 CSS mask 或 blend，性能极好。

`tap-to-lock` 是移动端专属：长按或双指捏一下，让整页 `overflow: hidden`，这样可以在某个区域内做横向滑动 / 缩放，不会触发页面滚动。落地页和图册常用。

`swipe-cards` / `drag-sort` / `drop-upload` / `3d-tilt-card` 把"手势"从纯视觉转到**真功能**：滑动判定方向、拖拽改变顺序、放文件触发上传、鼠标偏移驱动 3D 倾斜。共同的核心是把**位移转成意图**：阈值（80px）、方向（左右）、目标（drop zone）、坐标（rotateX/Y）—— 都是从一个连续值里榨出离散决策。

特别说 `3d-tilt-card`：`perspective` + `rotateX/Y` 几行 CSS 加上几行 JS 就能做出"卡片在追鼠标"的物理感，性价比极高，是作品集网站和产品卡片的常驻技。
