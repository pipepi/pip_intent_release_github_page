# Pip Intent 真机测试发布

此仓库仅保存静态构建产物，源码在 `pipepi/pip_intent`。

站点：https://pipepi.github.io/pip_intent_release_github_page/

## 首次启用

仓库 Settings → Pages → Build and deployment → Source 选择 GitHub Actions。
若首次自动部署已失败，在 Actions 中重新运行 Deploy Pip Intent preview。

## 更新静态内容

在源码仓库运行：

```sh
PAGES_BASE_PATH=/pip_intent_release_github_page/ node scripts/build-github-pages.mjs
```

将 `dist/pages/` 完整同步到本仓库 `public/`，提交并推送 `main`。
部署工作流只上传 `public/`。不要复制源码目录、SSH 密钥、开发环境配置或本地用户数据。

## 真机测试范围

支持官网 A5 自动加载、深浅主题、投影导航、手势、表单及浏览器本地工作空间。
手机与电脑的数据分别保存在各自浏览器，不会自动同步。
需要 Rust/本机服务或外部 API 的功能不由 GitHub Pages 提供。
