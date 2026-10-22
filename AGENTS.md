# AGENTS.md

## Project Type
Static HTML/CSS coursework. No build, no package manager, no tests. Each `.html` file is self-contained (inline styles or external `css.css`).

## Tech Stack
- Frontend uses native HTML, CSS, and JavaScript only. No third-party libraries, frameworks, or CDN resources.
- Icons use the local iconfont in the `font/` directory: `<link rel="stylesheet" href="font/iconfont.css">`, class usage `iconfont icon-xxx` (see `font/iconfont.json` for available icon names).
- Use the `fetch` API to get server-side data when needed.

## Naming
Pattern: `X-Y.html` (chapter-exercise) or `X-Y<topic>.html` (e.g., `5-1层叠与继承.html`, `7.2左图右文.html`). `1.HTML` uses uppercase extension.

## Naming
All CSS class names, id names, and JS variables must start with `syr_` (e.g., `syr_box`, `syr_title`).

## HTML Header Comment
Every `.html` page must include a comment with author name, date, and feature name:

```html
<!--
  姓名：桑英锐
  日期：YYYY-MM-DD
  功能名称：<topic>
-->
```

Place it right after the opening `<body>` tag (or before `</head>` if inside `<head>`).

## Navigation
Every newly created `.html` file must be added as a hyperlink in `index.html`. Keep `index.html` as the complete catalog of all coursework pages.

## Prompt Log
Before executing any task, append to `sang_prompt.md`: timestamp, model name, and prompt content. Never overwrite.

## Known Issues
- Chapter 13 pages (13-1, 13-2) still reference `cdn/` third-party icon libraries — kept for history, do not use as templates for new pages.

## Language
All page content in Chinese (zh-CN). Titles: `桑英锐 - <topic>`.

## Viewing
Open directly in browser. No dev server required.
