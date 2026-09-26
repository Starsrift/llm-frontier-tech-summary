# 大模型技术全景与系统学习手册

面向计算机研究生、算法工程师与 AI Infra 学习者的中文大模型学习网站。正文、样式和交互封装在 HTML 中，可本地离线阅读，也可通过 GitHub Pages 发布。

## 阅读

**在线网站：** https://starsrift.github.io/llm-frontier-tech-summary/

- 网站首页：`index.html`。
- 兼容原路径：`llm-tech-stack-handbook.html`，内容与首页保持一致。
- 本地使用：直接用浏览器打开任一 HTML 文件。
- 正文离线可用；论文、课程与官方文档链接需要联网访问。

页面提供章节导航、全文搜索、阅读进度、学习路线和 KV Cache 显存计算等功能。资料核验日期与内容边界以页面内说明为准。

## GitHub Pages 发布

工作流位于 [`.github/workflows/pages.yml`](.github/workflows/pages.yml)，使用 GitHub 官方 Pages Actions，无需安装 Node.js、npm 包或其他构建依赖。

1. 在 GitHub 创建仓库，将本项目文件推送到 `main` 分支。
2. 进入仓库的 **Settings → Pages → Build and deployment**，将 **Source** 设为 **GitHub Actions**。
3. 在 **Actions** 中运行 **Deploy handbook to GitHub Pages**，或推送 HTML 修改以自动触发发布。
4. 以成功部署任务输出的 `page_url` 为实际访问地址。普通项目站点地址为 `https://<用户名>.github.io/<仓库名>/`。

工作流只将两份 HTML 复制到 `_site`，再上传该目录。`ai-labs-timeline.html` 不属于本站点，不会被部署。工作流会检查两个入口内容一致，避免访客从不同路径看到不同版本。

更新时先修改 `llm-tech-stack-handbook.html`，再同步首页：

```sh
cp llm-tech-stack-handbook.html index.html
```

提交并推送后，可在仓库 **Actions** 页检查构建与部署结果。工作流成功且公开地址能够访问，才代表本次更新已上线。

## 内容与数据

- 本项目采用纯静态页面；无需配置 API Key 或后端服务。
- 阅读进度如被保存，存储在当前浏览器中，不跨设备同步。
- 论文、课程和代码的版权归各自作者或机构所有；外链用于学习与溯源。

GitHub 官方配置参考：[Using custom workflows with GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages)、[静态站点工作流模板](https://github.com/actions/starter-workflows/blob/main/pages/static.yml)。
