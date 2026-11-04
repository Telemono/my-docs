# my-docs

基于 MkDocs Material 的个人技术文档网站，使用 GitHub Actions 自动构建并部署到 GitHub Pages。

- 网站地址：https://telemono.github.io/my-docs/
- 个人实验报告：[report/README.md](report/README.md)
- 源码仓库：https://github.com/Telemono/my-docs

## 本地预览

```bash
python -m venv .venv
```

Windows PowerShell 激活虚拟环境：

```powershell
.\.venv\Scripts\Activate.ps1
```

安装依赖并启动预览：

```bash
python -m pip install -r requirements.txt
python -m mkdocs serve
```

严格构建检查：

```bash
python -m mkdocs build --strict
```

## 目录说明

- `docs/`：四页 Markdown 文档源文件
- `mkdocs.yml`：站点与导航配置
- `.github/workflows/deploy.yml`：自动构建和部署工作流
- `report/`：个人实验报告与截图
- `site/`：构建产物，不提交到仓库
