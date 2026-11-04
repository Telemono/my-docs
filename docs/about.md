# 关于本项目

## 项目目标

实现从 Markdown 文档到公开网站的自动化发布。

## 技术组成

| 工具 | 作用 |
| --- | --- |
| Markdown | 编写文档内容 |
| MkDocs Material | 将文档构建成静态网站 |
| GitHub Actions | 自动执行安装、构建和部署 |
| GitHub Pages | 托管并提供网站访问地址 |

## 从 Markdown 到网站

| 阶段 | 输入 | 输出 | 执行位置 |
| --- | --- | --- | --- |
| 编写 | Markdown 源文件 | `docs/*.md` | 本地 |
| 构建 | `mkdocs.yml` 和依赖 | `site/` 静态网站 | GitHub Actions |
| 部署 | `site/` artifact | GitHub Pages 网站 | GitHub Actions |

`site/` 是构建产物，每次构建都会重新生成，并且已被 `.gitignore` 忽略。需要修改内容时，只修改 `docs/` 中的 Markdown，不要手工修改或提交 `site/`。

## 我的实践体会

实践前我以为发布文档网站需要自己维护一个 `gh-pages` 分支。实际使用 GitHub 官方 Pages Actions 后，构建产物通过 artifact 上传，再由 `deploy-pages` 直接发布，整个流程不需要额外分支，也不需要手动填写访问令牌。

另外，`mkdocs build --strict` 会把导航路径、页面链接等警告当作错误处理。在推送前执行严格构建，可以提前发现大部分路径问题，避免线上出现 404。

## 相关页面

- 返回[首页](index.md)
- 查看[使用指南](guide.md)
- 查看[API 参考](api.md)