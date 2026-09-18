# 拼豆图纸生成器

一个纯前端、离线可用的图片转拼豆图纸工具。选择图片后可以调整尺寸、选择拼豆品牌色库、匹配色号，并导出 PNG 图纸和豆数清单。

## 功能

- 拖拽或选择图片
- 调整图纸宽度和高度
- 支持 MARD、Artkal、Hama、Perler、COCO 等主流拼豆色号
- 默认使用 MARD 291 色色库
- 按 Lab 色彩空间匹配相近色号
- 主导色采样，减少边缘灰色过渡
- 照片模式提供适中的杂色清理和细节保留
- 干净模式强力清理孤立杂点和相近杂色
- 可选 Floyd-Steinberg 抖动，改善照片和渐变过渡
- 轻量边缘增强，提升轮廓清晰度
- 导出 PNG 图纸
- 导出 CSV 豆数清单
- 可爱风界面，手机和电脑浏览器都可以使用

## 本地使用

直接打开 [`outputs/index.html`](./outputs/index.html) 即可，不需要安装依赖或启动服务器。

也可以在本机启动一个静态服务器，例如：

```powershell
cd outputs
python -m http.server 8080
```

然后访问 `http://localhost:8080`。

## GitHub Pages 部署

1. 打开仓库的 **Settings > Pages**
2. 在 **Source** 中选择 **Deploy from a branch**
3. 选择 `main` 分支和 `/ (root)`
4. 保存后访问 `https://<你的用户名>.github.io/<仓库名>/outputs/index.html`

所有逻辑都在浏览器中运行，不上传图片到服务器。

## 文件结构

```text
outputs/
  index.html    工具页面和核心逻辑
  brands.js     拼豆品牌色号数据
  tailwind.js   本地内置的 Tailwind 运行时
```

## 许可证

MIT License
