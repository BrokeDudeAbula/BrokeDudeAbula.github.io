# BrokeDudeAbula.github.io

TheDudeAbula 的个人站点，基于 [Jekyll](https://jekyllrb.com/) 与 [jekyll-theme-chirpy](https://github.com/cotes2020/jekyll-theme-chirpy)。

## 环境准备

- 需要本机安装 Ruby 与 Bundler。
- 安装依赖：`bundle install`。

## 本地开发

```bash
bundle exec jekyll serve
```

- 默认端口 `4000`，LiveReload 已启用。
- 站点以用户页根路径发布，本地访问地址为 `http://localhost:4000/`。

## 本地构建验证

```bash
bundle exec jekyll build --trace
```

出现构建异常时，`--trace` 会输出完整堆栈便于排查。

## 目录结构

- `_config.yml`：站点全局配置（`url`/`baseurl`、插件、集合等）。
- `_posts/`：博客正文，文件名遵循 `YYYY-MM-DD-title.md`。
- `_tabs/`：侧边栏页面（关于、分类、标签、归档、项目、游戏）。
- `_games/` + `_layouts/game.html` + `assets/js/games/`：HTML5 游戏集合。
- `_data/`：项目、联系方式和中文文案覆盖。
- `assets/css/jekyll-theme-chirpy.scss`：Chirpy 样式入口与站点覆盖。
- `assets/`：头像、文章附图、游戏脚本与静态演示。
- `_site/`：构建输出，勿提交。

## 内容与数据编辑

- 新文章放在 `_posts/`。Front Matter 最小字段：`title`、`date`；推荐补充 `categories`、`tags`、`excerpt`。
- 独立页面放在 `_tabs/`，由 `icon` 与 `order` 控制侧边栏显示。
- 项目列表由 `_data/projects.yml` 维护，`featured` 仅作数据标记，展示页在 `/projects/`。
- 自定义样式只追加在 `assets/css/jekyll-theme-chirpy.scss`，不要覆盖 Chirpy 的 `_includes/head.html`。

## 构建缓存清理

如遇到异常缓存，可运行 `./clean_cache.sh` 清理 `_site`、`.jekyll-cache`、`.sass-cache`、`vendor/bundle`。

## 部署说明

- 推送到 `main` 分支即可用于 GitHub Pages。当前为用户页：`url: https://brokedudeabula.github.io`，`baseurl: ""`，线上地址为 `https://brokedudeabula.github.io/`。
- 仓库 Pages 的 Source 必须设为 GitHub Actions。若设成 Deploy from a branch，线上会直接发布源码，首页只显示 `layout: home`。
- 若改用自定义域名，请同步调整 `_config.yml` 中的 `url`/`baseurl`，并在 README 更新访问路径说明。
