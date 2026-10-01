# web-anim-cookbook

> 90 个可直接拷贝复用的 web 高级动效 demo。反向工程自 [landonorris.com](https://landonorris.com)（兰多·诺里斯官网，由 [OFF+BRAND](https://offbrand.studio) 工作室操刀），整理出一套"普通网页用不到的高级动效"配方集。

**在线浏览：** <https://xing0325.github.io/web-anim-cookbook/>  
**内容：** 90 个分类 demo + 1 个综合旗舰示例，均可独立阅读和运行。

赛车风视觉（柠檬绿 `#d2ff00` + 暗绿 `#0a0e07`），但 demo 本身是纯技术展示，可用于任何项目。

---

## 这是给谁的

- 前端开发者，需要做高级网页动效但懒得每次从零摸索的人
- 想看 GSAP / ScrollTrigger / Rive / Web Animations API 真实用法的人
- 想抄一个能跑的最小 demo，再缝进自己项目的人

每个 demo 都是一个**独立的 HTML 文件**，打开即跑，复制即用，不需要构建工具、不需要 npm install。

---

## 目录总览

| 类 | 名称 | 数量 | 一句话特点 |
|---|---|---|---|
| [A](./A-entrance/README.md) | 入场 & 转场 | 4 | 进站动作：字符 stagger、全屏过场幕布、SVG morph、logo 描线 |
| [B](./B-scroll/README.md) | 滚动驱动 | 11 | ScrollTrigger 的所有花活，scrub / pin / velocity / parallax / snap |
| [C](./C-nav/README.md) | 导航 & 主题 | 6 | 哨兵切色、Footer 主题、sticky shrink、hamburger、主题切换、dot nav |
| [D](./D-micro/README.md) | 微动效合集 | 40 | 4 个子组：按钮 / 链接 / 表单 / 反馈 |
| [E](./E-data/README.md) | 数据驱动 | 6 | 倒计时、CMS 日历、计数器、localStorage、multi-step、undo/redo |
| [F](./F-gesture/README.md) | 手势 & 光标 | 7 | tap-to-lock、cursor reveal、blend、swipe、drag-sort、drop-upload、3D tilt |
| [G](./G-visual/README.md) | 视觉系统 | 12 | clamp、椭圆排字、Variable Font、conic 仪表、玻璃、描边字、blob、3D flip、**流体光标位移** |
| [H](./H-media/README.md) | 媒体 | 4 | hover 自动播放、stat hover、lightbox、before/after 对比 |

---

## Quick start

### 浏览一个 demo

直接双击 `.html` 文件，浏览器打开即可。所有 demo 都是单文件、零依赖（除少数引用 CDN 上的 GSAP / Rive），打开就能看见效果。

如果想本地起一个 server（推荐，避免 CORS / file:// 限制）：

```bash
# Python
python -m http.server 8000

# Node
npx serve

# 然后访问 http://localhost:8000/
```

### 把代码搬到自己项目

每个 demo 是**单文件 self-contained**，结构都长这样：

```html
<!doctype html>
<html>
  <head>
    <link rel="stylesheet" href="../_shared/base.css"> <!-- 公共 tokens -->
    <style>/* demo 自己的样式 */</style>
  </head>
  <body>
    <!-- demo 标记 -->
    <script>/* demo 自己的脚本 */</script>
  </body>
</html>
```

要复用一个 demo，三步：

1. **抄走 `<style>` 块**（或里面你需要的那几条规则）
2. **抄走 `<body>` 里的标记**（保留 class / data-attribute）
3. **抄走 `<script>` 块**（如果有 GSAP / Rive，确保你项目里也加载了对应 CDN）

`_shared/base.css` 里只放了一些 CSS reset 和 cookbook 自己的 chrome（顶栏、标题样式）—— 如果你不要 cookbook 的外观，直接忽略它，每个 demo 的真·动效逻辑都在自己文件的 `<style>` 和 `<script>` 里。

---

## 设计哲学

- **单文件**：一个 demo = 一个 HTML，不拆 components，不搞 framework
- **零打包**：浏览器直接打开，不需要 build
- **可读**：变量名、注释、阶段分块都写清楚，照着改就行
- **真·可复用**：每个 demo 都假设你会把它拷进 React / Vue / Astro / 静态站，所以不依赖任何宿主框架

---

## 关于来源

灵感来源：[landonorris.com](https://landonorris.com)（F1 车手 Lando Norris 个人站，工作室 OFF+BRAND 出品），网站本身展示了大量"普通商业网页很少见"的高级动效组合。本仓库通过浏览器开发者工具反向工程 + 重新实现，把这些技术点抽成独立可读的 demo。

非官方、非合作，仅用于学习与技术参考。所有版权归原网站所有者。

---

## License

MIT — 随便拿去用，商用也行，不用署名。

---

## 关于这个仓库

- GitHub: [xing0325/web-anim-cookbook](https://github.com/xing0325/web-anim-cookbook)
- Issue / PR 欢迎，特别是：发现 bug、补充新的高级动效、或者你也反向工程了别的站想贡献进来
