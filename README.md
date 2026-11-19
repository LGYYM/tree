# Merry Christmas · 粒子圣诞树

一个纯前端、零依赖的粒子圣诞树网页。用 WebGL 渲染 30 万个发光粒子，带三级 Bloom 光晕、星空与飘雪。

![预览](https://img.shields.io/badge/WebGL-2.0-blue) ![无依赖](https://img.shields.io/badge/dependencies-0-brightgreen)

## 特性

- **单文件**：全部 HTML/CSS/JS 内联在一个 `index.html` 里，没有任何外部依赖、CDN 或图片资源
- **零安装**：浏览器打开即用，手机 / 电脑 / 平板都行
- **可交互**：拖动旋转视角、滚轮或双指缩放，松手 3.5 秒后自动恢复自转
- **自适应**：竖屏自动拉远相机并把文字上移；帧率低于 26fps 时自动降低渲染分辨率

## 本地打开

直接双击 `index.html` 用浏览器打开即可。

如果想在手机上预览，在本目录启动一个静态服务器，然后手机连同一个 WiFi 访问：

```bash
python -m http.server 8080
```

然后手机打开 `http://电脑的局域网IP:8080/`。

## 操作说明

| 操作 | 效果 |
|---|---|
| 鼠标拖动 / 单指滑动 | 旋转视角 |
| 滚轮 / 双指捏合 | 缩放 |
| 静置 3.5 秒 | 自动恢复缓慢自转 |

## 部署到 GitHub Pages

1. 新建一个 **Public** 仓库
2. 把 `index.html` 上传到仓库**根目录**
3. 进入 `Settings` → `Pages`
4. Source 选 `Deploy from a branch`，分支 `main`，目录 `/ (root)`，保存
5. 等 1–2 分钟，访问 `https://<你的用户名>.github.io/<仓库名>/`

## 自定义

改 `index.html` 里的这两行即可修改贺卡文字：

```html
<div class="l1">Merry Christmas</div>
<div class="l2">To 甘永天天开心</div>
```

其他可调参数在 `<script>` 开头：

| 参数 | 作用 |
|---|---|
| `CFG.tree` | 树体粒子数量（默认 30 万，手机端 13 万） |
| `TREE_STOPS` | 树体颜色渐变（从树顶到树底的 RGB） |
| `fExposure` | 整体曝光，越大越亮 |
| `fStrength` | Bloom 光晕强度 |
| `bThresh` | 亮部提取阈值，越大只有越亮的部分会发光 |
| `dist` | 相机初始距离，越大画面越远 |

移动端可以用 URL 参数强制画质：`index.html?q=low` 或 `?q=high`。

## 浏览器要求

需要支持 WebGL（现代浏览器都支持）。如果没有启用 WebGL，页面会显示提示文字。