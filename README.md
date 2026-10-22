# 报告网页版

《金属基复合材料制备技术及液相法的工艺实践》静态网页，入口为 `index.html`。

远程仓库 `mmcLect` 的根目录即站点根目录。

## 目录结构

```text
./
├── index.html                      # 网页入口
├── .nojekyll                       # GitHub Pages 不启用 Jekyll
├── README.md
└── assets/
    ├── css/style.css               # 页面样式
    ├── images/                     # 网页用图（统一 PNG）
    ├── ref.bib                     # BibTeX 文献库
    └── Frontiermmc2026-30min.pdf    # 30 分钟版报告 PDF（约 45 MB）
```

## 本地预览

在站点根目录（本地为 `docs/`，远程仓库为仓库根目录）运行：

```bash
python -m http.server 8000
```

然后打开 <http://localhost:8000/>。

## 发布到 GitHub Pages

1. 将站点文件提交到 GitHub 仓库根目录。
2. 进入仓库 **Settings → Pages**。
3. **Source** 选择 **Deploy from a branch**。
4. **Branch** 选择 `main`，**Folder** 选择 `/ (root)`。
5. 保存后等待 GitHub Pages 构建完成。

发布地址一般为：

```text
https://<用户名>.github.io/<仓库名>/
```

## 更新内容

- 修改 `index.html` 和 `assets/css/style.css`。
- 替换 `assets/images/` 中的 PNG 图片。
- 重新导出 30 分钟版 PDF 后，替换 `assets/Frontiermmc2026-30min.pdf`。
- 图片建议保持 PNG 格式；论文插图可在导出时按页码 + trim 裁剪，再转成 PNG。

## 图片来源与处理

- 论文插图从 `Frontiermmc2026/Zhou2025PartA.pdf` 按页码和 trim 视窗裁剪，300 dpi 渲染后压缩为 PNG。
- 其他插图由 `Frontiermmc2026/figures/` 中的 JPG/PNG 统一转为 PNG。
- 二维码由 LaTeX `qrcode` 宏包生成，指向报告网页。
- 页面不依赖外部字体或 JS，可直接静态托管。

## 说明

`assets/Frontiermmc2026-30min.pdf` 约 45 MB。如希望站点更轻，可以删除该 PDF，并在 `index.html` 中移除两个“下载报告 PDF”链接。
