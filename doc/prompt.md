# 多层旭日图页面风格提示词

## 最终整合版 Prompt

请生成一个高端专业、极具辨识度的 Web Dashboard 页面界面，核心主体是位于页面中心的大型多层同心旭日图（Sunburst Chart / 轮盘图）。整体视觉采用 Neo-Brutalism UI 风格，但不是生硬刺眼的工业粗暴风，而是融合插画感、漫画波普风、编辑排版感与现代专业仪表盘布局的高级版本。

页面背景使用温暖明亮的奶油黄/明黄色波普底纹，带有规则黑点网格（Halftone Dots）效果；主内容卡片使用柔和温润的奶杏色 / 奶油杏仁色；所有卡片、图表模块、图例、标签、徽标、按钮与装饰图形都使用极粗纯黑描边，并配合零模糊的硬偏移阴影，形成极强的图形识别度与层次感。

中心旭日图为页面视觉焦点，整体尺寸尽量大，尽可能铺满主展示区，使各层文字有足够空间排布，不拥挤、不重叠。旭日图采用完全扁平化 2D 矢量风格，不要渐变、不要拟物、不要玻璃拟态、不要 3D 渲染。图表颜色使用高饱和但彼此协调的霓虹系色块，建议以皇家蓝、薄荷绿、番茄红 / 珊瑚红、亮黄为主，形成强烈但舒适的视觉冲击。

页面整体要有“高端信息图编辑设计 + 漫画波普 UI + 专业仪表盘”的综合气质：布局整洁、留白明确、信息层级清楚、模块边界鲜明、阅读路径清晰，适合用于 PPT 展示、汇报页面、能力地图展示和专业作品集展示。

## 简化英文版 Prompt

Design a premium web dashboard UI featuring a very large multi-layer concentric sunburst chart at the center. The overall style is Neo-Brutalism with a clean editorial layout, playful pop-art illustration influence, and a professional infographic feel.

Use a warm creamy yellow background with a black halftone dot grid pattern. Main cards should use soft almond-cream surfaces. Apply very thick solid black outlines and hard offset black shadows with zero blur to all cards, chart frames, legends, labels, badges, and decorative geometric shapes.

The sunburst chart should be the dominant visual focus, scaled up as much as possible so labels have enough space and do not overlap. Use a fully flat 2D vector style with no gradients, no glassmorphism, no 3D effects. Use saturated but visually comfortable neon-inspired color blocks such as royal blue, mint green, poppy red / coral red, and bright yellow.

The final result should feel like a hybrid of modern dashboard UI, editorial infographic design, and pop-comic Neo-Brutalism: highly scannable, visually bold, playful, clean, premium, and presentation-ready.

## 结构化风格要求

### 1. 整体气质

- 风格关键词：`Neo-Brutalism`、`Pop Art`、`Editorial Infographic`、`Premium Dashboard`
- 视觉目标：`强辨识度`、`高信息密度但不拥挤`、`专业可汇报`、`舒适而有记忆点`
- 画面属性：`100% flat 2D`、`vector style`、`clean UI layout`

### 2. 背景

- 页面背景建议：`#F7D84B`、`#FAF3C0`、`#FAF9F6`
- 推荐方式：明黄色或奶油黄底色 + 规则黑点网格
- 允许加入极简几何装饰，如圆形、方块、网格、线框图形

### 3. 卡片与容器

- 卡片底色建议：`#FFF1DE`、`#FFF3E0`、`#FFF8EF`
- 描边：`3px` 到 `4px solid #000000`
- 阴影：`6px 6px 0 #000000` 或 `10px 10px 0 #000000`
- 不要模糊阴影，不要透明玻璃感

### 4. 旭日图

- 图表必须尽可能大，优先保证标签可读性
- 层级建议：`大类 -> 工具 -> 实践场景`
- 文字不要挤在圆心，必要时增大外半径并缩小内孔
- 标签可采用：`径向排布 + 智能截断`
- 外层文本允许简化，完整信息由 tooltip 提供

### 5. 图表配色

- 高频：皇家蓝 `#4169E1`
- 中频：薄荷绿 `#00D68F`
- 低频：番茄红 / 珊瑚红 `#FF5A5F`
- 辅助强调色：亮黄 `#FFE95C` 或 `#FFD60A`
- 要求：高饱和、纯色块、对比明确，但整体仍然精致舒适

### 6. 描边与阴影

- 所有模块统一使用纯黑粗描边
- 所有阴影统一使用零模糊硬阴影
- 推荐参数：

```css
border: 4px solid #000000;
box-shadow: 6px 6px 0 #000000;
```

### 7. 字体与排版

- 字体风格：干净、现代、粗体无衬线
- 推荐字体：`Inter`、`Segoe UI`、`Microsoft YaHei`
- 标题：高字重、大字号、紧凑行高
- 正文：清晰克制，不使用花哨装饰
- 版式强调模块边界、标签层级和扫描效率

## 不要出现的风格

- 不要 3D
- 不要渐变
- 不要玻璃拟态
- 不要毛玻璃
- 不要柔糊阴影
- 不要灰蒙蒙的低对比莫兰迪主画面
- 不要过度装饰导致图表主体不清晰

## 适用于图像生成 / 页面生成的短 Prompt

大型多层同心旭日图居中展示的高端 Web Dashboard 界面，Neo-Brutalism 风格，完全扁平化 2D 矢量设计，明黄色黑点网格背景，奶杏色卡片，极粗纯黑描边与零模糊硬阴影，皇家蓝、薄荷绿、番茄红、亮黄的高饱和协调配色，融合漫画波普、编辑信息图和现代专业 UI 排版，干净、醒目、舒适、适合展示汇报。

