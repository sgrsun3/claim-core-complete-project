# 理赔核心完整展示项目

这是从当前理赔核心原型整理出的自包含静态项目。项目所需页面、办公区 iframe、Agent 精灵图、办公室素材、众安 Logo、车辆图和 Demo 图片都在本目录内。

## 入口

- 在线部署入口：`index.html`
- 原始主页面：`claim_core_vehicle_survey_page_v4.html`
- 办公区 iframe：`claim_core_star_office_home.html`

`index.html` 与原始主页面内容相同。部署时应上传整个目录，不能只上传一个 HTML。

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

可将本目录整体拖入 Netlify Deploys，也可以在本目录执行：

```bash
netlify deploy --prod --dir .
```

`netlify.toml` 已将当前目录设为发布目录。

## 外部依赖状态

- 不包含 `file://` 路径。
- 不包含 `/Users/...` 等本机绝对路径。
- 不从第三方网站加载图片或动画素材。
- 页面字体使用操作系统自带的中文和无衬线字体，不需要下载字体文件。

完整文件用途见 [RESOURCE_MANIFEST.md](RESOURCE_MANIFEST.md)。
