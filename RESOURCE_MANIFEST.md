# 资源清单

## 页面文件

| 文件 | 用途 | 是否直接访问 |
|---|---|---|
| `index.html` | Netlify 和本地服务器默认入口，包含理赔空间、办公区、智能伙伴、数据分析、风控中心、业务管理和系统管理 | 是 |
| `claim_core_vehicle_survey_page_v4.html` | 主页面原始文件名，供办公区任务跳转使用 | 是 |
| `claim_core_star_office_home.html` | 办公区 iframe，包含顶部指标、办公室场景和理赔动态 | 由主页面加载 |

## 品牌与业务图片

| 文件 | 用途 |
|---|---|
| `assets/zhongan-insurance-logo.png` | 众安保险 Logo 和站点图标 |
| `assets/car-top-view.png` | 车辆俯视图、损失证据和材料示例 |
| `assets/demo-avatars/claim-contact-1.jpg` | Demo 材料图片一 |
| `assets/demo-avatars/claim-contact-2.jpg` | Demo 材料图片二 |

## 办公区场景

| 文件 | 用途 |
|---|---|
| `assets/office/office.png` | 办公室整体背景 |
| `assets/office/desk.png` | Agent 办公桌 |
| `assets/office/chair.png` | Agent 办公椅 |

## Agent 动画精灵图

| 文件 | 用途 |
|---|---|
| `assets/admin-penguin-spritesheet.webp` | 调度 Agent 形象 |
| `assets/prompt-penguin-spritesheet.webp` | Agent 形象 |
| `assets/ai-spritesheet.webp` | Agent 形象 |
| `assets/calcifer-spritesheet.webp` | Agent 形象 |
| `assets/bocchi-spritesheet.webp` | Agent 形象 |
| `assets/ayanami-spritesheet.webp` | Agent 形象 |

## 配置与说明

| 文件 | 用途 |
|---|---|
| `README.md` | 项目入口、本地运行和部署说明 |
| `netlify.toml` | Netlify 静态站点发布目录配置 |
| `RESOURCE_MANIFEST.md` | 本文件，说明所有页面和素材的用途 |

## 依赖结论

当前项目的运行依赖全部位于 `claim-core-complete-project` 目录内。项目外没有必须复制的图片、动画、iframe 页面或 JavaScript 文件。
