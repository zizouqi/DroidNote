# DroidNote

安卓手机使用与维护手册站点，基于 [Hugo](https://gohugo.io/) 与 [Hextra](https://imfing.github.io/hextra) 主题构建，通过 GitHub Actions 自动构建并发布至 GitHub Pages。

## 站点结构

- `hugo.yaml`：站点与 Hextra 主题配置
- `content/_index.md`：站点首页
- `content/docs/`：安卓手机使用与维护手册正文（按章节目录组织）
- `content/about.md`：关于与维护说明
- `.github/workflows/pages.yaml`：GitHub Pages 自动构建与部署工作流

## 本地预览

需要本地安装 **Hugo Extended (>= 0.146.0)** 与 **Go (>= 1.26)**：

```powershell
hugo server -D
```

启动后在浏览器访问 `http://localhost:1313/DroidNote/`。

## 部署到 GitHub Pages

1. 在 GitHub 创建仓库 `zizouqi/DroidNote`。
2. 在仓库 **Settings → Pages → Build and deployment** 中将 **Source** 设置为 **GitHub Actions**。
3. 将本地代码推送到 `main` 分支，GitHub Actions 会自动构建并发布到 `https://zizouqi.github.io/DroidNote/`。
