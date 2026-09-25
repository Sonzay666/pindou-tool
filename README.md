# 拼豆图纸生成器

一个纯前端、离线可用的图片转拼豆图纸工具。选择图片后可以调整尺寸、选择拼豆品牌色库、匹配色号，并导出 PNG 图纸和豆数清单。所有图片处理都在浏览器本地完成，不会上传到服务器。

## 功能

- 拖拽或选择图片
- 调整图纸宽度和高度
- 提供 16、24、32、48、64、96、128 等常用尺寸预设
- 支持 MARD、Artkal、Hama、Perler、COCO 等主流拼豆色号
- 默认使用 MARD 291 色色库
- 默认使用 Oklab 色彩空间匹配相近色号，过渡更自然
- 默认开启“真实”模式，使用 CIEDE2000 感知色差匹配，更适合真人照片和肤色还原
- 自动识别像素图案，使用邻近采样保留原像素；也可手动切换照片或像素图模式
- 照片使用主导色采样，减少边缘灰色过渡
- 可选边缘增强，提升轮廓清晰度，默认关闭
- 保留孤立像素和小面积色块，不自动清理图案细节
- 导出 PNG 图纸
- 导出 CSV 豆数清单
- 一键导出“图纸 + 色号清单”图片，包含数量、总数和尺寸
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

## Netlify 部署

1. 将仓库推送到 GitHub
2. 打开 [Netlify](https://app.netlify.com)，选择 **Add new site > Import an existing project**
3. 选择 GitHub 仓库 `Sonzay666/pindou-tool`
4. 构建命令留空，发布目录填写 `outputs`
5. 点击 **Deploy site**

部署完成后，Netlify 会提供一个类似 `https://你的站点名.netlify.app` 的链接，直接分享给其他人即可使用。

## 文件结构

```text
outputs/
  index.html    工具页面和核心逻辑
  brands.js     拼豆品牌色号数据
  tailwind.js   本地内置的 Tailwind 运行时
```

## 许可证

MIT License
