# 我的学术主页

基于 [al-folio](https://github.com/alshedivat/al-folio) 主题（Jekyll）构建的学术个人主页，
与 [sijie-yang.com](https://sijie-yang.com/) 同款技术栈。

> al-folio 官方原版 README 的中文要点已并入本文档；完整官方文档见 `docs/` 目录。

## 内容编辑指南

| 内容 | 文件位置 |
|------|----------|
| 姓名、站点标题、域名 | `_config.yml`（搜 `TODO`） |
| 个人简介（首页） | `_pages/about.md` |
| 头像照片 | `assets/img/prof_pic.jpg`（覆盖同名文件） |
| 社交链接（邮箱/Scholar/GitHub 等） | `_data/socials.yml` |
| 论文列表 | `_bibliography/papers.bib`（含字段说明注释） |
| 新闻动态（首页） | `_news/` 目录 |
| 博客文章 | `_posts/` 目录（文件名格式：`YYYY-MM-DD-标题.md`） |
| 项目展示 | `_projects/` 目录 |
| 简历（CV 页面） | `_data/cv.yml` |
| 导航栏页面开关 | 各页面头部的 `nav: true/false` |

## 本地预览

本机已安装 Ruby 3.3（`C:\Ruby33-x64`，已加入 PATH，新开终端生效），
项目依赖也已安装完毕。直接运行：

```bash
bundle exec jekyll serve
# 浏览器打开 http://localhost:4000
```

注意事项：

- **响应式图片已关闭**（`_config.yml` 中 `imagemagick.enabled: false`）：
  本地 Windows 没有 ImageMagick。Netlify 构建环境自带该工具，
  部署后想启用 WebP 自动优化可改回 `true`
- 博客中嵌入 `.ipynb` 需要 Python + jupyter（`pip install jupyter nbconvert`），
  示例 notebook 已删除，不影响正常使用

## 部署到 Netlify

1. 把本仓库推送到你的 GitHub：

   ```bash
   git remote add origin https://github.com/<你的用户名>/<仓库名>.git
   git push -u origin main
   ```

2. 打开 [Netlify](https://app.netlify.com) → **Add new site → Import an existing project**
   → 选择你的 GitHub 仓库
3. 构建配置已写在 `netlify.toml`，无需手动填写，直接点 **Deploy**
4. 部署完成后即可通过 `xxx.netlify.app` 访问；自定义域名在
   Netlify 的 **Domain settings** 中添加

## 更多定制

- 主题官方文档：`docs/CUSTOMIZE.md`、`docs/FAQ.md`
- 改主题色、暗色模式、评论区（giscus）等见 `docs/` 目录
