# H · 媒体

> 视频和图片的"出现方式"。简单但容易做错 —— 直接 `autoplay` 会卡，直接 `<img>` 会闪。

## 包含

| 文件 | 说明 |
|---|---|
| `hover-video.html` | Hover 自动播放视频（`IntersectionObserver` lazy-load · 鼠标进入才 `play()`） |
| `stat-hover-img.html` | Stat hover 大图淡入（`mouseenter` + 背景图 fade · 数据卡片配预览图） |

## 共同点 / 设计哲学

媒体动效要解决两个问题：**何时加载** 和 **如何出现**。

- **何时加载**：永远用 `IntersectionObserver`，不要无脑 `autoplay`。视频在视口外播放是浪费带宽 + 浪费电池
- **如何出现**：`opacity` 淡入比硬切优雅 100 倍。视频要先 `play()` 等 `loadeddata` 再淡入，否则会看见第一帧黑屏

`hover-video` 把这两点合一：进入视口才加载，hover 才播放，离开就暂停。在画廊 / 产品列表 / 作品集场景特别有用，能做到"满屏视频但页面不卡"。

`stat-hover-img` 是 OFF+BRAND 在数据展示页常用的小心机：用户 hover 一个数字（"24 站冠军"），右上角浮现对应的视觉图（赛车现场照）—— 把抽象数字和具体形象关联起来。
