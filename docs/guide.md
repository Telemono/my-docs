# 使用指南

1. 修改 docs 目录中的 Markdown 文件。
2. 在本地预览并检查页面及链接。
3. 提交修改并推送到 main 分支。
4. 在 Actions 页面查看构建与部署状态。
5. 打开网站检查内容是否更新。

## 常用命令

- python -m mkdocs serve：本地预览。
- python -m mkdocs build --strict：构建网站并严格检查警告。

## 本地操作示例

在项目根目录创建虚拟环境：

```bash
python -m venv .venv
```

Windows PowerShell 激活虚拟环境：

```powershell
.\.venv\Scripts\Activate.ps1
```

如果 PowerShell 阻止脚本运行，可以改用 Git Bash 执行 `source .venv/Scripts/activate`，不需要修改系统执行策略。

安装依赖并启动预览：

```bash
python -m pip install -r requirements.txt
python -m mkdocs serve
```

浏览器打开终端显示的地址，通常为 `http://127.0.0.1:8000/my-docs/`。检查四页导航、表格、代码块和页面间链接，完成后按 `Ctrl+C` 停止预览。

## 构建与发布

推送前执行严格构建：

```bash
python -m mkdocs build --strict
```

`--strict` 会把警告当作错误。如果构建失败，应根据终端提示检查导航路径、页面链接或 Markdown 语法。

发布流程：

1. 修改 `docs/` 中的 Markdown 文件。
2. 本地预览并执行严格构建。
3. 提交并推送到 `main` 分支。
4. 在 Actions 页面查看 build 和 deploy 是否成功。
5. 刷新公开网站，确认内容已经更新。

工作流只会在 `docs/**`、`mkdocs.yml`、`requirements.txt` 或 `deploy.yml` 发生变化时自动运行。只修改报告或根目录 README 不会触发部署。

## 常见问题

| 现象 | 可能原因 | 处理方式 |
| --- | --- | --- |
| 本地预览打不开 | 虚拟环境未激活或依赖未安装 | 重新激活并安装依赖 |
| 页面出现 404 | 链接路径或文件名大小写错误 | 按 `--strict` 提示修正 |
| 推送后网站没变化 | Actions 未完成或浏览器缓存 | 查看 Actions，强制刷新或无痕访问 |
| PowerShell 无法激活 | 执行策略限制脚本 | 改用 Git Bash 激活 |

## 相关页面

- 返回[首页](index.md)
- 了解[项目背景](about.md)
- 查看[API 参考](api.md)