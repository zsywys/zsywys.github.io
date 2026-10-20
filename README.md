# 章书莹 · 个人主页

一个纯静态页面（HTML + CSS + 原生 JS），不依赖任何框架和外部字体，国内打开也快。

```
个人主页/
├── index.html                      页面本体（场景、面板、阅读模式都在这里）
└── assets/
    ├── photo.jpg                   照片
    ├── favicon.svg                 浏览器标签图标
    └── zhang-shuying-resume.pdf    公开版简历（不含手机、微信、籍贯、出生年月）
```

## 本地预览

在“个人主页”文件夹里打开终端，运行：

```bash
python3 -m http.server 8000
```

然后浏览器打开 http://localhost:8000 。

## 部署到 GitHub Pages

1. 在 GitHub 新建一个公开仓库，名字必须是 `你的用户名.github.io`。
2. 把本文件夹里的 `index.html` 和整个 `assets/` 上传到仓库根目录（网页上点 “Add file → Upload files” 拖进去即可）。
3. 打开仓库 Settings → Pages，Source 选 “Deploy from a branch”，分支选 `main`、目录选 `/ (root)`，保存。
4. 等一两分钟，访问 `https://你的用户名.github.io`。

## 改内容

- **Skill 仓库链接**：打开 `index.html`，搜索 `var SKILL_REPO = ''`，把 GitHub 仓库地址填进引号里。填好后“Skill 库”面板会出现“在 GitHub 查看 Skill 库”按钮；留空则不显示。
- 文字内容：`index.html` 里 `<main id="content">` 下的 8 个 `<section>`（关于我、代表业绩、Skill 库、AI 工作流、工作经历、技能、教育背景、联系我）。房间面板和阅读模式共用这一份内容，改一处两边都变。
- harness 各组成的说明：搜索 `var LAYERS`。
- 房间场景：由脚本里的 `Scene` 用三维体块生成（`box` 画立方体、`decal` 把平面图案贴到墙面或桌面上）。每个可点物件对应一个 `hot('key', ...)` 调用，`key` 就是要打开的 section。
- 换简历：重新导出公开版 PDF，覆盖 `assets/zhang-shuying-resume.pdf`。

## 小功能

- 点桌上的台灯或右上角灯泡：开灯 / 关灯（夜景会亮起台灯、串灯、电脑屏幕和霓虹灯牌；默认跟随系统深浅色）。
- 鼠标在房间上移动，房间会跟着轻微转动；打开面板时房间会左移让位。
- 右上角“阅读模式”：不想点物件的人可以直接从头读到尾。
- 链接可以直接定位到某个面板，例如 `https://你的用户名.github.io/#ai` 会打开 AI 工作流。
