# 配置说明

本文说明站点中可调整的配置项，均位于 `index.html` 顶部的 `<script>` 区域。

## 仓库信息

```js
const REPO = 'TanchiPanda/r6t5-docs';
const DEFAULT_PATH = 'docs/index.md';
```

| 配置 | 说明 |
| ---- | ---- |
| `REPO` | GitHub 仓库地址，格式为 `用户名/仓库名`，用于拼接「在 GitHub 上编辑」链接 |
| `DEFAULT_PATH` | 未携带 `?path=` 参数时默认加载的文档路径 |

## 目录清单格式

`manifest.json` 支持嵌套层级，节点类型有两种：

**分组节点**（可折叠）：

```json
{
  "title": "分组名称",
  "children": [ /* 子节点 */ ]
}
```

**文档节点**：

```json
{ "title": "文档标题", "path": "docs/reference/config.md" }
```

分组可以多层嵌套，侧边栏会递归生成可折叠目录。

## Markdown 渲染

页面使用 [marked](https://marked.js.org/) 在浏览器端将 Markdown 转为 HTML，已开启 GFM 表格与换行支持。如需代码高亮、数学公式等扩展能力，可在 `index.html` 中引入对应插件并在 `marked.setOptions` 中配置。

## 自定义样式

所有样式集中在 `index.html` 的 `<style>` 区域，CSS 变量定义在 `:root` 下，可直接修改主题色、边框、背景等：

```css
:root {
  --accent: #0969da;
  --sidebar-bg: #f7f8fa;
  --border: #e5e7eb;
}
```
