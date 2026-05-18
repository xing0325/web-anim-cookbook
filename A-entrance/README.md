# A · 入场 & 转场

> 用户进站第一眼、以及页面切换瞬间的"进站动作"。第一印象很重要，这类动效决定了用户接下来会不会留下来。

## 包含

| 文件 | 说明 |
|---|---|
| `char-stagger.html` | 字符级 stagger 入场（GSAP SplitText · `power3.out` · 0.025s stagger，按字依次推上来） |
| `lime-curtain.html` | 全屏柠檬绿过场幕布（`.transition-w` + Rive 三态 input · Taxi.js 触发的路由转场） |

## 共同点 / 设计哲学

入场动效的核心是**遮蔽真实加载时间**：在数据 / 资源准备好之前，给用户一个"正在进入"的仪式感。SplitText 把整句拆成字符再 stagger，比整段淡入更精致；全屏幕布则负责盖住路由切换的丑陋瞬间。

两个 demo 都强调 `easing` 而非 `duration` —— 真正决定"高级感"的不是动效多长，而是缓动曲线对不对。
