# 理赔核心完整展示项目

这是从当前理赔核心原型整理出的自包含静态项目。项目所需页面、办公区 iframe、Agent 精灵图、办公室素材、众安 Logo、车辆图和 Demo 图片都在本目录内。

## 入口

- 在线部署入口：`index.html`（集成办公区、任务工作台与智能伙伴）
- 车辆查勘主页面：`claim_core_vehicle_survey_page_v5.html`
- 办公区 iframe：`claim_core_star_office_home.html`（左侧办公区 + 右侧任务详情）

`index.html` 为统一入口，部署时应上传整个目录，不能只上传一个 HTML。

## 本地运行

在本目录执行：

```bash
python3 -m http.server 8080
```

然后访问：

```text
http://127.0.0.1:8080/
```

直接双击 `index.html` 也可以打开，但使用本地 HTTP 服务更接近 Netlify 的线上环境。

## 部署到 Netlify

- 在线地址：<https://xos-claimsystem.netlify.app/>
- GitHub 仓库：<https://github.com/sgrsun3/claim-core-complete-project>

采用 **Git 持续部署**：每次 `git push origin main` 后，Netlify 自动拉取并发布，约 1 分钟生效。

```bash
git add -A
 git commit -m "更新说明"
 git push
```

也可将本目录整体拖入 Netlify Deploys，或使用 CLI：

```bash
netlify deploy --prod --dir .
```

`netlify.toml` 已将当前目录设为发布目录（`publish = "."`，无构建命令）。

## 外部依赖状态

- 不包含 `file://` 路径。
- 不包含 `/Users/...` 等本机绝对路径。
- 不从第三方网站加载图片或动画素材。
- 页面字体使用操作系统自带的中文和无衬线字体，不需要下载字体文件。

完整文件用途见 [RESOURCE_MANIFEST.md](RESOURCE_MANIFEST.md)。

## 更新记录

### 2026-07-25 理赔空间折叠按钮优化

- **重新设计图标**：由"方框+竖线+直角箭头"换为更清爽的面板图标（圆角矩形 + 居中箭头），打开/关闭两态箭头方向相反。
- **美化按钮样式**：尺寸 30×30 → 34×34，圆角加大至 10px，添加柔和阴影与主色 hover 过渡动画。
- **完善显隐逻辑**：扩展隐藏规则——打开右侧任务信息时折叠按钮自动消失，关闭后恢复显示（原先仅在对话模式下隐藏）。
- 涉及文件：`index.html`（CSS 样式、HTML 图标、JS 切换逻辑）。

### 2026-07-25 办公区小人交互重构

- **点击小人不再直接对话**：原先点击小人会同时切换暂停状态并弹出对话框，现在改为点击后在小人身上展开操作浮层。
- **操作浮层**：浮层显示 Agent 名称/状态 + 4 个操作按钮（定位工位、暂停/继续、完成并汇报、与他沟通），带展开动画与指向箭头。
- **“与他沟通”才打开对话框**：只有点击浮层中的“与他沟通”按钮才会打开对话弹窗，其余操作直接执行。
- **浮层跟随小人**：小人在办公区内移动时浮层实时跟随定位。
- **点击空白收起**：点击 canvas 空白处自动收起浮层并取消选择。
- 涉及文件：`claim_core_star_office_home.html`（浮层 HTML/CSS、selectAgent 改造、定位逻辑、按钮事件、动画循环）。
