<div align="center">

# xrc.github.io

**个人主页 —— 基于 Academic Pages（Jekyll）搭建，托管于 GitHub Pages**

[![Pages](https://img.shields.io/badge/GitHub%20Pages-online-222?style=flat-square&logo=github)](https://xrc111.github.io/)
[![Jekyll](https://img.shields.io/badge/Jekyll-4.x-CC0000?style=flat-square&logo=jekyll)](https://jekyllrb.com/)
[![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)](./LICENSE)

</div>

---

## 简介

这是个人站点仓库，使用 [Academic Pages](https://github.com/academicpages/academicpages.github.io) 模板（Jekyll + Minimal Mistakes 衍生主题），通过 GitHub Pages 自动构建发布。

站点用于放置个人介绍、项目作品、文章与简历。

> **当前状态**：模板占位内容（`Your Name` / `Your Sidebar Name`）尚未替换，按下方「定制清单」逐项修改即可。

## 目录结构

```
.
├── _config.yml          # 站点全局配置（标题、作者、社交链接）
├── _data/
│   └── navigation.yml   # 顶部导航
├── _pages/              # 独立页面（关于、简历、作品集…）
├── _posts/              # 博客文章（Markdown）
├── _includes/           # 局部模板（作者卡片、页脚…）
├── _layouts/            # 页面布局
├── _sass/               # 样式变量与组件
├── assets/
│   ├── css/             # 主样式
│   ├── images/          # 图片（头像 profile.png 等）
│   └── js/
├── files/               # 可直接下载的 PDF / 附件
├── markdown_generator/  # 从 TSV 批量生成文章/出版物页面的脚本
├── Gemfile
└── _config.dev.yml      # 本地开发覆盖配置
```

## 本地预览

```bash
# 依赖：Ruby 3.x、Bundler、Node.js
bundle install
bundle exec jekyll serve -l -H 0.0.0.0
# 打开 http://localhost:4000
```

> 修改 `_config.yml` 后需要重启服务。若 `bundle install` 失败，删除 `Gemfile.lock` 重试。

## 部署

推送到 `main` 分支后，GitHub Pages 会自动构建（仓库 Settings → Pages → Source 选择 GitHub Actions / 分支）。

自定义域名：在 `_config.yml` 修改 `url`，并在仓库根目录添加 `CNAME` 文件。

## 定制清单

- [ ] `_config.yml`：`title` / `name` / `description` / `url` / `repository`
- [ ] `_config.yml` 的 `author`：头像、姓名、简介、所在地、单位、社交链接
- [ ] `_data/navigation.yml`：顶部导航项
- [ ] `_pages/about.md`：个人介绍
- [ ] `assets/images/profile.png`：头像
- [ ] `_pages/` 下的项目/简历页面
- [ ] `_posts/`：第一篇文章
- [ ] 删除模板自带的示例文章与图片

## 写作

新建文章：`_posts/YYYY-MM-DD-title.md`，头部字段：

```yaml
---
title: "文章标题"
date: 2026-01-01
categories: [笔记]
tags: [Jekyll, 前端]
---
```

批量生成（出版物/演讲）：`markdown_generator/` 下的 Python 脚本读取 TSV，输出 Markdown。

## 常见问题

| 问题 | 处理 |
| --- | --- |
| 本地 4000 端口被占用 | `bundle exec jekyll serve --port 4001` |
| 改了 `_config.yml` 不生效 | 重启 `jekyll serve` |
| 页面 404 | 检查 front matter 的 `permalink` 与文件名 |
| 样式没更新 | 清理 `_site/` 与浏览器缓存 |

## License

MIT。主题版权归 [Academic Pages](https://github.com/academicpages/academicpages.github.io) 与 [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) 作者所有。
