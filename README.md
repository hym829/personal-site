# Personal Portfolio Site

> 暗黑科技风个人作品集网站 — 粒子动画背景、打字机效果、滚动动画、霓虹发光交互。

![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)
![GitHub Pages](https://img.shields.io/badge/Deployed_on-GitHub_Pages-222222?logo=github)

---

## 在线预览

👉 [https://hym829.github.io/personal-site/](https://hym829.github.io/personal-site/)

## 功能特性

- **Hero 首屏** — 全屏粒子动画背景 + 打字机自我介绍 + CTA 按钮
- **About Me** — 个人简介 + 社交链接（GitHub / Email）
- **Projects** — 项目卡片网格，鼠标追踪霓虹光晕效果
- **Skills** — 分类技能进度条，滚动触发渐增动画
- **Contact** — 联系方式入口
- **响应式设计** — 桌面 / 平板 / 手机三档适配
- **移动端汉堡菜单** — 侧滑导航面板
- **滚动动画** — IntersectionObserver 驱动的淡入效果
- **返回顶部** — 浮动按钮，滚动 400px 后出现

## 技术栈

| 类别 | 技术 |
|------|------|
| 样式 | CSS3 Custom Properties, Flexbox, Grid, Glassmorphism |
| 动画 | CSS Transitions, Keyframe Animations, Intersection Observer API |
| 粒子背景 | [Particles.js](https://github.com/VincentGarreau/particles.js) 2.0 |
| 打字机效果 | [Typed.js](https://github.com/mattboldt/typed.js) 2.1 |
| 图标 | [Font Awesome](https://fontawesome.com/) 6.5 |
| 字体 | Google Fonts — Orbitron (标题), Inter (正文) |
| 部署 | GitHub Pages + Actions |

## 视觉设计

- **主题**：暗黑科技风（Dark Tech）
- **配色**：深黑底 `#0a0a0f` + 青蓝光晕 `#00d4ff` + 紫色点缀 `#7b2ff7`
- **卡片**：半透明玻璃态 `rgba(255,255,255,0.05)` + `backdrop-filter: blur`
- **交互**：鼠标追踪光晕、霓虹边框发光、平滑滚动

## 项目结构

```
personal-site/
├── index.html              # 单页 HTML（6 个 section）
├── css/
│   └── style.css           # 全站样式（580+ 行）
├── js/
│   └── main.js             # 交互逻辑（粒子/打字机/滚动动画）
├── .github/
│   └── workflows/
│       └── deploy.yml      # GitHub Pages CI/CD
└── README.md
```

## 本地开发

```bash
# 1. 克隆项目
git clone https://github.com/hym829/personal-site.git
cd personal-site

# 2. 用任意本地服务器打开 index.html
# 推荐 VS Code Live Server 插件
# 或直接: npx serve .
```

## 自定义

修改以下文件即可定制个人网站：

| 修改项 | 文件 | 位置 |
|--------|------|------|
| 个人信息 / 简介 | `index.html` | `#about` section |
| 项目卡片 | `index.html` | `#projects` section |
| 技能数据 | `index.html` | `data-level` 属性 |
| 打字机文案 | `js/main.js` | `Typed.js` 配置 |
| 粒子颜色/密度 | `js/main.js` | `particlesJS()` 配置 |
| 配色方案 | `css/style.css` | `:root` 变量 |

## 许可证

MIT