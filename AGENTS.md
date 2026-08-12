# AGENTS.md

Momo 是一个基于 Astro 5 的极简博客模板（本站：blog.muchstarlight.top）。环境为 Windows（Git Bash shell），包管理器为 **pnpm**。

## 常用命令

- `pnpm dev` — 开发服务器，端口 4321
- `pnpm build` — `astro build && pagefind --site dist`，输出到 `dist/`
- `pnpm preview` — 预览构建产物
- `pnpm newpost <path> [lang]` — 创建新文章脚手架，lang 为 `zh-cn`（默认）或 `en`

## 目录结构

- `src/content/blog/**/*.md` — 博客文章（loader 为 glob `**/[^_]*.md`，`_` 开头的文件会被忽略）；每篇文章一个文件夹，内含 `zh-cn.md` / `en.md`
- `src/content/spec/**/*.md` — 静态页面（关于等）
- `src/content.config.ts` — 文章 frontmatter schema：`title`、`pubDate`、`draft`、`description`、`image`、`slugId`（必填）、`category`、`pinTop`
- `src/components/` — 静态组件用 `.astro`，交互组件用 `.svelte`（TOC、评论、搜索、归档等）
- `src/plugins/` — 自定义 remark/rehype 插件，在 `astro.config.mjs` 中注册
- `src/i18n/` — 国际化文案（`key.ts`、`translation.ts`、`language/`）
- `src/pages/[...locale]/` — 本地化路由；默认语言 zh-cn **无** URL 前缀，en 在 `/en/` 下
- `src/config.ts` — 站点配置（siteConfig / profileConfig / licenseConfig / friendLinkConfig）
- `doc/` — 项目文档（`config_zh-cn.md`、`release_zh-cn.md`、`README_en.md`），改敏感区域前先读

## 注意事项 / 已知坑

- **`.astro/` 缓存目录**：移动或删除文章/图片后，残留缓存会导致 `ImageNotFound`（如 `heading_en.png`）类报错。修复方式：重启 dev server，必要时删除 `.astro/` 目录。
- **markdown 内的图片路径**（`![]()` 和 frontmatter `image:`）相对于文章所在目录解析，图片必须真实存在，否则 build 会失败。
- **`script/newpost.js` 生成的模板已过时**：它输出 `date` / `slug` 字段，但 schema 要求的是 `pubDate` / `slugId`，新文章需手动修正。
- 自定义 markdown 语法：KaTeX 数学、Typst（remark-typst）、admonition 提示块（note/tip/important/caution/warning）、`github`/`music`/`quote` 卡片组件、figure 图片标题、LQIP 占位图。
- 评论平台通过 `src/config.ts` 的 `siteConfig.comments` 配置：`default`（Momo-Backend）或 `twikoo`。
- 默认分支为 `main`；README 提到 `memos`、`v6` 等实验分支，与 main 可能不一致。当前工作分支为 `blog`。
