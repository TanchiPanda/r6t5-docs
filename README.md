# r6t5-docs

基于 GitHub Pages 的静态文档站：左侧可折叠目录，URL 通过 `?path=` 指定文档，右侧提供「在 GitHub 上编辑」按钮。

## 在线访问

```text
https://TanchiPanda.github.io/r6t5-docs/
```

## 功能

- **可折叠文档目录**：由 `manifest.json` 驱动，支持多层分组嵌套。
- **按路径加载文档**：`?path=docs/guide/getting-started.md` 指定任意 Markdown 文档。
- **GitHub 一键编辑**：顶栏按钮跳转当前文档的 GitHub 编辑页面。
- **浏览器端渲染**：Markdown 经 marked 实时渲染为 HTML，无需本地构建。
- **响应式布局**：窄屏下侧边栏变为抽屉式菜单。

## 目录结构

```text
├── index.html          # 站点渲染器
├── manifest.json       # 文档目录清单
└── docs/               # Markdown 文档
```

## 本地预览

```bash
python3 -m http.server 8000
# 访问 http://localhost:8000
```

## 新增文档

1. 在 `docs/` 下新建 `.md` 文件；
2. 在 `manifest.json` 对应分组中添加 `{ "title": "...", "path": "..." }`；
3. 推送到 `main` 分支，Pages 自动部署。

## 开启 GitHub Pages

仓库 **Settings → Pages**：Source 选择 `Deploy from a branch`，Branch 选 `main`、文件夹选 `/(root)`，保存即可。
